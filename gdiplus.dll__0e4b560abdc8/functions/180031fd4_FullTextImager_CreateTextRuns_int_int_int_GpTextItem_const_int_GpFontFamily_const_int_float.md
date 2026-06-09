# FullTextImager::CreateTextRuns(int,int,int,GpTextItem const &,int,GpFontFamily const *,int,float)

- ea: `0x180031fd4`
- end: `0x180032e36`
- name: `?CreateTextRuns@FullTextImager@@AEAA?AW4Status@@HHHAEBVGpTextItem@@HPEBVGpFontFamily@@HM@Z`
- size: `3682`
- prototype: `enum Status __high(int, int, int, const struct GpTextItem *, int, const struct GpFontFamily *, int, float)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x1800316a0`

## callees

- `0x18001f950`
- `0x18003078c`
- `0x180031fd4`
- `0x180032fc4`
- `0x1800350cc`
- `0x180037638`
- `0x18003e66c`
- `0x18009a8e8`
- `0x1800a9820`
- `0x1800b94bc`
- `0x1800bcfb0`
- `0x1800bf59c`
- `0x1800cab08`
- `0x1800e5044`
- `0x1800e9380`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800320b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800320eb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032115`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032147`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032398`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800323c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800323fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032436`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003249b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003297a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800320b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800320eb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032115`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032147`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032398`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800323c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800323fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032436`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003249b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003297a`

## pseudocode

```c
__int64 __fastcall FullTextImager::CreateTextRuns(
        FullTextImager *a1,
        unsigned int a2,
        int a3,
        signed int a4,
        _BYTE *a5,
        int a6,
        GpFontFamily *a7,
        int a8,
        float a9)
{
  int v9; // r15d
  unsigned int v10; // edi
  char v12; // al
  struct GpFontFace *v13; // r14
  signed int v14; // eax
  unsigned __int64 v15; // rbx
  SIZE_T v16; // rax
  unsigned __int16 *v17; // r12
  SIZE_T v18; // rax
  SIZE_T v19; // rax
  unsigned __int16 *v20; // r13
  SIZE_T v21; // rax
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v22; // rbx
  __int16 v24; // ax
  struct GpFontFace *v25; // r8
  int v26; // r15d
  FullTextImager *v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  unsigned int *v30; // r11
  int GlyphsWithHotKeys; // eax
  BOOL v32; // ebx
  unsigned int v33; // edx
  int v34; // r14d
  unsigned int v35; // r15d
  __int16 v36; // r9
  int v37; // r14d
  __int64 v38; // rdx
  int v39; // r8d
  __int64 v40; // rcx
  bool v41; // zf
  struct GpFontFace *v42; // r13
  SIZE_T v43; // rax
  unsigned __int64 v44; // rbx
  SIZE_T v45; // rax
  SIZE_T v46; // rax
  unsigned __int16 *v47; // r15
  SIZE_T v48; // rax
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v49; // rbx
  unsigned int UniformFallbackFace; // r14d
  _DWORD *v51; // rax
  _DWORD *v52; // rbx
  struct GpFontFace *v53; // r11
  _DWORD *v54; // r9
  _QWORD *v55; // rax
  FullTextImager *v56; // rcx
  struct DWRITE_SHAPING_TEXT_PROPERTIES *v57; // rax
  unsigned int v58; // r12d
  __int64 v59; // rdx
  unsigned int v60; // edx
  unsigned int v61; // r15d
  __int64 v62; // r9
  _BYTE *v63; // rdx
  __int64 v64; // r8
  FullTextImager *v65; // r11
  __int64 v66; // r9
  int v67; // ecx
  unsigned int v68; // eax
  signed __int64 v69; // r12
  char *v70; // r14
  struct GpFontFace *v71; // r11
  unsigned __int16 *v72; // rdx
  signed int v73; // r9d
  __int64 v74; // r8
  FullTextImager *v75; // rbx
  signed __int64 v76; // r15
  _WORD *v77; // rax
  _BYTE *v78; // rcx
  int v79; // r10d
  struct GpFamilyFallback *FamilyFallback; // rax
  int v81; // r14d
  FullTextImager *v82; // rcx
  __int64 v83; // r8
  __int64 v84; // r9
  unsigned int *v85; // r11
  int v86; // eax
  _DWORD *v87; // rax
  _DWORD *v88; // r8
  struct GpFontFace *v89; // r11
  __int64 *v90; // rax
  __int64 v91; // rcx
  unsigned int v92; // r12d
  __int64 v93; // r8
  unsigned int v94; // ebx
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rdx
  unsigned __int16 *v103; // r8
  unsigned int v104; // eax
  unsigned __int64 v105; // rbx
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  const unsigned __int16 *v112; // [rsp+40h] [rbp-E8h]
  struct IDWriteNumberSubstitution *v113; // [rsp+48h] [rbp-E0h]
  struct DWRITE_TYPOGRAPHIC_FEATURES **v114; // [rsp+50h] [rbp-D8h]
  unsigned int *v115; // [rsp+58h] [rbp-D0h]
  unsigned int v116; // [rsp+60h] [rbp-C8h]
  unsigned __int16 v117; // [rsp+A8h] [rbp-80h] BYREF
  unsigned __int16 v118; // [rsp+AAh] [rbp-7Eh]
  unsigned int v119; // [rsp+ACh] [rbp-7Ch] BYREF
  int v120; // [rsp+B0h] [rbp-78h]
  unsigned int v121; // [rsp+B4h] [rbp-74h]
  unsigned int v122; // [rsp+B8h] [rbp-70h] BYREF
  unsigned int v123; // [rsp+BCh] [rbp-6Ch]
  struct DWRITE_SHAPING_TEXT_PROPERTIES *v124; // [rsp+C0h] [rbp-68h]
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v125; // [rsp+C8h] [rbp-60h] BYREF
  unsigned __int16 v126; // [rsp+D0h] [rbp-58h]
  int v127; // [rsp+D4h] [rbp-54h]
  int v128; // [rsp+D8h] [rbp-50h]
  unsigned int v129; // [rsp+DCh] [rbp-4Ch]
  __int64 v130; // [rsp+E0h] [rbp-48h] BYREF
  struct DWRITE_SHAPING_TEXT_PROPERTIES *v131; // [rsp+E8h] [rbp-40h]
  __int16 v132; // [rsp+F0h] [rbp-38h] BYREF
  FullTextImager *v133; // [rsp+F8h] [rbp-30h]
  struct GpFontFace *Face; // [rsp+100h] [rbp-28h]
  unsigned __int16 *v135; // [rsp+108h] [rbp-20h] BYREF
  _BYTE *v136; // [rsp+110h] [rbp-18h]
  unsigned __int16 *v137; // [rsp+118h] [rbp-10h] BYREF
  struct GpFontFace *v138; // [rsp+120h] [rbp-8h] BYREF
  unsigned int v139; // [rsp+128h] [rbp+0h]
  __int64 v140; // [rsp+130h] [rbp+8h]
  unsigned __int16 *v141; // [rsp+138h] [rbp+10h]
  GpFontFamily *v142; // [rsp+140h] [rbp+18h]
  int v143; // [rsp+148h] [rbp+20h] BYREF
  _BYTE *v144; // [rsp+150h] [rbp+28h]
  _BYTE v145[128]; // [rsp+158h] [rbp+30h] BYREF

  v9 = a3;
  v133 = a1;
  v10 = 1;
  v136 = a5;
  v120 = a3;
  v12 = a5[1];
  v127 = a5[4] & 1;
  v123 = a2;
  v142 = a7;
  v139 = a8;
  v128 = v12 & 8;
  Face = GpFontFamily::GetFace(a7, a8);
  v13 = Face;
  if ( !Face )
    return v10;
  while ( 1 )
  {
    if ( a4 <= 0 )
      return 0;
    v14 = 3 * a4 / 2 + 16;
    v121 = v14;
    if ( (unsigned int)v14 > 0xFFFF )
      return 2;
    v15 = v14;
    v16 = 2LL * v14;
    if ( !is_mul_ok(v15, 2u) )
      v16 = -1;
    v17 = (unsigned __int16 *)HeapAlloc(GpRuntime::GpMemHeap, 0, v16);
    v141 = v17;
    v137 = v17;
    v18 = 2LL * a4;
    if ( !is_mul_ok(a4, 2u) )
      v18 = -1;
    v131 = (struct DWRITE_SHAPING_TEXT_PROPERTIES *)HeapAlloc(GpRuntime::GpMemHeap, 0, v18);
    v19 = 2 * v15;
    if ( !is_mul_ok(v15, 2u) )
      v19 = -1;
    v20 = (unsigned __int16 *)HeapAlloc(GpRuntime::GpMemHeap, 0, v19);
    v135 = v20;
    v21 = 2 * v15;
    if ( !is_mul_ok(v15, 2u) )
      v21 = -1;
    v22 = (struct DWRITE_SHAPING_GLYPH_PROPERTIES *)HeapAlloc(GpRuntime::GpMemHeap, 0, v21);
    v125 = v22;
    v119 = 0;
    if ( !v17 || !v131 || !v20 || !v22 )
    {
LABEL_13:
      v10 = 3;
      goto LABEL_14;
    }
    v130 = 0;
    v24 = GdipScriptToDWriteScript((unsigned int)(char)*v136);
    v25 = (struct GpFontFace *)v9;
    v26 = v121;
    HIDWORD(v130) = 0;
    v138 = v25;
    LOWORD(v130) = v24;
    while ( 1 )
    {
      if ( *v136 == 44 )
      {
        v62 = *((_QWORD *)v13 + 1);
        v132 = 8203;
        v116 = 0;
        v115 = 0;
        v114 = 0;
        v113 = 0;
        v112 = 0;
        v126 = 0;
        if ( (*(int (__fastcall **)(struct IDWriteTextAnalyzer *, __int16 *, __int64, __int64, int, int, __int64 *))(*(_QWORD *)Globals::g_DWriteTextAnalyzer + 56LL))(
               Globals::g_DWriteTextAnalyzer,
               &v132,
               1,
               v62,
               v128,
               v127,
               &v130) < 0 )
          goto LABEL_14;
        v143 = 32;
        v63 = v145;
        v144 = v145;
        if ( a4 > 32 )
        {
          AutoBuffer<unsigned int,32>::SetSize(&v143, (unsigned int)a4);
          v63 = v144;
          if ( v143 < 0 || v143 > 32 && v144 == v145 )
          {
            if ( v144 != v145 )
              GpFree(v144);
            v144 = v145;
            v143 = -1;
            goto LABEL_13;
          }
        }
        v64 = 0;
        v65 = v133;
        v66 = 2LL * (_QWORD)v138;
        do
        {
          v67 = *(unsigned __int16 *)(v66 + *((_QWORD *)v65 + 3));
          v66 += 2;
          *(_DWORD *)&v63[4 * v64++] = v67;
          v63 = v144;
        }
        while ( v64 < a4 );
        v68 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, unsigned __int16 *))(**((_QWORD **)v13 + 1) + 88LL))(
                *((_QWORD *)v13 + 1),
                v144,
                (unsigned int)a4,
                v20);
        v69 = (char *)v17 - (char *)v131;
        v70 = (char *)(v131 - (struct DWRITE_SHAPING_TEXT_PROPERTIES *)v20);
        v71 = Face;
        v72 = v20;
        v73 = 0;
        LODWORD(v124) = v68;
        v74 = 0;
        v129 = v68 >> 31;
        v75 = v133;
        v76 = v125 - (struct DWRITE_SHAPING_GLYPH_PROPERTIES *)v20;
        do
        {
          v77 = (unsigned __int16 *)((char *)v72 + (_QWORD)v70);
          *(_WORD *)((char *)v77 + v69) = v73;
          *(unsigned __int16 *)((char *)v72 + v76) = 16;
          v78 = v144;
          *v77 = 0;
          if ( (a6 & 0x20) == 0 && ((v79 = *(_DWORD *)&v78[v74], v79 == 65279) || (unsigned int)(v79 - 8203) < 5)
            || *v72 == *((_WORD *)v71 + 50)
            || *(_DWORD *)&v78[v74] == 0xFFFF && (v95 = *((_QWORD *)v75 + 23)) != 0 && *(_DWORD *)(v95 + 68) )
          {
            *v72 = *((_WORD *)v71 + 51);
            *(unsigned __int16 *)((char *)v72 + v76) = v126;
            v78 = v144;
          }
          ++v73;
          v74 += 4;
          ++v72;
        }
        while ( v73 < a4 );
        v17 = v141;
        v20 = v135;
        v33 = a4;
        v32 = v129;
        v34 = (int)v124;
        v119 = a4;
        if ( v78 != v145 )
        {
          GpFree(v78);
          v33 = v119;
        }
        v26 = v121;
        v144 = v145;
        v143 = -1;
      }
      else
      {
        if ( (unsigned int)FullTextImager::GetFormatHotkeyPrefix(v133, 0) )
        {
          GlyphsWithHotKeys = FullTextImager::GetGlyphsWithHotKeys(
                                v27,
                                (unsigned __int16 *)(*(_QWORD *)(v29 + 24) + 2 * v28),
                                a4,
                                v13,
                                v128,
                                v127,
                                (const struct DWRITE_SCRIPT_ANALYSIS *)&v130,
                                v112,
                                v113,
                                v114,
                                v115,
                                v116,
                                v26,
                                v17,
                                v131,
                                v20,
                                v22,
                                &v119);
          v32 = (unsigned int)GlyphsWithHotKeys >> 31;
        }
        else
        {
          v116 = (unsigned int)v30;
          v115 = v30;
          v114 = (struct DWRITE_TYPOGRAPHIC_FEATURES **)v30;
          v113 = (struct IDWriteNumberSubstitution *)v30;
          v112 = (const unsigned __int16 *)v30;
          GlyphsWithHotKeys = (*(__int64 (__fastcall **)(struct IDWriteTextAnalyzer *, __int64, _QWORD, _QWORD, int, int, __int64 *))(*(_QWORD *)Globals::g_DWriteTextAnalyzer + 56LL))(
                                Globals::g_DWriteTextAnalyzer,
                                *(_QWORD *)(v29 + 24) + 2 * v28,
                                (unsigned int)a4,
                                *((_QWORD *)v13 + 1),
                                v128,
                                v127,
                                &v130);
          v32 = GlyphsWithHotKeys < 0;
        }
        v33 = v119;
        v34 = GlyphsWithHotKeys;
      }
      if ( v34 != -2147024774 )
        break;
      if ( v26 >= 0x10000 )
        goto LABEL_109;
      v26 *= 2;
      v96 = 2LL * v26;
      v121 = v26;
      if ( !is_mul_ok(v26, 2u) )
        v96 = -1;
      v97 = GpMallocEx(v96, 0);
      AutoArray<PointF>::operator=(&v137, v97);
      v98 = 2LL * v26;
      if ( !is_mul_ok(v26, 2u) )
        v98 = -1;
      v99 = GpMallocEx(v98, 0);
      AutoArray<PointF>::operator=(&v135, v99);
      v100 = 2LL * v26;
      if ( !is_mul_ok(v26, 2u) )
        v100 = -1;
      v101 = GpMallocEx(v100, 0);
      AutoArray<PointF>::operator=(&v125, v101);
      v17 = v137;
      v20 = v135;
      v22 = v125;
      v141 = v137;
      if ( !v137 || !v135 || !v125 )
        goto LABEL_13;
      v13 = Face;
    }
    if ( v34 < 0 )
    {
LABEL_109:
      v10 = v32;
      v22 = v125;
LABEL_14:
      GpFree(v22);
      GpFree(v20);
      GpFree(v131);
LABEL_15:
      GpFree(v17);
      return v10;
    }
    v35 = 0;
    v129 = a4;
    v36 = *((_WORD *)Face + 50);
    if ( (a6 & 0x400) != 0 || *((_DWORD *)Face + 27) )
    {
      v35 = v33;
LABEL_52:
      v37 = a4;
      goto LABEL_53;
    }
    if ( !v33 )
      goto LABEL_52;
    do
    {
      if ( v20[v35] == v36 )
        break;
      ++v35;
    }
    while ( v35 < v33 );
    if ( v35 >= v33 )
      goto LABEL_52;
    v37 = 0;
    v38 = 0;
    do
    {
      if ( v17[v38] >= v35 )
        break;
      ++v37;
      ++v38;
    }
    while ( v38 < a4 );
    v129 = v37;
    v39 = v37;
    v40 = v38;
    v41 = v37 == a4;
    if ( v37 < a4 )
    {
      if ( v38 < a4 )
      {
        do
        {
          if ( v20[v17[v40]] != v36 )
            break;
          ++v39;
          ++v40;
        }
        while ( v40 < a4 );
        v129 = v39;
      }
      v41 = v37 == a4;
    }
    if ( v41 || v17[v38] > v35 )
    {
      v102 = v38 - 1;
      --v37;
      v35 = v17[v102];
      if ( v102 > 0 )
      {
        v103 = &v17[v102 - 1];
        do
        {
          if ( *v103 != v35 )
            break;
          --v37;
          --v102;
          --v103;
        }
        while ( v102 > 0 );
      }
    }
    if ( v37 <= 0 )
      break;
LABEL_53:
    v51 = HeapAlloc(GpRuntime::GpMemHeap, 0, 0x60u);
    v52 = v51;
    if ( !v51 )
    {
      v22 = v125;
      goto LABEL_13;
    }
    v53 = Face;
    v54 = v51;
    *v51 = 0;
    v51[1] = v120;
    v55 = v136;
    v52[2] = v37;
    *(_QWORD *)(v52 + 3) = *v55;
    v56 = v133;
    v52[5] = a6;
    v57 = v131;
    *((_QWORD *)v52 + 4) = 0;
    *((_WORD *)v52 + 40) = 0;
    *(_QWORD *)(v52 + 21) = 0;
    *((_BYTE *)v52 + 92) = 0;
    *((_QWORD *)v52 + 7) = v17;
    v58 = v123;
    v59 = v123;
    *((_QWORD *)v52 + 8) = v57;
    *((_QWORD *)v52 + 9) = v125;
    *((float *)v52 + 8) = a9;
    *((_QWORD *)v52 + 3) = v53;
    v52[10] = v35;
    *((_QWORD *)v52 + 6) = v20;
    v42 = 0;
    v61 = SpanVector<lsrun *>::SetSpan((char *)v56 + 440, v59, (unsigned int)v37, v54);
    if ( v61 )
    {
      lsrun::`scalar deleting destructor'((lsrun *)v52, v60);
      GpFree(0);
      GpFree(0);
      GpFree(0);
      GpFree(0);
      return v61;
    }
    v9 = v37 + v120;
    v123 = v37 + v58;
    a4 -= v37;
    v120 += v37;
    if ( a4 > 0 )
      goto LABEL_40;
LABEL_56:
    GpFree(0);
    GpFree(0);
    GpFree(0);
    GpFree(0);
    v13 = Face;
  }
  GpFree(v20);
  GpFree(v17);
  GpFree(v125);
  GpFree(v131);
  v42 = 0;
LABEL_40:
  v43 = 2LL * (unsigned int)a4;
  if ( !is_mul_ok((unsigned int)a4, 2u) )
    v43 = -1;
  v124 = (struct DWRITE_SHAPING_TEXT_PROPERTIES *)HeapAlloc(GpRuntime::GpMemHeap, 0, v43);
  GpFree(0);
  v44 = (int)v121;
  v45 = 2LL * (int)v121;
  if ( !is_mul_ok((int)v121, 2u) )
    v45 = -1;
  v17 = (unsigned __int16 *)HeapAlloc(GpRuntime::GpMemHeap, 0, v45);
  GpFree(0);
  v137 = v17;
  v46 = 2 * v44;
  if ( !is_mul_ok(v44, 2u) )
    v46 = -1;
  v47 = (unsigned __int16 *)HeapAlloc(GpRuntime::GpMemHeap, 0, v46);
  GpFree(0);
  v135 = v47;
  v48 = 2 * v44;
  if ( !is_mul_ok(v44, 2u) )
    v48 = -1;
  v49 = (struct DWRITE_SHAPING_GLYPH_PROPERTIES *)HeapAlloc(GpRuntime::GpMemHeap, 0, v48);
  GpFree(0);
  v125 = v49;
  if ( !v17 || !v124 || !v47 || !v49 )
  {
    UniformFallbackFace = 3;
    goto LABEL_50;
  }
  v138 = 0;
  v122 = 0;
  v118 = 0;
  v117 = 0;
  FamilyFallback = GpFontFamily::GetFamilyFallback(v142);
  if ( FamilyFallback )
  {
    v113 = (struct IDWriteNumberSubstitution *)((char *)&v117 + 1);
    v112 = &v117;
    UniformFallbackFace = GpFamilyFallback::GetUniformFallbackFace(
                            FamilyFallback,
                            *((_QWORD *)v133 + 3) + 2LL * v120,
                            v129 - v37,
                            v139,
                            (char)*v136,
                            &v138,
                            &v122);
    if ( !UniformFallbackFace )
    {
      v42 = v138;
      v81 = v122;
      v118 = v117;
      goto LABEL_79;
    }
LABEL_50:
    GpFree(v49);
    GpFree(v47);
    GpFree(v124);
    GpFree(v17);
    return UniformFallbackFace;
  }
  v81 = a4;
LABEL_79:
  if ( v81 <= 0 )
  {
    UniformFallbackFace = 1;
    goto LABEL_50;
  }
  if ( !v42 )
    v42 = Face;
  if ( v42 == Face )
    LOWORD(v130) = 0;
  else
    LOWORD(v130) = GdipScriptToDWriteScript((unsigned int)(char)*v136);
  v140 = v120;
  while ( 1 )
  {
    if ( (unsigned int)FullTextImager::GetFormatHotkeyPrefix(v133, 0) )
    {
      v86 = FullTextImager::GetGlyphsWithHotKeys(
              v82,
              (unsigned __int16 *)(*(_QWORD *)(v84 + 24) + 2 * v83),
              v81,
              v42,
              v128,
              v127,
              (const struct DWRITE_SCRIPT_ANALYSIS *)&v130,
              v112,
              v113,
              v114,
              v115,
              v116,
              v121,
              v17,
              v124,
              v47,
              v49,
              &v119);
      v122 = (unsigned int)v86 >> 31;
    }
    else
    {
      v116 = (unsigned int)v85;
      v115 = v85;
      v114 = (struct DWRITE_TYPOGRAPHIC_FEATURES **)v85;
      v113 = (struct IDWriteNumberSubstitution *)v85;
      v112 = (const unsigned __int16 *)v85;
      v86 = (*(__int64 (__fastcall **)(struct IDWriteTextAnalyzer *, __int64, _QWORD, _QWORD, int, int, __int64 *))(*(_QWORD *)Globals::g_DWriteTextAnalyzer + 56LL))(
              Globals::g_DWriteTextAnalyzer,
              *(_QWORD *)(v84 + 24) + 2 * v83,
              (unsigned int)v81,
              *((_QWORD *)v42 + 1),
              v128,
              v127,
              &v130);
      if ( v86 >= 0 )
        goto LABEL_90;
      v122 = 1;
    }
    if ( v86 != -2147024774 )
      break;
    v104 = v121;
    if ( (int)v121 >= 0x10000 )
      goto LABEL_105;
    v121 *= 2;
    v105 = (int)(2 * v104);
    v106 = 2 * v105;
    if ( !is_mul_ok(v105, 2u) )
      v106 = -1;
    v107 = GpMallocEx(v106, 0);
    AutoArray<PointF>::operator=(&v137, v107);
    v108 = 2 * v105;
    if ( !is_mul_ok(v105, 2u) )
      v108 = -1;
    v109 = GpMallocEx(v108, 0);
    AutoArray<PointF>::operator=(&v135, v109);
    v110 = 2 * v105;
    if ( !is_mul_ok(v105, 2u) )
      v110 = -1;
    v111 = GpMallocEx(v110, 0);
    AutoArray<PointF>::operator=(&v125, v111);
    v17 = v137;
    v47 = v135;
    v49 = v125;
    if ( !v137 || !v135 || !v125 )
      goto LABEL_104;
  }
  if ( v86 < 0 )
  {
LABEL_105:
    GpFree(v49);
    GpFree(v47);
    GpFree(v124);
    v10 = v122;
    goto LABEL_15;
  }
LABEL_90:
  v87 = HeapAlloc(GpRuntime::GpMemHeap, 0, 0x60u);
  v88 = v87;
  if ( !v87 )
  {
LABEL_104:
    GpFree(v49);
    GpFree(v47);
    GpFree(v124);
    v10 = 3;
    goto LABEL_15;
  }
  v89 = Face;
  *v87 = 0;
  v87[1] = v120;
  v90 = (__int64 *)v136;
  v88[2] = v81;
  v91 = *v90;
  v88[5] = a6;
  *(_QWORD *)(v88 + 3) = v91;
  *((_QWORD *)v88 + 4) = 0;
  v88[10] = 0;
  *((_QWORD *)v88 + 6) = 0;
  *((_QWORD *)v88 + 7) = 0;
  *((_QWORD *)v88 + 8) = 0;
  *((_QWORD *)v88 + 9) = 0;
  *((_WORD *)v88 + 40) = 0;
  *(_QWORD *)(v88 + 21) = 0;
  *((_BYTE *)v88 + 92) = 0;
  *((_QWORD *)v88 + 3) = v42;
  v88[10] = v119;
  *((_QWORD *)v88 + 8) = v124;
  *((_QWORD *)v88 + 6) = v47;
  *((_QWORD *)v88 + 7) = v17;
  *((_QWORD *)v88 + 9) = v49;
  if ( v42 != v89 )
    *((_BYTE *)v88 + 92) = (32 * HIBYTE(v118)) | v118 & 0x1F;
  FullTextImager::GetFallbackFontSize((FullTextImager *)(v88 + 8), v89, a9, v42, (float *)v88 + 8, (float *)v88 + 9);
  v92 = v123;
  v94 = SpanVector<lsrun *>::SetSpan((char *)v133 + 440, v123, (unsigned int)v81, v93);
  if ( !v94 )
  {
    v9 = v81 + v120;
    v123 = v81 + v92;
    v120 += v81;
    a4 -= v81;
    goto LABEL_56;
  }
  GpFree(0);
  GpFree(0);
  GpFree(0);
  GpFree(0);
  return v94;
}

```

## disassembly

```asm
0x180031fd4  mov     rax, rsp
0x180031fd7  push    rbp
0x180031fd8  push    rbx
0x180031fd9  push    rsi
0x180031fda  push    rdi
0x180031fdb  push    r12
0x180031fdd  push    r13
0x180031fdf  push    r14
0x180031fe1  push    r15
0x180031fe3  lea     rbp, [rax-118h]
0x180031fea  sub     rsp, 1F8h
0x180031ff1  movaps  xmmword ptr [rax-58h], xmm6
0x180031ff5  mov     rax, cs:__security_cookie
0x180031ffc  xor     rax, rsp
0x180031fff  mov     [rbp+110h+var_60], rax
0x180032006  mov     rax, [rbp+110h+arg_20]
0x18003200d  mov     r15d, r8d
0x180032010  mov     [rbp+110h+var_140], rcx
0x180032014  mov     edi, 1
0x180032019  mov     [rbp+110h+var_128], rax
0x18003201d  mov     esi, r9d
0x180032020  mov     [rbp+110h+var_188], r8d
0x180032024  movzx   ecx, byte ptr [rax+4]
0x180032028  mov     r8, [rbp+110h+arg_30]
0x18003202f  and     ecx, edi
0x180032031  movsx   eax, byte ptr [rax+1]
0x180032035  mov     [rbp+110h+var_164], ecx
0x180032038  and     eax, 8
0x18003203b  mov     [rbp+110h+var_17C], edx
0x18003203e  mov     rcx, r8; this
0x180032041  mov     edx, [rbp+110h+arg_38]; int
0x180032047  mov     [rbp+110h+var_F8], r8
0x18003204b  mov     [rbp+110h+var_110], edx
0x18003204e  mov     [rbp+110h+var_160], eax
0x180032051  call    ?GetFace@GpFontFamily@@QEBAPEAVGpFontFace@@H@Z; GpFontFamily::GetFace(int)
0x180032056  mov     [rbp+110h+var_138], rax
0x18003205a  mov     r14, rax
0x18003205d  test    rax, rax
0x180032060  jz      loc_18003218A
0x180032066  movss   xmm6, [rbp+110h+arg_40]
0x18003206e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180032072  lea     r9d, [r8+11h]
0x180032076  lea     ecx, [r8+3]
0x18003207a  test    esi, esi
0x18003207c  jle     loc_18003257A
0x180032082  lea     eax, [rsi+rsi*2]
0x180032085  cdq
0x180032086  idiv    ecx
0x180032088  add     eax, r9d
0x18003208b  mov     [rbp+110h+var_184], eax
0x18003208e  cmp     eax, 0FFFFh
0x180032093  ja      loc_180032AAA
0x180032099  movsxd  rbx, eax
0x18003209c  mov     eax, ecx
0x18003209e  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800320a5  mul     rbx
0x1800320a8  cmovo   rax, r8
0x1800320ac  xor     edx, edx; dwFlags
0x1800320ae  mov     r8, rax; dwBytes
0x1800320b1  call    cs:__imp_HeapAlloc
0x1800320b8  nop     dword ptr [rax+rax+00h]
0x1800320bd  mov     r13d, 2
0x1800320c3  movsxd  rcx, esi
0x1800320c6  mov     r12, rax
0x1800320c9  mov     [rbp+110h+var_100], rax
0x1800320cd  mov     [rbp+110h+var_120], rax
0x1800320d1  mov     eax, r13d
0x1800320d4  mul     rcx
0x1800320d7  lea     rcx, [r13-3]
0x1800320db  cmovo   rax, rcx
0x1800320df  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800320e6  mov     r8, rax; dwBytes
0x1800320e9  xor     edx, edx; dwFlags
0x1800320eb  call    cs:__imp_HeapAlloc
0x1800320f2  nop     dword ptr [rax+rax+00h]
0x1800320f7  mov     [rbp+110h+var_150], rax
0x1800320fb  lea     rcx, [r13-3]
0x1800320ff  mov     eax, r13d
0x180032102  mul     rbx
0x180032105  cmovo   rax, rcx
0x180032109  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180032110  mov     r8, rax; dwBytes
0x180032113  xor     edx, edx; dwFlags
0x180032115  call    cs:__imp_HeapAlloc
0x18003211c  nop     dword ptr [rax+rax+00h]
0x180032121  mov     r13, rax
0x180032124  mov     [rbp+110h+var_130], rax
0x180032128  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003212f  mov     eax, 2
0x180032134  mul     rbx
0x180032137  cmovo   rax, rcx
0x18003213b  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180032142  mov     r8, rax; dwBytes
0x180032145  xor     edx, edx; dwFlags
0x180032147  call    cs:__imp_HeapAlloc
0x18003214e  nop     dword ptr [rax+rax+00h]
0x180032153  mov     rbx, rax
0x180032156  mov     [rbp+110h+var_170], rax
0x18003215a  xor     eax, eax
0x18003215c  mov     [rbp+110h+var_18C], eax
0x18003215f  test    r12, r12
0x180032162  jnz     short loc_1800321B8
0x180032164  mov     edi, 3
0x180032169  mov     rcx, rbx
0x18003216c  call    GpFree
0x180032171  mov     rcx, r13
0x180032174  call    GpFree
0x180032179  mov     rcx, [rbp+110h+var_150]
0x18003217d  call    GpFree
0x180032182  mov     rcx, r12
0x180032185  call    GpFree
0x18003218a  mov     eax, edi
0x18003218c  mov     rcx, [rbp+110h+var_60]
0x180032193  xor     rcx, rsp; StackCookie
0x180032196  call    __security_check_cookie
0x18003219b  movaps  xmm6, [rsp+230h+var_58+8]
0x1800321a3  add     rsp, 1F8h
0x1800321aa  pop     r15
0x1800321ac  pop     r14
0x1800321ae  pop     r13
0x1800321b0  pop     r12
0x1800321b2  pop     rdi
0x1800321b3  pop     rsi
0x1800321b4  pop     rbx
0x1800321b5  pop     rbp
0x1800321b6  retn
0x1800321b8  cmp     [rbp+110h+var_150], rax
0x1800321bc  jz      short loc_180032164
0x1800321be  test    r13, r13
0x1800321c1  jz      short loc_180032164
0x1800321c3  test    rbx, rbx
0x1800321c6  jz      short loc_180032164
0x1800321c8  mov     [rbp+110h+var_158], rax
0x1800321cc  mov     rax, [rbp+110h+var_128]
0x1800321d0  movsx   ecx, byte ptr [rax]
0x1800321d3  call    ?GdipScriptToDWriteScript@@YAGW4ItemScript@@@Z; GdipScriptToDWriteScript(ItemScript)
0x1800321d8  movsxd  r8, r15d
0x1800321db  xor     r11d, r11d
0x1800321de  mov     r15d, [rbp+110h+var_184]
0x1800321e2  mov     dword ptr [rbp+110h+var_158+4], r11d
0x1800321e6  mov     [rbp+110h+var_118], r8
0x1800321ea  mov     word ptr [rbp+110h+var_158], ax
0x1800321ee  mov     rax, [rbp+110h+var_128]
0x1800321f2  cmp     byte ptr [rax], 2Ch ; ','
0x1800321f5  jz      loc_180032581
0x1800321fb  mov     r9, [rbp+110h+var_140]
0x1800321ff  xor     edx, edx; struct GpStringFormat *
0x180032201  mov     rcx, r9; this
0x180032204  call    ?GetFormatHotkeyPrefix@FullTextImager@@AEAAHPEBVGpStringFormat@@@Z; FullTextImager::GetFormatHotkeyPrefix(GpStringFormat const *)
0x180032209  test    eax, eax
0x18003220b  jnz     loc_180032762
0x180032211  mov     rcx, cs:?g_DWriteTextAnalyzer@Globals@@3PEAUIDWriteTextAnalyzer@@EA; IDWriteTextAnalyzer * Globals::g_DWriteTextAnalyzer
0x180032218  mov     rax, [rcx]
0x18003221b  mov     r10, [rax+38h]
0x18003221f  mov     rax, [r9+18h]
0x180032223  mov     r9, [r14+8]
0x180032227  lea     rdx, [rax+r8*2]
0x18003222b  mov     r8d, esi
0x18003222e  lea     rax, [rbp+110h+var_18C]
0x180032232  mov     [rsp+88h], rax
0x18003223a  mov     rax, [rbp+110h+var_150]
0x18003223e  mov     [rsp+230h+var_1B0], rbx
0x180032246  mov     [rsp+230h+var_1B8], r13
0x18003224b  mov     [rsp+230h+var_1C0], rax
0x180032250  lea     rax, [rbp+110h+var_158]
0x180032254  mov     [rsp+230h+var_1C8], r12
0x180032259  mov     [rsp+230h+var_1D0], r15d
0x18003225e  mov     [rsp+230h+var_1D8], r11d; unsigned int
0x180032263  mov     [rsp+230h+var_1E0], r11; unsigned int *
0x180032268  mov     [rsp+230h+var_1E8], r11; struct DWRITE_TYPOGRAPHIC_FEATURES **
0x18003226d  mov     [rsp+230h+var_1F0], r11
0x180032272  mov     [rsp+230h+var_1F8], r11
0x180032277  mov     [rsp+230h+var_200], rax
0x18003227c  mov     eax, [rbp+110h+var_164]
0x18003227f  mov     dword ptr [rsp+230h+var_208], eax
0x180032283  mov     eax, [rbp+110h+var_160]
0x180032286  mov     dword ptr [rsp+230h+var_210], eax
0x18003228a  mov     rax, r10
0x18003228d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032292  xor     r11d, r11d
0x180032295  test    eax, eax
0x180032297  mov     ebx, r11d
0x18003229a  sets    bl
0x18003229d  mov     edx, [rbp+110h+var_18C]
0x1800322a0  mov     r14d, eax
0x1800322a3  cmp     r14d, 8007007Ah
0x1800322aa  jz      loc_180032C4E
0x1800322b0  test    r14d, r14d
0x1800322b3  js      loc_180032BA8
0x1800322b9  test    [rbp+110h+arg_28], 400h
0x1800322c3  mov     r15d, r11d
0x1800322c6  mov     rax, [rbp+110h+var_138]
0x1800322ca  mov     [rbp+110h+var_15C], esi
0x1800322cd  movzx   r9d, word ptr [rax+64h]
0x1800322d2  jnz     loc_180032488
0x1800322d8  cmp     [rax+6Ch], r11d
0x1800322dc  jnz     loc_180032488
0x1800322e2  test    edx, edx
0x1800322e4  jz      loc_18003248B
0x1800322ea  mov     eax, r15d
0x1800322ed  cmp     [r13+rax*2+0], r9w
0x1800322f3  jz      short loc_1800322FD
0x1800322f5  add     r15d, edi
0x1800322f8  cmp     r15d, edx
0x1800322fb  jb      short loc_1800322EA
0x1800322fd  cmp     r15d, edx
0x180032300  jnb     loc_18003248B
0x180032306  movsxd  r10, esi
0x180032309  mov     r14d, r11d
0x18003230c  mov     rdx, r11
0x18003230f  test    esi, esi
0x180032311  jle     short loc_180032321
0x180032313  movzx   eax, word ptr [r12+rdx*2]
0x180032318  cmp     eax, r15d
0x18003231b  jb      loc_180032AB1
0x180032321  mov     [rbp+110h+var_15C], r14d
0x180032325  mov     r8d, r14d
0x180032328  mov     rcx, rdx
0x18003232b  cmp     r14d, esi
0x18003232e  jl      loc_180032AC5
0x180032334  jz      loc_180032D0A
0x18003233a  movzx   eax, word ptr [r12+rdx*2]
0x18003233f  cmp     eax, r15d
0x180032342  ja      loc_180032D0A
0x180032348  test    r14d, r14d
0x18003234b  jg      loc_18003248E
0x180032351  mov     rcx, r13
0x180032354  call    GpFree
0x180032359  mov     rcx, r12
0x18003235c  call    GpFree
0x180032361  mov     rcx, [rbp+110h+var_170]
0x180032365  call    GpFree
0x18003236a  mov     rcx, [rbp+110h+var_150]
0x18003236e  call    GpFree
0x180032373  xor     r13d, r13d
0x180032376  mov     r15d, 2
0x18003237c  mov     ecx, esi
0x18003237e  mov     eax, r15d
0x180032381  mul     rcx
0x180032384  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18003238b  lea     r12, [r15-3]
0x18003238f  cmovo   rax, r12
0x180032393  xor     edx, edx; dwFlags
0x180032395  mov     r8, rax; dwBytes
0x180032398  call    cs:__imp_HeapAlloc
0x18003239f  nop     dword ptr [rax+rax+00h]
0x1800323a4  xor     ecx, ecx
0x1800323a6  mov     [rbp+110h+var_178], rax
0x1800323aa  call    GpFree
0x1800323af  movsxd  rbx, [rbp+110h+var_184]
0x1800323b3  mov     eax, r15d
0x1800323b6  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800323bd  mul     rbx
0x1800323c0  cmovo   rax, r12
0x1800323c4  xor     edx, edx; dwFlags
0x1800323c6  mov     r8, rax; dwBytes
0x1800323c9  call    cs:__imp_HeapAlloc
0x1800323d0  nop     dword ptr [rax+rax+00h]
0x1800323d5  xor     ecx, ecx
0x1800323d7  mov     r12, rax
0x1800323da  call    GpFree
0x1800323df  lea     rcx, [r15-3]
0x1800323e3  mov     [rbp+110h+var_120], r12
0x1800323e7  mov     eax, r15d
0x1800323ea  mul     rbx
0x1800323ed  cmovo   rax, rcx
0x1800323f1  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800323f8  mov     r8, rax; dwBytes
0x1800323fb  xor     edx, edx; dwFlags
0x1800323fd  call    cs:__imp_HeapAlloc
0x180032404  nop     dword ptr [rax+rax+00h]
0x180032409  xor     ecx, ecx
0x18003240b  mov     r15, rax
0x18003240e  call    GpFree
0x180032413  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003241a  mov     [rbp+110h+var_130], r15
0x18003241e  mov     eax, 2
0x180032423  mul     rbx
0x180032426  cmovo   rax, rcx
0x18003242a  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180032431  mov     r8, rax; dwBytes
0x180032434  xor     edx, edx; dwFlags
0x180032436  call    cs:__imp_HeapAlloc
0x18003243d  nop     dword ptr [rax+rax+00h]
0x180032442  xor     ecx, ecx
0x180032444  mov     rbx, rax
0x180032447  call    GpFree
0x18003244c  mov     [rbp+110h+var_170], rbx
0x180032450  test    r12, r12
0x180032453  jnz     loc_1800327C5
0x180032459  mov     r14d, 3
0x18003245f  mov     rcx, rbx
0x180032462  call    GpFree
0x180032467  mov     rcx, r15
0x18003246a  call    GpFree
0x18003246f  mov     rcx, [rbp+110h+var_178]
0x180032473  call    GpFree
0x180032478  mov     rcx, r12
0x18003247b  call    GpFree
0x180032480  mov     eax, r14d
  ... truncated ...
```
