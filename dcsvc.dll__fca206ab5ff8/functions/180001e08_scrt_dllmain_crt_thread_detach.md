# __scrt_dllmain_crt_thread_detach

- ea: `0x180001e08`
- end: `0x180001e1d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001970`

## callees

- `0x180002cdc`

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
0x180001e08  sub     rsp, 28h
0x180001e0c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e11  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e16  mov     al, 1
0x180001e18  add     rsp, 28h
0x180001e1c  retn
```
