# CalcAggregatedCustomStates::TryGetCustomStatesFromProvider(Windows::Foundation::Collections::IIterable<Windows::Storage::Provider::StorageProviderItemProperty *> * *)

- ea: `0x18001886c`
- end: `0x180018a8b`
- name: `?TryGetCustomStatesFromProvider@CalcAggregatedCustomStates@@AEAAJPEAPEAU?$IIterable@PEAVStorageProviderItemProperty@Provider@Storage@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `543`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017ec0`

## callees

- `0x180003f94`
- `0x180004148`
- `0x18001886c`
- `0x180018a94`
- `0x180025dd4`
- `0x18006ed20`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001895a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001895a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800189b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800189b9`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x1800188c4`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x1800188c4`

## string_xrefs

- `0x180018a05`: `onecoreuap\shell\propsys\itemprop.cpp`
- `0x180018a40`: `onecoreuap\shell\propsys\itemprop.cpp`
- `0x180018a5a`: `onecoreuap\shell\propsys\itemprop.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CalcAggregatedCustomStates::TryGetCustomStatesFromProvider(__int64 a1, _QWORD *a2)
{
  HRESULT v4; // eax
  int v5; // ebx
  int v6; // eax
  __int64 v7; // rax
  HRESULT v8; // eax
  LPVOID v9; // rcx
  void *v10; // rcx
  void *v12; // rcx
  int ppvItem; // [rsp+20h] [rbp-40h]
  int ppvItema; // [rsp+20h] [rbp-40h]
  _BYTE v15[8]; // [rsp+30h] [rbp-30h] BYREF
  void *v16; // [rsp+38h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  *a2 = 0;
  v16 = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v16);
  v4 = SHCreateItemWithParent(
         0,
         *(IShellFolder **)(a1 + 24),
         *(LPCITEMIDLIST *)(a1 + 32),
         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
         &v16);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D2,
      (unsigned int)"onecoreuap\\shell\\propsys\\itemprop.cpp",
      (const char *)(unsigned int)v4,
      ppvItem);
    v12 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return (unsigned int)v5;
  }
  v15[0] = 0;
  v6 = IsShellItemUnderStorageProviderAndShowsState(v16, v15);
  v5 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D5,
      (unsigned int)"onecoreuap\\shell\\propsys\\itemprop.cpp",
      (const char *)(unsigned int)v6,
      ppvItem);
LABEL_21:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v16);
    return (unsigned int)v5;
  }
  if ( v15[0] )
  {
    pv = 0;
    v7 = *(_QWORD *)v16;
    pv = 0;
    v5 = (*(__int64 (__fastcall **)(void *, __int64, LPVOID *))(v7 + 40))(v16, 2147844096LL, &pv);
    if ( v5 >= 0 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
      v8 = CoCreateInstance(
             &GUID_f324e4f9_8496_40b2_a1ff_9617c1c9affe,
             0,
             1u,
             &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64,
             &ppv);
      v5 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6DD,
          (unsigned int)"onecoreuap\\shell\\propsys\\itemprop.cpp",
          (const char *)(unsigned int)v8,
          ppvItema);
      }
      else
      {
        v5 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, GUID *, _QWORD *))(*(_QWORD *)ppv + 80LL))(
               ppv,
               pv,
               &GUID_4584cb69_ee26_59e0_b05d_c9a7851a7317,
               a2);
        if ( v5 >= 0 )
        {
          v9 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
          }
          if ( pv )
            CoTaskMemFree(pv);
          goto LABEL_11;
        }
      }
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
    goto LABEL_21;
  }
LABEL_11:
  v10 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18001886c  mov     [rsp-8+arg_10], rbx
0x180018871  mov     [rsp-8+arg_18], rdi
0x180018876  push    rbp
0x180018877  mov     rbp, rsp
0x18001887a  sub     rsp, 60h
0x18001887e  mov     rax, cs:__security_cookie
0x180018885  xor     rax, rsp
0x180018888  mov     [rbp+var_10], rax
0x18001888c  mov     rdi, rdx
0x18001888f  mov     rbx, rcx
0x180018892  mov     qword ptr [rdx], 0
0x180018899  mov     [rbp+var_28], 0
0x1800188a1  lea     rcx, [rbp+var_28]
0x1800188a5  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800188aa  lea     rax, [rbp+var_28]
0x1800188ae  mov     qword ptr [rsp+60h+ppvItem], rax; int
0x1800188b3  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800188ba  mov     r8, [rbx+20h]; pidl
0x1800188be  mov     rdx, [rbx+18h]; psfParent
0x1800188c2  xor     ecx, ecx; pidlParent
0x1800188c4  call    cs:__imp_SHCreateItemWithParent
0x1800188ca  mov     ebx, eax
0x1800188cc  test    eax, eax
0x1800188ce  js      loc_1800189FE
0x1800188d4  mov     [rbp+var_30], 0
0x1800188d8  lea     rdx, [rbp+var_30]
0x1800188dc  mov     rcx, [rbp+var_28]
0x1800188e0  call    ?IsShellItemUnderStorageProviderAndShowsState@@YAJPEAUIShellItem@@PEA_NW4StorageProviderPathStateFlags@@@Z; IsShellItemUnderStorageProviderAndShowsState(IShellItem *,bool *,StorageProviderPathStateFlags)
0x1800188e5  mov     ebx, eax
0x1800188e7  test    eax, eax
0x1800188e9  js      loc_180018A39
0x1800188ef  cmp     [rbp+var_30], 0
0x1800188f3  jz      loc_1800189C0
0x1800188f9  mov     [rbp+pv], 0
0x180018901  mov     rcx, [rbp+var_28]
0x180018905  mov     rax, [rcx]
0x180018908  mov     [rbp+pv], 0
0x180018910  lea     r8, [rbp+pv]
0x180018914  mov     edx, 80058000h
0x180018919  mov     rax, [rax+28h]
0x18001891d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018922  mov     ebx, eax
0x180018924  test    eax, eax
0x180018926  js      loc_180018A76
0x18001892c  mov     [rbp+ppv], 0
0x180018934  lea     rcx, [rbp+ppv]
0x180018938  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001893d  lea     rax, [rbp+ppv]
0x180018941  mov     qword ptr [rsp+60h+ppvItem], rax; int
0x180018946  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x18001894d  xor     edx, edx; pUnkOuter
0x18001894f  lea     r8d, [rdx+1]; dwClsContext
0x180018953  lea     rcx, _GUID_f324e4f9_8496_40b2_a1ff_9617c1c9affe; rclsid
0x18001895a  call    cs:__imp_CoCreateInstance
0x180018960  mov     ebx, eax
0x180018962  test    eax, eax
0x180018964  js      loc_180018A53
0x18001896a  mov     rcx, [rbp+ppv]
0x18001896e  mov     rax, [rcx]
0x180018971  mov     r9, rdi
0x180018974  lea     r8, _GUID_4584cb69_ee26_59e0_b05d_c9a7851a7317
0x18001897b  mov     rdx, [rbp+pv]
0x18001897f  mov     rax, [rax+50h]
0x180018983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018988  mov     ebx, eax
0x18001898a  test    eax, eax
0x18001898c  js      loc_180018A6C
0x180018992  mov     rcx, [rbp+ppv]
0x180018996  test    rcx, rcx
0x180018999  jz      short loc_1800189B0
0x18001899b  mov     [rbp+ppv], 0
0x1800189a3  mov     rax, [rcx]
0x1800189a6  mov     rax, [rax+10h]
0x1800189aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189af  nop
0x1800189b0  mov     rcx, [rbp+pv]; pv
0x1800189b4  test    rcx, rcx
0x1800189b7  jz      short loc_1800189C0
0x1800189b9  call    cs:__imp_CoTaskMemFree
0x1800189bf  nop
0x1800189c0  mov     rcx, [rbp+var_28]
0x1800189c4  test    rcx, rcx
0x1800189c7  jz      short loc_1800189DE
0x1800189c9  mov     [rbp+var_28], 0
0x1800189d1  mov     rax, [rcx]
0x1800189d4  mov     rax, [rax+10h]
0x1800189d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189dd  nop
0x1800189de  xor     eax, eax
0x1800189e0  mov     rcx, [rbp+var_10]
0x1800189e4  xor     rcx, rsp; StackCookie
0x1800189e7  call    __security_check_cookie
0x1800189ec  lea     r11, [rsp+60h+var_s0]
0x1800189f1  mov     rbx, [r11+20h]
0x1800189f5  mov     rdi, [r11+28h]
0x1800189f9  mov     rsp, r11
0x1800189fc  pop     rbp
0x1800189fd  retn
0x1800189fe  mov     rcx, [rbp+8]; this
0x180018a02  mov     r9d, ebx; char *
0x180018a05  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\propsys\\itemprop.cp"...
0x180018a0c  mov     edx, 6D2h; void *
0x180018a11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018a16  nop
0x180018a17  mov     rcx, [rbp+var_28]
0x180018a1b  test    rcx, rcx
0x180018a1e  jz      short loc_180018A35
0x180018a20  mov     [rbp+var_28], 0
0x180018a28  mov     rax, [rcx]
0x180018a2b  mov     rax, [rax+10h]
0x180018a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a34  nop
0x180018a35  mov     eax, ebx
0x180018a37  jmp     short loc_1800189E0
0x180018a39  mov     rcx, [rbp+8]; this
0x180018a3d  mov     r9d, eax; char *
0x180018a40  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\propsys\\itemprop.cp"...
0x180018a47  mov     edx, 6D5h; void *
0x180018a4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018a51  jmp     short loc_180018A80
0x180018a53  mov     rcx, [rbp+8]; this
0x180018a57  mov     r9d, eax; char *
0x180018a5a  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\propsys\\itemprop.cp"...
0x180018a61  mov     edx, 6DDh; void *
0x180018a66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018a6b  nop
0x180018a6c  lea     rcx, [rbp+ppv]
0x180018a70  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180018a75  nop
0x180018a76  lea     rcx, [rbp+pv]
0x180018a7a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180018a7f  nop
0x180018a80  lea     rcx, [rbp+var_28]
0x180018a84  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180018a89  jmp     short loc_180018A35
```
