# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800024d0`
- end: `0x1800024d3`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001640`
- `0x180001670`
- `0x180001714`
- `0x180001730`
- `0x1800018d0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800024d0  mov     al, 1
0x1800024d2  retn
```
