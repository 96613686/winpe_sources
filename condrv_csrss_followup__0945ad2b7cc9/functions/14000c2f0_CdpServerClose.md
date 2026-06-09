# CdpServerClose

- ea: `0x14000c2f0`
- end: `0x14000c321`
- name: `CdpServerClose`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000b020`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000c30c`
- `ntoskrnl!IofCompleteRequest` at `0x14000c30c`

## pseudocode

```c
__int64 __fastcall CdpServerClose(char *a1, IRP *a2)
{
  CdDereferenceServer(a1);
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14000c2f0  push    rbx
0x14000c2f2  sub     rsp, 20h
0x14000c2f6  mov     rbx, rdx
0x14000c2f9  call    CdDereferenceServer
0x14000c2fe  xor     eax, eax
0x14000c300  xor     edx, edx; PriorityBoost
0x14000c302  mov     rcx, rbx; Irp
0x14000c305  mov     [rbx+30h], eax
0x14000c308  mov     [rbx+38h], rax
0x14000c30c  call    cs:__imp_IofCompleteRequest
0x14000c313  nop     dword ptr [rax+rax+00h]
0x14000c318  xor     eax, eax
0x14000c31a  add     rsp, 20h
0x14000c31e  pop     rbx
0x14000c31f  retn
```
