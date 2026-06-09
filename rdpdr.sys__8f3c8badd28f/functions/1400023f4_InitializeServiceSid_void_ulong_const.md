# InitializeServiceSid(void *,ulong * const)

- ea: `0x1400023f4`
- end: `0x1400024ea`
- name: `?InitializeServiceSid@@YAXPEAXQEAK@Z`
- size: `246`
- prototype: `void __fastcall(PSID Sid, unsigned int *const)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callers

- `0x140018ea4`
- `0x14002a1e0`
- `0x14002b088`
- `0x14002c54c`
- `0x14002ce44`

## callees

- `0x140006480`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x14000242d`
- `ntoskrnl!RtlInitializeSid` at `0x14000242d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000243e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000245a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140002473`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000248c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400024a5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400024be`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000243e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000245a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140002473`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000248c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400024a5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400024be`

## pseudocode

```c
void __fastcall InitializeServiceSid(PSID Sid, unsigned int *const a2)
{
  ULONG v4; // ebx
  ULONG v5; // ebx
  ULONG v6; // ebx
  ULONG v7; // ebx
  ULONG v8; // ebx
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-18h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  RtlInitializeSid(Sid, &IdentifierAuthority, 6u);
  *RtlSubAuthoritySid(Sid, 0) = 80;
  v4 = *a2;
  *RtlSubAuthoritySid(Sid, 1u) = v4;
  v5 = a2[1];
  *RtlSubAuthoritySid(Sid, 2u) = v5;
  v6 = a2[2];
  *RtlSubAuthoritySid(Sid, 3u) = v6;
  v7 = a2[3];
  *RtlSubAuthoritySid(Sid, 4u) = v7;
  v8 = a2[4];
  *RtlSubAuthoritySid(Sid, 5u) = v8;
}

```

## disassembly

```asm
0x1400023f4  mov     [rsp+arg_8], rbx
0x1400023f9  mov     [rsp+arg_10], rsi
0x1400023fe  push    rdi
0x1400023ff  sub     rsp, 30h
0x140002403  mov     rax, cs:__security_cookie
0x14000240a  xor     rax, rsp
0x14000240d  mov     [rsp+38h+var_10], rax
0x140002412  mov     rdi, rdx
0x140002415  mov     word ptr [rsp+38h+IdentifierAuthority.Value+4], 500h
0x14000241c  xor     eax, eax
0x14000241e  lea     rdx, [rsp+38h+IdentifierAuthority]; IdentifierAuthority
0x140002423  mov     r8b, 6; SubAuthorityCount
0x140002426  mov     dword ptr [rsp+38h+IdentifierAuthority.Value], eax
0x14000242a  mov     rsi, rcx
0x14000242d  call    cs:__imp_RtlInitializeSid
0x140002434  nop     dword ptr [rax+rax+00h]
0x140002439  xor     edx, edx; SubAuthority
0x14000243b  mov     rcx, rsi; Sid
0x14000243e  call    cs:__imp_RtlSubAuthoritySid
0x140002445  nop     dword ptr [rax+rax+00h]
0x14000244a  mov     edx, 1; SubAuthority
0x14000244f  mov     rcx, rsi; Sid
0x140002452  mov     dword ptr [rax], 50h ; 'P'
0x140002458  mov     ebx, [rdi]
0x14000245a  call    cs:__imp_RtlSubAuthoritySid
0x140002461  nop     dword ptr [rax+rax+00h]
0x140002466  mov     edx, 2; SubAuthority
0x14000246b  mov     rcx, rsi; Sid
0x14000246e  mov     [rax], ebx
0x140002470  mov     ebx, [rdi+4]
0x140002473  call    cs:__imp_RtlSubAuthoritySid
0x14000247a  nop     dword ptr [rax+rax+00h]
0x14000247f  mov     edx, 3; SubAuthority
0x140002484  mov     rcx, rsi; Sid
0x140002487  mov     [rax], ebx
0x140002489  mov     ebx, [rdi+8]
0x14000248c  call    cs:__imp_RtlSubAuthoritySid
0x140002493  nop     dword ptr [rax+rax+00h]
0x140002498  mov     edx, 4; SubAuthority
0x14000249d  mov     rcx, rsi; Sid
0x1400024a0  mov     [rax], ebx
0x1400024a2  mov     ebx, [rdi+0Ch]
0x1400024a5  call    cs:__imp_RtlSubAuthoritySid
0x1400024ac  nop     dword ptr [rax+rax+00h]
0x1400024b1  mov     edx, 5; SubAuthority
0x1400024b6  mov     rcx, rsi; Sid
0x1400024b9  mov     [rax], ebx
0x1400024bb  mov     ebx, [rdi+10h]
0x1400024be  call    cs:__imp_RtlSubAuthoritySid
0x1400024c5  nop     dword ptr [rax+rax+00h]
0x1400024ca  mov     [rax], ebx
0x1400024cc  mov     rcx, [rsp+38h+var_10]
0x1400024d1  xor     rcx, rsp; StackCookie
0x1400024d4  call    __security_check_cookie
0x1400024d9  mov     rbx, [rsp+38h+arg_8]
0x1400024de  mov     rsi, [rsp+38h+arg_10]
0x1400024e3  add     rsp, 30h
0x1400024e7  pop     rdi
0x1400024e8  retn
```
