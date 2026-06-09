# __scrt_dllmain_crt_thread_attach

- ea: `0x1800017f0`
- end: `0x180001818`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001240`

## callees

- `0x1800017f0`
- `0x18000208c`

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
0x1800017f0  sub     rsp, 28h
0x1800017f4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017f9  test    al, al
0x1800017fb  jnz     short loc_180001801
0x1800017fd  xor     al, al
0x1800017ff  jmp     short loc_180001813
0x180001801  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001806  test    al, al
0x180001808  jnz     short loc_180001811
0x18000180a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000180f  jmp     short loc_1800017FD
0x180001811  mov     al, 1
0x180001813  add     rsp, 28h
0x180001817  retn
```
