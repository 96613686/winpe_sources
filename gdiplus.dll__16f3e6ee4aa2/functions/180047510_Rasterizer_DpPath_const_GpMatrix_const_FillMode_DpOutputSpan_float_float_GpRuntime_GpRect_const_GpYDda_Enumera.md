# Rasterizer(DpPath const *,GpMatrix const *,FillMode,DpOutputSpan *,float,float,GpRuntime::GpRect const *,GpYDda *,EnumerationType,DpPen const *)

- ea: `0x180047510`
- end: `0x1800482d3`
- name: `?Rasterizer@@YA?AW4Status@@PEBVDpPath@@PEBVGpMatrix@@W4FillMode@@PEAVDpOutputSpan@@MMPEBVGpRect@GpRuntime@@PEAVGpYDda@@W4EnumerationType@@PEBUDpPen@@@Z`
- size: `3523`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180046dd8`

## callees

- `0x18002abc0`
- `0x180047510`
- `0x1800482dc`
- `0x180048400`
- `0x1800484e0`
- `0x180048784`
- `0x18005b2a0`
- `0x1800fe680`
- `0x1800fefe0`
- `0x180163624`
- `0x180168478`
- `0x180169010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x180047df4`
- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x180047df4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047633`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047e59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047633`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047e59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047a27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047a27`

## pseudocode

```c
__int64 __fastcall Rasterizer(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  PointF *v6; // rbx
  int v7; // r12d
  __int64 v8; // rdi
  __int64 v9; // rax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned __int128 v12; // rax
  struct RasterizeVector *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned __int8 *v16; // r13
  struct PointF *v17; // rdi
  int v18; // r15d
  int v19; // r15d
  unsigned int v20; // ecx
  int v21; // eax
  int v22; // r14d
  unsigned int v23; // edi
  __m128 v24; // xmm1
  unsigned int v25; // r14d
  __m128 v26; // xmm1
  int v27; // r12d
  __int64 v28; // r9
  int v29; // r15d
  int v30; // r13d
  int v31; // r14d
  int i; // eax
  __m128 v33; // xmm1
  int v34; // eax
  __m128 v35; // xmm1
  int v36; // ecx
  int v37; // edx
  unsigned int v38; // eax
  void (__fastcall ***v40)(_QWORD, __int64); // r14
  int v41; // eax
  int v42; // r9d
  unsigned int v43; // r10d
  int v44; // r11d
  unsigned int v45; // edx
  int v46; // edx
  int v47; // eax
  int v48; // ecx
  __int64 v49; // rbx
  size_t v50; // rdi
  int v51; // ecx
  int v52; // eax
  int v53; // edi
  unsigned __int8 *v54; // rbx
  struct PointF *v55; // r12
  int v56; // eax
  int v57; // eax
  int v58; // ecx
  unsigned int v59; // r8d
  int v60; // r9d
  unsigned int v61; // edx
  int v62; // r12d
  int *v63; // rdi
  __int64 v64; // rcx
  LPVOID v65; // rbx
  __int64 v66; // rdx
  __int64 v67; // rcx
  int v68; // r10d
  unsigned int v69; // eax
  int v70; // eax
  int v71; // r14d
  int v72; // eax
  int v73; // eax
  int v74; // ecx
  int v75; // r10d
  unsigned int v76; // r11d
  __m128 v77; // xmm1
  unsigned int v78; // r15d
  __m128 v79; // xmm1
  bool v80; // [rsp+50h] [rbp-2B8h]
  int v81; // [rsp+54h] [rbp-2B4h]
  unsigned int v82; // [rsp+58h] [rbp-2B0h]
  unsigned int v83; // [rsp+64h] [rbp-2A4h]
  unsigned int v84; // [rsp+68h] [rbp-2A0h]
  int v85; // [rsp+6Ch] [rbp-29Ch]
  int v86; // [rsp+70h] [rbp-298h]
  int v87; // [rsp+70h] [rbp-298h]
  int v88; // [rsp+74h] [rbp-294h]
  int v89; // [rsp+78h] [rbp-290h]
  int v90; // [rsp+78h] [rbp-290h]
  int v91; // [rsp+78h] [rbp-290h]
  int v92; // [rsp+7Ch] [rbp-28Ch]
  int v93; // [rsp+7Ch] [rbp-28Ch]
  __int64 v94; // [rsp+80h] [rbp-288h]
  unsigned int v95; // [rsp+88h] [rbp-280h]
  int v96; // [rsp+8Ch] [rbp-27Ch]
  int v97; // [rsp+90h] [rbp-278h]
  int v98; // [rsp+94h] [rbp-274h]
  unsigned int v99; // [rsp+9Ch] [rbp-26Ch]
  int v100; // [rsp+A0h] [rbp-268h]
  int v101; // [rsp+A0h] [rbp-268h]
  int v102; // [rsp+A4h] [rbp-264h]
  struct RasterizeVector *lpMem; // [rsp+A8h] [rbp-260h]
  int v104; // [rsp+B4h] [rbp-254h] BYREF
  int v105; // [rsp+B8h] [rbp-250h] BYREF
  int v106; // [rsp+BCh] [rbp-24Ch] BYREF
  int v107; // [rsp+C0h] [rbp-248h] BYREF
  int v108; // [rsp+C4h] [rbp-244h] BYREF
  int v109; // [rsp+C8h] [rbp-240h] BYREF
  int v110; // [rsp+CCh] [rbp-23Ch]
  __int64 v111; // [rsp+D0h] [rbp-238h]
  struct RasterizeVector *v112; // [rsp+D8h] [rbp-230h]
  __int64 v113; // [rsp+E0h] [rbp-228h] BYREF
  int v114; // [rsp+E8h] [rbp-220h]
  __int64 v115; // [rsp+F0h] [rbp-218h]
  unsigned int v116; // [rsp+F8h] [rbp-210h]
  int v117; // [rsp+FCh] [rbp-20Ch]
  int v118; // [rsp+104h] [rbp-204h]
  int v119; // [rsp+108h] [rbp-200h]
  unsigned int v120; // [rsp+10Ch] [rbp-1FCh]
  __int64 v121; // [rsp+120h] [rbp-1E8h]
  int v122; // [rsp+130h] [rbp-1D8h]
  int v123; // [rsp+134h] [rbp-1D4h]
  int v124; // [rsp+138h] [rbp-1D0h]
  int v125; // [rsp+13Ch] [rbp-1CCh]
  __int64 v126; // [rsp+140h] [rbp-1C8h]
  int *v127; // [rsp+148h] [rbp-1C0h]
  struct RasterizeVector *v128; // [rsp+150h] [rbp-1B8h]
  unsigned __int8 *v129; // [rsp+158h] [rbp-1B0h]
  float *v130; // [rsp+160h] [rbp-1A8h]
  __int64 v131; // [rsp+170h] [rbp-198h]
  float v132; // [rsp+180h] [rbp-188h] BYREF
  unsigned int v133[63]; // [rsp+184h] [rbp-184h]
  _BYTE v134[32]; // [rsp+280h] [rbp-88h] BYREF

  v126 = a4;
  v131 = a4;
  v6 = (PointF *)&v132;
  v7 = 32;
  v8 = 32;
  do
  {
    PointF::PointF(v6);
    v6 = (PointF *)((char *)v6 + 8);
    --v8;
  }
  while ( v8 );
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)a1 + 96LL))(a1, a2, 1, 0);
  v94 = v9;
  if ( !v9 )
    return 3;
  v10 = 0;
  lpMem = 0;
  DpPathIterator::DpPathIterator(
    (DpPathIterator *)&v113,
    *(const struct PointF **)(v9 + 80),
    *(const unsigned __int8 **)(v9 + 32),
    *(_DWORD *)(v9 + 104));
  if ( v114 != 1231114289 )
    goto LABEL_51;
  v11 = v116 + v117;
  if ( v116 + v117 < v116 )
  {
LABEL_50:
    v10 = 3;
    goto LABEL_51;
  }
  if ( v11 < 3 )
  {
LABEL_51:
    v40 = (void (__fastcall ***)(_QWORD, __int64))v94;
    goto LABEL_52;
  }
  v127 = (int *)(v11 - 1);
  v128 = 0;
  v12 = (v11 - 1) * (unsigned __int128)0x18u;
  if ( !is_mul_ok((unsigned __int64)v127, 0x18u) )
    goto LABEL_50;
  v13 = (struct RasterizeVector *)HeapAlloc(GpRuntime::GpMemHeap, DWORD2(v12), v12);
  lpMem = v13;
  v128 = v13;
  if ( !v13 )
    goto LABEL_50;
  if ( (*(unsigned int (__fastcall **)(__int64 *))(v113 + 40))(&v113) && v116 )
  {
    v16 = v134;
    v17 = (struct PointF *)&v132;
    v18 = 0;
    v81 = 0;
    if ( (*(unsigned int (__fastcall **)(__int64 *))(v113 + 40))(&v113) && v116 )
    {
      v106 = 0;
      v105 = 0;
      v104 = 0;
      v19 = v118;
      if ( !v118 )
      {
        (*(void (__fastcall **)(__int64 *, int *, int *, int *))(v113 + 8))(&v113, &v106, &v105, &v104);
        v19 = v118;
      }
      v20 = v120;
      if ( v19 > (int)v120 )
      {
        v21 = (*(__int64 (__fastcall **)(__int64 *, int *, int *, int *))(v113 + 8))(&v113, &v106, &v105, &v104);
        v20 = v120;
        v19 = v118;
      }
      else
      {
        v21 = v120 - v119 + 1;
      }
      if ( v21 )
      {
        v22 = 32;
        if ( (int)(v20 - v19 + 1) <= 32 )
          v22 = v20 - v19 + 1;
        if ( v22 > 0 )
        {
          memcpy_0(&v132, (const void *)(v121 + 8LL * v19), 8LL * v22);
          memcpy_0(v134, (const void *)(v19 + v115), v22);
          v118 = v22 + v19;
          v17 = (struct PointF *)&v132;
        }
        v18 = 0;
      }
      else
      {
        v22 = 0;
        v18 = 0;
      }
    }
    else
    {
      v22 = 0;
    }
    if ( v22 <= 0 )
      goto LABEL_28;
    do
    {
      v18 += v22;
      v7 -= v22;
      if ( v7 > 0 )
      {
        v17 = (struct PointF *)((char *)v17 + 8 * (unsigned int)v22);
        v16 += (unsigned int)v22;
        v22 = DpPathIterator::EnumerateWithinSubpath((DpPathIterator *)&v113, v17, v16, v7);
      }
      else
      {
        v22 = 0;
      }
    }
    while ( v22 > 0 );
  }
  else
  {
    v18 = 0;
  }
  v81 = v18;
LABEL_28:
  if ( v18 <= 0 )
  {
LABEL_132:
    v10 = 0;
    goto LABEL_51;
  }
  v98 = 0;
  v85 = 0;
  v95 = 0;
  v110 = 0;
  v112 = v13;
  v23 = 0;
  v83 = 0;
  v24 = (__m128)LODWORD(v132);
  v24.m128_f32[0] = (float)(v132 * 16.0) + 0.5;
  LOBYTE(v15) = Feature_GdiPlusOptimizations_Misc_IsEnabled;
  v80 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
  if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
  {
    v25 = (int)_mm_round_ss(v24, v24, 9).m128_f32[0];
  }
  else
  {
    v25 = (int)floor(v24.m128_f32[0]);
    LOBYTE(v15) = 0;
  }
  v84 = v25;
  v26 = (__m128)v133[0];
  v26.m128_f32[0] = (float)(*(float *)v133 * 16.0) + 0.5;
  if ( (_BYTE)v15 )
  {
    v27 = (int)_mm_round_ss(v26, v26, 9).m128_f32[0];
  }
  else
  {
    v27 = (int)floor(v26.m128_f32[0]);
    LOBYTE(v15) = v80;
  }
  v96 = v27;
  v28 = v25;
  v82 = v25;
  v99 = v25;
  v29 = v27;
  v97 = v27;
  v30 = v27;
  v31 = v27;
  for ( i = 1; ; i = v86 + 1 )
  {
    v86 = i;
    if ( i != v81 )
      goto LABEL_35;
    v88 = v31;
    v90 = v31;
    v101 = v30;
    v102 = v30;
    v123 = v31;
    LODWORD(v111) = v31;
    v125 = v30;
    v122 = v30;
    if ( (*(unsigned int (__fastcall **)(__int64 *, __int64, __int64, __int64))(v113 + 40))(&v113, v14, v15, v28)
      && v116 )
    {
      v124 = 32;
      v129 = v134;
      v130 = &v132;
      v81 = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64 *))(v113 + 40))(&v113) || !v116 )
        goto LABEL_109;
      v109 = 0;
      v108 = 0;
      v107 = 0;
      v46 = v118;
      if ( !v118 )
      {
        (*(void (__fastcall **)(__int64 *, int *, int *, int *))(v113 + 8))(&v113, &v109, &v108, &v107);
        v46 = v118;
      }
      v15 = v120;
      if ( v46 > (int)v120 )
      {
        v47 = (*(__int64 (__fastcall **)(__int64 *, int *, int *, int *))(v113 + 8))(&v113, &v109, &v108, &v107);
        v15 = v120;
        v46 = v118;
      }
      else
      {
        v47 = v120 - v119 + 1;
      }
      if ( v47 )
      {
        v48 = 32;
        v15 = (unsigned int)(v15 - v46);
        if ( (int)v15 + 1 <= 32 )
          v48 = v15 + 1;
        v87 = v48;
        if ( v48 <= 0 )
          goto LABEL_81;
        v49 = v46;
        v50 = v48;
        memcpy_0(&v132, (const void *)(v121 + 8LL * v46), 8LL * v48);
        memcpy_0(v134, (const void *)(v49 + v115), v50);
        v51 = v87;
        v118 += v87;
        v13 = v112;
        v23 = v83;
      }
      else
      {
LABEL_109:
        v51 = 0;
      }
      if ( v51 > 0 )
      {
        v52 = 0;
        v53 = v124;
        v54 = v129;
        v55 = (struct PointF *)v130;
        do
        {
          v52 += v51;
          v81 = v52;
          v53 -= v51;
          if ( v53 > 0 )
          {
            v55 = (struct PointF *)((char *)v55 + 8 * (unsigned int)v51);
            v54 += (unsigned int)v51;
            v51 = DpPathIterator::EnumerateWithinSubpath((DpPathIterator *)&v113, v55, v54, v53);
            v52 = v81;
          }
          else
          {
            v51 = 0;
          }
        }
        while ( v51 > 0 );
        v27 = v96;
        v13 = v112;
        v23 = v83;
      }
LABEL_81:
      v56 = v81;
      goto LABEL_82;
    }
    v56 = 0;
    v81 = 0;
LABEL_82:
    if ( v56 <= 0 )
      break;
    i = 0;
    v86 = 0;
    LOBYTE(v15) = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    v80 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    LODWORD(v28) = v82;
LABEL_35:
    if ( i >= 32 )
    {
      v62 = v95;
      goto LABEL_92;
    }
    v14 = i;
    v111 = i;
    if ( (v134[i] & 7) != 0 )
    {
      v100 = v98;
      v33 = (__m128)v133[2 * i - 1];
      v33.m128_f32[0] = (float)(v33.m128_f32[0] * 16.0) + 0.5;
      if ( (_BYTE)v15 )
      {
        v34 = (int)_mm_round_ss(v33, v33, 9).m128_f32[0];
      }
      else
      {
        v34 = (int)floor(v33.m128_f32[0]);
        v14 = v111;
        LOBYTE(v15) = v80;
      }
      v82 = v34;
      v35 = (__m128)v133[2 * v14];
      v35.m128_f32[0] = (float)(v35.m128_f32[0] * 16.0) + 0.5;
      if ( (_BYTE)v15 )
      {
        v29 = (int)_mm_round_ss(v35, v35, 9).m128_f32[0];
      }
      else
      {
        v29 = (int)floor(v35.m128_f32[0]);
        LOBYTE(v15) = v80;
      }
      if ( (((v97 + 15) ^ (v29 + 15)) & 0xFFFFFFF0) != 0 )
      {
        v92 = v31;
        v89 = v31;
        v41 = v30;
        if ( v97 > v29 )
        {
          v70 = v31;
          v36 = 1;
          v71 = v97;
          v42 = v97;
          v43 = v99;
          v44 = v29;
          v45 = v82;
          if ( v97 <= v30 )
            v71 = v30;
          v30 = v71;
          v31 = v29;
          if ( v29 >= v70 )
            v31 = v70;
        }
        else
        {
          v36 = -1;
          v42 = v29;
          v43 = v82;
          v44 = v97;
          v30 = v29;
          if ( v29 <= v41 )
            v30 = v41;
          v31 = v97;
          if ( v97 >= v92 )
            v31 = v89;
          v45 = v99;
        }
        v85 = v36;
        *(_DWORD *)v13 = v45;
        *((_DWORD *)v13 + 1) = v44;
        *((_DWORD *)v13 + 2) = v43;
        *((_DWORD *)v13 + 3) = v42;
        *((_DWORD *)v13 + 4) = v36;
        v83 = ++v23;
        v13 = (struct RasterizeVector *)((char *)v13 + 20);
        v112 = v13;
      }
      else
      {
        v36 = v85;
      }
      v37 = v36;
      if ( v36 == v98 )
        v37 = v98;
      v98 = v37;
      v14 = v95;
      v38 = v95 + 1;
      if ( v36 == v100 )
        v38 = v95;
      v95 = v38;
      v28 = v82;
    }
    else
    {
      if ( (((v27 + 15) ^ (v29 + 15)) & 0xFFFFFFF0) != 0 )
      {
        v72 = v31;
        v93 = v30;
        v91 = v30;
        if ( v29 <= v27 )
        {
          v74 = -1;
          v75 = v27;
          v76 = v84;
          v30 = v27;
          if ( v27 <= v93 )
            v30 = v91;
          v31 = v29;
          if ( v29 >= v72 )
            v31 = v72;
        }
        else
        {
          v73 = v29;
          v74 = 1;
          v75 = v29;
          v76 = v28;
          v29 = v27;
          LODWORD(v28) = v84;
          if ( v73 <= v30 )
            v73 = v30;
          v30 = v73;
          if ( v27 >= v31 )
            v27 = v31;
          v31 = v27;
        }
        v85 = v74;
        *(_DWORD *)v13 = v28;
        *((_DWORD *)v13 + 1) = v29;
        *((_DWORD *)v13 + 2) = v76;
        *((_DWORD *)v13 + 3) = v75;
        *((_DWORD *)v13 + 4) = v74;
        v83 = ++v23;
        v13 = (struct RasterizeVector *)((char *)v13 + 20);
        v112 = v13;
      }
      v77 = (__m128)v133[2 * v14 - 1];
      v77.m128_f32[0] = (float)(v77.m128_f32[0] * 16.0) + 0.5;
      if ( (_BYTE)v15 )
      {
        v78 = (int)_mm_round_ss(v77, v77, 9).m128_f32[0];
      }
      else
      {
        v78 = (int)floor(v77.m128_f32[0]);
        v14 = v111;
        LOBYTE(v15) = v80;
      }
      v84 = v78;
      v79 = (__m128)v133[2 * v14];
      v79.m128_f32[0] = (float)(v79.m128_f32[0] * 16.0) + 0.5;
      if ( (_BYTE)v15 )
      {
        v27 = (int)_mm_round_ss(v79, v79, 9).m128_f32[0];
      }
      else
      {
        v27 = (int)floor(v79.m128_f32[0]);
        LOBYTE(v15) = v80;
      }
      v96 = v27;
      v28 = v78;
      v82 = v78;
      v29 = v27;
      v110 = 1;
    }
    v99 = v28;
    v97 = v29;
  }
  if ( (((v27 + 15) ^ (v29 + 15)) & 0xFFFFFFF0) != 0 )
  {
    if ( v29 <= v27 )
    {
      v57 = -1;
      v58 = v27;
      v59 = v84;
      v60 = v29;
      v30 = v27;
      if ( v27 <= v125 )
        v30 = v122;
      v31 = v29;
      if ( v29 >= v123 )
        v31 = v111;
      v61 = v82;
    }
    else
    {
      v57 = 1;
      v58 = v29;
      v59 = v82;
      v60 = v27;
      v61 = v84;
      v30 = v29;
      if ( v29 <= v101 )
        v30 = v102;
      v31 = v27;
      if ( v27 >= v88 )
        v31 = v90;
    }
    *(_DWORD *)v13 = v61;
    *((_DWORD *)v13 + 1) = v60;
    *((_DWORD *)v13 + 2) = v59;
    *((_DWORD *)v13 + 3) = v58;
    *((_DWORD *)v13 + 4) = v57;
    v83 = ++v23;
  }
  else
  {
    v57 = v85;
  }
  v62 = v95 + 1;
  if ( v57 == v98 )
    v62 = v95;
LABEL_92:
  if ( v23 < 2 )
    goto LABEL_132;
  v63 = (int *)((char *)lpMem + 20 * (_QWORD)v127);
  v127 = v63;
  v64 = 0;
  do
  {
    v63[v64] = v64;
    v64 = (unsigned int)(v64 + 1);
  }
  while ( (unsigned int)v64 < v83 );
  QuickSortIndex(lpMem, v63, &v63[v83 - 1]);
  v65 = HeapAlloc(GpRuntime::GpMemHeap, 0, 0x28u);
  if ( v65 )
    *(_QWORD *)v65 = &GpYDda::`vftable';
  else
    v65 = 0;
  if ( !v65 )
    goto LABEL_50;
  v66 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v65 + 24LL))(v65);
  if ( !v66 )
  {
    (**(void (__fastcall ***)(LPVOID, __int64))v65)(v65, 1);
    goto LABEL_50;
  }
  v67 = (unsigned int)((v31 + 15) >> 4);
  v68 = (v30 + 15) >> 4;
  v40 = (void (__fastcall ***)(_QWORD, __int64))v94;
  if ( (*(_BYTE *)(v94 + 244) & 1) == 0 && (v110 || v62 > 3) )
    v69 = NonConvexRasterizer(v67, (unsigned int)(v68 - 1), v83, lpMem, v63, v65, v66, v126);
  else
    v69 = ConvexRasterizer(v67, (unsigned int)(v68 - 1), v83, lpMem, v63, v65, v66, v126);
  v10 = v69;
LABEL_52:
  if ( lpMem )
    HeapFree(GpRuntime::GpMemHeap, 0, lpMem);
  (**v40)(v40, 1);
  return v10;
}

```

## disassembly

```asm
0x180047510  mov     rax, rsp
0x180047513  mov     [rax+18h], r8d
0x180047517  push    rbx
0x180047518  push    rdi
0x180047519  push    r12
0x18004751b  push    r13
0x18004751d  push    r14
0x18004751f  push    r15
0x180047521  sub     rsp, 2D8h
0x180047528  movaps  xmmword ptr [rax-48h], xmm6
0x18004752c  movaps  xmmword ptr [rax-58h], xmm7
0x180047530  mov     rax, cs:__security_cookie
0x180047537  xor     rax, rsp
0x18004753a  mov     [rsp+308h+var_68], rax
0x180047542  mov     rax, r9
0x180047545  mov     [rsp+308h+var_1C8], rax
0x18004754d  mov     r15, rdx
0x180047550  mov     r14, rcx
0x180047553  mov     [rsp+308h+var_198], rax
0x18004755b  lea     rbx, [rsp+308h+var_188]
0x180047563  mov     r12d, 20h ; ' '
0x180047569  mov     edi, r12d
0x18004756c  mov     rcx, rbx; this
0x18004756f  call    ??0PointF@@QEAA@XZ; PointF::PointF(void)
0x180047574  add     rbx, 8
0x180047578  sub     rdi, 1
0x18004757c  jnz     short loc_18004756C
0x18004757e  mov     rax, [r14]
0x180047581  xor     r9d, r9d
0x180047584  lea     r8d, [rdi+1]
0x180047588  mov     rdx, r15
0x18004758b  mov     rcx, r14
0x18004758e  mov     rax, [rax+60h]
0x180047592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047597  mov     [rsp+308h+var_288], rax
0x18004759f  test    rax, rax
0x1800475a2  jz      loc_1800479FA
0x1800475a8  xor     ebx, ebx
0x1800475aa  mov     [rsp+308h+var_258], ebx
0x1800475b1  mov     [rsp+308h+lpMem], rbx
0x1800475b9  mov     r9d, [rax+68h]; int
0x1800475bd  mov     r8, [rax+20h]; unsigned __int8 *
0x1800475c1  mov     rdx, [rax+50h]; struct PointF *
0x1800475c5  lea     rcx, [rsp+308h+var_228]; this
0x1800475cd  call    ??0DpPathIterator@@QEAA@PEBVPointF@@PEBEH@Z; DpPathIterator::DpPathIterator(PointF const *,uchar const *,int)
0x1800475d2  cmp     [rsp+308h+var_220], 49615031h
0x1800475dd  jnz     loc_180047A06
0x1800475e3  mov     eax, [rsp+308h+var_20C]
0x1800475ea  add     eax, [rsp+308h+var_210]
0x1800475f1  cmp     eax, [rsp+308h+var_210]
0x1800475f8  jb      loc_180047A01
0x1800475fe  cmp     eax, 3
0x180047601  jb      loc_180047A06
0x180047607  lea     ecx, [rax-1]
0x18004760a  mov     [rsp+308h+var_1C0], rcx
0x180047612  mov     [rsp+308h+var_1B8], rbx
0x18004761a  lea     eax, [rdi+18h]
0x18004761d  mul     rcx
0x180047620  test    rdx, rdx
0x180047623  jnz     loc_180047A01
0x180047629  mov     r8, rax; dwBytes
0x18004762c  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180047633  call    cs:__imp_HeapAlloc
0x180047639  mov     rbx, rax
0x18004763c  mov     [rsp+308h+lpMem], rax
0x180047644  mov     [rsp+308h+var_1B8], rax
0x18004764c  test    rax, rax
0x18004764f  jz      loc_180047A01
0x180047655  mov     rax, [rsp+308h+var_228]
0x18004765d  lea     rcx, [rsp+308h+var_228]
0x180047665  mov     rax, [rax+28h]
0x180047669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004766e  test    eax, eax
0x180047670  jz      loc_180048191
0x180047676  cmp     [rsp+308h+var_210], edi
0x18004767d  jz      loc_180048191
0x180047683  lea     r13, [rsp+308h+var_88]
0x18004768b  lea     rdi, [rsp+308h+var_188]
0x180047693  xor     r15d, r15d
0x180047696  mov     [rsp+308h+var_2B4], r15d
0x18004769b  mov     rax, [rsp+308h+var_228]
0x1800476a3  lea     rcx, [rsp+308h+var_228]
0x1800476ab  mov     rax, [rax+28h]
0x1800476af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476b4  test    eax, eax
0x1800476b6  jz      loc_180048139
0x1800476bc  cmp     [rsp+308h+var_210], r15d
0x1800476c4  jz      loc_180048139
0x1800476ca  mov     [rsp+308h+var_24C], r15d
0x1800476d2  mov     [rsp+308h+var_250], r15d
0x1800476da  mov     [rsp+308h+var_254], r15d
0x1800476e2  mov     r15d, [rsp+308h+var_204]
0x1800476ea  test    r15d, r15d
0x1800476ed  jnz     short loc_180047728
0x1800476ef  mov     rax, [rsp+308h+var_228]
0x1800476f7  lea     r9, [rsp+308h+var_254]
0x1800476ff  lea     r8, [rsp+308h+var_250]
0x180047707  lea     rdx, [rsp+308h+var_24C]
0x18004770f  lea     rcx, [rsp+308h+var_228]
0x180047717  mov     rax, [rax+8]
0x18004771b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047720  mov     r15d, [rsp+308h+var_204]
0x180047728  mov     ecx, [rsp+308h+var_1FC]
0x18004772f  cmp     r15d, ecx
0x180047732  jg      loc_180047FE8
0x180047738  mov     eax, ecx
0x18004773a  sub     eax, [rsp+308h+var_200]
0x180047741  inc     eax
0x180047743  test    eax, eax
0x180047745  jz      loc_180047F98
0x18004774b  mov     r14d, r12d
0x18004774e  sub     ecx, r15d
0x180047751  lea     eax, [rcx+1]
0x180047754  cmp     eax, r12d
0x180047757  cmovle  r14d, eax
0x18004775b  test    r14d, r14d
0x18004775e  jle     short loc_1800477BD
0x180047760  movsxd  rdi, r14d
0x180047763  movsxd  rbx, r15d
0x180047766  lea     r8, ds:0[rdi*8]; Size
0x18004776e  mov     rax, [rsp+308h+var_1E8]
0x180047776  lea     rdx, [rax+rbx*8]; Src
0x18004777a  lea     rcx, [rsp+308h+var_188]; void *
0x180047782  call    memcpy_0
0x180047787  mov     rdx, [rsp+308h+var_218]
0x18004778f  add     rdx, rbx; Src
0x180047792  mov     r8, rdi; Size
0x180047795  lea     rcx, [rsp+308h+var_88]; void *
0x18004779d  call    memcpy_0
0x1800477a2  add     r15d, r14d
0x1800477a5  mov     [rsp+308h+var_204], r15d
0x1800477ad  mov     rbx, [rsp+308h+lpMem]
0x1800477b5  lea     rdi, [rsp+308h+var_188]
0x1800477bd  mov     r15d, [rsp+308h+var_2B4]
0x1800477c2  test    r14d, r14d
0x1800477c5  jle     short loc_1800477E3
0x1800477c7  add     r15d, r14d
0x1800477ca  sub     r12d, r14d
0x1800477cd  test    r12d, r12d
0x1800477d0  jg      loc_180047F70
0x1800477d6  xor     r14d, r14d
0x1800477d9  test    r14d, r14d
0x1800477dc  jg      short loc_1800477C7
0x1800477de  mov     [rsp+308h+var_2B4], r15d
0x1800477e3  test    r15d, r15d
0x1800477e6  jle     loc_180048199
0x1800477ec  mov     [rsp+308h+var_274], 0
0x1800477f7  xor     ecx, ecx
0x1800477f9  mov     [rsp+308h+var_29C], ecx
0x1800477fd  xor     eax, eax
0x1800477ff  mov     [rsp+308h+var_280], eax
0x180047806  mov     [rsp+308h+var_270], eax
0x18004780d  mov     [rsp+308h+var_23C], eax
0x180047814  mov     [rsp+308h+var_230], rbx
0x18004781c  xor     edi, edi
0x18004781e  mov     [rsp+308h+var_2A4], edi
0x180047822  movss   xmm1, [rsp+308h+var_188]
0x18004782b  movss   xmm6, cs:__real@41800000
0x180047833  mulss   xmm1, xmm6
0x180047837  movss   xmm7, cs:__real@3f000000
0x18004783f  addss   xmm1, xmm7
0x180047843  mov     r8b, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x18004784a  mov     [rsp+308h+var_2B8], r8b
0x18004784f  test    r8b, r8b
0x180047852  jnz     loc_180048271
0x180047858  cvtps2pd xmm0, xmm1; X
0x18004785b  call    floor
0x180047860  cvttsd2si r14d, xmm0
0x180047865  mov     r8b, [rsp+308h+var_2B8]
0x18004786a  mov     [rsp+308h+var_2A0], r14d
0x18004786f  movss   xmm1, [rsp+308h+var_184]
0x180047878  mulss   xmm1, xmm6
0x18004787c  addss   xmm1, xmm7
0x180047880  test    r8b, r8b
0x180047883  jnz     loc_180048284
0x180047889  cvtps2pd xmm0, xmm1; X
0x18004788c  call    floor
0x180047891  cvttsd2si r12d, xmm0
0x180047896  mov     r8b, [rsp+308h+var_2B8]
0x18004789b  mov     [rsp+308h+var_27C], r12d
0x1800478a3  mov     r9d, r14d
0x1800478a6  mov     [rsp+308h+var_2B0], r14d
0x1800478ab  mov     [rsp+308h+var_26C], r14d
0x1800478b3  mov     r15d, r12d
0x1800478b6  mov     [rsp+308h+var_278], r12d
0x1800478be  mov     r13d, r12d
0x1800478c1  mov     [rsp+308h+var_2AC], r12d
0x1800478c6  mov     r14d, r12d
0x1800478c9  mov     [rsp+308h+var_2A8], r12d
0x1800478ce  mov     eax, 1
0x1800478d3  mov     [rsp+308h+var_298], eax
0x1800478d7  cmp     eax, [rsp+308h+var_2B4]
0x1800478db  jz      loc_180047AEA
0x1800478e1  cmp     eax, 20h ; ' '
0x1800478e4  jge     loc_1800482C6
0x1800478ea  movsxd  rdx, eax
0x1800478ed  mov     [rsp+308h+var_238], rdx
0x1800478f5  test    [rsp+rdx+308h+var_88], 7
0x1800478fd  jz      loc_18004802D
0x180047903  mov     ecx, [rsp+308h+var_274]
0x18004790a  mov     [rsp+308h+var_268], ecx
0x180047911  mov     eax, [rsp+308h+var_280]
0x180047918  mov     [rsp+308h+var_264], eax
0x18004791f  mov     [rsp+308h+var_294], ecx
0x180047923  movss   xmm1, [rsp+rdx*8+308h+var_188]
0x18004792c  mulss   xmm1, xmm6
0x180047930  addss   xmm1, xmm7
0x180047934  test    r8b, r8b
0x180047937  jnz     loc_18004824C
0x18004793d  cvtps2pd xmm0, xmm1; X
0x180047940  call    floor
0x180047945  cvttsd2si eax, xmm0
0x180047949  mov     rdx, [rsp+308h+var_238]
0x180047951  mov     r8b, [rsp+308h+var_2B8]
0x180047956  mov     [rsp+308h+var_2B0], eax
0x18004795a  movss   xmm1, [rsp+rdx*8+308h+var_184]
0x180047963  mulss   xmm1, xmm6
0x180047967  addss   xmm1, xmm7
0x18004796b  test    r8b, r8b
0x18004796e  jnz     loc_18004825E
0x180047974  cvtps2pd xmm0, xmm1; X
0x180047977  call    floor
0x18004797c  cvttsd2si r15d, xmm0
0x180047981  mov     r8b, [rsp+308h+var_2B8]
0x180047986  lea     ecx, [r15+0Fh]
0x18004798a  mov     edx, [rsp+308h+var_278]
0x180047991  lea     eax, [rdx+0Fh]
0x180047994  xor     ecx, eax
0x180047996  test    ecx, 0FFFFFFF0h
0x18004799c  jnz     loc_180047A72
0x1800479a2  mov     ecx, [rsp+308h+var_29C]
0x1800479a6  mov     edx, ecx
0x1800479a8  cmp     ecx, [rsp+308h+var_294]
0x1800479ac  cmovz   edx, [rsp+308h+var_294]
0x1800479b1  mov     [rsp+308h+var_274], edx
0x1800479b8  mov     edx, [rsp+308h+var_264]
0x1800479bf  lea     eax, [rdx+1]
0x1800479c2  cmp     ecx, [rsp+308h+var_268]
0x1800479c9  cmovz   eax, edx
0x1800479cc  mov     [rsp+308h+var_280], eax
0x1800479d3  mov     [rsp+308h+var_270], eax
0x1800479da  mov     r9d, [rsp+308h+var_2B0]
0x1800479df  mov     [rsp+308h+var_26C], r9d
0x1800479e7  mov     [rsp+308h+var_278], r15d
0x1800479ef  mov     eax, [rsp+308h+var_298]
0x1800479f3  inc     eax
0x1800479f5  jmp     loc_1800478D3
0x1800479fa  mov     eax, 3
0x1800479ff  jmp     short loc_180047A42
0x180047a01  mov     ebx, 3
0x180047a06  mov     r14, [rsp+308h+var_288]
0x180047a0e  mov     rax, [rsp+308h+lpMem]
0x180047a16  test    rax, rax
0x180047a19  jz      short loc_180047A2D
0x180047a1b  mov     r8, rax; lpMem
0x180047a1e  xor     edx, edx; dwFlags
0x180047a20  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180047a27  call    cs:__imp_HeapFree
0x180047a2d  mov     rax, [r14]
0x180047a30  mov     edx, 1
0x180047a35  mov     rcx, r14
0x180047a38  mov     rax, [rax]
0x180047a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a40  mov     eax, ebx
0x180047a42  mov     rcx, [rsp+308h+var_68]
0x180047a4a  xor     rcx, rsp; StackCookie
0x180047a4d  call    __security_check_cookie
0x180047a52  lea     r11, [rsp+308h+var_30]
0x180047a5a  movaps  xmm6, xmmword ptr [r11-18h]
0x180047a5f  movaps  xmm7, xmmword ptr [r11-28h]
0x180047a64  mov     rsp, r11
0x180047a67  pop     r15
0x180047a69  pop     r14
0x180047a6b  pop     r13
0x180047a6d  pop     r12
0x180047a6f  pop     rdi
0x180047a70  pop     rbx
0x180047a71  retn
0x180047a72  mov     [rsp+308h+var_28C], r14d
0x180047a77  mov     [rsp+308h+var_290], r14d
0x180047a7c  mov     eax, r13d
0x180047a7f  cmp     edx, r15d
0x180047a82  jg      loc_180047F09
0x180047a88  or      ecx, 0FFFFFFFFh
0x180047a8b  mov     r9d, r15d
0x180047a8e  mov     r10d, [rsp+308h+var_2B0]
0x180047a93  mov     r11d, edx
0x180047a96  mov     r13d, r15d
0x180047a99  cmp     r15d, eax
0x180047a9c  cmovle  r13d, eax
0x180047aa0  mov     r14d, edx
0x180047aa3  cmp     edx, [rsp+308h+var_28C]
0x180047aa7  cmovge  r14d, [rsp+308h+var_290]
0x180047aad  mov     edx, [rsp+308h+var_26C]
0x180047ab4  mov     [rsp+308h+var_2A8], r14d
0x180047ab9  mov     [rsp+308h+var_2AC], r13d
0x180047abe  mov     [rsp+308h+var_29C], ecx
0x180047ac2  mov     [rbx], edx
0x180047ac4  mov     [rbx+4], r11d
0x180047ac8  mov     [rbx+8], r10d
  ... truncated ...
```
