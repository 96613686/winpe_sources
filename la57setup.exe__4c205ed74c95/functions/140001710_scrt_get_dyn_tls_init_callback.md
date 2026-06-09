# __scrt_get_dyn_tls_init_callback

- ea: `0x140001710`
- end: `0x140001718`
- name: `__scrt_get_dyn_tls_init_callback`
- size: `8`
- prototype: `__int64 *()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001180`

## pseudocode

```c
__int64 *_scrt_get_dyn_tls_init_callback()
{
  return _dyn_tls_init_callback;
}

```

## disassembly

```asm
0x140001710  lea     rax, __dyn_tls_init_callback
0x140001717  retn
```
