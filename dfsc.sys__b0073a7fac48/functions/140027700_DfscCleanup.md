# DfscCleanup

- ea: `0x140027700`
- end: `0x140027743`
- name: `DfscCleanup`
- size: `67`
- prototype: `__int64 __fastcall(PVOID, IRP *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002772e`
- `ntoskrnl!IofCompleteRequest` at `0x14002772e`

## pseudocode

```c
__int64 __fastcall DfscCleanup(PVOID a1, IRP *a2)
{
  unsigned int v2; // ebx

  v2 = a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext != a1 ? 0xC0000010 : 0;
  a2->IoStatus.Status = v2;
  IofCompleteRequest(a2, 0);
  return v2;
}

```

## disassembly

```asm
0x140027700  push    rbx
0x140027702  sub     rsp, 20h
0x140027706  mov     rax, [rdx+0B8h]
0x14002770d  mov     r9, rdx
0x140027710  mov     r8, [rax+30h]
0x140027714  mov     rax, [r8+18h]
0x140027718  sub     rax, rcx
0x14002771b  mov     rcx, r9; Irp
0x14002771e  neg     rax
0x140027721  sbb     ebx, ebx
0x140027723  and     ebx, 0C0000010h
0x140027729  mov     [rdx+30h], ebx
0x14002772c  xor     edx, edx; PriorityBoost
0x14002772e  call    cs:__imp_IofCompleteRequest
0x140027735  nop     dword ptr [rax+rax+00h]
0x14002773a  mov     eax, ebx
0x14002773c  add     rsp, 20h
0x140027740  pop     rbx
0x140027741  retn
```
