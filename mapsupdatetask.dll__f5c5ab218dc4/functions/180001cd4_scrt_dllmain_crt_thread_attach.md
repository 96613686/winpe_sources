# __scrt_dllmain_crt_thread_attach

- ea: `0x180001cd4`
- end: `0x180001cfc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001870`

## callees

- `0x180001cd4`
- `0x18000270c`

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
0x180001cd4  sub     rsp, 28h
0x180001cd8  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001cdd  test    al, al
0x180001cdf  jnz     short loc_180001CE5
0x180001ce1  xor     al, al
0x180001ce3  jmp     short loc_180001CF7
0x180001ce5  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001cea  test    al, al
0x180001cec  jnz     short loc_180001CF5
0x180001cee  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001cf3  jmp     short loc_180001CE1
0x180001cf5  mov     al, 1
0x180001cf7  add     rsp, 28h
0x180001cfb  retn
```
