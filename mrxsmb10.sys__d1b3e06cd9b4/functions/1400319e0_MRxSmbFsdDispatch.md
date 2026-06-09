# MRxSmbFsdDispatch

- ea: `0x1400319e0`
- end: `0x140031a0f`
- name: `MRxSmbFsdDispatch`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400319f8`
- `ntoskrnl!IofCompleteRequest` at `0x1400319f8`

## pseudocode

```c
__int64 __fastcall MRxSmbFsdDispatch(__int64 a1, IRP *a2)
{
  a2->IoStatus.Status = -1073741808;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 3221225488LL;
}

```

## disassembly

```asm
0x1400319e0  sub     rsp, 28h
0x1400319e4  mov     rcx, rdx; Irp
0x1400319e7  mov     dword ptr [rdx+30h], 0C0000010h
0x1400319ee  mov     qword ptr [rdx+38h], 0
0x1400319f6  xor     edx, edx; PriorityBoost
0x1400319f8  call    cs:__imp_IofCompleteRequest
0x1400319ff  nop     dword ptr [rax+rax+00h]
0x140031a04  mov     eax, 0C0000010h
0x140031a09  add     rsp, 28h
0x140031a0d  retn
```
