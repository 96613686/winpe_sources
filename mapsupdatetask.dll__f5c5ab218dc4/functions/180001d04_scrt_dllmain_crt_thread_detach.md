# __scrt_dllmain_crt_thread_detach

- ea: `0x180001d04`
- end: `0x180001d19`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001870`

## callees

- `0x18000270c`

## pseudocode

```c
char _scrt_dllmain_crt_thread_detach()
{
  _scrt_stub_for_acrt_uninitialize_critical();
  _scrt_stub_for_acrt_uninitialize_critical();
  return 1;
}

```

## disassembly

```asm
0x180001d04  sub     rsp, 28h
0x180001d08  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001d0d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001d12  mov     al, 1
0x180001d14  add     rsp, 28h
0x180001d18  retn
```
