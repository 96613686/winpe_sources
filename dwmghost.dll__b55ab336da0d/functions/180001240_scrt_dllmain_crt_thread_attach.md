# __scrt_dllmain_crt_thread_attach

- ea: `0x180001240`
- end: `0x180001268`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002330`

## callees

- `0x180001240`
- `0x18000299c`

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
0x180001240  sub     rsp, 28h
0x180001244  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001249  test    al, al
0x18000124b  jnz     short loc_180001251
0x18000124d  xor     al, al
0x18000124f  jmp     short loc_180001263
0x180001251  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001256  test    al, al
0x180001258  jnz     short loc_180001261
0x18000125a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000125f  jmp     short loc_18000124D
0x180001261  mov     al, 1
0x180001263  add     rsp, 28h
0x180001267  retn
```
