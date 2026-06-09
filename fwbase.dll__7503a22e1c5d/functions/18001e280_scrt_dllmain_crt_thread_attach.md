# __scrt_dllmain_crt_thread_attach

- ea: `0x18001e280`
- end: `0x18001e2a8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001de50`

## callees

- `0x18001e280`
- `0x18001f140`

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
0x18001e280  sub     rsp, 28h
0x18001e284  call    __scrt_stub_for_acrt_uninitialize_critical
0x18001e289  test    al, al
0x18001e28b  jnz     short loc_18001E291
0x18001e28d  xor     al, al
0x18001e28f  jmp     short loc_18001E2A3
0x18001e291  call    __scrt_stub_for_acrt_uninitialize_critical
0x18001e296  test    al, al
0x18001e298  jnz     short loc_18001E2A1
0x18001e29a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18001e29f  jmp     short loc_18001E28D
0x18001e2a1  mov     al, 1
0x18001e2a3  add     rsp, 28h
0x18001e2a7  retn
```
