# CreatePsDec

- ea: `0x180042430`
- end: `0x180043026`
- name: `CreatePsDec`
- size: `3062`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180039380`

## callees

- `0x1800021a8`
- `0x180042430`
- `0x180048f00`

## pseudocode

```c
__int64 __fastcall CreatePsDec(__int64 a1, _OWORD *a2, int a3)
{
  __int64 v6; // r8
  __int64 result; // rax
  _OWORD *v8; // rcx
  __int64 v9; // rdx
  _OWORD *v10; // r12
  _OWORD *v11; // r15
  int v12; // r14d
  __int64 v13; // rbp
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
  size_t v17; // rdi
  __int64 v18; // rbx
  int v19; // r10d
  __int64 v20; // r9
  _OWORD *v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r9
  _OWORD *v24; // rcx
  _OWORD *v25; // rcx
  char *v26; // r8
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rax
  int v30; // r10d
  __int64 v31; // r9
  _OWORD *v32; // r8
  _OWORD *v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r9
  _OWORD *v36; // rcx
  _OWORD *v37; // rcx
  __int64 v38; // r8
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rax
  int v42; // r10d
  __int64 v43; // r9
  __int64 v44; // r8
  __int64 v45; // r8
  __int64 v46; // rdx
  __int64 v47; // r9
  _OWORD *v48; // rcx
  _OWORD *v49; // rcx
  __int64 v50; // r8
  __int64 v51; // rcx
  __int64 v52; // rcx
  _OWORD *v53; // [rsp+78h] [rbp+20h] BYREF

  memset_0((void *)a1, 0, 0x4E30u);
  if ( !a3 )
    return 1;
  *(_QWORD *)(a1 + 2184) = a2 + 3456;
  *(_DWORD *)(a1 + 4) = a3;
  *(float *)(a1 + 8) = 1.0 / (float)a3;
  a2[3456] = 0;
  a2[3457] = 0;
  a2[3458] = 0;
  a2[3459] = 0;
  a2[3460] = 0;
  *(_QWORD *)(a1 + 2192) = a2 + 3461;
  a2[3461] = 0;
  v53 = a2 + 3471;
  a2[3462] = 0;
  a2[3463] = 0;
  a2[3464] = 0;
  a2[3465] = 0;
  *(_QWORD *)(a1 + 2200) = a2 + 3466;
  a2[3466] = 0;
  a2[3467] = 0;
  a2[3468] = 0;
  a2[3469] = 0;
  a2[3470] = 0;
  result = CreateHybridFilterBank(a1 + 2240, a2 + 3466, v6, &v53);
  if ( !(_DWORD)result )
  {
    v8 = v53;
    *(_QWORD *)(a1 + 2208) = v53;
    v9 = (__int64)v8 + 40;
    v10 = a2 + 2100;
    *v8 = 0;
    v8[1] = 0;
    *((_QWORD *)v8 + 4) = 0;
    *(_QWORD *)(a1 + 2216) = (char *)v8 + 40;
    *(_OWORD *)((char *)v8 + 40) = 0;
    v11 = a2 + 2004;
    *(_OWORD *)((char *)v8 + 56) = 0;
    *((_QWORD *)v8 + 9) = 0;
    v8 = (_OWORD *)((char *)v8 + 120);
    *(_QWORD *)(a1 + 2224) = v9 + 40;
    *(_OWORD *)(v9 + 40) = 0;
    *(_OWORD *)(v9 + 56) = 0;
    *(_QWORD *)(v9 + 72) = 0;
    *(_QWORD *)(a1 + 2232) = v9 + 80;
    v9 += 120;
    *v8 = 0;
    v8[1] = 0;
    *((_QWORD *)v8 + 4) = 0;
    *(_DWORD *)(a1 + 2024) = 0;
    *(_QWORD *)(a1 + 2248) = 0;
    *(_DWORD *)(a1 + 2412) = 14;
    *(_DWORD *)(a1 + 2416) = 14;
    *(_QWORD *)(a1 + 2256) = 0;
    *(_DWORD *)(a1 + 2420) = 14;
    *(_DWORD *)(a1 + 2424) = 14;
    *(_QWORD *)(a1 + 2264) = 0;
    *(_DWORD *)(a1 + 2428) = 14;
    *(_DWORD *)(a1 + 2432) = 14;
    *(_QWORD *)(a1 + 2272) = 0;
    *(_DWORD *)(a1 + 2436) = 14;
    *(_DWORD *)(a1 + 2440) = 14;
    *(_QWORD *)(a1 + 2280) = 0;
    *(_DWORD *)(a1 + 2444) = 14;
    *(_DWORD *)(a1 + 2448) = 14;
    *(_QWORD *)(a1 + 2288) = 0;
    *(_DWORD *)(a1 + 2452) = 14;
    *(_DWORD *)(a1 + 2456) = 14;
    *(_QWORD *)(a1 + 2296) = 0;
    *(_DWORD *)(a1 + 2460) = 1;
    *(_DWORD *)(a1 + 2464) = 1;
    *(_QWORD *)(a1 + 2304) = 0;
    *(_DWORD *)(a1 + 2468) = 1;
    *(_DWORD *)(a1 + 2472) = 1;
    *(_QWORD *)(a1 + 2312) = 0;
    *(_DWORD *)(a1 + 2476) = 1;
    *(_DWORD *)(a1 + 2480) = 1;
    *(_QWORD *)(a1 + 2320) = 0;
    *(_DWORD *)(a1 + 2484) = 1;
    *(_DWORD *)(a1 + 2488) = 1;
    *(_QWORD *)(a1 + 2328) = 0;
    *(_DWORD *)(a1 + 2492) = 1;
    *(_DWORD *)(a1 + 2496) = 1;
    *(_QWORD *)(a1 + 2336) = 0;
    *(_DWORD *)(a1 + 2500) = 1;
    *(_DWORD *)(a1 + 2504) = 1;
    *(_QWORD *)(a1 + 2344) = 0;
    *(_DWORD *)(a1 + 2508) = 1;
    *(_DWORD *)(a1 + 2512) = 1;
    *(_QWORD *)(a1 + 2352) = 0;
    *(_DWORD *)(a1 + 2516) = 1;
    *(_DWORD *)(a1 + 2520) = 1;
    *(_QWORD *)(a1 + 2360) = 0;
    *(_DWORD *)(a1 + 2524) = 1;
    *(_DWORD *)(a1 + 2528) = 1;
    *(_QWORD *)(a1 + 2368) = 0;
    *(_DWORD *)(a1 + 2532) = 1;
    *(_DWORD *)(a1 + 2536) = 1;
    *(_QWORD *)(a1 + 2376) = 0;
    v12 = 0;
    *(_DWORD *)(a1 + 2540) = 1;
    v13 = 0;
    *(_DWORD *)(a1 + 2544) = 1;
    *(_QWORD *)(a1 + 2384) = 0;
    *(_DWORD *)(a1 + 2548) = 1;
    *(_DWORD *)(a1 + 2552) = 1;
    *(_QWORD *)(a1 + 2392) = 0;
    *(_DWORD *)(a1 + 2556) = 1;
    *(_DWORD *)(a1 + 2560) = 1;
    *(_QWORD *)(a1 + 2400) = 0;
    *(_DWORD *)(a1 + 2564) = 1;
    *(_DWORD *)(a1 + 2568) = 1;
    *(_DWORD *)(a1 + 2408) = 0;
    *(_DWORD *)(a1 + 2572) = 1;
    *(_QWORD *)(a1 + 2032) = a2 + 3744;
    *(_QWORD *)(a1 + 2040) = a2 + 3872;
    *(_QWORD *)(a1 + 2176) = v9 + 80;
    v14 = v9 + 160;
    *(_QWORD *)(a1 + 2168) = v9;
    do
    {
      v15 = *(_QWORD *)(a1 + 2032);
      if ( (unsigned int)v12 >= 0x14 )
      {
        v16 = *(int *)(a1 + 4 * v13 + 2332);
        *(_QWORD *)(v15 + 8 * v13) = v14;
        v17 = 4 * v16;
        v18 = 4 * v16 + v14;
        memset_0(*(void **)(*(_QWORD *)(a1 + 2032) + 8 * v13), 0, 4 * v16);
        *(_QWORD *)(*(_QWORD *)(a1 + 2040) + 8 * v13) = v18;
        v14 = v17 + v18;
        memset_0(*(void **)(*(_QWORD *)(a1 + 2040) + 8 * v13), 0, v17);
      }
      else
      {
        *(_QWORD *)(v15 + 8 * v13) = v11;
        v11 = (_OWORD *)((char *)v11 + 8);
        **(_QWORD **)(*(_QWORD *)(a1 + 2032) + 8 * v13) = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 2040) + 8 * v13) = v10;
        v10 = (_OWORD *)((char *)v10 + 8);
        **(_QWORD **)(*(_QWORD *)(a1 + 2040) + 8 * v13) = 0;
      }
      ++v12;
      ++v13;
    }
    while ( v12 < 61 );
    **(_QWORD **)(a1 + 2168) = v14;
    ***(_QWORD ***)(a1 + 2168) = 0;
    **(_QWORD **)(a1 + 2176) = v14 + 8;
    ***(_QWORD ***)(a1 + 2176) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2168) + 8LL) = v14 + 16;
    **(_QWORD **)(*(_QWORD *)(a1 + 2168) + 8LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2176) + 8LL) = v14 + 24;
    **(_QWORD **)(*(_QWORD *)(a1 + 2176) + 8LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2168) + 16LL) = v14 + 32;
    **(_QWORD **)(*(_QWORD *)(a1 + 2168) + 16LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2176) + 16LL) = v14 + 40;
    **(_QWORD **)(*(_QWORD *)(a1 + 2176) + 16LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2168) + 24LL) = v14 + 48;
    **(_QWORD **)(*(_QWORD *)(a1 + 2168) + 24LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2176) + 24LL) = v14 + 56;
    **(_QWORD **)(*(_QWORD *)(a1 + 2176) + 24LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2168) + 32LL) = v14 + 64;
    **(_QWORD **)(*(_QWORD *)(a1 + 2168) + 32LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2176) + 32LL) = v14 + 72;
    **(_QWORD **)(*(_QWORD *)(a1 + 2176) + 32LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2168) + 40LL) = v14 + 80;
    **(_QWORD **)(*(_QWORD *)(a1 + 2168) + 40LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2176) + 40LL) = v14 + 88;
    **(_QWORD **)(*(_QWORD *)(a1 + 2176) + 40LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2168) + 48LL) = v14 + 96;
    **(_QWORD **)(*(_QWORD *)(a1 + 2168) + 48LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2176) + 48LL) = v14 + 104;
    **(_QWORD **)(*(_QWORD *)(a1 + 2176) + 48LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2168) + 56LL) = v14 + 112;
    **(_QWORD **)(*(_QWORD *)(a1 + 2168) + 56LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2176) + 56LL) = v14 + 120;
    **(_QWORD **)(*(_QWORD *)(a1 + 2176) + 56LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2168) + 64LL) = v14 + 128;
    **(_QWORD **)(*(_QWORD *)(a1 + 2168) + 64LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2176) + 64LL) = v14 + 136;
    **(_QWORD **)(*(_QWORD *)(a1 + 2176) + 64LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2168) + 72LL) = v14 + 144;
    **(_QWORD **)(*(_QWORD *)(a1 + 2168) + 72LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 2176) + 72LL) = v14 + 152;
    **(_QWORD **)(*(_QWORD *)(a1 + 2176) + 72LL) = 0;
    _mm_lfence();
    *(_DWORD *)(a1 + 2060) = 3;
    *(_DWORD *)(a1 + 2048) = 0;
    v19 = 0;
    *(_QWORD *)(a1 + 2072) = a1 + 5680;
    *(_QWORD *)(a1 + 2096) = a1 + 5704;
    *(_QWORD *)(a1 + 2120) = a2 + 320;
    v20 = a1 + 5728;
    *(_QWORD *)(a1 + 2144) = (char *)a2 + 5144;
    v21 = a2 + 323;
    do
    {
      v22 = v19++;
      *(_QWORD *)(*(_QWORD *)(a1 + 2072) + 8 * v22) = v20;
      v23 = v20 + 80;
      v24 = *(_OWORD **)(*(_QWORD *)(a1 + 2072) + 8 * v22);
      *v24 = 0;
      v24[1] = 0;
      v24[2] = 0;
      v24[3] = 0;
      v24[4] = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 2096) + 8 * v22) = v23;
      v20 = v23 + 80;
      v25 = *(_OWORD **)(*(_QWORD *)(a1 + 2096) + 8 * v22);
      *v25 = 0;
      v25[1] = 0;
      v25[2] = 0;
      v25[3] = 0;
      v25[4] = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 2120) + 8 * v22) = v21;
      v26 = (char *)v21 + 40;
      v27 = *(_QWORD *)(*(_QWORD *)(a1 + 2120) + 8 * v22);
      *(_OWORD *)v27 = 0;
      *(_OWORD *)(v27 + 16) = 0;
      *(_QWORD *)(v27 + 32) = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 2144) + 8 * v22) = v26;
      v21 = v26 + 40;
      v28 = *(_QWORD *)(*(_QWORD *)(a1 + 2144) + 8 * v22);
      *(_OWORD *)v28 = 0;
      *(_OWORD *)(v28 + 16) = 0;
      *(_QWORD *)(v28 + 32) = 0;
    }
    while ( v19 < *(_DWORD *)(a1 + 2060) );
    *(_DWORD *)(a1 + 2052) = 0;
    v29 = v20 + 32;
    *(_DWORD *)(a1 + 2064) = 4;
    v30 = 0;
    *(_QWORD *)(a1 + 2080) = v20;
    v31 = v20 + 64;
    *(_QWORD *)(a1 + 2104) = v29;
    *(_QWORD *)(a1 + 2128) = v21;
    v32 = v21 + 2;
    *(_QWORD *)(a1 + 2152) = v32;
    v33 = v32 + 2;
    do
    {
      v34 = v30++;
      *(_QWORD *)(*(_QWORD *)(a1 + 2080) + 8 * v34) = v31;
      v35 = v31 + 80;
      v36 = *(_OWORD **)(*(_QWORD *)(a1 + 2080) + 8 * v34);
      *v36 = 0;
      v36[1] = 0;
      v36[2] = 0;
      v36[3] = 0;
      v36[4] = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 2104) + 8 * v34) = v35;
      v31 = v35 + 80;
      v37 = *(_OWORD **)(*(_QWORD *)(a1 + 2104) + 8 * v34);
      *v37 = 0;
      v37[1] = 0;
      v37[2] = 0;
      v37[3] = 0;
      v37[4] = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 2128) + 8 * v34) = v33;
      v38 = (__int64)v33 + 40;
      v39 = *(_QWORD *)(*(_QWORD *)(a1 + 2128) + 8 * v34);
      *(_OWORD *)v39 = 0;
      *(_OWORD *)(v39 + 16) = 0;
      *(_QWORD *)(v39 + 32) = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 2152) + 8 * v34) = v38;
      v33 = (_OWORD *)(v38 + 40);
      v40 = *(_QWORD *)(*(_QWORD *)(a1 + 2152) + 8 * v34);
      *(_OWORD *)v40 = 0;
      *(_OWORD *)(v40 + 16) = 0;
      *(_QWORD *)(v40 + 32) = 0;
    }
    while ( v30 < *(_DWORD *)(a1 + 2064) );
    *(_DWORD *)(a1 + 2056) = 0;
    v41 = v31 + 40;
    *(_DWORD *)(a1 + 2068) = 5;
    v42 = 0;
    *(_QWORD *)(a1 + 2088) = v31;
    v43 = v31 + 80;
    *(_QWORD *)(a1 + 2112) = v41;
    *(_QWORD *)(a1 + 2136) = v33;
    v44 = (__int64)v33 + 40;
    *(_QWORD *)(a1 + 2160) = v44;
    v45 = v44 + 40;
    do
    {
      v46 = v42++;
      *(_QWORD *)(*(_QWORD *)(a1 + 2088) + 8 * v46) = v43;
      v47 = v43 + 80;
      v48 = *(_OWORD **)(*(_QWORD *)(a1 + 2088) + 8 * v46);
      *v48 = 0;
      v48[1] = 0;
      v48[2] = 0;
      v48[3] = 0;
      v48[4] = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 2112) + 8 * v46) = v47;
      v43 = v47 + 80;
      v49 = *(_OWORD **)(*(_QWORD *)(a1 + 2112) + 8 * v46);
      *v49 = 0;
      v49[1] = 0;
      v49[2] = 0;
      v49[3] = 0;
      v49[4] = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 2136) + 8 * v46) = v45;
      v50 = v45 + 40;
      v51 = *(_QWORD *)(*(_QWORD *)(a1 + 2136) + 8 * v46);
      *(_OWORD *)v51 = 0;
      *(_OWORD *)(v51 + 16) = 0;
      *(_QWORD *)(v51 + 32) = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 2160) + 8 * v46) = v50;
      v45 = v50 + 40;
      v52 = *(_QWORD *)(*(_QWORD *)(a1 + 2160) + 8 * v46);
      *(_OWORD *)v52 = 0;
      *(_OWORD *)(v52 + 16) = 0;
      *(_QWORD *)(v52 + 32) = 0;
    }
    while ( v42 < *(_DWORD *)(a1 + 2068) );
    *(_DWORD *)(a1 + 2576) = 1065353216;
    *(_DWORD *)(a1 + 2664) = 1065353216;
    *(_DWORD *)(a1 + 2580) = 1065353216;
    *(_DWORD *)(a1 + 2668) = 1065353216;
    *(_DWORD *)(a1 + 2584) = 1065353216;
    *(_DWORD *)(a1 + 2672) = 1065353216;
    *(_DWORD *)(a1 + 2588) = 1065353216;
    *(_DWORD *)(a1 + 2676) = 1065353216;
    *(_DWORD *)(a1 + 2592) = 1065353216;
    *(_DWORD *)(a1 + 2680) = 1065353216;
    *(_DWORD *)(a1 + 2596) = 1065353216;
    *(_DWORD *)(a1 + 2684) = 1065353216;
    *(_DWORD *)(a1 + 2600) = 1065353216;
    *(_DWORD *)(a1 + 2688) = 1065353216;
    *(_DWORD *)(a1 + 2604) = 1065353216;
    *(_DWORD *)(a1 + 2692) = 1065353216;
    *(_DWORD *)(a1 + 2608) = 1065353216;
    *(_DWORD *)(a1 + 2696) = 1065353216;
    *(_DWORD *)(a1 + 2612) = 1065353216;
    *(_DWORD *)(a1 + 2700) = 1065353216;
    *(_DWORD *)(a1 + 2616) = 1065353216;
    *(_DWORD *)(a1 + 2704) = 1065353216;
    *(_DWORD *)(a1 + 2620) = 1065353216;
    *(_DWORD *)(a1 + 2708) = 1065353216;
    *(_DWORD *)(a1 + 2624) = 1065353216;
    *(_DWORD *)(a1 + 2712) = 1065353216;
    *(_DWORD *)(a1 + 2628) = 1065353216;
    *(_DWORD *)(a1 + 2716) = 1065353216;
    *(_DWORD *)(a1 + 2632) = 1065353216;
    *(_DWORD *)(a1 + 2720) = 1065353216;
    *(_DWORD *)(a1 + 2636) = 1065353216;
    *(_DWORD *)(a1 + 2724) = 1065353216;
    *(_DWORD *)(a1 + 2640) = 1065353216;
    *(_DWORD *)(a1 + 2728) = 1065353216;
    *(_DWORD *)(a1 + 2644) = 1065353216;
    *(_DWORD *)(a1 + 2732) = 1065353216;
    *(_DWORD *)(a1 + 2648) = 1065353216;
    *(_DWORD *)(a1 + 2736) = 1065353216;
    *(_DWORD *)(a1 + 2652) = 1065353216;
    *(_DWORD *)(a1 + 2740) = 1065353216;
    *(_DWORD *)(a1 + 2656) = 1065353216;
    *(_DWORD *)(a1 + 2744) = 1065353216;
    *(_DWORD *)(a1 + 2660) = 1065353216;
    *(_DWORD *)(a1 + 2748) = 1065353216;
    *(_OWORD *)(a1 + 2752) = 0;
    *(_OWORD *)(a1 + 2768) = 0;
    *(_OWORD *)(a1 + 2784) = 0;
    *(_OWORD *)(a1 + 2800) = 0;
    *(_OWORD *)(a1 + 2816) = 0;
    *(_QWORD *)(a1 + 2832) = 0;
    *(_OWORD *)(a1 + 2840) = 0;
    *(_OWORD *)(a1 + 2856) = 0;
    *(_OWORD *)(a1 + 2872) = 0;
    *(_OWORD *)(a1 + 2888) = 0;
    *(_OWORD *)(a1 + 2904) = 0;
    *(_QWORD *)(a1 + 2920) = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180042430  push    rbx
0x180042432  push    rsi
0x180042433  push    r13
0x180042435  sub     rsp, 40h
0x180042439  mov     ebx, r8d
0x18004243c  mov     r13, rdx
0x18004243f  xor     edx, edx; Val
0x180042441  mov     r8d, 4E30h; Size
0x180042447  mov     rsi, rcx
0x18004244a  call    memset_0
0x18004244f  test    ebx, ebx
0x180042451  jnz     short loc_180042462
0x180042453  mov     eax, 1
0x180042458  add     rsp, 40h
0x18004245c  pop     r13
0x18004245e  pop     rsi
0x18004245f  pop     rbx
0x180042460  retn
0x180042462  movss   xmm1, cs:__real@3f800000
0x18004246a  lea     rax, [r13+0D800h]
0x180042471  mov     [rsi+888h], rax
0x180042478  lea     rcx, [rax+50h]
0x18004247c  mov     [rsi+4], ebx
0x18004247f  lea     rdx, [rcx+50h]
0x180042483  xorps   xmm0, xmm0
0x180042486  lea     r9, [rsp+58h+arg_18]
0x18004248b  cvtsi2ss xmm0, rbx
0x180042490  divss   xmm1, xmm0
0x180042494  xorps   xmm0, xmm0
0x180042497  movss   dword ptr [rsi+8], xmm1
0x18004249c  movups  xmmword ptr [rax], xmm0
0x18004249f  movups  xmmword ptr [rax+10h], xmm0
0x1800424a3  movups  xmmword ptr [rax+20h], xmm0
0x1800424a7  movups  xmmword ptr [rax+30h], xmm0
0x1800424ab  movups  xmmword ptr [rax+40h], xmm0
0x1800424af  mov     [rsi+890h], rcx
0x1800424b6  lea     rax, [rdx+50h]
0x1800424ba  movups  xmmword ptr [rcx], xmm0
0x1800424bd  mov     [rsp+58h+arg_18], rax
0x1800424c2  movups  xmmword ptr [rcx+10h], xmm0
0x1800424c6  movups  xmmword ptr [rcx+20h], xmm0
0x1800424ca  movups  xmmword ptr [rcx+30h], xmm0
0x1800424ce  movups  xmmword ptr [rcx+40h], xmm0
0x1800424d2  mov     [rsi+898h], rdx
0x1800424d9  lea     rcx, [rsi+8C0h]
0x1800424e0  movups  xmmword ptr [rdx], xmm0
0x1800424e3  movups  xmmword ptr [rdx+10h], xmm0
0x1800424e7  movups  xmmword ptr [rdx+20h], xmm0
0x1800424eb  movups  xmmword ptr [rdx+30h], xmm0
0x1800424ef  movups  xmmword ptr [rdx+40h], xmm0
0x1800424f3  call    CreateHybridFilterBank
0x1800424f8  mov     [rsp+58h+arg_10], eax
0x1800424fc  test    eax, eax
0x1800424fe  jnz     loc_18004301C
0x180042504  mov     rcx, [rsp+58h+arg_18]
0x180042509  xorps   xmm0, xmm0
0x18004250c  mov     [rsi+8A0h], rcx
0x180042513  lea     rdx, [rcx+28h]
0x180042517  xor     eax, eax
0x180042519  mov     [rsp+58h+arg_0], rbp
0x18004251e  mov     [rsp+58h+var_28], r12
0x180042523  lea     r12, [r13+8340h]
0x18004252a  movups  xmmword ptr [rcx], xmm0
0x18004252d  mov     [rsp+58h+var_30], r14
0x180042532  movups  xmmword ptr [rcx+10h], xmm0
0x180042536  mov     [rcx+20h], rax
0x18004253a  lea     rax, [rdx+28h]
0x18004253e  mov     [rsi+8A8h], rdx
0x180042545  xor     ecx, ecx
0x180042547  movups  xmmword ptr [rdx], xmm0
0x18004254a  mov     [rsp+58h+var_38], r15
0x18004254f  lea     r15, [r13+7D40h]
0x180042556  movups  xmmword ptr [rdx+10h], xmm0
0x18004255a  mov     [rdx+20h], rcx
0x18004255e  lea     rcx, [rax+28h]
0x180042562  mov     [rsi+8B0h], rax
0x180042569  xor     edx, edx
0x18004256b  movups  xmmword ptr [rax], xmm0
0x18004256e  movups  xmmword ptr [rax+10h], xmm0
0x180042572  mov     [rax+20h], rdx
0x180042576  xor     eax, eax
0x180042578  mov     [rsi+8B8h], rcx
0x18004257f  lea     rdx, [rcx+28h]
0x180042583  movups  xmmword ptr [rcx], xmm0
0x180042586  movups  xmmword ptr [rcx+10h], xmm0
0x18004258a  mov     [rcx+20h], rax
0x18004258e  xor     ecx, ecx
0x180042590  mov     [rsi+7E8h], ecx
0x180042596  mov     [rsi+8C8h], rcx
0x18004259d  mov     dword ptr [rsi+96Ch], 0Eh
0x1800425a7  mov     dword ptr [rsi+970h], 0Eh
0x1800425b1  mov     [rsi+8D0h], rcx
0x1800425b8  mov     dword ptr [rsi+974h], 0Eh
0x1800425c2  mov     dword ptr [rsi+978h], 0Eh
0x1800425cc  mov     [rsi+8D8h], rcx
0x1800425d3  mov     dword ptr [rsi+97Ch], 0Eh
0x1800425dd  mov     dword ptr [rsi+980h], 0Eh
0x1800425e7  mov     [rsi+8E0h], rcx
0x1800425ee  mov     dword ptr [rsi+984h], 0Eh
0x1800425f8  mov     dword ptr [rsi+988h], 0Eh
0x180042602  mov     [rsi+8E8h], rcx
0x180042609  mov     dword ptr [rsi+98Ch], 0Eh
0x180042613  mov     dword ptr [rsi+990h], 0Eh
0x18004261d  mov     [rsi+8F0h], rcx
0x180042624  mov     dword ptr [rsi+994h], 0Eh
0x18004262e  mov     dword ptr [rsi+998h], 0Eh
0x180042638  mov     [rsi+8F8h], rcx
0x18004263f  mov     dword ptr [rsi+99Ch], 1
0x180042649  mov     dword ptr [rsi+9A0h], 1
0x180042653  mov     [rsi+900h], rcx
0x18004265a  mov     dword ptr [rsi+9A4h], 1
0x180042664  mov     dword ptr [rsi+9A8h], 1
0x18004266e  mov     [rsi+908h], rcx
0x180042675  mov     dword ptr [rsi+9ACh], 1
0x18004267f  mov     dword ptr [rsi+9B0h], 1
0x180042689  mov     [rsi+910h], rcx
0x180042690  mov     dword ptr [rsi+9B4h], 1
0x18004269a  mov     dword ptr [rsi+9B8h], 1
0x1800426a4  mov     [rsi+918h], rcx
0x1800426ab  mov     dword ptr [rsi+9BCh], 1
0x1800426b5  mov     dword ptr [rsi+9C0h], 1
0x1800426bf  mov     [rsi+920h], rcx
0x1800426c6  mov     dword ptr [rsi+9C4h], 1
0x1800426d0  mov     dword ptr [rsi+9C8h], 1
0x1800426da  mov     [rsi+928h], rcx
0x1800426e1  mov     dword ptr [rsi+9CCh], 1
0x1800426eb  mov     dword ptr [rsi+9D0h], 1
0x1800426f5  mov     [rsi+930h], rcx
0x1800426fc  mov     dword ptr [rsi+9D4h], 1
0x180042706  mov     dword ptr [rsi+9D8h], 1
0x180042710  mov     [rsi+938h], rcx
0x180042717  mov     dword ptr [rsi+9DCh], 1
0x180042721  mov     dword ptr [rsi+9E0h], 1
0x18004272b  mov     [rsi+940h], rcx
0x180042732  mov     dword ptr [rsi+9E4h], 1
0x18004273c  mov     dword ptr [rsi+9E8h], 1
0x180042746  lea     rax, [r13+0EA00h]
0x18004274d  mov     [rsi+948h], rcx
0x180042754  mov     r14d, ecx
0x180042757  mov     dword ptr [rsi+9ECh], 1
0x180042761  mov     ebp, ecx
0x180042763  mov     dword ptr [rsi+9F0h], 1
0x18004276d  mov     [rsi+950h], rcx
0x180042774  mov     dword ptr [rsi+9F4h], 1
0x18004277e  mov     dword ptr [rsi+9F8h], 1
0x180042788  mov     [rsi+958h], rcx
0x18004278f  mov     dword ptr [rsi+9FCh], 1
0x180042799  mov     dword ptr [rsi+0A00h], 1
0x1800427a3  mov     [rsi+960h], rcx
0x1800427aa  mov     dword ptr [rsi+0A04h], 1
0x1800427b4  mov     dword ptr [rsi+0A08h], 1
0x1800427be  mov     [rsi+968h], ecx
0x1800427c4  mov     dword ptr [rsi+0A0Ch], 1
0x1800427ce  mov     [rsi+7F0h], rax
0x1800427d5  lea     rax, [r13+0F200h]
0x1800427dc  mov     [rsi+7F8h], rax
0x1800427e3  lea     rax, [rdx+50h]
0x1800427e7  mov     [rsi+880h], rax
0x1800427ee  lea     rbx, [rax+50h]
0x1800427f2  mov     [rsi+878h], rdx
0x1800427f9  mov     [rsp+58h+var_20], rdi
0x1800427fe  xchg    ax, ax
0x180042800  mov     rax, [rsi+7F0h]
0x180042807  cmp     r14d, 14h
0x18004280b  jnb     short loc_180042844
0x18004280d  mov     [rax+rbp*8], r15
0x180042811  xor     ecx, ecx
0x180042813  mov     rax, [rsi+7F0h]
0x18004281a  add     r15, 8
0x18004281e  mov     rax, [rax+rbp*8]
0x180042822  mov     [rax], rcx
0x180042825  mov     rax, [rsi+7F8h]
0x18004282c  mov     [rax+rbp*8], r12
0x180042830  add     r12, 8
0x180042834  mov     rax, [rsi+7F8h]
0x18004283b  mov     rax, [rax+rbp*8]
0x18004283f  mov     [rax], rcx
0x180042842  jmp     short loc_180042893
0x180042844  movsxd  rcx, dword ptr [rsi+rbp*4+91Ch]
0x18004284c  xor     edx, edx; Val
0x18004284e  mov     [rax+rbp*8], rbx
0x180042852  lea     rdi, ds:0[rcx*4]
0x18004285a  mov     rcx, [rsi+7F0h]
0x180042861  mov     r8, rdi; Size
0x180042864  add     rbx, rdi
0x180042867  mov     rcx, [rcx+rbp*8]; void *
0x18004286b  call    memset_0
0x180042870  mov     rax, [rsi+7F8h]
0x180042877  mov     r8, rdi; Size
0x18004287a  xor     edx, edx; Val
0x18004287c  mov     [rax+rbp*8], rbx
0x180042880  add     rbx, rdi
0x180042883  mov     rcx, [rsi+7F8h]
0x18004288a  mov     rcx, [rcx+rbp*8]; void *
0x18004288e  call    memset_0
0x180042893  inc     r14d
0x180042896  inc     rbp
0x180042899  cmp     r14d, 3Dh ; '='
0x18004289d  jl      loc_180042800
0x1800428a3  mov     rax, [rsi+878h]
0x1800428aa  lea     rcx, [rbx+8]
0x1800428ae  mov     r15, [rsp+58h+var_38]
0x1800428b3  xor     edx, edx
0x1800428b5  mov     r14, [rsp+58h+var_30]
0x1800428ba  mov     r12, [rsp+58h+var_28]
0x1800428bf  mov     [rax], rbx
0x1800428c2  mov     rax, [rsi+878h]
0x1800428c9  mov     rdi, [rsp+58h+var_20]
0x1800428ce  mov     rbp, [rsp+58h+arg_0]
0x1800428d3  mov     rax, [rax]
0x1800428d6  mov     [rax], rdx
0x1800428d9  mov     rax, [rsi+880h]
0x1800428e0  mov     [rax], rcx
0x1800428e3  add     rcx, 8
0x1800428e7  mov     rax, [rsi+880h]
0x1800428ee  mov     rax, [rax]
0x1800428f1  mov     [rax], rdx
0x1800428f4  mov     rax, [rsi+878h]
0x1800428fb  mov     [rax+8], rcx
0x1800428ff  add     rcx, 8
0x180042903  mov     rax, [rsi+878h]
0x18004290a  mov     rax, [rax+8]
0x18004290e  mov     [rax], rdx
0x180042911  mov     rax, [rsi+880h]
0x180042918  mov     [rax+8], rcx
0x18004291c  add     rcx, 8
0x180042920  mov     rax, [rsi+880h]
0x180042927  mov     rax, [rax+8]
0x18004292b  mov     [rax], rdx
0x18004292e  mov     rax, [rsi+878h]
0x180042935  mov     [rax+10h], rcx
0x180042939  add     rcx, 8
0x18004293d  mov     rax, [rsi+878h]
0x180042944  mov     rax, [rax+10h]
0x180042948  mov     [rax], rdx
0x18004294b  mov     rax, [rsi+880h]
0x180042952  mov     [rax+10h], rcx
0x180042956  add     rcx, 8
0x18004295a  mov     rax, [rsi+880h]
0x180042961  mov     rax, [rax+10h]
0x180042965  mov     [rax], rdx
0x180042968  mov     rax, [rsi+878h]
0x18004296f  mov     [rax+18h], rcx
0x180042973  add     rcx, 8
0x180042977  mov     rax, [rsi+878h]
0x18004297e  mov     rax, [rax+18h]
0x180042982  mov     [rax], rdx
0x180042985  mov     rax, [rsi+880h]
0x18004298c  mov     [rax+18h], rcx
0x180042990  add     rcx, 8
0x180042994  mov     rax, [rsi+880h]
0x18004299b  mov     rax, [rax+18h]
0x18004299f  mov     [rax], rdx
0x1800429a2  mov     rax, [rsi+878h]
0x1800429a9  mov     [rax+20h], rcx
0x1800429ad  add     rcx, 8
0x1800429b1  mov     rax, [rsi+878h]
0x1800429b8  mov     rax, [rax+20h]
0x1800429bc  mov     [rax], rdx
0x1800429bf  mov     rax, [rsi+880h]
0x1800429c6  mov     [rax+20h], rcx
0x1800429ca  add     rcx, 8
0x1800429ce  mov     rax, [rsi+880h]
0x1800429d5  mov     rax, [rax+20h]
0x1800429d9  mov     [rax], rdx
0x1800429dc  mov     rax, [rsi+878h]
0x1800429e3  mov     [rax+28h], rcx
0x1800429e7  add     rcx, 8
0x1800429eb  mov     rax, [rsi+878h]
0x1800429f2  mov     rax, [rax+28h]
0x1800429f6  mov     [rax], rdx
0x1800429f9  mov     rax, [rsi+880h]
0x180042a00  mov     [rax+28h], rcx
0x180042a04  add     rcx, 8
0x180042a08  mov     rax, [rsi+880h]
0x180042a0f  mov     rax, [rax+28h]
0x180042a13  mov     [rax], rdx
0x180042a16  mov     rax, [rsi+878h]
0x180042a1d  mov     [rax+30h], rcx
0x180042a21  add     rcx, 8
0x180042a25  mov     rax, [rsi+878h]
0x180042a2c  mov     rax, [rax+30h]
0x180042a30  mov     [rax], rdx
0x180042a33  mov     rax, [rsi+880h]
0x180042a3a  mov     [rax+30h], rcx
0x180042a3e  add     rcx, 8
0x180042a42  mov     rax, [rsi+880h]
0x180042a49  mov     rax, [rax+30h]
0x180042a4d  mov     [rax], rdx
0x180042a50  mov     rax, [rsi+878h]
0x180042a57  mov     [rax+38h], rcx
0x180042a5b  add     rcx, 8
0x180042a5f  mov     rax, [rsi+878h]
0x180042a66  mov     rax, [rax+38h]
0x180042a6a  mov     [rax], rdx
0x180042a6d  mov     rax, [rsi+880h]
0x180042a74  mov     [rax+38h], rcx
0x180042a78  add     rcx, 8
0x180042a7c  mov     rax, [rsi+880h]
0x180042a83  mov     rax, [rax+38h]
  ... truncated ...
```
