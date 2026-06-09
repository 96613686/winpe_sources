# ndisUnloadPeriodicReceives

- ea: `0x140193ae0`
- end: `0x140193c72`
- name: `ndisUnloadPeriodicReceives`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1401937ec`

## callees

- `0x140020a70`
- `0x14002fe60`
- `0x14005d440`
- `0x14006e240`
- `0x1400eb7c0`
- `0x140193ae0`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140193b41`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140193b54`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140193b41`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140193b54`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193bc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193be5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193c0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193c2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193c54`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193bc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193be5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193c0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193c2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193c54`

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
      ExDeleteNPagedLookasideList(&stru_140121500);
      memset(&Lookaside, 0, sizeof(Lookaside));
      memset(&stru_140121500, 0, sizeof(stru_140121500));
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
  if ( qword_140121448 )
  {
    ExFreePoolWithTag(qword_140121448, 0);
    qword_140121448 = 0;
  }
  if ( qword_140121440 )
  {
    ExFreePoolWithTag(qword_140121440, 0);
    qword_140121440 = 0;
  }
  if ( qword_140121438 )
  {
    ExFreePoolWithTag(qword_140121438, 0);
    qword_140121438 = 0;
  }
  if ( qword_140121430 )
  {
    ExFreePoolWithTag(qword_140121430, 0);
    qword_140121430 = 0;
  }
}

```

## disassembly

```asm
0x140193ae0  push    rbx
0x140193ae2  sub     rsp, 20h
0x140193ae6  mov     rcx, cs:Lock; Lock
0x140193aed  xor     eax, eax
0x140193aef  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x140193af4  mov     [rsp+28h+LockState.Flags], al
0x140193af8  test    rcx, rcx
0x140193afb  jz      loc_140193BB2
0x140193b01  xor     r8d, r8d; Flags
0x140193b04  lea     rdx, [rsp+28h+LockState]; LockState
0x140193b09  xor     ebx, ebx
0x140193b0b  call    NdisAcquireRWLockWrite
0x140193b10  mov     rax, cs:PoolHandle
0x140193b17  test    rax, rax
0x140193b1a  jz      short loc_140193B2A
0x140193b1c  mov     rbx, rax
0x140193b1f  mov     cs:PoolHandle, 0
0x140193b2a  cmp     cs:?ndisPeriodicReceives@@3U_NDIS_PERIODIC_RECEIVES@@A, 1; _NDIS_PERIODIC_RECEIVES ndisPeriodicReceives
0x140193b31  jnz     short loc_140193B88
0x140193b33  lea     rcx, Lookaside; Lookaside
0x140193b3a  mov     cs:?ndisPeriodicReceives@@3U_NDIS_PERIODIC_RECEIVES@@A, 0; _NDIS_PERIODIC_RECEIVES ndisPeriodicReceives
0x140193b41  call    cs:__imp_ExDeleteNPagedLookasideList
0x140193b48  nop     dword ptr [rax+rax+00h]
0x140193b4d  lea     rcx, stru_140121500; Lookaside
0x140193b54  call    cs:__imp_ExDeleteNPagedLookasideList
0x140193b5b  nop     dword ptr [rax+rax+00h]
0x140193b60  xor     edx, edx; Val
0x140193b62  lea     rcx, Lookaside; void *
0x140193b69  mov     r8d, 80h; Size
0x140193b6f  call    memset
0x140193b74  xor     edx, edx; Val
0x140193b76  lea     rcx, stru_140121500; void *
0x140193b7d  mov     r8d, 80h; Size
0x140193b83  call    memset
0x140193b88  mov     rcx, cs:Lock; Lock
0x140193b8f  lea     rdx, [rsp+28h+LockState]; LockState
0x140193b94  call    NdisReleaseRWLock
0x140193b99  mov     rcx, cs:Lock; Lock
0x140193ba0  call    NdisFreeRWLock
0x140193ba5  test    rbx, rbx
0x140193ba8  jz      short loc_140193BB2
0x140193baa  mov     rcx, rbx; PoolHandle
0x140193bad  call    NdisFreeNetBufferListPool
0x140193bb2  mov     rcx, cs:?ndisPerCpuPoisonPills@@3PEAU_WORK_QUEUE_ITEM@@EA; P
0x140193bb9  test    rcx, rcx
0x140193bbc  jz      short loc_140193BD7
0x140193bbe  xor     edx, edx; Tag
0x140193bc0  call    cs:__imp_ExFreePoolWithTag
0x140193bc7  nop     dword ptr [rax+rax+00h]
0x140193bcc  mov     cs:?ndisPerCpuPoisonPills@@3PEAU_WORK_QUEUE_ITEM@@EA, 0; _WORK_QUEUE_ITEM * ndisPerCpuPoisonPills
0x140193bd7  mov     rcx, cs:qword_140121448; P
0x140193bde  test    rcx, rcx
0x140193be1  jz      short loc_140193BFC
0x140193be3  xor     edx, edx; Tag
0x140193be5  call    cs:__imp_ExFreePoolWithTag
0x140193bec  nop     dword ptr [rax+rax+00h]
0x140193bf1  mov     cs:qword_140121448, 0
0x140193bfc  mov     rcx, cs:qword_140121440; P
0x140193c03  test    rcx, rcx
0x140193c06  jz      short loc_140193C21
0x140193c08  xor     edx, edx; Tag
0x140193c0a  call    cs:__imp_ExFreePoolWithTag
0x140193c11  nop     dword ptr [rax+rax+00h]
0x140193c16  mov     cs:qword_140121440, 0
0x140193c21  mov     rcx, cs:qword_140121438; P
0x140193c28  test    rcx, rcx
0x140193c2b  jz      short loc_140193C46
0x140193c2d  xor     edx, edx; Tag
0x140193c2f  call    cs:__imp_ExFreePoolWithTag
0x140193c36  nop     dword ptr [rax+rax+00h]
0x140193c3b  mov     cs:qword_140121438, 0
0x140193c46  mov     rcx, cs:qword_140121430; P
0x140193c4d  test    rcx, rcx
0x140193c50  jz      short loc_140193C6B
0x140193c52  xor     edx, edx; Tag
0x140193c54  call    cs:__imp_ExFreePoolWithTag
0x140193c5b  nop     dword ptr [rax+rax+00h]
0x140193c60  mov     cs:qword_140121430, 0
0x140193c6b  add     rsp, 20h
0x140193c6f  pop     rbx
0x140193c70  retn
```
