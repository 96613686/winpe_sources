# nullsub_125

- ea: `0x3f1b68`
- end: `0x3f1b6b`
- name: `nullsub_125`
- size: `3`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall nullsub_125(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  _BYTE retaddr[16]; // [rsp+0h] [rbp+0h]

  return MK_FP(*(_WORD *)retaddr, *(_QWORD *)retaddr)(a4);
}

```

## disassembly

```asm
0x3f1b68  retf    0Eh
```
