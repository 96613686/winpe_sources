# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800156d4`
- end: `0x1800156d7`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180014fa4`
- `0x180014fd4`
- `0x180015078`
- `0x180015094`
- `0x180015234`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800156d4  mov     al, 1
0x1800156d6  retn
```
