# LuafvCreateTrustedInstallerSid

- ea: `0x140016d94`
- end: `0x140016ebf`
- name: `LuafvCreateTrustedInstallerSid`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14002965c`

## callees

- `0x140005f30`
- `0x140016d94`
- `0x14001b6a0`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x140016dc4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140016dc4`
- `ntoskrnl!RtlInitializeSid` at `0x140016dfc`
- `ntoskrnl!RtlInitializeSid` at `0x140016dfc`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e0d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e27`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e41`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e5b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e75`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e8f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e0d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e27`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e41`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e5b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e75`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140016e8f`

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
0x140016d94  mov     [rsp+arg_8], rbx
0x140016d99  push    rdi
0x140016d9a  sub     rsp, 30h
0x140016d9e  mov     rax, cs:__security_cookie
0x140016da5  xor     rax, rsp
0x140016da8  mov     [rsp+38h+var_10], rax
0x140016dad  mov     rdi, rcx
0x140016db0  mov     dword ptr [rsp+38h+IdentifierAuthority.Value], 0
0x140016db8  mov     ecx, 6; SubAuthorityCount
0x140016dbd  mov     word ptr [rsp+38h+IdentifierAuthority.Value+4], 500h
0x140016dc4  call    cs:__imp_RtlLengthRequiredSid
0x140016dcb  nop     dword ptr [rax+rax+00h]
0x140016dd0  mov     r8b, 0Dh
0x140016dd3  mov     ecx, 1
0x140016dd8  mov     edx, eax
0x140016dda  call    LuafvAllocatePool
0x140016ddf  mov     rbx, rax
0x140016de2  test    rax, rax
0x140016de5  jnz     short loc_140016DF1
0x140016de7  mov     eax, 0C000009Ah
0x140016dec  jmp     loc_140016EA6
0x140016df1  mov     r8b, 6; SubAuthorityCount
0x140016df4  lea     rdx, [rsp+38h+IdentifierAuthority]; IdentifierAuthority
0x140016df9  mov     rcx, rbx; Sid
0x140016dfc  call    cs:__imp_RtlInitializeSid
0x140016e03  nop     dword ptr [rax+rax+00h]
0x140016e08  xor     edx, edx; SubAuthority
0x140016e0a  mov     rcx, rbx; Sid
0x140016e0d  call    cs:__imp_RtlSubAuthoritySid
0x140016e14  nop     dword ptr [rax+rax+00h]
0x140016e19  mov     edx, 1; SubAuthority
0x140016e1e  mov     rcx, rbx; Sid
0x140016e21  mov     dword ptr [rax], 50h ; 'P'
0x140016e27  call    cs:__imp_RtlSubAuthoritySid
0x140016e2e  nop     dword ptr [rax+rax+00h]
0x140016e33  mov     edx, 2; SubAuthority
0x140016e38  mov     rcx, rbx; Sid
0x140016e3b  mov     dword ptr [rax], 38FB89B5h
0x140016e41  call    cs:__imp_RtlSubAuthoritySid
0x140016e48  nop     dword ptr [rax+rax+00h]
0x140016e4d  mov     edx, 3; SubAuthority
0x140016e52  mov     rcx, rbx; Sid
0x140016e55  mov     dword ptr [rax], 0CBC28419h
0x140016e5b  call    cs:__imp_RtlSubAuthoritySid
0x140016e62  nop     dword ptr [rax+rax+00h]
0x140016e67  mov     edx, 4; SubAuthority
0x140016e6c  mov     rcx, rbx; Sid
0x140016e6f  mov     dword ptr [rax], 6D236C5Ch
0x140016e75  call    cs:__imp_RtlSubAuthoritySid
0x140016e7c  nop     dword ptr [rax+rax+00h]
0x140016e81  mov     edx, 5; SubAuthority
0x140016e86  mov     rcx, rbx; Sid
0x140016e89  mov     dword ptr [rax], 6E770057h
0x140016e8f  call    cs:__imp_RtlSubAuthoritySid
0x140016e96  nop     dword ptr [rax+rax+00h]
0x140016e9b  mov     dword ptr [rax], 876402C0h
0x140016ea1  xor     eax, eax
0x140016ea3  mov     [rdi], rbx
0x140016ea6  mov     rcx, [rsp+38h+var_10]
0x140016eab  xor     rcx, rsp; StackCookie
0x140016eae  call    __security_check_cookie
0x140016eb3  mov     rbx, [rsp+38h+arg_8]
0x140016eb8  add     rsp, 30h
0x140016ebc  pop     rdi
0x140016ebd  retn
```
