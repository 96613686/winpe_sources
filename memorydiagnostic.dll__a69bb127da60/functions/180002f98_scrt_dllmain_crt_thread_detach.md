# __scrt_dllmain_crt_thread_detach

- ea: `0x180002f98`
- end: `0x180002fad`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002ae0`

## callees

- `0x180003ac8`

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
0x180002f98  sub     rsp, 28h
0x180002f9c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002fa1  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002fa6  mov     al, 1
0x180002fa8  add     rsp, 28h
0x180002fac  retn
```
