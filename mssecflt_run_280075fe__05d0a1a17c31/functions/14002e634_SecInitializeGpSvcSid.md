# SecInitializeGpSvcSid

- ea: `0x14002e634`
- end: `0x14002e7a5`
- name: `SecInitializeGpSvcSid`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14003ef8c`

## callees

- `0x140009b80`
- `0x140011610`
- `0x140011650`
- `0x14002e634`

## import_xrefs

- `ntoskrnl!RtlSubAuthoritySid` at `0x14002e6e2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002e6fc`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002e716`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002e730`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002e74a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002e764`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002e6e2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002e6fc`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002e716`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002e730`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002e74a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002e764`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002e669`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002e669`
- `ntoskrnl!RtlInitializeSid` at `0x14002e6c4`
- `ntoskrnl!RtlInitializeSid` at `0x14002e6c4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002e69b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002e69b`

## pseudocode

```c
__int64 __fastcall SecInitializeGpSvcSid(_QWORD *a1)
{
  SIZE_T v2; // rdx
  PVOID PoolWithTag; // rax
  void *v4; // rbx
  NTSTATUS v5; // edi
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-18h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v2 = RtlLengthRequiredSid(6u);
  if ( qword_140020008 )
    PoolWithTag = (PVOID)qword_140020008(256, v2, 1685283667);
  else
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, v2, 0x64736353u);
  v4 = PoolWithTag;
  if ( PoolWithTag )
  {
    v5 = RtlInitializeSid(PoolWithTag, &IdentifierAuthority, 6u);
    if ( v5 < 0 )
    {
      SecFreePool(v4, 0x64736353u);
    }
    else
    {
      _mm_lfence();
      *RtlSubAuthoritySid(v4, 0) = 80;
      *RtlSubAuthoritySid(v4, 1u) = 2024188204;
      *RtlSubAuthoritySid(v4, 2u) = -1849157069;
      *RtlSubAuthoritySid(v4, 3u) = 898691311;
      *RtlSubAuthoritySid(v4, 4u) = -1352947212;
      *RtlSubAuthoritySid(v4, 5u) = 762398166;
      *a1 = v4;
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14002e634  mov     [rsp+arg_8], rbx
0x14002e639  mov     [rsp+arg_10], rsi
0x14002e63e  push    rdi
0x14002e63f  sub     rsp, 30h
0x14002e643  mov     rax, cs:__security_cookie
0x14002e64a  xor     rax, rsp
0x14002e64d  mov     [rsp+38h+var_10], rax
0x14002e652  mov     rsi, rcx
0x14002e655  mov     dword ptr [rsp+38h+IdentifierAuthority.Value], 0
0x14002e65d  mov     ecx, 6; SubAuthorityCount
0x14002e662  mov     word ptr [rsp+38h+IdentifierAuthority.Value+4], 500h
0x14002e669  call    cs:__imp_RtlLengthRequiredSid
0x14002e670  nop     dword ptr [rax+rax+00h]
0x14002e675  mov     edx, eax; NumberOfBytes
0x14002e677  mov     r8d, 64736353h; Tag
0x14002e67d  mov     rax, cs:qword_140020008
0x14002e684  test    rax, rax
0x14002e687  jz      short loc_14002E696
0x14002e689  mov     ecx, 100h
0x14002e68e  call    cs:__guard_dispatch_icall_fptr
0x14002e694  jmp     short loc_14002E6A7
0x14002e696  mov     ecx, 1; PoolType
0x14002e69b  call    cs:__imp_ExAllocatePoolWithTag
0x14002e6a2  nop     dword ptr [rax+rax+00h]
0x14002e6a7  mov     rbx, rax
0x14002e6aa  test    rax, rax
0x14002e6ad  jnz     short loc_14002E6B9
0x14002e6af  mov     edi, 0C000009Ah
0x14002e6b4  jmp     loc_14002E785
0x14002e6b9  mov     r8b, 6; SubAuthorityCount
0x14002e6bc  lea     rdx, [rsp+38h+IdentifierAuthority]; IdentifierAuthority
0x14002e6c1  mov     rcx, rbx; Sid
0x14002e6c4  call    cs:__imp_RtlInitializeSid
0x14002e6cb  nop     dword ptr [rax+rax+00h]
0x14002e6d0  mov     edi, eax
0x14002e6d2  mov     rcx, rbx; P
0x14002e6d5  test    eax, eax
0x14002e6d7  js      loc_14002E77B
0x14002e6dd  lfence
0x14002e6e0  xor     edx, edx; SubAuthority
0x14002e6e2  call    cs:__imp_RtlSubAuthoritySid
0x14002e6e9  nop     dword ptr [rax+rax+00h]
0x14002e6ee  mov     edx, 1; SubAuthority
0x14002e6f3  mov     rcx, rbx; Sid
0x14002e6f6  mov     dword ptr [rax], 50h ; 'P'
0x14002e6fc  call    cs:__imp_RtlSubAuthoritySid
0x14002e703  nop     dword ptr [rax+rax+00h]
0x14002e708  mov     edx, 2; SubAuthority
0x14002e70d  mov     rcx, rbx; Sid
0x14002e710  mov     dword ptr [rax], 78A6A92Ch
0x14002e716  call    cs:__imp_RtlSubAuthoritySid
0x14002e71d  nop     dword ptr [rax+rax+00h]
0x14002e722  mov     edx, 3; SubAuthority
0x14002e727  mov     rcx, rbx; Sid
0x14002e72a  mov     dword ptr [rax], 91C81A33h
0x14002e730  call    cs:__imp_RtlSubAuthoritySid
0x14002e737  nop     dword ptr [rax+rax+00h]
0x14002e73c  mov     edx, 4; SubAuthority
0x14002e741  mov     rcx, rbx; Sid
0x14002e744  mov     dword ptr [rax], 3590F0EFh
0x14002e74a  call    cs:__imp_RtlSubAuthoritySid
0x14002e751  nop     dword ptr [rax+rax+00h]
0x14002e756  mov     edx, 5; SubAuthority
0x14002e75b  mov     rcx, rbx; Sid
0x14002e75e  mov     dword ptr [rax], 0AF5BA9F4h
0x14002e764  call    cs:__imp_RtlSubAuthoritySid
0x14002e76b  nop     dword ptr [rax+rax+00h]
0x14002e770  mov     dword ptr [rax], 2D7145D6h
0x14002e776  mov     [rsi], rbx
0x14002e779  jmp     short loc_14002E785
0x14002e77b  mov     edx, 64736353h; Tag
0x14002e780  call    SecFreePool
0x14002e785  mov     eax, edi
0x14002e787  mov     rcx, [rsp+38h+var_10]
0x14002e78c  xor     rcx, rsp; StackCookie
0x14002e78f  call    __security_check_cookie
0x14002e794  mov     rbx, [rsp+38h+arg_8]
0x14002e799  mov     rsi, [rsp+38h+arg_10]
0x14002e79e  add     rsp, 30h
0x14002e7a2  pop     rdi
0x14002e7a3  retn
```
