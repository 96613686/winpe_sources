# Pku2uInitGlobalVariables(void)

- ea: `0x180031a6c`
- end: `0x180031b68`
- name: `?Pku2uInitGlobalVariables@@YAJXZ`
- size: `252`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1800238f0`

## callees

- `0x1800210f0`
- `0x180031a6c`

## import_xrefs

- `ntdll!NtAllocateLocallyUniqueId` at `0x180031aa6`
- `ntdll!NtAllocateLocallyUniqueId` at `0x180031aa6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180031ae7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180031b31`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180031ae7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180031b31`

## pseudocode

```c
NTSTATUS Pku2uInitGlobalVariables(void)
{
  NTSTATUS result; // eax
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+60h] [rbp-18h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_QWORD *)Pku2uGlobalSource.SourceName = 0x7073537532756B50LL;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  NtAllocateLocallyUniqueId(&LocallyUniqueId);
  if ( Pku2uGlobalLocalSystemSid
    || (result = RtlAllocateAndInitializeSid(
                   &IdentifierAuthority,
                   1u,
                   0x12u,
                   0,
                   0,
                   0,
                   0,
                   0,
                   0,
                   0,
                   &Pku2uGlobalLocalSystemSid),
        result >= 0) )
  {
    if ( Pku2uGlobalAliasAdminsSid
      || (result = RtlAllocateAndInitializeSid(
                     &IdentifierAuthority,
                     2u,
                     0x20u,
                     0x220u,
                     0,
                     0,
                     0,
                     0,
                     0,
                     0,
                     &Pku2uGlobalAliasAdminsSid),
          result >= 0) )
    {
      Pku2uGlobalHasNeverTime.QuadPart = 0;
      Pku2uGlobalWillNeverTime.QuadPart = 0x7FFFFF36D5969FFFLL;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180031a6c  push    rbx
0x180031a6e  sub     rsp, 70h
0x180031a72  mov     rax, cs:__security_cookie
0x180031a79  xor     rax, rsp
0x180031a7c  mov     [rsp+78h+var_10], rax
0x180031a81  mov     rax, 7073537532756B50h
0x180031a8b  mov     word ptr [rsp+78h+IdentifierAuthority.Value+4], 500h
0x180031a92  xor     ebx, ebx
0x180031a94  mov     cs:?Pku2uGlobalSource@@3U_TOKEN_SOURCE@@A, rax; _TOKEN_SOURCE Pku2uGlobalSource
0x180031a9b  lea     rcx, LocallyUniqueId; LocallyUniqueId
0x180031aa2  mov     dword ptr [rsp+78h+IdentifierAuthority.Value], ebx
0x180031aa6  call    cs:__imp_NtAllocateLocallyUniqueId
0x180031aac  cmp     cs:?Pku2uGlobalLocalSystemSid@@3PEAXEA, rbx; void * Pku2uGlobalLocalSystemSid
0x180031ab3  jnz     short loc_180031AF1
0x180031ab5  lea     rax, ?Pku2uGlobalLocalSystemSid@@3PEAXEA; void * Pku2uGlobalLocalSystemSid
0x180031abc  xor     r9d, r9d; SubAuthority1
0x180031abf  mov     [rsp+78h+Sid], rax; Sid
0x180031ac4  lea     r8d, [rbx+12h]; SubAuthority0
0x180031ac8  mov     [rsp+78h+SubAuthority7], ebx; SubAuthority7
0x180031acc  lea     rcx, [rsp+78h+IdentifierAuthority]; IdentifierAuthority
0x180031ad1  mov     [rsp+78h+SubAuthority6], ebx; SubAuthority6
0x180031ad5  mov     dl, 1; SubAuthorityCount
0x180031ad7  mov     [rsp+78h+SubAuthority5], ebx; SubAuthority5
0x180031adb  mov     [rsp+78h+SubAuthority4], ebx; SubAuthority4
0x180031adf  mov     [rsp+78h+SubAuthority3], ebx; SubAuthority3
0x180031ae3  mov     [rsp+78h+SubAuthority2], ebx; SubAuthority2
0x180031ae7  call    cs:__imp_RtlAllocateAndInitializeSid
0x180031aed  test    eax, eax
0x180031aef  js      short loc_180031B55
0x180031af1  cmp     cs:?Pku2uGlobalAliasAdminsSid@@3PEAXEA, rbx; void * Pku2uGlobalAliasAdminsSid
0x180031af8  jnz     short loc_180031B3B
0x180031afa  lea     rax, ?Pku2uGlobalAliasAdminsSid@@3PEAXEA; void * Pku2uGlobalAliasAdminsSid
0x180031b01  mov     r9d, 220h; SubAuthority1
0x180031b07  mov     [rsp+78h+Sid], rax; Sid
0x180031b0c  lea     rcx, [rsp+78h+IdentifierAuthority]; IdentifierAuthority
0x180031b11  mov     [rsp+78h+SubAuthority7], ebx; SubAuthority7
0x180031b15  mov     r8d, 20h ; ' '; SubAuthority0
0x180031b1b  mov     [rsp+78h+SubAuthority6], ebx; SubAuthority6
0x180031b1f  mov     dl, 2; SubAuthorityCount
0x180031b21  mov     [rsp+78h+SubAuthority5], ebx; SubAuthority5
0x180031b25  mov     [rsp+78h+SubAuthority4], ebx; SubAuthority4
0x180031b29  mov     [rsp+78h+SubAuthority3], ebx; SubAuthority3
0x180031b2d  mov     [rsp+78h+SubAuthority2], ebx; SubAuthority2
0x180031b31  call    cs:__imp_RtlAllocateAndInitializeSid
0x180031b37  test    eax, eax
0x180031b39  js      short loc_180031B55
0x180031b3b  mov     rax, 7FFFFF36D5969FFFh
0x180031b45  mov     cs:?Pku2uGlobalHasNeverTime@@3T_LARGE_INTEGER@@A, rbx; _LARGE_INTEGER Pku2uGlobalHasNeverTime
0x180031b4c  mov     qword ptr cs:?Pku2uGlobalWillNeverTime@@3T_LARGE_INTEGER@@A, rax; _LARGE_INTEGER Pku2uGlobalWillNeverTime ...
0x180031b53  mov     eax, ebx
0x180031b55  mov     rcx, [rsp+78h+var_10]
0x180031b5a  xor     rcx, rsp; StackCookie
0x180031b5d  call    __security_check_cookie
0x180031b62  add     rsp, 70h
0x180031b66  pop     rbx
0x180031b67  retn
```
