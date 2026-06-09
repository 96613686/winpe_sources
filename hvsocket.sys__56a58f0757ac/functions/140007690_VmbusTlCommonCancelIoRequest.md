# VmbusTlCommonCancelIoRequest

- ea: `0x140007690`
- end: `0x1400076c7`
- name: `VmbusTlCommonCancelIoRequest`
- size: `55`
- prototype: `void __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400076b4`
- `ntoskrnl!IofCompleteRequest` at `0x1400076b4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000769c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000769c`

## pseudocode

```c
void __fastcall VmbusTlCommonCancelIoRequest(__int64 a1, IRP *a2)
{
  IoReleaseCancelSpinLock(a2->CancelIrql);
  a2->IoStatus.Status = -1073741247;
  IofCompleteRequest(a2, 2);
}

```

## disassembly

```asm
0x140007690  push    rbx
0x140007692  sub     rsp, 20h
0x140007696  mov     cl, [rdx+45h]; Irql
0x140007699  mov     rbx, rdx
0x14000769c  call    cs:__imp_IoReleaseCancelSpinLock
0x1400076a3  nop     dword ptr [rax+rax+00h]
0x1400076a8  mov     dl, 2; PriorityBoost
0x1400076aa  mov     dword ptr [rbx+30h], 0C0000241h
0x1400076b1  mov     rcx, rbx; Irp
0x1400076b4  call    cs:__imp_IofCompleteRequest
0x1400076bb  nop     dword ptr [rax+rax+00h]
0x1400076c0  add     rsp, 20h
0x1400076c4  pop     rbx
0x1400076c5  retn
```
