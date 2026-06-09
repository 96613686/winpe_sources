# MarkProviderConnected

- ea: `0x140011474`
- end: `0x140011526`
- name: `MarkProviderConnected`
- size: `178`
- prototype: `void __fastcall(struct _SINGLE_LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004ad0`

## callees

- `0x140011474`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400114c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400114c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400114ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400114ee`
- `NDIS!NdisReleaseRWLock` at `0x140011510`
- `NDIS!NdisReleaseRWLock` at `0x140011510`
- `NDIS!NdisAcquireRWLockRead` at `0x14001149a`
- `NDIS!NdisAcquireRWLockRead` at `0x14001149a`

## pseudocode

```c
void __fastcall MarkProviderConnected(struct _SINGLE_LIST_ENTRY *a1)
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
        LODWORD(Next[10].Next[7].Next) |= 1u;
      KeReleaseSpinLock((PKSPIN_LOCK)&Next[15], (KIRQL)Next[16].Next);
    }
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState);
}

```

## disassembly

```asm
0x140011474  push    rbx
0x140011476  push    rbp
0x140011477  push    rsi
0x140011478  push    rdi
0x140011479  sub     rsp, 28h
0x14001147d  xor     eax, eax
0x14001147f  lea     rdx, [rsp+48h+LockState]; LockState
0x140011484  mov     rbp, rcx
0x140011487  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x14001148c  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x140011493  xor     r8d, r8d; Flags
0x140011496  mov     [rsp+48h+LockState.Flags], al
0x14001149a  call    cs:__imp_NdisAcquireRWLockRead
0x1400114a1  nop     dword ptr [rax+rax+00h]
0x1400114a6  xor     edi, edi
0x1400114a8  cmp     dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h+4, edi
0x1400114ae  jz      short loc_140011504
0x1400114b0  mov     rax, cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next
0x1400114b7  mov     rbx, [rax+rdi*8]
0x1400114bb  test    rbx, rbx
0x1400114be  jz      short loc_1400114FA
0x1400114c0  lea     rcx, [rbx+78h]; SpinLock
0x1400114c4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400114cb  nop     dword ptr [rax+rax+00h]
0x1400114d0  mov     [rbx+80h], al
0x1400114d6  cmp     [rbx+18h], rbp
0x1400114da  jnz     short loc_1400114E4
0x1400114dc  mov     rax, [rbx+50h]
0x1400114e0  or      dword ptr [rax+38h], 1
0x1400114e4  mov     dl, [rbx+80h]; NewIrql
0x1400114ea  lea     rcx, [rbx+78h]; SpinLock
0x1400114ee  call    cs:__imp_KeReleaseSpinLock
0x1400114f5  nop     dword ptr [rax+rax+00h]
0x1400114fa  inc     edi
0x1400114fc  cmp     edi, dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h+4
0x140011502  jb      short loc_1400114B0
0x140011504  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x14001150b  lea     rdx, [rsp+48h+LockState]; LockState
0x140011510  call    cs:__imp_NdisReleaseRWLock
0x140011517  nop     dword ptr [rax+rax+00h]
0x14001151c  add     rsp, 28h
0x140011520  pop     rdi
0x140011521  pop     rsi
0x140011522  pop     rbp
0x140011523  pop     rbx
0x140011524  retn
```
