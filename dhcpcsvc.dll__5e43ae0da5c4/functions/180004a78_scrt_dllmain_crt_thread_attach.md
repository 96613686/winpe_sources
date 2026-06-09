# __scrt_dllmain_crt_thread_attach

- ea: `0x180004a78`
- end: `0x180004aa0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004550`

## callees

- `0x180004a78`
- `0x18000559c`

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
0x180004a78  sub     rsp, 28h
0x180004a7c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004a81  test    al, al
0x180004a83  jnz     short loc_180004A89
0x180004a85  xor     al, al
0x180004a87  jmp     short loc_180004A9B
0x180004a89  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004a8e  test    al, al
0x180004a90  jnz     short loc_180004A99
0x180004a92  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004a97  jmp     short loc_180004A85
0x180004a99  mov     al, 1
0x180004a9b  add     rsp, 28h
0x180004a9f  retn
```
