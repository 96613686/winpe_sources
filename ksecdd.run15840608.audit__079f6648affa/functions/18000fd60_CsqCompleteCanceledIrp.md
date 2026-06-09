# CsqCompleteCanceledIrp

- ea: `0x18000fd60`
- end: `0x18000fdbb`
- name: `CsqCompleteCanceledIrp`
- size: `91`
- prototype: `IO_CSQ_COMPLETE_CANCELED_IRP`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ded4`
- `0x18000fd60`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18000fda8`
- `ntoskrnl!IofCompleteRequest` at `0x18000fda8`

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
0x18000fd60  push    rbx
0x18000fd62  sub     rsp, 20h
0x18000fd66  mov     rbx, rdx
0x18000fd69  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd70  lea     rax, WPP_GLOBAL_Control
0x18000fd77  cmp     rcx, rax
0x18000fd7a  jz      short loc_18000FD94
0x18000fd7c  mov     rcx, [rcx+18h]
0x18000fd80  lea     r8, WPP_f9740104427135617d8c60794f45a901_Traceguids
0x18000fd87  mov     edx, 15h
0x18000fd8c  mov     r9, rbx
0x18000fd8f  call    WPP_SF_q
0x18000fd94  xor     edx, edx; PriorityBoost
0x18000fd96  mov     qword ptr [rbx+38h], 0
0x18000fd9e  mov     rcx, rbx; Irp
0x18000fda1  mov     dword ptr [rbx+30h], 0C0000120h
0x18000fda8  call    cs:__imp_IofCompleteRequest
0x18000fdaf  nop     dword ptr [rax+rax+00h]
0x18000fdb4  add     rsp, 20h
0x18000fdb8  pop     rbx
0x18000fdb9  retn
```
