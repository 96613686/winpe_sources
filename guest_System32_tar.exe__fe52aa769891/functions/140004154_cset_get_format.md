# cset_get_format

- ea: `0x140004154`
- end: `0x140004158`
- name: `cset_get_format`
- size: `4`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400061dc`
- `0x1400063bc`

## pseudocode

```c
__int64 __fastcall cset_get_format(__int64 a1)
{
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x140004154  mov     rax, [rcx]
0x140004157  retn
```
