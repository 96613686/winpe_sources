# DropQoSSendNetBufferList

- ea: `0x140008e5c`
- end: `0x140008f8a`
- name: `DropQoSSendNetBufferList`
- size: `302`
- prototype: `__int64 __fastcall(PNET_BUFFER_LIST NetBufferList)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140001be0`
- `0x1400112d0`

## callees

- `0x1400035f0`
- `0x140005494`
- `0x140008e5c`
- `0x14002e898`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140008f46`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008f46`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008f1f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008f1f`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140008ed4`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140008ed4`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140008efb`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140008efb`
- `NDIS!NdisFreeNetBufferListContext` at `0x140008eaf`
- `NDIS!NdisFreeNetBufferListContext` at `0x140008eaf`

## pseudocode

```c
void __fastcall DropQoSSendNetBufferList(PNET_BUFFER_LIST NetBufferList)
{
  PNET_BUFFER_LIST Alignment; // rsi
  SLIST_HEADER *v2; // rax
  struct _NET_BUFFER_LIST *v3; // rbp
  PNET_BUFFER_LIST_CONTEXT Context; // rcx
  __int64 Offset; // rax
  __int64 v6; // r15
  __int64 v7; // rbx
  __int64 v8; // r14
  __int64 v9; // rdi
  KIRQL v10; // al
  bool v11; // zf

  if ( NetBufferList )
  {
    Alignment = NetBufferList;
    do
    {
      v2 = (SLIST_HEADER *)Alignment;
      v3 = Alignment;
      Alignment = (PNET_BUFFER_LIST)Alignment->Link.Alignment;
      Context = v3->Context;
      v2->Alignment = 0;
      Offset = Context->Offset;
      v6 = *(_QWORD *)&Context->ContextData[Offset + 48];
      v7 = *(_QWORD *)&Context->ContextData[Offset + 72];
      v8 = *(_QWORD *)&Context->ContextData[Offset + 64];
      v9 = *(_QWORD *)&Context->ContextData[Offset + 56];
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 1752));
      NdisFreeNetBufferListContext(v3, 0x80u);
      v3->Status = -1073741823;
      if ( v7 )
      {
        NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(v7 + 40), v3, 0);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 24), 0xFFFFFFFF) == 1 )
          DoDerefCmVcCBWork(v7);
      }
      else
      {
        NdisMSendNetBufferListsComplete(*(NDIS_HANDLE *)(v8 + 40), v3, 0);
      }
      DereferenceRefCount(v6 + 24);
      if ( v9 )
      {
        v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v9 + 1768));
        v11 = (*(_DWORD *)(v9 + 24))-- == 1;
        *(_BYTE *)(v9 + 1776) = v10;
        if ( v11 )
          DoDerefBundleCBWork((PVOID)v9);
        else
          KeReleaseSpinLock((PKSPIN_LOCK)(v9 + 1768), v10);
      }
      if ( v7 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 24), 0xFFFFFFFF) == 1 )
          DoDerefCmVcCBWork(v7);
      }
      _InterlockedIncrement(&glSendCompleteCount);
    }
    while ( Alignment );
  }
}

```

## disassembly

```asm
0x140008e5c  test    rcx, rcx
0x140008e5f  jz      locret_140008F88
0x140008e65  push    rbx
0x140008e66  push    rbp
0x140008e67  push    rsi
0x140008e68  push    rdi
0x140008e69  push    r14
0x140008e6b  push    r15
0x140008e6d  sub     rsp, 28h
0x140008e71  mov     rsi, rcx
0x140008e74  mov     rax, rsi
0x140008e77  mov     rbp, rsi
0x140008e7a  mov     rsi, [rsi]
0x140008e7d  mov     rcx, [rbp+10h]
0x140008e81  mov     qword ptr [rax], 0
0x140008e88  movzx   eax, word ptr [rcx+0Ah]
0x140008e8c  mov     r15, [rax+rcx+40h]
0x140008e91  mov     rbx, [rax+rcx+58h]
0x140008e96  mov     r14, [rax+rcx+50h]
0x140008e9b  mov     rdi, [rax+rcx+48h]
0x140008ea0  lock inc dword ptr [rdi+6D8h]
0x140008ea7  mov     edx, 80h; ContextSize
0x140008eac  mov     rcx, rbp; NetBufferList
0x140008eaf  call    cs:__imp_NdisFreeNetBufferListContext
0x140008eb6  nop     dword ptr [rax+rax+00h]
0x140008ebb  xor     r8d, r8d; SendCompleteFlags
0x140008ebe  mov     dword ptr [rbp+8Ch], 0C0000001h
0x140008ec8  mov     rdx, rbp; NetBufferList
0x140008ecb  test    rbx, rbx
0x140008ece  jz      short loc_140008EF7
0x140008ed0  mov     rcx, [rbx+28h]; NdisVcHandle
0x140008ed4  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x140008edb  nop     dword ptr [rax+rax+00h]
0x140008ee0  or      eax, 0FFFFFFFFh
0x140008ee3  lock xadd [rbx+18h], eax
0x140008ee8  cmp     eax, 1
0x140008eeb  jnz     short loc_140008F07
0x140008eed  mov     rcx, rbx
0x140008ef0  call    DoDerefCmVcCBWork
0x140008ef5  jmp     short loc_140008F07
0x140008ef7  mov     rcx, [r14+28h]; MiniportAdapterHandle
0x140008efb  call    cs:__imp_NdisMSendNetBufferListsComplete
0x140008f02  nop     dword ptr [rax+rax+00h]
0x140008f07  lea     rcx, [r15+18h]
0x140008f0b  call    DereferenceRefCount
0x140008f10  test    rdi, rdi
0x140008f13  jz      short loc_140008F52
0x140008f15  lea     rbp, [rdi+6E8h]
0x140008f1c  mov     rcx, rbp; SpinLock
0x140008f1f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008f26  nop     dword ptr [rax+rax+00h]
0x140008f2b  add     dword ptr [rdi+18h], 0FFFFFFFFh
0x140008f2f  mov     [rdi+6F0h], al
0x140008f35  jnz     short loc_140008F41
0x140008f37  mov     rcx, rdi; Entry
0x140008f3a  call    DoDerefBundleCBWork
0x140008f3f  jmp     short loc_140008F52
0x140008f41  mov     dl, al; NewIrql
0x140008f43  mov     rcx, rbp; SpinLock
0x140008f46  call    cs:__imp_KeReleaseSpinLock
0x140008f4d  nop     dword ptr [rax+rax+00h]
0x140008f52  test    rbx, rbx
0x140008f55  jz      short loc_140008F6C
0x140008f57  or      eax, 0FFFFFFFFh
0x140008f5a  lock xadd [rbx+18h], eax
0x140008f5f  cmp     eax, 1
0x140008f62  jnz     short loc_140008F6C
0x140008f64  mov     rcx, rbx
0x140008f67  call    DoDerefCmVcCBWork
0x140008f6c  lock inc cs:glSendCompleteCount
0x140008f73  test    rsi, rsi
0x140008f76  jnz     loc_140008E74
0x140008f7c  add     rsp, 28h
0x140008f80  pop     r15
0x140008f82  pop     r14
0x140008f84  pop     rdi
0x140008f85  pop     rsi
0x140008f86  pop     rbp
0x140008f87  pop     rbx
0x140008f88  retn
```
