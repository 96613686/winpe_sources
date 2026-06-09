# IsTIFileDescriptor

- ea: `0x1800f6be0`
- end: `0x1800f6d42`
- name: `IsTIFileDescriptor`
- size: `354`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800f699c`

## callees

- `0x180037920`
- `0x1800391f0`
- `0x1800f6be0`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x1800f6c46`
- `ntdll!RtlInitializeSid` at `0x1800f6c46`
- `ntdll!RtlSubAuthoritySid` at `0x1800f6c57`
- `ntdll!RtlSubAuthoritySid` at `0x1800f6c73`
- `ntdll!RtlSubAuthoritySid` at `0x1800f6c8b`
- `ntdll!RtlSubAuthoritySid` at `0x1800f6ca3`
- `ntdll!RtlSubAuthoritySid` at `0x1800f6cbb`
- `ntdll!RtlSubAuthoritySid` at `0x1800f6cd3`
- `ntdll!RtlSubAuthoritySid` at `0x1800f6c57`
- `ntdll!RtlSubAuthoritySid` at `0x1800f6c73`
- `ntdll!RtlSubAuthoritySid` at `0x1800f6c8b`
- `ntdll!RtlSubAuthoritySid` at `0x1800f6ca3`
- `ntdll!RtlSubAuthoritySid` at `0x1800f6cbb`
- `ntdll!RtlSubAuthoritySid` at `0x1800f6cd3`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1800f6cf0`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1800f6cf0`
- `ntdll!RtlLengthRequiredSid` at `0x1800f6c0e`
- `ntdll!RtlLengthRequiredSid` at `0x1800f6c0e`
- `ntdll!RtlEqualSid` at `0x1800f6d0c`
- `ntdll!RtlEqualSid` at `0x1800f6d0c`

## pseudocode

```c
HLOCAL __fastcall IsTIFileDescriptor(PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  ULONG v2; // eax
  HLOCAL result; // rax
  HLOCAL v4; // rbx
  unsigned int v5; // edi
  unsigned __int8 OwnerDefaulted[8]; // [rsp+20h] [rbp-28h] BYREF
  PSID Owner; // [rsp+28h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+30h] [rbp-18h] BYREF

  Owner = 0;
  OwnerDefaulted[0] = 0;
  v2 = RtlLengthRequiredSid(6u);
  result = LocalAlloc(0, v2);
  v4 = result;
  if ( result )
  {
    *(_DWORD *)IdentifierAuthority.Value = 0;
    *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
    RtlInitializeSid(result, &IdentifierAuthority, 6u);
    v5 = 1;
    *RtlSubAuthoritySid(v4, 0) = 80;
    *RtlSubAuthoritySid(v4, 1u) = 956008885;
    *RtlSubAuthoritySid(v4, 2u) = -876444647;
    *RtlSubAuthoritySid(v4, 3u) = 1831038044;
    *RtlSubAuthoritySid(v4, 4u) = 1853292631;
    *RtlSubAuthoritySid(v4, 5u) = -2023488832;
    if ( RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, OwnerDefaulted) < 0
      || !Owner
      || !RtlEqualSid(v4, Owner) )
    {
      v5 = 0;
    }
    LocalFree(v4);
    return (HLOCAL)v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800f6be0  push    rbp
0x1800f6be2  push    rbx
0x1800f6be3  push    rsi
0x1800f6be4  push    rdi
0x1800f6be5  mov     rbp, rsp
0x1800f6be8  sub     rsp, 48h
0x1800f6bec  mov     rax, cs:__security_cookie
0x1800f6bf3  xor     rax, rsp
0x1800f6bf6  mov     [rbp+var_10], rax
0x1800f6bfa  mov     rsi, rcx
0x1800f6bfd  mov     [rbp+Owner], 0
0x1800f6c05  mov     ecx, 6; SubAuthorityCount
0x1800f6c0a  mov     [rbp+OwnerDefaulted], 0
0x1800f6c0e  call    cs:__imp_RtlLengthRequiredSid
0x1800f6c15  nop     dword ptr [rax+rax+00h]
0x1800f6c1a  mov     edx, eax; uBytes
0x1800f6c1c  xor     ecx, ecx; uFlags
0x1800f6c1e  call    LocalAlloc
0x1800f6c23  mov     rbx, rax
0x1800f6c26  test    rax, rax
0x1800f6c29  jz      loc_1800F6D3C
0x1800f6c2f  mov     r8b, 6; SubAuthorityCount
0x1800f6c32  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x1800f6c39  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1800f6c3d  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x1800f6c43  mov     rcx, rax; Sid
0x1800f6c46  call    cs:__imp_RtlInitializeSid
0x1800f6c4d  nop     dword ptr [rax+rax+00h]
0x1800f6c52  xor     edx, edx; SubAuthority
0x1800f6c54  mov     rcx, rbx; Sid
0x1800f6c57  call    cs:__imp_RtlSubAuthoritySid
0x1800f6c5e  nop     dword ptr [rax+rax+00h]
0x1800f6c63  mov     edi, 1
0x1800f6c68  mov     rcx, rbx; Sid
0x1800f6c6b  mov     edx, edi; SubAuthority
0x1800f6c6d  mov     dword ptr [rax], 50h ; 'P'
0x1800f6c73  call    cs:__imp_RtlSubAuthoritySid
0x1800f6c7a  nop     dword ptr [rax+rax+00h]
0x1800f6c7f  lea     edx, [rdi+1]; SubAuthority
0x1800f6c82  mov     rcx, rbx; Sid
0x1800f6c85  mov     dword ptr [rax], 38FB89B5h
0x1800f6c8b  call    cs:__imp_RtlSubAuthoritySid
0x1800f6c92  nop     dword ptr [rax+rax+00h]
0x1800f6c97  lea     edx, [rdi+2]; SubAuthority
0x1800f6c9a  mov     rcx, rbx; Sid
0x1800f6c9d  mov     dword ptr [rax], 0CBC28419h
0x1800f6ca3  call    cs:__imp_RtlSubAuthoritySid
0x1800f6caa  nop     dword ptr [rax+rax+00h]
0x1800f6caf  lea     edx, [rdi+3]; SubAuthority
0x1800f6cb2  mov     rcx, rbx; Sid
0x1800f6cb5  mov     dword ptr [rax], 6D236C5Ch
0x1800f6cbb  call    cs:__imp_RtlSubAuthoritySid
0x1800f6cc2  nop     dword ptr [rax+rax+00h]
0x1800f6cc7  lea     edx, [rdi+4]; SubAuthority
0x1800f6cca  mov     rcx, rbx; Sid
0x1800f6ccd  mov     dword ptr [rax], 6E770057h
0x1800f6cd3  call    cs:__imp_RtlSubAuthoritySid
0x1800f6cda  nop     dword ptr [rax+rax+00h]
0x1800f6cdf  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1800f6ce3  mov     rcx, rsi; SecurityDescriptor
0x1800f6ce6  lea     rdx, [rbp+Owner]; Owner
0x1800f6cea  mov     dword ptr [rax], 876402C0h
0x1800f6cf0  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1800f6cf7  nop     dword ptr [rax+rax+00h]
0x1800f6cfc  test    eax, eax
0x1800f6cfe  js      short loc_1800F6D3E
0x1800f6d00  mov     rdx, [rbp+Owner]; Sid2
0x1800f6d04  test    rdx, rdx
0x1800f6d07  jz      short loc_1800F6D3E
0x1800f6d09  mov     rcx, rbx; Sid1
0x1800f6d0c  call    cs:__imp_RtlEqualSid
0x1800f6d13  nop     dword ptr [rax+rax+00h]
0x1800f6d18  test    al, al
0x1800f6d1a  jz      short loc_1800F6D3E
0x1800f6d1c  mov     rcx, rbx; hMem
0x1800f6d1f  call    LocalFree
0x1800f6d24  mov     eax, edi
0x1800f6d26  mov     rcx, [rbp+var_10]
0x1800f6d2a  xor     rcx, rsp; StackCookie
0x1800f6d2d  call    __security_check_cookie
0x1800f6d32  add     rsp, 48h
0x1800f6d36  pop     rdi
0x1800f6d37  pop     rsi
0x1800f6d38  pop     rbx
0x1800f6d39  pop     rbp
0x1800f6d3a  retn
0x1800f6d3c  jmp     short loc_1800F6D26
0x1800f6d3e  xor     edi, edi
0x1800f6d40  jmp     short loc_1800F6D1C
```
