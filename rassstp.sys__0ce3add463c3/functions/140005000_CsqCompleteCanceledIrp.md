# CsqCompleteCanceledIrp

- ea: `0x140005000`
- end: `0x140005022`
- name: `CsqCompleteCanceledIrp`
- size: `34`
- prototype: `IO_CSQ_COMPLETE_CANCELED_IRP`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140005010`
- `ntoskrnl!IofCompleteRequest` at `0x140005010`

## pseudocode

```c
void __fastcall CsqCompleteCanceledIrp(PIO_CSQ Csq, PIRP Irp)
{
  Irp->IoStatus.Status = -1073741536;
  IofCompleteRequest(Irp, 0);
}

```

## disassembly

```asm
0x140005000  sub     rsp, 28h
0x140005004  mov     rcx, rdx; Irp
0x140005007  mov     dword ptr [rdx+30h], 0C0000120h
0x14000500e  xor     edx, edx; PriorityBoost
0x140005010  call    cs:__imp_IofCompleteRequest
0x140005017  nop     dword ptr [rax+rax+00h]
0x14000501c  add     rsp, 28h
0x140005020  retn
```
