# Rdp::Security::details::InitializeSecurityAttrFromSid(void *)

- ea: `0x180018b30`
- end: `0x180018d3d`
- name: `?InitializeSecurityAttrFromSid@details@Security@Rdp@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SECURITY_ATTRIBUTES@@P6AXPEAU1@@Z$1?DestroySecurityAttributes@details@Security@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@Z`
- size: `525`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180018aec`
- `0x180018d44`
- `0x18003f990`

## callees

- `0x18000e82c`
- `0x18001733c`
- `0x180018b30`
- `0x180019998`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018bae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018c20`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018c68`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018bae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018c20`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018c68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018cb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018cc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018cb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018cc7`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180018be7`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180018be7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180018c02`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180018c02`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180018c13`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180018c13`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180018c57`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180018c57`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180018b98`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180018b98`

## string_xrefs

- `0x180018bbf`: `Failed to allocate security descriptor`
- `0x180018d0f`: `InitializeSecurityDescriptor`
- `0x180018d28`: `SetSecurityDescriptorDacl`
- `0x180018ce1`: `Failed to create self-relative SD`
- `0x180018c79`: `Failed to allocate memory for security attributes`
- `0x180018bcf`: `onecoreuap\termsrv\rdp_bin\win\common/inc/RdpSecurity.h`
- `0x180018cf6`: `onecoreuap\termsrv\rdp_bin\win\common/inc/RdpSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Rdp::Security::details::InitializeSecurityAttrFromSid(__int64 a1, WCHAR *a2)
{
  const char *v3; // r9
  HLOCAL v4; // rbx
  HLOCAL v5; // rdi
  char *v7; // [rsp+20h] [rbp-58h]
  char *v8; // [rsp+20h] [rbp-58h]
  HLOCAL v9; // [rsp+38h] [rbp-40h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]
  DWORD dwBufferLength; // [rsp+B8h] [rbp+40h] BYREF
  PACL NewAcl; // [rsp+C0h] [rbp+48h] BYREF
  HLOCAL v14; // [rsp+C8h] [rbp+50h] BYREF

  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
  *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 1;
  pListOfExplicitEntries.grfAccessPermissions = -1073741824;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  pListOfExplicitEntries.Trustee.ptstrName = a2;
  NewAcl = 0;
  if ( SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RdpSecurity.h",
      v3);
  v4 = LocalAlloc(0x40u, 0x28u);
  v14 = v4;
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(
    (_DWORD)retaddr,
    94,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RdpSecurity.h",
    (unsigned int)&v14,
    (void *)"Failed to allocate security descriptor");
  if ( !InitializeSecurityDescriptor(v4, 1u) )
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RdpSecurity.h",
      "InitializeSecurityDescriptor",
      v7);
  if ( !SetSecurityDescriptorDacl(v4, 1, NewAcl, 0) )
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x70,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RdpSecurity.h",
      "SetSecurityDescriptorDacl",
      v7);
  dwBufferLength = GetSecurityDescriptorLength(v4);
  v5 = LocalAlloc(0x40u, dwBufferLength);
  v9 = v5;
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(
    (_DWORD)retaddr,
    121,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RdpSecurity.h",
    (unsigned int)&v9,
    (void *)"Failed to allocate memory for self-relative SD");
  if ( !MakeSelfRelativeSD(v4, v5, &dwBufferLength) )
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RdpSecurity.h",
      "Failed to create self-relative SD",
      v8);
  *(_QWORD *)a1 = LocalAlloc(0x40u, 0x18u);
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(
    (_DWORD)retaddr,
    132,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RdpSecurity.h",
    a1,
    "Failed to allocate memory for security attributes");
  **(_DWORD **)a1 = 24;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = v5;
  *(_DWORD *)(*(_QWORD *)a1 + 16LL) = 0;
  if ( v4 )
    LocalFree(v4);
  if ( NewAcl )
    LocalFree(NewAcl);
  return a1;
}

```

## disassembly

```asm
0x180018b30  mov     [rsp-30h+arg_0], rcx
0x180018b35  push    rbp
0x180018b36  push    rbx
0x180018b37  push    rsi
0x180018b38  push    rdi
0x180018b39  push    r13
0x180018b3b  push    r14
0x180018b3d  mov     rbp, rsp
0x180018b40  sub     rsp, 78h
0x180018b44  mov     r14, rcx
0x180018b47  mov     [rbp+var_48], 0
0x180018b4e  xorps   xmm0, xmm0
0x180018b51  movdqu  xmmword ptr [rbp+pListOfExplicitEntries+0Ch], xmm0
0x180018b56  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], 1
0x180018b5e  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], 0C0000000h
0x180018b65  mov     qword ptr [rbp+pListOfExplicitEntries.grfAccessMode], 2
0x180018b6d  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeForm], 0
0x180018b74  mov     r13d, 1
0x180018b7a  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rdx
0x180018b7e  mov     [rbp+NewAcl], 0
0x180018b86  mov     rbx, [rbp+30h]
0x180018b8a  lea     r9, [rbp+NewAcl]; NewAcl
0x180018b8e  xor     r8d, r8d; OldAcl
0x180018b91  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x180018b95  mov     ecx, r13d; cCountOfExplicitEntries
0x180018b98  call    cs:__imp_SetEntriesInAclW
0x180018b9e  test    eax, eax
0x180018ba0  jnz     loc_180018CF6
0x180018ba6  lea     edx, [rax+28h]; uBytes
0x180018ba9  lea     edi, [rax+40h]
0x180018bac  mov     ecx, edi; uFlags
0x180018bae  call    cs:__imp_LocalAlloc
0x180018bb4  mov     rbx, rax
0x180018bb7  mov     [rbp+arg_18], rax
0x180018bbb  mov     rcx, [rbp+30h]
0x180018bbf  lea     rax, aFailedToAlloca_1; "Failed to allocate security descriptor"
0x180018bc6  mov     [rsp+78h+var_58], rax; char *
0x180018bcb  lea     r9, [rbp+arg_18]
0x180018bcf  lea     rsi, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180018bd6  mov     r8, rsi
0x180018bd9  lea     edx, [rdi+1Eh]
0x180018bdc  call    ??$Throw_GetLastErrorIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> const &,char const *,...)
0x180018be1  mov     edx, r13d; dwRevision
0x180018be4  mov     rcx, rbx; pSecurityDescriptor
0x180018be7  call    cs:__imp_InitializeSecurityDescriptor
0x180018bed  test    eax, eax
0x180018bef  jz      loc_180018D0B
0x180018bf5  xor     r9d, r9d; bDaclDefaulted
0x180018bf8  mov     r8, [rbp+NewAcl]; pDacl
0x180018bfc  mov     edx, r13d; bDaclPresent
0x180018bff  mov     rcx, rbx; pSecurityDescriptor
0x180018c02  call    cs:__imp_SetSecurityDescriptorDacl
0x180018c08  test    eax, eax
0x180018c0a  jz      loc_180018D24
0x180018c10  mov     rcx, rbx; pSecurityDescriptor
0x180018c13  call    cs:__imp_GetSecurityDescriptorLength
0x180018c19  mov     edx, eax; uBytes
0x180018c1b  mov     [rbp+dwBufferLength], edx
0x180018c1e  mov     ecx, edi; uFlags
0x180018c20  call    cs:__imp_LocalAlloc
0x180018c26  mov     rdi, rax
0x180018c29  mov     [rbp+var_40], rax
0x180018c2d  mov     rcx, [rbp+30h]
0x180018c31  lea     rax, aFailedToAlloca; "Failed to allocate memory for self-rela"...
0x180018c38  mov     [rsp+78h+var_58], rax; char *
0x180018c3d  lea     r9, [rbp+var_40]
0x180018c41  mov     r8, rsi
0x180018c44  lea     edx, [r13+78h]
0x180018c48  call    ??$Throw_GetLastErrorIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> const &,char const *,...)
0x180018c4d  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x180018c51  mov     rdx, rdi; pSelfRelativeSecurityDescriptor
0x180018c54  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x180018c57  call    cs:__imp_MakeSelfRelativeSD
0x180018c5d  test    eax, eax
0x180018c5f  jz      short loc_180018CDD
0x180018c61  lea     edx, [r13+17h]; uBytes
0x180018c65  lea     ecx, [rdx+28h]; uFlags
0x180018c68  call    cs:__imp_LocalAlloc
0x180018c6e  mov     [r14], rax
0x180018c71  mov     [rbp+var_48], r13d
0x180018c75  mov     rcx, [rbp+30h]
0x180018c79  lea     rax, aFailedToAlloca_3; "Failed to allocate memory for security "...
0x180018c80  mov     [rsp+78h+var_58], rax
0x180018c85  mov     r9, r14
0x180018c88  mov     r8, rsi
0x180018c8b  mov     edx, 84h
0x180018c90  call    ??$Throw_GetLastErrorIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> const &,char const *,...)
0x180018c95  mov     rax, [r14]
0x180018c98  mov     dword ptr [rax], 18h
0x180018c9e  mov     rax, [r14]
0x180018ca1  mov     [rax+8], rdi
0x180018ca5  mov     rax, [r14]
0x180018ca8  mov     dword ptr [rax+10h], 0
0x180018caf  test    rbx, rbx
0x180018cb2  jz      short loc_180018CBE
0x180018cb4  mov     rcx, rbx; hMem
0x180018cb7  call    cs:__imp_LocalFree
0x180018cbd  nop
0x180018cbe  mov     rcx, [rbp+NewAcl]; hMem
0x180018cc2  test    rcx, rcx
0x180018cc5  jz      short loc_180018CCD
0x180018cc7  call    cs:__imp_LocalFree
0x180018ccd  mov     rax, r14
0x180018cd0  add     rsp, 78h
0x180018cd4  pop     r14
0x180018cd6  pop     r13
0x180018cd8  pop     rdi
0x180018cd9  pop     rsi
0x180018cda  pop     rbx
0x180018cdb  pop     rbp
0x180018cdc  retn
0x180018cdd  mov     rcx, [rbp+30h]; this
0x180018ce1  lea     r9, aFailedToCreate_9; "Failed to create self-relative SD"
0x180018ce8  mov     r8, rsi; unsigned int
0x180018ceb  mov     edx, 7Dh ; '}'; void *
0x180018cf0  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180018cf6  lea     r8, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180018cfd  mov     edx, 57h ; 'W'; void *
0x180018d02  mov     rcx, rbx; this
0x180018d05  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180018d0b  mov     rcx, [rbp+30h]; this
0x180018d0f  lea     r9, aInitializesecu; "InitializeSecurityDescriptor"
0x180018d16  mov     r8, rsi; unsigned int
0x180018d19  mov     edx, 64h ; 'd'; void *
0x180018d1e  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180018d24  mov     rcx, [rbp+30h]; this
0x180018d28  lea     r9, aSetsecuritydes; "SetSecurityDescriptorDacl"
0x180018d2f  mov     r8, rsi; unsigned int
0x180018d32  mov     edx, 70h ; 'p'; void *
0x180018d37  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
