# CCompositionMagnifierBrush::GetLayeredBrushParameters(CBrushDrawListGenerator *)

- ea: `0x1801ff624`
- end: `0x180200460`
- name: `?GetLayeredBrushParameters@CCompositionMagnifierBrush@@AEBAJPEAVCBrushDrawListGenerator@@@Z`
- size: `3644`
- prototype: `__int64 __fastcall(CCompositionMagnifierBrush *__hidden this, struct CBrushDrawListGenerator *)`
- caller_count: `1`
- callee_count: `46`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18025e890`

## callees

- `0x18001dfb0`
- `0x1800210e4`
- `0x180026eac`
- `0x18004061c`
- `0x18004fce4`
- `0x1800654d4`
- `0x1800873d0`
- `0x1800882e0`
- `0x18008df5c`
- `0x18008df88`
- `0x1800917b4`
- `0x180093160`
- `0x1800976a0`
- `0x180099d10`
- `0x18009a1f8`
- `0x18009b460`
- `0x18009cd80`
- `0x1800ae8a0`
- `0x1800b3630`
- `0x1800cdd70`
- `0x1800cff38`
- `0x1800efd40`
- `0x1800fdd80`
- `0x180109520`
- `0x180118a9c`
- `0x180119230`
- `0x18011a3c0`
- `0x18011a460`
- `0x18011a480`
- `0x18011a810`
- `0x18011aa20`
- `0x180140d20`
- `0x180142d50`
- `0x18014ed10`
- `0x180153b20`
- `0x1801853e0`
- `0x1801a1410`
- `0x1801a1df4`
- `0x1801f1804`
- `0x1801ff624`
- `0x180200468`
- `0x1802284b0`
- `0x18025e3b4`
- `0x18025e8f4`
- `0x18029a940`
- `0x1802b6010`

## string_xrefs

- `0x1801ff71d`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`
- `0x1801ff7ca`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`
- `0x1801ff87c`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`
- `0x1801ff936`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`
- `0x1801ffa09`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`
- `0x1801ffaff`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`
- `0x1801ffbd9`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`
- `0x1801ffd45`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`
- `0x1801ffed3`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`
- `0x18020009a`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`
- `0x180200168`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`
- `0x18020028a`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`
- `0x1802002b7`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`
- `0x1802002df`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`
- `0x180200377`: `onecoreuap\windows\dwm\dwmcore\resources\compositionmagnifierbrush.cpp`

## pseudocode

```c
__int64 __fastcall CCompositionMagnifierBrush::GetLayeredBrushParameters(
        CCompositionMagnifierBrush *this,
        struct CBrushDrawListGenerator *a2)
{
  CDrawingContext *v2; // rdi
  D2D_SIZE_F v4; // xmm0_8
  CDrawingContext *v5; // rcx
  struct CBrushDrawListGenerator *v6; // r12
  struct CVisual *CurrentVisual; // r13
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  int v11; // esi
  char v12; // si
  FLOAT height; // xmm6_4
  FLOAT width; // xmm7_4
  __int64 v15; // rcx
  int v16; // eax
  int v17; // r14d
  int v18; // eax
  char v19; // r14
  __int128 *v20; // rax
  __int128 v21; // xmm0
  int v22; // eax
  int BVIBrushParameters; // r15d
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int DrawList; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  __m128i si128; // xmm8
  __m128i v41; // xmm9
  __m128i v42; // xmm10
  __m128i v43; // xmm11
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  const struct CVisualTreePath *v48; // rdx
  struct CBackdropVisualImage *BackdropVisualImage; // rax
  BOOL v50; // eax
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // eax
  CExcludeVisualReference *v55; // rbx
  CExcludeVisualReference *v56; // r15
  struct CVisual *VisualNoRef; // rax
  CVisualTree *v58; // r13
  const struct CVisualTree *RootVisualTree; // rax
  CVisual *v60; // r11
  int WorldTransform; // eax
  int v62; // r12d
  __int64 Bounds; // rax
  __int64 v64; // rdx
  int v65; // eax
  int v66; // eax
  int v67; // eax
  int v68; // eax
  int v69; // eax
  int v70; // eax
  int v71; // eax
  int v72; // eax
  int v73; // eax
  int v74; // eax
  __int64 v76; // rax
  int v77; // [rsp+20h] [rbp-E0h]
  int v78; // [rsp+20h] [rbp-E0h]
  int v79; // [rsp+20h] [rbp-E0h]
  int v80; // [rsp+20h] [rbp-E0h]
  int v81; // [rsp+20h] [rbp-E0h]
  int v82; // [rsp+20h] [rbp-E0h]
  int v83; // [rsp+20h] [rbp-E0h]
  int v84; // [rsp+20h] [rbp-E0h]
  int v85; // [rsp+20h] [rbp-E0h]
  int v86; // [rsp+20h] [rbp-E0h]
  int v87; // [rsp+20h] [rbp-E0h]
  int v88; // [rsp+20h] [rbp-E0h]
  D2D_SIZE_F v89; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v90; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v91; // [rsp+40h] [rbp-C0h] BYREF
  char v92; // [rsp+42h] [rbp-BEh]
  __int64 v93; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v94; // [rsp+58h] [rbp-A8h] BYREF
  const char *v95; // [rsp+60h] [rbp-A0h] BYREF
  CExcludeVisualReference *v96; // [rsp+68h] [rbp-98h] BYREF
  char v97; // [rsp+70h] [rbp-90h]
  unsigned __int64 v98; // [rsp+78h] [rbp-88h] BYREF
  __int128 v99; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v100[60]; // [rsp+90h] [rbp-70h]
  int v101; // [rsp+CCh] [rbp-34h]
  __int128 v102; // [rsp+D0h] [rbp-30h]
  int v103; // [rsp+E0h] [rbp-20h]
  int v104; // [rsp+F0h] [rbp-10h] BYREF
  char v105; // [rsp+F4h] [rbp-Ch]
  CBrushDrawListGenerator *v106; // [rsp+F8h] [rbp-8h]
  __int64 *v107; // [rsp+100h] [rbp+0h] BYREF
  __int64 v108; // [rsp+108h] [rbp+8h] BYREF
  char v109; // [rsp+110h] [rbp+10h]
  _BYTE v110[24]; // [rsp+118h] [rbp+18h] BYREF
  _OWORD v111[4]; // [rsp+130h] [rbp+30h] BYREF
  int v112; // [rsp+170h] [rbp+70h]
  _OWORD v113[4]; // [rsp+180h] [rbp+80h] BYREF
  int v114; // [rsp+1C0h] [rbp+C0h]
  _OWORD v115[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  int v116; // [rsp+210h] [rbp+110h]
  __int128 v117; // [rsp+220h] [rbp+120h] BYREF
  __int64 v118; // [rsp+230h] [rbp+130h]
  _BYTE v119[80]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v120[4496]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+14D8h] [rbp+13D8h]

  v2 = *(CDrawingContext **)a2;
  v4 = *(D2D_SIZE_F *)((char *)a2 + 44);
  v5 = *(CDrawingContext **)a2;
  v106 = a2;
  v6 = a2;
  v98 = 0;
  v89 = v4;
  CurrentVisual = CDrawingContext::GetCurrentVisual(v5);
  wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(&v98);
  v8 = (*(__int64 (__fastcall **)(_QWORD *))(*((_QWORD *)v2 + 2) + 16LL))((_QWORD *)v2 + 2);
  LODWORD(v96) = 36;
  v95 = "DWM Magnifier Brush Resample Surface";
  v77 = 3;
  v9 = CDrawingContext::PushOffScreenRenderingLayer(v2, &v95, &v89, *(unsigned int *)(v8 + 8));
  v11 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
      (const char *)(unsigned int)v9,
      3);
LABEL_106:
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v98);
    return (unsigned int)v11;
  }
  v12 = *((_BYTE *)this + 108);
  height = v89.height;
  width = v89.width;
  if ( v12 )
  {
    v104 = *((_DWORD *)this + 26);
    v105 = 1;
    v93 = 0x3F8000003F800000LL;
    v95 = 0;
    LODWORD(v96) = PixelAlign(v10, 1);
    HIDWORD(v96) = PixelAlign(v15, 1);
    v16 = CDrawingContext::PushResampleLayer(v2, CurrentVisual, (__int64)&v93, (__int64)&v104);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
        (const char *)(unsigned int)v16,
        v77);
      v18 = CDrawingContext::PopLayer(v2);
      if ( v18 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x48,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)v18,
          v78);
      v11 = v17;
      goto LABEL_106;
    }
  }
  v19 = *((_BYTE *)this + 152);
  if ( v19 )
  {
    v20 = (__int128 *)*((_QWORD *)this + 16);
    *(_DWORD *)v100 = 0;
    *(_DWORD *)&v100[20] = 0;
    *(_DWORD *)&v100[40] = 0;
    v21 = *v20;
    v101 = 0;
    v103 = 1065353216;
    v99 = v21;
    *(_OWORD *)&v100[4] = v20[1];
    *(_OWORD *)&v100[24] = v20[2];
    *(_OWORD *)&v100[44] = v20[3];
    v102 = v20[4];
    v22 = CDrawingContext::PushColorTransformLayer(v2);
    BVIBrushParameters = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
        (const char *)(unsigned int)v22,
        v77);
      if ( v12 )
      {
        v24 = CDrawingContext::PopLayer(v2);
        if ( v24 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x69,
            (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
            (const char *)(unsigned int)v24,
            v79);
      }
      v25 = CDrawingContext::PopLayer(v2);
      if ( v25 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x48,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)v25,
          v79);
LABEL_15:
      v11 = BVIBrushParameters;
      goto LABEL_106;
    }
  }
  v90 = 0;
  v95 = (const char *)&v90;
  v96 = 0;
  v97 = 1;
  BVIBrushParameters = CBrush::CreateLayoutGeometryDrawListBrush(this, v2, &v89, &v96);
  wil::details::out_param_t<std::unique_ptr<CDrawListBrush>>::~out_param_t<std::unique_ptr<CDrawListBrush>>(&v95);
  if ( BVIBrushParameters < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
      (const char *)(unsigned int)BVIBrushParameters,
      v77);
    std::unique_ptr<CShape>::~unique_ptr<CShape>(&v90);
    if ( v19 )
    {
      v26 = CDrawingContext::PopLayer(v2);
      if ( v26 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x83,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)v26,
          v80);
    }
    if ( v12 )
    {
      v27 = CDrawingContext::PopLayer(v2);
      if ( v27 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x69,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)v27,
          v80);
    }
    v28 = CDrawingContext::PopLayer(v2);
    if ( v28 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
        (const char *)(unsigned int)v28,
        v80);
    goto LABEL_15;
  }
  CBrushDrawListGenerator::CBrushDrawListGenerator((CBrushDrawListGenerator *)v119, v2, &v89);
  BVIBrushParameters = CCompositionMagnifierBrush::GetBVIBrushParameters(this, (struct CBrushDrawListGenerator *)v119);
  if ( BVIBrushParameters < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
      (const char *)(unsigned int)BVIBrushParameters,
      v77);
    CBrushDrawListGenerator::~CBrushDrawListGenerator((CBrushDrawListGenerator *)v119);
    std::unique_ptr<CShape>::~unique_ptr<CShape>(&v90);
    if ( v19 )
    {
      v29 = CDrawingContext::PopLayer(v2);
      if ( v29 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x83,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)v29,
          v81);
    }
    if ( v12 )
    {
      v30 = CDrawingContext::PopLayer(v2);
      if ( v30 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x69,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)v30,
          v81);
    }
    v31 = CDrawingContext::PopLayer(v2);
    if ( v31 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
        (const char *)(unsigned int)v31,
        v81);
    goto LABEL_15;
  }
  *(_DWORD *)v100 = 0;
  LOBYTE(v103) = 0;
  v99 = v90;
  HIDWORD(v102) = 257;
  CDrawListEntryBuilder::CDrawListEntryBuilder((CDrawListEntryBuilder *)v120);
  DrawList = CBrushDrawListGenerator::GenerateDrawList(
               (CBrushDrawListGenerator *)v119,
               (const struct CBrushDrawListGenerator::GenerateDrawListProperties *)&v99,
               (struct CDrawListEntryBuilder *)v120);
  BVIBrushParameters = DrawList;
  if ( DrawList < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
      (const char *)(unsigned int)DrawList,
      v77);
    CDrawListEntryBuilder::~CDrawListEntryBuilder((CDrawListEntryBuilder *)v120);
    CBrushDrawListGenerator::~CBrushDrawListGenerator((CBrushDrawListGenerator *)v119);
    std::unique_ptr<CShape>::~unique_ptr<CShape>(&v90);
    if ( v19 )
    {
      v33 = CDrawingContext::PopLayer(v2);
      if ( v33 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x83,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)v33,
          v82);
    }
    if ( v12 )
    {
      v34 = CDrawingContext::PopLayer(v2);
      if ( v34 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x69,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)v34,
          v82);
    }
    v35 = CDrawingContext::PopLayer(v2);
    if ( v35 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
        (const char *)(unsigned int)v35,
        v82);
    goto LABEL_15;
  }
  v89 = 0;
  v36 = CDrawListCache::InternalCreate(1, (struct CDrawListCache **)&v89);
  BVIBrushParameters = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
      (const char *)(unsigned int)v36,
      v77);
    wil::com_ptr_t<CDrawListCache,wil::err_returncode_policy>::~com_ptr_t<CDrawListCache,wil::err_returncode_policy>(&v89);
    CDrawListEntryBuilder::~CDrawListEntryBuilder((CDrawListEntryBuilder *)v120);
    CBrushDrawListGenerator::~CBrushDrawListGenerator((CBrushDrawListGenerator *)v119);
    std::unique_ptr<CShape>::~unique_ptr<CShape>(&v90);
    if ( v19 )
    {
      v37 = CDrawingContext::PopLayer(v2);
      if ( v37 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x83,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)v37,
          v83);
    }
    if ( v12 )
    {
      v38 = CDrawingContext::PopLayer(v2);
      if ( v38 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x69,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)v38,
          v83);
    }
    v39 = CDrawingContext::PopLayer(v2);
    if ( v39 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
        (const char *)(unsigned int)v39,
        v83);
    goto LABEL_15;
  }
  CDrawListCache::Update(*(CDrawListCache **)&v89, v2, (struct CDrawListEntryBuilder *)v120);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v41 = _mm_load_si128((const __m128i *)&_xmm);
  v42 = _mm_load_si128((const __m128i *)&_xmm);
  v43 = _mm_load_si128((const __m128i *)&_xmm);
  v114 = 10666;
  v113[0] = si128;
  v113[1] = v41;
  v113[2] = v42;
  v113[3] = v43;
  v84 = 5;
  v44 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))CDrawListCache::Render)(v89, v2, v113);
  BVIBrushParameters = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
      (const char *)(unsigned int)v44,
      5);
    wil::com_ptr_t<CDrawListCache,wil::err_returncode_policy>::~com_ptr_t<CDrawListCache,wil::err_returncode_policy>(&v89);
    CDrawListEntryBuilder::~CDrawListEntryBuilder((CDrawListEntryBuilder *)v120);
    CBrushDrawListGenerator::~CBrushDrawListGenerator((CBrushDrawListGenerator *)v119);
    std::unique_ptr<CShape>::~unique_ptr<CShape>(&v90);
    if ( v19 )
    {
      v45 = CDrawingContext::PopLayer(v2);
      if ( v45 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x83,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)v45,
          v85);
    }
    if ( v12 )
    {
      v46 = CDrawingContext::PopLayer(v2);
      if ( v46 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x69,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)v46,
          v85);
    }
    v47 = CDrawingContext::PopLayer(v2);
    if ( v47 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
        (const char *)(unsigned int)v47,
        v85);
    goto LABEL_15;
  }
  if ( *((_BYTE *)this + 110) )
  {
    v48 = (const struct CVisualTreePath *)*((_QWORD *)v2 + 996);
    v112 = 10666;
    v111[0] = si128;
    v111[1] = v41;
    v111[2] = v42;
    v111[3] = v43;
    BackdropVisualImage = CVisual::GetBackdropVisualImage(CurrentVisual, v48);
    CMILMatrix::Translate(
      (CMILMatrix *)v111,
      COERCE_FLOAT(*((_DWORD *)BackdropVisualImage + 24) ^ _xmm) - *((float *)BackdropVisualImage + 414),
      COERCE_FLOAT(*((_DWORD *)BackdropVisualImage + 25) ^ _xmm) - *((float *)BackdropVisualImage + 415));
    *(_QWORD *)&v117 = 6;
    LOBYTE(v50) = 1;
    DWORD2(v117) = 1;
    if ( !*((_BYTE *)this + 108) )
    {
      CMILMatrix::Scale((CMILMatrix *)v111, *((float *)this + 26), *((float *)this + 26), 0.0);
      DWORD1(v117) = v50;
    }
    v51 = CDrawingContext::PushRenderOptionsInternal(v2, 0, (const struct MilRenderOptions *)&v117, v50);
    BVIBrushParameters = v51;
    if ( v51 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
        (const char *)(unsigned int)v51,
        5);
      wil::com_ptr_t<CDrawListCache,wil::err_returncode_policy>::~com_ptr_t<CDrawListCache,wil::err_returncode_policy>(&v89);
      CDrawListEntryBuilder::~CDrawListEntryBuilder((CDrawListEntryBuilder *)v120);
      CBrushDrawListGenerator::~CBrushDrawListGenerator((CBrushDrawListGenerator *)v119);
      std::unique_ptr<CShape>::~unique_ptr<CShape>(&v90);
      if ( v19 )
      {
        v52 = CDrawingContext::PopLayer(v2);
        if ( v52 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x83,
            (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
            (const char *)(unsigned int)v52,
            v86);
      }
      if ( v12 )
      {
        v53 = CDrawingContext::PopLayer(v2);
        if ( v53 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x69,
            (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
            (const char *)(unsigned int)v53,
            v86);
      }
      v54 = CDrawingContext::PopLayer(v2);
      if ( v54 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x48,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)v54,
          v86);
      goto LABEL_15;
    }
    CComposition::GetCursorVisuals(*((_QWORD *)this + 3), &v95);
    v55 = v96;
    v56 = (CExcludeVisualReference *)((char *)v96 + 32 * (_QWORD)v95);
    while ( v55 != v56 )
    {
      VisualNoRef = CExcludeVisualReference::GetVisualNoRef(v55);
      v58 = (CVisualTree *)*((_QWORD *)v55 + 3);
      v93 = (__int64)VisualNoRef;
      RootVisualTree = CVisualTree::GetRootVisualTree(v58);
      v116 = 0;
      WorldTransform = CVisual::GetWorldTransform(v60, RootVisualTree, (struct CMILMatrix *)v115, 0, 0);
      v62 = WorldTransform;
      if ( WorldTransform < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD1,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)WorldTransform,
          v84);
        CDrawingContext::PopRenderOptionsInternal(v2, 1);
        wil::com_ptr_t<CDrawListCache,wil::err_returncode_policy>::~com_ptr_t<CDrawListCache,wil::err_returncode_policy>(&v89);
        CDrawListEntryBuilder::~CDrawListEntryBuilder((CDrawListEntryBuilder *)v120);
        CBrushDrawListGenerator::~CBrushDrawListGenerator((CBrushDrawListGenerator *)v119);
        std::unique_ptr<CShape>::~unique_ptr<CShape>(&v90);
        if ( v19 )
        {
          v69 = CDrawingContext::PopLayer(v2);
          if ( v69 < 0 )
            wil::details::in1diag3::FailFast_Hr(
              retaddr,
              (void *)0x83,
              (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
              (const char *)(unsigned int)v69,
              v88);
        }
        if ( v12 )
        {
          v70 = CDrawingContext::PopLayer(v2);
          if ( v70 < 0 )
            wil::details::in1diag3::FailFast_Hr(
              retaddr,
              (void *)0x69,
              (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
              (const char *)(unsigned int)v70,
              v88);
        }
        v71 = CDrawingContext::PopLayer(v2);
        if ( v71 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x48,
            (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
            (const char *)(unsigned int)v71,
            v88);
        goto LABEL_94;
      }
      v99 = v115[0];
      *(_OWORD *)v100 = v115[1];
      *(_OWORD *)&v100[16] = v115[2];
      *(_OWORD *)&v100[32] = v115[3];
      *(_DWORD *)&v100[48] = v116;
      CMILMatrix::Multiply((CMILMatrix *)&v99, (const struct CMILMatrix *)v111);
      Bounds = CVisual::GetBounds(v93, v58);
      v117 = *(_OWORD *)Bounds;
      v118 = *(_QWORD *)(Bounds + 16);
      v65 = CDrawingContext::DrawSubVisualTree(v2, v64, &v117, &v99);
      v62 = v65;
      if ( v65 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD9,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
          (const char *)(unsigned int)v65,
          v84);
        CDrawingContext::PopRenderOptionsInternal(v2, 1);
        wil::com_ptr_t<CDrawListCache,wil::err_returncode_policy>::~com_ptr_t<CDrawListCache,wil::err_returncode_policy>(&v89);
        CDrawListEntryBuilder::~CDrawListEntryBuilder((CDrawListEntryBuilder *)v120);
        CBrushDrawListGenerator::~CBrushDrawListGenerator((CBrushDrawListGenerator *)v119);
        std::unique_ptr<CShape>::~unique_ptr<CShape>(&v90);
        if ( v19 )
        {
          v66 = CDrawingContext::PopLayer(v2);
          if ( v66 < 0 )
            wil::details::in1diag3::FailFast_Hr(
              retaddr,
              (void *)0x83,
              (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
              (const char *)(unsigned int)v66,
              v87);
        }
        if ( v12 )
        {
          v67 = CDrawingContext::PopLayer(v2);
          if ( v67 < 0 )
            wil::details::in1diag3::FailFast_Hr(
              retaddr,
              (void *)0x69,
              (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
              (const char *)(unsigned int)v67,
              v87);
        }
        v68 = CDrawingContext::PopLayer(v2);
        if ( v68 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x48,
            (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
            (const char *)(unsigned int)v68,
            v87);
LABEL_94:
        v11 = v62;
        goto LABEL_106;
      }
      v55 = (CExcludeVisualReference *)((char *)v55 + 32);
    }
    CDrawingContext::PopRenderOptionsInternal(v2, 1);
    v6 = v106;
  }
  wil::com_ptr_t<CDrawListCache,wil::err_returncode_policy>::~com_ptr_t<CDrawListCache,wil::err_returncode_policy>(&v89);
  CDrawListEntryBuilder::~CDrawListEntryBuilder((CDrawListEntryBuilder *)v120);
  CBrushDrawListGenerator::~CBrushDrawListGenerator((CBrushDrawListGenerator *)v119);
  std::unique_ptr<CShape>::~unique_ptr<CShape>(&v90);
  if ( v19 )
  {
    v72 = CDrawingContext::PopLayer(v2);
    if ( v72 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
        (const char *)(unsigned int)v72,
        v84);
  }
  if ( v12 )
  {
    v73 = CDrawingContext::PopLayer(v2);
    if ( v73 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
        (const char *)(unsigned int)v73,
        v84);
  }
  v74 = CDrawingContext::PopLayer(v2);
  if ( v74 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
      (const char *)(unsigned int)v74,
      v84);
  v94 = 0;
  CDrawListBitmap::CDrawListBitmap(
    (CDrawListBitmap *)v110,
    (struct IBitmapRealization *)((v98 + 8) & ((unsigned __int128)-(__int128)v98 >> 64)));
  v96 = (CExcludeVisualReference *)__PAIR64__(LODWORD(height), LODWORD(width));
  v107 = &v94;
  v110[16] = 1;
  v108 = 0;
  v109 = 1;
  v95 = 0;
  v91 = 256;
  v92 = 1;
  v11 = CSurfaceDrawListBrush::CreateWithContentRect(v110, &v91, &v95, &v108);
  wil::details::out_param_t<std::unique_ptr<CSurfaceDrawListBrush>>::~out_param_t<std::unique_ptr<CSurfaceDrawListBrush>>(&v107);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\compositionmagnifierbrush.cpp",
      (const char *)(unsigned int)v11,
      v84);
    CDrawListBitmap::~CDrawListBitmap((CDrawListBitmap *)v110);
    std::unique_ptr<CSurfaceDrawListBrush>::~unique_ptr<CSurfaceDrawListBrush>(&v94);
    goto LABEL_106;
  }
  v76 = v94;
  *(_QWORD *)(v94 + 120) = 0;
  *(FLOAT *)(v76 + 128) = width;
  *(FLOAT *)(v76 + 132) = height;
  CBrushDrawListGenerator::Reset(v6);
  v93 = v94;
  v94 = 0;
  CBrushDrawListGenerator::AttachInput(v6, 0, &v93);
  std::unique_ptr<CShape>::~unique_ptr<CShape>(&v93);
  CDrawListBitmap::~CDrawListBitmap((CDrawListBitmap *)v110);
  std::unique_ptr<CSurfaceDrawListBrush>::~unique_ptr<CSurfaceDrawListBrush>(&v94);
  wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v98);
  return 0;
}

```

## disassembly

```asm
0x1801ff624  mov     [rsp-8+arg_10], rbx
0x1801ff629  push    rbp
0x1801ff62a  push    rsi
0x1801ff62b  push    rdi
0x1801ff62c  push    r12
0x1801ff62e  push    r13
0x1801ff630  push    r14
0x1801ff632  push    r15
0x1801ff634  lea     rbp, [rsp-13A0h]
0x1801ff63c  mov     eax, 14A0h
0x1801ff641  call    _alloca_probe
0x1801ff646  sub     rsp, rax
0x1801ff649  movaps  [rsp+14D0h+var_40], xmm6
0x1801ff651  movaps  [rsp+14D0h+var_50], xmm7
0x1801ff659  movaps  [rsp+14D0h+var_60], xmm8
0x1801ff662  movaps  [rsp+14D0h+var_70], xmm9
0x1801ff66b  movaps  [rsp+14D0h+var_80], xmm10
0x1801ff674  movaps  [rsp+14D0h+var_90], xmm11
0x1801ff67d  mov     rax, cs:__security_cookie
0x1801ff684  xor     rax, rsp
0x1801ff687  mov     [rbp+13D0h+var_A0], rax
0x1801ff68e  mov     rdi, [rdx]
0x1801ff691  mov     rbx, rcx
0x1801ff694  movsd   xmm0, qword ptr [rdx+2Ch]
0x1801ff699  xor     r15d, r15d
0x1801ff69c  mov     rcx, rdi; this
0x1801ff69f  mov     [rbp+13D0h+var_13D8], rdx
0x1801ff6a3  mov     r12, rdx
0x1801ff6a6  mov     [rsp+14D0h+var_1458], r15
0x1801ff6ab  movsd   qword ptr [rsp+14D0h+var_14A0.width], xmm0
0x1801ff6b1  call    ?GetCurrentVisual@CDrawingContext@@QEBAPEAVCVisual@@XZ; CDrawingContext::GetCurrentVisual(void)
0x1801ff6b6  lea     rcx, [rsp+14D0h+var_1458]
0x1801ff6bb  mov     r13, rax
0x1801ff6be  call    ?reset@?$com_ptr_t@UIDXGISwapChain1@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(void)
0x1801ff6c3  mov     rcx, [rdi+10h]
0x1801ff6c7  mov     rax, [rcx+10h]
0x1801ff6cb  lea     rcx, [rdi+10h]
0x1801ff6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff6d4  lea     rcx, aDwmMagnifierBr; "DWM Magnifier Brush Resample Surface"
0x1801ff6db  mov     dword ptr [rsp+14D0h+var_1468], 24h ; '$'
0x1801ff6e3  mov     [rsp+14D0h+var_1470], rcx
0x1801ff6e8  lea     r8, [rsp+14D0h+var_14A0]
0x1801ff6ed  lea     rcx, [rsp+14D0h+var_1458]
0x1801ff6f2  mov     r9d, [rax+8]
0x1801ff6f6  lea     rdx, [rsp+14D0h+var_1470]
0x1801ff6fb  mov     [rsp+14D0h+var_14A8], rcx
0x1801ff700  mov     rcx, rdi
0x1801ff703  mov     dword ptr [rsp+14D0h+var_14B0], 3; int
0x1801ff70b  call    ?PushOffScreenRenderingLayer@CDrawingContext@@QEAAJAEBVCResourceTag@@AEBUD2D_SIZE_F@@VDisplayId@@W4Enum@CacheMode@@PEAPEAVIRenderTargetBitmap@@@Z; CDrawingContext::PushOffScreenRenderingLayer(CResourceTag const &,D2D_SIZE_F const &,DisplayId,CacheMode::Enum,IRenderTargetBitmap * *)
0x1801ff710  mov     esi, eax
0x1801ff712  test    eax, eax
0x1801ff714  jns     short loc_1801FF735
0x1801ff716  mov     rcx, [rbp+13D8h]; this
0x1801ff71d  lea     r8, aOnecoreuapWind_122; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x1801ff724  mov     r9d, eax; char *
0x1801ff727  lea     edx, [r15+45h]; void *
0x1801ff72b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ff730  jmp     loc_18020039E
0x1801ff735  mov     sil, [rbx+6Ch]
0x1801ff739  mov     r14d, 1
0x1801ff73f  movss   xmm6, [rsp+14D0h+var_14A0.height]
0x1801ff745  movss   xmm7, [rsp+14D0h+var_14A0.width]
0x1801ff74b  test    sil, sil
0x1801ff74e  jz      loc_1801FF80D
0x1801ff754  movss   xmm0, dword ptr [rbx+68h]
0x1801ff759  mov     edx, r14d
0x1801ff75c  movss   dword ptr [rbp+13D0h+var_13E0], xmm0
0x1801ff761  movaps  xmm0, xmm7
0x1801ff764  mov     byte ptr [rbp+13D0h+var_13E0+4], r14b
0x1801ff768  mov     dword ptr [rsp+14D0h+var_1480], 3F800000h
0x1801ff770  mov     dword ptr [rsp+14D0h+var_1480+4], 3F800000h
0x1801ff778  mov     [rsp+14D0h+var_1470], r15
0x1801ff77d  call    ?PixelAlign@@YAHMW4Enum@PixelAlignMode@@@Z; PixelAlign(float,PixelAlignMode::Enum)
0x1801ff782  mov     edx, r14d
0x1801ff785  mov     dword ptr [rsp+14D0h+var_1468], eax
0x1801ff789  movaps  xmm0, xmm6
0x1801ff78c  call    ?PixelAlign@@YAHMW4Enum@PixelAlignMode@@@Z; PixelAlign(float,PixelAlignMode::Enum)
0x1801ff791  mov     dword ptr [rsp+14D0h+var_1468+4], eax
0x1801ff795  lea     r9, [rsp+14D0h+var_1470]
0x1801ff79a  lea     rax, [rbp+13D0h+var_13E0]
0x1801ff79e  mov     rdx, r13; struct CVisual *
0x1801ff7a1  mov     [rsp+14D0h+var_14A8], rax; __int64
0x1801ff7a6  lea     r8d, [r14+1]
0x1801ff7aa  lea     rax, [rsp+14D0h+var_1480]
0x1801ff7af  mov     rcx, rdi; this
0x1801ff7b2  mov     [rsp+14D0h+var_14B0], rax; int
0x1801ff7b7  call    ?PushResampleLayer@CDrawingContext@@AEAAJPEBVCVisual@@W4Enum@CompositionResampleMode@@AEBUD2D_POINTANDSIZE_L@@AEBUD2D_SIZE_F@@AEBV?$optional@M@std@@@Z; CDrawingContext::PushResampleLayer(CVisual const *,CompositionResampleMode::Enum,D2D_POINTANDSIZE_L const &,D2D_SIZE_F const &,std::optional<float> const &)
0x1801ff7bc  mov     r14d, eax
0x1801ff7bf  test    eax, eax
0x1801ff7c1  jns     short loc_1801FF80D
0x1801ff7c3  mov     rcx, [rbp+13D8h]; this
0x1801ff7ca  lea     rbx, aOnecoreuapWind_122; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x1801ff7d1  mov     r8, rbx; unsigned int
0x1801ff7d4  mov     r9d, eax; char *
0x1801ff7d7  mov     edx, 63h ; 'c'; void *
0x1801ff7dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ff7e1  mov     rcx, rdi; this
0x1801ff7e4  call    ?PopLayer@CDrawingContext@@QEAAJXZ; CDrawingContext::PopLayer(void)
0x1801ff7e9  test    eax, eax
0x1801ff7eb  jns     short loc_1801FF805
0x1801ff7ed  mov     rcx, [rbp+13D8h]; this
0x1801ff7f4  mov     r9d, eax; char *
0x1801ff7f7  mov     r8, rbx; unsigned int
0x1801ff7fa  mov     edx, 48h ; 'H'; void *
0x1801ff7ff  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1801ff805  mov     esi, r14d
0x1801ff808  jmp     loc_18020039E
0x1801ff80d  mov     r14b, [rbx+98h]
0x1801ff814  test    r14b, r14b
0x1801ff817  jz      loc_1801FF8EB
0x1801ff81d  mov     rax, [rbx+80h]
0x1801ff824  lea     r8, [rbp+13D0h+var_1450]
0x1801ff828  mov     rcx, rdi; this
0x1801ff82b  mov     dword ptr [rbp+13D0h+var_1440], r15d
0x1801ff82f  mov     [rbp+13D0h+var_142C], r15d
0x1801ff833  mov     [rbp+13D0h+var_1418], r15d
0x1801ff837  movups  xmm0, xmmword ptr [rax]
0x1801ff83a  mov     [rbp+13D0h+var_1404], r15d
0x1801ff83e  mov     [rbp+13D0h+var_13F0], 3F800000h
0x1801ff845  movaps  [rbp+13D0h+var_1450], xmm0
0x1801ff849  movups  xmm0, xmmword ptr [rax+10h]
0x1801ff84d  movups  [rbp+13D0h+var_1440+4], xmm0
0x1801ff851  movups  xmm0, xmmword ptr [rax+20h]
0x1801ff855  movups  [rbp+13D0h+var_1428], xmm0
0x1801ff859  movups  xmm0, xmmword ptr [rax+30h]
0x1801ff85d  movups  [rbp+13D0h+var_1414], xmm0
0x1801ff861  movups  xmm0, xmmword ptr [rax+40h]
0x1801ff865  movaps  [rbp+13D0h+var_1400], xmm0
0x1801ff869  call    ?PushColorTransformLayer@CDrawingContext@@QEAAJPEBV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@AEBUMilColorTransform@@@Z; CDrawingContext::PushColorTransformLayer(TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const *,MilColorTransform const &)
0x1801ff86e  mov     r15d, eax
0x1801ff871  test    eax, eax
0x1801ff873  jns     short loc_1801FF8E8
0x1801ff875  mov     rcx, [rbp+13D8h]; this
0x1801ff87c  lea     rbx, aOnecoreuapWind_122; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x1801ff883  mov     r8, rbx; unsigned int
0x1801ff886  mov     r9d, eax; char *
0x1801ff889  mov     edx, 7Dh ; '}'; void *
0x1801ff88e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ff893  test    sil, sil
0x1801ff896  jz      short loc_1801FF8BC
0x1801ff898  mov     rcx, rdi; this
0x1801ff89b  call    ?PopLayer@CDrawingContext@@QEAAJXZ; CDrawingContext::PopLayer(void)
0x1801ff8a0  test    eax, eax
0x1801ff8a2  jns     short loc_1801FF8BC
0x1801ff8a4  mov     rcx, [rbp+13D8h]; this
0x1801ff8ab  mov     r9d, eax; char *
0x1801ff8ae  mov     r8, rbx; unsigned int
0x1801ff8b1  mov     edx, 69h ; 'i'; void *
0x1801ff8b6  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1801ff8bc  mov     rcx, rdi; this
0x1801ff8bf  call    ?PopLayer@CDrawingContext@@QEAAJXZ; CDrawingContext::PopLayer(void)
0x1801ff8c4  test    eax, eax
0x1801ff8c6  jns     short loc_1801FF8E0
0x1801ff8c8  mov     rcx, [rbp+13D8h]; this
0x1801ff8cf  mov     r9d, eax; char *
0x1801ff8d2  mov     r8, rbx; unsigned int
0x1801ff8d5  mov     edx, 48h ; 'H'; void *
0x1801ff8da  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1801ff8e0  mov     esi, r15d
0x1801ff8e3  jmp     loc_18020039E
0x1801ff8e8  xor     r15d, r15d
0x1801ff8eb  lea     rax, [rsp+14D0h+var_1498]
0x1801ff8f0  mov     [rsp+14D0h+var_1498], r15
0x1801ff8f5  lea     r9, [rsp+14D0h+var_1468]; struct CDrawListBrush **
0x1801ff8fa  mov     [rsp+14D0h+var_1470], rax
0x1801ff8ff  lea     r8, [rsp+14D0h+var_14A0]; struct D2D_SIZE_F *
0x1801ff904  mov     [rsp+14D0h+var_1468], r15
0x1801ff909  mov     rdx, rdi; struct CDrawingContext *
0x1801ff90c  mov     [rsp+14D0h+var_1460], 1
0x1801ff911  mov     rcx, rbx; this
0x1801ff914  call    ?CreateLayoutGeometryDrawListBrush@CBrush@@MEBAJPEAVCDrawingContext@@AEBUD2D_SIZE_F@@PEAPEAVCDrawListBrush@@@Z; CBrush::CreateLayoutGeometryDrawListBrush(CDrawingContext *,D2D_SIZE_F const &,CDrawListBrush * *)
0x1801ff919  lea     rcx, [rsp+14D0h+var_1470]
0x1801ff91e  mov     r15d, eax
0x1801ff921  call    ??1?$out_param_t@V?$unique_ptr@VCDrawListBrush@@U?$default_delete@VCDrawListBrush@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<CDrawListBrush>>::~out_param_t<std::unique_ptr<CDrawListBrush>>(void)
0x1801ff926  test    r15d, r15d
0x1801ff929  jns     loc_1801FF9D1
0x1801ff92f  mov     rcx, [rbp+13D8h]; this
0x1801ff936  lea     rbx, aOnecoreuapWind_122; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x1801ff93d  mov     r8, rbx; unsigned int
0x1801ff940  mov     r9d, r15d; char *
0x1801ff943  mov     edx, 8Bh; void *
0x1801ff948  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ff94d  lea     rcx, [rsp+14D0h+var_1498]
0x1801ff952  call    ??1?$unique_ptr@VCShape@@U?$default_delete@VCShape@@@std@@@std@@QEAA@XZ; std::unique_ptr<CShape>::~unique_ptr<CShape>(void)
0x1801ff957  test    r14b, r14b
0x1801ff95a  jz      short loc_1801FF980
0x1801ff95c  mov     rcx, rdi; this
0x1801ff95f  call    ?PopLayer@CDrawingContext@@QEAAJXZ; CDrawingContext::PopLayer(void)
0x1801ff964  test    eax, eax
0x1801ff966  jns     short loc_1801FF980
0x1801ff968  mov     rcx, [rbp+13D8h]; this
0x1801ff96f  mov     r9d, eax; char *
0x1801ff972  mov     r8, rbx; unsigned int
0x1801ff975  mov     edx, 83h; void *
0x1801ff97a  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1801ff980  test    sil, sil
0x1801ff983  jz      short loc_1801FF9A9
0x1801ff985  mov     rcx, rdi; this
0x1801ff988  call    ?PopLayer@CDrawingContext@@QEAAJXZ; CDrawingContext::PopLayer(void)
0x1801ff98d  test    eax, eax
0x1801ff98f  jns     short loc_1801FF9A9
0x1801ff991  mov     rcx, [rbp+13D8h]; this
0x1801ff998  mov     r9d, eax; char *
0x1801ff99b  mov     r8, rbx; unsigned int
0x1801ff99e  mov     edx, 69h ; 'i'; void *
0x1801ff9a3  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1801ff9a9  mov     rcx, rdi; this
0x1801ff9ac  call    ?PopLayer@CDrawingContext@@QEAAJXZ; CDrawingContext::PopLayer(void)
0x1801ff9b1  test    eax, eax
0x1801ff9b3  jns     loc_1801FF8E0
0x1801ff9b9  mov     rcx, [rbp+13D8h]; this
0x1801ff9c0  mov     r9d, eax; char *
0x1801ff9c3  mov     r8, rbx; unsigned int
0x1801ff9c6  mov     edx, 48h ; 'H'; void *
0x1801ff9cb  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1801ff9d1  lea     r8, [rsp+14D0h+var_14A0]; struct D2D_SIZE_F *
0x1801ff9d6  mov     rdx, rdi; struct CDrawingContext *
0x1801ff9d9  lea     rcx, [rbp+13D0h+var_1280]; this
0x1801ff9e0  call    ??0CBrushDrawListGenerator@@QEAA@PEAVCDrawingContext@@AEBUD2D_SIZE_F@@@Z; CBrushDrawListGenerator::CBrushDrawListGenerator(CDrawingContext *,D2D_SIZE_F const &)
0x1801ff9e5  lea     rdx, [rbp+13D0h+var_1280]; struct CBrushDrawListGenerator *
0x1801ff9ec  mov     rcx, rbx; this
0x1801ff9ef  call    ?GetBVIBrushParameters@CCompositionMagnifierBrush@@AEBAJPEAVCBrushDrawListGenerator@@@Z; CCompositionMagnifierBrush::GetBVIBrushParameters(CBrushDrawListGenerator *)
0x1801ff9f4  mov     r15d, eax
0x1801ff9f7  xor     eax, eax
0x1801ff9f9  test    r15d, r15d
0x1801ff9fc  jns     loc_1801FFAB0
0x1801ffa02  mov     rcx, [rbp+13D8h]; this
0x1801ffa09  lea     rbx, aOnecoreuapWind_122; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x1801ffa10  mov     r8, rbx; unsigned int
0x1801ffa13  mov     r9d, r15d; char *
0x1801ffa16  mov     edx, 91h; void *
0x1801ffa1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ffa20  lea     rcx, [rbp+13D0h+var_1280]; this
0x1801ffa27  call    ??1CBrushDrawListGenerator@@QEAA@XZ; CBrushDrawListGenerator::~CBrushDrawListGenerator(void)
0x1801ffa2c  lea     rcx, [rsp+14D0h+var_1498]
0x1801ffa31  call    ??1?$unique_ptr@VCShape@@U?$default_delete@VCShape@@@std@@@std@@QEAA@XZ; std::unique_ptr<CShape>::~unique_ptr<CShape>(void)
0x1801ffa36  test    r14b, r14b
0x1801ffa39  jz      short loc_1801FFA5F
0x1801ffa3b  mov     rcx, rdi; this
0x1801ffa3e  call    ?PopLayer@CDrawingContext@@QEAAJXZ; CDrawingContext::PopLayer(void)
0x1801ffa43  test    eax, eax
0x1801ffa45  jns     short loc_1801FFA5F
0x1801ffa47  mov     rcx, [rbp+13D8h]; this
0x1801ffa4e  mov     r9d, eax; char *
0x1801ffa51  mov     r8, rbx; unsigned int
0x1801ffa54  mov     edx, 83h; void *
0x1801ffa59  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1801ffa5f  test    sil, sil
0x1801ffa62  jz      short loc_1801FFA88
0x1801ffa64  mov     rcx, rdi; this
0x1801ffa67  call    ?PopLayer@CDrawingContext@@QEAAJXZ; CDrawingContext::PopLayer(void)
0x1801ffa6c  test    eax, eax
0x1801ffa6e  jns     short loc_1801FFA88
0x1801ffa70  mov     rcx, [rbp+13D8h]; this
0x1801ffa77  mov     r9d, eax; char *
0x1801ffa7a  mov     r8, rbx; unsigned int
0x1801ffa7d  mov     edx, 69h ; 'i'; void *
0x1801ffa82  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1801ffa88  mov     rcx, rdi; this
0x1801ffa8b  call    ?PopLayer@CDrawingContext@@QEAAJXZ; CDrawingContext::PopLayer(void)
0x1801ffa90  test    eax, eax
0x1801ffa92  jns     loc_1801FF8E0
0x1801ffa98  mov     rcx, [rbp+13D8h]; this
0x1801ffa9f  mov     r9d, eax; char *
0x1801ffaa2  mov     r8, rbx; unsigned int
0x1801ffaa5  mov     edx, 48h ; 'H'; void *
0x1801ffaaa  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1801ffab0  mov     qword ptr [rbp+13D0h+var_1450+8], rax
0x1801ffab4  lea     rcx, [rbp+13D0h+var_1230]; this
0x1801ffabb  mov     dword ptr [rbp+13D0h+var_1440], eax
0x1801ffabe  mov     byte ptr [rbp+13D0h+var_13F0], al
0x1801ffac1  mov     rax, [rsp+14D0h+var_1498]
0x1801ffac6  mov     qword ptr [rbp+13D0h+var_1450], rax
0x1801ffaca  mov     dword ptr [rbp+13D0h+var_1400+0Ch], 101h
0x1801ffad1  call    ??0CDrawListEntryBuilder@@QEAA@XZ; CDrawListEntryBuilder::CDrawListEntryBuilder(void)
0x1801ffad6  lea     r8, [rbp+13D0h+var_1230]; struct CDrawListEntryBuilder *
0x1801ffadd  lea     rdx, [rbp+13D0h+var_1450]; struct CBrushDrawListGenerator::GenerateDrawListProperties *
0x1801ffae1  lea     rcx, [rbp+13D0h+var_1280]; this
0x1801ffae8  call    ?GenerateDrawList@CBrushDrawListGenerator@@QEAAJAEBUGenerateDrawListProperties@1@PEAVCDrawListEntryBuilder@@@Z; CBrushDrawListGenerator::GenerateDrawList(CBrushDrawListGenerator::GenerateDrawListProperties const &,CDrawListEntryBuilder *)
0x1801ffaed  mov     r15d, eax
0x1801ffaf0  test    eax, eax
0x1801ffaf2  jns     loc_1801FFBB2
0x1801ffaf8  mov     rcx, [rbp+13D8h]; this
0x1801ffaff  lea     rbx, aOnecoreuapWind_122; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x1801ffb06  mov     r8, rbx; unsigned int
0x1801ffb09  mov     r9d, eax; char *
0x1801ffb0c  mov     edx, 98h; void *
0x1801ffb11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ffb16  lea     rcx, [rbp+13D0h+var_1230]; this
0x1801ffb1d  call    ??1CDrawListEntryBuilder@@QEAA@XZ; CDrawListEntryBuilder::~CDrawListEntryBuilder(void)
0x1801ffb22  lea     rcx, [rbp+13D0h+var_1280]; this
0x1801ffb29  call    ??1CBrushDrawListGenerator@@QEAA@XZ; CBrushDrawListGenerator::~CBrushDrawListGenerator(void)
0x1801ffb2e  lea     rcx, [rsp+14D0h+var_1498]
0x1801ffb33  call    ??1?$unique_ptr@VCShape@@U?$default_delete@VCShape@@@std@@@std@@QEAA@XZ; std::unique_ptr<CShape>::~unique_ptr<CShape>(void)
0x1801ffb38  test    r14b, r14b
0x1801ffb3b  jz      short loc_1801FFB61
0x1801ffb3d  mov     rcx, rdi; this
0x1801ffb40  call    ?PopLayer@CDrawingContext@@QEAAJXZ; CDrawingContext::PopLayer(void)
0x1801ffb45  test    eax, eax
0x1801ffb47  jns     short loc_1801FFB61
  ... truncated ...
```
