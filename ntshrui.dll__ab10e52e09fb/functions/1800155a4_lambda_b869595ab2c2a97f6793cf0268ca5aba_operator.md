# _lambda_b869595ab2c2a97f6793cf0268ca5aba_::operator()

- ea: `0x1800155a4`
- end: `0x180015806`
- name: `_lambda_b869595ab2c2a97f6793cf0268ca5aba_::operator()`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014830`

## callees

- `0x180008900`
- `0x1800155a4`
- `0x180015970`
- `0x180015ab0`
- `0x1800214cc`
- `0x180021dd4`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015772`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800155dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800155dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001560a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001560a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157f3`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180015681`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180015681`

## string_xrefs

- `0x1800155cf`: `Software\Microsoft\Windows\CurrentVersion\Explorer\CommandStore`
- `0x1800155ee`: `shell\osshell\lmui\ntshrui\dll\share.cpp`
- `0x18001563d`: `shell\osshell\lmui\ntshrui\dll\share.cpp`
- `0x180015694`: `shell\osshell\lmui\ntshrui\dll\share.cpp`
- `0x1800156ce`: `shell\osshell\lmui\ntshrui\dll\share.cpp`
- `0x18001574a`: `shell\osshell\lmui\ntshrui\dll\share.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_b869595ab2c2a97f6793cf0268ca5aba_::operator()(_QWORD ***a1)
{
  unsigned int v2; // eax
  unsigned __int64 v3; // r8
  unsigned int v4; // ebx
  void *v6; // rsi
  HRESULT v7; // eax
  int v8; // eax
  void *v9; // rcx
  void *v10; // rbx
  __int64 (__fastcall *v11)(void *, GUID *, __int64 *); // rdi
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  void *v15; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-20h]
  int phkResulta; // [rsp+20h] [rbp-20h]
  LPVOID pv[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  void *ppv; // [rsp+78h] [rbp+38h] BYREF
  __int64 v21; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\CommandStore",
         0,
         9u,
         &hKey);
  if ( v2 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xC9,
           (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\share.cpp",
           (const char *)v2,
           phkResult);
LABEL_3:
    if ( hKey )
      RegCloseKey(hKey);
    return v4;
  }
  wil::make_cotaskmem_string_nothrow((wil *)pv, L"Windows.Share", v3);
  v6 = pv[0];
  if ( !pv[0] )
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\share.cpp",
      (const char *)0x8007000ELL,
      phkResult);
LABEL_17:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v4;
  }
  ppv = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
  v7 = SHCoCreateInstance(0, &CLSID_RegDataDrivenCommand, 0, &GUID_697d9b7b_a001_4cdd_8be8_eb7874b5b956, &ppv);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\share.cpp",
      (const char *)(unsigned int)v7,
      phkResulta);
LABEL_16:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
    CoTaskMemFree(v6);
    goto LABEL_17;
  }
  v8 = (*(__int64 (__fastcall **)(void *, HKEY, void *))(*(_QWORD *)ppv + 24LL))(ppv, hKey, v6);
  v4 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\share.cpp",
      (const char *)(unsigned int)v8,
      phkResulta);
    v9 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    CoTaskMemFree(v6);
    goto LABEL_3;
  }
  v21 = 0;
  v10 = ppv;
  v11 = **(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v21);
  v12 = v11(v10, &GUID_a08ce4d0_fa25_44ab_b57c_c7b1c323e0b9, &v21);
  v4 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\share.cpp",
      (const char *)(unsigned int)v12,
      phkResulta);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v21);
    goto LABEL_16;
  }
  v13 = v21;
  v21 = 0;
  ***a1 = v13;
  pv[0] = 0;
  **a1[1] = v6;
  v14 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800155a4  push    rbp
0x1800155a6  push    rbx
0x1800155a7  push    rsi
0x1800155a8  push    rdi
0x1800155a9  push    r14
0x1800155ab  mov     rbp, rsp
0x1800155ae  sub     rsp, 40h
0x1800155b2  mov     r14, rcx
0x1800155b5  mov     [rbp+hKey], 0
0x1800155bd  lea     rax, [rbp+hKey]
0x1800155c1  mov     qword ptr [rsp+40h+phkResult], rax; int
0x1800155c6  mov     r9d, 9; samDesired
0x1800155cc  xor     r8d, r8d; ulOptions
0x1800155cf  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800155d6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800155dd  call    cs:__imp_RegOpenKeyExW
0x1800155e3  test    eax, eax
0x1800155e5  jz      short loc_180015617
0x1800155e7  mov     rcx, [rbp+28h]; this
0x1800155eb  mov     r9d, eax; char *
0x1800155ee  lea     r8, aShellOsshellLm_3; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x1800155f5  mov     edx, 0C9h; void *
0x1800155fa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800155ff  mov     ebx, eax
0x180015601  mov     rcx, [rbp+hKey]; hKey
0x180015605  test    rcx, rcx
0x180015608  jz      short loc_180015610
0x18001560a  call    cs:__imp_RegCloseKey
0x180015610  mov     eax, ebx
0x180015612  jmp     loc_1800157FB
0x180015617  lea     rdx, aWindowsShare; "Windows.Share"
0x18001561e  lea     rcx, [rbp+pv]; this
0x180015622  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180015627  nop
0x180015628  mov     rsi, [rbp+pv]
0x18001562c  test    rsi, rsi
0x18001562f  jnz     short loc_180015654
0x180015631  mov     rcx, [rbp+28h]; this
0x180015635  mov     ebx, 8007000Eh
0x18001563a  mov     r9d, ebx; char *
0x18001563d  lea     r8, aShellOsshellLm_3; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180015644  mov     edx, 0CCh; void *
0x180015649  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001564e  nop
0x18001564f  jmp     loc_180015779
0x180015654  mov     [rbp+ppv], 0
0x18001565c  lea     rcx, [rbp+ppv]
0x180015660  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180015665  lea     rax, [rbp+ppv]
0x180015669  mov     qword ptr [rsp+40h+phkResult], rax; int
0x18001566e  lea     r9, _GUID_697d9b7b_a001_4cdd_8be8_eb7874b5b956; riid
0x180015675  xor     r8d, r8d; pUnkOuter
0x180015678  lea     rdx, CLSID_RegDataDrivenCommand; pclsid
0x18001567f  xor     ecx, ecx; pszCLSID
0x180015681  call    cs:__imp_SHCoCreateInstance
0x180015687  mov     ebx, eax
0x180015689  test    eax, eax
0x18001568b  jns     short loc_1800156AA
0x18001568d  mov     rcx, [rbp+28h]; this
0x180015691  mov     r9d, eax; char *
0x180015694  lea     r8, aShellOsshellLm_3; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18001569b  mov     edx, 0CFh; void *
0x1800156a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800156a5  jmp     loc_180015765
0x1800156aa  mov     rcx, [rbp+ppv]
0x1800156ae  mov     rax, [rcx]
0x1800156b1  mov     r8, rsi
0x1800156b4  mov     rdx, [rbp+hKey]
0x1800156b8  mov     rax, [rax+18h]
0x1800156bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156c1  mov     ebx, eax
0x1800156c3  test    eax, eax
0x1800156c5  jns     short loc_18001570C
0x1800156c7  mov     rcx, [rbp+28h]; this
0x1800156cb  mov     r9d, eax; char *
0x1800156ce  lea     r8, aShellOsshellLm_3; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x1800156d5  mov     edx, 0D0h; void *
0x1800156da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800156df  nop
0x1800156e0  mov     rcx, [rbp+ppv]
0x1800156e4  test    rcx, rcx
0x1800156e7  jz      short loc_1800156FE
0x1800156e9  mov     [rbp+ppv], 0
0x1800156f1  mov     rax, [rcx]
0x1800156f4  mov     rax, [rax+10h]
0x1800156f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156fd  nop
0x1800156fe  mov     rcx, rsi; pv
0x180015701  call    cs:__imp_CoTaskMemFree
0x180015707  jmp     loc_180015601
0x18001570c  mov     [rbp+arg_10], 0
0x180015714  mov     rbx, [rbp+ppv]
0x180015718  mov     rax, [rbx]
0x18001571b  mov     rdi, [rax]
0x18001571e  lea     rcx, [rbp+arg_10]
0x180015722  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180015727  lea     r8, [rbp+arg_10]
0x18001572b  lea     rdx, _GUID_a08ce4d0_fa25_44ab_b57c_c7b1c323e0b9
0x180015732  mov     rcx, rbx
0x180015735  mov     rax, rdi
0x180015738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001573d  mov     ebx, eax
0x18001573f  test    eax, eax
0x180015741  jns     short loc_180015787
0x180015743  mov     rcx, [rbp+28h]; this
0x180015747  mov     r9d, eax; char *
0x18001574a  lea     r8, aShellOsshellLm_3; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180015751  mov     edx, 0D2h; void *
0x180015756  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001575b  lea     rcx, [rbp+arg_10]
0x18001575f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180015764  nop
0x180015765  lea     rcx, [rbp+ppv]
0x180015769  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001576e  nop
0x18001576f  mov     rcx, rsi; pv
0x180015772  call    cs:__imp_CoTaskMemFree
0x180015778  nop
0x180015779  lea     rcx, [rbp+hKey]
0x18001577d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180015782  jmp     loc_180015610
0x180015787  mov     rdx, [rbp+arg_10]
0x18001578b  mov     [rbp+arg_10], 0
0x180015793  mov     rax, [r14]
0x180015796  mov     rcx, [rax]
0x180015799  mov     [rcx], rdx
0x18001579c  mov     [rbp+pv], 0
0x1800157a4  mov     rax, [r14+8]
0x1800157a8  mov     rcx, [rax]
0x1800157ab  mov     [rcx], rsi
0x1800157ae  mov     rcx, [rbp+arg_10]
0x1800157b2  test    rcx, rcx
0x1800157b5  jz      short loc_1800157CC
0x1800157b7  mov     [rbp+arg_10], 0
0x1800157bf  mov     rax, [rcx]
0x1800157c2  mov     rax, [rax+10h]
0x1800157c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157cb  nop
0x1800157cc  mov     rcx, [rbp+ppv]
0x1800157d0  test    rcx, rcx
0x1800157d3  jz      short loc_1800157EA
0x1800157d5  mov     [rbp+ppv], 0
0x1800157dd  mov     rax, [rcx]
0x1800157e0  mov     rax, [rax+10h]
0x1800157e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157e9  nop
0x1800157ea  mov     rcx, [rbp+hKey]; hKey
0x1800157ee  test    rcx, rcx
0x1800157f1  jz      short loc_1800157F9
0x1800157f3  call    cs:__imp_RegCloseKey
0x1800157f9  xor     eax, eax
0x1800157fb  add     rsp, 40h
0x1800157ff  pop     r14
0x180015801  pop     rdi
0x180015802  pop     rsi
0x180015803  pop     rbx
0x180015804  pop     rbp
0x180015805  retn
```
