# __scrt_dllmain_crt_thread_attach

- ea: `0x180001b0c`
- end: `0x180001b34`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800016e0`

## callees

- `0x180001b0c`
- `0x1800025a4`

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
0x180001b0c  sub     rsp, 28h
0x180001b10  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001b15  test    al, al
0x180001b17  jnz     short loc_180001B1D
0x180001b19  xor     al, al
0x180001b1b  jmp     short loc_180001B2F
0x180001b1d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001b22  test    al, al
0x180001b24  jnz     short loc_180001B2D
0x180001b26  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001b2b  jmp     short loc_180001B19
0x180001b2d  mov     al, 1
0x180001b2f  add     rsp, 28h
0x180001b33  retn
```
