# __scrt_dllmain_crt_thread_detach

- ea: `0x180001c88`
- end: `0x180001c9d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001730`

## callees

- `0x180002604`

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
0x180001c88  sub     rsp, 28h
0x180001c8c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001c91  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001c96  mov     al, 1
0x180001c98  add     rsp, 28h
0x180001c9c  retn
```
