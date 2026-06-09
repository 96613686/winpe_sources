# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000bfbc`
- end: `0x18000bfbf`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000abe0`
- `0x18000ac10`
- `0x18000acb4`
- `0x18000acd0`
- `0x18000ae70`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000bfbc  mov     al, 1
0x18000bfbe  retn
```
