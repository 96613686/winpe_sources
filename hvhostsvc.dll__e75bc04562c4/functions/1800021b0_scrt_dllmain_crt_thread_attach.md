# __scrt_dllmain_crt_thread_attach

- ea: `0x1800021b0`
- end: `0x1800021d8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001d90`

## callees

- `0x1800021b0`
- `0x180002e0c`

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
0x1800021b0  sub     rsp, 28h
0x1800021b4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800021b9  test    al, al
0x1800021bb  jnz     short loc_1800021C1
0x1800021bd  xor     al, al
0x1800021bf  jmp     short loc_1800021D3
0x1800021c1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800021c6  test    al, al
0x1800021c8  jnz     short loc_1800021D1
0x1800021ca  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800021cf  jmp     short loc_1800021BD
0x1800021d1  mov     al, 1
0x1800021d3  add     rsp, 28h
0x1800021d7  retn
```
