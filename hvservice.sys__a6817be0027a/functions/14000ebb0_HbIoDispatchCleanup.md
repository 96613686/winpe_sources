# HbIoDispatchCleanup

- ea: `0x14000ebb0`
- end: `0x14000ec00`
- name: `HbIoDispatchCleanup`
- size: `80`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001600`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000ebeb`
- `ntoskrnl!IofCompleteRequest` at `0x14000ebeb`

## pseudocode

```c
__int64 __fastcall HbIoDispatchCleanup(__int64 a1, IRP *a2)
{
  HbpTraceEvent(3, "HbIoDispatchCleanup", 209, "Cleanup IRP: handle closed");
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14000ebb0  push    rbx
0x14000ebb2  sub     rsp, 20h
0x14000ebb6  mov     rbx, rdx
0x14000ebb9  lea     r9, aCleanupIrpHand; "Cleanup IRP: handle closed"
0x14000ebc0  mov     r8d, 0D1h
0x14000ebc6  lea     rdx, aHbiodispatchcl; "HbIoDispatchCleanup"
0x14000ebcd  mov     ecx, 3
0x14000ebd2  call    HbpTraceEvent
0x14000ebd7  xor     edx, edx; PriorityBoost
0x14000ebd9  mov     qword ptr [rbx+38h], 0
0x14000ebe1  mov     rcx, rbx; Irp
0x14000ebe4  mov     dword ptr [rbx+30h], 0
0x14000ebeb  call    cs:__imp_IofCompleteRequest
0x14000ebf2  nop     dword ptr [rax+rax+00h]
0x14000ebf7  xor     eax, eax
0x14000ebf9  add     rsp, 20h
0x14000ebfd  pop     rbx
0x14000ebfe  retn
```
