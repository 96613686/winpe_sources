# ExtSTADelayedSendMicFailureReport(_DEVICE_OBJECT *,EXTSTA_SEND_MIC_FAILURE_REPORT_WORKITEM *)

- ea: `0x14005d660`
- end: `0x14005d759`
- name: `?ExtSTADelayedSendMicFailureReport@@YAXPEAU_DEVICE_OBJECT@@PEAUEXTSTA_SEND_MIC_FAILURE_REPORT_WORKITEM@@@Z`
- size: `249`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140024944`
- `0x14005d660`
- `0x14005d9d4`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005d71d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005d71d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d72e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d72e`
- `ntoskrnl!IoUninitializeWorkItem` at `0x14005d6ff`
- `ntoskrnl!IoUninitializeWorkItem` at `0x14005d6ff`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005d691`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005d691`
- `NDIS!NdisReleaseRWLock` at `0x14005d6ef`
- `NDIS!NdisReleaseRWLock` at `0x14005d6ef`

## pseudocode

```c
void __fastcall ExtSTADelayedSendMicFailureReport(PDEVICE_OBJECT DeviceObject, char *Context)
{
  __int64 v2; // rbx
  struct DOT11_MAC_STATE_ENTRY *v3; // rdi
  int v5; // ebp
  __int64 v6; // r9
  __int64 v7; // rcx
  unsigned int v8; // edx
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF

  v2 = *(_QWORD *)Context;
  v3 = (struct DOT11_MAC_STATE_ENTRY *)*((_QWORD *)Context + 1);
  v5 = *((_DWORD *)Context + 4);
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v2 + 144), &LockState, 0);
  v6 = *(_QWORD *)(v2 + 8040);
  if ( v6 )
  {
    if ( *(struct DOT11_DRIVER **)(v2 + 152) == &ExtSTA )
    {
      v7 = *(_QWORD *)(v6 + 416);
      if ( v7 != v6 + 416 && *(struct DOT11_MAC_STATE_ENTRY **)(v7 + 16) == v3 && v3->pTkipMicFailureInfo )
        ExtSTASendMicFailureReport(*(struct EXTSTA_VELAN **)(v2 + 8040), v3, v5);
    }
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v2 + 144), &LockState);
  IoUninitializeWorkItem(*((PIO_WORKITEM *)Context + 3));
  if ( *((_QWORD *)Context - 2) )
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)Context - 2), Context - 16);
  else
    ExFreePoolWithTag(Context - 16, *((_DWORD *)Context - 2));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 28), 0xFFFFFFFF) == 1 )
    PtDeallocateVElan((struct _VELAN *)v2, v8);
}

```

## disassembly

```asm
0x14005d660  push    rbx
0x14005d662  push    rbp
0x14005d663  push    rsi
0x14005d664  push    rdi
0x14005d665  sub     rsp, 28h
0x14005d669  mov     rbx, [rdx]
0x14005d66c  xor     eax, eax
0x14005d66e  mov     rdi, [rdx+8]
0x14005d672  mov     rsi, rdx
0x14005d675  mov     ebp, [rdx+10h]
0x14005d678  xor     r8d, r8d; Flags
0x14005d67b  mov     [rsp+48h+LockState.OldIrql], 0
0x14005d680  lea     rdx, [rsp+48h+LockState]; LockState
0x14005d685  mov     word ptr [rsp+48h+LockState.LockState], ax
0x14005d68a  mov     rcx, [rbx+90h]; Lock
0x14005d691  call    cs:__imp_NdisAcquireRWLockWrite
0x14005d698  nop     dword ptr [rax+rax+00h]
0x14005d69d  mov     r9, [rbx+1F68h]
0x14005d6a4  test    r9, r9
0x14005d6a7  jz      short loc_14005D6E3
0x14005d6a9  lea     rax, ?ExtSTA@@3UDOT11_DRIVER@@A; DOT11_DRIVER ExtSTA
0x14005d6b0  cmp     [rbx+98h], rax
0x14005d6b7  jnz     short loc_14005D6E3
0x14005d6b9  lea     rax, [r9+1A0h]
0x14005d6c0  mov     rcx, [rax]
0x14005d6c3  cmp     rcx, rax
0x14005d6c6  jz      short loc_14005D6E3
0x14005d6c8  cmp     [rcx+10h], rdi
0x14005d6cc  jnz     short loc_14005D6E3
0x14005d6ce  cmp     qword ptr [rdi+70h], 0
0x14005d6d3  jz      short loc_14005D6E3
0x14005d6d5  mov     r8d, ebp; int
0x14005d6d8  mov     rdx, rdi; struct DOT11_MAC_STATE_ENTRY *
0x14005d6db  mov     rcx, r9; struct EXTSTA_VELAN *
0x14005d6de  call    ?ExtSTASendMicFailureReport@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@H@Z; ExtSTASendMicFailureReport(EXTSTA_VELAN *,DOT11_MAC_STATE_ENTRY *,int)
0x14005d6e3  mov     rcx, [rbx+90h]; Lock
0x14005d6ea  lea     rdx, [rsp+48h+LockState]; LockState
0x14005d6ef  call    cs:__imp_NdisReleaseRWLock
0x14005d6f6  nop     dword ptr [rax+rax+00h]
0x14005d6fb  mov     rcx, [rsi+18h]; IoWorkItem
0x14005d6ff  call    cs:__imp_IoUninitializeWorkItem
0x14005d706  nop     dword ptr [rax+rax+00h]
0x14005d70b  lea     rcx, [rsi-10h]; P
0x14005d70f  mov     rax, [rcx]
0x14005d712  test    rax, rax
0x14005d715  jz      short loc_14005D72B
0x14005d717  mov     rdx, rcx; Entry
0x14005d71a  mov     rcx, rax; Lookaside
0x14005d71d  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005d724  nop     dword ptr [rax+rax+00h]
0x14005d729  jmp     short loc_14005D73A
0x14005d72b  mov     edx, [rcx+8]; Tag
0x14005d72e  call    cs:__imp_ExFreePoolWithTag
0x14005d735  nop     dword ptr [rax+rax+00h]
0x14005d73a  or      eax, 0FFFFFFFFh
0x14005d73d  lock xadd [rbx+1Ch], eax
0x14005d742  cmp     eax, 1
0x14005d745  jnz     short loc_14005D74F
0x14005d747  mov     rcx, rbx; struct _VELAN *
0x14005d74a  call    ?PtDeallocateVElan@@YAXPEAU_VELAN@@@Z; PtDeallocateVElan(_VELAN *)
0x14005d74f  add     rsp, 28h
0x14005d753  pop     rdi
0x14005d754  pop     rsi
0x14005d755  pop     rbp
0x14005d756  pop     rbx
0x14005d757  retn
```
