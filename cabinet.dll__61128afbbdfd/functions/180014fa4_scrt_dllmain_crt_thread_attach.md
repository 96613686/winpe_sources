# __scrt_dllmain_crt_thread_attach

- ea: `0x180014fa4`
- end: `0x180014fcc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180014a50`

## callees

- `0x180014fa4`
- `0x1800156d4`

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
0x180014fa4  sub     rsp, 28h
0x180014fa8  call    __scrt_stub_for_acrt_uninitialize_critical
0x180014fad  test    al, al
0x180014faf  jnz     short loc_180014FB5
0x180014fb1  xor     al, al
0x180014fb3  jmp     short loc_180014FC7
0x180014fb5  call    __scrt_stub_for_acrt_uninitialize_critical
0x180014fba  test    al, al
0x180014fbc  jnz     short loc_180014FC5
0x180014fbe  call    __scrt_stub_for_acrt_uninitialize_critical
0x180014fc3  jmp     short loc_180014FB1
0x180014fc5  mov     al, 1
0x180014fc7  add     rsp, 28h
0x180014fcb  retn
```
