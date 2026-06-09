# __scrt_dllmain_crt_thread_attach

- ea: `0x18000e4a8`
- end: `0x18000e4d0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000df80`

## callees

- `0x18000e4a8`
- `0x18000f190`

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
0x18000e4a8  sub     rsp, 28h
0x18000e4ac  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000e4b1  test    al, al
0x18000e4b3  jnz     short loc_18000E4B9
0x18000e4b5  xor     al, al
0x18000e4b7  jmp     short loc_18000E4CB
0x18000e4b9  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000e4be  test    al, al
0x18000e4c0  jnz     short loc_18000E4C9
0x18000e4c2  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000e4c7  jmp     short loc_18000E4B5
0x18000e4c9  mov     al, 1
0x18000e4cb  add     rsp, 28h
0x18000e4cf  retn
```
