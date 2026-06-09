# __scrt_dllmain_crt_thread_attach

- ea: `0x180003368`
- end: `0x180003390`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002e40`

## callees

- `0x180003368`
- `0x180004e14`

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
0x180003368  sub     rsp, 28h
0x18000336c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003371  test    al, al
0x180003373  jnz     short loc_180003379
0x180003375  xor     al, al
0x180003377  jmp     short loc_18000338B
0x180003379  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000337e  test    al, al
0x180003380  jnz     short loc_180003389
0x180003382  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003387  jmp     short loc_180003375
0x180003389  mov     al, 1
0x18000338b  add     rsp, 28h
0x18000338f  retn
```
