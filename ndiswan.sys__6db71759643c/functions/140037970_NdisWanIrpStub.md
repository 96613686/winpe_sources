# NdisWanIrpStub

- ea: `0x140037970`
- end: `0x14003799f`
- name: `NdisWanIrpStub`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140037988`
- `ntoskrnl!IofCompleteRequest` at `0x140037988`

## pseudocode

```c
__int64 __fastcall NdisWanIrpStub(__int64 a1, IRP *a2)
{
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = -1073741637;
  IofCompleteRequest(a2, 0);
  return 3221225659LL;
}

```

## disassembly

```asm
0x140037970  sub     rsp, 28h
0x140037974  mov     rcx, rdx; Irp
0x140037977  mov     qword ptr [rdx+38h], 0
0x14003797f  mov     dword ptr [rdx+30h], 0C00000BBh
0x140037986  xor     edx, edx; PriorityBoost
0x140037988  call    cs:__imp_IofCompleteRequest
0x14003798f  nop     dword ptr [rax+rax+00h]
0x140037994  mov     eax, 0C00000BBh
0x140037999  add     rsp, 28h
0x14003799d  retn
```
