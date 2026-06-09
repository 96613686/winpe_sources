# CdAcquireForCache

- ea: `0x140018160`
- end: `0x14001819e`
- name: `CdAcquireForCache`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x140018174`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140018174`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140018186`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140018186`

## pseudocode

```c
BOOLEAN __fastcall CdAcquireForCache(__int64 a1, BOOLEAN a2)
{
  IoSetTopLevelIrp((PIRP)2);
  return ExAcquireResourceSharedLite(*(PERESOURCE *)(a1 + 8), a2);
}

```

## disassembly

```asm
0x140018160  mov     [rsp+arg_0], rbx
0x140018165  push    rdi
0x140018166  sub     rsp, 20h
0x14001816a  mov     rdi, rcx
0x14001816d  mov     bl, dl
0x14001816f  mov     ecx, 2; Irp
0x140018174  call    cs:__imp_IoSetTopLevelIrp
0x14001817b  nop     dword ptr [rax+rax+00h]
0x140018180  mov     rcx, [rdi+8]; Resource
0x140018184  mov     dl, bl; Wait
0x140018186  call    cs:__imp_ExAcquireResourceSharedLite
0x14001818d  nop     dword ptr [rax+rax+00h]
0x140018192  mov     rbx, [rsp+28h+arg_0]
0x140018197  add     rsp, 20h
0x14001819b  pop     rdi
0x14001819c  retn
```
