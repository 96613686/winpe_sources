# __scrt_dllmain_crt_thread_attach

- ea: `0x18000b4c0`
- end: `0x18000b4e8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b090`

## callees

- `0x18000b4c0`
- `0x18000c350`

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
0x18000b4c0  sub     rsp, 28h
0x18000b4c4  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000b4c9  test    al, al
0x18000b4cb  jnz     short loc_18000B4D1
0x18000b4cd  xor     al, al
0x18000b4cf  jmp     short loc_18000B4E3
0x18000b4d1  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000b4d6  test    al, al
0x18000b4d8  jnz     short loc_18000B4E1
0x18000b4da  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000b4df  jmp     short loc_18000B4CD
0x18000b4e1  mov     al, 1
0x18000b4e3  add     rsp, 28h
0x18000b4e7  retn
```
