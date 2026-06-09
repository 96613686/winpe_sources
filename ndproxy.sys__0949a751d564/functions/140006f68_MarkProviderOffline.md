# MarkProviderOffline

- ea: `0x140006f68`
- end: `0x140007037`
- name: `MarkProviderOffline`
- size: `207`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001030`
- `0x1400011b0`
- `0x140003940`

## callees

- `0x140006f68`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006fca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006fca`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006fff`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006fff`
- `NDIS!NdisReleaseRWLock` at `0x140007021`
- `NDIS!NdisReleaseRWLock` at `0x140007021`
- `NDIS!NdisAcquireRWLockRead` at `0x140006f9d`
- `NDIS!NdisAcquireRWLockRead` at `0x140006f9d`

## pseudocode

```c
void __fastcall MarkProviderOffline(__int64 a1)
{
  __int64 i; // rdi
  struct _SINGLE_LIST_ENTRY *Next; // rbx
  KIRQL v4; // al
  KIRQL v5; // dl
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp+8h] BYREF

  *(_DWORD *)(a1 + 16) = 1;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState, 0);
  for ( i = 0; (unsigned int)i < *((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1); i = (unsigned int)(i + 1) )
  {
    Next = WPP_MAIN_CB.Dpc.DpcListEntry.Next[i].Next;
    if ( Next )
    {
      v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&Next[15]);
      LOBYTE(Next[16].Next) = v4;
      if ( Next[3].Next == (struct _SINGLE_LIST_ENTRY *)a1 )
      {
        LODWORD(Next[10].Next[7].Next) &= ~4u;
        v5 = (KIRQL)Next[16].Next;
        Next[7].Next = 0;
      }
      else
      {
        v5 = v4;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)&Next[15], v5);
    }
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState);
}

```

## disassembly

```asm
0x140006f68  push    rbx
0x140006f6a  push    rbp
0x140006f6b  push    rsi
0x140006f6c  push    rdi
0x140006f6d  sub     rsp, 28h
0x140006f71  xor     eax, eax
0x140006f73  mov     dword ptr [rcx+10h], 1
0x140006f7a  mov     [rcx+20h], rax
0x140006f7e  lea     rdx, [rsp+48h+LockState]; LockState
0x140006f83  mov     [rcx+18h], rax
0x140006f87  mov     rbp, rcx
0x140006f8a  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x140006f91  xor     r8d, r8d; Flags
0x140006f94  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x140006f99  mov     [rsp+48h+LockState.Flags], al
0x140006f9d  call    cs:__imp_NdisAcquireRWLockRead
0x140006fa4  nop     dword ptr [rax+rax+00h]
0x140006fa9  xor     edi, edi
0x140006fab  cmp     dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h+4, edi
0x140006fb1  jz      short loc_140007015
0x140006fb3  mov     rax, cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next
0x140006fba  mov     rbx, [rax+rdi*8]
0x140006fbe  test    rbx, rbx
0x140006fc1  jz      short loc_14000700B
0x140006fc3  lea     rsi, [rbx+78h]
0x140006fc7  mov     rcx, rsi; SpinLock
0x140006fca  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006fd1  nop     dword ptr [rax+rax+00h]
0x140006fd6  mov     rcx, rsi; SpinLock
0x140006fd9  mov     [rbx+80h], al
0x140006fdf  cmp     [rbx+18h], rbp
0x140006fe3  jnz     short loc_140006FFD
0x140006fe5  mov     rax, [rbx+50h]
0x140006fe9  and     dword ptr [rax+38h], 0FFFFFFFBh
0x140006fed  mov     dl, [rbx+80h]
0x140006ff3  mov     qword ptr [rbx+38h], 0
0x140006ffb  jmp     short loc_140006FFF
0x140006ffd  mov     dl, al; NewIrql
0x140006fff  call    cs:__imp_KeReleaseSpinLock
0x140007006  nop     dword ptr [rax+rax+00h]
0x14000700b  inc     edi
0x14000700d  cmp     edi, dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h+4
0x140007013  jb      short loc_140006FB3
0x140007015  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x14000701c  lea     rdx, [rsp+48h+LockState]; LockState
0x140007021  call    cs:__imp_NdisReleaseRWLock
0x140007028  nop     dword ptr [rax+rax+00h]
0x14000702d  add     rsp, 28h
0x140007031  pop     rdi
0x140007032  pop     rsi
0x140007033  pop     rbp
0x140007034  pop     rbx
0x140007035  retn
```
