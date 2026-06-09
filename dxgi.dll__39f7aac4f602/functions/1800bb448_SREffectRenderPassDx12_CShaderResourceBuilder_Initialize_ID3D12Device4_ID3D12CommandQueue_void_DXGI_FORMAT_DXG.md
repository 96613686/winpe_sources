# SREffectRenderPassDx12::CShaderResourceBuilder::Initialize(ID3D12Device4 *,ID3D12CommandQueue *,void *,DXGI_FORMAT,DXGI_FORMAT,uint,DSR_SIZE const &,DSR_SIZE const &)

- ea: `0x1800bb448`
- end: `0x1800bbbe7`
- name: `?Initialize@CShaderResourceBuilder@SREffectRenderPassDx12@@QEAAJPEAUID3D12Device4@@PEAUID3D12CommandQueue@@PEAXW4DXGI_FORMAT@@3IAEBUDSR_SIZE@@4@Z`
- size: `1951`
- prototype: `__int64 __usercall@<rax>(SREffectRenderPassDx12::CShaderResourceBuilder *__hidden this@<rcx>, struct ID3D12Device4 *@<rdx>, struct ID3D12CommandQueue *@<r8>, void *@<r9>, enum DXGI_FORMAT, enum DXGI_FORMAT, unsigned int, const struct DSR_SIZE *, const struct DSR_SIZE *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800bbc98`

## callees

- `0x180030320`
- `0x1800306f4`
- `0x1800334f4`
- `0x1800337ec`
- `0x180033838`
- `0x180067d2c`
- `0x18006989c`
- `0x180075fa0`
- `0x180076f20`
- `0x1800a13a0`
- `0x1800b05bc`
- `0x1800b1d64`
- `0x1800b6bc0`
- `0x1800b6ef4`
- `0x1800b71ac`
- `0x1800bb448`
- `0x1800bbbf0`
- `0x1800bd2a0`
- `0x1800bd2dc`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bb4ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bb500`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bb4ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bb500`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800bb4bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800bb4d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800bb4bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800bb4d4`

## string_xrefs

- `0x1800bb4b5`: `SuperResExt.dll`
- `0x1800bb555`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800bbba0`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800bb4cd`: `DXGITestEffects.dll`

## pseudocode

```c
__int64 __fastcall SREffectRenderPassDx12::CShaderResourceBuilder::Initialize(
        SREffectRenderPassDx12::CShaderResourceBuilder *this,
        struct IUnknown *a2,
        struct IUnknown *a3,
        void *a4,
        enum DXGI_FORMAT a5,
        enum DXGI_FORMAT a6,
        unsigned int a7,
        const struct DSR_SIZE *a8,
        const struct DSR_SIZE *a9)
{
  struct ID3D12Device **v13; // r13
  HMODULE ModuleHandleA; // rbx
  FARPROC ProcAddress; // rax
  unsigned int v16; // eax
  unsigned __int64 v17; // r15
  int RootSignatureHelper; // ebx
  __int64 v19; // rdx
  bool v21; // al
  const char *v22; // rcx
  unsigned __int64 v23; // rsi
  __int64 v24; // r8
  unsigned __int64 v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // r8
  unsigned __int64 v28; // rcx
  __int64 v29; // rbx
  _QWORD *v30; // r13
  __int64 v31; // r8
  unsigned __int64 v32; // rcx
  __int64 v33; // rbx
  unsigned __int64 v34; // rax
  unsigned __int64 v35; // r14
  __int64 v36; // r8
  unsigned __int64 v37; // rcx
  __int64 v38; // rbx
  __int64 v39; // r8
  unsigned __int64 v40; // rcx
  __int64 v41; // rbx
  __int64 v42; // r8
  unsigned __int64 v43; // rcx
  __int64 v44; // rbx
  __int64 v45; // rdx
  __int64 v46; // r15
  unsigned __int64 v47; // rcx
  __int64 v48; // rax
  size_t v49; // rbx
  __int64 v50; // rax
  __int64 v51; // rbx
  int Resources; // esi
  __int64 v53; // rdx
  GUID *v54; // [rsp+20h] [rbp-128h]
  unsigned int v55; // [rsp+40h] [rbp-108h]
  _QWORD v56[4]; // [rsp+48h] [rbp-100h] BYREF
  _DWORD v57[4]; // [rsp+68h] [rbp-E0h] BYREF
  _QWORD *v58; // [rsp+78h] [rbp-D0h]
  int v59; // [rsp+80h] [rbp-C8h]
  __m128i *p_si128; // [rsp+88h] [rbp-C0h]
  int v61; // [rsp+90h] [rbp-B8h]
  _DWORD v62[4]; // [rsp+98h] [rbp-B0h] BYREF
  _DWORD v63[4]; // [rsp+A8h] [rbp-A0h] BYREF
  int v64; // [rsp+B8h] [rbp-90h] BYREF
  __int64 v65; // [rsp+BCh] [rbp-8Ch]
  int v66; // [rsp+C4h] [rbp-84h]
  int v67; // [rsp+C8h] [rbp-80h]
  __m128i si128; // [rsp+D0h] [rbp-78h] BYREF
  int v69; // [rsp+E0h] [rbp-68h]
  int v70; // [rsp+E4h] [rbp-64h]
  int v71; // [rsp+E8h] [rbp-60h]
  __int64 v72; // [rsp+ECh] [rbp-5Ch]
  int v73; // [rsp+F4h] [rbp-54h]
  __int64 v74; // [rsp+F8h] [rbp-50h]
  int v75; // [rsp+100h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v13 = (struct ID3D12Device **)((char *)this + 32);
  if ( *((struct IUnknown **)this + 4) != a2 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 4, a2);
  if ( *((struct IUnknown **)this + 5) != a3 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 5, a3);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
  {
    *((_QWORD *)this + 6) = a4;
    if ( a4 )
    {
      ModuleHandleA = GetModuleHandleA("SuperResExt.dll");
      if ( ModuleHandleA || (ModuleHandleA = GetModuleHandleA("DXGITestEffects.dll")) != 0 )
      {
        *((_QWORD *)this + 10) = GetProcAddress(ModuleHandleA, "DSRExAllocateDeviceMem");
        ProcAddress = GetProcAddress(ModuleHandleA, "DSRExFreeDeviceMem");
        *((_QWORD *)this + 11) = ProcAddress;
        if ( *((_QWORD *)this + 10) )
        {
          if ( ProcAddress )
            goto LABEL_13;
        }
        else
        {
          *((_QWORD *)this + 11) = 0;
        }
        *((_QWORD *)this + 10) = 0;
      }
    }
  }
LABEL_13:
  v16 = ((__int64 (__fastcall *)(struct ID3D12Device *))(*v13)->lpVtbl->GetNodeCount)(*v13);
  v17 = v16;
  v55 = v16;
  if ( !v16 )
  {
    RootSignatureHelper = -2147024809;
    v19 = 2384;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
      (const char *)(unsigned int)RootSignatureHelper,
      (int)v54);
    return (unsigned int)RootSignatureHelper;
  }
  *((_QWORD *)this + 14) = *(_QWORD *)a9;
  *((_QWORD *)this + 13) = *(_QWORD *)a8;
  *((_DWORD *)this + 32) = a5;
  *((_DWORD *)this + 33) = a6;
  *((_DWORD *)this + 24) = v16;
  *((_DWORD *)this + 25) = a7;
  v21 = !*(&g_AutoSRConfig + 4) && DeviceSupportsCrossAdapterRT(*v13);
  *((_BYTE *)this + 136) = v21;
  if ( *(&g_AutoSRConfig + 6) )
  {
    v22 = "Cross adapter RT ? Yes";
    if ( !v21 )
      v22 = "Cross adapter RT ? No";
    DebugPrint(v22);
  }
  v64 = 2;
  v65 = 1;
  v66 = 0;
  v67 = -1;
  v56[0] = 0;
  v56[1] = 1;
  v56[3] = 5;
  v56[2] = &v64;
  v69 = 0;
  v72 = 0;
  v74 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v71 = 8;
  v73 = 2139095039;
  v70 = 1;
  v75 = 5;
  v57[0] = 1;
  v57[2] = 1;
  v58 = v56;
  v59 = 1;
  p_si128 = &si128;
  v61 = 1;
  RootSignatureHelper = CreateRootSignatureHelper(
                          (struct ID3D12Device4 *)a2,
                          (struct CD3DX12_VERSIONED_ROOT_SIGNATURE_DESC *)v57,
                          (struct ID3D12RootSignature **)this + 7);
  if ( RootSignatureHelper < 0 )
  {
    v19 = 2422;
    goto LABEL_15;
  }
  RootSignatureHelper = ((__int64 (__fastcall *)(struct ID3D12Device *, _QWORD, GUID *, char *))(*v13)->lpVtbl->CreateCommandAllocator)(
                          *v13,
                          0,
                          &GUID_6102dee4_af59_4b09_b999_b44d73f09b24,
                          (char *)this + 72);
  if ( RootSignatureHelper < 0 )
  {
    v19 = 2427;
    goto LABEL_15;
  }
  RootSignatureHelper = SREffectRenderPassDx12::WaitableFence::Initialize(this, (struct ID3D12Device4 *)a2);
  if ( RootSignatureHelper < 0 )
  {
    v19 = 2432;
    goto LABEL_15;
  }
  try
  {
    v23 = v17;
    v24 = *((_QWORD *)this + 18);
    v25 = (*((_QWORD *)this + 19) - v24) >> 3;
    if ( v17 >= v25 )
    {
      if ( v17 > v25 )
      {
        if ( v17 <= (*((_QWORD *)this + 20) - v24) >> 3 )
          *((_QWORD *)this + 19) = std::_Uninitialized_value_construct_n<std::allocator<ATL::CComPtr<IDXGIResource>>>(
                                     *((_QWORD *)this + 19),
                                     v17 - v25);
        else
          std::vector<ATL::CComPtr<ID3D11Fence>>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 144, v17);
      }
    }
    else
    {
      v26 = v24 + 8 * v17;
      std::_Destroy_range<std::allocator<ATL::CComPtr<ID3D12Resource>>>(v26, *((_QWORD *)this + 19));
      *((_QWORD *)this + 19) = v26;
    }
    v27 = *((_QWORD *)this + 21);
    v28 = (*((_QWORD *)this + 22) - v27) >> 3;
    if ( v17 >= v28 )
    {
      if ( v17 > v28 )
      {
        if ( v17 <= (*((_QWORD *)this + 23) - v27) >> 3 )
          *((_QWORD *)this + 22) = std::_Uninitialized_value_construct_n<std::allocator<ATL::CComPtr<IDXGIResource>>>(
                                     *((_QWORD *)this + 22),
                                     v17 - v28);
        else
          std::vector<ATL::CComPtr<ID3D11Fence>>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 168, v17);
      }
    }
    else
    {
      v29 = v27 + 8 * v17;
      std::_Destroy_range<std::allocator<ATL::CComPtr<ID3D12Resource>>>(v29, *((_QWORD *)this + 22));
      *((_QWORD *)this + 22) = v29;
    }
    v30 = (_QWORD *)((char *)this + 192);
    v31 = *((_QWORD *)this + 24);
    v32 = (*((_QWORD *)this + 25) - v31) >> 3;
    if ( v17 >= v32 )
    {
      if ( v17 > v32 )
      {
        if ( v17 <= (*((_QWORD *)this + 26) - v31) >> 3 )
          *((_QWORD *)this + 25) = std::_Uninitialized_value_construct_n<std::allocator<ATL::CComPtr<IDXGIResource>>>(
                                     *((_QWORD *)this + 25),
                                     v17 - v32);
        else
          std::vector<ATL::CComPtr<ID3D11Fence>>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 192, v17);
      }
    }
    else
    {
      v33 = v31 + 8 * v17;
      std::_Destroy_range<std::allocator<ATL::CComPtr<ID3D12Resource>>>(v33, *((_QWORD *)this + 25));
      *((_QWORD *)this + 25) = v33;
    }
    v34 = a7 * (unsigned int)v17;
    v35 = v34;
    v36 = *((_QWORD *)this + 27);
    v37 = (*((_QWORD *)this + 28) - v36) >> 3;
    if ( v34 >= v37 )
    {
      if ( v34 > v37 )
      {
        if ( v34 <= (*((_QWORD *)this + 29) - v36) >> 3 )
          *((_QWORD *)this + 28) = std::_Uninitialized_value_construct_n<std::allocator<ATL::CComPtr<IDXGIResource>>>(
                                     *((_QWORD *)this + 28),
                                     v34 - v37);
        else
          std::vector<ATL::CComPtr<ID3D11Fence>>::_Resize_reallocate<std::_Value_init_tag>(
            (char *)this + 216,
            a7 * (unsigned int)v17);
      }
    }
    else
    {
      v38 = v36 + 8 * v34;
      std::_Destroy_range<std::allocator<ATL::CComPtr<ID3D12Resource>>>(v38, *((_QWORD *)this + 28));
      *((_QWORD *)this + 28) = v38;
    }
    v39 = *((_QWORD *)this + 30);
    v40 = (*((_QWORD *)this + 31) - v39) >> 3;
    if ( v35 >= v40 )
    {
      if ( v35 > v40 )
      {
        if ( v35 <= (*((_QWORD *)this + 32) - v39) >> 3 )
          *((_QWORD *)this + 31) = std::_Uninitialized_value_construct_n<std::allocator<ATL::CComPtr<IDXGIResource>>>(
                                     *((_QWORD *)this + 31),
                                     v35 - v40);
        else
          std::vector<ATL::CComPtr<ID3D11Fence>>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 240, v35);
      }
    }
    else
    {
      v41 = v39 + 8 * v35;
      std::_Destroy_range<std::allocator<ATL::CComPtr<ID3D12Resource>>>(v41, *((_QWORD *)this + 31));
      *((_QWORD *)this + 31) = v41;
    }
    v42 = *((_QWORD *)this + 34);
    v43 = (*((_QWORD *)this + 35) - v42) >> 3;
    if ( v17 >= v43 )
    {
      if ( v17 > v43 )
      {
        if ( v17 <= (*((_QWORD *)this + 36) - v42) >> 3 )
          *((_QWORD *)this + 35) = std::_Uninitialized_value_construct_n<std::allocator<ATL::CComPtr<IDXGIResource>>>(
                                     *((_QWORD *)this + 35),
                                     v17 - v43);
        else
          std::vector<ATL::CComPtr<ID3D11Fence>>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 272, v17);
      }
    }
    else
    {
      v44 = v42 + 8 * v17;
      std::_Destroy_range<std::allocator<ATL::CComPtr<ID3D12Resource>>>(v44, *((_QWORD *)this + 35));
      *((_QWORD *)this + 35) = v44;
    }
    v45 = *((_QWORD *)this + 37);
    v46 = *((_QWORD *)this + 38);
    v47 = (v46 - v45) >> 3;
    if ( v23 < v47 )
    {
      v48 = v45 + 8 * v23;
LABEL_72:
      *((_QWORD *)this + 38) = v48;
      goto LABEL_73;
    }
    if ( v23 > v47 )
    {
      if ( v23 <= (*((_QWORD *)this + 39) - v45) >> 3 )
      {
        v49 = 8 * (v23 - v47);
        memset_0(*((void **)this + 38), 0, v49);
        v48 = v49 + v46;
        goto LABEL_72;
      }
      std::vector<HDRConvertCb *>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 296, v23);
    }
LABEL_73:
    std::vector<ATL::CComPtr<ID3D12Resource>>::clear((char *)this + 344);
    std::vector<wistd::unique_ptr<void,wil::virtualalloc_deleter>>::clear((char *)this + 320);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
    {
      v50 = *((_QWORD *)this + 46);
      if ( v50 != *((_QWORD *)this + 47) )
        *((_QWORD *)this + 47) = v50;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  v51 = 0;
  if ( v55 )
  {
    while ( 1 )
    {
      v62[3] = 1 << v51;
      v62[1] = 1;
      v62[0] = 2;
      v62[2] = 0;
      Resources = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, GUID *, __int64))(**((_QWORD **)this + 4) + 112LL))(
                    *((_QWORD *)this + 4),
                    v62,
                    &GUID_8efb471d_616c_4f49_90f7_127bb763fa51,
                    *((_QWORD *)this + 21) + 8 * v51);
      if ( Resources < 0 )
        break;
      v63[3] = 1 << v51;
      v63[1] = 3;
      v63[0] = 0;
      v63[2] = 1;
      Resources = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, GUID *, __int64))(**((_QWORD **)this + 4) + 112LL))(
                    *((_QWORD *)this + 4),
                    v63,
                    &GUID_8efb471d_616c_4f49_90f7_127bb763fa51,
                    *v30 + 8 * v51);
      if ( Resources < 0 )
      {
        v53 = 2483;
        goto LABEL_89;
      }
      Resources = SREffectRenderPassDx12::CShaderResourceBuilder::CreateResources(this, v51);
      if ( Resources < 0 )
      {
        v53 = 2488;
        goto LABEL_89;
      }
      v54 = &GUID_5b160d0f_ac1b_4185_8ba8_b3ae42a5a455;
      Resources = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 408LL))(
                    *((_QWORD *)this + 4),
                    (unsigned int)(1 << v51),
                    0,
                    0);
      if ( Resources < 0 )
      {
        v53 = 2493;
        goto LABEL_89;
      }
      v51 = (unsigned int)(v51 + 1);
      if ( (unsigned int)v51 >= v55 )
        goto LABEL_82;
    }
    v53 = 2473;
LABEL_89:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v53,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
      (const char *)(unsigned int)Resources,
      (int)v54);
    return (unsigned int)Resources;
  }
  else
  {
LABEL_82:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_OverlayIndicator>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_OverlayIndicator>::GetImpl'::`2'::impl) )
    {
      RootSignatureHelper = SREffectRenderPassDx12::CShaderResourceBuilder::CreateOverlayResource(this);
      if ( RootSignatureHelper < 0 )
      {
        v19 = 2498;
        goto LABEL_15;
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800bb448  push    rbx
0x1800bb44a  push    rsi
0x1800bb44b  push    rdi
0x1800bb44c  push    r12
0x1800bb44e  push    r13
0x1800bb450  push    r14
0x1800bb452  push    r15
0x1800bb454  sub     rsp, 110h
0x1800bb45b  mov     rax, cs:__security_cookie
0x1800bb462  xor     rax, rsp
0x1800bb465  mov     [rsp+148h+var_40], rax
0x1800bb46d  mov     r14, r9
0x1800bb470  mov     rbx, r8
0x1800bb473  mov     rsi, rdx
0x1800bb476  mov     rdi, rcx
0x1800bb479  lea     r13, [rcx+20h]
0x1800bb47d  cmp     [r13+0], rdx
0x1800bb481  jz      short loc_1800BB48B
0x1800bb483  mov     rcx, r13; struct IUnknown **
0x1800bb486  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800bb48b  lea     rcx, [rdi+28h]; struct IUnknown **
0x1800bb48f  cmp     [rcx], rbx
0x1800bb492  jz      short loc_1800BB49C
0x1800bb494  mov     rdx, rbx; struct IUnknown *
0x1800bb497  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800bb49c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x1800bb4a3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x1800bb4a8  test    al, al
0x1800bb4aa  jz      short loc_1800BB521
0x1800bb4ac  mov     [rdi+30h], r14
0x1800bb4b0  test    r14, r14
0x1800bb4b3  jz      short loc_1800BB521
0x1800bb4b5  lea     rcx, aSuperresextDll; "SuperResExt.dll"
0x1800bb4bc  call    cs:__imp_GetModuleHandleA
0x1800bb4c2  mov     rbx, rax
0x1800bb4c5  xor     r14d, r14d
0x1800bb4c8  test    rax, rax
0x1800bb4cb  jnz     short loc_1800BB4E2
0x1800bb4cd  lea     rcx, aDxgitesteffect; "DXGITestEffects.dll"
0x1800bb4d4  call    cs:__imp_GetModuleHandleA
0x1800bb4da  mov     rbx, rax
0x1800bb4dd  test    rax, rax
0x1800bb4e0  jz      short loc_1800BB524
0x1800bb4e2  lea     rdx, aDsrexallocated; "DSRExAllocateDeviceMem"
0x1800bb4e9  mov     rcx, rbx; hModule
0x1800bb4ec  call    cs:__imp_GetProcAddress
0x1800bb4f2  mov     [rdi+50h], rax
0x1800bb4f6  lea     rdx, aDsrexfreedevic; "DSRExFreeDeviceMem"
0x1800bb4fd  mov     rcx, rbx; hModule
0x1800bb500  call    cs:__imp_GetProcAddress
0x1800bb506  mov     [rdi+58h], rax
0x1800bb50a  cmp     [rdi+50h], r14
0x1800bb50e  jnz     short loc_1800BB516
0x1800bb510  mov     [rdi+58h], r14
0x1800bb514  jmp     short loc_1800BB51B
0x1800bb516  test    rax, rax
0x1800bb519  jnz     short loc_1800BB524
0x1800bb51b  mov     [rdi+50h], r14
0x1800bb51f  jmp     short loc_1800BB524
0x1800bb521  xor     r14d, r14d
0x1800bb524  mov     rcx, [r13+0]
0x1800bb528  mov     rax, [rcx]
0x1800bb52b  mov     rax, [rax+38h]
0x1800bb52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb534  mov     r15d, eax
0x1800bb537  mov     [rsp+148h+var_108], r15d
0x1800bb53c  test    eax, eax
0x1800bb53e  jnz     short loc_1800BB568
0x1800bb540  mov     ebx, 80070057h
0x1800bb545  mov     edx, 950h; void *
0x1800bb54a  mov     rcx, [rsp+148h]; this
0x1800bb552  mov     r9d, ebx; char *
0x1800bb555  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800bb55c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb561  mov     eax, ebx
0x1800bb563  jmp     loc_1800BBBC4
0x1800bb568  mov     rax, [rsp+148h+arg_40]
0x1800bb570  mov     rcx, [rax]
0x1800bb573  mov     [rdi+70h], rcx
0x1800bb577  mov     rax, [rsp+148h+arg_38]
0x1800bb57f  mov     rcx, [rax]
0x1800bb582  mov     [rdi+68h], rcx
0x1800bb586  mov     eax, [rsp+148h+arg_20]
0x1800bb58d  mov     [rdi+80h], eax
0x1800bb593  mov     eax, [rsp+148h+arg_28]
0x1800bb59a  mov     [rdi+84h], eax
0x1800bb5a0  mov     [rdi+60h], r15d
0x1800bb5a4  mov     eax, [rsp+148h+arg_30]
0x1800bb5ab  mov     [rdi+64h], eax
0x1800bb5ae  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+4, r14b; AutoSRConfig g_AutoSRConfig
0x1800bb5b5  jnz     short loc_1800BB5CF
0x1800bb5b7  mov     rcx, [r13+0]; struct ID3D12Device *
0x1800bb5bb  call    ?DeviceSupportsCrossAdapterRT@@YA_NPEAUID3D12Device@@@Z; DeviceSupportsCrossAdapterRT(ID3D12Device *)
0x1800bb5c0  test    al, al
0x1800bb5c2  jz      short loc_1800BB5CF
0x1800bb5c4  mov     r12d, 1
0x1800bb5ca  mov     al, r12b
0x1800bb5cd  jmp     short loc_1800BB5D8
0x1800bb5cf  mov     al, r14b
0x1800bb5d2  mov     r12d, 1
0x1800bb5d8  mov     [rdi+88h], al
0x1800bb5de  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, r14b; AutoSRConfig g_AutoSRConfig
0x1800bb5e5  jz      short loc_1800BB600
0x1800bb5e7  lea     rdx, aCrossAdapterRt; "Cross adapter RT ? No"
0x1800bb5ee  lea     rcx, aCrossAdapterRt_0; "Cross adapter RT ? Yes"
0x1800bb5f5  test    al, al
0x1800bb5f7  cmovz   rcx, rdx; Format
0x1800bb5fb  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800bb600  mov     [rsp+148h+var_90], 2
0x1800bb60b  mov     [rsp+148h+var_8C], 1
0x1800bb617  mov     [rsp+148h+var_84], r14d
0x1800bb61f  mov     [rsp+148h+var_80], 0FFFFFFFFh
0x1800bb62a  mov     [rsp+148h+var_100], 0
0x1800bb633  mov     [rsp+148h+var_F8], 1
0x1800bb63c  mov     [rsp+148h+var_E8], 5
0x1800bb645  mov     ecx, 5
0x1800bb64a  lea     rax, [rsp+148h+var_90]
0x1800bb652  mov     [rsp+148h+var_F0], rax
0x1800bb657  mov     [rsp+148h+var_68], r14d
0x1800bb65f  mov     [rsp+148h+var_5C], r14
0x1800bb667  mov     [rsp+148h+var_50], 0
0x1800bb673  movdqa  xmm0, cs:__xmm@00000003000000030000000300000000
0x1800bb67b  movdqu  [rsp+148h+var_78], xmm0
0x1800bb684  mov     [rsp+148h+var_60], 8
0x1800bb68f  mov     [rsp+148h+var_54], 7F7FFFFFh
0x1800bb69a  mov     [rsp+148h+var_64], r12d
0x1800bb6a2  mov     [rsp+148h+var_48], ecx
0x1800bb6a9  mov     [rsp+148h+var_E0], r12d
0x1800bb6ae  mov     [rsp+148h+var_D8], r12d
0x1800bb6b3  lea     rax, [rsp+148h+var_100]
0x1800bb6b8  mov     [rsp+148h+var_D0], rax
0x1800bb6bd  mov     [rsp+148h+var_C8], r12d
0x1800bb6c5  lea     rax, [rsp+148h+var_78]
0x1800bb6cd  mov     [rsp+148h+var_C0], rax
0x1800bb6d5  mov     [rsp+148h+var_B8], r12d
0x1800bb6dd  lea     r8, [rdi+38h]; struct ID3D12RootSignature **
0x1800bb6e1  lea     rdx, [rsp+148h+var_E0]; struct CD3DX12_VERSIONED_ROOT_SIGNATURE_DESC *
0x1800bb6e6  mov     rcx, rsi; struct ID3D12Device4 *
0x1800bb6e9  call    ?CreateRootSignatureHelper@@YAJPEAUID3D12Device4@@AEAUCD3DX12_VERSIONED_ROOT_SIGNATURE_DESC@@PEAPEAUID3D12RootSignature@@@Z; CreateRootSignatureHelper(ID3D12Device4 *,CD3DX12_VERSIONED_ROOT_SIGNATURE_DESC &,ID3D12RootSignature * *)
0x1800bb6ee  mov     ebx, eax
0x1800bb6f0  test    eax, eax
0x1800bb6f2  jns     short loc_1800BB6FE
0x1800bb6f4  mov     edx, 976h
0x1800bb6f9  jmp     loc_1800BB54A
0x1800bb6fe  mov     rcx, [r13+0]
0x1800bb702  mov     rax, [rcx]
0x1800bb705  lea     r9, [rdi+48h]
0x1800bb709  lea     r8, _GUID_6102dee4_af59_4b09_b999_b44d73f09b24
0x1800bb710  xor     edx, edx
0x1800bb712  mov     rax, [rax+48h]
0x1800bb716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb71b  mov     ebx, eax
0x1800bb71d  test    eax, eax
0x1800bb71f  jns     short loc_1800BB72B
0x1800bb721  mov     edx, 97Bh
0x1800bb726  jmp     loc_1800BB54A
0x1800bb72b  mov     rdx, rsi; struct ID3D12Device4 *
0x1800bb72e  mov     rcx, rdi; this
0x1800bb731  call    ?Initialize@WaitableFence@SREffectRenderPassDx12@@QEAAJPEAUID3D12Device4@@@Z; SREffectRenderPassDx12::WaitableFence::Initialize(ID3D12Device4 *)
0x1800bb736  mov     ebx, eax
0x1800bb738  test    eax, eax
0x1800bb73a  jns     short loc_1800BB746
0x1800bb73c  mov     edx, 980h
0x1800bb741  jmp     loc_1800BB54A
0x1800bb746  lea     r14, [rdi+90h]
0x1800bb74d  mov     rsi, r15
0x1800bb750  mov     r8, [r14]
0x1800bb753  mov     rcx, [r14+8]
0x1800bb757  sub     rcx, r8
0x1800bb75a  sar     rcx, 3
0x1800bb75e  cmp     r15, rcx
0x1800bb761  jnb     short loc_1800BB779
0x1800bb763  lea     rbx, [r8+r15*8]
0x1800bb767  mov     rdx, [r14+8]
0x1800bb76b  mov     rcx, rbx
0x1800bb76e  call    ??$_Destroy_range@V?$allocator@V?$CComPtr@UID3D12Resource@@@ATL@@@std@@@std@@YAXPEAV?$CComPtr@UID3D12Resource@@@ATL@@QEAV12@AEAV?$allocator@V?$CComPtr@UID3D12Resource@@@ATL@@@0@@Z; std::_Destroy_range<std::allocator<ATL::CComPtr<ID3D12Resource>>>(ATL::CComPtr<ID3D12Resource> *,ATL::CComPtr<ID3D12Resource> * const,std::allocator<ATL::CComPtr<ID3D12Resource>> &)
0x1800bb773  mov     [r14+8], rbx
0x1800bb777  jmp     short loc_1800BB7A8
0x1800bb779  jbe     short loc_1800BB7A8
0x1800bb77b  mov     rax, [r14+10h]
0x1800bb77f  sub     rax, r8
0x1800bb782  sar     rax, 3
0x1800bb786  mov     rdx, rsi
0x1800bb789  cmp     rsi, rax
0x1800bb78c  jbe     short loc_1800BB798
0x1800bb78e  mov     rcx, r14
0x1800bb791  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@V?$CComPtr@UID3D11Fence@@@ATL@@V?$allocator@V?$CComPtr@UID3D11Fence@@@ATL@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ATL::CComPtr<ID3D11Fence>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800bb796  jmp     short loc_1800BB7A8
0x1800bb798  sub     rdx, rcx
0x1800bb79b  mov     rcx, [r14+8]
0x1800bb79f  call    ??$_Uninitialized_value_construct_n@V?$allocator@V?$CComPtr@UIDXGIResource@@@ATL@@@std@@@std@@YAPEAV?$CComPtr@UIDXGIResource@@@ATL@@PEAV12@_KAEAV?$allocator@V?$CComPtr@UIDXGIResource@@@ATL@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<ATL::CComPtr<IDXGIResource>>>(ATL::CComPtr<IDXGIResource> *,unsigned __int64,std::allocator<ATL::CComPtr<IDXGIResource>> &)
0x1800bb7a4  mov     [r14+8], rax
0x1800bb7a8  lea     r14, [rdi+0A8h]
0x1800bb7af  mov     r8, [r14]
0x1800bb7b2  mov     rcx, [r14+8]
0x1800bb7b6  sub     rcx, r8
0x1800bb7b9  sar     rcx, 3
0x1800bb7bd  cmp     rsi, rcx
0x1800bb7c0  jnb     short loc_1800BB7D8
0x1800bb7c2  lea     rbx, [r8+r15*8]
0x1800bb7c6  mov     rdx, [r14+8]
0x1800bb7ca  mov     rcx, rbx
0x1800bb7cd  call    ??$_Destroy_range@V?$allocator@V?$CComPtr@UID3D12Resource@@@ATL@@@std@@@std@@YAXPEAV?$CComPtr@UID3D12Resource@@@ATL@@QEAV12@AEAV?$allocator@V?$CComPtr@UID3D12Resource@@@ATL@@@0@@Z; std::_Destroy_range<std::allocator<ATL::CComPtr<ID3D12Resource>>>(ATL::CComPtr<ID3D12Resource> *,ATL::CComPtr<ID3D12Resource> * const,std::allocator<ATL::CComPtr<ID3D12Resource>> &)
0x1800bb7d2  mov     [r14+8], rbx
0x1800bb7d6  jmp     short loc_1800BB807
0x1800bb7d8  jbe     short loc_1800BB807
0x1800bb7da  mov     rax, [r14+10h]
0x1800bb7de  sub     rax, r8
0x1800bb7e1  sar     rax, 3
0x1800bb7e5  mov     rdx, rsi
0x1800bb7e8  cmp     rsi, rax
0x1800bb7eb  jbe     short loc_1800BB7F7
0x1800bb7ed  mov     rcx, r14
0x1800bb7f0  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@V?$CComPtr@UID3D11Fence@@@ATL@@V?$allocator@V?$CComPtr@UID3D11Fence@@@ATL@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ATL::CComPtr<ID3D11Fence>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800bb7f5  jmp     short loc_1800BB807
0x1800bb7f7  sub     rdx, rcx
0x1800bb7fa  mov     rcx, [r14+8]
0x1800bb7fe  call    ??$_Uninitialized_value_construct_n@V?$allocator@V?$CComPtr@UIDXGIResource@@@ATL@@@std@@@std@@YAPEAV?$CComPtr@UIDXGIResource@@@ATL@@PEAV12@_KAEAV?$allocator@V?$CComPtr@UIDXGIResource@@@ATL@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<ATL::CComPtr<IDXGIResource>>>(ATL::CComPtr<IDXGIResource> *,unsigned __int64,std::allocator<ATL::CComPtr<IDXGIResource>> &)
0x1800bb803  mov     [r14+8], rax
0x1800bb807  lea     r13, [rdi+0C0h]
0x1800bb80e  mov     r8, [r13+0]
0x1800bb812  mov     rcx, [r13+8]
0x1800bb816  sub     rcx, r8
0x1800bb819  sar     rcx, 3
0x1800bb81d  cmp     rsi, rcx
0x1800bb820  jnb     short loc_1800BB838
0x1800bb822  lea     rbx, [r8+r15*8]
0x1800bb826  mov     rdx, [r13+8]
0x1800bb82a  mov     rcx, rbx
0x1800bb82d  call    ??$_Destroy_range@V?$allocator@V?$CComPtr@UID3D12Resource@@@ATL@@@std@@@std@@YAXPEAV?$CComPtr@UID3D12Resource@@@ATL@@QEAV12@AEAV?$allocator@V?$CComPtr@UID3D12Resource@@@ATL@@@0@@Z; std::_Destroy_range<std::allocator<ATL::CComPtr<ID3D12Resource>>>(ATL::CComPtr<ID3D12Resource> *,ATL::CComPtr<ID3D12Resource> * const,std::allocator<ATL::CComPtr<ID3D12Resource>> &)
0x1800bb832  mov     [r13+8], rbx
0x1800bb836  jmp     short loc_1800BB867
0x1800bb838  jbe     short loc_1800BB867
0x1800bb83a  mov     rax, [r13+10h]
0x1800bb83e  sub     rax, r8
0x1800bb841  sar     rax, 3
0x1800bb845  mov     rdx, rsi
0x1800bb848  cmp     rsi, rax
0x1800bb84b  jbe     short loc_1800BB857
0x1800bb84d  mov     rcx, r13
0x1800bb850  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@V?$CComPtr@UID3D11Fence@@@ATL@@V?$allocator@V?$CComPtr@UID3D11Fence@@@ATL@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ATL::CComPtr<ID3D11Fence>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800bb855  jmp     short loc_1800BB867
0x1800bb857  sub     rdx, rcx
0x1800bb85a  mov     rcx, [r13+8]
0x1800bb85e  call    ??$_Uninitialized_value_construct_n@V?$allocator@V?$CComPtr@UIDXGIResource@@@ATL@@@std@@@std@@YAPEAV?$CComPtr@UIDXGIResource@@@ATL@@PEAV12@_KAEAV?$allocator@V?$CComPtr@UIDXGIResource@@@ATL@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<ATL::CComPtr<IDXGIResource>>>(ATL::CComPtr<IDXGIResource> *,unsigned __int64,std::allocator<ATL::CComPtr<IDXGIResource>> &)
0x1800bb863  mov     [r13+8], rax
0x1800bb867  lea     r15, [rdi+0D8h]
0x1800bb86e  mov     eax, esi
0x1800bb870  imul    eax, [rsp+148h+arg_30]
0x1800bb878  mov     r14d, eax
0x1800bb87b  mov     r8, [r15]
0x1800bb87e  mov     rcx, [r15+8]
0x1800bb882  sub     rcx, r8
0x1800bb885  sar     rcx, 3
0x1800bb889  cmp     r14, rcx
0x1800bb88c  jnb     short loc_1800BB8A4
0x1800bb88e  lea     rbx, [r8+rax*8]
0x1800bb892  mov     rdx, [r15+8]
0x1800bb896  mov     rcx, rbx
0x1800bb899  call    ??$_Destroy_range@V?$allocator@V?$CComPtr@UID3D12Resource@@@ATL@@@std@@@std@@YAXPEAV?$CComPtr@UID3D12Resource@@@ATL@@QEAV12@AEAV?$allocator@V?$CComPtr@UID3D12Resource@@@ATL@@@0@@Z; std::_Destroy_range<std::allocator<ATL::CComPtr<ID3D12Resource>>>(ATL::CComPtr<ID3D12Resource> *,ATL::CComPtr<ID3D12Resource> * const,std::allocator<ATL::CComPtr<ID3D12Resource>> &)
0x1800bb89e  mov     [r15+8], rbx
0x1800bb8a2  jmp     short loc_1800BB8D3
0x1800bb8a4  jbe     short loc_1800BB8D3
0x1800bb8a6  mov     rax, [r15+10h]
0x1800bb8aa  sub     rax, r8
0x1800bb8ad  sar     rax, 3
0x1800bb8b1  mov     rdx, r14
0x1800bb8b4  cmp     r14, rax
0x1800bb8b7  jbe     short loc_1800BB8C3
0x1800bb8b9  mov     rcx, r15
0x1800bb8bc  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@V?$CComPtr@UID3D11Fence@@@ATL@@V?$allocator@V?$CComPtr@UID3D11Fence@@@ATL@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ATL::CComPtr<ID3D11Fence>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800bb8c1  jmp     short loc_1800BB8D3
0x1800bb8c3  sub     rdx, rcx
0x1800bb8c6  mov     rcx, [r15+8]
0x1800bb8ca  call    ??$_Uninitialized_value_construct_n@V?$allocator@V?$CComPtr@UIDXGIResource@@@ATL@@@std@@@std@@YAPEAV?$CComPtr@UIDXGIResource@@@ATL@@PEAV12@_KAEAV?$allocator@V?$CComPtr@UIDXGIResource@@@ATL@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<ATL::CComPtr<IDXGIResource>>>(ATL::CComPtr<IDXGIResource> *,unsigned __int64,std::allocator<ATL::CComPtr<IDXGIResource>> &)
0x1800bb8cf  mov     [r15+8], rax
0x1800bb8d3  lea     r15, [rdi+0F0h]
0x1800bb8da  mov     r8, [r15]
0x1800bb8dd  mov     rcx, [r15+8]
0x1800bb8e1  sub     rcx, r8
0x1800bb8e4  sar     rcx, 3
0x1800bb8e8  cmp     r14, rcx
0x1800bb8eb  jnb     short loc_1800BB903
0x1800bb8ed  lea     rbx, [r8+r14*8]
0x1800bb8f1  mov     rdx, [r15+8]
0x1800bb8f5  mov     rcx, rbx
0x1800bb8f8  call    ??$_Destroy_range@V?$allocator@V?$CComPtr@UID3D12Resource@@@ATL@@@std@@@std@@YAXPEAV?$CComPtr@UID3D12Resource@@@ATL@@QEAV12@AEAV?$allocator@V?$CComPtr@UID3D12Resource@@@ATL@@@0@@Z; std::_Destroy_range<std::allocator<ATL::CComPtr<ID3D12Resource>>>(ATL::CComPtr<ID3D12Resource> *,ATL::CComPtr<ID3D12Resource> * const,std::allocator<ATL::CComPtr<ID3D12Resource>> &)
0x1800bb8fd  mov     [r15+8], rbx
0x1800bb901  jmp     short loc_1800BB935
0x1800bb903  jbe     short loc_1800BB935
0x1800bb905  mov     rax, [r15+10h]
0x1800bb909  sub     rax, r8
0x1800bb90c  sar     rax, 3
0x1800bb910  cmp     r14, rax
0x1800bb913  jbe     short loc_1800BB922
0x1800bb915  mov     rdx, r14
0x1800bb918  mov     rcx, r15
0x1800bb91b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@V?$CComPtr@UID3D11Fence@@@ATL@@V?$allocator@V?$CComPtr@UID3D11Fence@@@ATL@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ATL::CComPtr<ID3D11Fence>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800bb920  jmp     short loc_1800BB935
0x1800bb922  sub     r14, rcx
  ... truncated ...
```
