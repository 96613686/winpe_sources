# __scrt_dllmain_crt_thread_attach

- ea: `0x1800015b0`
- end: `0x1800015d8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001190`

## callees

- `0x1800015b0`
- `0x180002c20`
- `0x180002c3c`
- `0x180005364`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !_vcrt_thread_attach() )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _vcrt_thread_detach();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800015b0  sub     rsp, 28h
0x1800015b4  call    __vcrt_thread_attach
0x1800015b9  test    al, al
0x1800015bb  jnz     short loc_1800015C1
0x1800015bd  xor     al, al
0x1800015bf  jmp     short loc_1800015D3
0x1800015c1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015c6  test    al, al
0x1800015c8  jnz     short loc_1800015D1
0x1800015ca  call    __vcrt_thread_detach
0x1800015cf  jmp     short loc_1800015BD
0x1800015d1  mov     al, 1
0x1800015d3  add     rsp, 28h
0x1800015d7  retn
```
