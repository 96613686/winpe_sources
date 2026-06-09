# HbIoDispatchCreate

- ea: `0x14000ec70`
- end: `0x14000ecc0`
- name: `HbIoDispatchCreate`
- size: `80`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001600`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000ecab`
- `ntoskrnl!IofCompleteRequest` at `0x14000ecab`

## string_xrefs

- `0x14000ec79`: `Create IRP: new handle opened`
- `0x14000ec86`: `HbIoDispatchCreate`

## pseudocode

```c
__int64 __fastcall HbIoDispatchCreate(__int64 a1, IRP *a2)
{
  HbpTraceEvent(3, "HbIoDispatchCreate", 166, "Create IRP: new handle opened");
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14000ec70  push    rbx
0x14000ec72  sub     rsp, 20h
0x14000ec76  mov     rbx, rdx
0x14000ec79  lea     r9, aCreateIrpNewHa; "Create IRP: new handle opened"
0x14000ec80  mov     r8d, 0A6h
0x14000ec86  lea     rdx, aHbiodispatchcr; "HbIoDispatchCreate"
0x14000ec8d  mov     ecx, 3
0x14000ec92  call    HbpTraceEvent
0x14000ec97  xor     edx, edx; PriorityBoost
0x14000ec99  mov     qword ptr [rbx+38h], 0
0x14000eca1  mov     rcx, rbx; Irp
0x14000eca4  mov     dword ptr [rbx+30h], 0
0x14000ecab  call    cs:__imp_IofCompleteRequest
0x14000ecb2  nop     dword ptr [rax+rax+00h]
0x14000ecb7  xor     eax, eax
0x14000ecb9  add     rsp, 20h
0x14000ecbd  pop     rbx
0x14000ecbe  retn
```
