# __scrt_dllmain_crt_thread_attach

- ea: `0x180001780`
- end: `0x1800017a8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001360`

## callees

- `0x180001780`
- `0x180002354`

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
0x180001780  sub     rsp, 28h
0x180001784  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001789  test    al, al
0x18000178b  jnz     short loc_180001791
0x18000178d  xor     al, al
0x18000178f  jmp     short loc_1800017A3
0x180001791  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001796  test    al, al
0x180001798  jnz     short loc_1800017A1
0x18000179a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000179f  jmp     short loc_18000178D
0x1800017a1  mov     al, 1
0x1800017a3  add     rsp, 28h
0x1800017a7  retn
```
