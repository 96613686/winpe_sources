# __scrt_dllmain_crt_thread_attach

- ea: `0x180001d24`
- end: `0x180001d4c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800016f0`

## callees

- `0x180001d24`
- `0x1800027f4`

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
0x180001d24  sub     rsp, 28h
0x180001d28  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001d2d  test    al, al
0x180001d2f  jnz     short loc_180001D35
0x180001d31  xor     al, al
0x180001d33  jmp     short loc_180001D47
0x180001d35  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001d3a  test    al, al
0x180001d3c  jnz     short loc_180001D45
0x180001d3e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001d43  jmp     short loc_180001D31
0x180001d45  mov     al, 1
0x180001d47  add     rsp, 28h
0x180001d4b  retn
```
