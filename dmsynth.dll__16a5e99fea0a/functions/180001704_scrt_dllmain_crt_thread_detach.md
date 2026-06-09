# __scrt_dllmain_crt_thread_detach

- ea: `0x180001704`
- end: `0x180001719`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001180`

## callees

- `0x180001da8`

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
0x180001704  sub     rsp, 28h
0x180001708  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000170d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001712  mov     al, 1
0x180001714  add     rsp, 28h
0x180001718  retn
```
