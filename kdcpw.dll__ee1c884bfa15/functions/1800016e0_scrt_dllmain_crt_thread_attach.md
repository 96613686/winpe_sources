# __scrt_dllmain_crt_thread_attach

- ea: `0x1800016e0`
- end: `0x180001708`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800012c0`

## callees

- `0x1800016e0`
- `0x180009340`

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
0x1800016e0  sub     rsp, 28h
0x1800016e4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016e9  test    al, al
0x1800016eb  jnz     short loc_1800016F1
0x1800016ed  xor     al, al
0x1800016ef  jmp     short loc_180001703
0x1800016f1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016f6  test    al, al
0x1800016f8  jnz     short loc_180001701
0x1800016fa  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016ff  jmp     short loc_1800016ED
0x180001701  mov     al, 1
0x180001703  add     rsp, 28h
0x180001707  retn
```
