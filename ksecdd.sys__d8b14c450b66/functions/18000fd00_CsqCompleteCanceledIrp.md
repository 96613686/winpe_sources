# CsqCompleteCanceledIrp

- ea: `0x18000fd00`
- end: `0x18000fd5b`
- name: `CsqCompleteCanceledIrp`
- size: `91`
- prototype: `IO_CSQ_COMPLETE_CANCELED_IRP`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ded4`
- `0x18000fd00`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18000fd48`
- `ntoskrnl!IofCompleteRequest` at `0x18000fd48`

## pseudocode

```c
void __fastcall CsqCompleteCanceledIrp(PIO_CSQ Csq, PIRP Irp)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 3), 21, WPP_f9740104427135617d8c60794f45a901_Traceguids, Irp);
  Irp->IoStatus.Information = 0;
  Irp->IoStatus.Status = -1073741536;
  IofCompleteRequest(Irp, 0);
}

```

## disassembly

```asm
0x18000fd00  push    rbx
0x18000fd02  sub     rsp, 20h
0x18000fd06  mov     rbx, rdx
0x18000fd09  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd10  lea     rax, WPP_GLOBAL_Control
0x18000fd17  cmp     rcx, rax
0x18000fd1a  jz      short loc_18000FD34
0x18000fd1c  mov     rcx, [rcx+18h]
0x18000fd20  lea     r8, WPP_f9740104427135617d8c60794f45a901_Traceguids
0x18000fd27  mov     edx, 15h
0x18000fd2c  mov     r9, rbx
0x18000fd2f  call    WPP_SF_q
0x18000fd34  xor     edx, edx; PriorityBoost
0x18000fd36  mov     qword ptr [rbx+38h], 0
0x18000fd3e  mov     rcx, rbx; Irp
0x18000fd41  mov     dword ptr [rbx+30h], 0C0000120h
0x18000fd48  call    cs:__imp_IofCompleteRequest
0x18000fd4f  nop     dword ptr [rax+rax+00h]
0x18000fd54  add     rsp, 20h
0x18000fd58  pop     rbx
0x18000fd59  retn
```
