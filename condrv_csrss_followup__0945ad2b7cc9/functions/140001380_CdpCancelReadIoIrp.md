# CdpCancelReadIoIrp

- ea: `0x140001380`
- end: `0x1400013a7`
- name: `CdpCancelReadIoIrp`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400091c0`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000138c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000138c`

## pseudocode

```c
void __fastcall CdpCancelReadIoIrp(__int64 a1, IRP *a2)
{
  IoReleaseCancelSpinLock(a2->CancelIrql);
  CdpCancelReadIoIrpPaged(a2);
}

```

## disassembly

```asm
0x140001380  push    rbx
0x140001382  sub     rsp, 20h
0x140001386  mov     cl, [rdx+45h]; Irql
0x140001389  mov     rbx, rdx
0x14000138c  call    cs:__imp_IoReleaseCancelSpinLock
0x140001393  nop     dword ptr [rax+rax+00h]
0x140001398  mov     rcx, rbx; Irp
0x14000139b  call    CdpCancelReadIoIrpPaged
0x1400013a0  add     rsp, 20h
0x1400013a4  pop     rbx
0x1400013a5  retn
```
