# SamIRemoveDSNameFromGroup

- ea: `0x1803fbe0c`
- end: `0x1803fbf60`
- name: `SamIRemoveDSNameFromGroup`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18040720c`

## callees

- `0x1803fbe0c`
- `0x1803fc2a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fbf04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fbf04`
- `ntdll!RtlEqualSid` at `0x1803fbedd`
- `ntdll!RtlEqualSid` at `0x1803fbedd`
- `SAMSRV!SampUpdatePerformanceCounters` at `0x1803fbe53`
- `SAMSRV!SampUpdatePerformanceCounters` at `0x1803fbe53`
- `SAMSRV!SampSplitSid` at `0x1803fbebe`
- `SAMSRV!SampSplitSid` at `0x1803fbebe`
- `SAMSRV!SampReferenceContext` at `0x1803fbe5c`
- `SAMSRV!SampReferenceContext` at `0x1803fbe5c`
- `SAMSRV!SampDeReferenceContext` at `0x1803fbf3a`
- `SAMSRV!SampDeReferenceContext` at `0x1803fbf3a`
- `SAMSRV!SampTraceEvent` at `0x1803fbe43`
- `SAMSRV!SampTraceEvent` at `0x1803fbf4b`
- `SAMSRV!SampTraceEvent` at `0x1803fbe43`
- `SAMSRV!SampTraceEvent` at `0x1803fbf4b`
- `SAMSRV!SampGetDomainSidFromAccountContext` at `0x1803fbed0`
- `SAMSRV!SampGetDomainSidFromAccountContext` at `0x1803fbed0`
- `SAMSRV!SampRemoveSameDomainMemberFromGlobalOrUniversalGroup` at `0x1803fbef5`
- `SAMSRV!SampRemoveSameDomainMemberFromGlobalOrUniversalGroup` at `0x1803fbef5`
- `SAMSRV!SampRemoveAccountFromGroupMembers` at `0x1803fbf20`
- `SAMSRV!SampRemoveAccountFromGroupMembers` at `0x1803fbf20`

## pseudocode

```c
__int64 __fastcall SamIRemoveDSNameFromGroup(__int64 a1, int a2)
{
  __int64 v4; // r8
  int v5; // ebx
  __int64 v6; // rcx
  char v7; // si
  void *DomainSidFromAccountContext; // rax
  __int64 v9; // rdx
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+20h] BYREF
  PSID Sid1; // [rsp+70h] [rbp+30h] BYREF
  __int64 v14; // [rsp+78h] [rbp+38h] BYREF

  v12 = 0;
  v11 = 0;
  v14 = 0;
  SampTraceEvent(1);
  SampUpdatePerformanceCounters(5);
  SampReferenceContext(a1);
  if ( (*(_BYTE *)(a1 + 192) & 2) == 0 )
  {
    v5 = -1073741811;
    goto LABEL_13;
  }
  v5 = SampDsValidateName(a1, a2, (unsigned int)&v12, (unsigned int)&v11, 0, (__int64)&v14);
  if ( v5 < 0 )
    goto LABEL_13;
  v6 = v12;
  if ( !v12 )
    goto LABEL_9;
  Sid1 = 0;
  LODWORD(v12) = 0;
  v5 = SampSplitSid(v6, &Sid1, &v12);
  if ( v5 < 0 )
    goto LABEL_13;
  v7 = 0;
  DomainSidFromAccountContext = (void *)SampGetDomainSidFromAccountContext(a1);
  if ( RtlEqualSid(Sid1, DomainSidFromAccountContext) )
  {
    v5 = SampRemoveSameDomainMemberFromGlobalOrUniversalGroup(a1, (unsigned int)v12, v11, v14);
    v7 = 1;
  }
  LocalFree(Sid1);
  if ( v5 < 0 )
    goto LABEL_13;
  if ( !v7 )
LABEL_9:
    v5 = SampRemoveAccountFromGroupMembers(a1, 0, v11, v14);
  if ( v5 < 0 )
  {
LABEL_13:
    v9 = 0;
    goto LABEL_14;
  }
  LOBYTE(v9) = 1;
LABEL_14:
  SampDeReferenceContext(a1, v9, v4);
  SampTraceEvent(2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1803fbe0c  mov     [rsp-18h+arg_8], rbx
0x1803fbe11  push    rbp
0x1803fbe12  push    rsi
0x1803fbe13  push    rdi
0x1803fbe14  mov     rbp, rsp
0x1803fbe17  sub     rsp, 40h
0x1803fbe1b  xor     r8d, r8d
0x1803fbe1e  mov     [rbp+arg_0], 0
0x1803fbe26  mov     rbx, rdx
0x1803fbe29  mov     [rbp+var_10], 0
0x1803fbe31  mov     rdi, rcx
0x1803fbe34  mov     [rbp+arg_18], 0
0x1803fbe3c  lea     edx, [r8+19h]
0x1803fbe40  lea     ecx, [rdx-18h]
0x1803fbe43  call    cs:__imp_SampTraceEvent
0x1803fbe49  xor     r8d, r8d
0x1803fbe4c  lea     edx, [r8+1]
0x1803fbe50  lea     ecx, [rdx+4]
0x1803fbe53  call    cs:__imp_SampUpdatePerformanceCounters
0x1803fbe59  mov     rcx, rdi
0x1803fbe5c  call    cs:__imp_SampReferenceContext
0x1803fbe62  test    byte ptr [rdi+0C0h], 2
0x1803fbe69  jz      loc_1803FBF30
0x1803fbe6f  lea     rax, [rbp+arg_18]
0x1803fbe73  mov     rdx, rbx
0x1803fbe76  mov     [rsp+40h+var_18], rax
0x1803fbe7b  lea     r9, [rbp+var_10]
0x1803fbe7f  lea     r8, [rbp+arg_0]
0x1803fbe83  mov     [rsp+40h+var_20], 0
0x1803fbe8c  mov     rcx, rdi
0x1803fbe8f  call    SampDsValidateName
0x1803fbe94  mov     ebx, eax
0x1803fbe96  test    eax, eax
0x1803fbe98  js      loc_1803FBF35
0x1803fbe9e  mov     rcx, [rbp+arg_0]
0x1803fbea2  test    rcx, rcx
0x1803fbea5  jz      short loc_1803FBF13
0x1803fbea7  lea     r8, [rbp+arg_0]
0x1803fbeab  mov     [rbp+Sid1], 0
0x1803fbeb3  lea     rdx, [rbp+Sid1]
0x1803fbeb7  mov     dword ptr [rbp+arg_0], 0
0x1803fbebe  call    cs:__imp_SampSplitSid
0x1803fbec4  mov     ebx, eax
0x1803fbec6  test    eax, eax
0x1803fbec8  js      short loc_1803FBF35
0x1803fbeca  mov     rcx, rdi
0x1803fbecd  xor     sil, sil
0x1803fbed0  call    cs:__imp_SampGetDomainSidFromAccountContext
0x1803fbed6  mov     rcx, [rbp+Sid1]; Sid1
0x1803fbeda  mov     rdx, rax; Sid2
0x1803fbedd  call    cs:__imp_RtlEqualSid
0x1803fbee3  test    al, al
0x1803fbee5  jz      short loc_1803FBF00
0x1803fbee7  mov     r9, [rbp+arg_18]
0x1803fbeeb  mov     rcx, rdi
0x1803fbeee  mov     r8, [rbp+var_10]
0x1803fbef2  mov     edx, dword ptr [rbp+arg_0]
0x1803fbef5  call    cs:__imp_SampRemoveSameDomainMemberFromGlobalOrUniversalGroup
0x1803fbefb  mov     ebx, eax
0x1803fbefd  mov     sil, 1
0x1803fbf00  mov     rcx, [rbp+Sid1]; hMem
0x1803fbf04  call    cs:__imp_LocalFree
0x1803fbf0a  test    ebx, ebx
0x1803fbf0c  js      short loc_1803FBF35
0x1803fbf0e  test    sil, sil
0x1803fbf11  jnz     short loc_1803FBF28
0x1803fbf13  mov     r9, [rbp+arg_18]
0x1803fbf17  xor     edx, edx
0x1803fbf19  mov     r8, [rbp+var_10]
0x1803fbf1d  mov     rcx, rdi
0x1803fbf20  call    cs:__imp_SampRemoveAccountFromGroupMembers
0x1803fbf26  mov     ebx, eax
0x1803fbf28  test    ebx, ebx
0x1803fbf2a  js      short loc_1803FBF35
0x1803fbf2c  mov     dl, 1
0x1803fbf2e  jmp     short loc_1803FBF37
0x1803fbf30  mov     ebx, 0C000000Dh
0x1803fbf35  xor     edx, edx
0x1803fbf37  mov     rcx, rdi
0x1803fbf3a  call    cs:__imp_SampDeReferenceContext
0x1803fbf40  mov     edx, 19h
0x1803fbf45  mov     r8d, ebx
0x1803fbf48  lea     ecx, [rdx-17h]
0x1803fbf4b  call    cs:__imp_SampTraceEvent
0x1803fbf51  mov     eax, ebx
0x1803fbf53  mov     rbx, [rsp+40h+arg_8]
0x1803fbf58  add     rsp, 40h
0x1803fbf5c  pop     rdi
0x1803fbf5d  pop     rsi
0x1803fbf5e  pop     rbp
0x1803fbf5f  retn
```
