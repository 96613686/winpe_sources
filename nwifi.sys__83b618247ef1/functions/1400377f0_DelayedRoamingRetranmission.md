# DelayedRoamingRetranmission

- ea: `0x1400377f0`
- end: `0x1400378c8`
- name: `DelayedRoamingRetranmission`
- size: `216`
- prototype: `__int64 __fastcall(struct _VELAN *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x14000d2f0`
- `0x140024944`
- `0x1400377f0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140037824`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140037824`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037835`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037835`
- `NDIS!NdisAcquireRWLockWrite` at `0x140037858`
- `NDIS!NdisAcquireRWLockWrite` at `0x140037858`
- `NDIS!NdisReleaseRWLock` at `0x14003788b`
- `NDIS!NdisReleaseRWLock` at `0x14003788b`

## pseudocode

```c
void __fastcall DelayedRoamingRetranmission(struct _VELAN *a1)
{
  _WORK_QUEUE_ITEM *pReTXWorkItem; // rcx
  ULONG *p_WorkerRoutine; // rcx
  struct _NDIS_RW_LOCK_EX *pRWLock; // rcx
  struct _NET_BUFFER_LIST *pNBLQueueHead; // rdi
  struct _NDIS_RW_LOCK_EX *v6; // rcx
  unsigned int v7; // edx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  pReTXWorkItem = a1->pReTXWorkItem;
  if ( pReTXWorkItem )
  {
    p_WorkerRoutine = (ULONG *)&pReTXWorkItem[-1].WorkerRoutine;
    if ( *(_QWORD *)p_WorkerRoutine )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)p_WorkerRoutine, p_WorkerRoutine);
    else
      ExFreePoolWithTag(p_WorkerRoutine, p_WorkerRoutine[2]);
  }
  pRWLock = a1->pRWLock;
  a1->pReTXWorkItem = 0;
  NdisAcquireRWLockWrite(pRWLock, &LockState, 0);
  pNBLQueueHead = a1->pNBLQueueHead;
  v6 = a1->pRWLock;
  a1->uNumRoamingNBL = 0;
  a1->pNBLQueueTail = 0;
  a1->pNBLQueueHead = 0;
  NdisReleaseRWLock(v6, &LockState);
  if ( pNBLQueueHead )
    MP6SendNBLInternal(a1, pNBLQueueHead);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&a1->RefCount, 0xFFFFFFFF) == 1 )
    PtDeallocateVElan(a1, v7);
}

```

## disassembly

```asm
0x1400377f0  mov     [rsp+arg_8], rbx
0x1400377f5  push    rdi
0x1400377f6  sub     rsp, 20h
0x1400377fa  xor     eax, eax
0x1400377fc  mov     [rsp+28h+LockState.OldIrql], 0
0x140037801  mov     rbx, rcx
0x140037804  mov     word ptr [rsp+28h+LockState.LockState], ax
0x140037809  mov     rcx, [rcx+58h]
0x14003780d  test    rcx, rcx
0x140037810  jz      short loc_140037841
0x140037812  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140037816  mov     rax, [rcx]
0x140037819  test    rax, rax
0x14003781c  jz      short loc_140037832
0x14003781e  mov     rdx, rcx; Entry
0x140037821  mov     rcx, rax; Lookaside
0x140037824  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003782b  nop     dword ptr [rax+rax+00h]
0x140037830  jmp     short loc_140037841
0x140037832  mov     edx, [rcx+8]; Tag
0x140037835  call    cs:__imp_ExFreePoolWithTag
0x14003783c  nop     dword ptr [rax+rax+00h]
0x140037841  mov     rcx, [rbx+90h]; Lock
0x140037848  lea     rdx, [rsp+28h+LockState]; LockState
0x14003784d  xor     r8d, r8d; Flags
0x140037850  mov     qword ptr [rbx+58h], 0
0x140037858  call    cs:__imp_NdisAcquireRWLockWrite
0x14003785f  nop     dword ptr [rax+rax+00h]
0x140037864  mov     rdi, [rbx+68h]
0x140037868  lea     rdx, [rsp+28h+LockState]; LockState
0x14003786d  mov     rcx, [rbx+90h]; Lock
0x140037874  mov     dword ptr [rbx+60h], 0
0x14003787b  mov     qword ptr [rbx+70h], 0
0x140037883  mov     qword ptr [rbx+68h], 0
0x14003788b  call    cs:__imp_NdisReleaseRWLock
0x140037892  nop     dword ptr [rax+rax+00h]
0x140037897  test    rdi, rdi
0x14003789a  jz      short loc_1400378A7
0x14003789c  mov     rdx, rdi; struct _NET_BUFFER_LIST *
0x14003789f  mov     rcx, rbx; struct _VELAN *
0x1400378a2  call    ?MP6SendNBLInternal@@YAXPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@@Z; MP6SendNBLInternal(_VELAN *,_NET_BUFFER_LIST *)
0x1400378a7  or      eax, 0FFFFFFFFh
0x1400378aa  lock xadd [rbx+1Ch], eax
0x1400378af  cmp     eax, 1
0x1400378b2  jnz     short loc_1400378BC
0x1400378b4  mov     rcx, rbx; struct _VELAN *
0x1400378b7  call    ?PtDeallocateVElan@@YAXPEAU_VELAN@@@Z; PtDeallocateVElan(_VELAN *)
0x1400378bc  mov     rbx, [rsp+28h+arg_8]
0x1400378c1  add     rsp, 20h
0x1400378c5  pop     rdi
0x1400378c6  retn
```
