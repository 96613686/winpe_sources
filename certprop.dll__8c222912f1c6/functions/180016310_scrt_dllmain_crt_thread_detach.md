# __scrt_dllmain_crt_thread_detach

- ea: `0x180016310`
- end: `0x180016325`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180015d20`

## callees

- `0x18001788c`

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
0x180016310  sub     rsp, 28h
0x180016314  call    __scrt_stub_for_acrt_uninitialize_critical
0x180016319  call    __scrt_stub_for_acrt_uninitialize_critical
0x18001631e  mov     al, 1
0x180016320  add     rsp, 28h
0x180016324  retn
```
