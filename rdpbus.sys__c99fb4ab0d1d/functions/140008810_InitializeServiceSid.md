# InitializeServiceSid

- ea: `0x140008810`
- end: `0x140008905`
- name: `InitializeServiceSid`
- size: `245`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callers

- `0x140008c78`

## callees

- `0x140002520`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x140008849`
- `ntoskrnl!RtlInitializeSid` at `0x140008849`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000885c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140008875`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000888e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400088a7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400088c0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400088d9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000885c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140008875`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000888e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400088a7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400088c0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400088d9`

## pseudocode

```c
PULONG __fastcall InitializeServiceSid(PSID Sid, ULONG *a2)
{
  ULONG v4; // ebx
  ULONG v5; // ebx
  ULONG v6; // ebx
  ULONG v7; // ebx
  ULONG v8; // ebx
  ULONG v9; // ebx
  PULONG result; // rax
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-18h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  RtlInitializeSid(Sid, &IdentifierAuthority, 6u);
  v4 = *a2;
  *RtlSubAuthoritySid(Sid, 0) = v4;
  v5 = a2[1];
  *RtlSubAuthoritySid(Sid, 1u) = v5;
  v6 = a2[2];
  *RtlSubAuthoritySid(Sid, 2u) = v6;
  v7 = a2[3];
  *RtlSubAuthoritySid(Sid, 3u) = v7;
  v8 = a2[4];
  *RtlSubAuthoritySid(Sid, 4u) = v8;
  v9 = a2[5];
  result = RtlSubAuthoritySid(Sid, 5u);
  *result = v9;
  return result;
}

```

## disassembly

```asm
0x140008810  mov     [rsp+arg_8], rbx
0x140008815  mov     [rsp+arg_10], rsi
0x14000881a  push    rdi
0x14000881b  sub     rsp, 30h
0x14000881f  mov     rax, cs:__security_cookie
0x140008826  xor     rax, rsp
0x140008829  mov     [rsp+38h+var_10], rax
0x14000882e  mov     rdi, rdx
0x140008831  mov     word ptr [rsp+38h+IdentifierAuthority.Value+4], 500h
0x140008838  xor     eax, eax
0x14000883a  lea     rdx, [rsp+38h+IdentifierAuthority]; IdentifierAuthority
0x14000883f  mov     r8b, 6; SubAuthorityCount
0x140008842  mov     dword ptr [rsp+38h+IdentifierAuthority.Value], eax
0x140008846  mov     rsi, rcx
0x140008849  call    cs:__imp_RtlInitializeSid
0x140008850  nop     dword ptr [rax+rax+00h]
0x140008855  mov     ebx, [rdi]
0x140008857  xor     edx, edx; SubAuthority
0x140008859  mov     rcx, rsi; Sid
0x14000885c  call    cs:__imp_RtlSubAuthoritySid
0x140008863  nop     dword ptr [rax+rax+00h]
0x140008868  mov     edx, 1; SubAuthority
0x14000886d  mov     rcx, rsi; Sid
0x140008870  mov     [rax], ebx
0x140008872  mov     ebx, [rdi+4]
0x140008875  call    cs:__imp_RtlSubAuthoritySid
0x14000887c  nop     dword ptr [rax+rax+00h]
0x140008881  mov     edx, 2; SubAuthority
0x140008886  mov     rcx, rsi; Sid
0x140008889  mov     [rax], ebx
0x14000888b  mov     ebx, [rdi+8]
0x14000888e  call    cs:__imp_RtlSubAuthoritySid
0x140008895  nop     dword ptr [rax+rax+00h]
0x14000889a  mov     edx, 3; SubAuthority
0x14000889f  mov     rcx, rsi; Sid
0x1400088a2  mov     [rax], ebx
0x1400088a4  mov     ebx, [rdi+0Ch]
0x1400088a7  call    cs:__imp_RtlSubAuthoritySid
0x1400088ae  nop     dword ptr [rax+rax+00h]
0x1400088b3  mov     edx, 4; SubAuthority
0x1400088b8  mov     rcx, rsi; Sid
0x1400088bb  mov     [rax], ebx
0x1400088bd  mov     ebx, [rdi+10h]
0x1400088c0  call    cs:__imp_RtlSubAuthoritySid
0x1400088c7  nop     dword ptr [rax+rax+00h]
0x1400088cc  mov     edx, 5; SubAuthority
0x1400088d1  mov     rcx, rsi; Sid
0x1400088d4  mov     [rax], ebx
0x1400088d6  mov     ebx, [rdi+14h]
0x1400088d9  call    cs:__imp_RtlSubAuthoritySid
0x1400088e0  nop     dword ptr [rax+rax+00h]
0x1400088e5  mov     [rax], ebx
0x1400088e7  mov     rcx, [rsp+38h+var_10]
0x1400088ec  xor     rcx, rsp; StackCookie
0x1400088ef  call    __security_check_cookie
0x1400088f4  mov     rbx, [rsp+38h+arg_8]
0x1400088f9  mov     rsi, [rsp+38h+arg_10]
0x1400088fe  add     rsp, 30h
0x140008902  pop     rdi
0x140008903  retn
```
