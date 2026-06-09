# SREffectRenderPassDx12::CDSRProvider::GetDSRDevice(_LUID const &,ID3D12Device *,IDSRDevice * *)

- ea: `0x180068718`
- end: `0x1800689f4`
- name: `?GetDSRDevice@CDSRProvider@SREffectRenderPassDx12@@QEAAJAEBU_LUID@@PEAUID3D12Device@@PEAPEAUIDSRDevice@@@Z`
- size: `732`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, const struct _LUID *, struct ID3D12Device *, struct IDSRDevice **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b9548`
- `0x1800bbe98`

## callees

- `0x180014750`
- `0x1800306f4`
- `0x180067d2c`
- `0x180068718`
- `0x1800689fc`
- `0x180068ca8`
- `0x18006989c`
- `0x1800b5c54`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800689d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800689d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006873d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006873d`

## string_xrefs

- `0x18006879a`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x18006881d`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x180068916`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800689ab`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800688c1`: `DXGITestEffects.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SREffectRenderPassDx12::CDSRProvider::GetDSRDevice(
        PSRWLOCK SRWLock,
        PVOID *a2,
        struct ID3D12Device *a3,
        struct IDSRDevice **a4)
{
  int DSRDeviceFactory; // eax
  unsigned int v9; // edi
  char v10; // al
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64); // r15
  PVOID Ptr; // rax
  struct IDSRDevice *v17; // rdi
  PVOID v18; // rcx
  struct IDSRDevice *v19; // rcx
  struct IDSRDevice **v21; // [rsp+20h] [rbp-20h]
  struct ID3D12DSRDeviceFactory *v22[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  struct IDSRDevice *v24; // [rsp+70h] [rbp+30h] BYREF
  __int64 v25; // [rsp+78h] [rbp+38h] BYREF

  AcquireSRWLockExclusive(SRWLock);
  v22[1] = (struct ID3D12DSRDeviceFactory *)SRWLock;
  if ( __PAIR128__((unsigned __int64)a3, *a2) != *(_OWORD *)&SRWLock[6].Ptr || !SRWLock[8].Ptr )
  {
    if ( *(&g_AutoSRConfig + 6) )
      DebugPrint("Creating DSR factory");
    v22[0] = 0;
    DSRDeviceFactory = GetDSRDeviceFactory(v22);
    v9 = DSRDeviceFactory;
    if ( DSRDeviceFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AA,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
        (const char *)(unsigned int)DSRDeviceFactory,
        (int)v21);
LABEL_25:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v22);
      goto LABEL_32;
    }
    if ( *(&g_AutoSRConfig + 6) )
      DebugPrint("Creating DSR device");
    v10 = ((__int64 (__fastcall *)(struct ID3D12Device *))a3->lpVtbl->GetNodeCount)(a3);
    v24 = 0;
    v21 = &v24;
    v11 = (*(__int64 (__fastcall **)(struct ID3D12DSRDeviceFactory *, struct ID3D12Device *, _QWORD, GUID *))(*(_QWORD *)v22[0] + 24LL))(
            v22[0],
            a3,
            (unsigned int)((1 << v10) - 1),
            &GUID_994659a7_31ad_4912_9414_159f16630306);
    v9 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
        (const char *)(unsigned int)v11,
        (int)&v24);
LABEL_24:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
      goto LABEL_25;
    }
    v25 = 0;
    v12 = (**(__int64 (__fastcall ***)(struct IDSRDevice *, GUID *, __int64 *))v24)(
            v24,
            &GUID_6069f18a_2f9c_4e9c_afec_6a419387d914,
            &v25);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 434;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
        (const char *)(unsigned int)v12,
        (int)&v24);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
      goto LABEL_24;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 24LL))(v25, 1);
    v14 = v25;
    v15 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 32LL);
    SREffectRenderPassDx12::CDSRProvider::CacheExtensionDllPath((struct PACKAGE_VERSION *)SRWLock);
    v12 = v15(v14);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 438;
      goto LABEL_23;
    }
    if ( *(&g_AutoSRConfig + 8) )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, const CHAR *))(*(_QWORD *)v25 + 32LL))(v25, "DXGITestEffects.dll");
      v9 = v12;
      if ( v12 < 0 )
      {
        v13 = 443;
        goto LABEL_23;
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
    {
      Ptr = SRWLock[9].Ptr;
      if ( Ptr != SRWLock[10].Ptr )
        SRWLock[10].Ptr = Ptr;
      v12 = SREffectRenderPassDx12::CDSRProvider::CacheVariantInfo((SREffectRenderPassDx12::CDSRProvider *)SRWLock, v24);
      v9 = v12;
      if ( v12 < 0 )
      {
        v13 = 450;
        goto LABEL_23;
      }
    }
    v17 = v24;
    v24 = 0;
    v18 = SRWLock[8].Ptr;
    if ( v18 )
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v18 + 16LL))(v18);
    SRWLock[8].Ptr = v17;
    SRWLock[6].Ptr = *a2;
    SRWLock[7].Ptr = a3;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v22);
  }
  v19 = (struct IDSRDevice *)SRWLock[8].Ptr;
  if ( v19 )
  {
    *a4 = v19;
    (*(void (__fastcall **)(struct IDSRDevice *))(*(_QWORD *)v19 + 8LL))(v19);
    v9 = 0;
  }
  else
  {
    v9 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
      (const char *)0x8000FFFFLL,
      (int)v21);
  }
LABEL_32:
  ReleaseSRWLockExclusive(SRWLock);
  return v9;
}

```

## disassembly

```asm
0x180068718  mov     [rsp-28h+arg_10], rbx
0x18006871d  mov     [rsp-28h+arg_18], rsi
0x180068722  push    rbp
0x180068723  push    rdi
0x180068724  push    r12
0x180068726  push    r14
0x180068728  push    r15
0x18006872a  mov     rbp, rsp
0x18006872d  sub     rsp, 40h
0x180068731  mov     r12, r9
0x180068734  mov     r14, r8
0x180068737  mov     rsi, rdx
0x18006873a  mov     rbx, rcx
0x18006873d  call    cs:__imp_AcquireSRWLockExclusive
0x180068743  mov     [rbp+var_8], rbx
0x180068747  mov     eax, [rsi]
0x180068749  cmp     [rbx+30h], eax
0x18006874c  jnz     short loc_180068767
0x18006874e  mov     eax, [rsi+4]
0x180068751  cmp     [rbx+34h], eax
0x180068754  jnz     short loc_180068767
0x180068756  cmp     r14, [rbx+38h]
0x18006875a  jnz     short loc_180068767
0x18006875c  cmp     qword ptr [rbx+40h], 0
0x180068761  jnz     loc_180068996
0x180068767  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, 0; AutoSRConfig g_AutoSRConfig
0x18006876e  jz      short loc_18006877C
0x180068770  lea     rcx, aCreatingDsrFac; "Creating DSR factory"
0x180068777  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x18006877c  mov     [rbp+var_10], 0
0x180068784  lea     rcx, [rbp+var_10]; struct ID3D12DSRDeviceFactory **
0x180068788  call    ?GetDSRDeviceFactory@@YAJPEAPEAUID3D12DSRDeviceFactory@@@Z; GetDSRDeviceFactory(ID3D12DSRDeviceFactory * *)
0x18006878d  mov     edi, eax
0x18006878f  test    eax, eax
0x180068791  jns     short loc_1800687B0
0x180068793  mov     rcx, [rbp+28h]; this
0x180068797  mov     r9d, eax; char *
0x18006879a  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800687a1  mov     edx, 1AAh; void *
0x1800687a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800687ab  jmp     loc_18006893B
0x1800687b0  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, 0; AutoSRConfig g_AutoSRConfig
0x1800687b7  jz      short loc_1800687C5
0x1800687b9  lea     rcx, aCreatingDsrDev; "Creating DSR device"
0x1800687c0  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800687c5  mov     rax, [r14]
0x1800687c8  mov     rcx, r14
0x1800687cb  mov     rax, [rax+38h]
0x1800687cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800687d4  mov     ecx, eax
0x1800687d6  mov     r15d, 1
0x1800687dc  mov     r8d, r15d
0x1800687df  shl     r8d, cl
0x1800687e2  dec     r8d
0x1800687e5  mov     [rbp+arg_0], 0
0x1800687ed  mov     rcx, [rbp+var_10]
0x1800687f1  mov     rax, [rcx]
0x1800687f4  lea     rdx, [rbp+arg_0]
0x1800687f8  mov     qword ptr [rsp+40h+var_20], rdx; int
0x1800687fd  lea     r9, _GUID_994659a7_31ad_4912_9414_159f16630306
0x180068804  mov     rdx, r14
0x180068807  mov     rax, [rax+18h]
0x18006880b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068810  mov     edi, eax
0x180068812  test    eax, eax
0x180068814  jns     short loc_180068833
0x180068816  mov     rcx, [rbp+28h]; this
0x18006881a  mov     r9d, eax; char *
0x18006881d  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x180068824  mov     edx, 1B0h; void *
0x180068829  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006882e  jmp     loc_180068931
0x180068833  mov     [rbp+arg_8], 0
0x18006883b  mov     rcx, [rbp+arg_0]
0x18006883f  mov     rax, [rcx]
0x180068842  lea     r8, [rbp+arg_8]
0x180068846  lea     rdx, _GUID_6069f18a_2f9c_4e9c_afec_6a419387d914
0x18006884d  mov     rax, [rax]
0x180068850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068855  mov     edi, eax
0x180068857  test    eax, eax
0x180068859  jns     short loc_180068865
0x18006885b  mov     edx, 1B2h
0x180068860  jmp     loc_180068913
0x180068865  mov     rcx, [rbp+arg_8]
0x180068869  mov     rax, [rcx]
0x18006886c  mov     edx, r15d
0x18006886f  mov     rax, [rax+18h]
0x180068873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068878  mov     rdi, [rbp+arg_8]
0x18006887c  mov     rax, [rdi]
0x18006887f  mov     r15, [rax+20h]
0x180068883  mov     rcx, rbx; this
0x180068886  call    ?CacheExtensionDllPath@CDSRProvider@SREffectRenderPassDx12@@IEAAXXZ; SREffectRenderPassDx12::CDSRProvider::CacheExtensionDllPath(void)
0x18006888b  lea     rdx, [rbx+8]
0x18006888f  cmp     qword ptr [rdx+18h], 0Fh
0x180068894  jbe     short loc_180068899
0x180068896  mov     rdx, [rdx]
0x180068899  mov     rcx, rdi
0x18006889c  mov     rax, r15
0x18006889f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688a4  mov     edi, eax
0x1800688a6  test    eax, eax
0x1800688a8  jns     short loc_1800688B1
0x1800688aa  mov     edx, 1B6h
0x1800688af  jmp     short loc_180068913
0x1800688b1  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+8, 0; AutoSRConfig g_AutoSRConfig
0x1800688b8  jz      short loc_1800688DE
0x1800688ba  mov     rcx, [rbp+arg_8]
0x1800688be  mov     rax, [rcx]
0x1800688c1  lea     rdx, aDxgitesteffect; "DXGITestEffects.dll"
0x1800688c8  mov     rax, [rax+20h]
0x1800688cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688d1  mov     edi, eax
0x1800688d3  test    eax, eax
0x1800688d5  jns     short loc_1800688DE
0x1800688d7  mov     edx, 1BBh
0x1800688dc  jmp     short loc_180068913
0x1800688de  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x1800688e5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x1800688ea  test    al, al
0x1800688ec  jz      short loc_180068949
0x1800688ee  mov     rax, [rbx+48h]
0x1800688f2  cmp     rax, [rbx+50h]
0x1800688f6  jz      short loc_1800688FC
0x1800688f8  mov     [rbx+50h], rax
0x1800688fc  mov     rdx, [rbp+arg_0]; struct IDSRDevice *
0x180068900  mov     rcx, rbx; this
0x180068903  call    ?CacheVariantInfo@CDSRProvider@SREffectRenderPassDx12@@IEAAJPEAUIDSRDevice@@@Z; SREffectRenderPassDx12::CDSRProvider::CacheVariantInfo(IDSRDevice *)
0x180068908  mov     edi, eax
0x18006890a  test    eax, eax
0x18006890c  jns     short loc_180068949
0x18006890e  mov     edx, 1C2h; void *
0x180068913  mov     r9d, eax; char *
0x180068916  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x18006891d  mov     rcx, [rbp+28h]; this
0x180068921  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068926  nop
0x180068927  lea     rcx, [rbp+arg_8]
0x18006892b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180068930  nop
0x180068931  lea     rcx, [rbp+arg_0]
0x180068935  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006893a  nop
0x18006893b  lea     rcx, [rbp+var_10]
0x18006893f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180068944  jmp     loc_1800689D0
0x180068949  mov     rdi, [rbp+arg_0]
0x18006894d  mov     [rbp+arg_0], 0
0x180068955  mov     rcx, [rbx+40h]
0x180068959  test    rcx, rcx
0x18006895c  jz      short loc_18006896A
0x18006895e  mov     rax, [rcx]
0x180068961  mov     rax, [rax+10h]
0x180068965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006896a  mov     [rbx+40h], rdi
0x18006896e  mov     rax, [rsi]
0x180068971  mov     [rbx+30h], rax
0x180068975  mov     [rbx+38h], r14
0x180068979  lea     rcx, [rbp+arg_8]
0x18006897d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180068982  nop
0x180068983  lea     rcx, [rbp+arg_0]
0x180068987  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006898c  nop
0x18006898d  lea     rcx, [rbp+var_10]
0x180068991  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180068996  mov     rcx, [rbx+40h]
0x18006899a  test    rcx, rcx
0x18006899d  jnz     short loc_1800689BE
0x18006899f  mov     rcx, [rbp+28h]; this
0x1800689a3  mov     edi, 8000FFFFh
0x1800689a8  mov     r9d, edi; char *
0x1800689ab  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800689b2  mov     edx, 1CDh; void *
0x1800689b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800689bc  jmp     short loc_1800689D0
0x1800689be  mov     [r12], rcx
0x1800689c2  mov     rax, [rcx]
0x1800689c5  mov     rax, [rax+8]
0x1800689c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800689ce  xor     edi, edi
0x1800689d0  mov     rcx, rbx; SRWLock
0x1800689d3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800689d9  mov     eax, edi
0x1800689db  lea     r11, [rsp+40h+var_s0]
0x1800689e0  mov     rbx, [r11+40h]
0x1800689e4  mov     rsi, [r11+48h]
0x1800689e8  mov     rsp, r11
0x1800689eb  pop     r15
0x1800689ed  pop     r14
0x1800689ef  pop     r12
0x1800689f1  pop     rdi
0x1800689f2  pop     rbp
0x1800689f3  retn
```
