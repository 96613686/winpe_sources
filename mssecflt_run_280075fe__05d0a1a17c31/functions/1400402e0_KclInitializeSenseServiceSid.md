# KclInitializeSenseServiceSid

- ea: `0x1400402e0`
- end: `0x140040470`
- name: `KclInitializeSenseServiceSid`
- size: `400`
- prototype: `__int64 __fastcall(ULONG Tag)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x1400451e0`

## callees

- `0x140011650`
- `0x1400119c0`
- `0x1400402e0`

## import_xrefs

- `ntoskrnl!RtlSubAuthoritySid` at `0x140040390`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400403aa`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400403c4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400403de`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400403f8`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140040412`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140040390`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400403aa`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400403c4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400403de`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400403f8`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140040412`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14004031a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14004031a`
- `ntoskrnl!RtlInitializeSid` at `0x140040372`
- `ntoskrnl!RtlInitializeSid` at `0x140040372`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040441`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040441`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140040332`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140040332`

## pseudocode

```c
__int64 __fastcall KclInitializeSenseServiceSid(ULONG Tag, _QWORD *a2)
{
  ULONG v4; // edi
  PVOID PoolWithTag; // rax
  void *v6; // rbx
  void *v7; // rsi
  NTSTATUS v8; // edi
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-28h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v4 = RtlLengthRequiredSid(6u);
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, v4, Tag);
  v6 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported || !PoolWithTag )
  {
    v7 = PoolWithTag;
    if ( !PoolWithTag )
      return (unsigned int)-1073741670;
  }
  else
  {
    memset(PoolWithTag, 0, v4);
    v7 = v6;
  }
  v8 = RtlInitializeSid(v6, &IdentifierAuthority, 6u);
  if ( v8 < 0 )
  {
    ExFreePoolWithTag(v7, Tag);
  }
  else
  {
    _mm_lfence();
    *RtlSubAuthoritySid(v6, 0) = 80;
    *RtlSubAuthoritySid(v6, 1u) = 1523878533;
    *RtlSubAuthoritySid(v6, 2u) = 411328482;
    *RtlSubAuthoritySid(v6, 3u) = -1496889487;
    *RtlSubAuthoritySid(v6, 4u) = -1196303424;
    *RtlSubAuthoritySid(v6, 5u) = -1690953988;
    *a2 = v6;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400402e0  mov     [rsp+arg_10], rbx
0x1400402e5  mov     [rsp+arg_18], rbp
0x1400402ea  push    rsi
0x1400402eb  push    rdi
0x1400402ec  push    r14
0x1400402ee  sub     rsp, 30h
0x1400402f2  mov     rax, cs:__security_cookie
0x1400402f9  xor     rax, rsp
0x1400402fc  mov     [rsp+48h+var_20], rax
0x140040301  mov     ebp, ecx
0x140040303  mov     dword ptr [rsp+48h+IdentifierAuthority.Value], 0
0x14004030b  mov     ecx, 6; SubAuthorityCount
0x140040310  mov     word ptr [rsp+48h+IdentifierAuthority.Value+4], 500h
0x140040317  mov     r14, rdx
0x14004031a  call    cs:__imp_RtlLengthRequiredSid
0x140040321  nop     dword ptr [rax+rax+00h]
0x140040326  mov     edx, eax; NumberOfBytes
0x140040328  mov     r8d, ebp; Tag
0x14004032b  mov     ecx, 401h; PoolType
0x140040330  mov     edi, eax
0x140040332  call    cs:__imp_ExAllocatePoolWithTag
0x140040339  nop     dword ptr [rax+rax+00h]
0x14004033e  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140040345  mov     rbx, rax
0x140040348  jnz     loc_140040429
0x14004034e  test    rax, rax
0x140040351  jz      loc_140040429
0x140040357  mov     r8d, edi; Size
0x14004035a  xor     edx, edx; Val
0x14004035c  mov     rcx, rax; void *
0x14004035f  call    memset
0x140040364  mov     rsi, rbx
0x140040367  mov     r8b, 6; SubAuthorityCount
0x14004036a  lea     rdx, [rsp+48h+IdentifierAuthority]; IdentifierAuthority
0x14004036f  mov     rcx, rbx; Sid
0x140040372  call    cs:__imp_RtlInitializeSid
0x140040379  nop     dword ptr [rax+rax+00h]
0x14004037e  mov     edi, eax
0x140040380  test    eax, eax
0x140040382  js      loc_14004043C
0x140040388  lfence
0x14004038b  xor     edx, edx; SubAuthority
0x14004038d  mov     rcx, rbx; Sid
0x140040390  call    cs:__imp_RtlSubAuthoritySid
0x140040397  nop     dword ptr [rax+rax+00h]
0x14004039c  mov     edx, 1; SubAuthority
0x1400403a1  mov     rcx, rbx; Sid
0x1400403a4  mov     dword ptr [rax], 50h ; 'P'
0x1400403aa  call    cs:__imp_RtlSubAuthoritySid
0x1400403b1  nop     dword ptr [rax+rax+00h]
0x1400403b6  mov     edx, 2; SubAuthority
0x1400403bb  mov     rcx, rbx; Sid
0x1400403be  mov     dword ptr [rax], 5AD48A85h
0x1400403c4  call    cs:__imp_RtlSubAuthoritySid
0x1400403cb  nop     dword ptr [rax+rax+00h]
0x1400403d0  mov     edx, 3; SubAuthority
0x1400403d5  mov     rcx, rbx; Sid
0x1400403d8  mov     dword ptr [rax], 18845FE2h
0x1400403de  call    cs:__imp_RtlSubAuthoritySid
0x1400403e5  nop     dword ptr [rax+rax+00h]
0x1400403ea  mov     edx, 4; SubAuthority
0x1400403ef  mov     rcx, rbx; Sid
0x1400403f2  mov     dword ptr [rax], 0A6C74771h
0x1400403f8  call    cs:__imp_RtlSubAuthoritySid
0x1400403ff  nop     dword ptr [rax+rax+00h]
0x140040404  mov     edx, 5; SubAuthority
0x140040409  mov     rcx, rbx; Sid
0x14004040c  mov     dword ptr [rax], 0B8B1DBC0h
0x140040412  call    cs:__imp_RtlSubAuthoritySid
0x140040419  nop     dword ptr [rax+rax+00h]
0x14004041e  mov     dword ptr [rax], 9B3616FCh
0x140040424  mov     [r14], rbx
0x140040427  jmp     short loc_14004044D
0x140040429  mov     rsi, rbx
0x14004042c  test    rbx, rbx
0x14004042f  jnz     loc_140040367
0x140040435  mov     edi, 0C000009Ah
0x14004043a  jmp     short loc_14004044D
0x14004043c  mov     edx, ebp; Tag
0x14004043e  mov     rcx, rsi; P
0x140040441  call    cs:__imp_ExFreePoolWithTag
0x140040448  nop     dword ptr [rax+rax+00h]
0x14004044d  mov     eax, edi
0x14004044f  mov     rcx, [rsp+48h+var_20]
0x140040454  xor     rcx, rsp; StackCookie
0x140040457  call    __security_check_cookie
0x14004045c  mov     rbx, [rsp+48h+arg_10]
0x140040461  mov     rbp, [rsp+48h+arg_18]
0x140040466  add     rsp, 30h
0x14004046a  pop     r14
0x14004046c  pop     rdi
0x14004046d  pop     rsi
0x14004046e  retn
```
