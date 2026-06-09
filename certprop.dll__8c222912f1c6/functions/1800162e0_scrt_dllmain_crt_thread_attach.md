# __scrt_dllmain_crt_thread_attach

- ea: `0x1800162e0`
- end: `0x180016308`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015d20`

## callees

- `0x1800162e0`
- `0x18001788c`

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
0x1800162e0  sub     rsp, 28h
0x1800162e4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800162e9  test    al, al
0x1800162eb  jnz     short loc_1800162F1
0x1800162ed  xor     al, al
0x1800162ef  jmp     short loc_180016303
0x1800162f1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800162f6  test    al, al
0x1800162f8  jnz     short loc_180016301
0x1800162fa  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800162ff  jmp     short loc_1800162ED
0x180016301  mov     al, 1
0x180016303  add     rsp, 28h
0x180016307  retn
```
