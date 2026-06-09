# MarkProviderDisconnected

- ea: `0x14001152c`
- end: `0x1400115de`
- name: `MarkProviderDisconnected`
- size: `178`
- prototype: `void __fastcall(struct _SINGLE_LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004ad0`

## callees

- `0x14001152c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001157c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001157c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400115a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400115a6`
- `NDIS!NdisReleaseRWLock` at `0x1400115c8`
- `NDIS!NdisReleaseRWLock` at `0x1400115c8`
- `NDIS!NdisAcquireRWLockRead` at `0x140011552`
- `NDIS!NdisAcquireRWLockRead` at `0x140011552`

## pseudocode

```c
void __fastcall MarkProviderDisconnected(struct _SINGLE_LIST_ENTRY *a1)
{
  __int64 i; // rdi
  struct _SINGLE_LIST_ENTRY *Next; // rbx
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState, 0);
  for ( i = 0; (unsigned int)i < *((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1); i = (unsigned int)(i + 1) )
  {
    Next = WPP_MAIN_CB.Dpc.DpcListEntry.Next[i].Next;
    if ( Next )
    {
      LOBYTE(Next[16].Next) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&Next[15]);
      if ( Next[3].Next == a1 )
        LODWORD(Next[10].Next[7].Next) &= ~1u;
      KeReleaseSpinLock((PKSPIN_LOCK)&Next[15], (KIRQL)Next[16].Next);
    }
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState);
}

```

## disassembly

```asm
0x14001152c  push    rbx
0x14001152e  push    rbp
0x14001152f  push    rsi
0x140011530  push    rdi
0x140011531  sub     rsp, 28h
0x140011535  xor     eax, eax
0x140011537  lea     rdx, [rsp+48h+LockState]; LockState
0x14001153c  mov     rbp, rcx
0x14001153f  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x140011544  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x14001154b  xor     r8d, r8d; Flags
0x14001154e  mov     [rsp+48h+LockState.Flags], al
0x140011552  call    cs:__imp_NdisAcquireRWLockRead
0x140011559  nop     dword ptr [rax+rax+00h]
0x14001155e  xor     edi, edi
0x140011560  cmp     dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h+4, edi
0x140011566  jz      short loc_1400115BC
0x140011568  mov     rax, cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next
0x14001156f  mov     rbx, [rax+rdi*8]
0x140011573  test    rbx, rbx
0x140011576  jz      short loc_1400115B2
0x140011578  lea     rcx, [rbx+78h]; SpinLock
0x14001157c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011583  nop     dword ptr [rax+rax+00h]
0x140011588  mov     [rbx+80h], al
0x14001158e  cmp     [rbx+18h], rbp
0x140011592  jnz     short loc_14001159C
0x140011594  mov     rax, [rbx+50h]
0x140011598  and     dword ptr [rax+38h], 0FFFFFFFEh
0x14001159c  mov     dl, [rbx+80h]; NewIrql
0x1400115a2  lea     rcx, [rbx+78h]; SpinLock
0x1400115a6  call    cs:__imp_KeReleaseSpinLock
0x1400115ad  nop     dword ptr [rax+rax+00h]
0x1400115b2  inc     edi
0x1400115b4  cmp     edi, dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h+4
0x1400115ba  jb      short loc_140011568
0x1400115bc  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x1400115c3  lea     rdx, [rsp+48h+LockState]; LockState
0x1400115c8  call    cs:__imp_NdisReleaseRWLock
0x1400115cf  nop     dword ptr [rax+rax+00h]
0x1400115d4  add     rsp, 28h
0x1400115d8  pop     rdi
0x1400115d9  pop     rsi
0x1400115da  pop     rbp
0x1400115db  pop     rbx
0x1400115dc  retn
```
