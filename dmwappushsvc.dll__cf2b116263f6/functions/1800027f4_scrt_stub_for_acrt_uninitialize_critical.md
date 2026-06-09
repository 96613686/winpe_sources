# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800027f4`
- end: `0x1800027f7`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d24`
- `0x180001d54`
- `0x180001df8`
- `0x180001e14`
- `0x180001fb4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800027f4  mov     al, 1
0x1800027f6  retn
```
