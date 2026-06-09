# __scrt_dllmain_crt_thread_detach

- ea: `0x18000e904`
- end: `0x18000e919`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e3d0`

## callees

- `0x18000f028`

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
0x18000e904  sub     rsp, 28h
0x18000e908  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000e90d  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000e912  mov     al, 1
0x18000e914  add     rsp, 28h
0x18000e918  retn
```
