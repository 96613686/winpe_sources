# __scrt_dllmain_crt_thread_attach

- ea: `0x180002d84`
- end: `0x180002dac`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002940`

## callees

- `0x180002d84`
- `0x1800038b4`

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
0x180002d84  sub     rsp, 28h
0x180002d88  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002d8d  test    al, al
0x180002d8f  jnz     short loc_180002D95
0x180002d91  xor     al, al
0x180002d93  jmp     short loc_180002DA7
0x180002d95  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002d9a  test    al, al
0x180002d9c  jnz     short loc_180002DA5
0x180002d9e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002da3  jmp     short loc_180002D91
0x180002da5  mov     al, 1
0x180002da7  add     rsp, 28h
0x180002dab  retn
```
