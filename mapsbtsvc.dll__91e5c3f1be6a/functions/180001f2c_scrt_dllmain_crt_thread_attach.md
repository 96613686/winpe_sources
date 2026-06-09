# __scrt_dllmain_crt_thread_attach

- ea: `0x180001f2c`
- end: `0x180001f54`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001af0`

## callees

- `0x180001f2c`
- `0x1800029b4`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180001f2c  sub     rsp, 28h
0x180001f30  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f35  test    al, al
0x180001f37  jnz     short loc_180001F3D
0x180001f39  xor     al, al
0x180001f3b  jmp     short loc_180001F4F
0x180001f3d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f42  test    al, al
0x180001f44  jnz     short loc_180001F4D
0x180001f46  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f4b  jmp     short loc_180001F39
0x180001f4d  mov     al, 1
0x180001f4f  add     rsp, 28h
0x180001f53  retn
```
