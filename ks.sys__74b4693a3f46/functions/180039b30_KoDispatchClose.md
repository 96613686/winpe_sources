# KoDispatchClose

- ea: `0x180039b30`
- end: `0x180039ba4`
- name: `KoDispatchClose`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800088b0`
- `0x180059470`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180039b85`
- `ntoskrnl!IofCompleteRequest` at `0x180039b85`
- `ntoskrnl!ExFreePoolWithTag` at `0x180039b61`
- `ntoskrnl!ExFreePoolWithTag` at `0x180039b61`

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
0x180039b30  mov     [rsp+arg_0], rbx
0x180039b35  mov     [rsp+arg_8], rsi
0x180039b3a  push    rdi
0x180039b3b  sub     rsp, 20h
0x180039b3f  mov     rax, [rdx+0B8h]
0x180039b46  mov     rdi, rcx
0x180039b49  mov     rsi, rdx
0x180039b4c  mov     r8, [rax+30h]
0x180039b50  mov     rbx, [r8+18h]
0x180039b54  mov     rcx, [rbx]; Header
0x180039b57  call    KsFreeObjectHeader
0x180039b5c  xor     edx, edx; Tag
0x180039b5e  mov     rcx, rbx; P
0x180039b61  call    cs:__imp_ExFreePoolWithTag
0x180039b68  nop     dword ptr [rax+rax+00h]
0x180039b6d  mov     rcx, [rdi+40h]
0x180039b71  mov     rcx, [rcx]; Header
0x180039b74  call    KsDereferenceBusObject
0x180039b79  xor     edx, edx; PriorityBoost
0x180039b7b  mov     dword ptr [rsi+30h], 0
0x180039b82  mov     rcx, rsi; Irp
0x180039b85  call    cs:__imp_IofCompleteRequest
0x180039b8c  nop     dword ptr [rax+rax+00h]
0x180039b91  mov     rbx, [rsp+28h+arg_0]
0x180039b96  xor     eax, eax
0x180039b98  mov     rsi, [rsp+28h+arg_8]
0x180039b9d  add     rsp, 20h
0x180039ba1  pop     rdi
0x180039ba2  retn
```
