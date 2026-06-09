# __scrt_dllmain_crt_thread_attach

- ea: `0x180001644`
- end: `0x18000166c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800010f0`

## callees

- `0x180001644`
- `0x180001d30`

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
0x180001644  sub     rsp, 28h
0x180001648  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000164d  test    al, al
0x18000164f  jnz     short loc_180001655
0x180001651  xor     al, al
0x180001653  jmp     short loc_180001667
0x180001655  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000165a  test    al, al
0x18000165c  jnz     short loc_180001665
0x18000165e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001663  jmp     short loc_180001651
0x180001665  mov     al, 1
0x180001667  add     rsp, 28h
0x18000166b  retn
```
