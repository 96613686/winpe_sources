# __scrt_dllmain_crt_thread_attach

- ea: `0x180002f68`
- end: `0x180002f90`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002ae0`

## callees

- `0x180002f68`
- `0x180003ac8`

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
0x180002f68  sub     rsp, 28h
0x180002f6c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002f71  test    al, al
0x180002f73  jnz     short loc_180002F79
0x180002f75  xor     al, al
0x180002f77  jmp     short loc_180002F8B
0x180002f79  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002f7e  test    al, al
0x180002f80  jnz     short loc_180002F89
0x180002f82  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002f87  jmp     short loc_180002F75
0x180002f89  mov     al, 1
0x180002f8b  add     rsp, 28h
0x180002f8f  retn
```
