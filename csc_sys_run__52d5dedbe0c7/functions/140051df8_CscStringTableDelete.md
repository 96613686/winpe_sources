# CscStringTableDelete

- ea: `0x140051df8`
- end: `0x140051e48`
- name: `CscStringTableDelete`
- size: `80`
- prototype: `__int64 __fastcall(PERESOURCE Resource)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001bfac`
- `0x14005015c`

## callees

- `0x140020c7c`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140051e20`
- `ntoskrnl!ExDeleteResourceLite` at `0x140051e30`
- `ntoskrnl!ExDeleteResourceLite` at `0x140051e20`
- `ntoskrnl!ExDeleteResourceLite` at `0x140051e30`

## pseudocode

```c
NTSTATUS __fastcall CscStringTableDelete(PERESOURCE Resource)
{
  struct _RTL_AVL_TABLE *p_ActiveCount; // rbx

  p_ActiveCount = (struct _RTL_AVL_TABLE *)&Resource[2].ActiveCount;
  CscStringTablepDeleteTable((PRTL_AVL_TABLE)&Resource[2].ActiveCount);
  CscStringTablepDeleteTable(p_ActiveCount + 1);
  ExDeleteResourceLite(Resource);
  return ExDeleteResourceLite(Resource + 1);
}

```

## disassembly

```asm
0x140051df8  mov     [rsp+arg_0], rbx
0x140051dfd  push    rdi
0x140051dfe  sub     rsp, 20h
0x140051e02  lea     rbx, [rcx+0E8h]
0x140051e09  mov     rdi, rcx
0x140051e0c  mov     rcx, rbx; Table
0x140051e0f  call    CscStringTablepDeleteTable
0x140051e14  lea     rcx, [rbx+68h]; Table
0x140051e18  call    CscStringTablepDeleteTable
0x140051e1d  mov     rcx, rdi; Resource
0x140051e20  call    cs:__imp_ExDeleteResourceLite
0x140051e27  nop     dword ptr [rax+rax+00h]
0x140051e2c  lea     rcx, [rdi+68h]; Resource
0x140051e30  call    cs:__imp_ExDeleteResourceLite
0x140051e37  nop     dword ptr [rax+rax+00h]
0x140051e3c  mov     rbx, [rsp+28h+arg_0]
0x140051e41  add     rsp, 20h
0x140051e45  pop     rdi
0x140051e46  retn
```
