<template>
  <naver-maps
    width="800px"
    height="800px"
    :mapOptions="mapOptions"
    :initLayers="initLayers"
    @onLoad="onLoadMap($event)"
  >
  </naver-maps>
</template>

<script>
import { ref } from "vue";
import { NaverMaps } from "vue3-naver-maps";

export default {
  components: { NaverMaps },
  setup: () => {
    const map = ref();
    const mapOptions = {
      latitude: 37.56663888630603, // 지도 중앙 위도
      longitude: 126.97838310403904, // 지도 중앙 경도
      zoom: 16,
      zoomControl: false,
      zoomControlOptions: { position: "TOP_RIGHT" },
    };
    const initLayers = [
      "BACKGROUND",
      "BACKGROUND_DETAIL",
      "POI_KOREAN",
      "TRANSIT",
      "ENGLISH",
    ];

    const onLoadMap = (mapObject) => {
      map.value = mapObject;
    };

    return {
      map,
      mapOptions,
      initLayers,
      onLoadMap,
    };
  },
};
</script>