# DWriteTextAnalyzer::GetGlyphPlacements(wchar_t const *,ushort const *,DWRITE_SHAPING_TEXT_PROPERTIES *,uint,ushort const *,DWRITE_SHAPING_GLYPH_PROPERTIES const *,uint,IDWriteFontFace *,float,int,int,DWRITE_SCRIPT_ANALYSIS const *,wchar_t const *,DWRITE_TYPOGRAPHIC_FEATURES const * *,uint const *,uint,float *,DWRITE_GLYPH_OFFSET *)

- ea: `0x18013bb50`
- end: `0x18013c7f3`
- name: `?GetGlyphPlacements@DWriteTextAnalyzer@@UEAAJPEB_WPEBGPEAUDWRITE_SHAPING_TEXT_PROPERTIES@@I1PEBUDWRITE_SHAPING_GLYPH_PROPERTIES@@IPEAUIDWriteFontFace@@MHHPEBUDWRITE_SCRIPT_ANALYSIS@@0PEAPEBUDWRITE_TYPOGRAPHIC_FEATURES@@PEBIIPEAMPEAUDWRITE_GLYPH_OFFSET@@@Z`
- size: `3235`
- prototype: `__int64 __fastcall(DWriteTextAnalyzer *__hidden this, const wchar_t *, const unsigned __int16 *, struct DWRITE_SHAPING_TEXT_PROPERTIES *, unsigned int, const unsigned __int16 *, const struct DWRITE_SHAPING_GLYPH_PROPERTIES *, unsigned int, struct IDWriteFontFace *, float, int, int, const struct DWRITE_SCRIPT_ANALYSIS *, const wchar_t *, const struct DWRITE_TYPOGRAPHIC_FEATURES **, const unsigned int *, unsigned int, float *, struct DWRITE_GLYPH_OFFSET *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18011ef30`
- `0x18013bb50`
- `0x18013d760`
- `0x18013e870`
- `0x18013e8e0`
- `0x1801405dc`
- `0x180154068`
- `0x180167278`
- `0x1801d6730`
- `0x1801f37b0`
- `0x1801fa7e4`
- `0x1801fabd8`
- `0x18020c524`
- `0x180212490`
- `0x180252b20`
- `0x180252bc4`
- `0x180252e80`
- `0x180330010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18013c668`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18013c668`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18013c2c8`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18013c2c8`
- `TextShaping!ShapingSetInvariantAssertFunction` at `0x18013c6cf`
- `TextShaping!ShapingSetInvariantAssertFunction` at `0x18013c6cf`
- `TextShaping!ShapingGetGlyphPositions` at `0x18013c4c7`
- `TextShaping!ShapingGetGlyphPositions` at `0x18013c4c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall DWriteTextAnalyzer::GetGlyphPlacements(
        DWriteTextAnalyzer *this,
        const wchar_t *a2,
        const unsigned __int16 *a3,
        struct DWRITE_SHAPING_TEXT_PROPERTIES *a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        const struct DWRITE_SHAPING_GLYPH_PROPERTIES *a7,
        unsigned int a8,
        struct IDWriteFontFace *a9,
        float a10,
        int a11,
        int a12,
        const struct DWRITE_SCRIPT_ANALYSIS *a13,
        const wchar_t *a14,
        const struct DWRITE_TYPOGRAPHIC_FEATURES **a15,
        const unsigned int *a16,
        unsigned int a17,
        float *a18,
        struct DWRITE_GLYPH_OFFSET *a19)
{
  const WCHAR *v20; // rcx
  int v21; // ebx
  __int64 v22; // rax
  unsigned int v23; // edi
  __int64 v24; // r13
  unsigned __int64 v25; // r14
  __int64 v26; // rax
  __m128i v27; // xmm2
  BufferList *v28; // rcx
  struct BufferList::Buffer **v29; // rsi
  struct BufferList::Buffer *v30; // rdx
  __int64 v31; // r14
  unsigned __int64 v32; // rdx
  struct BufferList::Buffer **v33; // r13
  unsigned __int64 v34; // rdx
  struct BufferList::Buffer **v35; // rsi
  __int64 v36; // rcx
  int v37; // edi
  unsigned int v38; // r8d
  unsigned __int64 v39; // rdx
  unsigned int i; // r15d
  unsigned __int64 v41; // r8
  unsigned __int64 v42; // r9
  unsigned __int64 v43; // rcx
  struct BufferList::Buffer **v44; // rcx
  int v45; // r8d
  struct BufferList::Buffer **v46; // rcx
  int v47; // edx
  int v48; // ecx
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rax
  int GlyphPositions; // r9d
  __int64 v54; // rcx
  __int64 v55; // rdx
  unsigned __int64 v56; // rax
  float v57; // xmm1_4
  struct DWRITE_GLYPH_OFFSET *v58; // r10
  float *v59; // r11
  unsigned int v60; // edi
  __int64 result; // rax
  struct BufferList::Buffer **v62; // rax
  unsigned __int64 v63; // [rsp+88h] [rbp-2E0h] BYREF
  float *v64; // [rsp+90h] [rbp-2D8h]
  int v65; // [rsp+98h] [rbp-2D0h]
  LPCWSTR lpLocaleName; // [rsp+A0h] [rbp-2C8h] BYREF
  struct DWRITE_GLYPH_OFFSET *v67; // [rsp+A8h] [rbp-2C0h] BYREF
  struct BufferList::Buffer **v68; // [rsp+B0h] [rbp-2B8h]
  const unsigned int *v69; // [rsp+B8h] [rbp-2B0h]
  __int128 v70; // [rsp+C0h] [rbp-2A8h] BYREF
  __int128 v71; // [rsp+D0h] [rbp-298h]
  __int128 v72; // [rsp+E0h] [rbp-288h]
  struct BufferList::Buffer **v73; // [rsp+F0h] [rbp-278h]
  __int16 v74; // [rsp+F8h] [rbp-270h]
  const struct DWRITE_SHAPING_GLYPH_PROPERTIES *v75; // [rsp+100h] [rbp-268h]
  const unsigned __int16 *v76; // [rsp+108h] [rbp-260h]
  struct DWRITE_SHAPING_TEXT_PROPERTIES *v77; // [rsp+110h] [rbp-258h]
  const unsigned __int16 *v78; // [rsp+118h] [rbp-250h]
  const wchar_t *v79; // [rsp+120h] [rbp-248h]
  const struct DWRITE_TYPOGRAPHIC_FEATURES **v80; // [rsp+128h] [rbp-240h]
  char v81[8]; // [rsp+130h] [rbp-238h] BYREF
  __int64 v82; // [rsp+138h] [rbp-230h]
  __int64 v83; // [rsp+140h] [rbp-228h]
  __int128 v84; // [rsp+150h] [rbp-218h] BYREF
  __int64 v85; // [rsp+160h] [rbp-208h]
  void **v86; // [rsp+170h] [rbp-1F8h] BYREF
  void **v87; // [rsp+178h] [rbp-1F0h] BYREF
  void **v88; // [rsp+180h] [rbp-1E8h]
  int v89; // [rsp+188h] [rbp-1E0h]
  float v90; // [rsp+18Ch] [rbp-1DCh]
  char *v91; // [rsp+190h] [rbp-1D8h] BYREF
  struct BufferList::Buffer **v92; // [rsp+198h] [rbp-1D0h]
  struct BufferList::Buffer **v93; // [rsp+1A0h] [rbp-1C8h]
  char *v94; // [rsp+1A8h] [rbp-1C0h]
  __int64 v95; // [rsp+1B0h] [rbp-1B8h]
  bool v96; // [rsp+1B8h] [rbp-1B0h]
  char v97; // [rsp+1B9h] [rbp-1AFh]
  int v98; // [rsp+1BCh] [rbp-1ACh]
  _DWORD v99[2]; // [rsp+1C0h] [rbp-1A8h] BYREF
  int v100; // [rsp+1C8h] [rbp-1A0h]
  struct BufferList::Buffer **v101; // [rsp+1D0h] [rbp-198h]
  int v102; // [rsp+1D8h] [rbp-190h]
  float v103; // [rsp+1DCh] [rbp-18Ch]
  int v104; // [rsp+1E0h] [rbp-188h]
  __int128 v105; // [rsp+1E4h] [rbp-184h]
  __int64 v106; // [rsp+1F4h] [rbp-174h]
  _QWORD v107[3]; // [rsp+200h] [rbp-168h] BYREF
  struct BufferList::Buffer **v108; // [rsp+218h] [rbp-150h]
  int v109; // [rsp+220h] [rbp-148h]
  __int128 v110; // [rsp+228h] [rbp-140h]
  unsigned int v111; // [rsp+238h] [rbp-130h]
  struct BufferList::Buffer **v112; // [rsp+240h] [rbp-128h]
  int v113; // [rsp+248h] [rbp-120h]
  int v114; // [rsp+24Ch] [rbp-11Ch]
  _BYTE v115[96]; // [rsp+250h] [rbp-118h] BYREF
  void **v116; // [rsp+2B0h] [rbp-B8h] BYREF
  unsigned int v117; // [rsp+2B8h] [rbp-B0h]
  int v118; // [rsp+2BCh] [rbp-ACh]
  char *v119; // [rsp+2C0h] [rbp-A8h]
  unsigned __int64 v120; // [rsp+2C8h] [rbp-A0h]
  bool v121; // [rsp+2D0h] [rbp-98h]
  __int16 v122; // [rsp+2D1h] [rbp-97h]
  char v123; // [rsp+2D3h] [rbp-95h]
  __int64 v124; // [rsp+2D4h] [rbp-94h]
  int v125; // [rsp+2DCh] [rbp-8Ch]
  __int128 v126; // [rsp+2E0h] [rbp-88h]
  __int64 v127; // [rsp+2F0h] [rbp-78h]
  void ***v128; // [rsp+2F8h] [rbp-70h]
  WCHAR LCData[4]; // [rsp+300h] [rbp-68h] BYREF
  __int16 v130; // [rsp+308h] [rbp-60h]

  v77 = a4;
  v78 = a3;
  v79 = a2;
  v76 = a6;
  v75 = a7;
  v80 = a15;
  v69 = a16;
  v64 = a18;
  v67 = a19;
  if ( !a9 )
    return 2147942487LL;
  if ( !a8 )
    return 0;
  if ( !a5 )
    return 2147942487LL;
  v20 = &pszSrc;
  if ( a14 )
    v20 = a14;
  lpLocaleName = v20;
  LODWORD(v63) = _mm_getcsr();
  v21 = v63;
  v65 = v63;
  if ( (v63 & 0xFF80) != 0x1F80 )
  {
    LODWORD(v63) = 8064;
    _mm_setcsr(0x1F80u);
  }
  if ( *((_BYTE *)a9 + 220) == 7 )
  {
    result = 2291683337LL;
    if ( (v21 & 0xFF80) != 0x1F80 )
      _mm_setcsr(v21 & 0xFFFFFFC0);
  }
  else
  {
    v22 = *(_QWORD *)a13;
    LODWORD(v63) = (unsigned __int16)*(_QWORD *)a13;
    HIDWORD(v63) = HIDWORD(v22);
    v23 = v63;
    v24 = *((_QWORD *)a9 + 4) + 8LL;
    v25 = HIDWORD(v63);
    v86 = &IShapingClient::`vftable';
    v87 = &IShapingFont::`vftable';
    v88 = &IShapingCacheWriter::`vftable';
    v26 = *((_QWORD *)a9 + 6);
    v27 = *(__m128i *)(v26 + 24);
    v71 = *(_OWORD *)(v26 + 40);
    v72 = *(_OWORD *)(v26 + 56);
    v89 = 1065353216;
    v90 = a10 / (float)(unsigned __int16)_mm_cvtsi128_si32(v27);
    v86 = &ShapingInterface::`vftable'{for `IShapingClient'};
    v87 = &ShapingInterface::`vftable'{for `IShapingFont'};
    v88 = &ShapingInterface::`vftable'{for `IShapingCacheWriter'};
    v28 = (DWriteTextAnalyzer *)((char *)this + 16);
    v91 = (char *)this + 16;
    v92 = 0;
    v29 = (struct BufferList::Buffer **)_InterlockedExchange64((volatile __int64 *)this + 2, 0);
    if ( v29 )
    {
      v30 = *v29;
      *v29 = 0;
      if ( v30 && _InterlockedCompareExchange64((volatile signed __int64 *)v28, (signed __int64)v30, 0) )
        BufferList::FreeBuffers(v28, v30);
    }
    else
    {
      v62 = (struct BufferList::Buffer **)malloc(*((_QWORD *)this + 3));
      v29 = v62;
      if ( v62 )
        *v62 = 0;
      else
        v29 = 0;
    }
    v92 = v29;
    v93 = v29;
    if ( v29 )
    {
      *v29 = 0;
      v29 = 0;
      v93[1] = 0;
    }
    v94 = (char *)a9 + 48;
    v95 = v24;
    v96 = a11 != 0;
    v97 = (char)v29;
    v98 = (int)v29;
    v99[0] = v23;
    v99[1] = v25;
    v100 = *(_DWORD *)&aDflt[32 * (v23 < 0xAB ? v23 : 0)];
    v101 = v29;
    v102 = ShapingScriptFromScript((const struct ScriptAnalysis *)v99);
    v103 = a10;
    v104 = 1065353216;
    v105 = *(_OWORD *)&IdentityTransform.eM11;
    v106 = 0;
    v107[0] = &v91;
    v107[1] = v29;
    v107[2] = v29;
    std::_Tree<std::_Tmap_traits<unsigned int,ShapingCacheElement::SlotData,std::less<unsigned int>,StackAllocator::allocator<std::pair<unsigned int const,ShapingCacheElement::SlotData>>,0>>::_Alloc_sentinel_and_proxy(v107);
    v108 = v29;
    v109 = (int)v29;
    v110 = 0;
    v111 = (unsigned int)v29;
    v112 = v29;
    v113 = (int)v29;
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v115);
    v115[80] = (_BYTE)v29;
    if ( byte_1804B8A80 == (_BYTE)v29 )
    {
      ShapingSetInvariantAssertFunction(&ShapingAssertFailed);
      _mm_sfence();
      byte_1804B8A80 = 1;
    }
    else
    {
      _mm_lfence();
    }
    v70 = 0;
    v71 = 0;
    v72 = 0;
    WORD1(v63) = WORD1(v29);
    LOWORD(v63) = v23;
    HIDWORD(v63) = v25;
    v117 = (unsigned int)v29;
    v118 = 5;
    v116 = &ShapingCacheElement::ElementKey::`vftable';
    v119 = (char *)a9 + 80;
    v120 = v63;
    v121 = v96;
    v122 = 0;
    v123 = 0;
    v124 = 0;
    v128 = &v86;
    v125 = 0;
    v126 = 0;
    v127 = 0;
    v117 = ShapingCacheElement::ElementKey::ComputeHashCode((ShapingCacheElement::ElementKey *)&v116);
    *(_QWORD *)&v70 = 0;
    DWORD2(v70) = (_DWORD)v29;
    *(_QWORD *)&v71 = v29;
    DWORD2(v71) = (_DWORD)v29;
    *(_QWORD *)&v72 = v29;
    DWORD2(v72) = (_DWORD)v29;
    v73 = v29;
    v74 = 0;
    (*(void (__fastcall **)(__int64, void ***, __int128 *))(*(_QWORD *)v24 + 24LL))(v24, &v116, &v70);
    v31 = v71;
    if ( DWORD2(v71) < 0x14 || (v71 & 3) != 0 )
      FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(v71);
    v32 = *(unsigned int *)(v71 + 4);
    if ( v32 > DWORD2(v71)
      || DWORD2(v71) - v32 < 0x34
      || (v33 = (struct BufferList::Buffer **)(v71 + v32), (((_BYTE)v71 + (_BYTE)v32) & 3) != 0) )
    {
      FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(v71);
    }
    if ( *((_DWORD *)v33 + 2) > 1u )
    {
      Exception::Exception((Exception *)&v67, -2003283961, 0);
      v68 = v33;
      LogAndThrow<InvalidCacheDataException>(&v67, 0x6D656C655F6873LL, 422);
    }
    v84 = v71;
    v34 = *(unsigned int *)(v71 + 12);
    if ( v34 > DWORD2(v71) )
      FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(v71);
    v35 = (struct BufferList::Buffer **)(v71 + v34);
    v36 = (unsigned int)(DWORD2(v84) - v34);
    LODWORD(v63) = DWORD2(v84) - v34;
    v37 = HIDWORD(v84);
    v38 = *(_DWORD *)(v71 + 16);
    *(_DWORD *)LCData = v38;
    if ( (unsigned int)(DWORD2(v84) - v34) >> 4 < v38 || ((unsigned __int8)v35 & 3) != 0 )
      FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(v71 + v34);
    v39 = 16 * v38;
    for ( i = 0; i < v38; ++i )
    {
      v41 = HIDWORD(v35[2 * i + 1]);
      v42 = LODWORD(v35[2 * i + 1]);
      if ( v41 > (unsigned int)v36 || v36 - v41 < v42 )
        FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(v35);
      if ( (_DWORD)v41 != (_DWORD)v39 )
      {
        Exception::Exception((Exception *)&v67, -2003283961, 0);
        v68 = &v35[2 * i];
        LogAndThrow<InvalidCacheDataException>(&v67, 0x6D656C655F6873LL, 445);
      }
      if ( i && LODWORD(v35[2 * i - 2]) >= LODWORD(v35[2 * i]) )
      {
        LODWORD(v67) = -2003283961;
        CaptureStack(-2003283961, 0);
        v68 = &v35[2 * i];
        LogAndThrow<InvalidCacheDataException>(&v67, 0x6D656C655F6873LL, 451);
      }
      v43 = v42 + 7;
      if ( v42 + 7 < v42 || v43 > 0xFFFFFFFF )
        SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v43, v39);
      v39 = (v43 & 0xFFFFFFF8) + (unsigned int)v39;
      v36 = (unsigned int)v63;
      v38 = *(_DWORD *)LCData;
    }
    v44 = v108;
    v108 = v73;
    if ( v73 )
      _InterlockedIncrement((volatile signed __int32 *)v73 + 2);
    if ( v44 && _InterlockedExchangeAdd((volatile signed __int32 *)v44 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(struct BufferList::Buffer **, __int64))*v44)(v44, 1);
    v45 = *(_DWORD *)(v31 + 8);
    v109 = v45;
    *(_QWORD *)&v110 = v33;
    *((_QWORD *)&v110 + 1) = v35;
    v111 = *(_DWORD *)LCData;
    v112 = v35;
    v113 = v63;
    v114 = v37;
    v46 = v73;
    if ( v73 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v73 + 2, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(struct BufferList::Buffer **, __int64))*v46)(v46, 1);
      v45 = v109;
    }
    v102 = v45;
    v84 = 0;
    v85 = 0;
    LODWORD(v84) = v45;
    v47 = v100;
    if ( v45 == 1 )
      v47 = 0;
    DWORD1(v84) = v47;
    *(_QWORD *)LCData = 0;
    v130 = 0;
    if ( *lpLocaleName && GetLocaleInfoEx(lpLocaleName, 0x7Au, LCData, 5) == 5 )
      v48 = LOBYTE(LCData[0]) | ((LOBYTE(LCData[1]) | ((LOBYTE(LCData[2]) | (LOBYTE(LCData[3]) << 8)) << 8)) << 8);
    else
      v48 = 1953261156;
    DWORD2(v84) = v48;
    LODWORD(v85) = (*((_WORD *)v94 + 27) & 2) != 0 ? 0x5700 : 0;
    HIDWORD(v84) = v96 ? 2 : 0;
    HIDWORD(v85) = HIDWORD(v85) & 0xFFFFFF00 | (a12 != 0) | (((v102 != 26) | 2) << 7);
    lpLocaleName = (LPCWSTR)&v91;
    LODWORD(v63) = 0;
    std::vector<int,StackAllocator::allocator<int>>::vector<int,StackAllocator::allocator<int>>(
      &v70,
      a8,
      &v63,
      &lpLocaleName);
    lpLocaleName = (LPCWSTR)&v91;
    v63 = 0;
    std::vector<SHAPING_GLYPHOFFSET,StackAllocator::allocator<SHAPING_GLYPHOFFSET>>::vector<SHAPING_GLYPHOFFSET,StackAllocator::allocator<SHAPING_GLYPHOFFSET>>(
      v81,
      a8,
      &v63,
      &lpLocaleName);
    v97 = BYTE4(v85) & 1;
    if ( a8 > 0x7FFFFFFF )
      SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v50, v49);
    v51 = v82;
    if ( v82 == v83 )
      v51 = 0;
    v52 = *((_QWORD *)&v70 + 1);
    if ( *((_QWORD *)&v70 + 1) == (_QWORD)v71 )
      v52 = 0;
    GlyphPositions = ShapingGetGlyphPositions(
                       &v86,
                       &v87,
                       &v84,
                       v69,
                       v80,
                       a17,
                       v79,
                       v78,
                       v77,
                       a5,
                       v76,
                       v75,
                       a8,
                       v52,
                       v51);
    if ( !GlyphPositions )
    {
      v54 = v82;
      if ( v82 == v83 )
        v54 = 0;
      v55 = *((_QWORD *)&v70 + 1);
      if ( *((_QWORD *)&v70 + 1) == (_QWORD)v71 )
        v55 = 0;
      v56 = 0;
      v57 = v90;
      v58 = v67;
      v59 = v64;
      do
      {
        v59[v56] = (float)*(int *)(v55 + 4 * v56) * v57;
        *((float *)v58 + 2 * v56) = (float)*(int *)(v54 + 8 * v56) * v57;
        *((float *)v58 + 2 * v56 + 1) = (float)*(int *)(v54 + 8 * v56 + 4) * v57;
        ++v56;
      }
      while ( v56 < a8 );
    }
    v60 = ShapingException::HresultFromShapingError(GlyphPositions);
    std::vector<int,StackAllocator::allocator<int>>::_Tidy(v81);
    std::vector<int,StackAllocator::allocator<int>>::_Tidy(&v70);
    ShapingInterface::~ShapingInterface((ShapingInterface *)&v86);
    if ( (v21 & 0xFF80) != 0x1F80 )
      _mm_setcsr(v21 & 0xFFFFFFC0);
    return v60;
  }
  return result;
}

```

## disassembly

```asm
0x18013bb50  mov     rax, rsp
0x18013bb53  push    rbx
0x18013bb54  push    rsi
0x18013bb55  push    rdi
0x18013bb56  push    r12
0x18013bb58  push    r13
0x18013bb5a  push    r14
0x18013bb5c  push    r15
0x18013bb5e  sub     rsp, 330h
0x18013bb65  movaps  xmmword ptr [rax-48h], xmm6
0x18013bb69  mov     rax, cs:__security_cookie
0x18013bb70  xor     rax, rsp
0x18013bb73  mov     [rsp+368h+var_58], rax
0x18013bb7b  mov     [rsp+368h+var_258], r9
0x18013bb83  mov     [rsp+368h+var_250], r8
0x18013bb8b  mov     [rsp+368h+var_248], rdx
0x18013bb93  mov     r11, rcx
0x18013bb96  mov     rax, [rsp+368h+arg_28]
0x18013bb9e  mov     [rsp+368h+var_260], rax
0x18013bba6  mov     rax, [rsp+368h+arg_30]
0x18013bbae  mov     [rsp+368h+var_268], rax
0x18013bbb6  mov     r10, [rsp+368h+arg_40]
0x18013bbbe  mov     rax, [rsp+368h+arg_68]
0x18013bbc6  mov     rcx, [rsp+368h+arg_70]
0x18013bbce  mov     [rsp+368h+var_240], rcx
0x18013bbd6  mov     rcx, [rsp+368h+arg_78]
0x18013bbde  mov     [rsp+368h+var_2B0], rcx
0x18013bbe6  mov     rcx, [rsp+368h+arg_88]
0x18013bbee  mov     [rsp+368h+var_2D8], rcx
0x18013bbf6  mov     rcx, [rsp+368h+arg_90]
0x18013bbfe  mov     [rsp+368h+var_2C0], rcx
0x18013bc06  xor     r9d, r9d
0x18013bc09  test    r10, r10
0x18013bc0c  jz      loc_18013C710
0x18013bc12  mov     r12d, [rsp+368h+arg_38]
0x18013bc1a  test    r12d, r12d
0x18013bc1d  jz      loc_18013C71A
0x18013bc23  cmp     [rsp+368h+arg_20], r9d
0x18013bc2b  jz      loc_18013C710
0x18013bc31  lea     rcx, pszSrc
0x18013bc38  test    rax, rax
0x18013bc3b  cmovnz  rcx, rax
0x18013bc3f  mov     [rsp+368h+lpLocaleName], rcx
0x18013bc47  stmxcsr dword ptr [rsp+368h+var_2E0]
0x18013bc4f  mov     ebx, dword ptr [rsp+368h+var_2E0]
0x18013bc56  mov     [rsp+368h+var_2D0], ebx
0x18013bc5d  mov     eax, ebx
0x18013bc5f  mov     r8d, 0FF80h
0x18013bc65  and     eax, r8d
0x18013bc68  mov     edx, 1F80h
0x18013bc6d  cmp     eax, edx
0x18013bc6f  jz      short loc_18013BC80
0x18013bc71  mov     dword ptr [rsp+368h+var_2E0], edx
0x18013bc78  ldmxcsr dword ptr [rsp+368h+var_2E0]
0x18013bc80  cmp     byte ptr [r10+0DCh], 7
0x18013bc88  jz      loc_18013C681
0x18013bc8e  cmp     [rsp+368h+arg_50], r9d
0x18013bc96  setnz   [rsp+368h+var_2E8]
0x18013bc9e  mov     rax, [rsp+368h+arg_60]
0x18013bca6  mov     rax, [rax]
0x18013bca9  movzx   ecx, ax
0x18013bcac  mov     dword ptr [rsp+368h+var_2E0], ecx
0x18013bcb3  shr     rax, 20h
0x18013bcb7  mov     dword ptr [rsp+368h+var_2E0+4], eax
0x18013bcbe  mov     rdi, [rsp+368h+var_2E0]
0x18013bcc6  mov     r13, [r10+20h]
0x18013bcca  add     r13, 8
0x18013bcce  mov     dword ptr [rsp+368h+var_2E0], edi
0x18013bcd5  mov     r14, rdi
0x18013bcd8  shr     r14, 20h
0x18013bcdc  lea     r15, [r10+30h]
0x18013bce0  lea     rax, ??_7IShapingClient@@6B@; const IShapingClient::`vftable'
0x18013bce7  mov     [rsp+368h+var_1F8], rax
0x18013bcef  lea     rax, ??_7IShapingFont@@6B@; const IShapingFont::`vftable'
0x18013bcf6  mov     [rsp+368h+var_1F0], rax
0x18013bcfe  lea     rax, ??_7IShapingCacheWriter@@6B@; const IShapingCacheWriter::`vftable'
0x18013bd05  mov     [rsp+368h+var_1E8], rax
0x18013bd0d  mov     rax, [r15]
0x18013bd10  movups  xmm2, xmmword ptr [rax+18h]
0x18013bd14  movups  xmm0, xmmword ptr [rax+28h]
0x18013bd18  movups  [rsp+368h+var_298], xmm0
0x18013bd20  movups  xmm1, xmmword ptr [rax+38h]
0x18013bd24  movups  [rsp+368h+var_288], xmm1
0x18013bd2c  movzx   eax, word ptr [r15+36h]
0x18013bd31  mov     [rsp+368h+var_1E0], 3F800000h
0x18013bd3c  movd    eax, xmm2
0x18013bd40  movzx   eax, ax
0x18013bd43  movd    xmm1, eax
0x18013bd47  cvtdq2ps xmm1, xmm1
0x18013bd4a  movss   xmm6, [rsp+368h+arg_48]
0x18013bd53  movaps  xmm0, xmm6
0x18013bd56  divss   xmm0, xmm1
0x18013bd5a  movss   [rsp+368h+var_1DC], xmm0
0x18013bd63  lea     rax, ??_7ShapingInterface@@6BIShapingClient@@@; const ShapingInterface::`vftable'{for `IShapingClient'}
0x18013bd6a  mov     [rsp+368h+var_1F8], rax
0x18013bd72  lea     rax, ??_7ShapingInterface@@6BIShapingFont@@@; const ShapingInterface::`vftable'{for `IShapingFont'}
0x18013bd79  mov     [rsp+368h+var_1F0], rax
0x18013bd81  lea     rax, ??_7ShapingInterface@@6BIShapingCacheWriter@@@; const ShapingInterface::`vftable'{for `IShapingCacheWriter'}
0x18013bd88  mov     [rsp+368h+var_1E8], rax
0x18013bd90  lea     rcx, [r11+10h]; this
0x18013bd94  mov     [rsp+368h+var_1D8], rcx
0x18013bd9c  mov     [rsp+368h+var_1D0], r9
0x18013bda4  mov     rsi, r9
0x18013bda7  xchg    rsi, [rcx]
0x18013bdaa  test    rsi, rsi
0x18013bdad  jz      loc_18013C664
0x18013bdb3  mov     rdx, [rsi]; struct BufferList::Buffer *
0x18013bdb6  mov     [rsi], r9
0x18013bdb9  test    rdx, rdx
0x18013bdbc  jnz     loc_18013C721
0x18013bdc2  mov     [rsp+368h+var_1D0], rsi
0x18013bdca  mov     [rsp+368h+var_1C8], rsi
0x18013bdd2  test    rsi, rsi
0x18013bdd5  jz      short loc_18013BDE8
0x18013bdd7  mov     [rsi], r9
0x18013bdda  mov     rax, [rsp+368h+var_1C8]
0x18013bde2  xor     esi, esi
0x18013bde4  mov     [rax+8], rsi
0x18013bde8  mov     [rsp+368h+var_1C0], r15
0x18013bdf0  mov     [rsp+368h+var_1B8], r13
0x18013bdf8  mov     al, [rsp+368h+var_2E8]
0x18013bdff  mov     [rsp+368h+var_1B0], al
0x18013be06  mov     [rsp+368h+var_1AF], sil
0x18013be0e  mov     [rsp+368h+var_1AC], esi
0x18013be15  mov     [rsp+368h+var_1A8], edi
0x18013be1c  mov     [rsp+368h+var_1A4], r14d
0x18013be24  cmp     edi, 0ABh
0x18013be2a  sbb     eax, eax
0x18013be2c  and     eax, edi
0x18013be2e  shl     rax, 5
0x18013be32  lea     rcx, aDflt; "DFLT"
0x18013be39  mov     eax, [rax+rcx]
0x18013be3c  mov     [rsp+368h+var_1A0], eax
0x18013be43  mov     [rsp+368h+var_198], rsi
0x18013be4b  lea     rcx, [rsp+368h+var_1A8]; struct ScriptAnalysis *
0x18013be53  call    ?ShapingScriptFromScript@@YAJAEBVScriptAnalysis@@@Z; ShapingScriptFromScript(ScriptAnalysis const &)
0x18013be58  mov     [rsp+368h+var_190], eax
0x18013be5f  movss   [rsp+368h+var_18C], xmm6
0x18013be68  mov     [rsp+368h+var_188], 3F800000h
0x18013be73  movups  xmm0, xmmword ptr cs:?IdentityTransform@@3UDWRITE_MATRIX@@B.eM11; DWRITE_MATRIX const IdentityTransform ...
0x18013be7a  movdqu  [rsp+368h+var_184], xmm0
0x18013be83  mov     [rsp+368h+var_174], 0
0x18013be8f  lea     rax, [rsp+368h+var_1D8]
0x18013be97  mov     [rsp+368h+var_168], rax
0x18013be9f  mov     [rsp+368h+var_160], rsi
0x18013bea7  mov     [rsp+368h+var_158], rsi
0x18013beaf  lea     rcx, [rsp+368h+var_168]
0x18013beb7  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@IUSlotData@ShapingCacheElement@@U?$less@I@std@@U?$allocator@U?$pair@$$CBIUSlotData@ShapingCacheElement@@@std@@@StackAllocator@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<uint,ShapingCacheElement::SlotData,std::less<uint>,StackAllocator::allocator<std::pair<uint const,ShapingCacheElement::SlotData>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18013bebc  nop
0x18013bebd  mov     [rsp+368h+var_150], rsi
0x18013bec5  mov     [rsp+368h+var_148], esi
0x18013becc  xorps   xmm0, xmm0
0x18013becf  movdqu  [rsp+368h+var_140], xmm0
0x18013bed8  mov     [rsp+368h+var_130], esi
0x18013bedf  mov     [rsp+368h+var_128], rsi
0x18013bee7  mov     [rsp+368h+var_120], esi
0x18013beee  lea     rcx, [rsp+368h+var_118]; void *
0x18013bef6  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18013befb  nop
0x18013befc  mov     [rsp+368h+var_C8], sil
0x18013bf04  cmp     cs:byte_1804B8A80, sil
0x18013bf0b  jz      loc_18013C6C8
0x18013bf11  nop
0x18013bf12  lfence
0x18013bf15  nop
0x18013bf16  xorps   xmm0, xmm0
0x18013bf19  movups  [rsp+368h+var_2A8], xmm0
0x18013bf21  movups  [rsp+368h+var_298], xmm0
0x18013bf29  movups  [rsp+368h+var_288], xmm0
0x18013bf31  mov     [rsp+368h+var_2E0], rsi
0x18013bf39  mov     word ptr [rsp+368h+var_2E0], di
0x18013bf41  mov     dword ptr [rsp+368h+var_2E0+4], r14d
0x18013bf49  mov     rax, [rsp+368h+var_2E0]
0x18013bf51  mov     [rsp+368h+var_B0], esi
0x18013bf58  mov     [rsp+368h+var_AC], 5
0x18013bf63  lea     rcx, ??_7ElementKey@ShapingCacheElement@@6B@; const ShapingCacheElement::ElementKey::`vftable'
0x18013bf6a  mov     [rsp+368h+var_B8], rcx
0x18013bf72  lea     rcx, [r15+20h]
0x18013bf76  mov     [rsp+368h+var_A8], rcx
0x18013bf7e  mov     [rsp+368h+var_A0], rax
0x18013bf86  mov     al, [rsp+368h+var_1B0]
0x18013bf8d  mov     [rsp+368h+var_98], al
0x18013bf94  movzx   eax, word ptr [rsp+368h+var_2A8+9]
0x18013bf9c  mov     [rsp+368h+var_97], ax
0x18013bfa4  mov     al, byte ptr [rsp+368h+var_2A8+0Bh]
0x18013bfab  mov     [rsp+368h+var_95], al
0x18013bfb2  mov     [rsp+368h+var_94], 0
0x18013bfbe  mov     [rsp+368h+var_78], 0
0x18013bfca  lea     rax, [rsp+368h+var_1F8]
0x18013bfd2  mov     [rsp+368h+var_70], rax
0x18013bfda  mov     [rsp+368h+var_8C], 0
0x18013bfe5  xorps   xmm0, xmm0
0x18013bfe8  xor     eax, eax
0x18013bfea  movups  [rsp+368h+var_88], xmm0
0x18013bff2  mov     [rsp+368h+var_78], rax
0x18013bffa  lea     rcx, [rsp+368h+var_B8]; this
0x18013c002  call    ?ComputeHashCode@ElementKey@ShapingCacheElement@@AEBAIXZ; ShapingCacheElement::ElementKey::ComputeHashCode(void)
0x18013c007  mov     [rsp+368h+var_B0], eax
0x18013c00e  mov     qword ptr [rsp+368h+var_2A8], 0
0x18013c01a  mov     dword ptr [rsp+368h+var_2A8+8], esi
0x18013c021  mov     qword ptr [rsp+368h+var_298], rsi
0x18013c029  mov     dword ptr [rsp+368h+var_298+8], esi
0x18013c030  mov     qword ptr [rsp+368h+var_288], rsi
0x18013c038  mov     dword ptr [rsp+368h+var_288+8], esi
0x18013c03f  mov     [rsp+368h+var_278], rsi
0x18013c047  mov     [rsp+368h+var_270], 0
0x18013c051  mov     rax, [r13+0]
0x18013c055  lea     r8, [rsp+368h+var_2A8]
0x18013c05d  lea     rdx, [rsp+368h+var_B8]
0x18013c065  mov     rcx, r13
0x18013c068  mov     rax, [rax+18h]
0x18013c06c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c071  mov     ecx, dword ptr [rsp+368h+var_298+8]
0x18013c078  mov     r14, qword ptr [rsp+368h+var_298]
0x18013c080  cmp     ecx, 14h
0x18013c083  jb      loc_18013C7D6
0x18013c089  mov     r9b, 3
0x18013c08c  test    r9b, r14b
0x18013c08f  jnz     loc_18013C7D6
0x18013c095  mov     edx, [r14+4]
0x18013c099  cmp     rdx, rcx
0x18013c09c  ja      loc_18013C6BF
0x18013c0a2  mov     eax, ecx
0x18013c0a4  sub     rax, rdx
0x18013c0a7  cmp     rax, 34h ; '4'
0x18013c0ab  jb      loc_18013C6BF
0x18013c0b1  lea     r13, [r14+rdx]
0x18013c0b5  test    r9b, r13b
0x18013c0b8  jnz     loc_18013C6BF
0x18013c0be  cmp     dword ptr [r13+8], 1
0x18013c0c3  ja      loc_18013C73B
0x18013c0c9  movaps  xmm0, [rsp+368h+var_298]
0x18013c0d1  movdqu  [rsp+368h+var_218], xmm0
0x18013c0da  mov     edx, [r14+0Ch]
0x18013c0de  cmp     rdx, rcx
0x18013c0e1  ja      loc_18013C778
0x18013c0e7  lea     rsi, [r14+rdx]
0x18013c0eb  mov     ecx, dword ptr [rsp+368h+var_218+8]
0x18013c0f2  sub     ecx, edx
0x18013c0f4  mov     dword ptr [rsp+368h+var_2E0], ecx
0x18013c0fb  mov     edi, dword ptr [rsp+368h+var_218+0Ch]
0x18013c102  mov     r8d, [r14+10h]
0x18013c106  mov     dword ptr [rsp+368h+LCData], r8d
0x18013c10e  mov     eax, ecx
0x18013c110  shr     eax, 4
0x18013c113  cmp     eax, r8d
0x18013c116  jb      loc_18013C7CE
0x18013c11c  test    r9b, sil
0x18013c11f  jnz     loc_18013C7CE
0x18013c125  mov     edx, r8d
0x18013c128  shl     edx, 4
0x18013c12b  xor     r10d, r10d
0x18013c12e  mov     r15d, r10d
0x18013c131  cmp     r15d, r8d
0x18013c134  jnb     short loc_18013C1A9
0x18013c136  mov     eax, r15d
0x18013c139  add     rax, rax
0x18013c13c  mov     r8d, [rsi+rax*8+0Ch]
0x18013c141  mov     eax, r15d
0x18013c144  add     rax, rax
0x18013c147  mov     r9d, [rsi+rax*8+8]
0x18013c14c  mov     eax, ecx
0x18013c14e  cmp     r8, rax
0x18013c151  ja      loc_18013C6B2
0x18013c157  sub     rcx, r8
0x18013c15a  cmp     rcx, r9
0x18013c15d  jb      loc_18013C6B2
0x18013c163  cmp     r8d, edx
0x18013c166  jnz     loc_18013C780
0x18013c16c  test    r15d, r15d
0x18013c16f  jnz     loc_18013C5E7
0x18013c175  lea     rcx, [r9+7]
0x18013c179  cmp     rcx, r9
0x18013c17c  jb      loc_18013C6BA
0x18013c182  mov     eax, 0FFFFFFFFh
0x18013c187  cmp     rcx, rax
0x18013c18a  ja      loc_18013C6BA
0x18013c190  and     ecx, 0FFFFFFF8h
0x18013c193  add     edx, ecx
0x18013c195  inc     r15d
0x18013c198  mov     ecx, dword ptr [rsp+368h+var_2E0]
0x18013c19f  mov     r8d, dword ptr [rsp+368h+LCData]
0x18013c1a7  jmp     short loc_18013C131
0x18013c1a9  mov     rax, [rsp+368h+var_278]
0x18013c1b1  mov     rcx, [rsp+368h+var_150]
0x18013c1b9  mov     [rsp+368h+var_150], rax
0x18013c1c1  xor     r15d, r15d
0x18013c1c4  test    rax, rax
0x18013c1c7  jz      short loc_18013C1CD
0x18013c1c9  lock inc dword ptr [rax+8]
0x18013c1cd  test    rcx, rcx
0x18013c1d0  jz      short loc_18013C1E3
0x18013c1d2  or      eax, 0FFFFFFFFh
0x18013c1d5  lock xadd [rcx+8], eax
0x18013c1da  cmp     eax, 1
0x18013c1dd  jz      loc_18013C6FB
0x18013c1e3  mov     r8d, [r14+8]
0x18013c1e7  mov     [rsp+368h+var_148], r8d
0x18013c1ef  mov     qword ptr [rsp+368h+var_140], r13
0x18013c1f7  mov     qword ptr [rsp+368h+var_140+8], rsi
  ... truncated ...
```
