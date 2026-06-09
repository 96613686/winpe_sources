# CPaintHandler::BeginPaint(HWND__ *,CRect const &,HDC__ * *,CRegion &)

- ea: `0x18031b6e0`
- end: `0x18031c678`
- name: `?BeginPaint@CPaintHandler@@MEAA_NPEAUHWND__@@AEBVCRect@@PEAPEAUHDC__@@AEAVCRegion@@@Z`
- size: `3992`
- prototype: `bool __fastcall(CPaintHandler *__hidden this, HWND, const struct CRect *, HDC *, struct CRegion *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18031b5f0`

## callees

- `0x18005d080`
- `0x18005e684`
- `0x1801f1e70`
- `0x1801f26c8`
- `0x1802a578c`
- `0x1802b0a28`
- `0x1802cef14`
- `0x18031a8b0`
- `0x18031b6e0`
- `0x18031c680`
- `0x18031c8a0`
- `0x18031cb30`
- `0x1807be714`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18031bf6e`
- `KERNEL32!GetLastError` at `0x18031bf6e`
- `GDI32!GetRegionData` at `0x18031bd73`
- `GDI32!GetRegionData` at `0x18031bda3`
- `GDI32!GetRegionData` at `0x18031bd73`
- `GDI32!GetRegionData` at `0x18031bda3`
- `GDI32!DeleteObject` at `0x18031b76a`
- `GDI32!DeleteObject` at `0x18031bd4f`
- `GDI32!DeleteObject` at `0x18031bf4d`
- `GDI32!DeleteObject` at `0x18031bfda`
- `GDI32!DeleteObject` at `0x18031c167`
- `GDI32!DeleteObject` at `0x18031c1b4`
- `GDI32!DeleteObject` at `0x18031c202`
- `GDI32!DeleteObject` at `0x18031b76a`
- `GDI32!DeleteObject` at `0x18031bd4f`
- `GDI32!DeleteObject` at `0x18031bf4d`
- `GDI32!DeleteObject` at `0x18031bfda`
- `GDI32!DeleteObject` at `0x18031c167`
- `GDI32!DeleteObject` at `0x18031c1b4`
- `GDI32!DeleteObject` at `0x18031c202`
- `GDI32!CreateRectRgnIndirect` at `0x18031bc60`
- `GDI32!CreateRectRgnIndirect` at `0x18031bc60`
- `GDI32!GetRandomRgn` at `0x18031bcb5`
- `GDI32!GetRandomRgn` at `0x18031bcb5`
- `GDI32!OffsetRgn` at `0x18031bce0`
- `GDI32!OffsetRgn` at `0x18031bce0`
- `GDI32!SelectClipRgn` at `0x18031bfbc`
- `GDI32!SelectClipRgn` at `0x18031bfbc`
- `USER32!ValidateRgn` at `0x18031c147`
- `USER32!ValidateRgn` at `0x18031c147`
- `USER32!GetDCEx` at `0x18031bbfd`
- `USER32!GetDCEx` at `0x18031bbfd`
- `USER32!MapWindowPoints` at `0x18031bc9d`
- `USER32!MapWindowPoints` at `0x18031bd04`
- `USER32!MapWindowPoints` at `0x18031bc9d`
- `USER32!MapWindowPoints` at `0x18031bd04`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18031bc2f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18031bc2f`

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
  __int64 v81; // r8
  FastRegion::Internal::CRgnData *v82; // rbx
  void *v83; // r8
  unsigned int *v84; // r9
  int v85; // eax
  int v86; // r10d
  int v87; // edx
  __int64 v88; // r13
  char *v89; // r11
  __int64 v90; // rcx
  __int64 v91; // rdx
  signed int LastError; // eax
  bool v93; // sf
  int **v94; // rbx
  HRGN v95; // rax
  void *v96; // r8
  void *v97; // rcx
  unsigned int *v98; // rdx
  __int64 v99; // r8
  int v100; // eax
  __int64 v101; // rax
  _DWORD *v102; // r9
  int *v103; // r10
  int v104; // edx
  int v105; // ebx
  __int64 v106; // rsi
  _DWORD *v107; // rdi
  __int64 v108; // rcx
  __int64 v109; // rdx
  int *v110; // rcx
  unsigned __int64 v111; // r8
  HRGN v112; // rax
  void *v113; // r8
  void *v114; // rcx
  void *v116; // rcx
  int nCount; // edx
  struct FastRegion::Internal::CRgnData **RgnOfRectAry; // rax
  __int64 v119; // rdx
  struct FastRegion::Internal::CRgnData **v120; // rsi
  struct FastRegion::Internal::CRgnData *v121; // rcx
  struct FastRegion::Internal::CRgnData *v122; // rax
  int v123; // r10d
  __int64 v124; // rbx
  _DWORD *v125; // r11
  __int64 v126; // rcx
  _DWORD *v127; // rcx
  unsigned __int64 v128; // r8
  __int64 v129; // r9
  FastRegion::Internal::CRgnData *v130; // rcx
  const struct FastRegion::Internal::CRgnData *v131; // rdx
  FastRegion::Internal::CRgnData *v132; // rax
  __m128 v133; // xmm8
  int v134; // edx
  __m128 v135; // xmm5
  __m128 v136; // xmm4
  __m128 v137; // xmm1
  __m128 v138; // xmm7
  __m128i v139; // xmm0
  __m128 v140; // xmm1
  __m128 v141; // xmm2
  __m128 v142; // xmm3
  int v143; // ecx
  __int64 v144; // r9
  __int64 v145; // rcx
  struct tagPOINT Points; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int64 v147; // [rsp+50h] [rbp-B8h] BYREF
  struct tagPOINT v148; // [rsp+58h] [rbp-B0h] BYREF
  const struct FastRegion::Internal::CRgnData *rect; // [rsp+60h] [rbp-A8h]
  RECT rect_8; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v151; // [rsp+78h] [rbp-90h]
  struct CRegion *v152; // [rsp+80h] [rbp-88h]
  HWND hWnd; // [rsp+88h] [rbp-80h]
  _DWORD *v154; // [rsp+90h] [rbp-78h]
  struct FastRegion::Internal::CRgnData *v155; // [rsp+98h] [rbp-70h]
  _DWORD v156[18]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v157[64]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v158[208]; // [rsp+128h] [rbp+20h] BYREF

  v5 = a5;
  v6 = this;
  LOBYTE(this) = *(_BYTE *)(this + 8);
  hWnd = a2;
  v8 = a2;
  v148 = (struct tagPOINT)a4;
  v9 = (const __m128i *)a3;
  v152 = a5;
  v10 = (_DWORD *)(v6 + 176);
  v154 = (_DWORD *)(v6 + 176);
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
      v151 = v19;
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
        v147 = 0;
      else
        v147 = (unsigned int)this * (unsigned __int64)(unsigned int)v23;
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
          v21 = (struct tagPOINT)(v147 + v29 - v51);
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
        v5 = v152;
        v19 = v151;
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
          v61 = v151;
          v62 = rect;
          while ( 1 )
          {
            LODWORD(v147) = -1;
            FindBestMerge(
              v6 + 48,
              this,
              v22,
              (_DWORD)v14 + 16 * v22,
              (__int64)&v147,
              (__int64)&rect_8,
              (__int64)&Points);
            this = *(_QWORD *)&rect_8.left;
            if ( *(_QWORD *)&rect_8.left > (unsigned __int64)v62
              || *(_QWORD *)&rect_8.left > v61 && *(_QWORD *)&rect_8.left > *(unsigned __int64 *)&Points / 0xA )
            {
              break;
            }
            v133 = (__m128)_mm_loadu_si128(&v14[v22]);
            v134 = v147;
            a3 = (unsigned int)v22;
            v135 = (__m128)_mm_loadu_si128(&v14[(int)v147]);
            v136 = _mm_xor_ps(v133, v135);
            v137 = (__m128)_mm_cmpgt_epi32(
                             (__m128i)_mm_unpackhi_pd((__m128d)v133, (__m128d)v135),
                             (__m128i)_mm_unpacklo_pd((__m128d)v133, (__m128d)v135));
            v138 = _mm_and_ps((__m128)_mm_cmpgt_epi32((__m128i)v133, (__m128i)v135), v136);
            v139 = (__m128i)_mm_and_ps((__m128)_mm_srli_si128((__m128i)v137, 4), v137);
            v140 = (__m128)_mm_shuffle_epi32(v139, 0);
            v141 = (__m128)_mm_shuffle_epi32(v139, 170);
            v142 = _mm_and_ps(_mm_xor_ps(_mm_and_ps(v140, v136), v135), _mm_or_ps(v141, v140));
            v14[(int)v147] = (__m128i)_mm_xor_ps(
                                        _mm_and_ps(
                                          _mm_xor_ps(
                                            (__m128)_mm_shuffle_pd(
                                                      (__m128d)_mm_xor_ps(v133, v138),
                                                      (__m128d)_mm_xor_ps(v138, v135),
                                                      2),
                                            v142),
                                          _mm_and_ps(v141, v140)),
                                        v142);
            v143 = *(_DWORD *)(v6 + 176);
            if ( v22 < v143 - 1 )
            {
              do
              {
                v145 = (int)a3;
                a3 = (unsigned int)(a3 + 1);
                v14[v145] = v14[v145 + 1];
                v143 = *(_DWORD *)(v6 + 176);
              }
              while ( (int)a3 < v143 - 1 );
            }
            this = (unsigned int)(v143 - 1);
            *(_DWORD *)(v6 + 176) = this;
            if ( v134 > v22 )
              --v134;
            if ( (int)this <= 1 )
              break;
            v22 = v134;
          }
          v5 = v152;
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
    a4 = (HDC *)v148;
LABEL_42:
    v10 = (_DWORD *)(v6 + 176);
    v8 = hWnd;
    LOBYTE(this) = *(_BYTE *)(v6 + 8) & 0xFE;
    goto LABEL_43;
  }
  v154 = (_DWORD *)(v6 + 176);
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
      v116 = (void *)*((_QWORD *)v5 + 9);
      if ( v116 )
      {
        DeleteObject(v116);
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
    v144 = 80;
    goto LABEL_189;
  }
LABEL_48:
  DCEx = GetDCEx(v8, 0, 0x12u);
  v151 = (unsigned __int64)DCEx;
  v65 = DCEx;
  if ( !DCEx )
  {
    if ( (Microsoft_IEEnableBits & 0x20) == 0 )
      return 0;
    v144 = 96;
LABEL_189:
    McTemplateU0xx_EventWriteTransfer(this, MSHTML_CPAINTCONTROLLER_CANNOTPAINTNOW, v6, v144);
    return 0;
  }
  *a4 = DCEx;
  if ( (byte_1815BFC73 & 0x10) != 0
    && !(unsigned __int8)IEConfiguration_GetBool(268435481)
    && (*(_BYTE *)(v6 + 8) & 0x20) == 0 )
  {
    rect_8 = g_Zero;
    rect = (const struct FastRegion::Internal::CRgnData *)CreateRectRgnIndirect(&rect_8);
    v66 = (HRGN)rect;
    if ( rect )
      goto LABEL_53;
    LastError = GetLastError();
    v93 = LastError < 0;
    if ( LastError > 0 )
      v93 = 1;
    if ( !v93 )
    {
LABEL_53:
      v67 = hWnd;
      Points = 0;
      v148 = 0;
      MapWindowPoints(hWnd, 0, &Points, 1u);
      RandomRgn = GetRandomRgn(v65, v66, 4);
      if ( !RandomRgn )
      {
        if ( (Microsoft_IEEnableBits & 0x20) == 0 )
          goto LABEL_123;
        v129 = 112;
        goto LABEL_185;
      }
      if ( RandomRgn < 0 )
        goto LABEL_89;
      if ( !OffsetRgn(v66, -Points.x, -Points.y) )
        goto LABEL_89;
      MapWindowPoints(v67, 0, &v148, 1u);
      if ( Points.x != v148.x || Points.y != v148.y )
        goto LABEL_89;
      CBufferedRegion::PublishRegion((CBufferedRegion *)(v6 + 48));
      v70 = (void **)(v6 + 184);
      if ( !*(_QWORD *)(v6 + 184) )
      {
LABEL_87:
        if ( *v154 || *(_QWORD *)v11 )
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
        v129 = 128;
LABEL_185:
        McTemplateU0xx_EventWriteTransfer(v69, MSHTML_CPAINTCONTROLLER_CANNOTPAINTNOW, v6, v129);
        goto LABEL_123;
      }
      v71 = *(void **)(v6 + 256);
      if ( v71 )
      {
        DeleteObject(v71);
        *(_QWORD *)(v6 + 256) = 0;
      }
      v155 = 0;
      RegionData = GetRegionData(v66, 0, 0);
      v74 = RegionData;
      if ( RegionData )
      {
        v75 = (struct _RGNDATA *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, RegionData, v73);
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
              v120 = RgnOfRectAry;
              if ( RgnOfRectAry )
              {
                v121 = v155;
                v122 = *RgnOfRectAry;
                if ( v155 == (struct FastRegion::Internal::CRgnData *)1 )
                {
                  if ( v122 == (struct FastRegion::Internal::CRgnData *)1 )
                  {
                    FastRegion::Internal::CRgnData::Copy(
                      (FastRegion::Internal::CRgnData *)v157,
                      (const struct FastRegion::Internal::CRgnData *)(v120 + 1));
                    FastRegion::Internal::CRgnData::Copy(
                      (FastRegion::Internal::CRgnData *)(v120 + 1),
                      (const struct FastRegion::Internal::CRgnData *)v156);
                    v131 = (const struct FastRegion::Internal::CRgnData *)v157;
                    v130 = (FastRegion::Internal::CRgnData *)v156;
                  }
                  else
                  {
                    v155 = v122;
                    v130 = (FastRegion::Internal::CRgnData *)(v120 + 1);
                    *v120 = (struct FastRegion::Internal::CRgnData *)1;
                    v131 = (const struct FastRegion::Internal::CRgnData *)v156;
                  }
                  FastRegion::Internal::CRgnData::Copy(v130, v131);
                }
                else if ( v122 == (struct FastRegion::Internal::CRgnData *)1 )
                {
                  *v120 = v155;
                  v155 = (struct FastRegion::Internal::CRgnData *)1;
                  v123 = 0;
                  v156[0] = *((_DWORD *)v120 + 2);
                  v156[1] = *((_DWORD *)v120 + 3);
                  v156[2] = *((_DWORD *)v120 + 4);
                  v124 = (__int64)v120 + *((int *)v120 + 6) + 20;
                  v125 = &v156[2 * v156[0] + 3];
                  if ( v156[0] > 0 )
                  {
                    do
                    {
                      v126 = v123++;
                      v156[2 * v126 + 3] = HIDWORD(v120[v126 + 2]);
                      v156[2 * v126 + 4] = (_DWORD)v120
                                         + 20
                                         + 8 * v126
                                         + (((_DWORD)v125 - v124) & 0xFFFFFFFC)
                                         + LODWORD(v120[v126 + 3])
                                         - (unsigned int)&v156[2 * v126 + 3];
                    }
                    while ( v123 < v156[0] );
                    v5 = v152;
                  }
                  v119 = 0;
                  v127 = (_DWORD *)&v120[*((int *)v120 + 2) + 1] + 1;
                  v128 = (unsigned __int64)((int)v127 + v127[1] - ((int)v120 + 20) - *((_DWORD *)v120 + 6)) >> 2;
                  if ( (int)v128 > 0 )
                  {
                    do
                    {
                      v125[v119] = *(_DWORD *)(v124 + 4 * v119);
                      v119 = (unsigned int)(v119 + 1);
                    }
                    while ( (int)v119 < (int)v128 );
                  }
                }
                else
                {
                  v155 = v122;
                  *v120 = v121;
                }
                CRegion2::`scalar deleting destructor'((CRegion2 *)v120, v119);
              }
              v66 = (HRGN)rect;
            }
            else
            {
              if ( (unsigned __int64)v155 > 1 )
                MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v155, v77);
              v155 = 0;
            }
          }
          MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v76, v77);
        }
      }
      if ( v155 )
      {
        v78 = (const struct FastRegion::Internal::CRgnData *)*v70;
        if ( !*v70 )
        {
LABEL_84:
          if ( (unsigned __int64)v155 > 1 )
            MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v155, (void *)v73);
          v65 = (HDC)v151;
          goto LABEL_87;
        }
        if ( *v70 == (void *)1 )
          v78 = (const struct FastRegion::Internal::CRgnData *)(v6 + 192);
        v79 = (struct FastRegion::Internal::CRgnData *)v156;
        if ( v155 != (struct FastRegion::Internal::CRgnData *)1 )
          v79 = v155;
        rect = v79;
        v80 = FastRegion::Internal::CRgnData::EstimateSizeIntersect(v78, v79);
        if ( v80 > 200 )
        {
          v82 = (FastRegion::Internal::CRgnData *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v80, v81);
          if ( !v82 )
            goto LABEL_84;
        }
        else
        {
          v82 = (FastRegion::Internal::CRgnData *)v158;
        }
        FastRegion::Internal::CRgnData::Intersect(v82, v78, rect);
        if ( (unsigned __int64)*v70 > 1 )
          MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, *v70, v83);
        v73 = *(unsigned int *)v82;
        if ( (_DWORD)v73 )
        {
          v84 = (unsigned int *)((char *)v82 + 12);
          v85 = *((_DWORD *)v82 + 2 * (int)v73 + 2) + 8 * v73 - *((_DWORD *)v82 + 4) - 12 + 8 * (v73 - 1) + 24;
          if ( v85 > 60 )
          {
            v69 = (unsigned int *)v158;
            if ( v82 == (FastRegion::Internal::CRgnData *)v158 )
            {
              v132 = (FastRegion::Internal::CRgnData *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v85, v73);
              *v70 = v132;
              if ( v132 )
                FastRegion::Internal::CRgnData::Copy(v132, v82);
            }
            else
            {
              *v70 = v82;
            }
          }
          else
          {
            *v70 = (void *)1;
            v86 = 0;
            v87 = *(_DWORD *)v82;
            *(_DWORD *)(v6 + 192) = *(_DWORD *)v82;
            *(_DWORD *)(v6 + 196) = *((_DWORD *)v82 + 1);
            *(_DWORD *)(v6 + 200) = *((_DWORD *)v82 + 2);
            v88 = (__int64)v82 + *((int *)v82 + 4) + 12;
            v89 = (char *)&v70[v87 + 1] + 4;
            if ( v87 > 0 )
            {
              do
              {
                v90 = v86++;
                HIDWORD(v70[v90 + 2]) = *((_DWORD *)v82 + 2 * v90 + 3);
                *(_DWORD *)(v6 + 204 + 8 * v90 + 4) = (_DWORD)v84
                                                    + 8 * v90
                                                    + (((_DWORD)v89 + 8 - v88) & 0xFFFFFFFC)
                                                    + v84[2 * v90 + 1]
                                                    - (v6
                                                     + 204
                                                     + 8 * v90);
              }
              while ( v86 < *(_DWORD *)(v6 + 192) );
              v5 = v152;
            }
            v91 = 0;
            v69 = (unsigned int *)((char *)v82 + 8 * *(int *)v82 + 4);
            v73 = (unsigned __int64)(int)((_DWORD)v69 + v69[1] - *((_DWORD *)v82 + 4) - (_DWORD)v84) >> 2;
            if ( (int)v73 > 0 )
            {
              do
              {
                *(_DWORD *)&v89[4 * v91 + 8] = *(_DWORD *)(v88 + 4 * v91);
                v91 = (unsigned int)(v91 + 1);
              }
              while ( (int)v91 < (int)v73 );
            }
            if ( v82 != (FastRegion::Internal::CRgnData *)v158 )
              MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v82, (void *)v73);
          }
          goto LABEL_84;
        }
        if ( v82 != (FastRegion::Internal::CRgnData *)v158 )
          MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v82, (void *)v73);
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
  v94 = (int **)(v6 + 184);
  v95 = *(HRGN *)(v6 + 256);
  if ( v95 || (v95 = CRegion2::ConvertToWindows((CRegion2 *)(v6 + 184)), (*(_QWORD *)(v6 + 256) = v95) != 0) )
  {
    SelectClipRgn(v65, v95);
    CBufferedRegion::PublishRegion((CBufferedRegion *)(v6 + 48));
    v97 = (void *)*((_QWORD *)v5 + 9);
    if ( v97 )
    {
      DeleteObject(v97);
      *((_QWORD *)v5 + 9) = 0;
    }
    if ( *(_QWORD *)v5 > 1u )
      MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, *(void **)v5, v96);
    v98 = (unsigned int *)*v94;
    if ( *v94 )
    {
      if ( *v94 == (int *)1 )
        v98 = (unsigned int *)(v6 + 192);
      v99 = *v98;
      v100 = v98[2 * (int)v99 + 2] - v98[4] + 8 * v99 - 12 + 8 * (v99 - 1) + 24;
      if ( v100 <= 60 )
      {
        *(_QWORD *)v5 = 1;
        goto LABEL_135;
      }
      v101 = MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v100, v99);
      *(_QWORD *)v5 = v101;
      v102 = (_DWORD *)v101;
      if ( v101 )
      {
        if ( v101 != 1 )
        {
LABEL_107:
          v103 = *v94;
          if ( *v94 == (int *)1 )
            v103 = (int *)(v6 + 192);
          v104 = *v103;
          *v102 = *v103;
          v105 = 0;
          v102[1] = v103[1];
          v102[2] = v103[2];
          v106 = (__int64)v103 + v103[4] + 12;
          v107 = &v102[2 * v104 + 3];
          if ( v104 > 0 )
          {
            do
            {
              v108 = v105++;
              v102[2 * v108 + 3] = v103[2 * v108 + 3];
              v102[2 * v108 + 4] = (_DWORD)v103
                                 + 8 * v108
                                 + 4 * (((__int64)v107 - v106) >> 2)
                                 + v103[2 * v108 + 4]
                                 - ((_DWORD)v102
                                  + 8 * v108);
            }
            while ( v105 < *v102 );
          }
          v109 = 0;
          v110 = &v103[2 * *v103 + 1];
          v111 = (unsigned __int64)((int)v110 + v110[1] - ((int)v103 + 12) - v103[4]) >> 2;
          if ( (int)v111 > 0 )
          {
            do
            {
              v107[v109] = *(_DWORD *)(v106 + 4 * v109);
              v109 = (unsigned int)(v109 + 1);
            }
            while ( (int)v109 < (int)v111 );
          }
          goto LABEL_113;
        }
LABEL_135:
        v102 = (_DWORD *)((char *)v5 + 8);
        goto LABEL_107;
      }
    }
    else
    {
      *(_QWORD *)v5 = 0;
    }
LABEL_113:
    v112 = (HRGN)*((_QWORD *)v5 + 9);
    if ( v112 || (v112 = CRegion2::ConvertToWindows(v5), (*((_QWORD *)v5 + 9) = v112) != 0) )
      ValidateRgn(hWnd, v112);
    *v154 = 0;
    v114 = *(void **)(v11 + 72);
    if ( v114 )
    {
      DeleteObject(v114);
      *(_QWORD *)(v11 + 72) = 0;
    }
    if ( *(_QWORD *)v11 > 1u )
      MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, *(void **)v11, v113);
    *(_QWORD *)v11 = 0;
    *(_BYTE *)(v6 + 8) &= ~1u;
    return 1;
  }
  if ( (Microsoft_IEEnableBits & 0x20) != 0 )
  {
    v144 = 144;
    goto LABEL_189;
  }
  return 0;
}

```

## disassembly

```asm
0x18031b6e0  mov     rax, rsp
0x18031b6e3  push    rbp
0x18031b6e4  push    rbx
0x18031b6e5  push    rsi
0x18031b6e6  push    rdi
0x18031b6e7  push    r12
0x18031b6e9  push    r13
0x18031b6eb  push    r14
0x18031b6ed  push    r15
0x18031b6ef  lea     rbp, [rax-178h]
0x18031b6f6  sub     rsp, 238h
0x18031b6fd  movaps  xmmword ptr [rax-58h], xmm6
0x18031b701  movaps  xmmword ptr [rax-68h], xmm7
0x18031b705  movaps  xmmword ptr [rax-78h], xmm8
0x18031b70a  mov     rax, cs:__security_cookie
0x18031b711  xor     rax, rsp
0x18031b714  mov     [rbp+170h+var_80], rax
0x18031b71b  mov     r15, [rbp+170h+arg_20]
0x18031b722  mov     r14, rcx
0x18031b725  mov     cl, [rcx+8]
0x18031b728  mov     rbx, r9
0x18031b72b  mov     [rbp+170h+hWnd], rdx
0x18031b72f  mov     r9, rdx
0x18031b732  mov     qword ptr [rsp+270h+var_220.x], rbx
0x18031b737  mov     rdi, r8
0x18031b73a  mov     [rsp+270h+var_1F8], r15
0x18031b73f  lea     rdx, [r14+0B0h]
0x18031b746  mov     [rbp+170h+var_1E8], rdx
0x18031b74a  lea     r12, [r14+0B8h]
0x18031b751  test    cl, 1
0x18031b754  jz      loc_18031C297
0x18031b75a  mov     dword ptr [rdx], 0
0x18031b760  mov     rcx, [r12+48h]; ho
0x18031b765  test    rcx, rcx
0x18031b768  jz      short loc_18031B77F
0x18031b76a  call    cs:__imp_DeleteObject
0x18031b771  nop     dword ptr [rax+rax+00h]
0x18031b776  mov     qword ptr [r12+48h], 0
0x18031b77f  cmp     qword ptr [r12], 1
0x18031b784  jbe     short loc_18031B796
0x18031b786  mov     rdx, [r12]; void *
0x18031b78a  mov     rcx, cs:g_hProcessHeap; this
0x18031b791  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x18031b796  mov     qword ptr [r12], 0
0x18031b79e  mov     ecx, [rdi+8]
0x18031b7a1  cmp     [rdi], ecx
0x18031b7a3  jge     loc_18031BBA9
0x18031b7a9  mov     eax, [rdi+0Ch]
0x18031b7ac  cmp     [rdi+4], eax
0x18031b7af  jge     loc_18031BBA9
0x18031b7b5  lea     rbx, [r14+30h]
0x18031b7b9  movsxd  r13, dword ptr [rbx+80h]
0x18031b7c0  test    r13d, r13d
0x18031b7c3  jz      loc_18031BB97
0x18031b7c9  movss   xmm0, dword ptr [rbx+0D8h]
0x18031b7d1  xor     edx, edx
0x18031b7d3  movss   xmm2, cs:__real@5f000000
0x18031b7db  movaps  xmm1, xmm0
0x18031b7de  mulss   xmm1, cs:__real@47435000
0x18031b7e6  mov     r8, 8000000000000000h
0x18031b7f0  comiss  xmm1, xmm2
0x18031b7f3  jb      short loc_18031B801
0x18031b7f5  subss   xmm1, xmm2
0x18031b7f9  comiss  xmm1, xmm2
0x18031b7fc  jnb     short loc_18031B801
0x18031b7fe  mov     rdx, r8
0x18031b801  mulss   xmm0, cs:__real@49095440
0x18031b809  cvttss2si r10, xmm1
0x18031b80e  add     r10, rdx
0x18031b811  xor     edx, edx
0x18031b813  comiss  xmm0, xmm2
0x18031b816  mov     [rsp+270h+var_200], r10
0x18031b81b  jb      short loc_18031B829
0x18031b81d  subss   xmm0, xmm2
0x18031b821  comiss  xmm0, xmm2
0x18031b824  jnb     short loc_18031B829
0x18031b826  mov     rdx, r8
0x18031b829  sub     ecx, [rdi]
0x18031b82b  xor     r9d, r9d
0x18031b82e  cvttss2si r8, xmm0
0x18031b833  or      esi, 0FFFFFFFFh
0x18031b836  mov     qword ptr [rsp+270h+Points.x], r9
0x18031b83b  add     r8, rdx
0x18031b83e  mov     qword ptr [rsp+270h+rect.left], r8
0x18031b843  xor     r8d, r8d
0x18031b846  mov     qword ptr [rsp+270h+rect.right], r8
0x18031b84b  test    ecx, ecx
0x18031b84d  jle     loc_18031C431
0x18031b853  sub     eax, [rdi+4]
0x18031b856  test    eax, eax
0x18031b858  jle     loc_18031C431
0x18031b85e  mov     edx, eax
0x18031b860  mov     eax, ecx
0x18031b862  imul    rdx, rax
0x18031b866  mov     [rsp+270h+var_228], rdx
0x18031b86b  xor     r11d, r11d
0x18031b86e  test    r13d, r13d
0x18031b871  jle     loc_18031BA62
0x18031b877  mov     r15, [rsp+270h+var_228]
0x18031b87c  mov     edx, r11d
0x18031b87f  add     rdx, rdx
0x18031b882  mov     r10d, [rbx+rdx*8+8]
0x18031b887  mov     eax, [rbx+rdx*8]
0x18031b88a  mov     r9d, [rbx+rdx*8+4]
0x18031b88f  mov     ecx, [rbx+rdx*8+0Ch]
0x18031b893  mov     dword ptr [rsp+270h+var_208], r10d
0x18031b898  sub     r10d, eax
0x18031b89b  mov     [rsp+270h+rect.right], eax
0x18031b89f  mov     [rsp+270h+rect.bottom], r9d
0x18031b8a4  mov     dword ptr [rsp+270h+var_208+4], ecx
0x18031b8a8  test    r10d, r10d
0x18031b8ab  jle     loc_18031C2A0
0x18031b8b1  sub     ecx, r9d
0x18031b8b4  test    ecx, ecx
0x18031b8b6  jle     loc_18031C2A0
0x18031b8bc  mov     r9d, ecx
0x18031b8bf  mov     eax, r10d
0x18031b8c2  imul    r9, rax
0x18031b8c6  movdqu  xmm6, xmmword ptr [rsp+270h+rect.right]
0x18031b8cc  movdqu  xmm8, xmmword ptr [rdi]
0x18031b8d1  movdqa  xmm5, xmm6
0x18031b8d5  movaps  xmm0, xmm8
0x18031b8d9  movaps  xmm1, xmm8
0x18031b8dd  unpcklpd xmm0, xmm6
0x18031b8e1  movdqa  xmm4, xmm8
0x18031b8e6  xorps   xmm4, xmm6
0x18031b8e9  unpckhpd xmm1, xmm6
0x18031b8ed  pcmpgtd xmm1, xmm0
0x18031b8f1  movdqa  xmm7, xmm8
0x18031b8f6  movdqa  xmm0, xmm1
0x18031b8fa  pcmpgtd xmm7, xmm6
0x18031b8fe  andps   xmm7, xmm4
0x18031b901  psrldq  xmm0, 4
0x18031b906  andps   xmm0, xmm1
0x18031b909  xorps   xmm5, xmm7
0x18031b90c  pshufd  xmm1, xmm0, 0
0x18031b911  pshufd  xmm2, xmm0, 0AAh
0x18031b916  movdqa  xmm3, xmm1
0x18031b91a  andps   xmm3, xmm4
0x18031b91d  movdqa  xmm0, xmm2
0x18031b921  orps    xmm0, xmm1
0x18031b924  movdqa  xmm4, xmm8
0x18031b929  xorps   xmm4, xmm7
0x18031b92c  xorps   xmm3, xmm6
0x18031b92f  andps   xmm3, xmm0
0x18031b932  shufpd  xmm4, xmm5, 2
0x18031b937  xorps   xmm4, xmm3
0x18031b93a  andps   xmm2, xmm1
0x18031b93d  andps   xmm4, xmm2
0x18031b940  xorps   xmm4, xmm3
0x18031b943  movdqa  xmm0, xmm4
0x18031b947  movd    eax, xmm4
0x18031b94b  psrldq  xmm0, 8
0x18031b950  movd    r10d, xmm0
0x18031b955  sub     r10d, eax
0x18031b958  test    r10d, r10d
0x18031b95b  jle     loc_18031C2A8
0x18031b961  movdqa  xmm0, xmm4
0x18031b965  psrldq  xmm4, 4
0x18031b96a  psrldq  xmm0, 0Ch
0x18031b96f  movd    ecx, xmm0
0x18031b973  movd    eax, xmm4
0x18031b977  sub     ecx, eax
0x18031b979  test    ecx, ecx
0x18031b97b  jle     loc_18031C2A8
0x18031b981  mov     eax, r10d
0x18031b984  imul    rcx, rax
0x18031b988  movups  xmm2, xmmword ptr [rbx+rdx*8]
0x18031b98c  movdqa  xmm1, xmm8
0x18031b991  pcmpgtd xmm1, xmm2
0x18031b995  movdqa  xmm3, xmm1
0x18031b999  movdqa  xmm0, xmm1
0x18031b99d  andps   xmm0, xmm2
0x18031b9a0  andnps  xmm3, xmm8
0x18031b9a4  orps    xmm3, xmm0
0x18031b9a7  xorps   xmm8, xmm2
0x18031b9ab  andps   xmm8, xmm1
0x18031b9af  movaps  xmm0, xmm3
0x18031b9b2  xorps   xmm8, xmm2
0x18031b9b6  movdqa  xmm1, xmm3
0x18031b9ba  unpcklpd xmm0, xmm8
0x18031b9bf  pcmpgtd xmm1, xmm0
0x18031b9c3  shufpd  xmm8, xmm3, 2
0x18031b9c9  pshufd  xmm0, xmm1, 0AAh
0x18031b9ce  pshufd  xmm2, xmm1, 0FFh
0x18031b9d3  andps   xmm2, xmm0
0x18031b9d6  andps   xmm2, xmm8
0x18031b9da  movdqa  xmm0, xmm2
0x18031b9de  movd    eax, xmm2
0x18031b9e2  psrldq  xmm0, 8
0x18031b9e7  movd    r10d, xmm0
0x18031b9ec  movdqu  xmmword ptr [rsp+270h+rect.right], xmm2
0x18031b9f2  sub     r10d, eax
0x18031b9f5  test    r10d, r10d
0x18031b9f8  jle     loc_18031C2AF
0x18031b9fe  movdqa  xmm0, xmm2
0x18031ba02  psrldq  xmm2, 4
0x18031ba07  psrldq  xmm0, 0Ch
0x18031ba0c  movd    edx, xmm0
0x18031ba10  movd    eax, xmm2
0x18031ba14  sub     edx, eax
0x18031ba16  test    edx, edx
0x18031ba18  jle     loc_18031C2AF
0x18031ba1e  mov     eax, r10d
0x18031ba21  imul    rdx, rax
0x18031ba25  sub     r9, rdx
0x18031ba28  add     r9, r15
0x18031ba2b  sub     rcx, r9
0x18031ba2e  cmp     esi, 0FFFFFFFFh
0x18031ba31  jnz     loc_18031BF5B
0x18031ba37  mov     qword ptr [rsp+270h+Points.x], r9
0x18031ba3c  mov     r8, rcx
0x18031ba3f  mov     esi, r11d
0x18031ba42  test    rcx, rcx
0x18031ba45  jz      short loc_18031BA53
0x18031ba47  inc     r11d
0x18031ba4a  cmp     r11d, r13d
0x18031ba4d  jl      loc_18031B87C
0x18031ba53  mov     r15, [rsp+270h+var_1F8]
0x18031ba58  mov     r10, [rsp+270h+var_200]
0x18031ba5d  mov     qword ptr [rsp+270h+rect.right], r8
0x18031ba62  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18031ba6c  cmp     r13d, 8
0x18031ba70  jnz     loc_18031C24B
0x18031ba76  movdqu  xmm8, xmmword ptr [rdi]
0x18031ba7b  movsxd  rax, esi
0x18031ba7e  add     rax, rax
0x18031ba81  movaps  xmm0, xmm8
0x18031ba85  movaps  xmm1, xmm8
0x18031ba89  movdqa  xmm4, xmm8
0x18031ba8e  movdqa  xmm7, xmm8
0x18031ba93  movdqu  xmm5, xmmword ptr [rbx+rax*8]
0x18031ba98  unpcklpd xmm0, xmm5
0x18031ba9c  xorps   xmm4, xmm5
0x18031ba9f  unpckhpd xmm1, xmm5
0x18031baa3  pcmpgtd xmm7, xmm5
0x18031baa7  pcmpgtd xmm1, xmm0
0x18031baab  andps   xmm7, xmm4
0x18031baae  xorps   xmm8, xmm7
0x18031bab2  movdqa  xmm0, xmm1
0x18031bab6  psrldq  xmm0, 4
0x18031babb  movdqa  xmm6, xmm7
0x18031babf  andps   xmm0, xmm1
0x18031bac2  xorps   xmm6, xmm5
0x18031bac5  pshufd  xmm1, xmm0, 0
0x18031baca  pshufd  xmm2, xmm0, 0AAh
0x18031bacf  movdqa  xmm3, xmm1
0x18031bad3  shufpd  xmm8, xmm6, 2
0x18031bad9  andps   xmm3, xmm4
0x18031badc  movdqa  xmm0, xmm2
0x18031bae0  xorps   xmm3, xmm5
0x18031bae3  orps    xmm0, xmm1
0x18031bae6  andps   xmm2, xmm1
0x18031bae9  andps   xmm3, xmm0
0x18031baec  xorps   xmm8, xmm3
0x18031baf0  andps   xmm8, xmm2
0x18031baf4  xorps   xmm8, xmm3
0x18031baf8  movdqu  xmmword ptr [rbx+rax*8], xmm8
0x18031bafe  mov     ecx, [rbx+80h]
0x18031bb04  cmp     ecx, 1
0x18031bb07  jle     loc_18031BBA4
0x18031bb0d  mov     rdi, [rsp+270h+var_200]
0x18031bb12  mov     r12, 0CCCCCCCCCCCCCCCDh
0x18031bb1c  mov     r15, qword ptr [rsp+270h+rect.left]
0x18031bb21  lea     rax, [rsp+270h+Points]
0x18031bb26  movsxd  r13, esi
0x18031bb29  mov     [rsp+270h+var_240], rax
0x18031bb2e  mov     edx, ecx
0x18031bb30  lea     rax, [rsp+270h+rect.right]
0x18031bb35  shl     r13, 4
0x18031bb39  mov     [rsp+270h+var_248], rax
0x18031bb3e  add     r13, rbx
0x18031bb41  lea     rax, [rsp+270h+var_228]
0x18031bb46  mov     dword ptr [rsp+270h+var_228], 0FFFFFFFFh
0x18031bb4e  mov     r9, r13
0x18031bb51  mov     [rsp+270h+var_250], rax
0x18031bb56  mov     r8d, esi
0x18031bb59  mov     rcx, rbx
0x18031bb5c  call    FindBestMerge
0x18031bb61  mov     rcx, qword ptr [rsp+270h+rect.right]
0x18031bb66  cmp     rcx, r15
0x18031bb69  ja      short loc_18031BB89
0x18031bb6b  cmp     rcx, rdi
0x18031bb6e  jbe     loc_18031C4C1
0x18031bb74  mov     rax, r12
0x18031bb77  mul     qword ptr [rsp+270h+Points.x]
0x18031bb7c  shr     rdx, 3
0x18031bb80  cmp     rcx, rdx
0x18031bb83  jbe     loc_18031C4C1
0x18031bb89  mov     r15, [rsp+270h+var_1F8]
0x18031bb8e  lea     r12, [r14+0B8h]
0x18031bb95  jmp     short loc_18031BBA4
0x18031bb97  movups  xmm0, xmmword ptr [rdi]
0x18031bb9a  movdqu  xmmword ptr [rbx], xmm0
0x18031bb9e  inc     dword ptr [rbx+80h]
0x18031bba4  mov     rbx, qword ptr [rsp+270h+var_220.x]
0x18031bba9  mov     cl, [r14+8]
0x18031bbad  lea     rdx, [r14+0B0h]
0x18031bbb4  mov     r9, [rbp+170h+hWnd]
0x18031bbb8  and     cl, 0FEh
  ... truncated ...
```
