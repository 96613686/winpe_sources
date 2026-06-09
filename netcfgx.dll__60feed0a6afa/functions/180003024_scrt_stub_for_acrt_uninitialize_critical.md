# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180003024`
- end: `0x180003027`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800020ac`
- `0x1800020dc`
- `0x180002180`
- `0x18000219c`
- `0x18000233c`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180003024  mov     al, 1
0x180003026  retn
```
