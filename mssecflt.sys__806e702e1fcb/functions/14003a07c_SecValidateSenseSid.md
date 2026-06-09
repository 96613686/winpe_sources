# SecValidateSenseSid

- ea: `0x14003a07c`
- end: `0x14003a142`
- name: `SecValidateSenseSid`
- size: `198`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140039c1c`
- `0x140039e84`

## callees

- `0x14003a07c`

## import_xrefs

- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a090`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a0ad`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a0c9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a0e5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a101`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a11d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a090`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a0ad`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a0c9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a0e5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a101`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a11d`

## pseudocode

```c
__int64 __fastcall SecValidateSenseSid(PSID Sid)
{
  unsigned int v2; // edi

  v2 = -1073741704;
  if ( *RtlSubAuthoritySid(Sid, 0) == 80
    && *RtlSubAuthoritySid(Sid, 1u) == 1523878533
    && *RtlSubAuthoritySid(Sid, 2u) == 411328482
    && *RtlSubAuthoritySid(Sid, 3u) == -1496889487
    && *RtlSubAuthoritySid(Sid, 4u) == -1196303424
    && *RtlSubAuthoritySid(Sid, 5u) == -1690953988 )
  {
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x14003a07c  mov     [rsp+arg_0], rbx
0x14003a081  push    rdi
0x14003a082  sub     rsp, 20h
0x14003a086  xor     edx, edx; SubAuthority
0x14003a088  mov     rbx, rcx
0x14003a08b  mov     edi, 0C0000078h
0x14003a090  call    cs:__imp_RtlSubAuthoritySid
0x14003a097  nop     dword ptr [rax+rax+00h]
0x14003a09c  cmp     dword ptr [rax], 50h ; 'P'
0x14003a09f  jnz     loc_14003A134
0x14003a0a5  mov     edx, 1; SubAuthority
0x14003a0aa  mov     rcx, rbx; Sid
0x14003a0ad  call    cs:__imp_RtlSubAuthoritySid
0x14003a0b4  nop     dword ptr [rax+rax+00h]
0x14003a0b9  cmp     dword ptr [rax], 5AD48A85h
0x14003a0bf  jnz     short loc_14003A134
0x14003a0c1  mov     edx, 2; SubAuthority
0x14003a0c6  mov     rcx, rbx; Sid
0x14003a0c9  call    cs:__imp_RtlSubAuthoritySid
0x14003a0d0  nop     dword ptr [rax+rax+00h]
0x14003a0d5  cmp     dword ptr [rax], 18845FE2h
0x14003a0db  jnz     short loc_14003A134
0x14003a0dd  mov     edx, 3; SubAuthority
0x14003a0e2  mov     rcx, rbx; Sid
0x14003a0e5  call    cs:__imp_RtlSubAuthoritySid
0x14003a0ec  nop     dword ptr [rax+rax+00h]
0x14003a0f1  cmp     dword ptr [rax], 0A6C74771h
0x14003a0f7  jnz     short loc_14003A134
0x14003a0f9  mov     edx, 4; SubAuthority
0x14003a0fe  mov     rcx, rbx; Sid
0x14003a101  call    cs:__imp_RtlSubAuthoritySid
0x14003a108  nop     dword ptr [rax+rax+00h]
0x14003a10d  cmp     dword ptr [rax], 0B8B1DBC0h
0x14003a113  jnz     short loc_14003A134
0x14003a115  mov     edx, 5; SubAuthority
0x14003a11a  mov     rcx, rbx; Sid
0x14003a11d  call    cs:__imp_RtlSubAuthoritySid
0x14003a124  nop     dword ptr [rax+rax+00h]
0x14003a129  xor     ecx, ecx
0x14003a12b  cmp     dword ptr [rax], 9B3616FCh
0x14003a131  cmovz   edi, ecx
0x14003a134  mov     rbx, [rsp+28h+arg_0]
0x14003a139  mov     eax, edi
0x14003a13b  add     rsp, 20h
0x14003a13f  pop     rdi
0x14003a140  retn
```
