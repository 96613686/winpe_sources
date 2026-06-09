# CPaintHandler::BeginPaint(HWND__ *,CRect const &,HDC__ * *,CRegion &)

- ea: `0x18045ed60`
- end: `0x18045fc85`
- name: `?BeginPaint@CPaintHandler@@MEAA_NPEAUHWND__@@AEBVCRect@@PEAPEAUHDC__@@AEAVCRegion@@@Z`
- size: `3877`
- prototype: `bool __fastcall(CPaintHandler *__hidden this, HWND, const struct CRect *, HDC *, struct CRegion *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18045ec80`

## callees

- `0x180171708`
- `0x180171f5c`
- `0x1801bf528`
- `0x1801c0b08`
- `0x1803eae4c`
- `0x1803f405c`
- `0x1803f5e64`
- `0x18045df4c`
- `0x18045ed60`
- `0x18045fc8c`
- `0x18045fe9c`
- `0x180460120`
- `0x1807b2fb4`
- `0x1810c2d60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18045f5a6`
- `KERNEL32!GetLastError` at `0x18045f5a6`
- `GDI32!GetRegionData` at `0x18045f3bd`
- `GDI32!GetRegionData` at `0x18045f3e7`
- `GDI32!GetRegionData` at `0x18045f3bd`
- `GDI32!GetRegionData` at `0x18045f3e7`
- `GDI32!DeleteObject` at `0x18045edea`
- `GDI32!DeleteObject` at `0x18045f39f`
- `GDI32!DeleteObject` at `0x18045f58b`
- `GDI32!DeleteObject` at `0x18045f606`
- `GDI32!DeleteObject` at `0x18045f787`
- `GDI32!DeleteObject` at `0x18045f7ce`
- `GDI32!DeleteObject` at `0x18045f815`
- `GDI32!DeleteObject` at `0x18045edea`
- `GDI32!DeleteObject` at `0x18045f39f`
- `GDI32!DeleteObject` at `0x18045f58b`
- `GDI32!DeleteObject` at `0x18045f606`
- `GDI32!DeleteObject` at `0x18045f787`
- `GDI32!DeleteObject` at `0x18045f7ce`
- `GDI32!DeleteObject` at `0x18045f815`
- `GDI32!CreateRectRgnIndirect` at `0x18045f2ce`
- `GDI32!CreateRectRgnIndirect` at `0x18045f2ce`
- `GDI32!GetRandomRgn` at `0x18045f317`
- `GDI32!GetRandomRgn` at `0x18045f317`
- `GDI32!OffsetRgn` at `0x18045f33c`
- `GDI32!OffsetRgn` at `0x18045f33c`
- `GDI32!SelectClipRgn` at `0x18045f5ee`
- `GDI32!SelectClipRgn` at `0x18045f5ee`
- `USER32!ValidateRgn` at `0x18045f76d`
- `USER32!ValidateRgn` at `0x18045f76d`
- `USER32!GetDCEx` at `0x18045f277`
- `USER32!GetDCEx` at `0x18045f277`
- `USER32!MapWindowPoints` at `0x18045f305`
- `USER32!MapWindowPoints` at `0x18045f35a`
- `USER32!MapWindowPoints` at `0x18045f305`
- `USER32!MapWindowPoints` at `0x18045f35a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18045f2a3`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18045f2a3`

## pseudocode

```c
char __fastcall CPaintHandler::BeginPaint(
        unsigned __int64 this,
        HWND a2,
        unsigned __int64 a3,
        HDC *a4,
        struct CRegion *a5)
{
  struct CRegion *v5; // r15
  unsigned __int64 v6; // r14
  HWND v8; // r9
  const __m128i *v9; // rdi
  _DWORD *v10; // rdx
  unsigned __int64 v11; // r12
  void *v12; // rcx
  __int32 v13; // eax
  __m128i *v14; // rbx
  __int64 v15; // r13
  unsigned __int64 v16; // rdx
  float v17; // xmm1_4
  float v18; // xmm0_4
  unsigned __int64 v19; // r10
  unsigned __int64 v20; // rdx
  struct tagPOINT v21; // r9
  int v22; // esi
  int v23; // eax
  unsigned int v24; // r11d
  LONG v25; // eax
  LONG v26; // r9d
  LONG v27; // ecx
  int v28; // ecx
  unsigned __int64 v29; // r9
  __m128 v30; // xmm6
  __m128 v31; // xmm8
  __m128 v32; // xmm4
  __m128 v33; // xmm1
  __m128 v34; // xmm7
  __m128i v35; // xmm0
  __m128 v36; // xmm1
  __m128 v37; // xmm2
  __m128 v38; // xmm3
  __m128i v39; // xmm4
  int v40; // r10d
  __int64 v41; // rcx
  __int64 v42; // rcx
  __m128 v43; // xmm2
  __m128 v44; // xmm1
  __m128d v45; // xmm3
  __m128d v46; // xmm8
  __m128i v47; // xmm1
  __m128i v48; // xmm2
  int v49; // r10d
  __int64 v50; // rdx
  __int64 v51; // rdx
  __m128 v52; // xmm8
  __m128 v53; // xmm5
  __m128 v54; // xmm4
  __m128 v55; // xmm1
  __m128 v56; // xmm7
  __m128i v57; // xmm0
  __m128 v58; // xmm1
  __m128 v59; // xmm2
  __m128 v60; // xmm3
  unsigned __int64 v61; // rdi
  const struct FastRegion::Internal::CRgnData *v62; // r15
  char v63; // al
  HDC DCEx; // rax
  HDC v65; // r13
  HRGN v66; // rsi
  HWND v67; // rbx
  int RandomRgn; // eax
  unsigned int *v69; // rcx
  void **v70; // rdi
  void *v71; // rcx
  DWORD RegionData; // eax
  unsigned __int64 v73; // r8
  DWORD v74; // ebx
  struct _RGNDATA *v75; // rax
  struct _RGNDATA *v76; // r13
  void *v77; // r8
  const struct FastRegion::Internal::CRgnData *v78; // r13
  struct FastRegion::Internal::CRgnData *v79; // rax
  int v80; // eax
  FastRegion::Internal::CRgnData *v81; // rbx
  void *v82; // r8
  unsigned int *v83; // r9
  int v84; // eax
  int v85; // r10d
  int v86; // edx
  __int64 v87; // r13
  char *v88; // r11
  __int64 v89; // rcx
  __int64 v90; // rdx
  signed int LastError; // eax
  bool v92; // sf
  int **v93; // rbx
  HRGN v94; // rax
  void *v95; // r8
  void *v96; // rcx
  int *v97; // rdx
  int v98; // eax
  __int64 v99; // rax
  _DWORD *v100; // r9
  int *v101; // r10
  int v102; // edx
  int v103; // ebx
  __int64 v104; // rsi
  _DWORD *v105; // rdi
  __int64 v106; // rcx
  __int64 v107; // rdx
  int *v108; // rcx
  unsigned __int64 v109; // r8
  HRGN v110; // rax
  void *v111; // r8
  void *v112; // rcx
  void *v114; // rcx
  int nCount; // edx
  struct FastRegion::Internal::CRgnData **RgnOfRectAry; // rax
  __int64 v117; // rdx
  struct FastRegion::Internal::CRgnData **v118; // rsi
  struct FastRegion::Internal::CRgnData *v119; // rcx
  struct FastRegion::Internal::CRgnData *v120; // rax
  int v121; // r10d
  __int64 v122; // rbx
  _DWORD *v123; // r11
  __int64 v124; // rcx
  _DWORD *v125; // rcx
  unsigned __int64 v126; // r8
  __int64 v127; // r9
  FastRegion::Internal::CRgnData *v128; // rcx
  const struct FastRegion::Internal::CRgnData *v129; // rdx
  FastRegion::Internal::CRgnData *v130; // rax
  __m128 v131; // xmm8
  int v132; // edx
  __m128 v133; // xmm5
  __m128 v134; // xmm4
  __m128 v135; // xmm1
  __m128 v136; // xmm7
  __m128i v137; // xmm0
  __m128 v138; // xmm1
  __m128 v139; // xmm2
  __m128 v140; // xmm3
  int v141; // ecx
  __int64 v142; // r9
  __int64 v143; // rcx
  struct tagPOINT Points; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int64 v145; // [rsp+50h] [rbp-B8h] BYREF
  struct tagPOINT v146; // [rsp+58h] [rbp-B0h] BYREF
  const struct FastRegion::Internal::CRgnData *rect; // [rsp+60h] [rbp-A8h]
  RECT rect_8; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v149; // [rsp+78h] [rbp-90h]
  struct CRegion *v150; // [rsp+80h] [rbp-88h]
  HWND hWnd; // [rsp+88h] [rbp-80h]
  _DWORD *v152; // [rsp+90h] [rbp-78h]
  struct FastRegion::Internal::CRgnData *v153; // [rsp+98h] [rbp-70h]
  _DWORD v154[18]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v155[64]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v156[208]; // [rsp+128h] [rbp+20h] BYREF

  v5 = a5;
  v6 = this;
  LOBYTE(this) = *(_BYTE *)(this + 8);
  hWnd = a2;
  v8 = a2;
  v146 = (struct tagPOINT)a4;
  v9 = (const __m128i *)a3;
  v150 = a5;
  v10 = (_DWORD *)(v6 + 176);
  v152 = (_DWORD *)(v6 + 176);
  v11 = v6 + 184;
  if ( (this & 1) != 0 )
  {
    *v10 = 0;
    v12 = *(void **)(v6 + 256);
    if ( v12 )
    {
      DeleteObject(v12);
      *(_QWORD *)(v6 + 256) = 0;
    }
    if ( *(_QWORD *)v11 > 1u )
      MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, *(void **)v11, (void *)a3);
    *(_QWORD *)v11 = 0;
    this = v9->m128i_u32[2];
    if ( v9->m128i_i32[0] >= (int)this )
      goto LABEL_42;
    v13 = v9->m128i_i32[3];
    if ( v9->m128i_i32[1] >= v13 )
      goto LABEL_42;
    v14 = (__m128i *)(v6 + 48);
    v15 = *(int *)(v6 + 176);
    if ( (_DWORD)v15 )
    {
      v16 = 0;
      v17 = *(float *)(v6 + 264) * 50000.0;
      if ( v17 >= 9.223372e18 )
      {
        v17 = v17 - 9.223372e18;
        if ( v17 < 9.223372e18 )
          v16 = 0x8000000000000000uLL;
      }
      v18 = *(float *)(v6 + 264) * 562500.0;
      v19 = v16 + (unsigned int)(int)v17;
      v20 = 0;
      v149 = v19;
      if ( v18 >= 9.223372e18 )
      {
        v18 = v18 - 9.223372e18;
        if ( v18 < 9.223372e18 )
          v20 = 0x8000000000000000uLL;
      }
      this = (unsigned int)(this - v9->m128i_i32[0]);
      v21 = 0;
      v22 = -1;
      Points = 0;
      rect = (const struct FastRegion::Internal::CRgnData *)(v20 + (unsigned int)(int)v18);
      a3 = 0;
      *(_QWORD *)&rect_8.left = 0;
      if ( (int)this <= 0 || (v23 = v13 - v9->m128i_i32[1], v23 <= 0) )
        v145 = 0;
      else
        v145 = (unsigned int)this * (unsigned __int64)(unsigned int)v23;
      v24 = 0;
      if ( (int)v15 > 0 )
      {
        do
        {
          v25 = v14[v24].m128i_i32[0];
          v26 = v14[v24].m128i_i32[1];
          v27 = v14[v24].m128i_i32[3];
          rect_8.right = v14[v24].m128i_i32[2];
          rect_8.left = v25;
          rect_8.top = v26;
          rect_8.bottom = v27;
          if ( rect_8.right - v25 <= 0 || (v28 = v27 - v26, v28 <= 0) )
            v29 = 0;
          else
            v29 = (unsigned int)(rect_8.right - v25) * (unsigned __int64)(unsigned int)v28;
          v30 = (__m128)_mm_loadu_si128((const __m128i *)&rect_8);
          v31 = (__m128)_mm_loadu_si128(v9);
          v32 = _mm_xor_ps(v31, v30);
          v33 = (__m128)_mm_cmpgt_epi32(
                          (__m128i)_mm_unpackhi_pd((__m128d)v31, (__m128d)v30),
                          (__m128i)_mm_unpacklo_pd((__m128d)v31, (__m128d)v30));
          v34 = _mm_and_ps((__m128)_mm_cmpgt_epi32((__m128i)v31, (__m128i)v30), v32);
          v35 = (__m128i)_mm_and_ps((__m128)_mm_srli_si128((__m128i)v33, 4), v33);
          v36 = (__m128)_mm_shuffle_epi32(v35, 0);
          v37 = (__m128)_mm_shuffle_epi32(v35, 170);
          v38 = _mm_and_ps(_mm_xor_ps(_mm_and_ps(v36, v32), v30), _mm_or_ps(v37, v36));
          v39 = (__m128i)_mm_xor_ps(
                           _mm_and_ps(
                             _mm_xor_ps(
                               (__m128)_mm_shuffle_pd((__m128d)_mm_xor_ps(v31, v34), (__m128d)_mm_xor_ps(v30, v34), 2),
                               v38),
                             _mm_and_ps(v37, v36)),
                           v38);
          v40 = _mm_cvtsi128_si32(_mm_srli_si128(v39, 8)) - _mm_cvtsi128_si32(v39);
          if ( v40 <= 0
            || (v41 = (unsigned int)(_mm_cvtsi128_si32(_mm_srli_si128(v39, 12))
                                   - _mm_cvtsi128_si32(_mm_srli_si128(v39, 4))),
                (int)v41 <= 0) )
          {
            v42 = 0;
          }
          else
          {
            v42 = (unsigned int)v40 * v41;
          }
          v43 = (__m128)v14[v24];
          v44 = (__m128)_mm_cmpgt_epi32((__m128i)v31, (__m128i)v43);
          v45 = (__m128d)_mm_or_ps(_mm_andnot_ps(v44, v31), _mm_and_ps(v44, v43));
          v46 = (__m128d)_mm_xor_ps(_mm_and_ps(_mm_xor_ps(v31, v43), v44), v43);
          v47 = _mm_cmpgt_epi32((__m128i)v45, (__m128i)_mm_unpacklo_pd(v45, v46));
          v48 = (__m128i)_mm_and_ps(
                           _mm_and_ps((__m128)_mm_shuffle_epi32(v47, 255), (__m128)_mm_shuffle_epi32(v47, 170)),
                           (__m128)_mm_shuffle_pd(v46, v45, 2));
          rect_8 = (RECT)v48;
          v49 = _mm_cvtsi128_si32(_mm_srli_si128(v48, 8)) - _mm_cvtsi128_si32(v48);
          if ( v49 <= 0
            || (v50 = (unsigned int)(_mm_cvtsi128_si32(_mm_srli_si128(v48, 12))
                                   - _mm_cvtsi128_si32(_mm_srli_si128(v48, 4))),
                (int)v50 <= 0) )
          {
            v51 = 0;
          }
          else
          {
            v51 = (unsigned int)v49 * v50;
          }
          v21 = (struct tagPOINT)(v145 + v29 - v51);
          this = v42 - *(_QWORD *)&v21;
          if ( v22 == -1 || this < a3 )
          {
            Points = v21;
            a3 = this;
            v22 = v24;
            if ( !this )
              break;
          }
          else
          {
            v21 = Points;
          }
          ++v24;
        }
        while ( (int)v24 < (int)v15 );
        v5 = v150;
        v19 = v149;
        *(_QWORD *)&rect_8.left = a3;
      }
      if ( (_DWORD)v15 == 8 || a3 <= (unsigned __int64)rect && (a3 <= v19 || a3 <= *(unsigned __int64 *)&v21 / 0xA) )
      {
        v52 = (__m128)_mm_loadu_si128(v9);
        v53 = (__m128)_mm_loadu_si128(&v14[v22]);
        v54 = _mm_xor_ps(v52, v53);
        v55 = (__m128)_mm_cmpgt_epi32(
                        (__m128i)_mm_unpackhi_pd((__m128d)v52, (__m128d)v53),
                        (__m128i)_mm_unpacklo_pd((__m128d)v52, (__m128d)v53));
        v56 = _mm_and_ps((__m128)_mm_cmpgt_epi32((__m128i)v52, (__m128i)v53), v54);
        v57 = (__m128i)_mm_and_ps((__m128)_mm_srli_si128((__m128i)v55, 4), v55);
        v58 = (__m128)_mm_shuffle_epi32(v57, 0);
        v59 = (__m128)_mm_shuffle_epi32(v57, 170);
        v60 = _mm_and_ps(_mm_xor_ps(_mm_and_ps(v58, v54), v53), _mm_or_ps(v59, v58));
        v14[v22] = (__m128i)_mm_xor_ps(
                              _mm_and_ps(
                                _mm_xor_ps(
                                  (__m128)_mm_shuffle_pd(
                                            (__m128d)_mm_xor_ps(v52, v56),
                                            (__m128d)_mm_xor_ps(v56, v53),
                                            2),
                                  v60),
                                _mm_and_ps(v59, v58)),
                              v60);
        this = *(unsigned int *)(v6 + 176);
        if ( (int)this > 1 )
        {
          v61 = v149;
          v62 = rect;
          while ( 1 )
          {
            LODWORD(v145) = -1;
            FindBestMerge(
              v6 + 48,
              this,
              v22,
              (_DWORD)v14 + 16 * v22,
              (__int64)&v145,
              (__int64)&rect_8,
              (__int64)&Points);
            this = *(_QWORD *)&rect_8.left;
            if ( *(_QWORD *)&rect_8.left > (unsigned __int64)v62
              || *(_QWORD *)&rect_8.left > v61 && *(_QWORD *)&rect_8.left > *(unsigned __int64 *)&Points / 0xA )
            {
              break;
            }
            v131 = (__m128)_mm_loadu_si128(&v14[v22]);
            v132 = v145;
            a3 = (unsigned int)v22;
            v133 = (__m128)_mm_loadu_si128(&v14[(int)v145]);
            v134 = _mm_xor_ps(v131, v133);
            v135 = (__m128)_mm_cmpgt_epi32(
                             (__m128i)_mm_unpackhi_pd((__m128d)v131, (__m128d)v133),
                             (__m128i)_mm_unpacklo_pd((__m128d)v131, (__m128d)v133));
            v136 = _mm_and_ps((__m128)_mm_cmpgt_epi32((__m128i)v131, (__m128i)v133), v134);
            v137 = (__m128i)_mm_and_ps((__m128)_mm_srli_si128((__m128i)v135, 4), v135);
            v138 = (__m128)_mm_shuffle_epi32(v137, 0);
            v139 = (__m128)_mm_shuffle_epi32(v137, 170);
            v140 = _mm_and_ps(_mm_xor_ps(_mm_and_ps(v138, v134), v133), _mm_or_ps(v139, v138));
            v14[(int)v145] = (__m128i)_mm_xor_ps(
                                        _mm_and_ps(
                                          _mm_xor_ps(
                                            (__m128)_mm_shuffle_pd(
                                                      (__m128d)_mm_xor_ps(v131, v136),
                                                      (__m128d)_mm_xor_ps(v136, v133),
                                                      2),
                                            v140),
                                          _mm_and_ps(v139, v138)),
                                        v140);
            v141 = *(_DWORD *)(v6 + 176);
            if ( v22 < v141 - 1 )
            {
              do
              {
                v143 = (int)a3;
                a3 = (unsigned int)(a3 + 1);
                v14[v143] = v14[v143 + 1];
                v141 = *(_DWORD *)(v6 + 176);
              }
              while ( (int)a3 < v141 - 1 );
            }
            this = (unsigned int)(v141 - 1);
            *(_DWORD *)(v6 + 176) = this;
            if ( v132 > v22 )
              --v132;
            if ( (int)this <= 1 )
              break;
            v22 = v132;
          }
          v5 = v150;
          v11 = v6 + 184;
        }
        goto LABEL_41;
      }
      v14[v15] = *v9;
    }
    else
    {
      *v14 = *v9;
    }
    ++*(_DWORD *)(v6 + 176);
LABEL_41:
    a4 = (HDC *)v146;
LABEL_42:
    v10 = (_DWORD *)(v6 + 176);
    v8 = hWnd;
    LOBYTE(this) = *(_BYTE *)(v6 + 8) & 0xFE;
    goto LABEL_43;
  }
  v152 = (_DWORD *)(v6 + 176);
LABEL_43:
  v63 = this ^ (this ^ (8 * this)) & 0x10;
  *(_BYTE *)(v6 + 8) = v63;
  if ( (v63 & 2) != 0 )
  {
    *(_BYTE *)(v6 + 8) = v63 & 0xFD;
    if ( *v10 )
      goto LABEL_48;
    if ( !*(_QWORD *)v11 )
    {
      v114 = (void *)*((_QWORD *)v5 + 9);
      if ( v114 )
      {
        DeleteObject(v114);
        *((_QWORD *)v5 + 9) = 0;
      }
      if ( *(_QWORD *)v5 > 1u )
        MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, *(void **)v5, (void *)a3);
      *(_QWORD *)v5 = 0;
      return 1;
    }
  }
  if ( !*v10 && !*(_QWORD *)v11 )
  {
    if ( (Microsoft_IEEnableBits & 0x20) == 0 )
      return 0;
    v142 = 80;
    goto LABEL_189;
  }
LABEL_48:
  DCEx = GetDCEx(v8, 0, 0x12u);
  v149 = (unsigned __int64)DCEx;
  v65 = DCEx;
  if ( !DCEx )
  {
    if ( (Microsoft_IEEnableBits & 0x20) == 0 )
      return 0;
    v142 = 96;
LABEL_189:
    McTemplateU0xx_EventWriteTransfer(this, &MSHTML_CPAINTCONTROLLER_CANNOTPAINTNOW, v6, v142);
    return 0;
  }
  *a4 = DCEx;
  if ( (byte_18158CB73 & 0x10) != 0
    && !(unsigned __int8)IEConfiguration_GetBool(268435481)
    && (*(_BYTE *)(v6 + 8) & 0x20) == 0 )
  {
    rect_8 = g_Zero;
    rect = (const struct FastRegion::Internal::CRgnData *)CreateRectRgnIndirect(&rect_8);
    v66 = (HRGN)rect;
    if ( rect )
      goto LABEL_53;
    LastError = GetLastError();
    v92 = LastError < 0;
    if ( LastError > 0 )
      v92 = 1;
    if ( !v92 )
    {
LABEL_53:
      v67 = hWnd;
      Points = 0;
      v146 = 0;
      MapWindowPoints(hWnd, 0, &Points, 1u);
      RandomRgn = GetRandomRgn(v65, v66, 4);
      if ( !RandomRgn )
      {
        if ( (Microsoft_IEEnableBits & 0x20) == 0 )
          goto LABEL_123;
        v127 = 112;
        goto LABEL_185;
      }
      if ( RandomRgn < 0 )
        goto LABEL_89;
      if ( !OffsetRgn(v66, -Points.x, -Points.y) )
        goto LABEL_89;
      MapWindowPoints(v67, 0, &v146, 1u);
      if ( Points.x != v146.x || Points.y != v146.y )
        goto LABEL_89;
      CBufferedRegion::PublishRegion((CBufferedRegion *)(v6 + 48));
      v70 = (void **)(v6 + 184);
      if ( !*(_QWORD *)(v6 + 184) )
      {
LABEL_87:
        if ( *v152 || *(_QWORD *)v11 )
        {
LABEL_89:
          DeleteObject(v66);
          goto LABEL_95;
        }
        if ( (Microsoft_IEEnableBits & 0x20) == 0 )
        {
LABEL_123:
          DeleteObject(v66);
          return 0;
        }
        v127 = 128;
LABEL_185:
        McTemplateU0xx_EventWriteTransfer(v69, &MSHTML_CPAINTCONTROLLER_CANNOTPAINTNOW, v6, v127);
        goto LABEL_123;
      }
      v71 = *(void **)(v6 + 256);
      if ( v71 )
      {
        DeleteObject(v71);
        *(_QWORD *)(v6 + 256) = 0;
      }
      v153 = 0;
      RegionData = GetRegionData(v66, 0, 0);
      v74 = RegionData;
      if ( RegionData )
      {
        v75 = (struct _RGNDATA *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, RegionData);
        v76 = v75;
        if ( v75 )
        {
          if ( GetRegionData(v66, v74, v75) == v74 && v76->rdh.iType == 1 )
          {
            nCount = v76->rdh.nCount;
            if ( nCount )
            {
              RgnOfRectAry = (struct FastRegion::Internal::CRgnData **)CRegion2::MakeRgnOfRectAry(
                                                                         (const struct CRect *)((char *)v76
                                                                                              + v76->rdh.dwSize),
                                                                         nCount);
              v118 = RgnOfRectAry;
              if ( RgnOfRectAry )
              {
                v119 = v153;
                v120 = *RgnOfRectAry;
                if ( v153 == (struct FastRegion::Internal::CRgnData *)1 )
                {
                  if ( v120 == (struct FastRegion::Internal::CRgnData *)1 )
                  {
                    FastRegion::Internal::CRgnData::Copy(
                      (FastRegion::Internal::CRgnData *)v155,
                      (const struct FastRegion::Internal::CRgnData *)(v118 + 1));
                    FastRegion::Internal::CRgnData::Copy(
                      (FastRegion::Internal::CRgnData *)(v118 + 1),
                      (const struct FastRegion::Internal::CRgnData *)v154);
                    v129 = (const struct FastRegion::Internal::CRgnData *)v155;
                    v128 = (FastRegion::Internal::CRgnData *)v154;
                  }
                  else
                  {
                    v153 = v120;
                    v128 = (FastRegion::Internal::CRgnData *)(v118 + 1);
                    *v118 = (struct FastRegion::Internal::CRgnData *)1;
                    v129 = (const struct FastRegion::Internal::CRgnData *)v154;
                  }
                  FastRegion::Internal::CRgnData::Copy(v128, v129);
                }
                else if ( v120 == (struct FastRegion::Internal::CRgnData *)1 )
                {
                  *v118 = v153;
                  v153 = (struct FastRegion::Internal::CRgnData *)1;
                  v121 = 0;
                  v154[0] = *((_DWORD *)v118 + 2);
                  v154[1] = *((_DWORD *)v118 + 3);
                  v154[2] = *((_DWORD *)v118 + 4);
                  v122 = (__int64)v118 + *((int *)v118 + 6) + 20;
                  v123 = &v154[2 * v154[0] + 3];
                  if ( v154[0] > 0 )
                  {
                    do
                    {
                      v124 = v121++;
                      v154[2 * v124 + 3] = HIDWORD(v118[v124 + 2]);
                      v154[2 * v124 + 4] = (_DWORD)v118
                                         + 20
                                         + 8 * v124
                                         + (((_DWORD)v123 - v122) & 0xFFFFFFFC)
                                         + LODWORD(v118[v124 + 3])
                                         - (unsigned int)&v154[2 * v124 + 3];
                    }
                    while ( v121 < v154[0] );
                    v5 = v150;
                  }
                  v117 = 0;
                  v125 = (_DWORD *)&v118[*((int *)v118 + 2) + 1] + 1;
                  v126 = (unsigned __int64)((int)v125 + v125[1] - ((int)v118 + 20) - *((_DWORD *)v118 + 6)) >> 2;
                  if ( (int)v126 > 0 )
                  {
                    do
                    {
                      v123[v117] = *(_DWORD *)(v122 + 4 * v117);
                      v117 = (unsigned int)(v117 + 1);
                    }
                    while ( (int)v117 < (int)v126 );
                  }
                }
                else
                {
                  v153 = v120;
                  *v118 = v119;
                }
                CRegion2::`scalar deleting destructor'((CRegion2 *)v118, v117);
              }
              v66 = (HRGN)rect;
            }
            else
            {
              if ( (unsigned __int64)v153 > 1 )
                MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v153, v77);
              v153 = 0;
            }
          }
          MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v76, v77);
        }
      }
      if ( v153 )
      {
        v78 = (const struct FastRegion::Internal::CRgnData *)*v70;
        if ( !*v70 )
        {
LABEL_84:
          if ( (unsigned __int64)v153 > 1 )
            MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v153, (void *)v73);
          v65 = (HDC)v149;
          goto LABEL_87;
        }
        if ( *v70 == (void *)1 )
          v78 = (const struct FastRegion::Internal::CRgnData *)(v6 + 192);
        v79 = (struct FastRegion::Internal::CRgnData *)v154;
        if ( v153 != (struct FastRegion::Internal::CRgnData *)1 )
          v79 = v153;
        rect = v79;
        v80 = FastRegion::Internal::CRgnData::EstimateSizeIntersect(v78, v79);
        if ( v80 > 200 )
        {
          v81 = (FastRegion::Internal::CRgnData *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v80);
          if ( !v81 )
            goto LABEL_84;
        }
        else
        {
          v81 = (FastRegion::Internal::CRgnData *)v156;
        }
        FastRegion::Internal::CRgnData::Intersect(v81, v78, rect);
        if ( (unsigned __int64)*v70 > 1 )
          MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, *v70, v82);
        v73 = *(unsigned int *)v81;
        if ( (_DWORD)v73 )
        {
          v83 = (unsigned int *)((char *)v81 + 12);
          v84 = *((_DWORD *)v81 + 2 * (int)v73 + 2) + 8 * v73 - *((_DWORD *)v81 + 4) - 12 + 8 * (v73 - 1) + 24;
          if ( v84 > 60 )
          {
            v69 = (unsigned int *)v156;
            if ( v81 == (FastRegion::Internal::CRgnData *)v156 )
            {
              v130 = (FastRegion::Internal::CRgnData *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v84);
              *v70 = v130;
              if ( v130 )
                FastRegion::Internal::CRgnData::Copy(v130, v81);
            }
            else
            {
              *v70 = v81;
            }
          }
          else
          {
            *v70 = (void *)1;
            v85 = 0;
            v86 = *(_DWORD *)v81;
            *(_DWORD *)(v6 + 192) = *(_DWORD *)v81;
            *(_DWORD *)(v6 + 196) = *((_DWORD *)v81 + 1);
            *(_DWORD *)(v6 + 200) = *((_DWORD *)v81 + 2);
            v87 = (__int64)v81 + *((int *)v81 + 4) + 12;
            v88 = (char *)&v70[v86 + 1] + 4;
            if ( v86 > 0 )
            {
              do
              {
                v89 = v85++;
                HIDWORD(v70[v89 + 2]) = *((_DWORD *)v81 + 2 * v89 + 3);
                *(_DWORD *)(v6 + 204 + 8 * v89 + 4) = (_DWORD)v83
                                                    + 8 * v89
                                                    + (((_DWORD)v88 + 8 - v87) & 0xFFFFFFFC)
                                                    + v83[2 * v89 + 1]
                                                    - (v6
                                                     + 204
                                                     + 8 * v89);
              }
              while ( v85 < *(_DWORD *)(v6 + 192) );
              v5 = v150;
            }
            v90 = 0;
            v69 = (unsigned int *)((char *)v81 + 8 * *(int *)v81 + 4);
            v73 = (unsigned __int64)(int)((_DWORD)v69 + v69[1] - *((_DWORD *)v81 + 4) - (_DWORD)v83) >> 2;
            if ( (int)v73 > 0 )
            {
              do
              {
                *(_DWORD *)&v88[4 * v90 + 8] = *(_DWORD *)(v87 + 4 * v90);
                v90 = (unsigned int)(v90 + 1);
              }
              while ( (int)v90 < (int)v73 );
            }
            if ( v81 != (FastRegion::Internal::CRgnData *)v156 )
              MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v81, (void *)v73);
          }
          goto LABEL_84;
        }
        if ( v81 != (FastRegion::Internal::CRgnData *)v156 )
          MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v81, (void *)v73);
      }
      else
      {
        CRegion2::FreeMemory((CRegion2 *)(v6 + 184));
      }
      *v70 = 0;
      goto LABEL_84;
    }
  }
LABEL_95:
  CBufferedRegion::PublishRegion((CBufferedRegion *)(v6 + 48));
  v93 = (int **)(v6 + 184);
  v94 = *(HRGN *)(v6 + 256);
  if ( v94 || (v94 = CRegion2::ConvertToWindows((CRegion2 *)(v6 + 184)), (*(_QWORD *)(v6 + 256) = v94) != 0) )
  {
    SelectClipRgn(v65, v94);
    CBufferedRegion::PublishRegion((CBufferedRegion *)(v6 + 48));
    v96 = (void *)*((_QWORD *)v5 + 9);
    if ( v96 )
    {
      DeleteObject(v96);
      *((_QWORD *)v5 + 9) = 0;
    }
    if ( *(_QWORD *)v5 > 1u )
      MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, *(void **)v5, v95);
    v97 = *v93;
    if ( *v93 )
    {
      if ( *v93 == (int *)1 )
        v97 = (int *)(v6 + 192);
      v98 = v97[2 * *v97 + 2] - v97[4] + 8 * *v97 - 12 + 8 * (*v97 - 1) + 24;
      if ( v98 <= 60 )
      {
        *(_QWORD *)v5 = 1;
        goto LABEL_135;
      }
      v99 = MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v98);
      *(_QWORD *)v5 = v99;
      v100 = (_DWORD *)v99;
      if ( v99 )
      {
        if ( v99 != 1 )
        {
LABEL_107:
          v101 = *v93;
          if ( *v93 == (int *)1 )
            v101 = (int *)(v6 + 192);
          v102 = *v101;
          *v100 = *v101;
          v103 = 0;
          v100[1] = v101[1];
          v100[2] = v101[2];
          v104 = (__int64)v101 + v101[4] + 12;
          v105 = &v100[2 * v102 + 3];
          if ( v102 > 0 )
          {
            do
            {
              v106 = v103++;
              v100[2 * v106 + 3] = v101[2 * v106 + 3];
              v100[2 * v106 + 4] = (_DWORD)v101
                                 + 8 * v106
                                 + 4 * (((__int64)v105 - v104) >> 2)
                                 + v101[2 * v106 + 4]
                                 - ((_DWORD)v100
                                  + 8 * v106);
            }
            while ( v103 < *v100 );
          }
          v107 = 0;
          v108 = &v101[2 * *v101 + 1];
          v109 = (unsigned __int64)((int)v108 + v108[1] - ((int)v101 + 12) - v101[4]) >> 2;
          if ( (int)v109 > 0 )
          {
            do
            {
              v105[v107] = *(_DWORD *)(v104 + 4 * v107);
              v107 = (unsigned int)(v107 + 1);
            }
            while ( (int)v107 < (int)v109 );
          }
          goto LABEL_113;
        }
LABEL_135:
        v100 = (_DWORD *)((char *)v5 + 8);
        goto LABEL_107;
      }
    }
    else
    {
      *(_QWORD *)v5 = 0;
    }
LABEL_113:
    v110 = (HRGN)*((_QWORD *)v5 + 9);
    if ( v110 || (v110 = CRegion2::ConvertToWindows(v5), (*((_QWORD *)v5 + 9) = v110) != 0) )
      ValidateRgn(hWnd, v110);
    *v152 = 0;
    v112 = *(void **)(v11 + 72);
    if ( v112 )
    {
      DeleteObject(v112);
      *(_QWORD *)(v11 + 72) = 0;
    }
    if ( *(_QWORD *)v11 > 1u )
      MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, *(void **)v11, v111);
    *(_QWORD *)v11 = 0;
    *(_BYTE *)(v6 + 8) &= ~1u;
    return 1;
  }
  if ( (Microsoft_IEEnableBits & 0x20) != 0 )
  {
    v142 = 144;
    goto LABEL_189;
  }
  return 0;
}

```

## disassembly

```asm
0x18045ed60  mov     rax, rsp
0x18045ed63  push    rbp
0x18045ed64  push    rbx
0x18045ed65  push    rsi
0x18045ed66  push    rdi
0x18045ed67  push    r12
0x18045ed69  push    r13
0x18045ed6b  push    r14
0x18045ed6d  push    r15
0x18045ed6f  lea     rbp, [rax-178h]
0x18045ed76  sub     rsp, 238h
0x18045ed7d  movaps  xmmword ptr [rax-58h], xmm6
0x18045ed81  movaps  xmmword ptr [rax-68h], xmm7
0x18045ed85  movaps  xmmword ptr [rax-78h], xmm8
0x18045ed8a  mov     rax, cs:__security_cookie
0x18045ed91  xor     rax, rsp
0x18045ed94  mov     [rbp+170h+var_80], rax
0x18045ed9b  mov     r15, [rbp+170h+arg_20]
0x18045eda2  mov     r14, rcx
0x18045eda5  mov     cl, [rcx+8]
0x18045eda8  mov     rbx, r9
0x18045edab  mov     [rbp+170h+hWnd], rdx
0x18045edaf  mov     r9, rdx
0x18045edb2  mov     qword ptr [rsp+270h+var_220.x], rbx
0x18045edb7  mov     rdi, r8
0x18045edba  mov     [rsp+270h+var_1F8], r15
0x18045edbf  lea     rdx, [r14+0B0h]
0x18045edc6  mov     [rbp+170h+var_1E8], rdx
0x18045edca  lea     r12, [r14+0B8h]
0x18045edd1  test    cl, 1
0x18045edd4  jz      loc_18045F8A4
0x18045edda  mov     dword ptr [rdx], 0
0x18045ede0  mov     rcx, [r12+48h]; ho
0x18045ede5  test    rcx, rcx
0x18045ede8  jz      short loc_18045EDF9
0x18045edea  call    cs:__imp_DeleteObject
0x18045edf0  mov     qword ptr [r12+48h], 0
0x18045edf9  cmp     qword ptr [r12], 1
0x18045edfe  jbe     short loc_18045EE10
0x18045ee00  mov     rdx, [r12]; void *
0x18045ee04  mov     rcx, cs:g_hProcessHeap; this
0x18045ee0b  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x18045ee10  mov     qword ptr [r12], 0
0x18045ee18  mov     ecx, [rdi+8]
0x18045ee1b  cmp     [rdi], ecx
0x18045ee1d  jge     loc_18045F223
0x18045ee23  mov     eax, [rdi+0Ch]
0x18045ee26  cmp     [rdi+4], eax
0x18045ee29  jge     loc_18045F223
0x18045ee2f  lea     rbx, [r14+30h]
0x18045ee33  movsxd  r13, dword ptr [rbx+80h]
0x18045ee3a  test    r13d, r13d
0x18045ee3d  jz      loc_18045F211
0x18045ee43  movss   xmm0, dword ptr [rbx+0D8h]
0x18045ee4b  xor     edx, edx
0x18045ee4d  movss   xmm2, cs:__real@5f000000
0x18045ee55  movaps  xmm1, xmm0
0x18045ee58  mulss   xmm1, cs:__real@47435000
0x18045ee60  mov     r8, 8000000000000000h
0x18045ee6a  comiss  xmm1, xmm2
0x18045ee6d  jb      short loc_18045EE7B
0x18045ee6f  subss   xmm1, xmm2
0x18045ee73  comiss  xmm1, xmm2
0x18045ee76  jnb     short loc_18045EE7B
0x18045ee78  mov     rdx, r8
0x18045ee7b  mulss   xmm0, cs:__real@49095440
0x18045ee83  cvttss2si r10, xmm1
0x18045ee88  add     r10, rdx
0x18045ee8b  xor     edx, edx
0x18045ee8d  comiss  xmm0, xmm2
0x18045ee90  mov     [rsp+270h+var_200], r10
0x18045ee95  jb      short loc_18045EEA3
0x18045ee97  subss   xmm0, xmm2
0x18045ee9b  comiss  xmm0, xmm2
0x18045ee9e  jnb     short loc_18045EEA3
0x18045eea0  mov     rdx, r8
0x18045eea3  sub     ecx, [rdi]
0x18045eea5  xor     r9d, r9d
0x18045eea8  cvttss2si r8, xmm0
0x18045eead  or      esi, 0FFFFFFFFh
0x18045eeb0  mov     qword ptr [rsp+270h+Points.x], r9
0x18045eeb5  add     r8, rdx
0x18045eeb8  mov     qword ptr [rsp+270h+rect.left], r8
0x18045eebd  xor     r8d, r8d
0x18045eec0  mov     qword ptr [rsp+270h+rect.right], r8
0x18045eec5  test    ecx, ecx
0x18045eec7  jle     loc_18045FA3E
0x18045eecd  sub     eax, [rdi+4]
0x18045eed0  test    eax, eax
0x18045eed2  jle     loc_18045FA3E
0x18045eed8  mov     edx, eax
0x18045eeda  mov     eax, ecx
0x18045eedc  imul    rdx, rax
0x18045eee0  mov     [rsp+270h+var_228], rdx
0x18045eee5  xor     r11d, r11d
0x18045eee8  test    r13d, r13d
0x18045eeeb  jle     loc_18045F0DC
0x18045eef1  mov     r15, [rsp+270h+var_228]
0x18045eef6  mov     edx, r11d
0x18045eef9  add     rdx, rdx
0x18045eefc  mov     r10d, [rbx+rdx*8+8]
0x18045ef01  mov     eax, [rbx+rdx*8]
0x18045ef04  mov     r9d, [rbx+rdx*8+4]
0x18045ef09  mov     ecx, [rbx+rdx*8+0Ch]
0x18045ef0d  mov     dword ptr [rsp+270h+var_208], r10d
0x18045ef12  sub     r10d, eax
0x18045ef15  mov     [rsp+270h+rect.right], eax
0x18045ef19  mov     [rsp+270h+rect.bottom], r9d
0x18045ef1e  mov     dword ptr [rsp+270h+var_208+4], ecx
0x18045ef22  test    r10d, r10d
0x18045ef25  jle     loc_18045F8AD
0x18045ef2b  sub     ecx, r9d
0x18045ef2e  test    ecx, ecx
0x18045ef30  jle     loc_18045F8AD
0x18045ef36  mov     r9d, ecx
0x18045ef39  mov     eax, r10d
0x18045ef3c  imul    r9, rax
0x18045ef40  movdqu  xmm6, xmmword ptr [rsp+270h+rect.right]
0x18045ef46  movdqu  xmm8, xmmword ptr [rdi]
0x18045ef4b  movdqa  xmm5, xmm6
0x18045ef4f  movaps  xmm0, xmm8
0x18045ef53  movaps  xmm1, xmm8
0x18045ef57  unpcklpd xmm0, xmm6
0x18045ef5b  movdqa  xmm4, xmm8
0x18045ef60  xorps   xmm4, xmm6
0x18045ef63  unpckhpd xmm1, xmm6
0x18045ef67  pcmpgtd xmm1, xmm0
0x18045ef6b  movdqa  xmm7, xmm8
0x18045ef70  movdqa  xmm0, xmm1
0x18045ef74  pcmpgtd xmm7, xmm6
0x18045ef78  andps   xmm7, xmm4
0x18045ef7b  psrldq  xmm0, 4
0x18045ef80  andps   xmm0, xmm1
0x18045ef83  xorps   xmm5, xmm7
0x18045ef86  pshufd  xmm1, xmm0, 0
0x18045ef8b  pshufd  xmm2, xmm0, 0AAh
0x18045ef90  movdqa  xmm3, xmm1
0x18045ef94  andps   xmm3, xmm4
0x18045ef97  movdqa  xmm0, xmm2
0x18045ef9b  orps    xmm0, xmm1
0x18045ef9e  movdqa  xmm4, xmm8
0x18045efa3  xorps   xmm4, xmm7
0x18045efa6  xorps   xmm3, xmm6
0x18045efa9  andps   xmm3, xmm0
0x18045efac  shufpd  xmm4, xmm5, 2
0x18045efb1  xorps   xmm4, xmm3
0x18045efb4  andps   xmm2, xmm1
0x18045efb7  andps   xmm4, xmm2
0x18045efba  xorps   xmm4, xmm3
0x18045efbd  movdqa  xmm0, xmm4
0x18045efc1  movd    eax, xmm4
0x18045efc5  psrldq  xmm0, 8
0x18045efca  movd    r10d, xmm0
0x18045efcf  sub     r10d, eax
0x18045efd2  test    r10d, r10d
0x18045efd5  jle     loc_18045F8B5
0x18045efdb  movdqa  xmm0, xmm4
0x18045efdf  psrldq  xmm4, 4
0x18045efe4  psrldq  xmm0, 0Ch
0x18045efe9  movd    ecx, xmm0
0x18045efed  movd    eax, xmm4
0x18045eff1  sub     ecx, eax
0x18045eff3  test    ecx, ecx
0x18045eff5  jle     loc_18045F8B5
0x18045effb  mov     eax, r10d
0x18045effe  imul    rcx, rax
0x18045f002  movups  xmm2, xmmword ptr [rbx+rdx*8]
0x18045f006  movdqa  xmm1, xmm8
0x18045f00b  pcmpgtd xmm1, xmm2
0x18045f00f  movdqa  xmm3, xmm1
0x18045f013  movdqa  xmm0, xmm1
0x18045f017  andps   xmm0, xmm2
0x18045f01a  andnps  xmm3, xmm8
0x18045f01e  orps    xmm3, xmm0
0x18045f021  xorps   xmm8, xmm2
0x18045f025  andps   xmm8, xmm1
0x18045f029  movaps  xmm0, xmm3
0x18045f02c  xorps   xmm8, xmm2
0x18045f030  movdqa  xmm1, xmm3
0x18045f034  unpcklpd xmm0, xmm8
0x18045f039  pcmpgtd xmm1, xmm0
0x18045f03d  shufpd  xmm8, xmm3, 2
0x18045f043  pshufd  xmm0, xmm1, 0AAh
0x18045f048  pshufd  xmm2, xmm1, 0FFh
0x18045f04d  andps   xmm2, xmm0
0x18045f050  andps   xmm2, xmm8
0x18045f054  movdqa  xmm0, xmm2
0x18045f058  movd    eax, xmm2
0x18045f05c  psrldq  xmm0, 8
0x18045f061  movd    r10d, xmm0
0x18045f066  movdqu  xmmword ptr [rsp+270h+rect.right], xmm2
0x18045f06c  sub     r10d, eax
0x18045f06f  test    r10d, r10d
0x18045f072  jle     loc_18045F8BC
0x18045f078  movdqa  xmm0, xmm2
0x18045f07c  psrldq  xmm2, 4
0x18045f081  psrldq  xmm0, 0Ch
0x18045f086  movd    edx, xmm0
0x18045f08a  movd    eax, xmm2
0x18045f08e  sub     edx, eax
0x18045f090  test    edx, edx
0x18045f092  jle     loc_18045F8BC
0x18045f098  mov     eax, r10d
0x18045f09b  imul    rdx, rax
0x18045f09f  sub     r9, rdx
0x18045f0a2  add     r9, r15
0x18045f0a5  sub     rcx, r9
0x18045f0a8  cmp     esi, 0FFFFFFFFh
0x18045f0ab  jnz     loc_18045F593
0x18045f0b1  mov     qword ptr [rsp+270h+Points.x], r9
0x18045f0b6  mov     r8, rcx
0x18045f0b9  mov     esi, r11d
0x18045f0bc  test    rcx, rcx
0x18045f0bf  jz      short loc_18045F0CD
0x18045f0c1  inc     r11d
0x18045f0c4  cmp     r11d, r13d
0x18045f0c7  jl      loc_18045EEF6
0x18045f0cd  mov     r15, [rsp+270h+var_1F8]
0x18045f0d2  mov     r10, [rsp+270h+var_200]
0x18045f0d7  mov     qword ptr [rsp+270h+rect.right], r8
0x18045f0dc  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18045f0e6  cmp     r13d, 8
0x18045f0ea  jnz     loc_18045F858
0x18045f0f0  movdqu  xmm8, xmmword ptr [rdi]
0x18045f0f5  movsxd  rax, esi
0x18045f0f8  add     rax, rax
0x18045f0fb  movaps  xmm0, xmm8
0x18045f0ff  movaps  xmm1, xmm8
0x18045f103  movdqa  xmm4, xmm8
0x18045f108  movdqa  xmm7, xmm8
0x18045f10d  movdqu  xmm5, xmmword ptr [rbx+rax*8]
0x18045f112  unpcklpd xmm0, xmm5
0x18045f116  xorps   xmm4, xmm5
0x18045f119  unpckhpd xmm1, xmm5
0x18045f11d  pcmpgtd xmm7, xmm5
0x18045f121  pcmpgtd xmm1, xmm0
0x18045f125  andps   xmm7, xmm4
0x18045f128  xorps   xmm8, xmm7
0x18045f12c  movdqa  xmm0, xmm1
0x18045f130  psrldq  xmm0, 4
0x18045f135  movdqa  xmm6, xmm7
0x18045f139  andps   xmm0, xmm1
0x18045f13c  xorps   xmm6, xmm5
0x18045f13f  pshufd  xmm1, xmm0, 0
0x18045f144  pshufd  xmm2, xmm0, 0AAh
0x18045f149  movdqa  xmm3, xmm1
0x18045f14d  shufpd  xmm8, xmm6, 2
0x18045f153  andps   xmm3, xmm4
0x18045f156  movdqa  xmm0, xmm2
0x18045f15a  xorps   xmm3, xmm5
0x18045f15d  orps    xmm0, xmm1
0x18045f160  andps   xmm2, xmm1
0x18045f163  andps   xmm3, xmm0
0x18045f166  xorps   xmm8, xmm3
0x18045f16a  andps   xmm8, xmm2
0x18045f16e  xorps   xmm8, xmm3
0x18045f172  movdqu  xmmword ptr [rbx+rax*8], xmm8
0x18045f178  mov     ecx, [rbx+80h]
0x18045f17e  cmp     ecx, 1
0x18045f181  jle     loc_18045F21E
0x18045f187  mov     rdi, [rsp+270h+var_200]
0x18045f18c  mov     r12, 0CCCCCCCCCCCCCCCDh
0x18045f196  mov     r15, qword ptr [rsp+270h+rect.left]
0x18045f19b  lea     rax, [rsp+270h+Points]
0x18045f1a0  movsxd  r13, esi
0x18045f1a3  mov     [rsp+270h+var_240], rax
0x18045f1a8  mov     edx, ecx
0x18045f1aa  lea     rax, [rsp+270h+rect.right]
0x18045f1af  shl     r13, 4
0x18045f1b3  mov     [rsp+270h+var_248], rax
0x18045f1b8  add     r13, rbx
0x18045f1bb  lea     rax, [rsp+270h+var_228]
0x18045f1c0  mov     dword ptr [rsp+270h+var_228], 0FFFFFFFFh
0x18045f1c8  mov     r9, r13
0x18045f1cb  mov     [rsp+270h+var_250], rax
0x18045f1d0  mov     r8d, esi
0x18045f1d3  mov     rcx, rbx
0x18045f1d6  call    FindBestMerge
0x18045f1db  mov     rcx, qword ptr [rsp+270h+rect.right]
0x18045f1e0  cmp     rcx, r15
0x18045f1e3  ja      short loc_18045F203
0x18045f1e5  cmp     rcx, rdi
0x18045f1e8  jbe     loc_18045FACE
0x18045f1ee  mov     rax, r12
0x18045f1f1  mul     qword ptr [rsp+270h+Points.x]
0x18045f1f6  shr     rdx, 3
0x18045f1fa  cmp     rcx, rdx
0x18045f1fd  jbe     loc_18045FACE
0x18045f203  mov     r15, [rsp+270h+var_1F8]
0x18045f208  lea     r12, [r14+0B8h]
0x18045f20f  jmp     short loc_18045F21E
0x18045f211  movups  xmm0, xmmword ptr [rdi]
0x18045f214  movdqu  xmmword ptr [rbx], xmm0
0x18045f218  inc     dword ptr [rbx+80h]
0x18045f21e  mov     rbx, qword ptr [rsp+270h+var_220.x]
0x18045f223  mov     cl, [r14+8]
0x18045f227  lea     rdx, [r14+0B0h]
0x18045f22e  mov     r9, [rbp+170h+hWnd]
0x18045f232  and     cl, 0FEh
0x18045f235  mov     al, cl
  ... truncated ...
```
