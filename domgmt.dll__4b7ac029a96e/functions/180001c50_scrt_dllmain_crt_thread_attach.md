# __scrt_dllmain_crt_thread_attach

- ea: `0x180001c50`
- end: `0x180001c78`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001830`

## callees

- `0x180001c50`
- `0x180002fe4`

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
0x180001c50  sub     rsp, 28h
0x180001c54  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001c59  test    al, al
0x180001c5b  jnz     short loc_180001C61
0x180001c5d  xor     al, al
0x180001c5f  jmp     short loc_180001C73
0x180001c61  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001c66  test    al, al
0x180001c68  jnz     short loc_180001C71
0x180001c6a  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001c6f  jmp     short loc_180001C5D
0x180001c71  mov     al, 1
0x180001c73  add     rsp, 28h
0x180001c77  retn
```
