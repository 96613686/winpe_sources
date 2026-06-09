# DelayedRoamingRetranmission

- ea: `0x140037a10`
- end: `0x140037ae8`
- name: `DelayedRoamingRetranmission`
- size: `216`
- prototype: `__int64 __fastcall(struct _VELAN *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x14000d2e0`
- `0x140024944`
- `0x140037a10`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140037a44`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140037a44`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a55`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a55`
- `NDIS!NdisAcquireRWLockWrite` at `0x140037a78`
- `NDIS!NdisAcquireRWLockWrite` at `0x140037a78`
- `NDIS!NdisReleaseRWLock` at `0x140037aab`
- `NDIS!NdisReleaseRWLock` at `0x140037aab`

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
0x140037a10  mov     [rsp+arg_8], rbx
0x140037a15  push    rdi
0x140037a16  sub     rsp, 20h
0x140037a1a  xor     eax, eax
0x140037a1c  mov     [rsp+28h+LockState.OldIrql], 0
0x140037a21  mov     rbx, rcx
0x140037a24  mov     word ptr [rsp+28h+LockState.LockState], ax
0x140037a29  mov     rcx, [rcx+58h]
0x140037a2d  test    rcx, rcx
0x140037a30  jz      short loc_140037A61
0x140037a32  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140037a36  mov     rax, [rcx]
0x140037a39  test    rax, rax
0x140037a3c  jz      short loc_140037A52
0x140037a3e  mov     rdx, rcx; Entry
0x140037a41  mov     rcx, rax; Lookaside
0x140037a44  call    cs:__imp_ExFreeToNPagedLookasideList
0x140037a4b  nop     dword ptr [rax+rax+00h]
0x140037a50  jmp     short loc_140037A61
0x140037a52  mov     edx, [rcx+8]; Tag
0x140037a55  call    cs:__imp_ExFreePoolWithTag
0x140037a5c  nop     dword ptr [rax+rax+00h]
0x140037a61  mov     rcx, [rbx+90h]; Lock
0x140037a68  lea     rdx, [rsp+28h+LockState]; LockState
0x140037a6d  xor     r8d, r8d; Flags
0x140037a70  mov     qword ptr [rbx+58h], 0
0x140037a78  call    cs:__imp_NdisAcquireRWLockWrite
0x140037a7f  nop     dword ptr [rax+rax+00h]
0x140037a84  mov     rdi, [rbx+68h]
0x140037a88  lea     rdx, [rsp+28h+LockState]; LockState
0x140037a8d  mov     rcx, [rbx+90h]; Lock
0x140037a94  mov     dword ptr [rbx+60h], 0
0x140037a9b  mov     qword ptr [rbx+70h], 0
0x140037aa3  mov     qword ptr [rbx+68h], 0
0x140037aab  call    cs:__imp_NdisReleaseRWLock
0x140037ab2  nop     dword ptr [rax+rax+00h]
0x140037ab7  test    rdi, rdi
0x140037aba  jz      short loc_140037AC7
0x140037abc  mov     rdx, rdi; struct _NET_BUFFER_LIST *
0x140037abf  mov     rcx, rbx; struct _VELAN *
0x140037ac2  call    ?MP6SendNBLInternal@@YAXPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@@Z; MP6SendNBLInternal(_VELAN *,_NET_BUFFER_LIST *)
0x140037ac7  or      eax, 0FFFFFFFFh
0x140037aca  lock xadd [rbx+1Ch], eax
0x140037acf  cmp     eax, 1
0x140037ad2  jnz     short loc_140037ADC
0x140037ad4  mov     rcx, rbx; struct _VELAN *
0x140037ad7  call    ?PtDeallocateVElan@@YAXPEAU_VELAN@@@Z; PtDeallocateVElan(_VELAN *)
0x140037adc  mov     rbx, [rsp+28h+arg_8]
0x140037ae1  add     rsp, 20h
0x140037ae5  pop     rdi
0x140037ae6  retn
```
