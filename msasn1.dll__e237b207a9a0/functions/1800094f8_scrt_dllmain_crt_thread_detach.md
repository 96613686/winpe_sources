# __scrt_dllmain_crt_thread_detach

- ea: `0x1800094f8`
- end: `0x18000950d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008fa0`

## callees

- `0x180009bec`

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
0x1800094f8  sub     rsp, 28h
0x1800094fc  call    __scrt_stub_for_acrt_uninitialize_critical
0x180009501  call    __scrt_stub_for_acrt_uninitialize_critical
0x180009506  mov     al, 1
0x180009508  add     rsp, 28h
0x18000950c  retn
```
