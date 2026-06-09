# __scrt_dllmain_crt_thread_attach

- ea: `0x180001dbc`
- end: `0x180001de4`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001980`

## callees

- `0x180001dbc`
- `0x1800029cc`

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
0x180001dbc  sub     rsp, 28h
0x180001dc0  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001dc5  test    al, al
0x180001dc7  jnz     short loc_180001DCD
0x180001dc9  xor     al, al
0x180001dcb  jmp     short loc_180001DDF
0x180001dcd  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001dd2  test    al, al
0x180001dd4  jnz     short loc_180001DDD
0x180001dd6  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001ddb  jmp     short loc_180001DC9
0x180001ddd  mov     al, 1
0x180001ddf  add     rsp, 28h
0x180001de3  retn
```
