# UcpFreeClientSessionContext

- ea: `0x1c0153aec`
- end: `0x1c0153bd4`
- name: `UcpFreeClientSessionContext`
- size: `232`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1c0152eec`
- `0x1c0153670`
- `0x1c0153bdc`

## callees

- `0x1c008f21c`
- `0x1c008f680`
- `0x1c0152f6c`
- `0x1c0153aec`
- `0x1c0153ed4`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c0153b57`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c0153b57`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c0153b32`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c0153b32`
- `ntoskrnl!ObfDereferenceObject` at `0x1c0153b87`
- `ntoskrnl!ObfDereferenceObject` at `0x1c0153b87`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0153b9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0153b9f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0153b63`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0153b63`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0153b22`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0153b22`

## pseudocode

```c
void __fastcall UcpFreeClientSessionContext(PVOID *P)
{
  _QWORD *v2; // rdi
  PSECURITY_DESCRIPTOR *v3; // rdi

  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000000) != 0 )
    WPP_SF_q(42, WPP_f62b8c1d254e300ad0c1fbfd2cbd38f2_Traceguids, P);
  v2 = P[1];
  if ( v2 )
  {
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(v2[14]);
    UcpRemoveSessionContextFromSessionList(P, P[1]);
    v3 = (PSECURITY_DESCRIPTOR *)P[1];
    P[1] = 0;
    ExReleaseCacheAwarePushLockExclusive(v3[14]);
    KeLeaveCriticalRegion();
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3, 0xFFFFFFFF) == 1 )
      UcFreeClientSession(v3);
  }
  ObfDereferenceObject(P[7]);
  *((_DWORD *)P + 4) = 1668498293;
  ExFreePoolWithTag(P, 0);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000000) != 0 )
    WPP_SF_(43, WPP_f62b8c1d254e300ad0c1fbfd2cbd38f2_Traceguids);
}

```

## disassembly

```asm
0x1c0153aec  mov     [rsp+arg_8], rbx
0x1c0153af1  push    rdi
0x1c0153af2  sub     rsp, 20h
0x1c0153af6  mov     rbx, rcx
0x1c0153af9  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000000h
0x1c0153b03  jz      short loc_1C0153B19
0x1c0153b05  mov     ecx, 2Ah ; '*'
0x1c0153b0a  lea     rdx, WPP_f62b8c1d254e300ad0c1fbfd2cbd38f2_Traceguids
0x1c0153b11  mov     r8, rbx
0x1c0153b14  call    WPP_SF_q
0x1c0153b19  mov     rdi, [rbx+8]
0x1c0153b1d  test    rdi, rdi
0x1c0153b20  jz      short loc_1C0153B83
0x1c0153b22  call    cs:__imp_KeEnterCriticalRegion
0x1c0153b29  nop     dword ptr [rax+rax+00h]
0x1c0153b2e  mov     rcx, [rdi+70h]
0x1c0153b32  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c0153b39  nop     dword ptr [rax+rax+00h]
0x1c0153b3e  mov     rdx, [rbx+8]
0x1c0153b42  mov     rcx, rbx
0x1c0153b45  call    UcpRemoveSessionContextFromSessionList
0x1c0153b4a  mov     rdi, [rbx+8]
0x1c0153b4e  and     qword ptr [rbx+8], 0
0x1c0153b53  mov     rcx, [rdi+70h]
0x1c0153b57  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c0153b5e  nop     dword ptr [rax+rax+00h]
0x1c0153b63  call    cs:__imp_KeLeaveCriticalRegion
0x1c0153b6a  nop     dword ptr [rax+rax+00h]
0x1c0153b6f  or      eax, 0FFFFFFFFh
0x1c0153b72  lock xadd [rdi], eax
0x1c0153b76  cmp     eax, 1
0x1c0153b79  jnz     short loc_1C0153B83
0x1c0153b7b  mov     rcx, rdi; P
0x1c0153b7e  call    UcFreeClientSession
0x1c0153b83  mov     rcx, [rbx+38h]; Object
0x1c0153b87  call    cs:__imp_ObfDereferenceObject
0x1c0153b8e  nop     dword ptr [rax+rax+00h]
0x1c0153b93  xor     edx, edx; Tag
0x1c0153b95  mov     dword ptr [rbx+10h], 63734375h
0x1c0153b9c  mov     rcx, rbx; P
0x1c0153b9f  call    cs:__imp_ExFreePoolWithTag
0x1c0153ba6  nop     dword ptr [rax+rax+00h]
0x1c0153bab  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000000h
0x1c0153bb5  jz      short loc_1C0153BC8
0x1c0153bb7  mov     ecx, 2Bh ; '+'
0x1c0153bbc  lea     rdx, WPP_f62b8c1d254e300ad0c1fbfd2cbd38f2_Traceguids
0x1c0153bc3  call    WPP_SF_
0x1c0153bc8  mov     rbx, [rsp+28h+arg_8]
0x1c0153bcd  add     rsp, 20h
0x1c0153bd1  pop     rdi
0x1c0153bd2  retn
```
