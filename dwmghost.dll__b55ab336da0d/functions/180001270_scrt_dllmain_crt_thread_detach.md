# __scrt_dllmain_crt_thread_detach

- ea: `0x180001270`
- end: `0x180001285`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002330`

## callees

- `0x18000299c`

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
0x180001270  sub     rsp, 28h
0x180001274  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001279  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000127e  mov     al, 1
0x180001280  add     rsp, 28h
0x180001284  retn
```
