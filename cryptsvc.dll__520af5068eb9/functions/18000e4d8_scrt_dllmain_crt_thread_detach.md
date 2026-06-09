# __scrt_dllmain_crt_thread_detach

- ea: `0x18000e4d8`
- end: `0x18000e4ed`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000df80`

## callees

- `0x18000f190`

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
0x18000e4d8  sub     rsp, 28h
0x18000e4dc  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000e4e1  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000e4e6  mov     al, 1
0x18000e4e8  add     rsp, 28h
0x18000e4ec  retn
```
