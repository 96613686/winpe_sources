# ProvCreateClose

- ea: `0x14000a010`
- end: `0x14000a03c`
- name: `ProvCreateClose`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000a028`
- `ntoskrnl!IofCompleteRequest` at `0x14000a028`

## pseudocode

```c
__int64 __fastcall ProvCreateClose(__int64 a1, IRP *a2)
{
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14000a010  sub     rsp, 28h
0x14000a014  mov     rcx, rdx; Irp
0x14000a017  mov     dword ptr [rdx+30h], 0
0x14000a01e  mov     qword ptr [rdx+38h], 0
0x14000a026  xor     edx, edx; PriorityBoost
0x14000a028  call    cs:__imp_IofCompleteRequest
0x14000a02f  nop     dword ptr [rax+rax+00h]
0x14000a034  xor     eax, eax
0x14000a036  add     rsp, 28h
0x14000a03a  retn
```
