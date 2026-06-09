# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002cdc`
- end: `0x180002cdf`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001dd8`
- `0x180001e08`
- `0x180001eac`
- `0x180001ec8`
- `0x180002068`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002cdc  mov     al, 1
0x180002cde  retn
```
