# nullsub_58

- ea: `0x1bbe70`
- end: `0x1bbe73`
- name: `nullsub_58`
- size: `3`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall nullsub_58(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6, __int64 a7)
{
  _BYTE retaddr[16]; // [rsp+0h] [rbp+0h]

  return MK_FP(*(_WORD *)retaddr, *(_QWORD *)retaddr)();
}

```

## disassembly

```asm
0x1bbe70  retf    1
```
