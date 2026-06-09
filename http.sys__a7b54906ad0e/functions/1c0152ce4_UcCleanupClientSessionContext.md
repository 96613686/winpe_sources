# UcCleanupClientSessionContext

- ea: `0x1c0152ce4`
- end: `0x1c0152ee6`
- name: `UcCleanupClientSessionContext`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1c00a7b10`

## callees

- `0x1c0057bac`
- `0x1c008f21c`
- `0x1c008f3ec`
- `0x1c00d6070`
- `0x1c00d60c4`
- `0x1c0152ce4`
- `0x1c015341c`
- `0x1c015356c`
- `0x1c01539ec`
- `0x1c0153ed4`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1c0152de6`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1c0152de6`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c0152e24`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c0152e24`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c0152d9d`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c0152d9d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0152e48`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0152e48`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0152d81`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0152d81`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0152e30`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0152e54`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0152e30`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0152e54`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0152d64`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0152d8d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0152d64`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0152d8d`

## pseudocode

```c
__int64 __fastcall UcCleanupClientSessionContext(__int64 a1, __int64 a2)
{
  char v4; // r14
  __int64 v5; // rdi
  __int64 v6; // rbx
  _QWORD *v7; // rax
  __int64 v8; // rdx
  _QWORD *v9; // rcx
  _QWORD v11[2]; // [rsp+20h] [rbp-38h] BYREF
  _OWORD v12[2]; // [rsp+30h] [rbp-28h] BYREF

  v12[0] = 0;
  v4 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000000) != 0 )
    WPP_SF_qq(36, WPP_f62b8c1d254e300ad0c1fbfd2cbd38f2_Traceguids, a1, a2);
  v11[1] = v11;
  v11[0] = v11;
  v5 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v6 = *(_QWORD *)(v5 + 8);
  UxPodAttachThread(*(_QWORD *)(v6 + 120), v12);
  *(_QWORD *)(*(_QWORD *)(a2 + 48) + 32LL) = 1699955544;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*(_QWORD *)(v6 + 128) + 7624LL, 0);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v6 + 112));
  *(_BYTE *)(v5 + 4) = 1;
  UcpFlushRequestsFromSessionContext(v5, v11);
  UcpRemoveSessionContextFromSessionList(v5, v6);
  if ( *(_QWORD *)(v6 + 72) == v6 + 72 )
  {
    v4 = 1;
    RtlRemoveEntryHashTable(
      (PRTL_DYNAMIC_HASH_TABLE)(*(_QWORD *)(v6 + 128) + 7632LL),
      (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v6 + 32),
      0);
    v7 = (_QWORD *)(v6 + 56);
    v8 = *(_QWORD *)(v6 + 56);
    if ( *(_QWORD *)(v8 + 8) != v6 + 56 || (v9 = *(_QWORD **)(v6 + 64), (_QWORD *)*v9 != v7) )
      __fastfail(3u);
    *v9 = v8;
    *(_QWORD *)(v8 + 8) = v9;
    *v7 = 0;
    *(_QWORD *)(v6 + 64) = 0;
  }
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v6 + 112));
  KeLeaveCriticalRegion();
  ExReleasePushLockExclusiveEx(*(_QWORD *)(v6 + 128) + 7624LL, 0);
  KeLeaveCriticalRegion();
  UcpDeleteFlushedRequests(v11);
  *(_BYTE *)(*(_QWORD *)(a1 + 184) + 3LL) |= 1u;
  *(_DWORD *)(a1 + 48) = 259;
  *(_QWORD *)(v5 + 24) = a1;
  if ( v4 )
    UcpCleanupClientSession((PVOID)v6);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5, 0xFFFFFFFF) == 1 )
    UcpCleanupSessionContextCompletion(v5);
  UxPodDetachThread(v12);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000000) != 0 )
    WPP_SF_(37, WPP_f62b8c1d254e300ad0c1fbfd2cbd38f2_Traceguids);
  return 259;
}

```

## disassembly

```asm
0x1c0152ce4  mov     [rsp+arg_0], rbx
0x1c0152ce9  mov     [rsp+arg_10], rbp
0x1c0152cee  push    rsi
0x1c0152cef  push    rdi
0x1c0152cf0  push    r14
0x1c0152cf2  sub     rsp, 40h
0x1c0152cf6  xorps   xmm0, xmm0
0x1c0152cf9  mov     rbp, rdx
0x1c0152cfc  movups  [rsp+58h+var_28], xmm0
0x1c0152d01  mov     rsi, rcx
0x1c0152d04  xor     r14b, r14b
0x1c0152d07  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000000h
0x1c0152d11  jz      short loc_1C0152D2A
0x1c0152d13  mov     r9, rdx
0x1c0152d16  mov     ecx, 24h ; '$'
0x1c0152d1b  lea     rdx, WPP_f62b8c1d254e300ad0c1fbfd2cbd38f2_Traceguids
0x1c0152d22  mov     r8, rsi
0x1c0152d25  call    WPP_SF_qq
0x1c0152d2a  lea     rax, [rsp+58h+var_38]
0x1c0152d2f  mov     [rsp+58h+var_30], rax
0x1c0152d34  lea     rdx, [rsp+58h+var_28]
0x1c0152d39  lea     rax, [rsp+58h+var_38]
0x1c0152d3e  mov     [rsp+58h+var_38], rax
0x1c0152d43  mov     rax, [rbp+30h]
0x1c0152d47  mov     rdi, [rax+18h]
0x1c0152d4b  mov     rbx, [rdi+8]
0x1c0152d4f  mov     rcx, [rbx+78h]
0x1c0152d53  call    UxPodAttachThread
0x1c0152d58  mov     rax, [rbp+30h]
0x1c0152d5c  mov     qword ptr [rax+20h], 65534358h
0x1c0152d64  call    cs:__imp_KeEnterCriticalRegion
0x1c0152d6b  nop     dword ptr [rax+rax+00h]
0x1c0152d70  mov     rcx, [rbx+80h]
0x1c0152d77  mov     ebp, 1DC8h
0x1c0152d7c  add     rcx, rbp
0x1c0152d7f  xor     edx, edx
0x1c0152d81  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c0152d88  nop     dword ptr [rax+rax+00h]
0x1c0152d8d  call    cs:__imp_KeEnterCriticalRegion
0x1c0152d94  nop     dword ptr [rax+rax+00h]
0x1c0152d99  mov     rcx, [rbx+70h]
0x1c0152d9d  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c0152da4  nop     dword ptr [rax+rax+00h]
0x1c0152da9  lea     rdx, [rsp+58h+var_38]
0x1c0152dae  mov     byte ptr [rdi+4], 1
0x1c0152db2  mov     rcx, rdi
0x1c0152db5  call    UcpFlushRequestsFromSessionContext
0x1c0152dba  mov     rdx, rbx
0x1c0152dbd  mov     rcx, rdi
0x1c0152dc0  call    UcpRemoveSessionContextFromSessionList
0x1c0152dc5  lea     rax, [rbx+48h]
0x1c0152dc9  cmp     [rax], rax
0x1c0152dcc  jnz     short loc_1C0152E20
0x1c0152dce  mov     rcx, [rbx+80h]
0x1c0152dd5  lea     rdx, [rbx+20h]; Entry
0x1c0152dd9  add     rcx, 1DD0h; HashTable
0x1c0152de0  xor     r8d, r8d; Context
0x1c0152de3  mov     r14b, 1
0x1c0152de6  call    cs:__imp_RtlRemoveEntryHashTable
0x1c0152ded  nop     dword ptr [rax+rax+00h]
0x1c0152df2  lea     rax, [rbx+38h]
0x1c0152df6  mov     rdx, [rax]
0x1c0152df9  cmp     [rdx+8], rax
0x1c0152dfd  jnz     loc_1C0152EDF
0x1c0152e03  mov     rcx, [rax+8]
0x1c0152e07  cmp     [rcx], rax
0x1c0152e0a  jnz     loc_1C0152EDF
0x1c0152e10  mov     [rcx], rdx
0x1c0152e13  mov     [rdx+8], rcx
0x1c0152e17  and     qword ptr [rax], 0
0x1c0152e1b  and     qword ptr [rax+8], 0
0x1c0152e20  mov     rcx, [rbx+70h]
0x1c0152e24  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c0152e2b  nop     dword ptr [rax+rax+00h]
0x1c0152e30  call    cs:__imp_KeLeaveCriticalRegion
0x1c0152e37  nop     dword ptr [rax+rax+00h]
0x1c0152e3c  mov     rcx, [rbx+80h]
0x1c0152e43  xor     edx, edx
0x1c0152e45  add     rcx, rbp
0x1c0152e48  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c0152e4f  nop     dword ptr [rax+rax+00h]
0x1c0152e54  call    cs:__imp_KeLeaveCriticalRegion
0x1c0152e5b  nop     dword ptr [rax+rax+00h]
0x1c0152e60  lea     rcx, [rsp+58h+var_38]
0x1c0152e65  call    UcpDeleteFlushedRequests
0x1c0152e6a  mov     rax, [rsi+0B8h]
0x1c0152e71  mov     ebp, 103h
0x1c0152e76  or      byte ptr [rax+3], 1
0x1c0152e7a  mov     [rsi+30h], ebp
0x1c0152e7d  mov     [rdi+18h], rsi
0x1c0152e81  test    r14b, r14b
0x1c0152e84  jz      short loc_1C0152E8E
0x1c0152e86  mov     rcx, rbx; P
0x1c0152e89  call    UcpCleanupClientSession
0x1c0152e8e  or      eax, 0FFFFFFFFh
0x1c0152e91  lock xadd [rdi], eax
0x1c0152e95  cmp     eax, 1
0x1c0152e98  jnz     short loc_1C0152EA2
0x1c0152e9a  mov     rcx, rdi
0x1c0152e9d  call    UcpCleanupSessionContextCompletion
0x1c0152ea2  lea     rcx, [rsp+58h+var_28]
0x1c0152ea7  call    UxPodDetachThread
0x1c0152eac  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000000h
0x1c0152eb6  jz      short loc_1C0152EC9
0x1c0152eb8  mov     ecx, 25h ; '%'
0x1c0152ebd  lea     rdx, WPP_f62b8c1d254e300ad0c1fbfd2cbd38f2_Traceguids
0x1c0152ec4  call    WPP_SF_
0x1c0152ec9  mov     rbx, [rsp+58h+arg_0]
0x1c0152ece  mov     eax, ebp
0x1c0152ed0  mov     rbp, [rsp+58h+arg_10]
0x1c0152ed5  add     rsp, 40h
0x1c0152ed9  pop     r14
0x1c0152edb  pop     rdi
0x1c0152edc  pop     rsi
0x1c0152edd  retn
0x1c0152edf  mov     ecx, 3
0x1c0152ee4  int     29h; Win8: RtlFailFast(ecx)
```
