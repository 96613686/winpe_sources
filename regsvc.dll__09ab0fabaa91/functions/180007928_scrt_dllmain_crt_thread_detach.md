# __scrt_dllmain_crt_thread_detach

- ea: `0x180007928`
- end: `0x18000793d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800073d0`

## callees

- `0x18000851c`

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
0x180007928  sub     rsp, 28h
0x18000792c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180007931  call    __scrt_stub_for_acrt_uninitialize_critical
0x180007936  mov     al, 1
0x180007938  add     rsp, 28h
0x18000793c  retn
```
