# __scrt_dllmain_crt_thread_detach

- ea: `0x180003c78`
- end: `0x180003c8d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003720`

## callees

- `0x180004554`

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
0x180003c78  sub     rsp, 28h
0x180003c7c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003c81  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003c86  mov     al, 1
0x180003c88  add     rsp, 28h
0x180003c8c  retn
```
