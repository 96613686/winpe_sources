# __scrt_dllmain_crt_thread_detach

- ea: `0x180002694`
- end: `0x1800026a9`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002120`

## callees

- `0x18000355c`

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
0x180002694  sub     rsp, 28h
0x180002698  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000269d  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800026a2  mov     al, 1
0x1800026a4  add     rsp, 28h
0x1800026a8  retn
```
