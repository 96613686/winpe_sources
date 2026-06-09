# lldpAttachOpenPort

- ea: `0x140006298`
- end: `0x140006302`
- name: `lldpAttachOpenPort`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000efd0`

## callees

- `0x140003d80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400062b2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400062b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400062e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400062e5`

## pseudocode

```c
void __fastcall lldpAttachOpenPort(__int64 a1)
{
  __int64 v1; // rdi

  v1 = *(_QWORD *)(a1 + 24);
  *(_BYTE *)(v1 + 80) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 72));
  *(_QWORD *)(a1 + 8) = *(_QWORD *)(v1 + 88);
  *(_QWORD *)(v1 + 88) = a1;
  lldpQueueChangeNotificationEx((PVOID)v1);
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 72), *(_BYTE *)(v1 + 80));
}

```

## disassembly

```asm
0x140006298  mov     [rsp+arg_0], rbx
0x14000629d  mov     [rsp+arg_8], rsi
0x1400062a2  push    rdi
0x1400062a3  sub     rsp, 20h
0x1400062a7  mov     rdi, [rcx+18h]
0x1400062ab  mov     rbx, rcx
0x1400062ae  lea     rcx, [rdi+48h]; SpinLock
0x1400062b2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400062b9  nop     dword ptr [rax+rax+00h]
0x1400062be  mov     [rdi+50h], al
0x1400062c1  mov     r8d, 40000000h
0x1400062c7  mov     rax, [rdi+58h]
0x1400062cb  mov     rdx, rbx
0x1400062ce  mov     [rbx+8], rax
0x1400062d2  mov     rcx, rdi; Context
0x1400062d5  mov     [rdi+58h], rbx
0x1400062d9  call    lldpQueueChangeNotificationEx
0x1400062de  mov     dl, [rdi+50h]; NewIrql
0x1400062e1  lea     rcx, [rdi+48h]; SpinLock
0x1400062e5  call    cs:__imp_KeReleaseSpinLock
0x1400062ec  nop     dword ptr [rax+rax+00h]
0x1400062f1  mov     rbx, [rsp+28h+arg_0]
0x1400062f6  mov     rsi, [rsp+28h+arg_8]
0x1400062fb  add     rsp, 20h
0x1400062ff  pop     rdi
0x140006300  retn
```
