# __scrt_dllmain_crt_thread_attach

- ea: `0x180002320`
- end: `0x180002348`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f00`

## callees

- `0x180002320`
- `0x180002ec4`

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
0x180002320  sub     rsp, 28h
0x180002324  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002329  test    al, al
0x18000232b  jnz     short loc_180002331
0x18000232d  xor     al, al
0x18000232f  jmp     short loc_180002343
0x180002331  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002336  test    al, al
0x180002338  jnz     short loc_180002341
0x18000233a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000233f  jmp     short loc_18000232D
0x180002341  mov     al, 1
0x180002343  add     rsp, 28h
0x180002347  retn
```
