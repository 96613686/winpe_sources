# lldpTooManyNeighborsTimer

- ea: `0x140004720`
- end: `0x1400047bc`
- name: `lldpTooManyNeighborsTimer`
- size: `156`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003d80`
- `0x140004720`
- `0x140005d78`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x140004775`
- `NDIS!NdisReleaseRWLock` at `0x140004775`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000474a`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000474a`

## pseudocode

```c
void __fastcall lldpTooManyNeighborsTimer(
        struct _KDPC *Dpc,
        PNDIS_RW_LOCK_EX *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  char v5; // di
  __int64 v6; // rcx
  __int64 v7; // r8
  struct _LOCK_STATE_EX LockState; // [rsp+38h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v5 = 0;
  NdisAcquireRWLockWrite(DeferredContext[120], &LockState, 1u);
  if ( *((_BYTE *)DeferredContext + 216) )
  {
    *((_BYTE *)DeferredContext + 216) = 0;
    v5 = 1;
  }
  NdisReleaseRWLock(DeferredContext[120], &LockState);
  if ( v5 )
  {
    lldpQueueChangeNotificationEx(DeferredContext);
    if ( (BYTE1(WPP_MAIN_CB.SecurityDescriptor) & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer(v6, TooManyNeighborsEnd, v7, *((unsigned int *)DeferredContext + 32));
  }
}

```

## disassembly

```asm
0x140004720  mov     [rsp+arg_0], rbx
0x140004725  push    rdi
0x140004726  sub     rsp, 20h
0x14000472a  mov     rbx, rdx
0x14000472d  xor     eax, eax
0x14000472f  mov     r8b, 1; Flags
0x140004732  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x140004737  lea     rdx, [rsp+28h+LockState]; LockState
0x14000473c  mov     [rsp+28h+LockState.Flags], al
0x140004740  xor     dil, dil
0x140004743  mov     rcx, [rbx+3C0h]; Lock
0x14000474a  call    cs:__imp_NdisAcquireRWLockWrite
0x140004751  nop     dword ptr [rax+rax+00h]
0x140004756  cmp     [rbx+0D8h], dil
0x14000475d  jz      short loc_140004769
0x14000475f  mov     [rbx+0D8h], dil
0x140004766  mov     dil, 1
0x140004769  mov     rcx, [rbx+3C0h]; Lock
0x140004770  lea     rdx, [rsp+28h+LockState]; LockState
0x140004775  call    cs:__imp_NdisReleaseRWLock
0x14000477c  nop     dword ptr [rax+rax+00h]
0x140004781  test    dil, dil
0x140004784  jz      short loc_1400047B0
0x140004786  xor     edx, edx
0x140004788  mov     rcx, rbx; Context
0x14000478b  lea     r8d, [rdx+8]
0x14000478f  call    lldpQueueChangeNotificationEx
0x140004794  test    byte ptr cs:WPP_MAIN_CB.SecurityDescriptor+1, 1
0x14000479b  jz      short loc_1400047B0
0x14000479d  mov     r9d, [rbx+80h]
0x1400047a4  lea     rdx, TooManyNeighborsEnd
0x1400047ab  call    McTemplateK0q_EtwWriteTransfer
0x1400047b0  mov     rbx, [rsp+28h+arg_0]
0x1400047b5  add     rsp, 20h
0x1400047b9  pop     rdi
0x1400047ba  retn
```
