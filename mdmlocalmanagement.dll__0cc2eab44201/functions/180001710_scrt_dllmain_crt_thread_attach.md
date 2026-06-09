# __scrt_dllmain_crt_thread_attach

- ea: `0x180001710`
- end: `0x180001738`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800012e0`

## callees

- `0x180001710`
- `0x1800020d8`

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
0x180001710  sub     rsp, 28h
0x180001714  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001719  test    al, al
0x18000171b  jnz     short loc_180001721
0x18000171d  xor     al, al
0x18000171f  jmp     short loc_180001733
0x180001721  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001726  test    al, al
0x180001728  jnz     short loc_180001731
0x18000172a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000172f  jmp     short loc_18000171D
0x180001731  mov     al, 1
0x180001733  add     rsp, 28h
0x180001737  retn
```
