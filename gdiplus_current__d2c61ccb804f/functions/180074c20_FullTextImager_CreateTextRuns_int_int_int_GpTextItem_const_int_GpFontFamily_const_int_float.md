# FullTextImager::CreateTextRuns(int,int,int,GpTextItem const &,int,GpFontFamily const *,int,float)

- ea: `0x180074c20`
- end: `0x180075a12`
- name: `?CreateTextRuns@FullTextImager@@AEAA?AW4Status@@HHHAEBVGpTextItem@@HPEBVGpFontFamily@@HM@Z`
- size: `3570`
- prototype: `enum Status __high(int, int, int, const struct GpTextItem *, int, const struct GpFontFamily *, int, float)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180074374`

## callees

- `0x180010bd0`
- `0x180012428`
- `0x180063cd8`
- `0x18006d8c8`
- `0x180074c20`
- `0x180076378`
- `0x180076860`
- `0x180081968`
- `0x1800845d4`
- `0x1800bef8c`
- `0x1800bfb84`
- `0x1800d85d4`
- `0x1800deacc`
- `0x180105d40`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074cf9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074d25`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074d4e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074d80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074f8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800750a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800750d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180075108`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007513d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180075329`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074cf9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074d25`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074d4e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074d80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074f8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800750a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800750d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180075108`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007513d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180075329`

## pseudocode

```c
__int64 __fastcall FullTextImager::CreateTextRuns(
        __int64 a1,
        unsigned int a2,
        int a3,
        signed int a4,
        __int64 *a5,
        int a6,
        GpFontFamily *a7,
        int a8,
        float a9)
{
  char v10; // bl
  int v11; // eax
  struct GpFontFace *v12; // r12
  unsigned int v13; // esi
  int v14; // eax
  unsigned __int64 v15; // rdi
  SIZE_T v16; // rax
  unsigned __int64 v17; // kr00_8
  unsigned __int16 *v18; // r13
  SIZE_T v19; // rax
  struct DWRITE_SHAPING_TEXT_PROPERTIES *v20; // rbx
  SIZE_T v21; // rax
  unsigned __int16 *v22; // r14
  SIZE_T v23; // rax
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v24; // rax
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v25; // rdi
  __int64 v26; // rax
  int v27; // ecx
  unsigned __int16 *v28; // rdx
  int GlyphsWithHotKeys; // r12d
  unsigned int v30; // edi
  unsigned int v31; // edx
  __int16 v32; // r8
  __int64 v33; // r12
  __int64 v34; // rdi
  signed int v35; // edx
  bool i; // cc
  _DWORD *v38; // rax
  _DWORD *v39; // r14
  _DWORD *v40; // r9
  __int64 *v41; // rax
  __int64 v42; // rcx
  struct GpFontFace *v43; // rax
  __int64 v44; // rcx
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v45; // rax
  unsigned int v46; // r13d
  __int64 v47; // rdx
  unsigned int v48; // edx
  unsigned int v49; // ebx
  SIZE_T v50; // rax
  unsigned __int64 v51; // rbx
  SIZE_T v52; // rax
  SIZE_T v53; // rax
  unsigned __int16 *v54; // r14
  SIZE_T v55; // rax
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v56; // r12
  struct DWRITE_SHAPING_TEXT_PROPERTIES *v57; // rbx
  FullTextImager *v58; // rcx
  struct GpFamilyFallback *FamilyFallback; // r10
  unsigned int UniformFallbackFace; // edi
  __int64 v61; // r8
  struct GpFontFace *v62; // rdi
  __int16 v63; // ax
  __int64 v64; // rdx
  __int64 v65; // rax
  int v66; // eax
  char *v67; // rax
  char *v68; // rbx
  __int64 v69; // rcx
  unsigned int v70; // eax
  struct DWRITE_SHAPING_TEXT_PROPERTIES *v71; // rax
  char *v72; // r9
  unsigned int v73; // ebx
  unsigned int v74; // r13d
  __int64 v75; // r9
  _BYTE *v76; // r8
  int v77; // r14d
  __int64 v78; // r9
  __int64 v79; // r11
  unsigned int v80; // eax
  struct GpFontFace *v81; // r10
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v82; // r11
  signed int v83; // r9d
  __int64 v84; // rdi
  __int64 v85; // rcx
  _BYTE *v86; // r8
  unsigned __int16 *v87; // rcx
  __int64 v88; // rax
  unsigned __int64 v89; // rdi
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  unsigned __int64 v96; // rbx
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rax
  signed int v103; // eax
  signed int v104; // eax
  const unsigned __int16 *v105; // [rsp+40h] [rbp-E8h]
  struct IDWriteNumberSubstitution *v106; // [rsp+48h] [rbp-E0h]
  struct DWRITE_TYPOGRAPHIC_FEATURES **v107; // [rsp+50h] [rbp-D8h]
  unsigned int *v108; // [rsp+58h] [rbp-D0h]
  unsigned int v109; // [rsp+60h] [rbp-C8h]
  unsigned __int16 v110; // [rsp+A8h] [rbp-80h] BYREF
  unsigned __int16 v111; // [rsp+AAh] [rbp-7Eh]
  unsigned int v112; // [rsp+ACh] [rbp-7Ch] BYREF
  unsigned int v113; // [rsp+B0h] [rbp-78h]
  int v114; // [rsp+B4h] [rbp-74h]
  signed int v115; // [rsp+B8h] [rbp-70h]
  unsigned int v116; // [rsp+BCh] [rbp-6Ch] BYREF
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v117; // [rsp+C0h] [rbp-68h] BYREF
  __int16 v118; // [rsp+C8h] [rbp-60h]
  int v119; // [rsp+CCh] [rbp-5Ch]
  int v120; // [rsp+D0h] [rbp-58h]
  unsigned int v121; // [rsp+D4h] [rbp-54h]
  __int64 v122; // [rsp+D8h] [rbp-50h] BYREF
  unsigned __int16 *v123; // [rsp+E0h] [rbp-48h] BYREF
  struct DWRITE_SHAPING_TEXT_PROPERTIES *v124; // [rsp+E8h] [rbp-40h]
  __int16 v125; // [rsp+F0h] [rbp-38h] BYREF
  __int64 v126; // [rsp+F8h] [rbp-30h]
  struct GpFontFace *Face; // [rsp+100h] [rbp-28h]
  __int64 *v128; // [rsp+108h] [rbp-20h]
  unsigned __int16 *v129; // [rsp+110h] [rbp-18h] BYREF
  unsigned int v130; // [rsp+118h] [rbp-10h]
  struct GpFontFace *j; // [rsp+120h] [rbp-8h]
  struct GpFontFace *v132; // [rsp+128h] [rbp+0h] BYREF
  GpFontFamily *v133; // [rsp+130h] [rbp+8h]
  int v134; // [rsp+138h] [rbp+10h] BYREF
  _BYTE *v135; // [rsp+140h] [rbp+18h]
  _BYTE v136[128]; // [rsp+148h] [rbp+20h] BYREF

  v128 = a5;
  v126 = a1;
  v10 = *((_BYTE *)a5 + 4);
  v11 = *((_BYTE *)a5 + 1) & 8;
  v121 = a2;
  v120 = v11;
  v114 = a3;
  v133 = a7;
  v130 = a8;
  Face = GpFontFamily::GetFace(a7, a8);
  v12 = Face;
  if ( !Face )
    return 1;
  v13 = 1;
  v119 = v10 & 1;
  while ( 1 )
  {
    if ( a4 <= 0 )
      return 0;
    v14 = 3 * a4 / 2 + 16;
    v115 = v14;
    if ( (unsigned int)v14 > 0xFFFF )
      return 2;
    v15 = v14;
    v17 = v14;
    v16 = 2LL * v14;
    if ( !is_mul_ok(v17, 2u) )
      v16 = -1;
    v18 = (unsigned __int16 *)HeapAlloc(GpRuntime::GpMemHeap, 0, v16);
    v129 = v18;
    v19 = 2LL * a4;
    if ( !is_mul_ok(a4, 2u) )
      v19 = -1;
    v20 = (struct DWRITE_SHAPING_TEXT_PROPERTIES *)HeapAlloc(GpRuntime::GpMemHeap, 0, v19);
    v21 = 2 * v15;
    if ( !is_mul_ok(v15, 2u) )
      v21 = -1;
    v22 = (unsigned __int16 *)HeapAlloc(GpRuntime::GpMemHeap, 0, v21);
    v123 = v22;
    v23 = 2 * v15;
    if ( !is_mul_ok(v15, 2u) )
      v23 = -1;
    v24 = (struct DWRITE_SHAPING_GLYPH_PROPERTIES *)HeapAlloc(GpRuntime::GpMemHeap, 0, v23);
    v112 = 0;
    v25 = v24;
    v117 = v24;
    if ( !v18 || !v20 || !v22 || !v24 )
    {
LABEL_91:
      v13 = 3;
LABEL_85:
      GpFree(v25);
      GpFree(v22);
      GpFree(v20);
LABEL_86:
      GpFree(v18);
      return v13;
    }
    v122 = 0;
    LOWORD(v122) = GdipScriptToDWriteScript((unsigned int)*(char *)v128);
    HIDWORD(v122) = 0;
    while ( 1 )
    {
      if ( *(_BYTE *)v128 == 44 )
      {
        v118 = 0;
        v109 = 0;
        v108 = 0;
        v107 = 0;
        v106 = 0;
        v105 = 0;
        v75 = *((_QWORD *)v12 + 1);
        v125 = 8203;
        if ( (*(int (__fastcall **)(struct IDWriteTextAnalyzer *, __int16 *, __int64, __int64, int, int, __int64 *))(*(_QWORD *)Globals::g_DWriteTextAnalyzer + 56LL))(
               Globals::g_DWriteTextAnalyzer,
               &v125,
               1,
               v75,
               v120,
               v119,
               &v122) < 0 )
          goto LABEL_85;
        v134 = 32;
        v76 = v136;
        v135 = v136;
        if ( a4 > 32 )
        {
          AutoBuffer<unsigned int,32>::SetSize(&v134, (unsigned int)a4);
          v76 = v135;
          if ( v134 < 0 || v134 > 32 && v135 == v136 )
          {
            if ( v135 != v136 )
              GpFree(v135);
            v134 = -1;
            v135 = v136;
            goto LABEL_91;
          }
        }
        v77 = v114;
        v78 = 0;
        v79 = v126;
        while ( 1 )
        {
          *(_DWORD *)&v76[4 * v78] = *(unsigned __int16 *)(*(_QWORD *)(v79 + 24) + 2LL * (v77 + (int)v78));
          v78 = (unsigned int)(v78 + 1);
          if ( (int)v78 >= a4 )
            break;
          v76 = v135;
        }
        v22 = v123;
        v80 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, unsigned __int16 *))(**((_QWORD **)v12 + 1) + 88LL))(
                *((_QWORD *)v12 + 1),
                v135,
                (unsigned int)a4,
                v123);
        v81 = Face;
        v82 = v117;
        v83 = 0;
        LODWORD(v124) = v80;
        v113 = v80 >> 31;
        v84 = v126;
        v85 = 0;
        do
        {
          v18[v85] = v83;
          *((_WORD *)v82 + v85) = 16;
          v86 = v135;
          *((_WORD *)v20 + v85) = 0;
          if ( (a6 & 0x20) == 0
            && ((unsigned int)(*(_DWORD *)&v86[4 * v85] - 8203) < 5 || *(_DWORD *)&v86[4 * v85] == 65279)
            || v22[v85] == *((_WORD *)v81 + 50)
            || *(_DWORD *)&v86[4 * v85] == 0xFFFF && (v88 = *(_QWORD *)(v84 + 184)) != 0 && *(_DWORD *)(v88 + 68) )
          {
            v22[v85] = *((_WORD *)v81 + 51);
            *((_WORD *)v82 + v85) = v118;
            v86 = v135;
          }
          ++v83;
          ++v85;
        }
        while ( v83 < a4 );
        v30 = v113;
        GlyphsWithHotKeys = (int)v124;
        v31 = a4;
        v112 = a4;
        if ( v86 != v136 )
        {
          GpFree(v86);
          v31 = v112;
        }
        v134 = -1;
        v135 = v136;
      }
      else
      {
        v26 = *(_QWORD *)(v126 + 184);
        v27 = v26 ? *(_DWORD *)(v26 + 68) : 0;
        v28 = (unsigned __int16 *)(*(_QWORD *)(v126 + 24) + 2LL * v114);
        if ( v27 )
        {
          GlyphsWithHotKeys = FullTextImager::GetGlyphsWithHotKeys(
                                (FullTextImager *)(unsigned int)v115,
                                v28,
                                a4,
                                v12,
                                v120,
                                v119,
                                (const struct DWRITE_SCRIPT_ANALYSIS *)&v122,
                                v105,
                                v106,
                                v107,
                                v108,
                                v109,
                                v115,
                                v18,
                                v20,
                                v22,
                                v25,
                                &v112);
          v30 = (unsigned int)GlyphsWithHotKeys >> 31;
        }
        else
        {
          v109 = 0;
          v108 = 0;
          v107 = 0;
          v106 = 0;
          v105 = 0;
          GlyphsWithHotKeys = (*(__int64 (__fastcall **)(struct IDWriteTextAnalyzer *, unsigned __int16 *, _QWORD, _QWORD, int, int, __int64 *))(*(_QWORD *)Globals::g_DWriteTextAnalyzer + 56LL))(
                                Globals::g_DWriteTextAnalyzer,
                                v28,
                                (unsigned int)a4,
                                *((_QWORD *)v12 + 1),
                                v120,
                                v119,
                                &v122);
          if ( GlyphsWithHotKeys >= 0 )
          {
            v31 = v112;
            goto LABEL_27;
          }
          v30 = 1;
        }
        v31 = v112;
      }
      if ( GlyphsWithHotKeys != -2147024774 )
        break;
      v103 = v115;
      if ( v115 >= 0x10000 )
        goto LABEL_115;
      v115 *= 2;
      v89 = 2 * v103;
      v90 = 2 * v89;
      if ( !is_mul_ok(v89, 2u) )
        v90 = -1;
      v91 = GpMallocEx(v90, 0);
      AutoArray<PointF>::operator=(&v129, v91);
      v92 = 2 * v89;
      if ( !is_mul_ok(v89, 2u) )
        v92 = -1;
      v93 = GpMallocEx(v92, 0);
      AutoArray<PointF>::operator=(&v123, v93);
      v94 = 2 * v89;
      if ( !is_mul_ok(v89, 2u) )
        v94 = -1;
      v95 = GpMallocEx(v94, 0);
      AutoArray<PointF>::operator=(&v117, v95);
      v18 = v129;
      v22 = v123;
      v25 = v117;
      if ( !v129 || !v123 || !v117 )
        goto LABEL_91;
      v12 = Face;
    }
    if ( GlyphsWithHotKeys < 0 )
    {
LABEL_115:
      v13 = v30;
      v25 = v117;
      goto LABEL_85;
    }
LABEL_27:
    v113 = a4;
    if ( (a6 & 0x400) == 0 && !*((_DWORD *)Face + 27) )
      break;
    LODWORD(v33) = v31;
LABEL_41:
    LODWORD(v34) = a4;
LABEL_45:
    v38 = HeapAlloc(GpRuntime::GpMemHeap, 0, 0x60u);
    v39 = v38;
    if ( !v38 )
    {
      v22 = v123;
      v25 = v117;
      goto LABEL_91;
    }
    *v38 = 0;
    v40 = v38;
    v38[1] = v114;
    v41 = v128;
    v39[2] = v34;
    v42 = *v41;
    v39[5] = a6;
    v43 = Face;
    *(_QWORD *)(v39 + 3) = v42;
    v44 = v126;
    *((_QWORD *)v39 + 4) = 0;
    *((_WORD *)v39 + 40) = 0;
    *(_QWORD *)(v39 + 21) = 0;
    *((_BYTE *)v39 + 92) = 0;
    *((_QWORD *)v39 + 3) = v43;
    *((_QWORD *)v39 + 6) = v123;
    v45 = v117;
    *((_QWORD *)v39 + 7) = v18;
    v46 = v121;
    v47 = v121;
    *((_QWORD *)v39 + 9) = v45;
    *((float *)v39 + 8) = a9;
    v39[10] = v33;
    *((_QWORD *)v39 + 8) = v20;
    v49 = SpanVector<lsrun *>::SetSpan(v44 + 440, v47, (unsigned int)v34, v40);
    if ( v49 )
    {
      lsrun::`scalar deleting destructor'((lsrun *)v39, v48);
      GpFree(0);
      GpFree(0);
      GpFree(0);
      GpFree(0);
      return v49;
    }
    v114 += v34;
    a4 -= v34;
    v121 = v34 + v46;
    if ( a4 > 0 )
      goto LABEL_51;
    v12 = Face;
LABEL_49:
    GpFree(0);
    GpFree(0);
    GpFree(0);
    GpFree(0);
  }
  v32 = *((_WORD *)Face + 50);
  v33 = 0;
  if ( !v31 )
    goto LABEL_41;
  do
  {
    if ( v22[v33] == v32 )
      break;
    v33 = (unsigned int)(v33 + 1);
  }
  while ( (unsigned int)v33 < v31 );
  if ( (unsigned int)v33 >= v31 )
    goto LABEL_41;
  v34 = 0;
  do
  {
    if ( v18[v34] >= (unsigned int)v33 )
      break;
    v34 = (unsigned int)(v34 + 1);
  }
  while ( (int)v34 < a4 );
  v35 = v34;
  for ( i = (int)v34 < a4; ; i = v35 < a4 )
  {
    v113 = v35;
    if ( !i )
      break;
    if ( v22[v18[v35]] != v32 )
      goto LABEL_43;
    ++v35;
  }
  if ( (_DWORD)v34 == a4 )
  {
LABEL_154:
    v34 = (unsigned int)(v34 - 1);
    LODWORD(v33) = v18[(int)v34];
    while ( (int)v34 > 0 )
    {
      if ( v18[v34 - 1] != (_DWORD)v33 )
        goto LABEL_45;
      v34 = (unsigned int)(v34 - 1);
    }
    goto LABEL_50;
  }
LABEL_43:
  if ( v18[(int)v34] > (unsigned int)v33 )
    goto LABEL_154;
  if ( (int)v34 > 0 )
    goto LABEL_45;
LABEL_50:
  GpFree(v22);
  GpFree(v18);
  GpFree(v117);
  GpFree(v20);
LABEL_51:
  v50 = 2LL * (unsigned int)a4;
  if ( !is_mul_ok((unsigned int)a4, 2u) )
    v50 = -1;
  v124 = (struct DWRITE_SHAPING_TEXT_PROPERTIES *)HeapAlloc(GpRuntime::GpMemHeap, 0, v50);
  GpFree(0);
  v51 = v115;
  v52 = 2LL * v115;
  if ( !is_mul_ok(v115, 2u) )
    v52 = -1;
  v18 = (unsigned __int16 *)HeapAlloc(GpRuntime::GpMemHeap, 0, v52);
  GpFree(0);
  v53 = 2 * v51;
  v129 = v18;
  if ( !is_mul_ok(v51, 2u) )
    v53 = -1;
  v54 = (unsigned __int16 *)HeapAlloc(GpRuntime::GpMemHeap, 0, v53);
  GpFree(0);
  v123 = v54;
  v55 = 2 * v51;
  if ( !is_mul_ok(v51, 2u) )
    v55 = -1;
  v56 = (struct DWRITE_SHAPING_GLYPH_PROPERTIES *)HeapAlloc(GpRuntime::GpMemHeap, 0, v55);
  GpFree(0);
  v57 = v124;
  v117 = v56;
  if ( !v18 || !v124 || !v54 || !v56 )
  {
    UniformFallbackFace = 3;
    goto LABEL_112;
  }
  j = 0;
  v132 = 0;
  v116 = 0;
  v111 = 0;
  v110 = 0;
  FamilyFallback = GpFontFamily::GetFamilyFallback(v133);
  if ( FamilyFallback )
  {
    v106 = (struct IDWriteNumberSubstitution *)((char *)&v110 + 1);
    v105 = &v110;
    UniformFallbackFace = GpFamilyFallback::GetUniformFallbackFace(
                            FamilyFallback,
                            *(_QWORD *)(v126 + 24) + 2LL * v114,
                            v113 - (unsigned int)v34,
                            v130,
                            *(char *)v128,
                            &v132,
                            &v116);
    if ( !UniformFallbackFace )
    {
      LOBYTE(v58) = HIBYTE(v110);
      v61 = v116;
      v62 = v132;
      v111 = v110;
      v113 = v116;
      goto LABEL_66;
    }
LABEL_112:
    GpFree(v56);
    GpFree(v54);
    GpFree(v57);
    v87 = v18;
  }
  else
  {
    v62 = j;
    v61 = (unsigned int)a4;
    v113 = a4;
LABEL_66:
    if ( (int)v61 <= 0 )
    {
      UniformFallbackFace = 1;
      goto LABEL_112;
    }
    if ( !v62 )
      v62 = Face;
    if ( v62 == Face )
    {
      v63 = 0;
    }
    else
    {
      v63 = GdipScriptToDWriteScript((unsigned int)*(char *)v128);
      v61 = v113;
    }
    v64 = 2LL * v114;
    LOWORD(v122) = v63;
    for ( j = (struct GpFontFace *)v64; ; v64 = (__int64)j )
    {
      v65 = *(_QWORD *)(v126 + 184);
      if ( v65 && *(_DWORD *)(v65 + 68) )
      {
        v66 = FullTextImager::GetGlyphsWithHotKeys(
                v58,
                (unsigned __int16 *)(*(_QWORD *)(v126 + 24) + v64),
                v61,
                v62,
                v120,
                v119,
                (const struct DWRITE_SCRIPT_ANALYSIS *)&v122,
                v105,
                v106,
                v107,
                v108,
                v109,
                v115,
                v18,
                v57,
                v54,
                v56,
                &v112);
        v116 = (unsigned int)v66 >> 31;
      }
      else
      {
        v109 = 0;
        v108 = 0;
        v107 = 0;
        v106 = 0;
        v105 = 0;
        v66 = (*(__int64 (__fastcall **)(struct IDWriteTextAnalyzer *, __int64, __int64, _QWORD, int, int, __int64 *))(*(_QWORD *)Globals::g_DWriteTextAnalyzer + 56LL))(
                Globals::g_DWriteTextAnalyzer,
                *(_QWORD *)(v126 + 24) + v64,
                v61,
                *((_QWORD *)v62 + 1),
                v120,
                v119,
                &v122);
        if ( v66 >= 0 )
          goto LABEL_78;
        v116 = 1;
      }
      if ( v66 != -2147024774 )
        break;
      v104 = v115;
      if ( v115 >= 0x10000 )
        goto LABEL_95;
      v115 *= 2;
      v96 = 2 * v104;
      v97 = 2 * v96;
      if ( !is_mul_ok(v96, 2u) )
        v97 = -1;
      v98 = GpMallocEx(v97, 0);
      AutoArray<PointF>::operator=(&v129, v98);
      v99 = 2 * v96;
      if ( !is_mul_ok(v96, 2u) )
        v99 = -1;
      v100 = GpMallocEx(v99, 0);
      AutoArray<PointF>::operator=(&v123, v100);
      v101 = 2 * v96;
      if ( !is_mul_ok(v96, 2u) )
        v101 = -1;
      v102 = GpMallocEx(v101, 0);
      AutoArray<PointF>::operator=(&v117, v102);
      v18 = v129;
      v54 = v123;
      v56 = v117;
      if ( !v129 || !v123 || !v117 )
        goto LABEL_96;
      v61 = v113;
      v57 = v124;
    }
    if ( v66 < 0 )
    {
LABEL_95:
      GpFree(v56);
      GpFree(v54);
      GpFree(v57);
      v13 = v116;
      goto LABEL_86;
    }
LABEL_78:
    v67 = (char *)HeapAlloc(GpRuntime::GpMemHeap, 0, 0x60u);
    v68 = v67;
    if ( !v67 )
    {
LABEL_96:
      GpFree(v56);
      GpFree(v54);
      GpFree(v124);
      v13 = 3;
      goto LABEL_86;
    }
    *(_DWORD *)v67 = 0;
    *((_DWORD *)v67 + 1) = v114;
    *((_DWORD *)v67 + 2) = v113;
    v69 = *v128;
    *((_DWORD *)v67 + 5) = a6;
    *(_QWORD *)(v67 + 12) = v69;
    *((_QWORD *)v67 + 4) = 0;
    *((_DWORD *)v67 + 10) = 0;
    *((_QWORD *)v67 + 6) = 0;
    *((_QWORD *)v67 + 7) = 0;
    *((_QWORD *)v67 + 8) = 0;
    *((_QWORD *)v67 + 9) = 0;
    *((_WORD *)v67 + 40) = 0;
    *(_QWORD *)(v67 + 84) = 0;
    v67[92] = 0;
    *((_QWORD *)v67 + 3) = v62;
    v70 = v112;
    *((_QWORD *)v68 + 9) = v56;
    v12 = Face;
    *((_DWORD *)v68 + 10) = v70;
    v71 = v124;
    *((_QWORD *)v68 + 6) = v54;
    *((_QWORD *)v68 + 7) = v18;
    *((_QWORD *)v68 + 8) = v71;
    if ( v62 != v12 )
      v68[92] = (32 * HIBYTE(v111)) | v111 & 0x1F;
    FullTextImager::GetFallbackFontSize((FullTextImager *)(v68 + 32), v12, a9, v62, (float *)v68 + 8, (float *)v68 + 9);
    v72 = v68;
    v73 = v113;
    v74 = v121;
    UniformFallbackFace = SpanVector<lsrun *>::SetSpan(v126 + 440, v121, v113, v72);
    if ( !UniformFallbackFace )
    {
      v114 += v73;
      v121 = v73 + v74;
      a4 -= v73;
      goto LABEL_49;
    }
    GpFree(0);
    GpFree(0);
    GpFree(0);
    v87 = 0;
  }
  GpFree(v87);
  return UniformFallbackFace;
}

```

## disassembly

```asm
0x180074c20  mov     rax, rsp
0x180074c23  push    rbp
0x180074c24  push    rbx
0x180074c25  push    rsi
0x180074c26  push    rdi
0x180074c27  push    r12
0x180074c29  push    r13
0x180074c2b  push    r14
0x180074c2d  push    r15
0x180074c2f  lea     rbp, [rax-108h]
0x180074c36  sub     rsp, 1E8h
0x180074c3d  movaps  xmmword ptr [rax-58h], xmm6
0x180074c41  mov     rax, cs:__security_cookie
0x180074c48  xor     rax, rsp
0x180074c4b  mov     [rbp+100h+var_60], rax
0x180074c52  mov     rax, [rbp+100h+arg_20]
0x180074c59  mov     r15d, r9d
0x180074c5c  mov     [rbp+100h+var_120], rax
0x180074c60  mov     [rbp+100h+var_130], rcx
0x180074c64  mov     rcx, [rbp+100h+arg_30]; this
0x180074c6b  movzx   ebx, byte ptr [rax+4]
0x180074c6f  movsx   eax, byte ptr [rax+1]
0x180074c73  and     eax, 8
0x180074c76  mov     [rbp+100h+var_154], edx
0x180074c79  mov     edx, [rbp+100h+arg_38]; int
0x180074c7f  mov     [rbp+100h+var_158], eax
0x180074c82  mov     [rbp+100h+var_174], r8d
0x180074c86  mov     [rbp+100h+var_F8], rcx
0x180074c8a  mov     [rbp+100h+var_110], edx
0x180074c8d  call    ?GetFace@GpFontFamily@@QEBAPEAVGpFontFace@@H@Z; GpFontFamily::GetFace(int)
0x180074c92  mov     [rbp+100h+var_128], rax
0x180074c96  mov     r12, rax
0x180074c99  test    rax, rax
0x180074c9c  jz      loc_180075946
0x180074ca2  movss   xmm6, [rbp+100h+arg_40]
0x180074caa  mov     esi, 1
0x180074caf  and     ebx, esi
0x180074cb1  mov     [rbp+100h+var_15C], ebx
0x180074cb4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180074cb8  lea     r14d, [rbx+3]
0x180074cbc  lea     ecx, [rbx+11h]
0x180074cbf  test    r15d, r15d
0x180074cc2  jle     loc_180074F27
0x180074cc8  lea     eax, [r15+r15*2]
0x180074ccc  cdq
0x180074ccd  idiv    r14d
0x180074cd0  add     eax, ecx
0x180074cd2  mov     dword ptr [rbp+100h+var_170], eax
0x180074cd5  cmp     eax, 0FFFFh
0x180074cda  ja      loc_18007555A
0x180074ce0  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180074ce7  movsxd  rdi, eax
0x180074cea  mov     eax, r14d
0x180074ced  mul     rdi
0x180074cf0  cmovb   rax, rbx
0x180074cf4  xor     edx, edx; dwFlags
0x180074cf6  mov     r8, rax; dwBytes
0x180074cf9  call    cs:__imp_HeapAlloc
0x180074d00  nop     dword ptr [rax+rax+00h]
0x180074d05  mov     r13, rax
0x180074d08  mov     [rbp+100h+var_118], rax
0x180074d0c  movsxd  rcx, r15d
0x180074d0f  mov     eax, r14d
0x180074d12  mul     rcx
0x180074d15  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180074d1c  cmovb   rax, rbx
0x180074d20  xor     edx, edx; dwFlags
0x180074d22  mov     r8, rax; dwBytes
0x180074d25  call    cs:__imp_HeapAlloc
0x180074d2c  nop     dword ptr [rax+rax+00h]
0x180074d31  mov     rbx, rax
0x180074d34  lea     rcx, [r14-3]
0x180074d38  mov     eax, r14d
0x180074d3b  mul     rdi
0x180074d3e  cmovb   rax, rcx
0x180074d42  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180074d49  mov     r8, rax; dwBytes
0x180074d4c  xor     edx, edx; dwFlags
0x180074d4e  call    cs:__imp_HeapAlloc
0x180074d55  nop     dword ptr [rax+rax+00h]
0x180074d5a  mov     r14, rax
0x180074d5d  mov     [rbp+100h+var_148], rax
0x180074d61  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180074d68  mov     eax, 2
0x180074d6d  mul     rdi
0x180074d70  cmovb   rax, rcx
0x180074d74  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180074d7b  mov     r8, rax; dwBytes
0x180074d7e  xor     edx, edx; dwFlags
0x180074d80  call    cs:__imp_HeapAlloc
0x180074d87  nop     dword ptr [rax+rax+00h]
0x180074d8c  mov     [rbp+100h+var_17C], 0
0x180074d93  mov     rdi, rax
0x180074d96  mov     [rbp+100h+var_168], rax
0x180074d9a  test    r13, r13
0x180074d9d  jz      loc_18007556A
0x180074da3  test    rbx, rbx
0x180074da6  jz      loc_18007556A
0x180074dac  test    r14, r14
0x180074daf  jz      loc_18007556A
0x180074db5  test    rax, rax
0x180074db8  jz      loc_18007556A
0x180074dbe  mov     rax, [rbp+100h+var_120]
0x180074dc2  mov     [rbp+100h+var_150], 0
0x180074dca  movsx   ecx, byte ptr [rax]
0x180074dcd  call    ?GdipScriptToDWriteScript@@YAGW4ItemScript@@@Z; GdipScriptToDWriteScript(ItemScript)
0x180074dd2  xor     r9d, r9d
0x180074dd5  mov     word ptr [rbp+100h+var_150], ax
0x180074dd9  mov     dword ptr [rbp+100h+var_150+4], r9d
0x180074ddd  mov     rax, [rbp+100h+var_120]
0x180074de1  cmp     byte ptr [rax], 2Ch ; ','
0x180074de4  jz      loc_180075422
0x180074dea  mov     r8, [rbp+100h+var_130]
0x180074dee  mov     rax, [r8+0B8h]
0x180074df5  test    rax, rax
0x180074df8  jz      loc_180075584
0x180074dfe  mov     ecx, [rax+44h]
0x180074e01  mov     rax, [r8+18h]
0x180074e05  mov     r8d, r15d; unsigned int
0x180074e08  movsxd  rdx, [rbp+100h+var_174]
0x180074e0c  lea     rdx, [rax+rdx*2]; unsigned __int16 *
0x180074e10  test    ecx, ecx
0x180074e12  jnz     loc_180075504
0x180074e18  mov     r10, cs:?g_DWriteTextAnalyzer@Globals@@3PEAUIDWriteTextAnalyzer@@EA; IDWriteTextAnalyzer * Globals::g_DWriteTextAnalyzer
0x180074e1f  mov     rcx, [r10]
0x180074e22  mov     rax, [rcx+38h]
0x180074e26  lea     rcx, [rbp+100h+var_17C]
0x180074e2a  mov     [rsp+88h], rcx
0x180074e32  mov     ecx, dword ptr [rbp+100h+var_170]
0x180074e35  mov     [rsp+220h+var_1A0], rdi
0x180074e3d  mov     [rsp+220h+var_1A8], r14
0x180074e42  mov     [rsp+220h+var_1B0], rbx
0x180074e47  mov     [rsp+220h+var_1B8], r13
0x180074e4c  mov     [rsp+220h+var_1C0], ecx
0x180074e50  lea     rcx, [rbp+100h+var_150]
0x180074e54  mov     [rsp+220h+var_1C8], r9d; unsigned int
0x180074e59  mov     [rsp+220h+var_1D0], r9; unsigned int *
0x180074e5e  mov     [rsp+220h+var_1D8], r9; struct DWRITE_TYPOGRAPHIC_FEATURES **
0x180074e63  mov     [rsp+220h+var_1E0], r9
0x180074e68  mov     [rsp+220h+var_1E8], r9
0x180074e6d  mov     r9, [r12+8]
0x180074e72  mov     [rsp+220h+var_1F0], rcx
0x180074e77  mov     ecx, [rbp+100h+var_15C]
0x180074e7a  mov     dword ptr [rsp+220h+var_1F8], ecx
0x180074e7e  mov     ecx, [rbp+100h+var_158]
0x180074e81  mov     dword ptr [rsp+220h+var_200], ecx
0x180074e85  mov     rcx, r10
0x180074e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074e8d  mov     r12d, eax
0x180074e90  test    eax, eax
0x180074e92  jns     loc_18007541A
0x180074e98  mov     edi, esi
0x180074e9a  mov     edx, [rbp+100h+var_17C]
0x180074e9d  cmp     r12d, 8007007Ah
0x180074ea4  jz      loc_18007599C
0x180074eaa  test    r12d, r12d
0x180074ead  js      loc_180075788
0x180074eb3  test    [rbp+100h+arg_28], 400h
0x180074ebd  mov     [rbp+100h+var_178], r15d
0x180074ec1  jnz     loc_180074F55
0x180074ec7  mov     rax, [rbp+100h+var_128]
0x180074ecb  cmp     dword ptr [rax+6Ch], 0
0x180074ecf  jnz     loc_180074F55
0x180074ed5  movzx   r8d, word ptr [rax+64h]
0x180074eda  xor     r12d, r12d
0x180074edd  test    edx, edx
0x180074edf  jz      short loc_180074F58
0x180074ee1  cmp     [r14+r12*2], r8w
0x180074ee6  jz      short loc_180074EF0
0x180074ee8  add     r12d, esi
0x180074eeb  cmp     r12d, edx
0x180074eee  jb      short loc_180074EE1
0x180074ef0  cmp     r12d, edx
0x180074ef3  jnb     short loc_180074F58
0x180074ef5  xor     edi, edi
0x180074ef7  movzx   ecx, word ptr [r13+rdi*2+0]
0x180074efd  cmp     ecx, r12d
0x180074f00  jb      loc_180075574
0x180074f06  mov     edx, edi
0x180074f08  cmp     edi, r15d
0x180074f0b  mov     [rbp+100h+var_178], edx
0x180074f0e  jge     short loc_180074F5D
0x180074f10  movsxd  rax, edx
0x180074f13  movzx   ecx, word ptr [r13+rax*2+0]
0x180074f19  cmp     [r14+rcx*2], r8w
0x180074f1e  jnz     short loc_180074F66
0x180074f20  add     edx, esi
0x180074f22  cmp     edx, r15d
0x180074f25  jmp     short loc_180074F0B
0x180074f27  xor     eax, eax
0x180074f29  mov     rcx, [rbp+100h+var_60]
0x180074f30  xor     rcx, rsp; StackCookie
0x180074f33  call    __security_check_cookie
0x180074f38  movaps  xmm6, [rsp+220h+var_58+8]
0x180074f40  add     rsp, 1E8h
0x180074f47  pop     r15
0x180074f49  pop     r14
0x180074f4b  pop     r13
0x180074f4d  pop     r12
0x180074f4f  pop     rdi
0x180074f50  pop     rsi
0x180074f51  pop     rbx
0x180074f52  pop     rbp
0x180074f53  retn
0x180074f55  mov     r12d, edx
0x180074f58  mov     edi, r15d
0x180074f5b  jmp     short loc_180074F80
0x180074f5d  cmp     edi, r15d
0x180074f60  jz      loc_1800759AF
0x180074f66  movsxd  rax, edi
0x180074f69  movzx   ecx, word ptr [r13+rax*2+0]
0x180074f6f  cmp     ecx, r12d
0x180074f72  ja      loc_1800759AF
0x180074f78  test    edi, edi
0x180074f7a  jle     loc_180075062
0x180074f80  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180074f87  xor     edx, edx; dwFlags
0x180074f89  lea     r8d, [rdx+60h]; dwBytes
0x180074f8d  call    cs:__imp_HeapAlloc
0x180074f94  nop     dword ptr [rax+rax+00h]
0x180074f99  xor     edx, edx
0x180074f9b  mov     r14, rax
0x180074f9e  test    rax, rax
0x180074fa1  jz      loc_180075562
0x180074fa7  mov     [rax], edx
0x180074fa9  mov     r9, r14
0x180074fac  mov     eax, [rbp+100h+var_174]
0x180074faf  mov     r8d, edi
0x180074fb2  mov     [r14+4], eax
0x180074fb6  mov     rax, [rbp+100h+var_120]
0x180074fba  mov     [r14+8], edi
0x180074fbe  mov     rcx, [rax]
0x180074fc1  mov     eax, [rbp+100h+arg_28]
0x180074fc7  mov     [r14+14h], eax
0x180074fcb  mov     rax, [rbp+100h+var_128]
0x180074fcf  mov     [r14+0Ch], rcx
0x180074fd3  mov     rcx, [rbp+100h+var_130]
0x180074fd7  mov     [r14+20h], rdx
0x180074fdb  add     rcx, 1B8h
0x180074fe2  mov     [r14+50h], dx
0x180074fe7  mov     [r14+54h], rdx
0x180074feb  mov     [r14+5Ch], dl
0x180074fef  mov     [r14+18h], rax
0x180074ff3  mov     rax, [rbp+100h+var_148]
0x180074ff7  mov     [r14+30h], rax
0x180074ffb  mov     rax, [rbp+100h+var_168]
0x180074fff  mov     [r14+38h], r13
0x180075003  mov     r13d, [rbp+100h+var_154]
0x180075007  mov     edx, r13d
0x18007500a  mov     [r14+48h], rax
0x18007500e  movss   dword ptr [r14+20h], xmm6
0x180075014  mov     [r14+28h], r12d
0x180075018  mov     [r14+40h], rbx
0x18007501c  call    ?SetSpan@?$SpanVector@PEAUlsrun@@@@QEAA?AW4Status@@HHPEAUlsrun@@@Z; SpanVector<lsrun *>::SetSpan(int,int,lsrun *)
0x180075021  mov     ebx, eax
0x180075023  test    eax, eax
0x180075025  jnz     loc_1800754D9
0x18007502b  add     [rbp+100h+var_174], edi
0x18007502e  add     r13d, edi
0x180075031  sub     r15d, edi
0x180075034  mov     [rbp+100h+var_154], r13d
0x180075038  test    r15d, r15d
0x18007503b  jg      short loc_180075083
0x18007503d  mov     r12, [rbp+100h+var_128]
0x180075041  xor     ecx, ecx
0x180075043  call    GpFree
0x180075048  xor     ecx, ecx
0x18007504a  call    GpFree
0x18007504f  xor     ecx, ecx
0x180075051  call    GpFree
0x180075056  xor     ecx, ecx
0x180075058  call    GpFree
0x18007505d  jmp     loc_180074CB4
0x180075062  mov     rcx, r14
0x180075065  call    GpFree
0x18007506a  mov     rcx, r13
0x18007506d  call    GpFree
0x180075072  mov     rcx, [rbp+100h+var_168]
0x180075076  call    GpFree
0x18007507b  mov     rcx, rbx
0x18007507e  call    GpFree
0x180075083  mov     r12d, 2
0x180075089  mov     ecx, r15d
0x18007508c  mov     eax, r12d
0x18007508f  mul     rcx
0x180075092  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180075099  lea     r14, [r12-3]
0x18007509e  cmovb   rax, r14
0x1800750a2  xor     edx, edx; dwFlags
0x1800750a4  mov     r8, rax; dwBytes
0x1800750a7  call    cs:__imp_HeapAlloc
0x1800750ae  nop     dword ptr [rax+rax+00h]
0x1800750b3  xor     ecx, ecx
0x1800750b5  mov     [rbp+100h+var_140], rax
0x1800750b9  call    GpFree
0x1800750be  movsxd  rbx, dword ptr [rbp+100h+var_170]
0x1800750c2  mov     eax, r12d
0x1800750c5  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800750cc  mul     rbx
0x1800750cf  cmovb   rax, r14
  ... truncated ...
```
