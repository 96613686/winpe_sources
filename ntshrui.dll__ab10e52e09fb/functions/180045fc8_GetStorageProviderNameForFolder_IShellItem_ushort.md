# GetStorageProviderNameForFolder(IShellItem *,ushort * *)

- ea: `0x180045fc8`
- end: `0x18004619d`
- name: `?GetStorageProviderNameForFolder@@YAJPEAUIShellItem@@PEAPEAG@Z`
- size: `469`
- prototype: `__int64 __fastcall(struct IShellItem *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003c3c0`

## callees

- `0x180008900`
- `0x18001d18c`
- `0x1800214cc`
- `0x180045fc8`
- `0x1800514e4`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800460d3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800460d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004618c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004618c`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18004607e`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18004607e`

## string_xrefs

- `0x180046019`: `onecoreuap\internal\shell\inc\private\friendlyitempath.h`
- `0x18004608f`: `onecoreuap\internal\shell\inc\private\friendlyitempath.h`
- `0x18004615c`: `onecoreuap\internal\shell\inc\private\friendlyitempath.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetStorageProviderNameForFolder(struct IShellItem *a1, unsigned __int16 **a2)
{
  HRESULT (__stdcall *GetDisplayName)(IShellItem *, SIGDN, LPWSTR *); // rbx
  __int64 v5; // rax
  int v6; // eax
  HRESULT v7; // ebx
  __int64 v9; // rdx
  void *v10; // rdi
  __int64 (__fastcall *v11)(void *, LPVOID, __int64 *, _QWORD); // rbx
  int v12; // eax
  int ppv; // [rsp+20h] [rbp-18h]
  int ppva; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  int v16; // [rsp+60h] [rbp+28h] BYREF
  void *v17; // [rsp+68h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+38h] BYREF
  __int64 v19; // [rsp+78h] [rbp+40h] BYREF

  *a2 = 0;
  pv = 0;
  GetDisplayName = a1->lpVtbl->GetDisplayName;
  v5 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
  v6 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, __int64))GetDisplayName)(a1, 2147647488LL, v5);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\friendlyitempath.h",
      (const char *)(unsigned int)v6,
      ppv);
LABEL_3:
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v7;
  }
  v17 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61110674>::GetImpl'::`2'::impl) )
  {
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v17);
    v7 = SHCoCreateInstance(0, &CLSID_SyncRootManager, 0, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &v17);
    if ( v7 < 0 )
    {
      v9 = 82;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\friendlyitempath.h",
        (const char *)(unsigned int)v7,
        ppva);
LABEL_10:
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v17);
      goto LABEL_3;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v17);
    v7 = CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &v17);
    if ( v7 < 0 )
    {
      v9 = 86;
      goto LABEL_9;
    }
  }
  v19 = 0;
  v16 = 0;
  v10 = v17;
  v11 = *(__int64 (__fastcall **)(void *, LPVOID, __int64 *, _QWORD))(*(_QWORD *)v17 + 32LL);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v19);
  v7 = v11(v10, pv, &v19, 0);
  if ( v7 < 0 )
  {
LABEL_14:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v19);
    goto LABEL_10;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v19 + 56LL))(v19, a2);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\friendlyitempath.h",
      (const char *)(unsigned int)v12,
      (int)&v16);
    goto LABEL_14;
  }
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v17);
  if ( pv )
    CoTaskMemFree(pv);
  return 0;
}

```

## disassembly

```asm
0x180045fc8  push    rbp
0x180045fca  push    rbx
0x180045fcb  push    rsi
0x180045fcc  push    rdi
0x180045fcd  mov     rbp, rsp
0x180045fd0  sub     rsp, 38h
0x180045fd4  mov     rsi, rdx
0x180045fd7  mov     rdi, rcx
0x180045fda  mov     qword ptr [rdx], 0
0x180045fe1  mov     [rbp+pv], 0
0x180045fe9  mov     rax, [rcx]
0x180045fec  mov     rbx, [rax+28h]
0x180045ff0  lea     rcx, [rbp+pv]
0x180045ff4  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180045ff9  mov     r8, rax
0x180045ffc  mov     edx, 80028000h
0x180046001  mov     rcx, rdi
0x180046004  mov     rax, rbx
0x180046007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004600c  mov     ebx, eax
0x18004600e  test    eax, eax
0x180046010  jns     short loc_180046041
0x180046012  mov     rcx, [rbp+20h]; this
0x180046016  mov     r9d, eax; char *
0x180046019  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180046020  mov     edx, 4Eh ; 'N'; void *
0x180046025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004602a  nop
0x18004602b  mov     rcx, [rbp+pv]; pv
0x18004602f  test    rcx, rcx
0x180046032  jz      short loc_18004603A
0x180046034  call    cs:__imp_CoTaskMemFree
0x18004603a  mov     eax, ebx
0x18004603c  jmp     loc_180046194
0x180046041  mov     [rbp+arg_8], 0
0x180046049  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61110674@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61110674@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674> `wil::Feature<__WilFeatureTraits_Feature_61110674>::GetImpl(void)'::`2'::impl
0x180046050  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61110674@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674>::__private_IsEnabled(void)
0x180046055  lea     rcx, [rbp+arg_8]
0x180046059  test    al, al
0x18004605b  jz      short loc_1800460B1
0x18004605d  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180046062  lea     rax, [rbp+arg_8]
0x180046066  mov     qword ptr [rsp+38h+ppv], rax; int
0x18004606b  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180046072  xor     r8d, r8d; pUnkOuter
0x180046075  lea     rdx, CLSID_SyncRootManager; pclsid
0x18004607c  xor     ecx, ecx; pszCLSID
0x18004607e  call    cs:__imp_SHCoCreateInstance
0x180046084  mov     ebx, eax
0x180046086  test    eax, eax
0x180046088  jns     short loc_1800460E6
0x18004608a  mov     edx, 52h ; 'R'; void *
0x18004608f  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180046096  mov     r9d, ebx; char *
0x180046099  mov     rcx, [rbp+20h]; this
0x18004609d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800460a2  nop
0x1800460a3  lea     rcx, [rbp+arg_8]
0x1800460a7  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800460ac  jmp     loc_18004602B
0x1800460b1  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800460b6  lea     rax, [rbp+arg_8]
0x1800460ba  mov     qword ptr [rsp+38h+ppv], rax; ppv
0x1800460bf  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x1800460c6  xor     edx, edx; pUnkOuter
0x1800460c8  lea     r8d, [rdx+1]; dwClsContext
0x1800460cc  lea     rcx, CLSID_SyncRootManager; rclsid
0x1800460d3  call    cs:__imp_CoCreateInstance
0x1800460d9  mov     ebx, eax
0x1800460db  test    eax, eax
0x1800460dd  jns     short loc_1800460E6
0x1800460df  mov     edx, 56h ; 'V'
0x1800460e4  jmp     short loc_18004608F
0x1800460e6  mov     [rbp+arg_18], 0
0x1800460ee  mov     [rbp+arg_0], 0
0x1800460f5  mov     rdi, [rbp+arg_8]
0x1800460f9  mov     rax, [rdi]
0x1800460fc  mov     rbx, [rax+20h]
0x180046100  lea     rcx, [rbp+arg_18]
0x180046104  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180046109  lea     rax, [rbp+arg_0]
0x18004610d  mov     qword ptr [rsp+38h+ppv], rax; int
0x180046112  xor     r9d, r9d
0x180046115  lea     r8, [rbp+arg_18]
0x180046119  mov     rdx, [rbp+pv]
0x18004611d  mov     rcx, rdi
0x180046120  mov     rax, rbx
0x180046123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046128  mov     ebx, eax
0x18004612a  test    eax, eax
0x18004612c  jns     short loc_18004613C
0x18004612e  lea     rcx, [rbp+arg_18]
0x180046132  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180046137  jmp     loc_1800460A3
0x18004613c  mov     rcx, [rbp+arg_18]
0x180046140  mov     rax, [rcx]
0x180046143  mov     rdx, rsi
0x180046146  mov     rax, [rax+38h]
0x18004614a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004614f  mov     ebx, eax
0x180046151  test    eax, eax
0x180046153  jns     short loc_18004616F
0x180046155  mov     rcx, [rbp+20h]; this
0x180046159  mov     r9d, eax; char *
0x18004615c  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180046163  mov     edx, 5Ch ; '\'; void *
0x180046168  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004616d  jmp     short loc_18004612E
0x18004616f  lea     rcx, [rbp+arg_18]
0x180046173  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180046178  nop
0x180046179  lea     rcx, [rbp+arg_8]
0x18004617d  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180046182  nop
0x180046183  mov     rcx, [rbp+pv]; pv
0x180046187  test    rcx, rcx
0x18004618a  jz      short loc_180046192
0x18004618c  call    cs:__imp_CoTaskMemFree
0x180046192  xor     eax, eax
0x180046194  add     rsp, 38h
0x180046198  pop     rdi
0x180046199  pop     rsi
0x18004619a  pop     rbx
0x18004619b  pop     rbp
0x18004619c  retn
```
