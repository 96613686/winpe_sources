# __scrt_dllmain_crt_thread_attach

- ea: `0x1800078f8`
- end: `0x180007920`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800073d0`

## callees

- `0x1800078f8`
- `0x18000851c`

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
0x1800078f8  sub     rsp, 28h
0x1800078fc  call    __scrt_stub_for_acrt_uninitialize_critical
0x180007901  test    al, al
0x180007903  jnz     short loc_180007909
0x180007905  xor     al, al
0x180007907  jmp     short loc_18000791B
0x180007909  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000790e  test    al, al
0x180007910  jnz     short loc_180007919
0x180007912  call    __scrt_stub_for_acrt_uninitialize_critical
0x180007917  jmp     short loc_180007905
0x180007919  mov     al, 1
0x18000791b  add     rsp, 28h
0x18000791f  retn
```
