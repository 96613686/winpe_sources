# __scrt_dllmain_crt_thread_detach

- ea: `0x180014254`
- end: `0x180014269`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180013db0`

## callees

- `0x1800151e0`

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
0x180014254  sub     rsp, 28h
0x180014258  call    __scrt_stub_for_acrt_uninitialize_critical
0x18001425d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180014262  mov     al, 1
0x180014264  add     rsp, 28h
0x180014268  retn
```
