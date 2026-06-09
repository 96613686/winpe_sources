# LuafvCreateTrustedInstallerSid

- ea: `0x140016d44`
- end: `0x140016e6f`
- name: `LuafvCreateTrustedInstallerSid`
- size: `299`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14002965c`

## callees

- `0x140005bb0`
- `0x140016d44`
- `0x14001b650`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x140016d74`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140016d74`
- `ntoskrnl!RtlInitializeSid` at `0x140016dac`
- `ntoskrnl!RtlInitializeSid` at `0x140016dac`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016dbd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016dd7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016df1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e0b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e25`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e3f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016dbd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016dd7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016df1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e0b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e25`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e3f`

## pseudocode

```c
__int64 __fastcall LuafvCreateTrustedInstallerSid(_QWORD *a1)
{
  ULONG v2; // eax
  __int64 v3; // r8
  void *Pool; // rax
  void *v5; // rbx
  __int64 result; // rax
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-18h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v2 = RtlLengthRequiredSid(6u);
  LOBYTE(v3) = 13;
  Pool = (void *)LuafvAllocatePool(1, v2, v3);
  v5 = Pool;
  if ( !Pool )
    return 3221225626LL;
  RtlInitializeSid(Pool, &IdentifierAuthority, 6u);
  *RtlSubAuthoritySid(v5, 0) = 80;
  *RtlSubAuthoritySid(v5, 1u) = 956008885;
  *RtlSubAuthoritySid(v5, 2u) = -876444647;
  *RtlSubAuthoritySid(v5, 3u) = 1831038044;
  *RtlSubAuthoritySid(v5, 4u) = 1853292631;
  *RtlSubAuthoritySid(v5, 5u) = -2023488832;
  result = 0;
  *a1 = v5;
  return result;
}

```

## disassembly

```asm
0x140016d44  mov     [rsp+arg_8], rbx
0x140016d49  push    rdi
0x140016d4a  sub     rsp, 30h
0x140016d4e  mov     rax, cs:__security_cookie
0x140016d55  xor     rax, rsp
0x140016d58  mov     [rsp+38h+var_10], rax
0x140016d5d  mov     rdi, rcx
0x140016d60  mov     dword ptr [rsp+38h+IdentifierAuthority.Value], 0
0x140016d68  mov     ecx, 6; SubAuthorityCount
0x140016d6d  mov     word ptr [rsp+38h+IdentifierAuthority.Value+4], 500h
0x140016d74  call    cs:__imp_RtlLengthRequiredSid
0x140016d7b  nop     dword ptr [rax+rax+00h]
0x140016d80  mov     r8b, 0Dh
0x140016d83  mov     ecx, 1
0x140016d88  mov     edx, eax
0x140016d8a  call    LuafvAllocatePool
0x140016d8f  mov     rbx, rax
0x140016d92  test    rax, rax
0x140016d95  jnz     short loc_140016DA1
0x140016d97  mov     eax, 0C000009Ah
0x140016d9c  jmp     loc_140016E56
0x140016da1  mov     r8b, 6; SubAuthorityCount
0x140016da4  lea     rdx, [rsp+38h+IdentifierAuthority]; IdentifierAuthority
0x140016da9  mov     rcx, rbx; Sid
0x140016dac  call    cs:__imp_RtlInitializeSid
0x140016db3  nop     dword ptr [rax+rax+00h]
0x140016db8  xor     edx, edx; SubAuthority
0x140016dba  mov     rcx, rbx; Sid
0x140016dbd  call    cs:__imp_RtlSubAuthoritySid
0x140016dc4  nop     dword ptr [rax+rax+00h]
0x140016dc9  mov     edx, 1; SubAuthority
0x140016dce  mov     rcx, rbx; Sid
0x140016dd1  mov     dword ptr [rax], 50h ; 'P'
0x140016dd7  call    cs:__imp_RtlSubAuthoritySid
0x140016dde  nop     dword ptr [rax+rax+00h]
0x140016de3  mov     edx, 2; SubAuthority
0x140016de8  mov     rcx, rbx; Sid
0x140016deb  mov     dword ptr [rax], 38FB89B5h
0x140016df1  call    cs:__imp_RtlSubAuthoritySid
0x140016df8  nop     dword ptr [rax+rax+00h]
0x140016dfd  mov     edx, 3; SubAuthority
0x140016e02  mov     rcx, rbx; Sid
0x140016e05  mov     dword ptr [rax], 0CBC28419h
0x140016e0b  call    cs:__imp_RtlSubAuthoritySid
0x140016e12  nop     dword ptr [rax+rax+00h]
0x140016e17  mov     edx, 4; SubAuthority
0x140016e1c  mov     rcx, rbx; Sid
0x140016e1f  mov     dword ptr [rax], 6D236C5Ch
0x140016e25  call    cs:__imp_RtlSubAuthoritySid
0x140016e2c  nop     dword ptr [rax+rax+00h]
0x140016e31  mov     edx, 5; SubAuthority
0x140016e36  mov     rcx, rbx; Sid
0x140016e39  mov     dword ptr [rax], 6E770057h
0x140016e3f  call    cs:__imp_RtlSubAuthoritySid
0x140016e46  nop     dword ptr [rax+rax+00h]
0x140016e4b  mov     dword ptr [rax], 876402C0h
0x140016e51  xor     eax, eax
0x140016e53  mov     [rdi], rbx
0x140016e56  mov     rcx, [rsp+38h+var_10]
0x140016e5b  xor     rcx, rsp; StackCookie
0x140016e5e  call    __security_check_cookie
0x140016e63  mov     rbx, [rsp+38h+arg_8]
0x140016e68  add     rsp, 30h
0x140016e6c  pop     rdi
0x140016e6d  retn
```
