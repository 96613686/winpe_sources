# Rdp::Security::GrantProcessAccessPermissions(void *,ulong)

- ea: `0x18005a918`
- end: `0x18005aa85`
- name: `?GrantProcessAccessPermissions@Security@Rdp@@YAXPEAXK@Z`
- size: `365`
- prototype: `void __fastcall(Rdp::Security *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18005c350`

## callees

- `0x18000e82c`
- `0x18005a918`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005a940`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005a9d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005a940`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005a9d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005aa1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005aa2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005aa1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005aa2b`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18005a97c`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18005a97c`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18005aa08`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18005aa08`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005a9c7`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005a9c7`

## string_xrefs

- `0x18005aa46`: `onecoreuap\termsrv\rdp_bin\win\common/inc/RdpSecurity.h`
- `0x18005aa5b`: `onecoreuap\termsrv\rdp_bin\win\common/inc/RdpSecurity.h`
- `0x18005aa70`: `onecoreuap\termsrv\rdp_bin\win\common/inc/RdpSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Rdp::Security::GrantProcessAccessPermissions(WCHAR *this, void *a2)
{
  HANDLE CurrentProcess; // rax
  const char *v4; // r9
  const char *v5; // r9
  struct _ACL *v6; // rbx
  HANDLE v7; // rax
  const char *v8; // r9
  PSECURITY_DESCRIPTOR hMem; // [rsp+40h] [rbp-40h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+48h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]
  PACL NewAcl; // [rsp+A0h] [rbp+20h] BYREF
  PACL OldAcl; // [rsp+A8h] [rbp+28h] BYREF

  OldAcl = 0;
  hMem = 0;
  CurrentProcess = GetCurrentProcess();
  if ( GetSecurityInfo(CurrentProcess, SE_KERNEL_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RdpSecurity.h",
      v4);
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
  *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 1;
  pListOfExplicitEntries.grfAccessPermissions = -2147479488;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 1;
  pListOfExplicitEntries.Trustee.ptstrName = this;
  NewAcl = 0;
  if ( SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RdpSecurity.h",
      v5);
  v6 = NewAcl;
  v7 = GetCurrentProcess();
  if ( SetSecurityInfo(v7, SE_KERNEL_OBJECT, 4u, 0, 0, v6, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RdpSecurity.h",
      v8);
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( hMem )
    LocalFree(hMem);
}

```

## disassembly

```asm
0x18005a918  mov     [rsp-8+arg_0], rbx
0x18005a91d  mov     [rsp-8+arg_8], rdi
0x18005a922  push    rbp
0x18005a923  mov     rbp, rsp
0x18005a926  sub     rsp, 80h
0x18005a92d  mov     rdi, rcx
0x18005a930  mov     [rbp+OldAcl], 0
0x18005a938  mov     [rbp+hMem], 0
0x18005a940  call    cs:__imp_GetCurrentProcess
0x18005a946  mov     rbx, [rbp+8]
0x18005a94a  lea     rcx, [rbp+hMem]
0x18005a94e  mov     [rsp+80h+ppSecurityDescriptor], rcx; ppSecurityDescriptor
0x18005a953  mov     [rsp+80h+ppSacl], 0; ppSacl
0x18005a95c  lea     rcx, [rbp+OldAcl]
0x18005a960  mov     [rsp+80h+ppDacl], rcx; ppDacl
0x18005a965  mov     [rsp+80h+ppsidGroup], 0; ppsidGroup
0x18005a96e  xor     r9d, r9d; ppsidOwner
0x18005a971  lea     edx, [r9+6]; ObjectType
0x18005a975  lea     r8d, [r9+4]; SecurityInfo
0x18005a979  mov     rcx, rax; handle
0x18005a97c  call    cs:__imp_GetSecurityInfo
0x18005a982  test    eax, eax
0x18005a984  jnz     loc_18005AA5B
0x18005a98a  xorps   xmm0, xmm0
0x18005a98d  movdqu  xmmword ptr [rbp+pListOfExplicitEntries+0Ch], xmm0
0x18005a992  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], 1
0x18005a99a  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], 80001040h
0x18005a9a1  lea     ecx, [rax+1]; cCountOfExplicitEntries
0x18005a9a4  mov     qword ptr [rbp+pListOfExplicitEntries.grfAccessMode], rcx
0x18005a9a8  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeForm], eax
0x18005a9ab  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rdi
0x18005a9af  mov     [rbp+NewAcl], 0
0x18005a9b7  mov     rbx, [rbp+8]
0x18005a9bb  lea     r9, [rbp+NewAcl]; NewAcl
0x18005a9bf  mov     r8, [rbp+OldAcl]; OldAcl
0x18005a9c3  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18005a9c7  call    cs:__imp_SetEntriesInAclW
0x18005a9cd  test    eax, eax
0x18005a9cf  jnz     loc_18005AA70
0x18005a9d5  mov     rbx, [rbp+NewAcl]
0x18005a9d9  call    cs:__imp_GetCurrentProcess
0x18005a9df  mov     rdi, [rbp+8]
0x18005a9e3  mov     [rsp+80h+ppSacl], 0; pSacl
0x18005a9ec  mov     [rsp+80h+ppDacl], rbx; pDacl
0x18005a9f1  mov     [rsp+80h+ppsidGroup], 0; psidGroup
0x18005a9fa  xor     r9d, r9d; psidOwner
0x18005a9fd  lea     edx, [r9+6]; ObjectType
0x18005aa01  lea     r8d, [r9+4]; SecurityInfo
0x18005aa05  mov     rcx, rax; handle
0x18005aa08  call    cs:__imp_SetSecurityInfo
0x18005aa0e  test    eax, eax
0x18005aa10  jnz     short loc_18005AA46
0x18005aa12  mov     rcx, [rbp+NewAcl]; hMem
0x18005aa16  test    rcx, rcx
0x18005aa19  jz      short loc_18005AA22
0x18005aa1b  call    cs:__imp_LocalFree
0x18005aa21  nop
0x18005aa22  mov     rcx, [rbp+hMem]; hMem
0x18005aa26  test    rcx, rcx
0x18005aa29  jz      short loc_18005AA31
0x18005aa2b  call    cs:__imp_LocalFree
0x18005aa31  lea     r11, [rsp+80h+var_s0]
0x18005aa39  mov     rbx, [r11+10h]
0x18005aa3d  mov     rdi, [r11+18h]
0x18005aa41  mov     rsp, r11
0x18005aa44  pop     rbp
0x18005aa45  retn
0x18005aa46  lea     r8, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18005aa4d  mov     edx, 12Ch; void *
0x18005aa52  mov     rcx, rdi; this
0x18005aa55  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005aa5b  lea     r8, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18005aa62  mov     edx, 10Fh; void *
0x18005aa67  mov     rcx, rbx; this
0x18005aa6a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005aa70  lea     r8, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18005aa77  mov     edx, 11Eh; void *
0x18005aa7c  mov     rcx, rbx; this
0x18005aa7f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
