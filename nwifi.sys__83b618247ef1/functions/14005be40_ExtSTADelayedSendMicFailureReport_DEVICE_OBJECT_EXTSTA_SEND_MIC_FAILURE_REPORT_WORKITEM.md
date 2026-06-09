# ExtSTADelayedSendMicFailureReport(_DEVICE_OBJECT *,EXTSTA_SEND_MIC_FAILURE_REPORT_WORKITEM *)

- ea: `0x14005be40`
- end: `0x14005bf39`
- name: `?ExtSTADelayedSendMicFailureReport@@YAXPEAU_DEVICE_OBJECT@@PEAUEXTSTA_SEND_MIC_FAILURE_REPORT_WORKITEM@@@Z`
- size: `249`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140024944`
- `0x14005be40`
- `0x14005c1b4`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005befd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005befd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005bf0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005bf0e`
- `ntoskrnl!IoUninitializeWorkItem` at `0x14005bedf`
- `ntoskrnl!IoUninitializeWorkItem` at `0x14005bedf`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005be71`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005be71`
- `NDIS!NdisReleaseRWLock` at `0x14005becf`
- `NDIS!NdisReleaseRWLock` at `0x14005becf`

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
0x14005be40  push    rbx
0x14005be42  push    rbp
0x14005be43  push    rsi
0x14005be44  push    rdi
0x14005be45  sub     rsp, 28h
0x14005be49  mov     rbx, [rdx]
0x14005be4c  xor     eax, eax
0x14005be4e  mov     rdi, [rdx+8]
0x14005be52  mov     rsi, rdx
0x14005be55  mov     ebp, [rdx+10h]
0x14005be58  xor     r8d, r8d; Flags
0x14005be5b  mov     [rsp+48h+LockState.OldIrql], 0
0x14005be60  lea     rdx, [rsp+48h+LockState]; LockState
0x14005be65  mov     word ptr [rsp+48h+LockState.LockState], ax
0x14005be6a  mov     rcx, [rbx+90h]; Lock
0x14005be71  call    cs:__imp_NdisAcquireRWLockWrite
0x14005be78  nop     dword ptr [rax+rax+00h]
0x14005be7d  mov     r9, [rbx+1F68h]
0x14005be84  test    r9, r9
0x14005be87  jz      short loc_14005BEC3
0x14005be89  lea     rax, ?ExtSTA@@3UDOT11_DRIVER@@A; DOT11_DRIVER ExtSTA
0x14005be90  cmp     [rbx+98h], rax
0x14005be97  jnz     short loc_14005BEC3
0x14005be99  lea     rax, [r9+1A0h]
0x14005bea0  mov     rcx, [rax]
0x14005bea3  cmp     rcx, rax
0x14005bea6  jz      short loc_14005BEC3
0x14005bea8  cmp     [rcx+10h], rdi
0x14005beac  jnz     short loc_14005BEC3
0x14005beae  cmp     qword ptr [rdi+70h], 0
0x14005beb3  jz      short loc_14005BEC3
0x14005beb5  mov     r8d, ebp; int
0x14005beb8  mov     rdx, rdi; struct DOT11_MAC_STATE_ENTRY *
0x14005bebb  mov     rcx, r9; struct EXTSTA_VELAN *
0x14005bebe  call    ?ExtSTASendMicFailureReport@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@H@Z; ExtSTASendMicFailureReport(EXTSTA_VELAN *,DOT11_MAC_STATE_ENTRY *,int)
0x14005bec3  mov     rcx, [rbx+90h]; Lock
0x14005beca  lea     rdx, [rsp+48h+LockState]; LockState
0x14005becf  call    cs:__imp_NdisReleaseRWLock
0x14005bed6  nop     dword ptr [rax+rax+00h]
0x14005bedb  mov     rcx, [rsi+18h]; IoWorkItem
0x14005bedf  call    cs:__imp_IoUninitializeWorkItem
0x14005bee6  nop     dword ptr [rax+rax+00h]
0x14005beeb  lea     rcx, [rsi-10h]; P
0x14005beef  mov     rax, [rcx]
0x14005bef2  test    rax, rax
0x14005bef5  jz      short loc_14005BF0B
0x14005bef7  mov     rdx, rcx; Entry
0x14005befa  mov     rcx, rax; Lookaside
0x14005befd  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005bf04  nop     dword ptr [rax+rax+00h]
0x14005bf09  jmp     short loc_14005BF1A
0x14005bf0b  mov     edx, [rcx+8]; Tag
0x14005bf0e  call    cs:__imp_ExFreePoolWithTag
0x14005bf15  nop     dword ptr [rax+rax+00h]
0x14005bf1a  or      eax, 0FFFFFFFFh
0x14005bf1d  lock xadd [rbx+1Ch], eax
0x14005bf22  cmp     eax, 1
0x14005bf25  jnz     short loc_14005BF2F
0x14005bf27  mov     rcx, rbx; struct _VELAN *
0x14005bf2a  call    ?PtDeallocateVElan@@YAXPEAU_VELAN@@@Z; PtDeallocateVElan(_VELAN *)
0x14005bf2f  add     rsp, 28h
0x14005bf33  pop     rdi
0x14005bf34  pop     rsi
0x14005bf35  pop     rbp
0x14005bf36  pop     rbx
0x14005bf37  retn
```
