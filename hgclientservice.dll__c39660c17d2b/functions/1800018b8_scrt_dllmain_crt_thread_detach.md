# __scrt_dllmain_crt_thread_detach

- ea: `0x1800018b8`
- end: `0x1800018cd`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001400`

## callees

- `0x180002e64`

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
0x1800018b8  sub     rsp, 28h
0x1800018bc  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018c1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018c6  mov     al, 1
0x1800018c8  add     rsp, 28h
0x1800018cc  retn
```
