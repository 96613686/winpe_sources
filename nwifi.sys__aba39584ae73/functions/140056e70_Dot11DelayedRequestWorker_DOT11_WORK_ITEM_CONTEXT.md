# Dot11DelayedRequestWorker(_DOT11_WORK_ITEM_CONTEXT *)

- ea: `0x140056e70`
- end: `0x140056fa9`
- name: `?Dot11DelayedRequestWorker@@YAXPEAU_DOT11_WORK_ITEM_CONTEXT@@@Z`
- size: `313`
- prototype: `void __fastcall(struct _DOT11_WORK_ITEM_CONTEXT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140020dc0`
- `0x140024944`
- `0x14003c800`
- `0x140056e70`
- `0x14009bbf0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056f36`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056f36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056f47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056f47`
- `NDIS!NdisAcquireRWLockWrite` at `0x140056e99`
- `NDIS!NdisAcquireRWLockWrite` at `0x140056e99`
- `NDIS!NdisReleaseRWLock` at `0x140056f68`
- `NDIS!NdisReleaseRWLock` at `0x140056f68`

## pseudocode

```c
void __fastcall Dot11DelayedRequestWorker(struct _DOT11_WORK_ITEM_CONTEXT *a1)
{
  struct _VELAN *v1; // rdi
  _LIST_ENTRY *p_WorkItemsList; // r14
  _LIST_ENTRY *Flink; // rsi
  _LIST_ENTRY *v4; // rax
  __int64 Blink_low; // rbx
  unsigned int v6; // edx
  struct _ADAPT *pAdapt; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp+8h] BYREF

  v1 = (struct _VELAN *)*((_QWORD *)a1 + 2);
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  NdisAcquireRWLockWrite(v1->pRWLock, &LockState, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_df7f430fb0d33aad844b51f0a6086e92_Traceguids,
      v1->WorkerRequestHandler.uWorkItemsQueued);
  p_WorkItemsList = &v1->WorkerRequestHandler.WorkItemsList;
  while ( 1 )
  {
    Flink = p_WorkItemsList->Flink;
    if ( p_WorkItemsList->Flink == p_WorkItemsList )
      break;
    if ( Flink->Blink != p_WorkItemsList || (v4 = Flink->Flink, Flink->Flink->Blink != Flink) )
      __fastfail(3u);
    p_WorkItemsList->Flink = v4;
    v4->Blink = p_WorkItemsList;
    Blink_low = SLODWORD(Flink[1].Blink);
    ((void (__fastcall *)(struct _VELAN *, struct _LOCK_STATE_EX *, _LIST_ENTRY **))Flink[2].Flink)(
      v1,
      &LockState,
      &Flink[2].Blink);
    --v1->WorkerRequestHandler.uWorkItemsQueued;
    --v1->WorkerRequestHandler.uWorkItemTypes[Blink_low];
    if ( Flink )
    {
      if ( Flink[-1].Flink )
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)Flink[-1].Flink, &Flink[-1]);
      else
        ExFreePoolWithTag(&Flink[-1], (ULONG)Flink[-1].Blink);
    }
  }
  NdisReleaseRWLock(v1->pRWLock, &LockState);
  pAdapt = v1->pAdapt;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&pAdapt->RefCount, 0xFFFFFFFF) == 1 )
    PtDestroyAdapter(pAdapt);
  if ( !_InterlockedDecrement((volatile signed __int32 *)&v1->RefCount) )
    PtDeallocateVElan(v1, v6);
}

```

## disassembly

```asm
0x140056e70  push    rbx
0x140056e72  push    rsi
0x140056e73  push    rdi
0x140056e74  push    r14
0x140056e76  sub     rsp, 28h
0x140056e7a  mov     rdi, [rcx+10h]
0x140056e7e  lea     rdx, [rsp+48h+LockState]; LockState
0x140056e83  xor     eax, eax
0x140056e85  mov     [rsp+48h+LockState.OldIrql], 0
0x140056e8a  mov     word ptr [rsp+48h+LockState.LockState], ax
0x140056e8f  xor     r8d, r8d; Flags
0x140056e92  mov     rcx, [rdi+90h]; Lock
0x140056e99  call    cs:__imp_NdisAcquireRWLockWrite
0x140056ea0  nop     dword ptr [rax+rax+00h]
0x140056ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x140056eac  lea     rax, WPP_GLOBAL_Control
0x140056eb3  cmp     rcx, rax
0x140056eb6  jz      short loc_140056ED4
0x140056eb8  mov     r9d, [rdi+1FD0h]
0x140056ebf  lea     r8, WPP_df7f430fb0d33aad844b51f0a6086e92_Traceguids
0x140056ec6  mov     rcx, [rcx+18h]
0x140056eca  mov     edx, 0Ah
0x140056ecf  call    WPP_SF_d
0x140056ed4  lea     r14, [rdi+1FC0h]
0x140056edb  mov     rsi, [r14]
0x140056ede  cmp     rsi, r14
0x140056ee1  jz      short loc_140056F5C
0x140056ee3  cmp     [rsi+8], r14
0x140056ee7  jnz     short loc_140056F55
0x140056ee9  mov     rax, [rsi]
0x140056eec  cmp     [rax+8], rsi
0x140056ef0  jnz     short loc_140056F55
0x140056ef2  mov     [r14], rax
0x140056ef5  lea     r8, [rsi+28h]
0x140056ef9  mov     [rax+8], r14
0x140056efd  lea     rdx, [rsp+48h+LockState]
0x140056f02  mov     rax, [rsi+20h]
0x140056f06  mov     rcx, rdi
0x140056f09  movsxd  rbx, dword ptr [rsi+18h]
0x140056f0d  call    _guard_dispatch_icall
0x140056f12  dec     dword ptr [rdi+1FD0h]
0x140056f18  dec     dword ptr [rdi+rbx*4+1FD4h]
0x140056f1f  test    rsi, rsi
0x140056f22  jz      short loc_140056EDB
0x140056f24  lea     rcx, [rsi-10h]; P
0x140056f28  mov     rax, [rcx]
0x140056f2b  test    rax, rax
0x140056f2e  jz      short loc_140056F44
0x140056f30  mov     rdx, rcx; Entry
0x140056f33  mov     rcx, rax; Lookaside
0x140056f36  call    cs:__imp_ExFreeToNPagedLookasideList
0x140056f3d  nop     dword ptr [rax+rax+00h]
0x140056f42  jmp     short loc_140056EDB
0x140056f44  mov     edx, [rcx+8]; Tag
0x140056f47  call    cs:__imp_ExFreePoolWithTag
0x140056f4e  nop     dword ptr [rax+rax+00h]
0x140056f53  jmp     short loc_140056EDB
0x140056f55  mov     ecx, 3
0x140056f5a  int     29h; Win8: RtlFailFast(ecx)
0x140056f5c  mov     rcx, [rdi+90h]; Lock
0x140056f63  lea     rdx, [rsp+48h+LockState]; LockState
0x140056f68  call    cs:__imp_NdisReleaseRWLock
0x140056f6f  nop     dword ptr [rax+rax+00h]
0x140056f74  mov     rcx, [rdi+10h]; struct _ADAPT *
0x140056f78  or      ebx, 0FFFFFFFFh
0x140056f7b  mov     eax, ebx
0x140056f7d  lock xadd [rcx+10h], eax
0x140056f82  add     eax, ebx
0x140056f84  jnz     short loc_140056F8B
0x140056f86  call    ?PtDestroyAdapter@@YAXPEAU_ADAPT@@@Z; PtDestroyAdapter(_ADAPT *)
0x140056f8b  mov     eax, ebx
0x140056f8d  lock xadd [rdi+1Ch], eax
0x140056f92  add     eax, ebx
0x140056f94  jnz     short loc_140056F9E
0x140056f96  mov     rcx, rdi; struct _VELAN *
0x140056f99  call    ?PtDeallocateVElan@@YAXPEAU_VELAN@@@Z; PtDeallocateVElan(_VELAN *)
0x140056f9e  add     rsp, 28h
0x140056fa2  pop     r14
0x140056fa4  pop     rdi
0x140056fa5  pop     rsi
0x140056fa6  pop     rbx
0x140056fa7  retn
```
