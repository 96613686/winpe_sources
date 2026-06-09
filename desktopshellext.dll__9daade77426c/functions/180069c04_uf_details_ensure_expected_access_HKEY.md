# uf::details::ensure_expected_access(HKEY__ *)

- ea: `0x180069c04`
- end: `0x180069e6a`
- name: `?ensure_expected_access@details@uf@@YAXPEAUHKEY__@@@Z`
- size: `614`
- prototype: `void __fastcall(HKEY hKey, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002346c`

## callees

- `0x18001a18c`
- `0x18002661c`
- `0x180039c50`
- `0x18005ed50`
- `0x180069c04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180069c2b`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180069c88`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180069c2b`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180069c88`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180069e0d`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180069e0d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069c6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069cb5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069da3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069c6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069cb5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069da3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180069d41`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180069d41`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180069db8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180069db8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180069de4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180069de4`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180069cce`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180069cce`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180069d78`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180069d78`

## string_xrefs

- `0x180069c3a`: `shellcommon\internal\shell\inc\UndockedFlighting\Registry.h`
- `0x180069c99`: `shellcommon\internal\shell\inc\UndockedFlighting\Registry.h`
- `0x180069cdc`: `shellcommon\internal\shell\inc\UndockedFlighting\Registry.h`
- `0x180069d4f`: `shellcommon\internal\shell\inc\UndockedFlighting\Registry.h`
- `0x180069d89`: `shellcommon\internal\shell\inc\UndockedFlighting\Registry.h`
- `0x180069dc6`: `shellcommon\internal\shell\inc\UndockedFlighting\Registry.h`
- `0x180069df2`: `shellcommon\internal\shell\inc\UndockedFlighting\Registry.h`
- `0x180069e1e`: `shellcommon\internal\shell\inc\UndockedFlighting\Registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall uf::details::ensure_expected_access(HKEY hKey, HKEY a2)
{
  unsigned int KeySecurity; // eax
  HLOCAL v4; // rbx
  unsigned int v5; // eax
  HLOCAL v6; // rdi
  const char *v7; // r9
  const char *v8; // r9
  DWORD v9; // eax
  HLOCAL v10; // rbx
  const char *v11; // r9
  const char *v12; // r9
  unsigned int v13; // eax
  WINBOOL bDaclPresent; // [rsp+20h] [rbp-60h] BYREF
  PACL NewAcl; // [rsp+28h] [rbp-58h] BYREF
  PACL pDacl; // [rsp+30h] [rbp-50h] BYREF
  HLOCAL v17; // [rsp+38h] [rbp-48h] BYREF
  HLOCAL v18; // [rsp+40h] [rbp-40h] BYREF
  HLOCAL v19; // [rsp+48h] [rbp-38h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  DWORD cbSecurityDescriptor; // [rsp+A8h] [rbp+28h] BYREF
  DWORD cbSid; // [rsp+B0h] [rbp+30h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+B8h] [rbp+38h] BYREF

  cbSecurityDescriptor = 0;
  KeySecurity = RegGetKeySecurity(hKey, 4u, 0, &cbSecurityDescriptor);
  if ( KeySecurity != 122 )
  {
    if ( KeySecurity )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1D,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\Registry.h",
        (const char *)KeySecurity,
        bDaclPresent);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\Registry.h",
      (const char *)0x8000FFFFLL,
      bDaclPresent);
  }
  v4 = LocalAlloc(0x40u, cbSecurityDescriptor);
  v19 = v4;
  v5 = RegGetKeySecurity(hKey, 4u, v4, &cbSecurityDescriptor);
  if ( v5 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x28,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\Registry.h",
      (const char *)v5,
      bDaclPresent);
  cbSid = 68;
  v6 = LocalAlloc(0, 0x44u);
  v18 = v6;
  if ( !CreateWellKnownSid(WinBuiltinAnyPackageSid, 0, v6, &cbSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2D,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\Registry.h",
      v7);
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
  *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 2;
  pListOfExplicitEntries.grfAccessPermissions = 131097;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.grfInheritance = 3;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v6;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  if ( !GetSecurityDescriptorDacl(v4, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3F,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\Registry.h",
      v8);
  NewAcl = 0;
  v9 = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl, &NewAcl);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x47,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\Registry.h",
      (const char *)v9,
      bDaclPresent);
  v10 = LocalAlloc(0x40u, 0x28u);
  v17 = v10;
  if ( !InitializeSecurityDescriptor(v10, 1u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4C,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\Registry.h",
      v11);
  if ( !SetSecurityDescriptorDacl(v10, 1, NewAcl, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x53,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\Registry.h",
      v12);
  v13 = RegSetKeySecurity(hKey, 4u, v10);
  if ( v13 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x58,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\Registry.h",
      (const char *)v13,
      bDaclPresent);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&NewAcl);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
}

```

## disassembly

```asm
0x180069c04  mov     [rsp-18h+arg_0], rbx
0x180069c09  push    rbp
0x180069c0a  push    rsi
0x180069c0b  push    rdi
0x180069c0c  mov     rbp, rsp
0x180069c0f  sub     rsp, 80h
0x180069c16  mov     rsi, rcx
0x180069c19  mov     [rbp+cbSecurityDescriptor], 0
0x180069c20  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180069c24  xor     r8d, r8d; pSecurityDescriptor
0x180069c27  lea     edx, [r8+4]; SecurityInformation
0x180069c2b  call    cs:__imp_RegGetKeySecurity
0x180069c31  cmp     eax, 7Ah ; 'z'
0x180069c34  jz      short loc_180069C64
0x180069c36  mov     rcx, [rbp+18h]; this
0x180069c3a  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180069c41  test    eax, eax
0x180069c43  jz      short loc_180069C53
0x180069c45  mov     r9d, eax; char *
0x180069c48  mov     edx, 1Dh; void *
0x180069c4d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180069c53  mov     r9d, 8000FFFFh; char *
0x180069c59  mov     edx, 20h ; ' '; void *
0x180069c5e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069c64  mov     edx, [rbp+cbSecurityDescriptor]; uBytes
0x180069c67  mov     ecx, 40h ; '@'; uFlags
0x180069c6c  call    cs:__imp_LocalAlloc
0x180069c72  mov     rbx, rax
0x180069c75  mov     [rbp+var_38], rax
0x180069c79  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180069c7d  mov     r8, rax; pSecurityDescriptor
0x180069c80  mov     edx, 4; SecurityInformation
0x180069c85  mov     rcx, rsi; hKey
0x180069c88  call    cs:__imp_RegGetKeySecurity
0x180069c8e  mov     rcx, [rbp+18h]; this
0x180069c92  test    eax, eax
0x180069c94  jz      short loc_180069CAB
0x180069c96  mov     r9d, eax; char *
0x180069c99  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180069ca0  mov     edx, 28h ; '('; void *
0x180069ca5  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180069cab  mov     edx, 44h ; 'D'; uBytes
0x180069cb0  mov     [rbp+cbSid], edx
0x180069cb3  xor     ecx, ecx; uFlags
0x180069cb5  call    cs:__imp_LocalAlloc
0x180069cbb  mov     rdi, rax
0x180069cbe  mov     [rbp+var_40], rax
0x180069cc2  lea     r9, [rbp+cbSid]; cbSid
0x180069cc6  mov     r8, rax; pSid
0x180069cc9  xor     edx, edx; DomainSid
0x180069ccb  lea     ecx, [rdx+54h]; WellKnownSidType
0x180069cce  call    cs:__imp_CreateWellKnownSid
0x180069cd4  mov     rcx, [rbp+18h]; this
0x180069cd8  test    eax, eax
0x180069cda  jnz     short loc_180069CEC
0x180069cdc  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180069ce3  lea     edx, [rax+2Dh]; void *
0x180069ce6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180069cec  xorps   xmm0, xmm0
0x180069cef  movdqu  xmmword ptr [rbp+pListOfExplicitEntries+0Ch], xmm0
0x180069cf4  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x180069cfc  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], 20019h
0x180069d03  mov     [rbp+pListOfExplicitEntries.grfAccessMode], 1
0x180069d0a  mov     [rbp+pListOfExplicitEntries.grfInheritance], 3
0x180069d11  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeForm], 0
0x180069d18  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rdi
0x180069d1c  mov     [rbp+bDaclPresent], 0
0x180069d23  mov     [rbp+bDaclDefaulted], 0
0x180069d2a  mov     [rbp+pDacl], 0
0x180069d32  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180069d36  lea     r8, [rbp+pDacl]; pDacl
0x180069d3a  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180069d3e  mov     rcx, rbx; pSecurityDescriptor
0x180069d41  call    cs:__imp_GetSecurityDescriptorDacl
0x180069d47  mov     rcx, [rbp+18h]; this
0x180069d4b  test    eax, eax
0x180069d4d  jnz     short loc_180069D5F
0x180069d4f  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180069d56  lea     edx, [rax+3Fh]; void *
0x180069d59  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180069d5f  mov     [rbp+NewAcl], 0
0x180069d67  lea     r9, [rbp+NewAcl]; NewAcl
0x180069d6b  mov     r8, [rbp+pDacl]; OldAcl
0x180069d6f  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x180069d73  mov     ecx, 1; cCountOfExplicitEntries
0x180069d78  call    cs:__imp_SetEntriesInAclW
0x180069d7e  mov     rcx, [rbp+18h]; this
0x180069d82  test    eax, eax
0x180069d84  jz      short loc_180069D9B
0x180069d86  mov     r9d, eax; char *
0x180069d89  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180069d90  mov     edx, 47h ; 'G'; void *
0x180069d95  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180069d9b  mov     edx, 28h ; '('; uBytes
0x180069da0  lea     ecx, [rdx+18h]; uFlags
0x180069da3  call    cs:__imp_LocalAlloc
0x180069da9  mov     rbx, rax
0x180069dac  mov     [rbp+var_48], rax
0x180069db0  mov     edx, 1; dwRevision
0x180069db5  mov     rcx, rax; pSecurityDescriptor
0x180069db8  call    cs:__imp_InitializeSecurityDescriptor
0x180069dbe  mov     rcx, [rbp+18h]; this
0x180069dc2  test    eax, eax
0x180069dc4  jnz     short loc_180069DD6
0x180069dc6  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180069dcd  lea     edx, [rax+4Ch]; void *
0x180069dd0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180069dd6  xor     r9d, r9d; bDaclDefaulted
0x180069dd9  mov     r8, [rbp+NewAcl]; pDacl
0x180069ddd  lea     edx, [r9+1]; bDaclPresent
0x180069de1  mov     rcx, rbx; pSecurityDescriptor
0x180069de4  call    cs:__imp_SetSecurityDescriptorDacl
0x180069dea  mov     rcx, [rbp+18h]; this
0x180069dee  test    eax, eax
0x180069df0  jnz     short loc_180069E02
0x180069df2  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180069df9  lea     edx, [rax+53h]; void *
0x180069dfc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180069e02  mov     r8, rbx; pSecurityDescriptor
0x180069e05  mov     edx, 4; SecurityInformation
0x180069e0a  mov     rcx, rsi; hKey
0x180069e0d  call    cs:__imp_RegSetKeySecurity
0x180069e13  mov     rcx, [rbp+18h]; this
0x180069e17  test    eax, eax
0x180069e19  jz      short loc_180069E30
0x180069e1b  mov     r9d, eax; char *
0x180069e1e  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180069e25  mov     edx, 58h ; 'X'; void *
0x180069e2a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180069e30  lea     rcx, [rbp+var_48]
0x180069e34  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180069e39  nop
0x180069e3a  lea     rcx, [rbp+NewAcl]
0x180069e3e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180069e43  nop
0x180069e44  lea     rcx, [rbp+var_40]
0x180069e48  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180069e4d  nop
0x180069e4e  lea     rcx, [rbp+var_38]
0x180069e52  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180069e57  mov     rbx, [rsp+80h+arg_0]
0x180069e5f  add     rsp, 80h
0x180069e66  pop     rdi
0x180069e67  pop     rsi
0x180069e68  pop     rbp
0x180069e69  retn
```
