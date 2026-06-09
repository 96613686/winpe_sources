# DeregisterSapPassive

- ea: `0x140001d60`
- end: `0x140001e15`
- name: `DeregisterSapPassive`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001870`
- `0x140001920`
- `0x140018e08`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140001db4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001db4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001d8b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001d8b`
- `NDIS!NdisCmDeregisterSapComplete` at `0x140001df8`
- `NDIS!NdisCmDeregisterSapComplete` at `0x140001df8`
- `NDIS!NdisFreeIoWorkItem` at `0x140001d75`
- `NDIS!NdisFreeIoWorkItem` at `0x140001d75`

## pseudocode

```c
void __fastcall DeregisterSapPassive(__int64 a1, void *a2)
{
  KIRQL v3; // al
  void *v4; // rdi
  __int64 v5; // rdx

  NdisFreeIoWorkItem(a2);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 384));
  v4 = *(void **)(a1 + 336);
  *(_BYTE *)(a1 + 392) = v3;
  *(_QWORD *)(a1 + 336) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 384), v3);
  LOBYTE(v5) = 1;
  TransportClose(a1 + 240, v5);
  TransportClose(a1 + 240, 0);
  DereferenceAdapter(a1);
  DereferenceAdapter(a1);
  DereferenceAf(a1);
  NdisCmDeregisterSapComplete(0, v4);
}

```

## disassembly

```asm
0x140001d60  mov     [rsp+arg_0], rbx
0x140001d65  mov     [rsp+arg_8], rsi
0x140001d6a  push    rdi
0x140001d6b  sub     rsp, 20h
0x140001d6f  mov     rsi, rcx
0x140001d72  mov     rcx, rdx; NdisIoWorkItemHandle
0x140001d75  call    cs:__imp_NdisFreeIoWorkItem
0x140001d7c  nop     dword ptr [rax+rax+00h]
0x140001d81  lea     rbx, [rsi+180h]
0x140001d88  mov     rcx, rbx; SpinLock
0x140001d8b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001d92  nop     dword ptr [rax+rax+00h]
0x140001d97  mov     rdi, [rsi+150h]
0x140001d9e  mov     rcx, rbx; SpinLock
0x140001da1  mov     dl, al; NewIrql
0x140001da3  mov     [rsi+188h], al
0x140001da9  mov     qword ptr [rsi+150h], 0
0x140001db4  call    cs:__imp_KeReleaseSpinLock
0x140001dbb  nop     dword ptr [rax+rax+00h]
0x140001dc0  lea     rbx, [rsi+0F0h]
0x140001dc7  mov     dl, 1
0x140001dc9  mov     rcx, rbx
0x140001dcc  call    TransportClose
0x140001dd1  xor     edx, edx
0x140001dd3  mov     rcx, rbx
0x140001dd6  call    TransportClose
0x140001ddb  mov     rcx, rsi
0x140001dde  call    DereferenceAdapter
0x140001de3  mov     rcx, rsi
0x140001de6  call    DereferenceAdapter
0x140001deb  mov     rcx, rsi
0x140001dee  call    DereferenceAf
0x140001df3  mov     rdx, rdi; NdisSapHandle
0x140001df6  xor     ecx, ecx; Status
0x140001df8  call    cs:__imp_NdisCmDeregisterSapComplete
0x140001dff  nop     dword ptr [rax+rax+00h]
0x140001e04  mov     rbx, [rsp+28h+arg_0]
0x140001e09  mov     rsi, [rsp+28h+arg_8]
0x140001e0e  add     rsp, 20h
0x140001e12  pop     rdi
0x140001e13  retn
```
