# __scrt_dllmain_crt_thread_attach

- ea: `0x180001c58`
- end: `0x180001c80`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001730`

## callees

- `0x180001c58`
- `0x180002604`

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
0x180001c58  sub     rsp, 28h
0x180001c5c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001c61  test    al, al
0x180001c63  jnz     short loc_180001C69
0x180001c65  xor     al, al
0x180001c67  jmp     short loc_180001C7B
0x180001c69  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001c6e  test    al, al
0x180001c70  jnz     short loc_180001C79
0x180001c72  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001c77  jmp     short loc_180001C65
0x180001c79  mov     al, 1
0x180001c7b  add     rsp, 28h
0x180001c7f  retn
```
