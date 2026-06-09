# KoDispatchClose

- ea: `0x180039b80`
- end: `0x180039bf4`
- name: `KoDispatchClose`
- size: `116`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800088b0`
- `0x180059610`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180039bd5`
- `ntoskrnl!IofCompleteRequest` at `0x180039bd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x180039bb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180039bb1`

## pseudocode

```c
__int64 __fastcall KoDispatchClose(__int64 a1, IRP *a2)
{
  KSOBJECT_HEADER *FsContext; // rbx

  FsContext = (KSOBJECT_HEADER *)a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  KsFreeObjectHeader(*FsContext);
  ExFreePoolWithTag(FsContext, 0);
  KsDereferenceBusObject(**(KSDEVICE_HEADER **)(a1 + 64));
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x180039b80  mov     [rsp+arg_0], rbx
0x180039b85  mov     [rsp+arg_8], rsi
0x180039b8a  push    rdi
0x180039b8b  sub     rsp, 20h
0x180039b8f  mov     rax, [rdx+0B8h]
0x180039b96  mov     rdi, rcx
0x180039b99  mov     rsi, rdx
0x180039b9c  mov     r8, [rax+30h]
0x180039ba0  mov     rbx, [r8+18h]
0x180039ba4  mov     rcx, [rbx]; Header
0x180039ba7  call    KsFreeObjectHeader
0x180039bac  xor     edx, edx; Tag
0x180039bae  mov     rcx, rbx; P
0x180039bb1  call    cs:__imp_ExFreePoolWithTag
0x180039bb8  nop     dword ptr [rax+rax+00h]
0x180039bbd  mov     rcx, [rdi+40h]
0x180039bc1  mov     rcx, [rcx]; Header
0x180039bc4  call    KsDereferenceBusObject
0x180039bc9  xor     edx, edx; PriorityBoost
0x180039bcb  mov     dword ptr [rsi+30h], 0
0x180039bd2  mov     rcx, rsi; Irp
0x180039bd5  call    cs:__imp_IofCompleteRequest
0x180039bdc  nop     dword ptr [rax+rax+00h]
0x180039be1  mov     rbx, [rsp+28h+arg_0]
0x180039be6  xor     eax, eax
0x180039be8  mov     rsi, [rsp+28h+arg_8]
0x180039bed  add     rsp, 20h
0x180039bf1  pop     rdi
0x180039bf2  retn
```
