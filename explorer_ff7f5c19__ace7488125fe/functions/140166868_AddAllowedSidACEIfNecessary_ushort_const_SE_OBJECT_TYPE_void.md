# AddAllowedSidACEIfNecessary(ushort const *,_SE_OBJECT_TYPE,void *)

- ea: `0x140166868`
- end: `0x140166a8a`
- name: `?AddAllowedSidACEIfNecessary@@YAJPEBGW4_SE_OBJECT_TYPE@@PEAX@Z`
- size: `546`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, enum _SE_OBJECT_TYPE, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14019449c`

## callees

- `0x1400485bc`
- `0x140090258`
- `0x140098dc4`
- `0x14009de4c`
- `0x14010e160`
- `0x140166868`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14016697f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14016697f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14016691f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14016691f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140166964`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140166964`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1401668dc`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1401668dc`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1401669e0`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1401669e0`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x140166a3d`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x140166a3d`

## pseudocode

```c
__int64 __fastcall AddAllowedSidACEIfNecessary(LPWSTR pObjectName, enum _SE_OBJECT_TYPE a2, void *a3)
{
  DWORD NamedSecurityInfoW; // eax
  unsigned int LastError; // eax
  const char *v7; // r9
  unsigned int v8; // ebx
  DWORD i; // ebx
  DWORD v10; // eax
  __int64 v11; // rdx
  unsigned int ppsidGroup; // [rsp+20h] [rbp-49h]
  PACL NewAcl; // [rsp+40h] [rbp-29h] BYREF
  PACL pAcl; // [rsp+48h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+50h] [rbp-19h] BYREF
  LPVOID pAce; // [rsp+58h] [rbp-11h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+60h] [rbp-9h] BYREF
  __int64 pAclInformation; // [rsp+90h] [rbp+27h] BYREF
  int v20; // [rsp+98h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  pAcl = 0;
  ppSecurityDescriptor = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &ppSecurityDescriptor,
    0);
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 4u, 0, 0, &pAcl, 0, &ppSecurityDescriptor);
  if ( NamedSecurityInfoW )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xFE,
                  (unsigned int)"onecoreuap\\internal\\shell\\inc\\PrivacyConsentHelpers.h",
                  (const char *)NamedSecurityInfoW,
                  ppsidGroup);
LABEL_5:
    v8 = LastError;
    goto LABEL_18;
  }
  pAclInformation = 0;
  v20 = 0;
  if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x101,
                  (unsigned int)"onecoreuap\\internal\\shell\\inc\\PrivacyConsentHelpers.h",
                  v7);
    goto LABEL_5;
  }
  for ( i = 0; i < (unsigned int)pAclInformation; ++i )
  {
    pAce = 0;
    if ( GetAce(pAcl, i, &pAce) && EqualSid((char *)pAce + 8, a3) )
      goto LABEL_17;
  }
  pListOfExplicitEntries.grfAccessPermissions = 0x80000000;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 28);
  pListOfExplicitEntries.grfInheritance = 2;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)a3;
  NewAcl = 0;
  v10 = SetEntriesInAclW(1u, &pListOfExplicitEntries, pAcl, &NewAcl);
  if ( v10 )
  {
    v11 = 281;
LABEL_13:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v11,
           (unsigned int)"onecoreuap\\internal\\shell\\inc\\PrivacyConsentHelpers.h",
           (const char *)v10,
           ppsidGroup);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&NewAcl);
    goto LABEL_18;
  }
  v10 = SetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 4u, 0, 0, NewAcl, 0);
  if ( v10 )
  {
    v11 = 282;
    goto LABEL_13;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&NewAcl);
LABEL_17:
  v8 = 0;
LABEL_18:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppSecurityDescriptor);
  return v8;
}

```

## disassembly

```asm
0x140166868  mov     [rsp-8+arg_8], rbx
0x14016686d  push    rbp
0x14016686e  push    rsi
0x14016686f  push    rdi
0x140166870  lea     rbp, [rsp-47h]
0x140166875  sub     rsp, 0B0h
0x14016687c  mov     rax, cs:__security_cookie
0x140166883  xor     rax, rsp
0x140166886  mov     [rbp+57h+var_20], rax
0x14016688a  mov     rsi, rcx
0x14016688d  mov     [rbp+57h+pAcl], 0
0x140166895  lea     rcx, [rbp+57h+var_70]
0x140166899  mov     [rbp+57h+var_70], 0
0x1401668a1  xor     edx, edx
0x1401668a3  mov     rdi, r8
0x1401668a6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1401668ab  xor     r9d, r9d; ppsidOwner
0x1401668ae  lea     rax, [rbp+57h+var_70]
0x1401668b2  mov     [rsp+0C0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1401668b7  mov     rcx, rsi; pObjectName
0x1401668ba  lea     rax, [rbp+57h+pAcl]
0x1401668be  mov     [rsp+0C0h+ppSacl], 0; ppSacl
0x1401668c7  mov     [rsp+0C0h+ppDacl], rax; ppDacl
0x1401668cc  lea     edx, [r9+4]; ObjectType
0x1401668d0  mov     [rsp+0C0h+ppsidGroup], 0; unsigned int
0x1401668d9  mov     r8d, edx; SecurityInfo
0x1401668dc  call    cs:__imp_GetNamedSecurityInfoW
0x1401668e3  nop     dword ptr [rax+rax+00h]
0x1401668e8  test    eax, eax
0x1401668ea  jz      short loc_140166906
0x1401668ec  mov     rcx, [rbp+5Fh]; this
0x1401668f0  lea     r8, aOnecoreuapInte_15; "onecoreuap\\internal\\shell\\inc\\Priva"...
0x1401668f7  mov     r9d, eax; char *
0x1401668fa  mov     edx, 0FEh; void *
0x1401668ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140166904  jmp     short loc_140166944
0x140166906  mov     rcx, [rbp+57h+pAcl]; pAcl
0x14016690a  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x14016690e  xor     eax, eax
0x140166910  mov     [rbp+57h+pAclInformation], rax
0x140166914  mov     [rbp+57h+var_28], eax
0x140166917  lea     r9d, [rax+2]; dwAclInformationClass
0x14016691b  lea     r8d, [rax+0Ch]; nAclInformationLength
0x14016691f  call    cs:__imp_GetAclInformation
0x140166926  nop     dword ptr [rax+rax+00h]
0x14016692b  test    eax, eax
0x14016692d  jnz     short loc_14016694B
0x14016692f  mov     rcx, [rbp+5Fh]; this
0x140166933  lea     r8, aOnecoreuapInte_15; "onecoreuap\\internal\\shell\\inc\\Priva"...
0x14016693a  mov     edx, 101h; void *
0x14016693f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140166944  mov     ebx, eax
0x140166946  jmp     loc_140166A5F
0x14016694b  xor     ebx, ebx
0x14016694d  cmp     ebx, dword ptr [rbp+57h+pAclInformation]
0x140166950  jnb     short loc_140166997
0x140166952  mov     rcx, [rbp+57h+pAcl]; pAcl
0x140166956  lea     r8, [rbp+57h+pAce]; pAce
0x14016695a  mov     edx, ebx; dwAceIndex
0x14016695c  mov     [rbp+57h+pAce], 0
0x140166964  call    cs:__imp_GetAce
0x14016696b  nop     dword ptr [rax+rax+00h]
0x140166970  test    eax, eax
0x140166972  jz      short loc_140166993
0x140166974  mov     rcx, [rbp+57h+pAce]
0x140166978  mov     rdx, rdi; pSid2
0x14016697b  add     rcx, 8; pSid1
0x14016697f  call    cs:__imp_EqualSid
0x140166986  nop     dword ptr [rax+rax+00h]
0x14016698b  test    eax, eax
0x14016698d  jnz     loc_140166A5D
0x140166993  inc     ebx
0x140166995  jmp     short loc_14016694D
0x140166997  mov     r8, [rbp+57h+pAcl]; OldAcl
0x14016699b  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x14016699f  xorps   xmm0, xmm0
0x1401669a2  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 0
0x1401669aa  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1401669ae  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x1401669b5  mov     ecx, 1; cCountOfExplicitEntries
0x1401669ba  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x1401669c1  movdqu  xmmword ptr [rbp+57h+pListOfExplicitEntries+0Ch], xmm0
0x1401669c6  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 2
0x1401669cd  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], 0
0x1401669d4  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rdi
0x1401669d8  mov     [rbp+57h+NewAcl], 0
0x1401669e0  call    cs:__imp_SetEntriesInAclW
0x1401669e7  nop     dword ptr [rax+rax+00h]
0x1401669ec  test    eax, eax
0x1401669ee  jz      short loc_140166A15
0x1401669f0  mov     edx, 119h; void *
0x1401669f5  mov     rcx, [rbp+5Fh]; this
0x1401669f9  lea     r8, aOnecoreuapInte_15; "onecoreuap\\internal\\shell\\inc\\Priva"...
0x140166a00  mov     r9d, eax; char *
0x140166a03  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140166a08  lea     rcx, [rbp+57h+NewAcl]
0x140166a0c  mov     ebx, eax
0x140166a0e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x140166a13  jmp     short loc_140166A5F
0x140166a15  mov     rax, [rbp+57h+NewAcl]
0x140166a19  xor     r9d, r9d; psidOwner
0x140166a1c  mov     [rsp+0C0h+ppSacl], 0; pSacl
0x140166a25  mov     rcx, rsi; pObjectName
0x140166a28  mov     [rsp+0C0h+ppDacl], rax; pDacl
0x140166a2d  mov     [rsp+0C0h+ppsidGroup], 0; psidGroup
0x140166a36  lea     edx, [r9+4]; ObjectType
0x140166a3a  mov     r8d, edx; SecurityInfo
0x140166a3d  call    cs:__imp_SetNamedSecurityInfoW
0x140166a44  nop     dword ptr [rax+rax+00h]
0x140166a49  test    eax, eax
0x140166a4b  jz      short loc_140166A54
0x140166a4d  mov     edx, 11Ah
0x140166a52  jmp     short loc_1401669F5
0x140166a54  lea     rcx, [rbp+57h+NewAcl]
0x140166a58  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x140166a5d  xor     ebx, ebx
0x140166a5f  lea     rcx, [rbp+57h+var_70]
0x140166a63  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x140166a68  mov     eax, ebx
0x140166a6a  mov     rcx, [rbp+57h+var_20]
0x140166a6e  xor     rcx, rsp; StackCookie
0x140166a71  call    __security_check_cookie
0x140166a76  mov     rbx, [rsp+0C0h+arg_8]
0x140166a7e  add     rsp, 0B0h
0x140166a85  pop     rdi
0x140166a86  pop     rsi
0x140166a87  pop     rbp
0x140166a88  retn
```
