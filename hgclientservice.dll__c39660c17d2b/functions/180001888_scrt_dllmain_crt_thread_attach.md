# __scrt_dllmain_crt_thread_attach

- ea: `0x180001888`
- end: `0x1800018b0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001400`

## callees

- `0x180001888`
- `0x180002e64`

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
0x180001888  sub     rsp, 28h
0x18000188c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001891  test    al, al
0x180001893  jnz     short loc_180001899
0x180001895  xor     al, al
0x180001897  jmp     short loc_1800018AB
0x180001899  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000189e  test    al, al
0x1800018a0  jnz     short loc_1800018A9
0x1800018a2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018a7  jmp     short loc_180001895
0x1800018a9  mov     al, 1
0x1800018ab  add     rsp, 28h
0x1800018af  retn
```
