# __scrt_dllmain_crt_thread_attach

- ea: `0x180002664`
- end: `0x18000268c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002120`

## callees

- `0x180002664`
- `0x18000355c`

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
0x180002664  sub     rsp, 28h
0x180002668  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000266d  test    al, al
0x18000266f  jnz     short loc_180002675
0x180002671  xor     al, al
0x180002673  jmp     short loc_180002687
0x180002675  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000267a  test    al, al
0x18000267c  jnz     short loc_180002685
0x18000267e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002683  jmp     short loc_180002671
0x180002685  mov     al, 1
0x180002687  add     rsp, 28h
0x18000268b  retn
```
