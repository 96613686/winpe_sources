# ProvFree

- ea: `0x140001fd4`
- end: `0x140001fef`
- name: `ProvFree`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000a620`
- `0x14000a690`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001fdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001fdd`

## pseudocode

```c
void __fastcall ProvFree(void *a1)
{
  ExFreePoolWithTag(a1, 0x48676E43u);
}

```

## disassembly

```asm
0x140001fd4  sub     rsp, 28h
0x140001fd8  mov     edx, 48676E43h; Tag
0x140001fdd  call    cs:__imp_ExFreePoolWithTag
0x140001fe4  nop     dword ptr [rax+rax+00h]
0x140001fe9  add     rsp, 28h
0x140001fed  retn
```
