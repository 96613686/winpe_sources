# DrainQueuedPackets

- ea: `0x140003b58`
- end: `0x140003c10`
- name: `DrainQueuedPackets`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400018b0`

## callees

- `0x140002030`
- `0x140003b58`
- `0x140005ef0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003bd8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003bd8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003ba0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003bfa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003ba0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003bfa`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140003bb6`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140003bb6`

## pseudocode

```c
void __fastcall DrainQueuedPackets(__int64 a1)
{
  KSPIN_LOCK *v2; // rsi
  struct _NET_BUFFER_LIST *v3; // rbx
  KIRQL v4; // bp
  __int64 v5; // rcx

  v2 = (KSPIN_LOCK *)(a1 + 32);
LABEL_5:
  v4 = KeAcquireSpinLockRaiseToDpc(v2);
  while ( 1 )
  {
    v5 = *(_QWORD *)(a1 + 96);
    if ( !v5 )
      break;
    *(_QWORD *)(a1 + 96) = *(_QWORD *)v5;
    if ( !*(_BYTE *)(v5 + 8) )
    {
      v3 = (struct _NET_BUFFER_LIST *)(v5 - 96);
      *(_DWORD *)(v5 - 96 + 140) = -1073741823;
      KeReleaseSpinLock(v2, v4);
      NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(a1 + 40), v3, 0);
      DereferenceRefCount((char *)SstpGlobals + 144);
      goto LABEL_5;
    }
    (*((void (**)(void))SstpGlobals + 68))();
  }
  KeReleaseSpinLock(v2, v4);
}

```

## disassembly

```asm
0x140003b58  push    rbx
0x140003b5a  push    rbp
0x140003b5b  push    rsi
0x140003b5c  push    rdi
0x140003b5d  sub     rsp, 28h
0x140003b61  mov     rdi, rcx
0x140003b64  lea     rsi, [rcx+20h]
0x140003b68  jmp     short loc_140003BD5
0x140003b6a  mov     rdx, [rcx]
0x140003b6d  mov     [rdi+60h], rdx
0x140003b71  cmp     byte ptr [rcx+8], 0
0x140003b75  jz      short loc_140003B8C
0x140003b77  mov     rax, cs:SstpGlobals
0x140003b7e  mov     rax, [rax+220h]
0x140003b85  call    _guard_dispatch_icall
0x140003b8a  jmp     short loc_140003BE7
0x140003b8c  lea     rbx, [rcx-60h]
0x140003b90  mov     dl, bpl; NewIrql
0x140003b93  mov     rcx, rsi; SpinLock
0x140003b96  mov     dword ptr [rbx+8Ch], 0C0000001h
0x140003ba0  call    cs:__imp_KeReleaseSpinLock
0x140003ba7  nop     dword ptr [rax+rax+00h]
0x140003bac  mov     rcx, [rdi+28h]; NdisVcHandle
0x140003bb0  xor     r8d, r8d; SendCompleteFlags
0x140003bb3  mov     rdx, rbx; NetBufferLists
0x140003bb6  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x140003bbd  nop     dword ptr [rax+rax+00h]
0x140003bc2  mov     rcx, cs:SstpGlobals
0x140003bc9  add     rcx, 90h
0x140003bd0  call    DereferenceRefCount
0x140003bd5  mov     rcx, rsi; SpinLock
0x140003bd8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003bdf  nop     dword ptr [rax+rax+00h]
0x140003be4  mov     bpl, al
0x140003be7  mov     rcx, [rdi+60h]
0x140003beb  test    rcx, rcx
0x140003bee  jnz     loc_140003B6A
0x140003bf4  mov     dl, bpl; NewIrql
0x140003bf7  mov     rcx, rsi; SpinLock
0x140003bfa  call    cs:__imp_KeReleaseSpinLock
0x140003c01  nop     dword ptr [rax+rax+00h]
0x140003c06  add     rsp, 28h
0x140003c0a  pop     rdi
0x140003c0b  pop     rsi
0x140003c0c  pop     rbp
0x140003c0d  pop     rbx
0x140003c0e  retn
```
