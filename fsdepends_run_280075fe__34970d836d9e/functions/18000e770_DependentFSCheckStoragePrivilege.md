# DependentFSCheckStoragePrivilege

- ea: `0x18000e770`
- end: `0x18000e83e`
- name: `DependentFSCheckStoragePrivilege`
- size: `206`
- prototype: `__int64 __fastcall(PSECURITY_SUBJECT_CONTEXT SubjectSecurityContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001f70`
- `0x18000e770`

## import_xrefs

- `ntoskrnl!SePrivilegeCheck` at `0x18000e80d`
- `ntoskrnl!SePrivilegeCheck` at `0x18000e80d`
- `ntoskrnl!RtlIsSandboxedToken` at `0x18000e7b1`
- `ntoskrnl!RtlIsSandboxedToken` at `0x18000e7b1`

## pseudocode

```c
__int64 __fastcall DependentFSCheckStoragePrivilege(
        PSECURITY_SUBJECT_CONTEXT SubjectSecurityContext,
        _DWORD *a2,
        int a3)
{
  _DWORD *v3; // rdi
  unsigned int v5; // edi
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+20h] [rbp-28h] BYREF

  v3 = a2;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  if ( (a3 & 0x70000) == 0 )
    return 0;
  LOBYTE(a2) = 1;
  if ( (unsigned __int8)RtlIsSandboxedToken(SubjectSecurityContext, a2) == 1 )
    return (unsigned int)-1073741790;
  if ( byte_18000519B && *v3 == 1 )
    return 0;
  v5 = -1073741727;
  if ( SubjectSecurityContext )
  {
    RequiredPrivileges.PrivilegeCount = 1;
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.Privilege[0].Luid = (LUID)28LL;
    RequiredPrivileges.Privilege[0].Attributes = 0;
    if ( SePrivilegeCheck(&RequiredPrivileges, SubjectSecurityContext, 1) )
      return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18000e770  mov     [rsp+arg_8], rbx
0x18000e775  mov     [rsp+arg_10], rsi
0x18000e77a  push    rdi
0x18000e77b  sub     rsp, 40h
0x18000e77f  mov     rax, cs:__security_cookie
0x18000e786  xor     rax, rsp
0x18000e789  mov     [rsp+48h+var_10], rax
0x18000e78e  xor     eax, eax
0x18000e790  xorps   xmm0, xmm0
0x18000e793  mov     [rsp+48h+RequiredPrivileges.Privilege.Attributes], eax
0x18000e797  mov     rdi, rdx
0x18000e79a  mov     rsi, rcx
0x18000e79d  movups  xmmword ptr [rsp+48h+RequiredPrivileges.PrivilegeCount], xmm0
0x18000e7a2  test    r8d, 70000h
0x18000e7a9  jnz     short loc_18000E7AF
0x18000e7ab  xor     ebx, ebx
0x18000e7ad  jmp     short loc_18000E7D7
0x18000e7af  mov     dl, 1
0x18000e7b1  call    cs:__imp_RtlIsSandboxedToken
0x18000e7b8  nop     dword ptr [rax+rax+00h]
0x18000e7bd  cmp     al, 1
0x18000e7bf  jnz     short loc_18000E7C8
0x18000e7c1  mov     edi, 0C0000022h
0x18000e7c6  jmp     short loc_18000E81E
0x18000e7c8  xor     ebx, ebx
0x18000e7ca  cmp     cs:byte_18000519B, bl
0x18000e7d0  jz      short loc_18000E7DB
0x18000e7d2  cmp     dword ptr [rdi], 1
0x18000e7d5  jnz     short loc_18000E7DB
0x18000e7d7  mov     edi, ebx
0x18000e7d9  jmp     short loc_18000E81E
0x18000e7db  mov     edi, 0C0000061h
0x18000e7e0  test    rsi, rsi
0x18000e7e3  jz      short loc_18000E81E
0x18000e7e5  mov     r8b, 1; AccessMode
0x18000e7e8  mov     [rsp+48h+RequiredPrivileges.PrivilegeCount], 1
0x18000e7f0  mov     rdx, rsi; SubjectSecurityContext
0x18000e7f3  mov     [rsp+48h+RequiredPrivileges.Control], 1
0x18000e7fb  lea     rcx, [rsp+48h+RequiredPrivileges]; RequiredPrivileges
0x18000e800  mov     qword ptr [rsp+48h+RequiredPrivileges.Privilege.Luid.LowPart], 1Ch
0x18000e809  mov     [rsp+48h+RequiredPrivileges.Privilege.Attributes], ebx
0x18000e80d  call    cs:__imp_SePrivilegeCheck
0x18000e814  nop     dword ptr [rax+rax+00h]
0x18000e819  test    al, al
0x18000e81b  cmovnz  edi, ebx
0x18000e81e  mov     eax, edi
0x18000e820  mov     rcx, [rsp+48h+var_10]
0x18000e825  xor     rcx, rsp; StackCookie
0x18000e828  call    __security_check_cookie
0x18000e82d  mov     rbx, [rsp+48h+arg_8]
0x18000e832  mov     rsi, [rsp+48h+arg_10]
0x18000e837  add     rsp, 40h
0x18000e83b  pop     rdi
0x18000e83c  retn
```
