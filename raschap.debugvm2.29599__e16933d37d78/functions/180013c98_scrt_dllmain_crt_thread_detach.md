# __scrt_dllmain_crt_thread_detach

- ea: `0x180013c98`
- end: `0x180013cad`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800137b0`

## callees

- `0x180014bcc`

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
0x180013c98  sub     rsp, 28h
0x180013c9c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180013ca1  call    __scrt_stub_for_acrt_uninitialize_critical
0x180013ca6  mov     al, 1
0x180013ca8  add     rsp, 28h
0x180013cac  retn
```
