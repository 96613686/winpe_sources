# ClearSapWithTapiLine

- ea: `0x140006b68`
- end: `0x140006c16`
- name: `ClearSapWithTapiLine`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400011b0`
- `0x140003940`

## callees

- `0x140006b68`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006bb8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006bb8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006bde`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006bde`
- `NDIS!NdisReleaseRWLock` at `0x140006c00`
- `NDIS!NdisReleaseRWLock` at `0x140006c00`
- `NDIS!NdisAcquireRWLockRead` at `0x140006b8e`
- `NDIS!NdisAcquireRWLockRead` at `0x140006b8e`

## pseudocode

```c
void __fastcall ClearSapWithTapiLine(struct _SINGLE_LIST_ENTRY *a1)
{
  __int64 i; // rbx
  struct _SINGLE_LIST_ENTRY *Next; // rdi
  KIRQL v4; // al
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF

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
      if ( Next[8].Next == a1 )
        Next[8].Next = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)&Next[15], v4);
    }
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState);
}

```

## disassembly

```asm
0x140006b68  push    rbx
0x140006b6a  push    rbp
0x140006b6b  push    rsi
0x140006b6c  push    rdi
0x140006b6d  sub     rsp, 28h
0x140006b71  xor     eax, eax
0x140006b73  lea     rdx, [rsp+48h+LockState]; LockState
0x140006b78  mov     rbp, rcx
0x140006b7b  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x140006b80  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x140006b87  xor     r8d, r8d; Flags
0x140006b8a  mov     [rsp+48h+LockState.Flags], al
0x140006b8e  call    cs:__imp_NdisAcquireRWLockRead
0x140006b95  nop     dword ptr [rax+rax+00h]
0x140006b9a  xor     ebx, ebx
0x140006b9c  cmp     dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h+4, ebx
0x140006ba2  jz      short loc_140006BF4
0x140006ba4  mov     rax, cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next
0x140006bab  mov     rdi, [rax+rbx*8]
0x140006baf  test    rdi, rdi
0x140006bb2  jz      short loc_140006BEA
0x140006bb4  lea     rcx, [rdi+78h]; SpinLock
0x140006bb8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006bbf  nop     dword ptr [rax+rax+00h]
0x140006bc4  mov     [rdi+80h], al
0x140006bca  cmp     [rdi+40h], rbp
0x140006bce  jnz     short loc_140006BD8
0x140006bd0  mov     qword ptr [rdi+40h], 0
0x140006bd8  mov     dl, al; NewIrql
0x140006bda  lea     rcx, [rdi+78h]; SpinLock
0x140006bde  call    cs:__imp_KeReleaseSpinLock
0x140006be5  nop     dword ptr [rax+rax+00h]
0x140006bea  inc     ebx
0x140006bec  cmp     ebx, dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h+4
0x140006bf2  jb      short loc_140006BA4
0x140006bf4  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x140006bfb  lea     rdx, [rsp+48h+LockState]; LockState
0x140006c00  call    cs:__imp_NdisReleaseRWLock
0x140006c07  nop     dword ptr [rax+rax+00h]
0x140006c0c  add     rsp, 28h
0x140006c10  pop     rdi
0x140006c11  pop     rsi
0x140006c12  pop     rbp
0x140006c13  pop     rbx
0x140006c14  retn
```
