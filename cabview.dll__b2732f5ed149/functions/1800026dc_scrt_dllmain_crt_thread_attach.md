# __scrt_dllmain_crt_thread_attach

- ea: `0x1800026dc`
- end: `0x180002704`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800022b0`

## callees

- `0x1800026dc`
- `0x180003050`

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
0x1800026dc  sub     rsp, 28h
0x1800026e0  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800026e5  test    al, al
0x1800026e7  jnz     short loc_1800026ED
0x1800026e9  xor     al, al
0x1800026eb  jmp     short loc_1800026FF
0x1800026ed  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800026f2  test    al, al
0x1800026f4  jnz     short loc_1800026FD
0x1800026f6  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800026fb  jmp     short loc_1800026E9
0x1800026fd  mov     al, 1
0x1800026ff  add     rsp, 28h
0x180002703  retn
```
