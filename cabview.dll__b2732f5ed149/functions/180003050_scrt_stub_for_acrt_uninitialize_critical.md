# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180003050`
- end: `0x180003053`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800026dc`
- `0x18000270c`
- `0x1800027b0`
- `0x1800027cc`
- `0x18000296c`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180003050  mov     al, 1
0x180003052  retn
```
