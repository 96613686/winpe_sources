# SREffectRenderPassDx12::CShaderResourceBuilder::MakeSysMemHeapAndResource(ID3D12Device4 *,int,int,DXGI_FORMAT,bool,ID3D12Resource * *)

- ea: `0x1800bc4f4`
- end: `0x1800bc966`
- name: `?MakeSysMemHeapAndResource@CShaderResourceBuilder@SREffectRenderPassDx12@@AEAAJPEAUID3D12Device4@@HHW4DXGI_FORMAT@@_NPEAPEAUID3D12Resource@@@Z`
- size: `1138`
- prototype: `__int64 __fastcall(SREffectRenderPassDx12::CShaderResourceBuilder *__hidden this, struct ID3D12Device4 *, int, int, enum DXGI_FORMAT, bool, struct ID3D12Resource **)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b6ef4`
- `0x1800ba6d8`

## callees

- `0x18000c6b0`
- `0x180014750`
- `0x1800306f4`
- `0x180067d2c`
- `0x18006989c`
- `0x180075fa0`
- `0x180076f20`
- `0x1800b4a68`
- `0x1800b4a90`
- `0x1800b4b9c`
- `0x1800b4e30`
- `0x1800bc4f4`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800bc691`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800bc691`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800bc623`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800bc623`

## string_xrefs

- `0x1800bc641`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800bc6c1`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800bc726`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800bc843`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800bc5ef`: `Extension allocator failed, falling back to VirtualAlloc`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SREffectRenderPassDx12::CShaderResourceBuilder::MakeSysMemHeapAndResource(
        SREffectRenderPassDx12::CShaderResourceBuilder *this,
        struct ID3D12Device4 *a2,
        unsigned int a3,
        int a4,
        enum DXGI_FORMAT a5,
        bool a6,
        struct ID3D12Resource **a7)
{
  __int64 v8; // r12
  __int64 v11; // rcx
  __int64 (__fastcall *v12)(__int64, size_t); // rax
  void *v13; // rax
  CModule *v14; // rcx
  void *v15; // rbx
  _QWORD *v16; // rdx
  char *v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  unsigned int v21; // edi
  bool v22; // zf
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rdx
  _QWORD *v26; // rdx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rdx
  struct ID3D12Resource *v30; // rdx
  int *v31; // [rsp+20h] [rbp-B1h]
  int v32[2]; // [rsp+50h] [rbp-81h] BYREF
  struct ID3D12Resource *v33; // [rsp+58h] [rbp-79h] BYREF
  LPVOID lpAddress; // [rsp+60h] [rbp-71h] BYREF
  size_t Size; // [rsp+68h] [rbp-69h] BYREF
  __int64 *v36; // [rsp+70h] [rbp-61h] BYREF
  int v37; // [rsp+78h] [rbp-59h] BYREF
  const void *v38; // [rsp+80h] [rbp-51h] BYREF
  int v39; // [rsp+88h] [rbp-49h] BYREF
  __int64 v40; // [rsp+8Ch] [rbp-45h]
  int v41; // [rsp+94h] [rbp-3Dh]
  __int64 v42; // [rsp+98h] [rbp-39h]
  int v43; // [rsp+A0h] [rbp-31h]
  int v44; // [rsp+A4h] [rbp-2Dh]
  enum DXGI_FORMAT v45; // [rsp+A8h] [rbp-29h]
  __int64 v46; // [rsp+ACh] [rbp-25h]
  int v47; // [rsp+B4h] [rbp-1Dh]
  int v48; // [rsp+B8h] [rbp-19h]
  int v49; // [rsp+BCh] [rbp-15h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+47h]

  v8 = a3;
  Size = (a4 * ((4 * a3 + 127) & 0xFFFFFF80) + 0xFFFF) & 0xFFFF0000;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
  {
    v11 = *((_QWORD *)this + 6);
    if ( v11 )
    {
      v12 = (__int64 (__fastcall *)(__int64, size_t))*((_QWORD *)this + 10);
      if ( v12 )
      {
        v13 = (void *)v12(v11, Size);
        v15 = v13;
        lpAddress = v13;
        if ( v13 )
        {
          v16 = (_QWORD *)*((_QWORD *)this + 47);
          if ( v16 == *((_QWORD **)this + 48) )
          {
            std::vector<void *>::_Emplace_reallocate<void * &>((char *)this + 368, v16, &lpAddress);
            v15 = lpAddress;
          }
          else
          {
            *v16 = v13;
            *((_QWORD *)this + 47) += 8LL;
          }
          if ( v15 )
          {
            if ( a6 )
              memset_0(v15, 0, Size);
            goto LABEL_21;
          }
        }
        else
        {
          if ( *(&g_AutoSRConfig + 6) )
            DebugPrint("Extension allocator failed, falling back to VirtualAlloc");
          CModule::RecordJournalImpl(v14, 0, "Ext allocator failed");
          *((_QWORD *)this + 10) = 0;
          *((_QWORD *)this + 11) = 0;
        }
      }
    }
  }
  v15 = VirtualAlloc(0, Size, 0x3000u, 4u);
  lpAddress = v15;
  if ( !v15 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8AD,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
      (const char *)0x8007000ELL,
      (int)v31);
    return 2147942414LL;
  }
  v18 = (char *)this + 320;
  v19 = *((_QWORD *)this + 41);
  if ( v19 == *((_QWORD *)this + 42) )
    std::vector<wistd::unique_ptr<void,wil::virtualalloc_deleter>>::_Emplace_reallocate<wistd::unique_ptr<void,wil::virtualalloc_deleter>>(
      v18,
      v19,
      &lpAddress);
  else
    std::vector<wistd::unique_ptr<void,wil::virtualalloc_deleter>>::_Emplace_back_with_unused_capacity<wistd::unique_ptr<void,wil::virtualalloc_deleter>>(
      v18,
      &lpAddress);
  if ( lpAddress )
    VirtualFree(lpAddress, 0, 0x8000u);
LABEL_21:
  v36 = 0;
  v20 = ((__int64 (__fastcall *)(struct ID3D12Device4 *, GUID *, __int64 **))a2->lpVtbl->QueryInterface)(
          a2,
          &GUID_14eecffc_4df8_40f7_a118_5c816f45695e,
          &v36);
  v21 = v20;
  if ( v20 >= 0 )
  {
    *(_QWORD *)v32 = 0;
    v22 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) == 0;
    v23 = *v36;
    if ( v22 )
    {
      v24 = (*(__int64 (__fastcall **)(__int64 *, void *, GUID *, int *))(v23 + 384))(
              v36,
              v15,
              &GUID_6b3b2502_6e51_45b3_90ee_9884265e8df3,
              v32);
      v21 = v24;
      if ( v24 < 0 )
      {
        v25 = 2247;
        goto LABEL_26;
      }
    }
    else
    {
      v31 = v32;
      v24 = (*(__int64 (__fastcall **)(__int64 *, void *, size_t, GUID *))(v23 + 648))(
              v36,
              v15,
              Size,
              &GUID_6b3b2502_6e51_45b3_90ee_9884265e8df3);
      v21 = v24;
      if ( v24 < 0 )
      {
        v25 = 2243;
LABEL_26:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
          (const char *)(unsigned int)v24,
          (int)v31);
LABEL_27:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v32);
        goto LABEL_47;
      }
    }
    v26 = (_QWORD *)*((_QWORD *)this + 44);
    if ( v26 == *((_QWORD **)this + 45) )
    {
      std::vector<ATL::CComPtr<ID3D12Heap>>::_Emplace_reallocate<ATL::CComPtr<ID3D12Heap> &>(
        (char *)this + 344,
        v26,
        v32);
    }
    else
    {
      v27 = *(_QWORD *)v32;
      *v26 = *(_QWORD *)v32;
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
      *((_QWORD *)this + 44) += 8LL;
    }
    v40 = 0;
    v41 = 0;
    v49 = 0;
    v39 = 3;
    v45 = a5;
    v47 = 1;
    v42 = v8;
    v43 = a4;
    v44 = 65537;
    v48 = (*((_BYTE *)this + 136) != 0) + 16;
    v46 = 1;
    v33 = 0;
    v28 = ((__int64 (__fastcall *)(struct ID3D12Device4 *, _QWORD, _QWORD, int *))a2->lpVtbl->CreatePlacedResource)(
            a2,
            *(_QWORD *)v32,
            0,
            &v39);
    v21 = v28;
    if ( v28 >= 0 )
    {
      v38 = v15;
      v37 = 128;
      v28 = ((__int64 (__fastcall *)(struct ID3D12Resource *, __int64 *, __int64, int *))v33->lpVtbl->SetPrivateData)(
              v33,
              DIRECTSR_EXT_PITCH_ALIGNMENT,
              4,
              &v37);
      v21 = v28;
      if ( v28 >= 0 )
      {
        v28 = ((__int64 (__fastcall *)(struct ID3D12Resource *, __int64 *, __int64, const void **))v33->lpVtbl->SetPrivateData)(
                v33,
                DIRECTSR_EXT_CPUVA,
                8,
                &v38);
        v21 = v28;
        if ( v28 >= 0 )
        {
          v28 = ((__int64 (__fastcall *)(struct ID3D12Resource *, __int64 *, __int64, size_t *))v33->lpVtbl->SetPrivateData)(
                  v33,
                  DIRECTSR_EXT_RES_SIZE,
                  8,
                  &Size);
          v21 = v28;
          if ( v28 >= 0 )
          {
            v30 = v33;
            v33 = 0;
            *a7 = v30;
            if ( *(&g_AutoSRConfig + 6) )
              DebugPrint("Allocated SysMemHeap resource 0x%p at VA 0x%p", v30, v38);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v32);
            v21 = 0;
            goto LABEL_47;
          }
          v29 = 2283;
        }
        else
        {
          v29 = 2282;
        }
      }
      else
      {
        v29 = 2281;
      }
    }
    else
    {
      v29 = 2274;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
      (const char *)(unsigned int)v28,
      0);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8BD,
    (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
    (const char *)(unsigned int)v20,
    (int)v31);
LABEL_47:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
  return v21;
}

```

## disassembly

```asm
0x1800bc4f4  push    rbp
0x1800bc4f6  push    rbx
0x1800bc4f7  push    rsi
0x1800bc4f8  push    rdi
0x1800bc4f9  push    r12
0x1800bc4fb  push    r13
0x1800bc4fd  push    r14
0x1800bc4ff  push    r15
0x1800bc501  lea     rbp, [rsp-7]
0x1800bc506  sub     rsp, 0D8h
0x1800bc50d  mov     rax, cs:__security_cookie
0x1800bc514  xor     rax, rsp
0x1800bc517  mov     [rbp+3Fh+var_50], rax
0x1800bc51b  mov     r13d, r9d
0x1800bc51e  mov     r12d, r8d
0x1800bc521  mov     r14, rdx
0x1800bc524  mov     rsi, rcx
0x1800bc527  mov     r15, [rbp+3Fh+arg_30]
0x1800bc52b  lea     eax, ds:7Fh[r12*4]
0x1800bc533  and     eax, 0FFFFFF80h
0x1800bc536  imul    eax, r9d
0x1800bc53a  add     eax, 0FFFFh
0x1800bc53f  mov     ecx, 0FFFF0000h
0x1800bc544  and     rax, rcx
0x1800bc547  mov     [rbp+3Fh+Size], rax
0x1800bc54b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x1800bc552  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x1800bc557  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x1800bc55e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x1800bc563  xor     edi, edi
0x1800bc565  test    al, al
0x1800bc567  jz      loc_1800BC611
0x1800bc56d  mov     rcx, [rsi+30h]
0x1800bc571  test    rcx, rcx
0x1800bc574  jz      loc_1800BC611
0x1800bc57a  mov     rax, [rsi+50h]
0x1800bc57e  test    rax, rax
0x1800bc581  jz      loc_1800BC611
0x1800bc587  mov     rdx, [rbp+3Fh+Size]
0x1800bc58b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc590  mov     rbx, rax
0x1800bc593  mov     [rbp+3Fh+lpAddress], rax
0x1800bc597  test    rax, rax
0x1800bc59a  jz      short loc_1800BC5E6
0x1800bc59c  lea     rcx, [rsi+170h]
0x1800bc5a3  mov     rdx, [rcx+8]
0x1800bc5a7  cmp     rdx, [rcx+10h]
0x1800bc5ab  jz      short loc_1800BC5B7
0x1800bc5ad  mov     [rdx], rax
0x1800bc5b0  add     qword ptr [rcx+8], 8
0x1800bc5b5  jmp     short loc_1800BC5C4
0x1800bc5b7  lea     r8, [rbp+3Fh+lpAddress]
0x1800bc5bb  call    ??$_Emplace_reallocate@AEAPEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEAPEAX@Z; std::vector<void *>::_Emplace_reallocate<void * &>(void * * const,void * &)
0x1800bc5c0  mov     rbx, [rbp+3Fh+lpAddress]
0x1800bc5c4  test    rbx, rbx
0x1800bc5c7  jz      short loc_1800BC611
0x1800bc5c9  cmp     [rbp+3Fh+arg_28], dil
0x1800bc5cd  jz      loc_1800BC697
0x1800bc5d3  mov     r8, [rbp+3Fh+Size]; Size
0x1800bc5d7  xor     edx, edx; Val
0x1800bc5d9  mov     rcx, rbx; void *
0x1800bc5dc  call    memset_0
0x1800bc5e1  jmp     loc_1800BC697
0x1800bc5e6  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, dil; AutoSRConfig g_AutoSRConfig
0x1800bc5ed  jz      short loc_1800BC5FB
0x1800bc5ef  lea     rcx, aExtensionAlloc; "Extension allocator failed, falling bac"...
0x1800bc5f6  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800bc5fb  lea     r8, aExtAllocatorFa; "Ext allocator failed"
0x1800bc602  xor     edx, edx; unsigned int
0x1800bc604  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800bc609  mov     [rsi+50h], rdi
0x1800bc60d  mov     [rsi+58h], rdi
0x1800bc611  mov     r9d, 4; flProtect
0x1800bc617  mov     r8d, 3000h; flAllocationType
0x1800bc61d  mov     rdx, [rbp+3Fh+Size]; dwSize
0x1800bc621  xor     ecx, ecx; lpAddress
0x1800bc623  call    cs:__imp_VirtualAlloc
0x1800bc629  mov     rbx, rax
0x1800bc62c  mov     [rbp+3Fh+lpAddress], rax
0x1800bc630  test    rax, rax
0x1800bc633  jnz     short loc_1800BC65A
0x1800bc635  mov     rcx, [rbp+47h]; this
0x1800bc639  mov     ebx, 8007000Eh
0x1800bc63e  mov     r9d, ebx; char *
0x1800bc641  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800bc648  mov     edx, 8ADh; void *
0x1800bc64d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc652  nop
0x1800bc653  mov     eax, ebx
0x1800bc655  jmp     loc_1800BC946
0x1800bc65a  lea     rcx, [rsi+140h]
0x1800bc661  mov     rdx, [rcx+8]
0x1800bc665  cmp     rdx, [rcx+10h]
0x1800bc669  jz      short loc_1800BC676
0x1800bc66b  lea     rdx, [rbp+3Fh+lpAddress]
0x1800bc66f  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@XUvirtualalloc_deleter@wil@@@wistd@@@?$vector@V?$unique_ptr@XUvirtualalloc_deleter@wil@@@wistd@@V?$allocator@V?$unique_ptr@XUvirtualalloc_deleter@wil@@@wistd@@@std@@@std@@AEAAAEAV?$unique_ptr@XUvirtualalloc_deleter@wil@@@wistd@@$$QEAV23@@Z; std::vector<wistd::unique_ptr<void,wil::virtualalloc_deleter>>::_Emplace_back_with_unused_capacity<wistd::unique_ptr<void,wil::virtualalloc_deleter>>(wistd::unique_ptr<void,wil::virtualalloc_deleter> &&)
0x1800bc674  jmp     short loc_1800BC680
0x1800bc676  lea     r8, [rbp+3Fh+lpAddress]
0x1800bc67a  call    ??$_Emplace_reallocate@V?$unique_ptr@XUvirtualalloc_deleter@wil@@@wistd@@@?$vector@V?$unique_ptr@XUvirtualalloc_deleter@wil@@@wistd@@V?$allocator@V?$unique_ptr@XUvirtualalloc_deleter@wil@@@wistd@@@std@@@std@@AEAAPEAV?$unique_ptr@XUvirtualalloc_deleter@wil@@@wistd@@QEAV23@$$QEAV23@@Z; std::vector<wistd::unique_ptr<void,wil::virtualalloc_deleter>>::_Emplace_reallocate<wistd::unique_ptr<void,wil::virtualalloc_deleter>>(wistd::unique_ptr<void,wil::virtualalloc_deleter> * const,wistd::unique_ptr<void,wil::virtualalloc_deleter> &&)
0x1800bc67f  nop
0x1800bc680  mov     rcx, [rbp+3Fh+lpAddress]; lpAddress
0x1800bc684  test    rcx, rcx
0x1800bc687  jz      short loc_1800BC697
0x1800bc689  xor     edx, edx; dwSize
0x1800bc68b  mov     r8d, 8000h; dwFreeType
0x1800bc691  call    cs:__imp_VirtualFree
0x1800bc697  mov     [rbp+3Fh+var_A0], rdi
0x1800bc69b  mov     rax, [r14]
0x1800bc69e  lea     r8, [rbp+3Fh+var_A0]
0x1800bc6a2  lea     rdx, _GUID_14eecffc_4df8_40f7_a118_5c816f45695e
0x1800bc6a9  mov     rcx, r14
0x1800bc6ac  mov     rax, [rax]
0x1800bc6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc6b4  mov     edi, eax
0x1800bc6b6  test    eax, eax
0x1800bc6b8  jns     short loc_1800BC6D7
0x1800bc6ba  mov     rcx, [rbp+47h]; this
0x1800bc6be  mov     r9d, eax; char *
0x1800bc6c1  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800bc6c8  mov     edx, 8BDh; void *
0x1800bc6cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc6d2  jmp     loc_1800BC93B
0x1800bc6d7  mov     qword ptr [rsp+110h+var_C0], 0
0x1800bc6e0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x1800bc6e7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x1800bc6ec  mov     rcx, [rbp+3Fh+var_A0]
0x1800bc6f0  test    al, al
0x1800bc6f2  mov     rax, [rcx]
0x1800bc6f5  jz      short loc_1800BC749
0x1800bc6f7  lea     rdx, [rsp+110h+var_C0]
0x1800bc6fc  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x1800bc701  lea     r9, _GUID_6b3b2502_6e51_45b3_90ee_9884265e8df3
0x1800bc708  mov     r8, [rbp+3Fh+Size]
0x1800bc70c  mov     rdx, rbx
0x1800bc70f  mov     rax, [rax+288h]
0x1800bc716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc71b  mov     edi, eax
0x1800bc71d  test    eax, eax
0x1800bc71f  jns     short loc_1800BC771
0x1800bc721  mov     edx, 8C3h; void *
0x1800bc726  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800bc72d  mov     r9d, eax; char *
0x1800bc730  mov     rcx, [rbp+47h]; this
0x1800bc734  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc739  nop
0x1800bc73a  lea     rcx, [rsp+110h+var_C0]
0x1800bc73f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800bc744  jmp     loc_1800BC93B
0x1800bc749  lea     r9, [rsp+110h+var_C0]
0x1800bc74e  lea     r8, _GUID_6b3b2502_6e51_45b3_90ee_9884265e8df3
0x1800bc755  mov     rdx, rbx
0x1800bc758  mov     rax, [rax+180h]
0x1800bc75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc764  mov     edi, eax
0x1800bc766  test    eax, eax
0x1800bc768  jns     short loc_1800BC771
0x1800bc76a  mov     edx, 8C7h
0x1800bc76f  jmp     short loc_1800BC726
0x1800bc771  lea     rdi, [rsi+158h]
0x1800bc778  mov     rdx, [rdi+8]
0x1800bc77c  cmp     rdx, [rdi+10h]
0x1800bc780  jz      short loc_1800BC7A3
0x1800bc782  mov     rcx, qword ptr [rsp+110h+var_C0]
0x1800bc787  mov     [rdx], rcx
0x1800bc78a  test    rcx, rcx
0x1800bc78d  jz      short loc_1800BC79C
0x1800bc78f  mov     rax, [rcx]
0x1800bc792  mov     rax, [rax+8]
0x1800bc796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc79b  nop
0x1800bc79c  add     qword ptr [rdi+8], 8
0x1800bc7a1  jmp     short loc_1800BC7B0
0x1800bc7a3  lea     r8, [rsp+110h+var_C0]
0x1800bc7a8  mov     rcx, rdi
0x1800bc7ab  call    ??$_Emplace_reallocate@AEAV?$CComPtr@UID3D12Heap@@@ATL@@@?$vector@V?$CComPtr@UID3D12Heap@@@ATL@@V?$allocator@V?$CComPtr@UID3D12Heap@@@ATL@@@std@@@std@@AEAAPEAV?$CComPtr@UID3D12Heap@@@ATL@@QEAV23@AEAV23@@Z; std::vector<ATL::CComPtr<ID3D12Heap>>::_Emplace_reallocate<ATL::CComPtr<ID3D12Heap> &>(ATL::CComPtr<ID3D12Heap> * const,ATL::CComPtr<ID3D12Heap> &)
0x1800bc7b0  xor     eax, eax
0x1800bc7b2  mov     [rbp+3Fh+var_84], rax
0x1800bc7b6  mov     [rbp+3Fh+var_7C], eax
0x1800bc7b9  mov     [rbp+3Fh+var_54], eax
0x1800bc7bc  mov     [rbp+3Fh+var_88], 3
0x1800bc7c3  mov     eax, [rbp+3Fh+arg_20]
0x1800bc7c6  mov     [rbp+3Fh+var_68], eax
0x1800bc7c9  mov     edx, 1
0x1800bc7ce  mov     [rbp+3Fh+var_5C], edx
0x1800bc7d1  mov     [rbp+3Fh+var_78], r12
0x1800bc7d5  mov     [rbp+3Fh+var_70], r13d
0x1800bc7d9  mov     [rbp+3Fh+var_6C], 10001h
0x1800bc7e0  mov     al, [rsi+88h]
0x1800bc7e6  neg     al
0x1800bc7e8  sbb     ecx, ecx
0x1800bc7ea  neg     ecx
0x1800bc7ec  add     ecx, 10h
0x1800bc7ef  mov     [rbp+3Fh+var_58], ecx
0x1800bc7f2  mov     [rbp+3Fh+var_64], rdx
0x1800bc7f6  xor     esi, esi
0x1800bc7f8  mov     [rbp+3Fh+var_B8], rsi
0x1800bc7fc  mov     rax, [r14]
0x1800bc7ff  lea     rcx, [rbp+3Fh+var_B8]
0x1800bc803  mov     [rsp+110h+var_D8], rcx
0x1800bc808  lea     rcx, _GUID_696442be_a72e_4059_bc79_5b5c98040fad
0x1800bc80f  mov     [rsp+110h+var_E0], rcx
0x1800bc814  mov     [rsp+110h+var_E8], rsi
0x1800bc819  mov     [rsp+110h+var_F0], esi; int
0x1800bc81d  lea     r9, [rbp+3Fh+var_88]
0x1800bc821  xor     r8d, r8d
0x1800bc824  mov     rdx, qword ptr [rsp+110h+var_C0]
0x1800bc829  mov     rcx, r14
0x1800bc82c  mov     rax, [rax+0E8h]
0x1800bc833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc838  mov     edi, eax
0x1800bc83a  test    eax, eax
0x1800bc83c  jns     short loc_1800BC865
0x1800bc83e  mov     edx, 8E2h; void *
0x1800bc843  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800bc84a  mov     r9d, eax; char *
0x1800bc84d  mov     rcx, [rbp+47h]; this
0x1800bc851  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc856  nop
0x1800bc857  lea     rcx, [rbp+3Fh+var_B8]
0x1800bc85b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800bc860  jmp     loc_1800BC73A
0x1800bc865  mov     [rbp+3Fh+var_90], rbx
0x1800bc869  mov     [rbp+3Fh+var_98], 80h
0x1800bc870  mov     rcx, [rbp+3Fh+var_B8]
0x1800bc874  mov     rax, [rcx]
0x1800bc877  lea     r9, [rbp+3Fh+var_98]
0x1800bc87b  mov     r8d, 4
0x1800bc881  lea     rdx, DIRECTSR_EXT_PITCH_ALIGNMENT
0x1800bc888  mov     rax, [rax+20h]
0x1800bc88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc891  mov     edi, eax
0x1800bc893  test    eax, eax
0x1800bc895  jns     short loc_1800BC89E
0x1800bc897  mov     edx, 8E9h
0x1800bc89c  jmp     short loc_1800BC843
0x1800bc89e  mov     rcx, [rbp+3Fh+var_B8]
0x1800bc8a2  mov     rax, [rcx]
0x1800bc8a5  lea     r9, [rbp+3Fh+var_90]
0x1800bc8a9  mov     r8d, 8
0x1800bc8af  lea     rdx, DIRECTSR_EXT_CPUVA
0x1800bc8b6  mov     rax, [rax+20h]
0x1800bc8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc8bf  mov     edi, eax
0x1800bc8c1  test    eax, eax
0x1800bc8c3  jns     short loc_1800BC8CF
0x1800bc8c5  mov     edx, 8EAh
0x1800bc8ca  jmp     loc_1800BC843
0x1800bc8cf  mov     rcx, [rbp+3Fh+var_B8]
0x1800bc8d3  mov     rax, [rcx]
0x1800bc8d6  lea     r9, [rbp+3Fh+Size]
0x1800bc8da  mov     r8d, 8
0x1800bc8e0  lea     rdx, DIRECTSR_EXT_RES_SIZE
0x1800bc8e7  mov     rax, [rax+20h]
0x1800bc8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc8f0  mov     edi, eax
0x1800bc8f2  test    eax, eax
0x1800bc8f4  jns     short loc_1800BC900
0x1800bc8f6  mov     edx, 8EBh
0x1800bc8fb  jmp     loc_1800BC843
0x1800bc900  mov     rdx, [rbp+3Fh+var_B8]
0x1800bc904  mov     [rbp+3Fh+var_B8], rsi
0x1800bc908  mov     [r15], rdx
0x1800bc90b  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, sil; AutoSRConfig g_AutoSRConfig
0x1800bc912  jz      short loc_1800BC925
0x1800bc914  mov     r8, [rbp+3Fh+var_90]
0x1800bc918  lea     rcx, aAllocatedSysme; "Allocated SysMemHeap resource 0x%p at V"...
0x1800bc91f  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800bc924  nop
0x1800bc925  lea     rcx, [rbp+3Fh+var_B8]
0x1800bc929  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800bc92e  nop
0x1800bc92f  lea     rcx, [rsp+110h+var_C0]
0x1800bc934  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800bc939  mov     edi, esi
0x1800bc93b  lea     rcx, [rbp+3Fh+var_A0]
0x1800bc93f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800bc944  mov     eax, edi
0x1800bc946  mov     rcx, [rbp+3Fh+var_50]
0x1800bc94a  xor     rcx, rsp; StackCookie
0x1800bc94d  call    __security_check_cookie
0x1800bc952  add     rsp, 0D8h
0x1800bc959  pop     r15
0x1800bc95b  pop     r14
0x1800bc95d  pop     r13
0x1800bc95f  pop     r12
0x1800bc961  pop     rdi
0x1800bc962  pop     rsi
0x1800bc963  pop     rbx
0x1800bc964  pop     rbp
0x1800bc965  retn
```
