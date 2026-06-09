# TpiDispatchIrpStub

- ea: `0x140003750`
- end: `0x14000377f`
- name: `TpiDispatchIrpStub`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140003768`
- `ntoskrnl!IofCompleteRequest` at `0x140003768`

## pseudocode

```c
__int64 __fastcall TpiDispatchIrpStub(__int64 a1, IRP *a2)
{
  a2->IoStatus.Status = -1073741637;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 3221225659LL;
}

```

## disassembly

```asm
0x140003750  sub     rsp, 28h
0x140003754  mov     rcx, rdx; Irp
0x140003757  mov     dword ptr [rdx+30h], 0C00000BBh
0x14000375e  mov     qword ptr [rdx+38h], 0
0x140003766  xor     edx, edx; PriorityBoost
0x140003768  call    cs:__imp_IofCompleteRequest
0x14000376f  nop     dword ptr [rax+rax+00h]
0x140003774  mov     eax, 0C00000BBh
0x140003779  add     rsp, 28h
0x14000377d  retn
```
