# HbIoDispatchClose

- ea: `0x14000ec10`
- end: `0x14000ec60`
- name: `HbIoDispatchClose`
- size: `80`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001600`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000ec4b`
- `ntoskrnl!IofCompleteRequest` at `0x14000ec4b`

## pseudocode

```c
__int64 __fastcall HbIoDispatchClose(__int64 a1, IRP *a2)
{
  HbpTraceEvent(3, "HbIoDispatchClose", 251, "Close IRP: file object destroyed");
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14000ec10  push    rbx
0x14000ec12  sub     rsp, 20h
0x14000ec16  mov     rbx, rdx
0x14000ec19  lea     r9, aCloseIrpFileOb; "Close IRP: file object destroyed"
0x14000ec20  mov     r8d, 0FBh
0x14000ec26  lea     rdx, aHbiodispatchcl_0; "HbIoDispatchClose"
0x14000ec2d  mov     ecx, 3
0x14000ec32  call    HbpTraceEvent
0x14000ec37  xor     edx, edx; PriorityBoost
0x14000ec39  mov     qword ptr [rbx+38h], 0
0x14000ec41  mov     rcx, rbx; Irp
0x14000ec44  mov     dword ptr [rbx+30h], 0
0x14000ec4b  call    cs:__imp_IofCompleteRequest
0x14000ec52  nop     dword ptr [rax+rax+00h]
0x14000ec57  xor     eax, eax
0x14000ec59  add     rsp, 20h
0x14000ec5d  pop     rbx
0x14000ec5e  retn
```
