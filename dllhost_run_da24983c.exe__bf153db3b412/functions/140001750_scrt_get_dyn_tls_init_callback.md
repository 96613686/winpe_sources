# __scrt_get_dyn_tls_init_callback

- ea: `0x140001750`
- end: `0x140001758`
- name: `__scrt_get_dyn_tls_init_callback`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400011d0`

## pseudocode

```c
void *_scrt_get_dyn_tls_init_callback()
{
  return &_dyn_tls_init_callback;
}

```

## disassembly

```asm
0x140001750  lea     rax, __dyn_tls_init_callback
0x140001757  retn
```
