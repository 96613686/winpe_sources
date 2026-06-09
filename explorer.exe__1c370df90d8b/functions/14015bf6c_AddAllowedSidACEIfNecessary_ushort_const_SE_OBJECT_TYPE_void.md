# AddAllowedSidACEIfNecessary(ushort const *,_SE_OBJECT_TYPE,void *)

- ea: `0x14015bf6c`
- end: `0x14015c169`
- name: `?AddAllowedSidACEIfNecessary@@YAJPEBGW4_SE_OBJECT_TYPE@@PEAX@Z`
- size: `509`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, enum _SE_OBJECT_TYPE, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1401882c0`

## callees

- `0x140011a10`
- `0x14008ac34`
- `0x1400936ec`
- `0x1400987b8`
- `0x1401040e0`
- `0x14015bf6c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14015c01d`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14015c01d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14015c05c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14015c05c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14015c071`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14015c071`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x14015bfe0`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x14015bfe0`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x14015c0cc`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x14015c0cc`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x14015c123`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x14015c123`

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
0x14015bf6c  mov     [rsp-8+arg_8], rbx
0x14015bf71  push    rbp
0x14015bf72  push    rsi
0x14015bf73  push    rdi
0x14015bf74  lea     rbp, [rsp-47h]
0x14015bf79  sub     rsp, 0B0h
0x14015bf80  mov     rax, cs:__security_cookie
0x14015bf87  xor     rax, rsp
0x14015bf8a  mov     [rbp+57h+var_20], rax
0x14015bf8e  mov     rsi, rcx
0x14015bf91  mov     [rbp+57h+pAcl], 0
0x14015bf99  lea     rcx, [rbp+57h+var_70]
0x14015bf9d  mov     [rbp+57h+var_70], 0
0x14015bfa5  xor     edx, edx
0x14015bfa7  mov     rdi, r8
0x14015bfaa  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14015bfaf  xor     r9d, r9d; ppsidOwner
0x14015bfb2  lea     rax, [rbp+57h+var_70]
0x14015bfb6  mov     [rsp+0C0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x14015bfbb  mov     rcx, rsi; pObjectName
0x14015bfbe  lea     rax, [rbp+57h+pAcl]
0x14015bfc2  mov     [rsp+0C0h+ppSacl], 0; ppSacl
0x14015bfcb  mov     [rsp+0C0h+ppDacl], rax; ppDacl
0x14015bfd0  lea     edx, [r9+4]; ObjectType
0x14015bfd4  mov     [rsp+0C0h+ppsidGroup], 0; unsigned int
0x14015bfdd  mov     r8d, edx; SecurityInfo
0x14015bfe0  call    cs:__imp_GetNamedSecurityInfoW
0x14015bfe6  test    eax, eax
0x14015bfe8  jz      short loc_14015C004
0x14015bfea  mov     rcx, [rbp+5Fh]; this
0x14015bfee  lea     r8, aOnecoreuapInte_15; "onecoreuap\\internal\\shell\\inc\\Priva"...
0x14015bff5  mov     r9d, eax; char *
0x14015bff8  mov     edx, 0FEh; void *
0x14015bffd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14015c002  jmp     short loc_14015C03C
0x14015c004  mov     rcx, [rbp+57h+pAcl]; pAcl
0x14015c008  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x14015c00c  xor     eax, eax
0x14015c00e  mov     [rbp+57h+pAclInformation], rax
0x14015c012  mov     [rbp+57h+var_28], eax
0x14015c015  lea     r9d, [rax+2]; dwAclInformationClass
0x14015c019  lea     r8d, [rax+0Ch]; nAclInformationLength
0x14015c01d  call    cs:__imp_GetAclInformation
0x14015c023  test    eax, eax
0x14015c025  jnz     short loc_14015C043
0x14015c027  mov     rcx, [rbp+5Fh]; this
0x14015c02b  lea     r8, aOnecoreuapInte_15; "onecoreuap\\internal\\shell\\inc\\Priva"...
0x14015c032  mov     edx, 101h; void *
0x14015c037  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14015c03c  mov     ebx, eax
0x14015c03e  jmp     loc_14015C13F
0x14015c043  xor     ebx, ebx
0x14015c045  cmp     ebx, dword ptr [rbp+57h+pAclInformation]
0x14015c048  jnb     short loc_14015C083
0x14015c04a  mov     rcx, [rbp+57h+pAcl]; pAcl
0x14015c04e  lea     r8, [rbp+57h+pAce]; pAce
0x14015c052  mov     edx, ebx; dwAceIndex
0x14015c054  mov     [rbp+57h+pAce], 0
0x14015c05c  call    cs:__imp_GetAce
0x14015c062  test    eax, eax
0x14015c064  jz      short loc_14015C07F
0x14015c066  mov     rcx, [rbp+57h+pAce]
0x14015c06a  mov     rdx, rdi; pSid2
0x14015c06d  add     rcx, 8; pSid1
0x14015c071  call    cs:__imp_EqualSid
0x14015c077  test    eax, eax
0x14015c079  jnz     loc_14015C13D
0x14015c07f  inc     ebx
0x14015c081  jmp     short loc_14015C045
0x14015c083  mov     r8, [rbp+57h+pAcl]; OldAcl
0x14015c087  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x14015c08b  xorps   xmm0, xmm0
0x14015c08e  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 0
0x14015c096  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x14015c09a  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x14015c0a1  mov     ecx, 1; cCountOfExplicitEntries
0x14015c0a6  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x14015c0ad  movdqu  xmmword ptr [rbp+57h+pListOfExplicitEntries+0Ch], xmm0
0x14015c0b2  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 2
0x14015c0b9  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], 0
0x14015c0c0  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rdi
0x14015c0c4  mov     [rbp+57h+NewAcl], 0
0x14015c0cc  call    cs:__imp_SetEntriesInAclW
0x14015c0d2  test    eax, eax
0x14015c0d4  jz      short loc_14015C0FB
0x14015c0d6  mov     edx, 119h; void *
0x14015c0db  mov     rcx, [rbp+5Fh]; this
0x14015c0df  lea     r8, aOnecoreuapInte_15; "onecoreuap\\internal\\shell\\inc\\Priva"...
0x14015c0e6  mov     r9d, eax; char *
0x14015c0e9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14015c0ee  lea     rcx, [rbp+57h+NewAcl]
0x14015c0f2  mov     ebx, eax
0x14015c0f4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14015c0f9  jmp     short loc_14015C13F
0x14015c0fb  mov     rax, [rbp+57h+NewAcl]
0x14015c0ff  xor     r9d, r9d; psidOwner
0x14015c102  mov     [rsp+0C0h+ppSacl], 0; pSacl
0x14015c10b  mov     rcx, rsi; pObjectName
0x14015c10e  mov     [rsp+0C0h+ppDacl], rax; pDacl
0x14015c113  mov     [rsp+0C0h+ppsidGroup], 0; psidGroup
0x14015c11c  lea     edx, [r9+4]; ObjectType
0x14015c120  mov     r8d, edx; SecurityInfo
0x14015c123  call    cs:__imp_SetNamedSecurityInfoW
0x14015c129  test    eax, eax
0x14015c12b  jz      short loc_14015C134
0x14015c12d  mov     edx, 11Ah
0x14015c132  jmp     short loc_14015C0DB
0x14015c134  lea     rcx, [rbp+57h+NewAcl]
0x14015c138  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14015c13d  xor     ebx, ebx
0x14015c13f  lea     rcx, [rbp+57h+var_70]
0x14015c143  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14015c148  mov     eax, ebx
0x14015c14a  mov     rcx, [rbp+57h+var_20]
0x14015c14e  xor     rcx, rsp; StackCookie
0x14015c151  call    __security_check_cookie
0x14015c156  mov     rbx, [rsp+0C0h+arg_8]
0x14015c15e  add     rsp, 0B0h
0x14015c165  pop     rdi
0x14015c166  pop     rsi
0x14015c167  pop     rbp
0x14015c168  retn
```
