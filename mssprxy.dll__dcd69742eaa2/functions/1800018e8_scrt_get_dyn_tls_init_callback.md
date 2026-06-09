# __scrt_get_dyn_tls_init_callback

- ea: `0x1800018e8`
- end: `0x1800018f0`
- name: `__scrt_get_dyn_tls_init_callback`
- size: `8`
- prototype: `__int64 *()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001158`

## pseudocode

```c
__int64 *_scrt_get_dyn_tls_init_callback()
{
  return _dyn_tls_init_callback;
}

```

## disassembly

```asm
0x1800018e8  lea     rax, __dyn_tls_init_callback
0x1800018ef  retn
```
