# __scrt_dllmain_crt_thread_attach

- ea: `0x180001ec4`
- end: `0x180001eec`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001970`

## callees

- `0x180001ec4`
- `0x1800026d8`

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
0x180001ec4  sub     rsp, 28h
0x180001ec8  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001ecd  test    al, al
0x180001ecf  jnz     short loc_180001ED5
0x180001ed1  xor     al, al
0x180001ed3  jmp     short loc_180001EE7
0x180001ed5  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001eda  test    al, al
0x180001edc  jnz     short loc_180001EE5
0x180001ede  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001ee3  jmp     short loc_180001ED1
0x180001ee5  mov     al, 1
0x180001ee7  add     rsp, 28h
0x180001eeb  retn
```
