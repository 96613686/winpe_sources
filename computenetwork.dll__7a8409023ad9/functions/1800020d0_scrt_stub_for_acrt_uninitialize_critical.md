# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800020d0`
- end: `0x1800020d3`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800016b0`
- `0x1800016e0`
- `0x180001784`
- `0x1800017a0`
- `0x180001940`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800020d0  mov     al, 1
0x1800020d2  retn
```
