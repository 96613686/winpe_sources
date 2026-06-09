# nullsub_8

- ea: `0x21d00`
- end: `0x21d03`
- name: `nullsub_8`
- size: `3`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 nullsub_8()
{
  _BYTE retaddr[16]; // [rsp+0h] [rbp+0h]

  return MK_FP(*(_WORD *)retaddr, *(_QWORD *)retaddr)();
}

```

## disassembly

```asm
0x21d00  retf    0
```
