# __scrt_dllmain_crt_thread_attach

- ea: `0x1800016b0`
- end: `0x1800016d8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001290`

## callees

- `0x1800016b0`
- `0x1800020d0`

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
0x1800016b0  sub     rsp, 28h
0x1800016b4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016b9  test    al, al
0x1800016bb  jnz     short loc_1800016C1
0x1800016bd  xor     al, al
0x1800016bf  jmp     short loc_1800016D3
0x1800016c1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016c6  test    al, al
0x1800016c8  jnz     short loc_1800016D1
0x1800016ca  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016cf  jmp     short loc_1800016BD
0x1800016d1  mov     al, 1
0x1800016d3  add     rsp, 28h
0x1800016d7  retn
```
