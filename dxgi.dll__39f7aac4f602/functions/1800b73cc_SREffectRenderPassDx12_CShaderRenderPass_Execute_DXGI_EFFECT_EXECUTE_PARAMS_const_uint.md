# SREffectRenderPassDx12::CShaderRenderPass::Execute(DXGI_EFFECT_EXECUTE_PARAMS const *,uint)

- ea: `0x1800b73cc`
- end: `0x1800b91fb`
- name: `?Execute@CShaderRenderPass@SREffectRenderPassDx12@@QEAAJPEBUDXGI_EFFECT_EXECUTE_PARAMS@@I@Z`
- size: `7727`
- prototype: `__int64 __fastcall(SREffectRenderPassDx12::CShaderRenderPass *__hidden this, const struct DXGI_EFFECT_EXECUTE_PARAMS *, unsigned int)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800b7360`

## callees

- `0x18000c6b0`
- `0x180014750`
- `0x1800306f4`
- `0x18004f810`
- `0x1800542bc`
- `0x180067d2c`
- `0x18006909c`
- `0x18006989c`
- `0x180075fa0`
- `0x180076f20`
- `0x180088468`
- `0x180091e70`
- `0x1800b5b70`
- `0x1800b68d0`
- `0x1800b7220`
- `0x1800b73cc`
- `0x1800b9204`
- `0x1800b949c`
- `0x1800b99d0`
- `0x1800b9a30`
- `0x1800b9a90`
- `0x1800ba6d8`
- `0x1800bc3ac`
- `0x1800bc4a8`
- `0x1800bca48`
- `0x1800bcb54`
- `0x1800bcc60`
- `0x1800bd144`
- `0x1800bd1e8`
- `0x1800bd2a0`
- `0x1800cb010`

## string_xrefs

- `0x1800b7466`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b74cf`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b752e`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b7582`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b77be`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b78b2`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b7d1c`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b8321`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b8381`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b85ec`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b91b9`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b84cc`: `Frame capture - copying target (0, 0, %d, %d) HR frame`
- `0x1800b873a`: `  CopyToInput 0x%p -> 0x%p`
- `0x1800b8489`: `Frame capture - copying src (0, 0, %d, %d) LR frame`
- `0x1800b8ff6`: `Frame capture - copying src (0, 0, %d, %d) LR frame`
- `0x1800b8c38`: `  CopyToOutput 0x%p -> 0x%p`
- `0x1800b8c85`: `  SS L copy 0x%p -> 0x%p`
- `0x1800b8cf0`: `  SS R copy 0x%p -> 0x%p`
- `0x1800b9150`: `Info: failed to write frame to disk`

## pseudocode

```c
__int64 __fastcall SREffectRenderPassDx12::CShaderRenderPass::Execute(
        SREffectRenderPassDx12::CShaderRenderPass *this,
        const struct DXGI_EFFECT_EXECUTE_PARAMS *a2,
        unsigned int a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // esi
  __int64 (__fastcall ***v7)(_QWORD, GUID *, struct ID3D12CommandQueue **); // rcx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // r14d
  char v12; // di
  char v13; // al
  bool v14; // dl
  UINT64 Width_low; // rcx
  UINT bottom; // eax
  unsigned int v17; // r12d
  int InputResNoRef; // eax
  __int64 v19; // rdx
  __int64 v20; // r9
  struct ID3D12GraphicsCommandList *v21; // r15
  char v22; // bl
  char v23; // bl
  int v24; // eax
  int v25; // eax
  int v26; // esi
  int v27; // r14d
  int v28; // r15d
  unsigned int v29; // r14d
  __int64 v30; // r8
  struct DDSData *CurrentOverlay; // rsi
  bool v32; // zf
  __int64 v33; // rcx
  struct ID3D12Resource *v34; // r14
  struct ID3D12Resource *v35; // rbx
  CModule *v36; // rcx
  bool v37; // r9
  int v38; // r12d
  int v39; // r15d
  __int64 v40; // r14
  int v41; // esi
  int v42; // ebx
  __int64 v43; // rax
  struct ID3D12DescriptorHeap *v44; // r12
  _QWORD *v45; // rax
  char IsEnabled; // al
  SREffectRenderPassDx12::CShaderResourceBuilder *v47; // rbx
  const struct DDSData *v48; // rax
  char *v49; // rbx
  struct ID3D12Resource *v50; // rsi
  _DWORD *v51; // r8
  struct ID3D12Resource *v52; // rdx
  D3D12_GPU_DESCRIPTOR_HANDLE (__stdcall *GetGPUDescriptorHandleForHeapStart)(ID3D12DescriptorHeap *); // rax
  _QWORD *v54; // rax
  __int64 v55; // rbx
  __int64 v56; // r8
  __int64 v57; // rdx
  _QWORD *v58; // rax
  __int64 v59; // rbx
  struct tagRECT v60; // xmm6
  char v61; // bl
  unsigned int v62; // r12d
  unsigned int v63; // r14d
  struct ID3D12Resource *v64; // r12
  D3D12_RESOURCE_DESC (__stdcall *GetDesc)(ID3D12Resource *); // r14
  __int64 v66; // rsi
  D3D12_RESOURCE_DESC (__stdcall *v67)(ID3D12Resource *); // r14
  __int64 v68; // rsi
  LONG v69; // esi
  LONG v70; // r14d
  CModule *v71; // rcx
  unsigned int v72; // r14d
  unsigned int v73; // ebx
  struct ID3D12Resource *v74; // r14
  struct ID3D12Resource *v75; // rbx
  struct ID3D12Resource *v76; // rsi
  struct tagRECT *v77; // r9
  __int64 v78; // rcx
  bool v79; // al
  int v80; // eax
  __int64 v81; // r8
  HRESULT (__stdcall *GetPrivateData)(ID3D12Resource *, const GUID *const, UINT *, void *); // rax
  int v83; // eax
  struct tagRECT *v84; // rsi
  LONG v85; // esi
  char v86; // bl
  unsigned int v87; // r15d
  unsigned int v88; // r14d
  struct ID3D12Resource *v89; // r15
  D3D12_RESOURCE_DESC (__stdcall *v90)(ID3D12Resource *); // r14
  __int64 v91; // rsi
  unsigned int v92; // edx
  unsigned int v93; // r8d
  struct ID3D12Resource *v94; // rsi
  struct ID3D12Resource *v95; // r15
  D3D12_RESOURCE_DESC (__stdcall *v96)(ID3D12Resource *); // r14
  __int64 v97; // rsi
  LONG v98; // r15d
  struct ID3D12GraphicsCommandList *v99; // r14
  struct ID3D12Resource *v100; // rsi
  char v101; // bl
  bool v102; // r9
  int v104; // [rsp+28h] [rbp-E0h]
  int v105; // [rsp+28h] [rbp-E0h]
  char *v106; // [rsp+30h] [rbp-D8h]
  __int64 v107; // [rsp+38h] [rbp-D0h]
  struct ID3D12Resource *v108; // [rsp+58h] [rbp-B0h] BYREF
  struct ID3D12Resource *v109; // [rsp+60h] [rbp-A8h] BYREF
  struct ID3D12CommandQueue *v110; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v111[2]; // [rsp+70h] [rbp-98h] BYREF
  struct ID3D12Resource *v112; // [rsp+78h] [rbp-90h] BYREF
  UINT Height; // [rsp+80h] [rbp-88h] BYREF
  unsigned int v114; // [rsp+84h] [rbp-84h] BYREF
  struct ID3D12CommandQueue *v115; // [rsp+88h] [rbp-80h] BYREF
  struct ID3D12Resource *v116; // [rsp+90h] [rbp-78h]
  unsigned int v117; // [rsp+98h] [rbp-70h]
  struct DDSData *v118; // [rsp+A0h] [rbp-68h]
  struct ID3D12GraphicsCommandList *v119; // [rsp+A8h] [rbp-60h] BYREF
  struct ID3D12DescriptorHeap *v120; // [rsp+B0h] [rbp-58h] BYREF
  const struct DXGI_EFFECT_EXECUTE_PARAMS *v121; // [rsp+B8h] [rbp-50h] BYREF
  UINT64 Width; // [rsp+C0h] [rbp-48h]
  struct ID3D12GraphicsCommandList *v123; // [rsp+C8h] [rbp-40h] BYREF
  const struct DXGI_EFFECT_EXECUTE_PARAMS **v124; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v125; // [rsp+D8h] [rbp-30h] BYREF
  struct ID3D12DescriptorHeap *v126; // [rsp+E0h] [rbp-28h] BYREF
  _DWORD v127[3]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v128; // [rsp+F4h] [rbp-14h]
  int v129; // [rsp+FCh] [rbp-Ch]
  __int128 v130; // [rsp+100h] [rbp-8h]
  _QWORD v131[2]; // [rsp+118h] [rbp+10h] BYREF
  unsigned int v132; // [rsp+128h] [rbp+20h]
  int v133; // [rsp+12Ch] [rbp+24h]
  struct ID3D12Resource *v134; // [rsp+130h] [rbp+28h]
  __int64 v135; // [rsp+138h] [rbp+30h]
  int v136; // [rsp+140h] [rbp+38h]
  int v137; // [rsp+144h] [rbp+3Ch]
  _BYTE v138[144]; // [rsp+148h] [rbp+40h] BYREF
  _QWORD v139[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  int v140; // [rsp+1E8h] [rbp+E0h]
  int v141; // [rsp+1ECh] [rbp+E4h]
  struct ID3D12Resource *v142; // [rsp+1F0h] [rbp+E8h]
  __int64 v143; // [rsp+1F8h] [rbp+F0h]
  unsigned int v144; // [rsp+200h] [rbp+F8h]
  int v145; // [rsp+204h] [rbp+FCh]
  _BYTE v146[144]; // [rsp+208h] [rbp+100h] BYREF
  struct tagRECT v147; // [rsp+298h] [rbp+190h] BYREF
  int v148; // [rsp+2B0h] [rbp+1A8h]
  int v149; // [rsp+2B4h] [rbp+1ACh]
  struct ID3D12Resource *v150[2]; // [rsp+2B8h] [rbp+1B0h] BYREF
  struct tagRECT v151; // [rsp+2C8h] [rbp+1C0h] BYREF
  struct tagRECT v152; // [rsp+2D8h] [rbp+1D0h] BYREF
  char v153; // [rsp+2E8h] [rbp+1E0h]
  float v154[6]; // [rsp+2F0h] [rbp+1E8h] BYREF
  struct D3D12_RESOURCE_DESC v155; // [rsp+308h] [rbp+200h] BYREF
  struct D3D12_RESOURCE_DESC v156; // [rsp+340h] [rbp+238h] BYREF
  _BYTE v157[56]; // [rsp+378h] [rbp+270h] BYREF
  _DWORD v158[3]; // [rsp+3B0h] [rbp+2A8h] BYREF
  __int64 v159; // [rsp+3BCh] [rbp+2B4h]
  int v160; // [rsp+3C4h] [rbp+2BCh]
  __int128 v161; // [rsp+3C8h] [rbp+2C0h]
  _BYTE v162[64]; // [rsp+3E8h] [rbp+2E0h] BYREF
  struct tagRECT v163; // [rsp+428h] [rbp+320h] BYREF
  _BYTE v164[16]; // [rsp+438h] [rbp+330h] BYREF
  unsigned int v165; // [rsp+448h] [rbp+340h]
  unsigned int v166; // [rsp+450h] [rbp+348h] BYREF
  int v167; // [rsp+458h] [rbp+350h]
  _BYTE v168[56]; // [rsp+470h] [rbp+368h] BYREF
  _BYTE v169[64]; // [rsp+4A8h] [rbp+3A0h] BYREF
  struct tagRECT si128; // [rsp+4E8h] [rbp+3E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+550h] [rbp+448h]

  v117 = a3;
  v121 = a2;
  if ( !*(_QWORD *)a2 || !*((_QWORD *)a2 + 2) || !*((_QWORD *)a2 + 4) )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x442,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
      (const char *)0x80070057LL,
      v104);
    return v6;
  }
  v115 = 0;
  v4 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, struct ID3D12CommandQueue **))a2)(
         *(_QWORD *)a2,
         &GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed,
         &v115);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v110 = 0;
    v7 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct ID3D12CommandQueue **))*((_QWORD *)v121 + 1);
    if ( v7 )
    {
      v8 = (**v7)(v7, &GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed, &v110);
      v5 = v8;
      if ( v8 < 0 )
      {
        v6 = -2147467262;
        if ( v8 != -2147467262 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x452,
            (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
            (const char *)(unsigned int)v8,
            v104);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v110);
          goto LABEL_7;
        }
LABEL_11:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v110);
        goto LABEL_248;
      }
    }
    else
    {
      ATL::CComPtr<ID3D12CommandQueue>::operator=(&v110, &v115);
    }
    v109 = 0;
    v9 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct ID3D12Resource **))v121 + 2))(
           *((_QWORD *)v121 + 2),
           &GUID_696442be_a72e_4059_bc79_5b5c98040fad,
           &v109);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45E,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
        (const char *)(unsigned int)v9,
        v104);
LABEL_16:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v109);
      goto LABEL_11;
    }
    v108 = 0;
    v10 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct ID3D12Resource **))v121 + 4))(
            *((_QWORD *)v121 + 4),
            &GUID_696442be_a72e_4059_bc79_5b5c98040fad,
            &v108);
    v6 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x461,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
        (const char *)(unsigned int)v10,
        v104);
LABEL_19:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v108);
      goto LABEL_16;
    }
    v124 = &v121;
    ((void (__fastcall *)(struct ID3D12Resource *, _BYTE *))v109->lpVtbl->GetDesc)(v109, v164);
    ((void (__fastcall *)(struct ID3D12Resource *, struct D3D12_RESOURCE_DESC *))v108->lpVtbl->GetDesc)(v108, &v155);
    v11 = *(&g_AutoSRConfig + 7);
    HIBYTE(v111[0]) = *(&g_AutoSRConfig + 7);
    *(&g_AutoSRConfig + 7) = 0;
    *(_OWORD *)v150 = 0;
    v151 = 0;
    v152 = 0;
    v153 = 0;
    v12 = *(&g_AutoSRConfig + 6);
    if ( !*(&g_AutoSRConfig + 6) || (v13 = 1, *((_DWORD *)this + 48) >= 5u) )
      v13 = 0;
    *(&g_AutoSRConfig + 6) = v13;
    if ( v13 )
      DebugPrint("Execute(): pSource12 0x%p (%d) -> pTarget12 0x%p (%d)", v109, v167, v108, v155.Format);
    *(_QWORD *)&v147.left = 0;
    Width = v155.Width;
    v147.right = v155.Width;
    Height = v155.Height;
    v147.bottom = v155.Height;
    BYTE2(v111[0]) = 1;
    if ( !*(&g_AutoSRConfig + 5) )
    {
      v111[1] = v155.Width;
      v114 = v165;
      GetAspectRatioCorrectDimensions(&v114, &v166, &v111[1], &v155.Height, &v147);
      v14 = RectCoversResource(&v147, &v155, 1);
      BYTE2(v111[0]) = v14;
      if ( v14 )
      {
        Width_low = LODWORD(v155.Width);
        v147.right = v155.Width;
        bottom = v155.Height;
        v147.bottom = v155.Height;
      }
      else
      {
        bottom = v147.bottom;
        Width_low = (unsigned int)v147.right;
      }
      Width = Width_low;
      Height = bottom;
      if ( *(&g_AutoSRConfig + 6) )
        DebugPrint("  AR rect: { %d, %d, %d, %d }", v147.left, v147.top, Width_low, bottom);
      else
        BYTE2(v111[0]) = v14;
    }
    if ( !*(&g_AutoSRConfig + 3)
      || *(&g_AutoSRConfig + 1)
      || (BYTE1(v111[0]) = 1, v155.Layout != D3D12_TEXTURE_LAYOUT_ROW_MAJOR) )
    {
      BYTE1(v111[0]) = 0;
    }
    v17 = DetermineNodeIndexFromCommandQueue(*((struct ID3D12Device4 **)this + 4), v115);
    v114 = v17;
    v119 = 0;
    *(_QWORD *)&si128.left = 0;
    v120 = 0;
    InputResNoRef = SREffectRenderPassDx12::CShaderRenderPass::EnsureRenderResourceForNode(
                      this,
                      v115,
                      &v119,
                      (struct ID3D12DescriptorHeap **)&si128,
                      &v120);
    v6 = InputResNoRef;
    if ( InputResNoRef < 0 )
    {
      v19 = 1206;
LABEL_38:
      v20 = (unsigned int)InputResNoRef;
LABEL_39:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
        (const char *)v20,
        v105);
      *(&g_AutoSRConfig + 6) = v12;
      goto LABEL_19;
    }
    v21 = v119;
    v123 = v119;
    InputResNoRef = SREffectRenderPassDx12::WaitableFence::WaitOnCPU(this, (const unsigned __int64 *)this + 2);
    v6 = InputResNoRef;
    if ( InputResNoRef < 0 )
    {
      v19 = 1217;
      goto LABEL_38;
    }
    v22 = *((_QWORD *)this + 5) == 0;
    LOBYTE(v111[0]) = v22;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
    {
      if ( !*((_QWORD *)this + 5)
        || (v23 = 0,
            (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 56LL))(*((_QWORD *)this + 11))) )
      {
        v23 = 1;
      }
      v22 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 56LL))(*((_QWORD *)this + 11)) | v23;
      LOBYTE(v111[0]) = v22;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl)
      && *((_BYTE *)this + 196)
      && (!v22 || *((_BYTE *)this + 197)) )
    {
      v119 = (struct ID3D12GraphicsCommandList *)v110;
      v24 = ((__int64 (__fastcall *)(struct ID3D12Resource *, __int64 *, __int64, struct ID3D12GraphicsCommandList **))v108->lpVtbl->SetPrivateData)(
              v108,
              DIRECTSR_EXT_QUEUE_TO_SIGNAL,
              8,
              &v119);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4DA,
          (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
          (const char *)(unsigned int)v24,
          v105);
      (*(void (__fastcall **)(_QWORD, struct tagRECT *))(**((_QWORD **)this + 11) + 88LL))(
        *((_QWORD *)this + 11),
        &v147);
      v149 = v11;
      v148 = (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 56LL))(*((_QWORD *)this + 11));
      v25 = ((__int64 (__fastcall *)(struct ID3D12Resource *, __int64 *, __int64, struct tagRECT *))v108->lpVtbl->SetPrivateData)(
              v108,
              DIRECTSR_EXT_CONFIG_GUID,
              32,
              &v147);
      if ( v25 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4E0,
          (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
          (const char *)(unsigned int)v25,
          v105);
      v149 = 0;
      InputResNoRef = SREffectRenderPassDx12::WaitableFence::SignalFence(this, v115);
      v6 = InputResNoRef;
      if ( InputResNoRef < 0 )
      {
        v19 = 1254;
        goto LABEL_38;
      }
      InputResNoRef = SREffectRenderPassDx12::WaitableFence::WaitOnGPU(this, *((struct ID3D12CommandQueue **)this + 6));
      v6 = InputResNoRef;
      if ( InputResNoRef < 0 )
      {
        v19 = 1255;
        goto LABEL_38;
      }
      InputResNoRef = lambda_8eec7823b81d4d24fb4c4eb39c547389_::operator()(&v124, v110);
      v6 = InputResNoRef;
      if ( InputResNoRef < 0 )
      {
        v19 = 1256;
        goto LABEL_38;
      }
      v26 = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, struct D3D12_RESOURCE_DESC *))v109->lpVtbl->GetDesc)(
                          v109,
                          &v156)
                      + 24);
      v27 = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, struct ID3D12Resource **))v109->lpVtbl->GetDesc)(
                          v109,
                          v150)
                      + 16);
      v28 = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, struct D3D12_RESOURCE_DESC *))v108->lpVtbl->GetDesc)(
                          v108,
                          &v156)
                      + 24);
      v114 = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, struct ID3D12Resource **))v108->lpVtbl->GetDesc)(
                           v108,
                           v150)
                       + 16);
      if ( *(&g_AutoSRConfig + 6) )
        DebugPrint("  ExecuteDirect 0x%p -> 0x%p", v109, v108);
      memset_0(v138, 0, sizeof(v138));
      v134 = v109;
      v135 = 0;
      v136 = v27;
      v137 = v26;
      v131[0] = v108;
      v29 = 0;
      v131[1] = 0;
      v132 = v114;
      v133 = v28;
      InputResNoRef = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, _QWORD))(**((_QWORD **)this + 5) + 24LL))(
                        *((_QWORD *)this + 5),
                        v131,
                        v30,
                        0);
      v6 = InputResNoRef;
      if ( InputResNoRef < 0 )
      {
        v19 = 1267;
        goto LABEL_38;
      }
      **((_DWORD **)v121 + 8) = 1;
      v111[1] = 8;
      if ( ((int (__fastcall *)(struct ID3D12Resource *, __int64 *, unsigned int *, struct ID3D12GraphicsCommandList **))v108->lpVtbl->GetPrivateData)(
             v108,
             DIRECTSR_EXT_QUEUE_TO_SIGNAL,
             &v111[1],
             &v119) >= 0
        && (v111[1] != 8 || v119) )
      {
        InputResNoRef = SREffectRenderPassDx12::WaitableFence::SignalFence(
                          this,
                          *((struct ID3D12CommandQueue **)this + 6));
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1276;
          goto LABEL_38;
        }
        InputResNoRef = SREffectRenderPassDx12::WaitableFence::WaitOnGPU(this, v110);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1277;
          goto LABEL_38;
        }
      }
      InputResNoRef = SREffectRenderPassDx12::WaitableFence::SignalFence(this, v110);
      v6 = InputResNoRef;
      if ( InputResNoRef < 0 )
      {
        v19 = 1279;
        goto LABEL_38;
      }
LABEL_247:
      ++*((_DWORD *)this + 48);
      *(&g_AutoSRConfig + 6) = v12;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v108);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v109);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v110);
      v6 = v29;
      goto LABEL_248;
    }
    InputResNoRef = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 64LL))(*((_QWORD *)this + 12));
    v6 = InputResNoRef;
    if ( InputResNoRef < 0 )
    {
      v19 = 1288;
      goto LABEL_38;
    }
    CurrentOverlay = 0;
    v118 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl'::`2'::impl)
      && g_AutoSRConfig )
    {
      CurrentOverlay = SREffectRenderPassDx12::CShaderRenderPass::GetCurrentOverlay(this);
      v118 = CurrentOverlay;
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
    {
      InputResNoRef = ((__int64 (__fastcall *)(struct ID3D12GraphicsCommandList *, _QWORD, _QWORD))v21->lpVtbl->Reset)(
                        v21,
                        *((_QWORD *)this + 12),
                        *(_QWORD *)(*((_QWORD *)this + 7) + 8LL));
      v6 = InputResNoRef;
      if ( InputResNoRef < 0 )
      {
        v19 = 1321;
        goto LABEL_38;
      }
      goto LABEL_91;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl'::`2'::impl) )
    {
      if ( !g_AutoSRConfig )
        goto LABEL_85;
      v32 = CurrentOverlay == 0;
    }
    else
    {
      v32 = g_AutoSRConfig == 0;
    }
    if ( !v32 )
    {
LABEL_86:
      v33 = 1;
LABEL_87:
      InputResNoRef = ((__int64 (__fastcall *)(struct ID3D12GraphicsCommandList *, _QWORD, _QWORD))v21->lpVtbl->Reset)(
                        v21,
                        *((_QWORD *)this + 12),
                        *(_QWORD *)(*((_QWORD *)this + 7) + 8 * v33 + 8));
      v6 = InputResNoRef;
      if ( InputResNoRef < 0 )
      {
        v19 = 1317;
        goto LABEL_38;
      }
LABEL_91:
      ((void (__fastcall *)(struct ID3D12GraphicsCommandList *, _QWORD))v21->lpVtbl->SetGraphicsRootSignature)(
        v21,
        **((_QWORD **)this + 7));
      v34 = v108;
      v116 = v108;
      *((_DWORD *)this + 50) = 1;
      if ( !v22 )
      {
        *((_DWORD *)this + 50) = 2;
        v112 = 0;
        InputResNoRef = SREffectRenderPassDx12::CShaderResourceBuilder::GetInputResNoRef(
                          *((SREffectRenderPassDx12::CShaderResourceBuilder **)this + 9),
                          v17,
                          v117,
                          &v112);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1345;
          goto LABEL_38;
        }
        v35 = v112;
        if ( (*(_BYTE *)(((__int64 (__fastcall *)(struct ID3D12Resource *, struct D3D12_RESOURCE_DESC *))v112->lpVtbl->GetDesc)(
                           v112,
                           &v156)
                       + 48)
            & 1) != 0 )
        {
          v34 = v35;
          v116 = v35;
          *((_DWORD *)this + 50) = BYTE1(v111[0]) + 3;
        }
      }
      if ( (*(_BYTE *)(((__int64 (__fastcall *)(struct ID3D12Resource *, struct D3D12_RESOURCE_DESC *))v34->lpVtbl->GetDesc)(
                         v34,
                         &v156)
                     + 48)
          & 1) == 0 )
      {
        CModule::RecordJournalImpl(v36, 0, "Shader passthrough not supported on cross-adapter targets", v37);
        v6 = -2147418113;
        v20 = 2147549183LL;
        v19 = 1364;
        goto LABEL_39;
      }
      if ( v34 == v108 )
      {
        InputResNoRef = lambda_8eec7823b81d4d24fb4c4eb39c547389_::operator()(&v124, v115);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1370;
          goto LABEL_38;
        }
      }
      if ( *(&g_AutoSRConfig + 6) )
      {
        v38 = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, struct D3D12_RESOURCE_DESC *))v34->lpVtbl->GetDesc)(
                            v34,
                            &v156)
                        + 32);
        v39 = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _DWORD *))v34->lpVtbl->GetDesc)(v34, v158)
                        + 24);
        v40 = *(_QWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v34->lpVtbl->GetDesc)(v34, v169)
                        + 16);
        v41 = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v109->lpVtbl->GetDesc)(v109, v168)
                        + 32);
        v42 = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v109->lpVtbl->GetDesc)(v109, v157)
                        + 24);
        v43 = ((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v109->lpVtbl->GetDesc)(v109, v162);
        v107 = v40;
        v34 = v116;
        DebugPrint(
          "  Shader pass SRC 0x%p %lldx%d (%d) -> DST 0x%p %lldx%d (%d)",
          v109,
          *(_QWORD *)(v43 + 16),
          v42,
          v41,
          v116,
          v107,
          v39,
          v38);
        v21 = v119;
      }
      ResourceBarrier(v21, v109, D3D12_RESOURCE_STATE_COMMON, D3D12_RESOURCE_STATE_PIXEL_SHADER_RESOURCE);
      ResourceBarrier(v21, v34, D3D12_RESOURCE_STATE_COMMON, D3D12_RESOURCE_STATE_RENDER_TARGET);
      v128 = 0;
      v130 = 0;
      v127[2] = 5768;
      v127[0] = v167;
      v127[1] = 4;
      v129 = 1;
      v44 = v120;
      v45 = (_QWORD *)((__int64 (__fastcall *)(struct ID3D12DescriptorHeap *, struct ID3D12Resource **))v120->lpVtbl->GetCPUDescriptorHandleForHeapStart)(
                        v120,
                        &v112);
      (*(void (__fastcall **)(_QWORD, struct ID3D12Resource *, _DWORD *, _QWORD))(**((_QWORD **)this + 4) + 144LL))(
        *((_QWORD *)this + 4),
        v109,
        v127,
        *v45);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_OverlayIndicator>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_OverlayIndicator>::GetImpl'::`2'::impl) )
      {
        v111[1] = *((_DWORD *)this + 47);
        v120 = *(struct ID3D12DescriptorHeap **)((__int64 (__fastcall *)(struct ID3D12DescriptorHeap *, struct ID3D12Resource **))v44->lpVtbl->GetCPUDescriptorHandleForHeapStart)(
                                                  v44,
                                                  &v112);
        v112 = 0;
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl'::`2'::impl);
        v47 = (SREffectRenderPassDx12::CShaderResourceBuilder *)*((_QWORD *)this + 9);
        if ( IsEnabled )
        {
          InputResNoRef = SREffectRenderPassDx12::CShaderResourceBuilder::GetOverlayResNoRef(
                            *((SREffectRenderPassDx12::CShaderResourceBuilder **)this + 9),
                            v118,
                            v21,
                            &v112);
          v6 = InputResNoRef;
          if ( InputResNoRef < 0 )
          {
            v19 = 1404;
            goto LABEL_38;
          }
        }
        else
        {
          v48 = SREffectRenderPassDx12::CShaderRenderPass::GetCurrentOverlay(this);
          InputResNoRef = SREffectRenderPassDx12::CShaderResourceBuilder::GetOverlayResNoRef(v47, v48, v21, &v112);
          v6 = InputResNoRef;
          if ( InputResNoRef < 0 )
          {
            v19 = 1408;
            goto LABEL_38;
          }
        }
        v49 = (char *)v120 + 2 * v111[1];
        v50 = v112;
        if ( v112 )
        {
          ((void (__fastcall *)(struct ID3D12Resource *, struct D3D12_RESOURCE_DESC *))v112->lpVtbl->GetDesc)(
            v112,
            &v156);
          v159 = 0;
          v161 = 0;
          v158[2] = 5768;
          v158[0] = v156.Format;
          v158[1] = 4;
          v160 = 1;
          v51 = v158;
          v52 = v50;
        }
        else
        {
          v51 = 0;
          v52 = 0;
        }
        (*(void (__fastcall **)(_QWORD, struct ID3D12Resource *, _DWORD *, char *))(**((_QWORD **)this + 4) + 144LL))(
          *((_QWORD *)this + 4),
          v52,
          v51,
          v49);
      }
      v126 = v44;
      ((void (__fastcall *)(struct ID3D12GraphicsCommandList *, __int64, struct ID3D12DescriptorHeap **))v21->lpVtbl->SetDescriptorHeaps)(
        v21,
        1,
        &v126);
      v32 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_OverlayIndicator>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_OverlayIndicator>::GetImpl'::`2'::impl) == 0;
      GetGPUDescriptorHandleForHeapStart = v44->lpVtbl->GetGPUDescriptorHandleForHeapStart;
      if ( v32 )
      {
        v58 = (_QWORD *)((__int64 (__fastcall *)(struct ID3D12DescriptorHeap *, struct ID3D12Resource **))GetGPUDescriptorHandleForHeapStart)(
                          v44,
                          &v112);
        v59 = *v58;
        ((void (__fastcall *)(struct ID3D12GraphicsCommandList *, _QWORD, _QWORD))v21->lpVtbl->SetGraphicsRootDescriptorTable)(
          v21,
          0,
          *v58);
        v56 = v59 + *((unsigned int *)this + 47);
        v57 = 1;
      }
      else
      {
        v54 = (_QWORD *)((__int64 (__fastcall *)(struct ID3D12DescriptorHeap *, struct ID3D12Resource **))GetGPUDescriptorHandleForHeapStart)(
                          v44,
                          &v112);
        v55 = *v54;
        ((void (__fastcall *)(struct ID3D12GraphicsCommandList *, _QWORD, _QWORD))v21->lpVtbl->SetGraphicsRootDescriptorTable)(
          v21,
          0,
          *v54);
        ((void (__fastcall *)(struct ID3D12GraphicsCommandList *, __int64, __int64))v21->lpVtbl->SetGraphicsRootDescriptorTable)(
          v21,
          1,
          v55 + *((unsigned int *)this + 47));
        v56 = v55 + 2LL * *((unsigned int *)this + 47);
        v57 = 2;
      }
      ((void (__fastcall *)(struct ID3D12GraphicsCommandList *, __int64, __int64))v21->lpVtbl->SetGraphicsRootDescriptorTable)(
        v21,
        v57,
        v56);
      v154[0] = (float)v147.left;
      v154[1] = (float)v147.top;
      v154[2] = (float)((int)Width - v147.left);
      v154[3] = (float)(int)(Height - v147.top);
      v154[4] = 0.0;
      v154[5] = 1.0;
      v60 = v147;
      v163 = v147;
      ((void (__fastcall *)(struct ID3D12GraphicsCommandList *, __int64, float *))v21->lpVtbl->RSSetViewports)(
        v21,
        1,
        v154);
      ((void (__fastcall *)(struct ID3D12GraphicsCommandList *, __int64, struct tagRECT *))v21->lpVtbl->RSSetScissorRects)(
        v21,
        1,
        &v163);
      v125 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, struct tagRECT *))(**(_QWORD **)&si128.left + 72LL))(
                          *(_QWORD *)&si128.left,
                          &si128);
      (*(void (__fastcall **)(_QWORD, struct ID3D12Resource *, _QWORD))(**((_QWORD **)this + 4) + 160LL))(
        *((_QWORD *)this + 4),
        v34,
        0);
      ((void (__fastcall *)(struct ID3D12GraphicsCommandList *, __int64, __int64 *, _QWORD, _QWORD))v21->lpVtbl->OMSetRenderTargets)(
        v21,
        1,
        &v125,
        0,
        0);
      if ( !BYTE2(v111[0]) )
      {
        if ( *(&g_AutoSRConfig + 6) )
          DebugPrint("  clearing RTV for partial shader fill");
        si128 = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
        ((void (__fastcall *)(struct ID3D12GraphicsCommandList *, __int64, struct tagRECT *, _QWORD, _QWORD))v21->lpVtbl->ClearRenderTargetView)(
          v21,
          v125,
          &si128,
          0,
          0);
      }
      ((void (__fastcall *)(struct ID3D12GraphicsCommandList *, __int64))v21->lpVtbl->IASetPrimitiveTopology)(v21, 5);
      v105 = 0;
      ((void (__fastcall *)(struct ID3D12GraphicsCommandList *, __int64, __int64))v21->lpVtbl->DrawInstanced)(v21, 4, 1);
      if ( HIBYTE(v111[0]) && !*((_QWORD *)this + 5) )
      {
        v61 = *(&g_AutoSRConfig + 6);
        *(&g_AutoSRConfig + 6) = v12;
        v62 = v117;
        v63 = v114;
        InputResNoRef = SREffectRenderPassDx12::CShaderResourceBuilder::GetInputResNoRef(
                          *((SREffectRenderPassDx12::CShaderResourceBuilder **)this + 9),
                          v114,
                          v117,
                          v150);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1502;
          goto LABEL_38;
        }
        InputResNoRef = SREffectRenderPassDx12::CShaderResourceBuilder::GetOutputResNoRef(
                          *((SREffectRenderPassDx12::CShaderResourceBuilder **)this + 9),
                          v63,
                          v62,
                          &v150[1]);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1503;
          goto LABEL_38;
        }
        v64 = v150[0];
        GetDesc = v150[0]->lpVtbl->GetDesc;
        v66 = ((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v109->lpVtbl->GetDesc)(v109, v162);
        if ( *(_DWORD *)(v66 + 32) != *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))GetDesc)(
                                                    v64,
                                                    v157)
                                                + 32) )
        {
          v6 = -2147024809;
          v20 = 2147942487LL;
          v19 = 1508;
          goto LABEL_39;
        }
        v67 = v150[1]->lpVtbl->GetDesc;
        v68 = ((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v108->lpVtbl->GetDesc)(v108, v162);
        if ( *(_DWORD *)(v68 + 32) != *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v67)(
                                                    v150[1],
                                                    v157)
                                                + 32) )
        {
          v6 = -2147024809;
          v20 = 2147942487LL;
          v19 = 1509;
          goto LABEL_39;
        }
        v153 = 0;
        ResourceBarrier(v21, v109, D3D12_RESOURCE_STATE_PIXEL_SHADER_RESOURCE, D3D12_RESOURCE_STATE_COPY_SOURCE);
        ResourceBarrier(v21, v108, D3D12_RESOURCE_STATE_RENDER_TARGET, D3D12_RESOURCE_STATE_COPY_SOURCE);
        ResourceBarrier(v21, v64, D3D12_RESOURCE_STATE_COMMON, D3D12_RESOURCE_STATE_COPY_DEST);
        ResourceBarrier(v21, v150[1], D3D12_RESOURCE_STATE_COMMON, D3D12_RESOURCE_STATE_COPY_DEST);
        v69 = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v109->lpVtbl->GetDesc)(v109, v162)
                        + 16);
        v151.right = v69;
        v70 = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v109->lpVtbl->GetDesc)(v109, v162)
                        + 24);
        v151.bottom = v70;
        v152.right = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v108->lpVtbl->GetDesc)(
                                   v108,
                                   v162)
                               + 16);
        v152.bottom = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v108->lpVtbl->GetDesc)(
                                    v108,
                                    v162)
                                + 24);
        if ( *(&g_AutoSRConfig + 6) )
          DebugPrint("Frame capture - copying src (0, 0, %d, %d) LR frame", v69, v70);
        CopyResourceHelper(v21, v109, v64, &v151, 0, 0);
        if ( *(&g_AutoSRConfig + 6) )
          DebugPrint("Frame capture - copying target (0, 0, %d, %d) HR frame", v152.right, v152.bottom);
        CopyResourceHelper(v21, v108, v150[1], &v152, 0, 0);
        ResourceBarrier(v21, v150[0], D3D12_RESOURCE_STATE_COPY_DEST, D3D12_RESOURCE_STATE_COMMON);
        ResourceBarrier(v21, v150[1], D3D12_RESOURCE_STATE_COPY_DEST, D3D12_RESOURCE_STATE_COMMON);
        ResourceBarrier(v21, v109, D3D12_RESOURCE_STATE_COPY_SOURCE, D3D12_RESOURCE_STATE_PIXEL_SHADER_RESOURCE);
        ResourceBarrier(v21, v108, D3D12_RESOURCE_STATE_COPY_SOURCE, D3D12_RESOURCE_STATE_RENDER_TARGET);
        *(&g_AutoSRConfig + 6) = v61;
        v34 = v116;
      }
      ResourceBarrier(v21, v109, D3D12_RESOURCE_STATE_PIXEL_SHADER_RESOURCE, D3D12_RESOURCE_STATE_COMMON);
      ResourceBarrier(v21, v34, D3D12_RESOURCE_STATE_RENDER_TARGET, D3D12_RESOURCE_STATE_COMMON);
      InputResNoRef = ((__int64 (__fastcall *)(struct ID3D12GraphicsCommandList *))v21->lpVtbl->Close)(v21);
      v6 = InputResNoRef;
      if ( InputResNoRef < 0 )
      {
        v19 = 1540;
        goto LABEL_38;
      }
      ((void (__fastcall *)(struct ID3D12CommandQueue *, __int64, struct ID3D12GraphicsCommandList **))v115->lpVtbl->ExecuteCommandLists)(
        v115,
        1,
        &v123);
      InputResNoRef = SREffectRenderPassDx12::WaitableFence::SignalFence(this, v115);
      v6 = InputResNoRef;
      if ( InputResNoRef < 0 )
      {
        v19 = 1556;
        goto LABEL_38;
      }
      v29 = 0;
      v111[1] = 0;
      if ( LOBYTE(v111[0]) )
        goto LABEL_239;
      if ( !*((_QWORD *)this + 6) )
      {
        v6 = -2147418113;
        v20 = 2147549183LL;
        v19 = 1566;
        goto LABEL_39;
      }
      *(_QWORD *)&si128.left = 0;
      v112 = 0;
      v72 = v117;
      v73 = v114;
      InputResNoRef = SREffectRenderPassDx12::CShaderResourceBuilder::GetInputResNoRef(
                        *((SREffectRenderPassDx12::CShaderResourceBuilder **)this + 9),
                        v114,
                        v117,
                        (struct ID3D12Resource **)&si128);
      v6 = InputResNoRef;
      if ( InputResNoRef < 0 )
      {
        v19 = 1573;
        goto LABEL_38;
      }
      InputResNoRef = SREffectRenderPassDx12::CShaderResourceBuilder::GetOutputResNoRef(
                        *((SREffectRenderPassDx12::CShaderResourceBuilder **)this + 9),
                        v73,
                        v72,
                        &v112);
      v6 = InputResNoRef;
      if ( InputResNoRef < 0 )
      {
        v19 = 1574;
        goto LABEL_38;
      }
      v74 = *(struct ID3D12Resource **)&si128.left;
      (*(void (__fastcall **)(_QWORD, struct D3D12_RESOURCE_DESC *))(**(_QWORD **)&si128.left + 80LL))(
        *(_QWORD *)&si128.left,
        &v156);
      v75 = v112;
      ((void (__fastcall *)(struct ID3D12Resource *, _BYTE *))v112->lpVtbl->GetDesc)(v112, v162);
      LOBYTE(v111[0]) = RectCoversResource(&v147, &v156, 0);
      if ( v116 != v74 )
      {
        InputResNoRef = ((__int64 (__fastcall *)(struct ID3D12GraphicsCommandList *, _QWORD, _QWORD))v21->lpVtbl->Reset)(
                          v21,
                          *((_QWORD *)this + 12),
                          0);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1589;
          goto LABEL_38;
        }
        v76 = v116;
        ResourceBarrier(v21, v116, D3D12_RESOURCE_STATE_COMMON, D3D12_RESOURCE_STATE_COPY_SOURCE);
        ResourceBarrier(v21, v74, D3D12_RESOURCE_STATE_COMMON, D3D12_RESOURCE_STATE_COPY_DEST);
        if ( *(&g_AutoSRConfig + 6) )
          DebugPrint("  CopyToInput 0x%p -> 0x%p", v76, v74);
        v77 = &v147;
        if ( LOBYTE(v111[0]) )
          v77 = 0;
        CopyResourceHelper(v21, v76, v74, v77, 0, 0);
        ResourceBarrier(v21, v74, D3D12_RESOURCE_STATE_COPY_DEST, D3D12_RESOURCE_STATE_COPY_SOURCE);
        ResourceBarrier(v21, v76, D3D12_RESOURCE_STATE_COPY_SOURCE, D3D12_RESOURCE_STATE_COMMON);
        InputResNoRef = ((__int64 (__fastcall *)(struct ID3D12GraphicsCommandList *))v21->lpVtbl->Close)(v21);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1611;
          goto LABEL_38;
        }
        ((void (__fastcall *)(struct ID3D12CommandQueue *, __int64, struct ID3D12GraphicsCommandList **))v115->lpVtbl->ExecuteCommandLists)(
          v115,
          1,
          &v123);
        InputResNoRef = SREffectRenderPassDx12::WaitableFence::SignalFence(this, v115);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1614;
          goto LABEL_38;
        }
        Width = (unsigned int)v147.right;
        v60 = v147;
      }
      InputResNoRef = SREffectRenderPassDx12::WaitableFence::WaitOnGPU(this, *((struct ID3D12CommandQueue **)this + 6));
      v6 = InputResNoRef;
      if ( InputResNoRef < 0 )
      {
        v19 = 1621;
        goto LABEL_38;
      }
      **((_DWORD **)v121 + 8) = 1;
      LOBYTE(v6) = *(&g_AutoSRConfig + 3);
      LODWORD(v118) = v6;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
      {
        v78 = *((_QWORD *)this + 11);
        v79 = v78 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v78 + 56LL))(v78);
        LOBYTE(v6) = v79 | v6;
        LODWORD(v118) = v6;
      }
      if ( !(_BYTE)v6 )
      {
        v112 = (struct ID3D12Resource *)v110;
        v80 = ((__int64 (__fastcall *)(struct ID3D12Resource *, __int64 *, __int64, struct ID3D12Resource **))v75->lpVtbl->SetPrivateData)(
                v75,
                DIRECTSR_EXT_QUEUE_TO_SIGNAL,
                8,
                &v112);
        if ( v80 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x664,
            (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
            (const char *)(unsigned int)v80,
            v105);
        LODWORD(v118) = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v74->lpVtbl->GetDesc)(
                                      v74,
                                      v157)
                                  + 24);
        v111[1] = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v74->lpVtbl->GetDesc)(
                                v74,
                                v168)
                            + 16);
        LODWORD(v116) = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v75->lpVtbl->GetDesc)(
                                      v75,
                                      v157)
                                  + 24);
        LODWORD(v120) = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v75->lpVtbl->GetDesc)(
                                      v75,
                                      v168)
                                  + 16);
        if ( *(&g_AutoSRConfig + 6) )
          DebugPrint("  SR Execute 0x%p -> 0x%p", v74, v75);
        memset_0(v146, 0, sizeof(v146));
        v142 = v74;
        v143 = 0;
        v144 = v111[1];
        v145 = (int)v118;
        v139[0] = v75;
        v139[1] = 0;
        v140 = (int)v120;
        v141 = (int)v116;
        v111[1] = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, _QWORD))(**((_QWORD **)this + 5) + 24LL))(
                    *((_QWORD *)this + 5),
                    v139,
                    v81,
                    0);
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x67B,
          (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
          (const char *)v111[1],
          (int)"Execute call failed unexpectedly",
          v106);
        *(&g_AutoSRConfig + 9) = (v111[1] & 0x80000000) != 0;
        LODWORD(v118) = v111[1] >> 31;
        Height = 8;
        v32 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) == 0;
        GetPrivateData = v75->lpVtbl->GetPrivateData;
        if ( v32 )
        {
          v83 = ((__int64 (__fastcall *)(struct ID3D12Resource *, __int64 *, UINT *, struct ID3D12Resource **))GetPrivateData)(
                  v75,
                  DIRECTSR_EXT_QUEUE_TO_SIGNAL,
                  &Height,
                  &v112);
          if ( v83 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x68A,
              (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
              (const char *)(unsigned int)v83,
              v105);
        }
        else if ( ((int (__fastcall *)(struct ID3D12Resource *, __int64 *, UINT *, struct ID3D12Resource **))GetPrivateData)(
                    v75,
                    DIRECTSR_EXT_QUEUE_TO_SIGNAL,
                    &Height,
                    &v112) < 0 )
        {
          goto LABEL_173;
        }
        if ( Height != 8 || v112 )
        {
          InputResNoRef = SREffectRenderPassDx12::WaitableFence::SignalFence(
                            this,
                            *((struct ID3D12CommandQueue **)this + 6));
          v6 = InputResNoRef;
          if ( InputResNoRef < 0 )
          {
            v19 = 1682;
            goto LABEL_38;
          }
          InputResNoRef = SREffectRenderPassDx12::WaitableFence::WaitOnGPU(this, v110);
          v6 = InputResNoRef;
          if ( InputResNoRef < 0 )
          {
            v19 = 1683;
            goto LABEL_38;
          }
        }
      }
LABEL_173:
      InputResNoRef = SREffectRenderPassDx12::WaitableFence::SignalFence(this, v110);
      v6 = InputResNoRef;
      if ( InputResNoRef < 0 )
      {
        v19 = 1688;
        goto LABEL_38;
      }
      if ( (_BYTE)v118 )
      {
        InputResNoRef = ((__int64 (__fastcall *)(struct ID3D12GraphicsCommandList *, _QWORD, _QWORD))v21->lpVtbl->Reset)(
                          v21,
                          *((_QWORD *)this + 12),
                          0);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1692;
          goto LABEL_38;
        }
        if ( BYTE1(v111[0]) )
        {
          ResourceBarrier(v21, v108, D3D12_RESOURCE_STATE_COMMON, D3D12_RESOURCE_STATE_COPY_DEST);
          ((void (__fastcall *)(struct ID3D12GraphicsCommandList *, struct ID3D12Resource *, struct ID3D12Resource *))v21->lpVtbl->CopyResource)(
            v21,
            v108,
            v74);
          ResourceBarrier(v21, v108, D3D12_RESOURCE_STATE_COPY_DEST, D3D12_RESOURCE_STATE_COMMON);
        }
        else
        {
          if ( *(&g_AutoSRConfig + 6) )
            DebugPrint("  SR Passthrough 0x%p -> 0x%p", v74, v75);
          ((void (__fastcall *)(struct ID3D12GraphicsCommandList *, struct ID3D12Resource *, struct ID3D12Resource *))v21->lpVtbl->CopyResource)(
            v21,
            v75,
            v74);
        }
        InputResNoRef = ((__int64 (__fastcall *)(struct ID3D12GraphicsCommandList *))v21->lpVtbl->Close)(v21);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1712;
          goto LABEL_38;
        }
        ((void (__fastcall *)(struct ID3D12CommandQueue *, __int64, struct ID3D12GraphicsCommandList **))v110->lpVtbl->ExecuteCommandLists)(
          v110,
          1,
          &v123);
      }
      if ( !BYTE1(v111[0]) )
      {
        InputResNoRef = ((__int64 (__fastcall *)(struct ID3D12GraphicsCommandList *, _QWORD, _QWORD))v21->lpVtbl->Reset)(
                          v21,
                          *((_QWORD *)this + 12),
                          0);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1721;
          goto LABEL_38;
        }
        ResourceBarrier(v21, v75, D3D12_RESOURCE_STATE_COPY_DEST, D3D12_RESOURCE_STATE_COPY_SOURCE);
        ResourceBarrier(v21, v108, D3D12_RESOURCE_STATE_COMMON, D3D12_RESOURCE_STATE_COPY_DEST);
        if ( *(&g_AutoSRConfig + 1) )
        {
          if ( *(&g_AutoSRConfig + 6) )
            DebugPrint("  SS L copy 0x%p -> 0x%p", v74, v108);
          v85 = Width;
          LODWORD(v116) = v147.left + 1 + ((unsigned int)(Width - v147.left) >> 1);
          si128 = v60;
          si128.right = (int)v116;
          CopyResourceHelper(v21, v74, v108, &si128, 0, v147.top);
          if ( *(&g_AutoSRConfig + 6) )
            DebugPrint("  SS R copy 0x%p -> 0x%p", v75, v108);
          si128 = v60;
          si128.left = (int)v116;
          si128.right = v85;
          CopyResourceHelper(v21, v75, v108, &si128, (unsigned int)v116, v147.top);
        }
        else
        {
          v84 = &v147;
          if ( LOBYTE(v111[0]) )
            v84 = 0;
          if ( *(&g_AutoSRConfig + 6) )
            DebugPrint("  CopyToOutput 0x%p -> 0x%p", v75, v108);
          CopyResourceHelper(v21, v75, v108, v84, 0, v147.top);
          v60 = v147;
        }
        ResourceBarrier(v21, v74, D3D12_RESOURCE_STATE_COPY_SOURCE, D3D12_RESOURCE_STATE_COMMON);
        ResourceBarrier(v21, v75, D3D12_RESOURCE_STATE_COPY_SOURCE, D3D12_RESOURCE_STATE_COMMON);
        ResourceBarrier(v21, v108, D3D12_RESOURCE_STATE_COPY_DEST, D3D12_RESOURCE_STATE_COMMON);
        InputResNoRef = lambda_8eec7823b81d4d24fb4c4eb39c547389_::operator()(&v124, v110);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1761;
          goto LABEL_38;
        }
        InputResNoRef = ((__int64 (__fastcall *)(struct ID3D12GraphicsCommandList *))v21->lpVtbl->Close)(v21);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1766;
          goto LABEL_38;
        }
        ((void (__fastcall *)(struct ID3D12CommandQueue *, __int64, struct ID3D12GraphicsCommandList **))v110->lpVtbl->ExecuteCommandLists)(
          v110,
          1,
          &v123);
      }
      if ( HIBYTE(v111[0]) )
      {
        v86 = *(&g_AutoSRConfig + 6);
        *(&g_AutoSRConfig + 6) = v12;
        v87 = v117;
        v88 = v114;
        InputResNoRef = SREffectRenderPassDx12::CShaderResourceBuilder::GetInputResNoRef(
                          *((SREffectRenderPassDx12::CShaderResourceBuilder **)this + 9),
                          v114,
                          v117,
                          v150);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1776;
          goto LABEL_38;
        }
        InputResNoRef = SREffectRenderPassDx12::CShaderResourceBuilder::GetOutputResNoRef(
                          *((SREffectRenderPassDx12::CShaderResourceBuilder **)this + 9),
                          v88,
                          v87,
                          &v150[1]);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1777;
          goto LABEL_38;
        }
        v89 = v109;
        v90 = v109->lpVtbl->GetDesc;
        v91 = ((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v150[0]->lpVtbl->GetDesc)(v150[0], v157);
        if ( *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v90)(v89, v168) + 32) == *(_DWORD *)(v91 + 32) )
        {
          v94 = v150[0];
        }
        else
        {
          InputResNoRef = SREffectRenderPassDx12::CShaderResourceBuilder::GetSrcFormatIntNoRef(
                            *((SREffectRenderPassDx12::CShaderResourceBuilder **)this + 9),
                            v92,
                            v93,
                            v150);
          v6 = InputResNoRef;
          if ( InputResNoRef < 0 )
          {
            v19 = 1783;
            goto LABEL_38;
          }
          v94 = v150[0];
          if ( !v150[0] )
          {
            v6 = -2147418113;
            v20 = 2147549183LL;
            v19 = 1785;
            goto LABEL_39;
          }
          if ( *(&g_AutoSRConfig + 6) )
            DebugPrint("Frame capture - format mismatch, using extra src-format intermediate");
        }
        v95 = v109;
        v96 = v109->lpVtbl->GetDesc;
        v97 = ((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v94->lpVtbl->GetDesc)(v94, v157);
        if ( *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v96)(v95, v168) + 32) == *(_DWORD *)(v97 + 32) )
        {
          v153 = 0;
          v98 = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v109->lpVtbl->GetDesc)(
                              v109,
                              v157)
                          + 16);
          v151.right = v98;
          LODWORD(v116) = *(_DWORD *)(((__int64 (__fastcall *)(struct ID3D12Resource *, _BYTE *))v109->lpVtbl->GetDesc)(
                                        v109,
                                        v157)
                                    + 24);
          v151.bottom = (int)v116;
          v152 = v60;
          v99 = v119;
          InputResNoRef = ((__int64 (__fastcall *)(struct ID3D12GraphicsCommandList *, _QWORD, _QWORD))v119->lpVtbl->Reset)(
                            v119,
                            *((_QWORD *)this + 12),
                            0);
          v6 = InputResNoRef;
          if ( InputResNoRef < 0 )
          {
            v19 = 1804;
            goto LABEL_38;
          }
          ResourceBarrier(v99, v109, D3D12_RESOURCE_STATE_COMMON, D3D12_RESOURCE_STATE_COPY_SOURCE);
          v100 = v150[0];
          ResourceBarrier(v99, v150[0], D3D12_RESOURCE_STATE_COMMON, D3D12_RESOURCE_STATE_COPY_DEST);
          if ( *(&g_AutoSRConfig + 6) )
            DebugPrint("Frame capture - copying src (0, 0, %d, %d) LR frame", v98, (_DWORD)v116);
          CopyResourceHelper(v99, v109, v100, &v151, 0, 0);
          ResourceBarrier(v99, v150[0], D3D12_RESOURCE_STATE_COPY_DEST, D3D12_RESOURCE_STATE_COMMON);
          ResourceBarrier(v99, v109, D3D12_RESOURCE_STATE_COPY_SOURCE, D3D12_RESOURCE_STATE_COMMON);
          InputResNoRef = ((__int64 (__fastcall *)(struct ID3D12GraphicsCommandList *))v99->lpVtbl->Close)(v99);
          v6 = InputResNoRef;
          if ( InputResNoRef < 0 )
          {
            v19 = 1812;
            goto LABEL_38;
          }
          ((void (__fastcall *)(struct ID3D12CommandQueue *, __int64, struct ID3D12GraphicsCommandList **))v110->lpVtbl->ExecuteCommandLists)(
            v110,
            1,
            &v123);
        }
        else
        {
          v151 = v60;
          v152 = v60;
        }
        *(&g_AutoSRConfig + 6) = v86;
      }
      InputResNoRef = SREffectRenderPassDx12::WaitableFence::SignalFence(this, v110);
      v6 = InputResNoRef;
      if ( InputResNoRef < 0 )
      {
        v19 = 1831;
        goto LABEL_38;
      }
      v29 = v111[1];
LABEL_239:
      if ( HIBYTE(v111[0]) )
      {
        v101 = *(&g_AutoSRConfig + 6);
        *(&g_AutoSRConfig + 6) = v12;
        InputResNoRef = SREffectRenderPassDx12::WaitableFence::WaitOnCPU(this, (const unsigned __int64 *)this + 2);
        v6 = InputResNoRef;
        if ( InputResNoRef < 0 )
        {
          v19 = 1852;
          goto LABEL_38;
        }
        if ( (int)WriteResourceToDisk(v150[0], v151.right, v151.bottom, L"_Orig") < 0
          || (int)WriteResourceToDisk(v150[1], v152.right, v152.bottom, L"_SR") < 0 )
        {
          CModule::RecordJournalImpl(v71, 0, "Info: failed to write frame to disk", v102);
        }
        *(&g_AutoSRConfig + 6) = v101;
      }
      SREffectRenderPassDx12::CShaderRenderPass::LogOnceRenderMode(v71, *((unsigned int *)this + 50));
      goto LABEL_247;
    }
LABEL_85:
    v33 = 0;
    if ( !*(&g_AutoSRConfig + 1) )
      goto LABEL_87;
    goto LABEL_86;
  }
  v6 = -2147467262;
  if ( v4 != -2147467262 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x448,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
      (const char *)(unsigned int)v4,
      v104);
LABEL_7:
    v6 = v5;
  }
LABEL_248:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v115);
  return v6;
}

```

## disassembly

```asm
0x1800b73cc  mov     rax, rsp
0x1800b73cf  mov     [rax+20h], rbx
0x1800b73d3  push    rbp
0x1800b73d4  push    rsi
0x1800b73d5  push    rdi
0x1800b73d6  push    r12
0x1800b73d8  push    r13
0x1800b73da  push    r14
0x1800b73dc  push    r15
0x1800b73de  lea     rbp, [rax-448h]
0x1800b73e5  sub     rsp, 510h
0x1800b73ec  movaps  xmmword ptr [rax-48h], xmm6
0x1800b73f0  mov     rax, cs:__security_cookie
0x1800b73f7  xor     rax, rsp
0x1800b73fa  mov     [rbp+440h+var_50], rax
0x1800b7401  mov     [rbp+440h+var_4B0], r8d
0x1800b7405  mov     r13, rcx
0x1800b7408  mov     [rbp+440h+var_490], rdx
0x1800b740c  xor     r15d, r15d
0x1800b740f  cmp     [rdx], r15
0x1800b7412  jz      loc_1800B91AA
0x1800b7418  cmp     [rdx+10h], r15
0x1800b741c  jz      loc_1800B91AA
0x1800b7422  cmp     [rdx+20h], r15
0x1800b7426  jz      loc_1800B91AA
0x1800b742c  mov     [rbp+440h+var_4C0], r15
0x1800b7430  mov     rcx, [rdx]
0x1800b7433  mov     rax, [rcx]
0x1800b7436  lea     r8, [rbp+440h+var_4C0]
0x1800b743a  lea     rdx, _GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed
0x1800b7441  mov     rax, [rax]
0x1800b7444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7449  mov     ebx, eax
0x1800b744b  test    eax, eax
0x1800b744d  jns     short loc_1800B747E
0x1800b744f  mov     esi, 80004002h
0x1800b7454  cmp     eax, esi
0x1800b7456  jz      loc_1800B919F
0x1800b745c  mov     rcx, [rbp+448h]; this
0x1800b7463  mov     r9d, eax; char *
0x1800b7466  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b746d  mov     edx, 448h; void *
0x1800b7472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7477  mov     esi, ebx
0x1800b7479  jmp     loc_1800B919F
0x1800b747e  mov     [rsp+540h+var_4E0], r15
0x1800b7483  mov     rax, [rbp+440h+var_490]
0x1800b7487  mov     rcx, [rax+8]
0x1800b748b  test    rcx, rcx
0x1800b748e  jz      short loc_1800B74EC
0x1800b7490  mov     rax, [rcx]
0x1800b7493  lea     r8, [rsp+540h+var_4E0]
0x1800b7498  lea     rdx, _GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed
0x1800b749f  mov     rax, [rax]
0x1800b74a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b74a7  mov     ebx, eax
0x1800b74a9  test    eax, eax
0x1800b74ab  jns     short loc_1800B74FA
0x1800b74ad  mov     esi, 80004002h
0x1800b74b2  cmp     eax, esi
0x1800b74b4  jnz     short loc_1800B74C5
0x1800b74b6  lea     rcx, [rsp+540h+var_4E0]
0x1800b74bb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b74c0  jmp     loc_1800B919F
0x1800b74c5  mov     rcx, [rbp+448h]; this
0x1800b74cc  mov     r9d, ebx; char *
0x1800b74cf  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b74d6  mov     edx, 452h; void *
0x1800b74db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b74e0  lea     rcx, [rsp+540h+var_4E0]
0x1800b74e5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b74ea  jmp     short loc_1800B7477
0x1800b74ec  lea     rdx, [rbp+440h+var_4C0]
0x1800b74f0  lea     rcx, [rsp+540h+var_4E0]
0x1800b74f5  call    ??4?$CComPtr@UID3D12CommandQueue@@@ATL@@QEAAPEAUID3D12CommandQueue@@AEBV01@@Z; ATL::CComPtr<ID3D12CommandQueue>::operator=(ATL::CComPtr<ID3D12CommandQueue> const &)
0x1800b74fa  mov     [rsp+540h+var_4E8], r15
0x1800b74ff  mov     rax, [rbp+440h+var_490]
0x1800b7503  mov     rcx, [rax+10h]
0x1800b7507  mov     rax, [rcx]
0x1800b750a  lea     r8, [rsp+540h+var_4E8]
0x1800b750f  lea     rdx, _GUID_696442be_a72e_4059_bc79_5b5c98040fad
0x1800b7516  mov     rax, [rax]
0x1800b7519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b751e  mov     esi, eax
0x1800b7520  test    eax, eax
0x1800b7522  jns     short loc_1800B754E
0x1800b7524  mov     rcx, [rbp+448h]; this
0x1800b752b  mov     r9d, eax; char *
0x1800b752e  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b7535  mov     edx, 45Eh; void *
0x1800b753a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b753f  lea     rcx, [rsp+540h+var_4E8]
0x1800b7544  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b7549  jmp     loc_1800B74B6
0x1800b754e  mov     [rsp+540h+var_4F0], r15
0x1800b7553  mov     rax, [rbp+440h+var_490]
0x1800b7557  mov     rcx, [rax+20h]
0x1800b755b  mov     rax, [rcx]
0x1800b755e  lea     r8, [rsp+540h+var_4F0]
0x1800b7563  lea     rdx, _GUID_696442be_a72e_4059_bc79_5b5c98040fad
0x1800b756a  mov     rax, [rax]
0x1800b756d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7572  mov     esi, eax
0x1800b7574  test    eax, eax
0x1800b7576  jns     short loc_1800B759F
0x1800b7578  mov     rcx, [rbp+448h]; this
0x1800b757f  mov     r9d, eax; char *
0x1800b7582  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b7589  mov     edx, 461h; void *
0x1800b758e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7593  lea     rcx, [rsp+540h+var_4F0]
0x1800b7598  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b759d  jmp     short loc_1800B753F
0x1800b759f  lea     rax, [rbp+440h+var_490]
0x1800b75a3  mov     [rbp+440h+var_478], rax
0x1800b75a7  mov     rcx, [rsp+540h+var_4E8]
0x1800b75ac  mov     rax, [rcx]
0x1800b75af  lea     rdx, [rbp+440h+var_110]
0x1800b75b6  mov     rax, [rax+50h]
0x1800b75ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b75bf  mov     rcx, [rsp+540h+var_4F0]
0x1800b75c4  mov     rax, [rcx]
0x1800b75c7  lea     rdx, [rbp+440h+var_240]
0x1800b75ce  mov     rax, [rax+50h]
0x1800b75d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b75d7  movzx   r14d, byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+7; AutoSRConfig g_AutoSRConfig
0x1800b75df  mov     byte ptr [rsp+540h+var_4D8+3], r14b
0x1800b75e4  mov     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+7, r15b; AutoSRConfig g_AutoSRConfig
0x1800b75eb  xorps   xmm0, xmm0
0x1800b75ee  movdqu  xmmword ptr [rbp+440h+var_290], xmm0
0x1800b75f6  movups  xmmword ptr [rbp+440h+var_280.left], xmm0
0x1800b75fd  xorps   xmm1, xmm1
0x1800b7600  movups  xmmword ptr [rbp+440h+var_270.left], xmm1
0x1800b7607  mov     [rbp+440h+var_260], r15b
0x1800b760e  mov     dil, byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6; AutoSRConfig g_AutoSRConfig
0x1800b7615  test    dil, dil
0x1800b7618  jz      short loc_1800B7626
0x1800b761a  cmp     dword ptr [r13+0C0h], 5
0x1800b7622  mov     al, 1
0x1800b7624  jb      short loc_1800B7629
0x1800b7626  mov     al, r15b
0x1800b7629  mov     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, al; AutoSRConfig g_AutoSRConfig
0x1800b762f  test    al, al
0x1800b7631  jz      short loc_1800B765A
0x1800b7633  mov     eax, [rbp+440h+var_240.Format]
0x1800b7639  mov     dword ptr [rsp+540h+var_520], eax
0x1800b763d  mov     r9, [rsp+540h+var_4F0]
0x1800b7642  mov     r8d, [rbp+440h+var_F0]
0x1800b7649  mov     rdx, [rsp+540h+var_4E8]
0x1800b764e  lea     rcx, aExecutePsource; "Execute(): pSource12 0x%p (%d) -> pTarg"...
0x1800b7655  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800b765a  mov     qword ptr [rbp+440h+var_2B0.left], r15
0x1800b7661  mov     rcx, [rbp+440h+var_240.Width]
0x1800b7668  mov     [rbp+440h+var_488], rcx
0x1800b766c  mov     [rbp+440h+var_2B0.right], ecx
0x1800b7672  mov     eax, [rbp+440h+var_240.Height]
0x1800b7678  mov     [rsp+540h+var_4C8], eax
0x1800b767c  mov     [rbp+440h+var_2B0.bottom], eax
0x1800b7682  mov     byte ptr [rsp+540h+var_4D8+2], 1
0x1800b7687  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+5, r15b; AutoSRConfig g_AutoSRConfig
0x1800b768e  jnz     loc_1800B774B
0x1800b7694  mov     [rsp+540h+var_4D8+4], ecx
0x1800b7698  mov     eax, [rbp+440h+var_100]
0x1800b769e  mov     [rsp+540h+var_4C4], eax
0x1800b76a2  lea     rax, [rbp+440h+var_2B0]
0x1800b76a9  mov     [rsp+540h+var_520], rax; struct tagRECT *
0x1800b76ae  lea     r9, [rbp+440h+var_240.Height]; unsigned int *
0x1800b76b5  lea     r8, [rsp+540h+var_4D8+4]; unsigned int *
0x1800b76ba  lea     rdx, [rbp+440h+var_F8]; unsigned int *
0x1800b76c1  lea     rcx, [rsp+540h+var_4C4]; unsigned int *
0x1800b76c6  call    ?GetAspectRatioCorrectDimensions@@YAXAEBI000PEAUtagRECT@@@Z; GetAspectRatioCorrectDimensions(uint const &,uint const &,uint const &,uint const &,tagRECT *)
0x1800b76cb  mov     r8d, 1; int
0x1800b76d1  lea     rdx, [rbp+440h+var_240]; struct D3D12_RESOURCE_DESC *
0x1800b76d8  lea     rcx, [rbp+440h+var_2B0]; struct tagRECT *
0x1800b76df  call    ?RectCoversResource@@YA_NAEBUtagRECT@@AEBUD3D12_RESOURCE_DESC@@H@Z; RectCoversResource(tagRECT const &,D3D12_RESOURCE_DESC const &,int)
0x1800b76e4  mov     dl, al
0x1800b76e6  mov     byte ptr [rsp+540h+var_4D8+2], al
0x1800b76ea  test    al, al
0x1800b76ec  jz      short loc_1800B7708
0x1800b76ee  mov     ecx, dword ptr [rbp+440h+var_240.Width]
0x1800b76f4  mov     [rbp+440h+var_2B0.right], ecx
0x1800b76fa  mov     eax, [rbp+440h+var_240.Height]
0x1800b7700  mov     [rbp+440h+var_2B0.bottom], eax
0x1800b7706  jmp     short loc_1800B7714
0x1800b7708  mov     eax, [rbp+440h+var_2B0.bottom]
0x1800b770e  mov     ecx, [rbp+440h+var_2B0.right]
0x1800b7714  mov     [rbp+440h+var_488], rcx
0x1800b7718  mov     [rsp+540h+var_4C8], eax
0x1800b771c  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, r15b; AutoSRConfig g_AutoSRConfig
0x1800b7723  jz      short loc_1800B7747
0x1800b7725  mov     dword ptr [rsp+540h+var_520], eax
0x1800b7729  mov     r9d, ecx
0x1800b772c  mov     r8d, [rbp+440h+var_2B0.top]
0x1800b7733  mov     edx, [rbp+440h+var_2B0.left]
0x1800b7739  lea     rcx, aArRectDDDD; "  AR rect: { %d, %d, %d, %d }"
0x1800b7740  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800b7745  jmp     short loc_1800B774B
0x1800b7747  mov     byte ptr [rsp+540h+var_4D8+2], dl
0x1800b774b  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+3, r15b; AutoSRConfig g_AutoSRConfig
0x1800b7752  jz      short loc_1800B776B
0x1800b7754  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+1, r15b; AutoSRConfig g_AutoSRConfig
0x1800b775b  jnz     short loc_1800B776B
0x1800b775d  cmp     [rbp+440h+var_240.Layout], 1
0x1800b7764  mov     byte ptr [rsp+540h+var_4D8+1], 1
0x1800b7769  jz      short loc_1800B7770
0x1800b776b  mov     byte ptr [rsp+540h+var_4D8+1], r15b
0x1800b7770  mov     rdx, [rbp+440h+var_4C0]; struct ID3D12CommandQueue *
0x1800b7774  mov     rcx, [r13+20h]; struct ID3D12Device4 *
0x1800b7778  call    ?DetermineNodeIndexFromCommandQueue@@YAIPEAUID3D12Device4@@PEAUID3D12CommandQueue@@@Z; DetermineNodeIndexFromCommandQueue(ID3D12Device4 *,ID3D12CommandQueue *)
0x1800b777d  mov     r12d, eax
0x1800b7780  mov     [rsp+540h+var_4C4], eax
0x1800b7784  mov     [rbp+440h+var_4A0], r15
0x1800b7788  mov     qword ptr [rbp+440h+var_60.left], r15
0x1800b778f  mov     [rbp+440h+var_498], r15
0x1800b7793  lea     rax, [rbp+440h+var_498]
0x1800b7797  mov     [rsp+540h+var_520], rax; int
0x1800b779c  lea     r9, [rbp+440h+var_60]; struct ID3D12DescriptorHeap **
0x1800b77a3  lea     r8, [rbp+440h+var_4A0]; struct ID3D12GraphicsCommandList **
0x1800b77a7  mov     rdx, [rbp+440h+var_4C0]; struct ID3D12CommandQueue *
0x1800b77ab  mov     rcx, r13; this
0x1800b77ae  call    ?EnsureRenderResourceForNode@CShaderRenderPass@SREffectRenderPassDx12@@AEAAJPEAUID3D12CommandQueue@@PEAPEAUID3D12GraphicsCommandList@@PEAPEAUID3D12DescriptorHeap@@2@Z; SREffectRenderPassDx12::CShaderRenderPass::EnsureRenderResourceForNode(ID3D12CommandQueue *,ID3D12GraphicsCommandList * *,ID3D12DescriptorHeap * *,ID3D12DescriptorHeap * *)
0x1800b77b3  mov     esi, eax
0x1800b77b5  test    eax, eax
0x1800b77b7  jns     short loc_1800B77E0
0x1800b77b9  mov     edx, 4B6h; void *
0x1800b77be  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b77c5  mov     r9d, eax; char *
0x1800b77c8  mov     rcx, [rbp+448h]; this
0x1800b77cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b77d4  mov     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, dil; AutoSRConfig g_AutoSRConfig
0x1800b77db  jmp     loc_1800B7593
0x1800b77e0  mov     r15, [rbp+440h+var_4A0]
0x1800b77e4  mov     [rbp+440h+var_480], r15
0x1800b77e8  lea     rdx, [r13+10h]; unsigned __int64 *
0x1800b77ec  mov     rcx, r13; this
0x1800b77ef  call    ?WaitOnCPU@WaitableFence@SREffectRenderPassDx12@@QEAAJAEB_K@Z; SREffectRenderPassDx12::WaitableFence::WaitOnCPU(unsigned __int64 const &)
0x1800b77f4  mov     esi, eax
0x1800b77f6  test    eax, eax
0x1800b77f8  jns     short loc_1800B7801
0x1800b77fa  mov     edx, 4C1h
0x1800b77ff  jmp     short loc_1800B77BE
0x1800b7801  xor     esi, esi
0x1800b7803  cmp     [r13+28h], rsi
0x1800b7807  setz    bl
0x1800b780a  mov     byte ptr [rsp+540h+var_4D8], bl
0x1800b780e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x1800b7815  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x1800b781a  test    al, al
0x1800b781c  jz      short loc_1800B7853
0x1800b781e  cmp     [r13+28h], rsi
0x1800b7822  jz      short loc_1800B783B
0x1800b7824  mov     rcx, [r13+58h]
0x1800b7828  mov     rax, [rcx]
0x1800b782b  mov     rax, [rax+38h]
0x1800b782f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7834  test    al, al
0x1800b7836  mov     bl, sil
0x1800b7839  jz      short loc_1800B783D
0x1800b783b  mov     bl, 1
0x1800b783d  mov     rcx, [r13+58h]
0x1800b7841  mov     rax, [rcx]
0x1800b7844  mov     rax, [rax+38h]
0x1800b7848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b784d  or      bl, al
0x1800b784f  mov     byte ptr [rsp+540h+var_4D8], bl
0x1800b7853  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x1800b785a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x1800b785f  test    al, al
0x1800b7861  jz      loc_1800B7B58
0x1800b7867  cmp     [r13+0C4h], sil
0x1800b786e  jz      loc_1800B7B58
0x1800b7874  test    bl, bl
0x1800b7876  jz      short loc_1800B7885
0x1800b7878  cmp     [r13+0C5h], sil
0x1800b787f  jz      loc_1800B7B58
0x1800b7885  mov     rax, [rsp+540h+var_4E0]
0x1800b788a  mov     [rbp+440h+var_4A0], rax
0x1800b788e  mov     rcx, [rsp+540h+var_4F0]
0x1800b7893  mov     rax, [rcx]
0x1800b7896  lea     r9, [rbp+440h+var_4A0]
0x1800b789a  mov     ebx, 8
0x1800b789f  mov     r8d, ebx
0x1800b78a2  lea     rdx, DIRECTSR_EXT_QUEUE_TO_SIGNAL
0x1800b78a9  mov     rax, [rax+20h]
0x1800b78ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b78b2  lea     r12, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b78b9  test    eax, eax
0x1800b78bb  jns     short loc_1800B78D4
0x1800b78bd  mov     rcx, [rbp+448h]; this
0x1800b78c4  mov     r9d, eax; char *
0x1800b78c7  mov     r8, r12; unsigned int
0x1800b78ca  mov     edx, 4DAh; void *
0x1800b78cf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b78d4  mov     rcx, [r13+58h]
0x1800b78d8  mov     rax, [rcx]
0x1800b78db  lea     rdx, [rbp+440h+var_2B0]
0x1800b78e2  mov     rax, [rax+58h]
0x1800b78e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b78eb  mov     [rbp+440h+var_294], r14d
0x1800b78f2  mov     rcx, [r13+58h]
  ... truncated ...
```
