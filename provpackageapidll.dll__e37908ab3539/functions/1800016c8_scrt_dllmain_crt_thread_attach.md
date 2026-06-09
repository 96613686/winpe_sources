# __scrt_dllmain_crt_thread_attach

- ea: `0x1800016c8`
- end: `0x1800016f0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011a0`

## callees

- `0x1800016c8`
- `0x1800022f0`

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
0x1800016c8  sub     rsp, 28h
0x1800016cc  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016d1  test    al, al
0x1800016d3  jnz     short loc_1800016D9
0x1800016d5  xor     al, al
0x1800016d7  jmp     short loc_1800016EB
0x1800016d9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016de  test    al, al
0x1800016e0  jnz     short loc_1800016E9
0x1800016e2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016e7  jmp     short loc_1800016D5
0x1800016e9  mov     al, 1
0x1800016eb  add     rsp, 28h
0x1800016ef  retn
```
