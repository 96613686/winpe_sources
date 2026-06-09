# __scrt_dllmain_crt_thread_detach

- ea: `0x1800016b0`
- end: `0x1800016c5`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001260`

## callees

- `0x180001f50`

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
0x1800016b0  sub     rsp, 28h
0x1800016b4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016b9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016be  mov     al, 1
0x1800016c0  add     rsp, 28h
0x1800016c4  retn
```
