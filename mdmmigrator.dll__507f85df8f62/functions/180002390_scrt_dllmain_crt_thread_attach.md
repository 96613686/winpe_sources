# __scrt_dllmain_crt_thread_attach

- ea: `0x180002390`
- end: `0x1800023b8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f70`

## callees

- `0x180002390`
- `0x1800038cc`

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
0x180002390  sub     rsp, 28h
0x180002394  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002399  test    al, al
0x18000239b  jnz     short loc_1800023A1
0x18000239d  xor     al, al
0x18000239f  jmp     short loc_1800023B3
0x1800023a1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800023a6  test    al, al
0x1800023a8  jnz     short loc_1800023B1
0x1800023aa  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800023af  jmp     short loc_18000239D
0x1800023b1  mov     al, 1
0x1800023b3  add     rsp, 28h
0x1800023b7  retn
```
