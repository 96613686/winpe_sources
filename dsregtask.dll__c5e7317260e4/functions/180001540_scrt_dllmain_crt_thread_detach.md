# __scrt_dllmain_crt_thread_detach

- ea: `0x180001540`
- end: `0x180001555`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800010f0`

## callees

- `0x180001df8`

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
0x180001540  sub     rsp, 28h
0x180001544  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001549  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000154e  mov     al, 1
0x180001550  add     rsp, 28h
0x180001554  retn
```
