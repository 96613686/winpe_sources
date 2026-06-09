# CdReleaseFromCache

- ea: `0x140018330`
- end: `0x14001835e`
- name: `CdReleaseFromCache`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14001834b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001834b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001833b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001833b`

## pseudocode

```c
void __fastcall CdReleaseFromCache(__int64 a1)
{
  IoSetTopLevelIrp(0);
  ExReleaseResourceLite(*(PERESOURCE *)(a1 + 8));
}

```

## disassembly

```asm
0x140018330  push    rbx
0x140018332  sub     rsp, 20h
0x140018336  mov     rbx, rcx
0x140018339  xor     ecx, ecx; Irp
0x14001833b  call    cs:__imp_IoSetTopLevelIrp
0x140018342  nop     dword ptr [rax+rax+00h]
0x140018347  mov     rcx, [rbx+8]; Resource
0x14001834b  call    cs:__imp_ExReleaseResourceLite
0x140018352  nop     dword ptr [rax+rax+00h]
0x140018357  add     rsp, 20h
0x14001835b  pop     rbx
0x14001835c  retn
```
