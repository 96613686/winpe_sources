# CdpServerCleanup

- ea: `0x14000c330`
- end: `0x14000c365`
- name: `CdpServerCleanup`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000b170`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000c350`
- `ntoskrnl!IofCompleteRequest` at `0x14000c350`

## pseudocode

```c
__int64 __fastcall CdpServerCleanup(__int64 a1, IRP *a2)
{
  CdDisconnectIoPipe((_QWORD *)(a1 + 64));
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14000c330  push    rbx
0x14000c332  sub     rsp, 20h
0x14000c336  add     rcx, 40h ; '@'
0x14000c33a  mov     rbx, rdx
0x14000c33d  call    CdDisconnectIoPipe
0x14000c342  xor     eax, eax
0x14000c344  xor     edx, edx; PriorityBoost
0x14000c346  mov     rcx, rbx; Irp
0x14000c349  mov     [rbx+30h], eax
0x14000c34c  mov     [rbx+38h], rax
0x14000c350  call    cs:__imp_IofCompleteRequest
0x14000c357  nop     dword ptr [rax+rax+00h]
0x14000c35c  xor     eax, eax
0x14000c35e  add     rsp, 20h
0x14000c362  pop     rbx
0x14000c363  retn
```
