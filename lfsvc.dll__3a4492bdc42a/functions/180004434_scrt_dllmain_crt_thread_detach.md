# __scrt_dllmain_crt_thread_detach

- ea: `0x180004434`
- end: `0x180004449`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003f90`

## callees

- `0x180004db4`

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
0x180004434  sub     rsp, 28h
0x180004438  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000443d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004442  mov     al, 1
0x180004444  add     rsp, 28h
0x180004448  retn
```
