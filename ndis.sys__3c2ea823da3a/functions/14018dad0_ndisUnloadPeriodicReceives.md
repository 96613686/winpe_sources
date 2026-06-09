# ndisUnloadPeriodicReceives

- ea: `0x14018dad0`
- end: `0x14018dc62`
- name: `ndisUnloadPeriodicReceives`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14018d7dc`

## callees

- `0x140004320`
- `0x140006330`
- `0x1400588d0`
- `0x140068be0`
- `0x1400e65c0`
- `0x14018dad0`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14018db31`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14018db44`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14018db31`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14018db44`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018dbb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018dbd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018dbfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018dc1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018dc44`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018dbb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018dbd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018dbfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018dc1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018dc44`

## pseudocode

```c
void ndisUnloadPeriodicReceives()
{
  NDIS_HANDLE v0; // rbx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( Lock )
  {
    v0 = 0;
    NdisAcquireRWLockWrite(Lock, &LockState, 0);
    if ( PoolHandle )
    {
      v0 = PoolHandle;
      PoolHandle = 0;
    }
    if ( ndisPeriodicReceives == 1 )
    {
      ndisPeriodicReceives = 0;
      ExDeleteNPagedLookasideList(&Lookaside);
      ExDeleteNPagedLookasideList(&stru_14011B500);
      memset(&Lookaside, 0, sizeof(Lookaside));
      memset(&stru_14011B500, 0, sizeof(stru_14011B500));
    }
    NdisReleaseRWLock(Lock, &LockState);
    NdisFreeRWLock(Lock);
    if ( v0 )
      NdisFreeNetBufferListPool(v0);
  }
  if ( ndisPerCpuPoisonPills )
  {
    ExFreePoolWithTag(ndisPerCpuPoisonPills, 0);
    ndisPerCpuPoisonPills = 0;
  }
  if ( qword_14011B448 )
  {
    ExFreePoolWithTag(qword_14011B448, 0);
    qword_14011B448 = 0;
  }
  if ( qword_14011B440 )
  {
    ExFreePoolWithTag(qword_14011B440, 0);
    qword_14011B440 = 0;
  }
  if ( qword_14011B438 )
  {
    ExFreePoolWithTag(qword_14011B438, 0);
    qword_14011B438 = 0;
  }
  if ( qword_14011B430 )
  {
    ExFreePoolWithTag(qword_14011B430, 0);
    qword_14011B430 = 0;
  }
}

```

## disassembly

```asm
0x14018dad0  push    rbx
0x14018dad2  sub     rsp, 20h
0x14018dad6  mov     rcx, cs:Lock; Lock
0x14018dadd  xor     eax, eax
0x14018dadf  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x14018dae4  mov     [rsp+28h+LockState.Flags], al
0x14018dae8  test    rcx, rcx
0x14018daeb  jz      loc_14018DBA2
0x14018daf1  xor     r8d, r8d; Flags
0x14018daf4  lea     rdx, [rsp+28h+LockState]; LockState
0x14018daf9  xor     ebx, ebx
0x14018dafb  call    NdisAcquireRWLockWrite
0x14018db00  mov     rax, cs:PoolHandle
0x14018db07  test    rax, rax
0x14018db0a  jz      short loc_14018DB1A
0x14018db0c  mov     rbx, rax
0x14018db0f  mov     cs:PoolHandle, 0
0x14018db1a  cmp     cs:?ndisPeriodicReceives@@3U_NDIS_PERIODIC_RECEIVES@@A, 1; _NDIS_PERIODIC_RECEIVES ndisPeriodicReceives
0x14018db21  jnz     short loc_14018DB78
0x14018db23  lea     rcx, Lookaside; Lookaside
0x14018db2a  mov     cs:?ndisPeriodicReceives@@3U_NDIS_PERIODIC_RECEIVES@@A, 0; _NDIS_PERIODIC_RECEIVES ndisPeriodicReceives
0x14018db31  call    cs:__imp_ExDeleteNPagedLookasideList
0x14018db38  nop     dword ptr [rax+rax+00h]
0x14018db3d  lea     rcx, stru_14011B500; Lookaside
0x14018db44  call    cs:__imp_ExDeleteNPagedLookasideList
0x14018db4b  nop     dword ptr [rax+rax+00h]
0x14018db50  xor     edx, edx; Val
0x14018db52  lea     rcx, Lookaside; void *
0x14018db59  mov     r8d, 80h; Size
0x14018db5f  call    memset
0x14018db64  xor     edx, edx; Val
0x14018db66  lea     rcx, stru_14011B500; void *
0x14018db6d  mov     r8d, 80h; Size
0x14018db73  call    memset
0x14018db78  mov     rcx, cs:Lock; Lock
0x14018db7f  lea     rdx, [rsp+28h+LockState]; LockState
0x14018db84  call    NdisReleaseRWLock
0x14018db89  mov     rcx, cs:Lock; Lock
0x14018db90  call    NdisFreeRWLock
0x14018db95  test    rbx, rbx
0x14018db98  jz      short loc_14018DBA2
0x14018db9a  mov     rcx, rbx; PoolHandle
0x14018db9d  call    NdisFreeNetBufferListPool
0x14018dba2  mov     rcx, cs:?ndisPerCpuPoisonPills@@3PEAU_WORK_QUEUE_ITEM@@EA; P
0x14018dba9  test    rcx, rcx
0x14018dbac  jz      short loc_14018DBC7
0x14018dbae  xor     edx, edx; Tag
0x14018dbb0  call    cs:__imp_ExFreePoolWithTag
0x14018dbb7  nop     dword ptr [rax+rax+00h]
0x14018dbbc  mov     cs:?ndisPerCpuPoisonPills@@3PEAU_WORK_QUEUE_ITEM@@EA, 0; _WORK_QUEUE_ITEM * ndisPerCpuPoisonPills
0x14018dbc7  mov     rcx, cs:qword_14011B448; P
0x14018dbce  test    rcx, rcx
0x14018dbd1  jz      short loc_14018DBEC
0x14018dbd3  xor     edx, edx; Tag
0x14018dbd5  call    cs:__imp_ExFreePoolWithTag
0x14018dbdc  nop     dword ptr [rax+rax+00h]
0x14018dbe1  mov     cs:qword_14011B448, 0
0x14018dbec  mov     rcx, cs:qword_14011B440; P
0x14018dbf3  test    rcx, rcx
0x14018dbf6  jz      short loc_14018DC11
0x14018dbf8  xor     edx, edx; Tag
0x14018dbfa  call    cs:__imp_ExFreePoolWithTag
0x14018dc01  nop     dword ptr [rax+rax+00h]
0x14018dc06  mov     cs:qword_14011B440, 0
0x14018dc11  mov     rcx, cs:qword_14011B438; P
0x14018dc18  test    rcx, rcx
0x14018dc1b  jz      short loc_14018DC36
0x14018dc1d  xor     edx, edx; Tag
0x14018dc1f  call    cs:__imp_ExFreePoolWithTag
0x14018dc26  nop     dword ptr [rax+rax+00h]
0x14018dc2b  mov     cs:qword_14011B438, 0
0x14018dc36  mov     rcx, cs:qword_14011B430; P
0x14018dc3d  test    rcx, rcx
0x14018dc40  jz      short loc_14018DC5B
0x14018dc42  xor     edx, edx; Tag
0x14018dc44  call    cs:__imp_ExFreePoolWithTag
0x14018dc4b  nop     dword ptr [rax+rax+00h]
0x14018dc50  mov     cs:qword_14011B430, 0
0x14018dc5b  add     rsp, 20h
0x14018dc5f  pop     rbx
0x14018dc60  retn
```
