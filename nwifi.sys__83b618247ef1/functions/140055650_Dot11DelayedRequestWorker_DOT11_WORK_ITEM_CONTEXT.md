# Dot11DelayedRequestWorker(_DOT11_WORK_ITEM_CONTEXT *)

- ea: `0x140055650`
- end: `0x140055789`
- name: `?Dot11DelayedRequestWorker@@YAXPEAU_DOT11_WORK_ITEM_CONTEXT@@@Z`
- size: `313`
- prototype: `void __fastcall(struct _DOT11_WORK_ITEM_CONTEXT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140020dc0`
- `0x140024944`
- `0x14003c5e0`
- `0x140055650`
- `0x14009a410`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140055716`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140055716`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055727`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055727`
- `NDIS!NdisAcquireRWLockWrite` at `0x140055679`
- `NDIS!NdisAcquireRWLockWrite` at `0x140055679`
- `NDIS!NdisReleaseRWLock` at `0x140055748`
- `NDIS!NdisReleaseRWLock` at `0x140055748`

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
0x140055650  push    rbx
0x140055652  push    rsi
0x140055653  push    rdi
0x140055654  push    r14
0x140055656  sub     rsp, 28h
0x14005565a  mov     rdi, [rcx+10h]
0x14005565e  lea     rdx, [rsp+48h+LockState]; LockState
0x140055663  xor     eax, eax
0x140055665  mov     [rsp+48h+LockState.OldIrql], 0
0x14005566a  mov     word ptr [rsp+48h+LockState.LockState], ax
0x14005566f  xor     r8d, r8d; Flags
0x140055672  mov     rcx, [rdi+90h]; Lock
0x140055679  call    cs:__imp_NdisAcquireRWLockWrite
0x140055680  nop     dword ptr [rax+rax+00h]
0x140055685  mov     rcx, cs:WPP_GLOBAL_Control
0x14005568c  lea     rax, WPP_GLOBAL_Control
0x140055693  cmp     rcx, rax
0x140055696  jz      short loc_1400556B4
0x140055698  mov     r9d, [rdi+1FD0h]
0x14005569f  lea     r8, WPP_df7f430fb0d33aad844b51f0a6086e92_Traceguids
0x1400556a6  mov     rcx, [rcx+18h]
0x1400556aa  mov     edx, 0Ah
0x1400556af  call    WPP_SF_d
0x1400556b4  lea     r14, [rdi+1FC0h]
0x1400556bb  mov     rsi, [r14]
0x1400556be  cmp     rsi, r14
0x1400556c1  jz      short loc_14005573C
0x1400556c3  cmp     [rsi+8], r14
0x1400556c7  jnz     short loc_140055735
0x1400556c9  mov     rax, [rsi]
0x1400556cc  cmp     [rax+8], rsi
0x1400556d0  jnz     short loc_140055735
0x1400556d2  mov     [r14], rax
0x1400556d5  lea     r8, [rsi+28h]
0x1400556d9  mov     [rax+8], r14
0x1400556dd  lea     rdx, [rsp+48h+LockState]
0x1400556e2  mov     rax, [rsi+20h]
0x1400556e6  mov     rcx, rdi
0x1400556e9  movsxd  rbx, dword ptr [rsi+18h]
0x1400556ed  call    _guard_dispatch_icall
0x1400556f2  dec     dword ptr [rdi+1FD0h]
0x1400556f8  dec     dword ptr [rdi+rbx*4+1FD4h]
0x1400556ff  test    rsi, rsi
0x140055702  jz      short loc_1400556BB
0x140055704  lea     rcx, [rsi-10h]; P
0x140055708  mov     rax, [rcx]
0x14005570b  test    rax, rax
0x14005570e  jz      short loc_140055724
0x140055710  mov     rdx, rcx; Entry
0x140055713  mov     rcx, rax; Lookaside
0x140055716  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005571d  nop     dword ptr [rax+rax+00h]
0x140055722  jmp     short loc_1400556BB
0x140055724  mov     edx, [rcx+8]; Tag
0x140055727  call    cs:__imp_ExFreePoolWithTag
0x14005572e  nop     dword ptr [rax+rax+00h]
0x140055733  jmp     short loc_1400556BB
0x140055735  mov     ecx, 3
0x14005573a  int     29h; Win8: RtlFailFast(ecx)
0x14005573c  mov     rcx, [rdi+90h]; Lock
0x140055743  lea     rdx, [rsp+48h+LockState]; LockState
0x140055748  call    cs:__imp_NdisReleaseRWLock
0x14005574f  nop     dword ptr [rax+rax+00h]
0x140055754  mov     rcx, [rdi+10h]; struct _ADAPT *
0x140055758  or      ebx, 0FFFFFFFFh
0x14005575b  mov     eax, ebx
0x14005575d  lock xadd [rcx+10h], eax
0x140055762  add     eax, ebx
0x140055764  jnz     short loc_14005576B
0x140055766  call    ?PtDestroyAdapter@@YAXPEAU_ADAPT@@@Z; PtDestroyAdapter(_ADAPT *)
0x14005576b  mov     eax, ebx
0x14005576d  lock xadd [rdi+1Ch], eax
0x140055772  add     eax, ebx
0x140055774  jnz     short loc_14005577E
0x140055776  mov     rcx, rdi; struct _VELAN *
0x140055779  call    ?PtDeallocateVElan@@YAXPEAU_VELAN@@@Z; PtDeallocateVElan(_VELAN *)
0x14005577e  add     rsp, 28h
0x140055782  pop     r14
0x140055784  pop     rdi
0x140055785  pop     rsi
0x140055786  pop     rbx
0x140055787  retn
```
