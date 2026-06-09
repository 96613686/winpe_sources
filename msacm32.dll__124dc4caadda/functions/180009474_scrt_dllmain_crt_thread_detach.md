# __scrt_dllmain_crt_thread_detach

- ea: `0x180009474`
- end: `0x180009489`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008f00`

## callees

- `0x18000ac94`

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
0x180009474  sub     rsp, 28h
0x180009478  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000947d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180009482  mov     al, 1
0x180009484  add     rsp, 28h
0x180009488  retn
```
