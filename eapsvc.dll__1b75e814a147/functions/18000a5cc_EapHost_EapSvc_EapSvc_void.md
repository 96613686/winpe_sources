# EapHost::EapSvc::EapSvc(void)

- ea: `0x18000a5cc`
- end: `0x18000a8e7`
- name: `??0EapSvc@EapHost@@QEAA@XZ`
- size: `795`
- prototype: `EapHost::EapSvc *__fastcall(EapHost::EapSvc *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b5c0`

## callees

- `0x18000a5ac`
- `0x18000a5cc`
- `0x18000cd98`
- `0x18000cee8`
- `0x18000d338`
- `0x18000d5cc`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a6d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a773`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a6d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a773`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a850`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a850`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000a6b7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000a758`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000a6b7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000a758`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a814`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a814`

## string_xrefs

- `0x18000a616`: `System\CurrentControlSet\Services\EapHost\Parameters`
- `0x18000a641`: `PeerInstalled`
- `0x18000a678`: `AuthenticatorInstalled`
- `0x18000a6b0`: `eapphost.dll`
- `0x18000a751`: `eapahost.dll`
- `0x18000a700`: `StopServiceOnLowPower`
- `0x18000a8ca`: `CoCreateInstance failed for CLSID_GlobalOptions`
- `0x18000a8d9`: `CLSID_GlobalOptions Set operation failed`
- `0x18000a884`: `RegOpenKeyExW`
- `0x18000a891`: `LoadLibraryW`
- `0x18000a89d`: `LoadLibraryW`

## pseudocode

```c
EapHost::EapSvc *__fastcall EapHost::EapSvc::EapSvc(EapHost::EapSvc *this)
{
  HMODULE *v2; // rsi
  HMODULE *v3; // r12
  bool v4; // r14
  int v5; // r15d
  bool v6; // di
  int v7; // r13d
  HMODULE LibraryW; // r15
  HMODULE v9; // rsi
  __int64 ProcAddress; // rax
  int v11; // eax
  int v12; // eax
  HRESULT v13; // eax
  int v14; // eax
  EapHost::EapSvc *result; // rax
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF
  int v17; // [rsp+38h] [rbp-40h]
  int v19; // [rsp+88h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp+18h] BYREF

  v2 = (HMODULE *)((char *)this + 16);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  v3 = (HMODULE *)((char *)this + 40);
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  ppv = 0;
  hKey = 0;
  v17 = 1;
  try
  {
    if ( (unsigned int)RegistryKey::Create() )
      SystemError::Throw(L"RegOpenKeyExW");
    v4 = 0;
    v19 = 0;
    v5 = RegistryKey::QueryValue(&hKey, L"PeerInstalled", &v19);
    if ( !v5 )
      v4 = v19 != 0;
    v6 = 0;
    v19 = 0;
    v7 = RegistryKey::QueryValue(&hKey, L"AuthenticatorInstalled", &v19);
    if ( !v7 )
      v6 = v19 != 0;
    if ( !v5 && v4 )
    {
      LibraryW = LoadLibraryW(L"eapphost.dll");
      if ( !LibraryW )
        SystemError::Throw(L"LoadLibraryW");
      if ( *v2 )
        FreeLibrary(*v2);
      *v2 = LibraryW;
      *((_QWORD *)this + 3) = DllHandle::GetProcAddress(v2, "InitializeEapHost");
      *((_QWORD *)this + 4) = DllHandle::GetProcAddress(v2, "UninitializeEapHost");
      *(_QWORD *)this = DllHandle::GetProcAddress(v2, "StopServiceOnLowPower");
      *((_QWORD *)this + 1) = DllHandle::GetProcAddress(v2, "OnSessionChange");
      if ( !*((_QWORD *)this + 3) || !*((_QWORD *)this + 4) )
      {
        v4 = 0;
        *((_QWORD *)this + 3) = 0;
        *((_QWORD *)this + 4) = 0;
        *(_QWORD *)this = 0;
      }
    }
    if ( !v7 && v6 )
    {
      v9 = LoadLibraryW(L"eapahost.dll");
      if ( !v9 )
        SystemError::Throw(L"LoadLibraryW");
      if ( *v3 )
        FreeLibrary(*v3);
      *v3 = v9;
      *((_QWORD *)this + 6) = DllHandle::GetProcAddress(v3, "InitializeEapHost");
      ProcAddress = DllHandle::GetProcAddress(v3, "UninitializeEapHost");
      *((_QWORD *)this + 7) = ProcAddress;
      if ( !*((_QWORD *)this + 6) || !ProcAddress )
      {
        v6 = 0;
        *((_QWORD *)this + 6) = 0;
        *((_QWORD *)this + 7) = 0;
      }
    }
    if ( v4 )
    {
      v11 = (*((__int64 (**)(void))this + 3))();
      if ( v11 < 0 )
        SystemError::Throw<long>(L"peerInitialize", (unsigned __int16)v11);
    }
    if ( v6 )
    {
      v12 = (*((__int64 (**)(void))this + 6))();
      if ( v12 < 0 )
        SystemError::Throw<long>(L"authrInitialize", (unsigned __int16)v12);
    }
    if ( v4 || v6 )
    {
      v13 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
      if ( v13 < 0 )
        SystemError::Throw<long>(L"CoCreateInstance failed for CLSID_GlobalOptions", (unsigned __int16)v13);
      v14 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
      if ( v14 < 0 )
        SystemError::Throw<long>(L"CLSID_GlobalOptions Set operation failed", (unsigned __int16)v14);
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    result = this;
  }
  catch ( Exception )
  {
    *((_QWORD *)this + 3) = 0;
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    if ( *((_QWORD *)this + 4) )
    {
      (*((void (**)(void))this + 4))();
      *((_QWORD *)this + 4) = 0;
    }
    *((_QWORD *)this + 6) = 0;
    if ( *((_QWORD *)this + 7) )
    {
      (*((void (**)(void))this + 7))();
      *((_QWORD *)this + 7) = 0;
    }
    throw;
  }
  if ( (unsigned int)RegistryKey::Create() )
    SystemError::Throw(L"RegOpenKeyExW");
}

```

## disassembly

```asm
0x18000a5cc  mov     rax, rsp
0x18000a5cf  mov     [rax+8], rcx
0x18000a5d3  push    rbx
0x18000a5d4  push    rsi
0x18000a5d5  push    rdi
0x18000a5d6  push    r12
0x18000a5d8  push    r13
0x18000a5da  push    r14
0x18000a5dc  push    r15
0x18000a5de  sub     rsp, 40h
0x18000a5e2  mov     rbx, rcx
0x18000a5e5  lea     rsi, [rcx+10h]
0x18000a5e9  xor     r13d, r13d
0x18000a5ec  mov     [rsi], r13
0x18000a5ef  mov     [rcx+18h], r13
0x18000a5f3  mov     [rcx+20h], r13
0x18000a5f7  lea     r12, [rcx+28h]
0x18000a5fb  mov     [r12], r13
0x18000a5ff  mov     [rcx+30h], r13
0x18000a603  mov     [rcx+38h], r13
0x18000a607  mov     [rax+18h], r13
0x18000a60b  mov     [rax-48h], r13
0x18000a60f  mov     dword ptr [rax-40h], 1
0x18000a616  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Ea"...
0x18000a61d  lea     rcx, [rax-48h]
0x18000a621  call    ?Create@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK_N@Z; RegistryKey::Create(HKEY__ *,wchar_t const *,ulong,bool)
0x18000a626  test    eax, eax
0x18000a628  jnz     loc_18000A884
0x18000a62e  mov     r14b, r13b
0x18000a631  mov     [rsp+78h+arg_8], r13d
0x18000a639  lea     r8, [rsp+78h+arg_8]
0x18000a641  lea     rdx, aPeerinstalled; "PeerInstalled"
0x18000a648  lea     rcx, [rsp+78h+hKey]
0x18000a64d  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18000a652  mov     r15d, eax
0x18000a655  test    eax, eax
0x18000a657  jnz     short loc_18000A665
0x18000a659  cmp     [rsp+78h+arg_8], r13d
0x18000a661  setnz   r14b
0x18000a665  mov     dil, r13b
0x18000a668  mov     [rsp+78h+arg_8], r13d
0x18000a670  lea     r8, [rsp+78h+arg_8]
0x18000a678  lea     rdx, aAuthenticatori; "AuthenticatorInstalled"
0x18000a67f  lea     rcx, [rsp+78h+hKey]
0x18000a684  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18000a689  mov     r13d, eax
0x18000a68c  test    eax, eax
0x18000a68e  jnz     short loc_18000A69B
0x18000a690  cmp     [rsp+78h+arg_8], eax
0x18000a697  setnz   dil
0x18000a69b  test    r15d, r15d
0x18000a69e  jnz     loc_18000A744
0x18000a6a4  xor     r15d, r15d
0x18000a6a7  test    r14b, r14b
0x18000a6aa  jz      loc_18000A747
0x18000a6b0  lea     rcx, LibFileName; "eapphost.dll"
0x18000a6b7  call    cs:__imp_LoadLibraryW
0x18000a6bd  mov     r15, rax
0x18000a6c0  test    rax, rax
0x18000a6c3  jz      loc_18000A891
0x18000a6c9  mov     rcx, [rsi]; hLibModule
0x18000a6cc  test    rcx, rcx
0x18000a6cf  jz      short loc_18000A6D7
0x18000a6d1  call    cs:__imp_FreeLibrary
0x18000a6d7  mov     [rsi], r15
0x18000a6da  lea     rdx, aInitializeeaph; "InitializeEapHost"
0x18000a6e1  mov     rcx, rsi
0x18000a6e4  call    ?GetProcAddress@DllHandle@@AEBAP6A_JXZPEBD@Z; DllHandle::GetProcAddress(char const *)
0x18000a6e9  mov     [rbx+18h], rax
0x18000a6ed  lea     rdx, aUninitializeea; "UninitializeEapHost"
0x18000a6f4  mov     rcx, rsi
0x18000a6f7  call    ?GetProcAddress@DllHandle@@AEBAP6A_JXZPEBD@Z; DllHandle::GetProcAddress(char const *)
0x18000a6fc  mov     [rbx+20h], rax
0x18000a700  lea     rdx, aStopserviceonl; "StopServiceOnLowPower"
0x18000a707  mov     rcx, rsi
0x18000a70a  call    ?GetProcAddress@DllHandle@@AEBAP6A_JXZPEBD@Z; DllHandle::GetProcAddress(char const *)
0x18000a70f  mov     [rbx], rax
0x18000a712  lea     rdx, aOnsessionchang; "OnSessionChange"
0x18000a719  mov     rcx, rsi
0x18000a71c  call    ?GetProcAddress@DllHandle@@AEBAP6A_JXZPEBD@Z; DllHandle::GetProcAddress(char const *)
0x18000a721  mov     [rbx+8], rax
0x18000a725  xor     r15d, r15d
0x18000a728  cmp     [rbx+18h], r15
0x18000a72c  jz      short loc_18000A734
0x18000a72e  cmp     [rbx+20h], r15
0x18000a732  jnz     short loc_18000A747
0x18000a734  mov     r14b, r15b
0x18000a737  mov     [rbx+18h], r15
0x18000a73b  mov     [rbx+20h], r15
0x18000a73f  mov     [rbx], r15
0x18000a742  jmp     short loc_18000A747
0x18000a744  xor     r15d, r15d
0x18000a747  test    r13d, r13d
0x18000a74a  jnz     short loc_18000A7B9
0x18000a74c  test    dil, dil
0x18000a74f  jz      short loc_18000A7B9
0x18000a751  lea     rcx, aEapahostDll; "eapahost.dll"
0x18000a758  call    cs:__imp_LoadLibraryW
0x18000a75e  mov     rsi, rax
0x18000a761  test    rax, rax
0x18000a764  jz      loc_18000A89D
0x18000a76a  mov     rcx, [r12]; hLibModule
0x18000a76e  test    rcx, rcx
0x18000a771  jz      short loc_18000A779
0x18000a773  call    cs:__imp_FreeLibrary
0x18000a779  mov     [r12], rsi
0x18000a77d  lea     rdx, aInitializeeaph; "InitializeEapHost"
0x18000a784  mov     rcx, r12
0x18000a787  call    ?GetProcAddress@DllHandle@@AEBAP6A_JXZPEBD@Z; DllHandle::GetProcAddress(char const *)
0x18000a78c  mov     [rbx+30h], rax
0x18000a790  lea     rdx, aUninitializeea; "UninitializeEapHost"
0x18000a797  mov     rcx, r12
0x18000a79a  call    ?GetProcAddress@DllHandle@@AEBAP6A_JXZPEBD@Z; DllHandle::GetProcAddress(char const *)
0x18000a79f  mov     [rbx+38h], rax
0x18000a7a3  cmp     [rbx+30h], r15
0x18000a7a7  jz      short loc_18000A7AE
0x18000a7a9  test    rax, rax
0x18000a7ac  jnz     short loc_18000A7B9
0x18000a7ae  mov     dil, r15b
0x18000a7b1  mov     [rbx+30h], r15
0x18000a7b5  mov     [rbx+38h], r15
0x18000a7b9  test    r14b, r14b
0x18000a7bc  jz      short loc_18000A7CF
0x18000a7be  mov     rax, [rbx+18h]
0x18000a7c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7c7  test    eax, eax
0x18000a7c9  js      loc_18000A8A9
0x18000a7cf  test    dil, dil
0x18000a7d2  jz      short loc_18000A7E5
0x18000a7d4  mov     rax, [rbx+30h]
0x18000a7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7dd  test    eax, eax
0x18000a7df  js      loc_18000A8B8
0x18000a7e5  test    r14b, r14b
0x18000a7e8  jnz     short loc_18000A7EF
0x18000a7ea  test    dil, dil
0x18000a7ed  jz      short loc_18000A846
0x18000a7ef  lea     rax, [rsp+78h+arg_10]
0x18000a7f7  mov     [rsp+78h+ppv], rax; ppv
0x18000a7fc  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18000a803  mov     edi, 1
0x18000a808  mov     r8d, edi; dwClsContext
0x18000a80b  xor     edx, edx; pUnkOuter
0x18000a80d  lea     rcx, CLSID_GlobalOptions; rclsid
0x18000a814  call    cs:__imp_CoCreateInstance
0x18000a81a  test    eax, eax
0x18000a81c  js      loc_18000A8C7
0x18000a822  mov     rcx, [rsp+78h+arg_10]
0x18000a82a  mov     rax, [rcx]
0x18000a82d  mov     r8, rdi
0x18000a830  mov     edx, 5
0x18000a835  mov     rax, [rax+18h]
0x18000a839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a83e  test    eax, eax
0x18000a840  js      loc_18000A8D6
0x18000a846  mov     rcx, [rsp+78h+hKey]; hKey
0x18000a84b  test    rcx, rcx
0x18000a84e  jz      short loc_18000A857
0x18000a850  call    cs:__imp_RegCloseKey
0x18000a856  nop
0x18000a857  mov     rcx, [rsp+78h+arg_10]
0x18000a85f  test    rcx, rcx
0x18000a862  jz      short loc_18000A871
0x18000a864  mov     rax, [rcx]
0x18000a867  mov     rax, [rax+10h]
0x18000a86b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a870  nop
0x18000a871  mov     rax, rbx
0x18000a874  add     rsp, 40h
0x18000a878  pop     r15
0x18000a87a  pop     r14
0x18000a87c  pop     r13
0x18000a87e  pop     r12
0x18000a880  pop     rdi
0x18000a881  pop     rsi
0x18000a882  pop     rbx
0x18000a883  retn
0x18000a884  lea     rcx, aRegopenkeyexw; "RegOpenKeyExW"
0x18000a88b  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
0x18000a891  lea     rcx, aLoadlibraryw; "LoadLibraryW"
0x18000a898  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
0x18000a89d  lea     rcx, aLoadlibraryw; "LoadLibraryW"
0x18000a8a4  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
0x18000a8a9  movzx   edx, ax
0x18000a8ac  lea     rcx, aPeerinitialize; "peerInitialize"
0x18000a8b3  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
0x18000a8b8  movzx   edx, ax
0x18000a8bb  lea     rcx, aAuthrinitializ; "authrInitialize"
0x18000a8c2  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
0x18000a8c7  movzx   edx, ax
0x18000a8ca  lea     rcx, aCocreateinstan_0; "CoCreateInstance failed for CLSID_Globa"...
0x18000a8d1  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
0x18000a8d6  movzx   edx, ax
0x18000a8d9  lea     rcx, aClsidGlobalopt; "CLSID_GlobalOptions Set operation faile"...
0x18000a8e0  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
```
