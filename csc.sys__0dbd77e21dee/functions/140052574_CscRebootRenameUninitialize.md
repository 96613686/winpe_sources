# CscRebootRenameUninitialize

- ea: `0x140052574`
- end: `0x1400525a3`
- name: `CscRebootRenameUninitialize`
- size: `47`
- prototype: `__int64 __fastcall(PERESOURCE Resource)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140090740`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140052581`
- `ntoskrnl!ExDeleteResourceLite` at `0x140052590`
- `ntoskrnl!ExDeleteResourceLite` at `0x140052581`
- `ntoskrnl!ExDeleteResourceLite` at `0x140052590`

## pseudocode

```c
NTSTATUS __fastcall CscRebootRenameUninitialize(PERESOURCE Resource)
{
  ExDeleteResourceLite(Resource + 1);
  return ExDeleteResourceLite(Resource);
}

```

## disassembly

```asm
0x140052574  push    rbx
0x140052576  sub     rsp, 20h
0x14005257a  mov     rbx, rcx
0x14005257d  add     rcx, 68h ; 'h'; Resource
0x140052581  call    cs:__imp_ExDeleteResourceLite
0x140052588  nop     dword ptr [rax+rax+00h]
0x14005258d  mov     rcx, rbx; Resource
0x140052590  call    cs:__imp_ExDeleteResourceLite
0x140052597  nop     dword ptr [rax+rax+00h]
0x14005259c  add     rsp, 20h
0x1400525a0  pop     rbx
0x1400525a1  retn
```
