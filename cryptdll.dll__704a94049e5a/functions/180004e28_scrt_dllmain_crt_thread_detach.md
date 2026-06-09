# __scrt_dllmain_crt_thread_detach

- ea: `0x180004e28`
- end: `0x180004e3d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800048d0`

## callees

- `0x180005640`

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
0x180004e28  sub     rsp, 28h
0x180004e2c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004e31  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004e36  mov     al, 1
0x180004e38  add     rsp, 28h
0x180004e3c  retn
```
