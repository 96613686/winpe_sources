# __scrt_dllmain_crt_thread_attach

- ea: `0x18000c880`
- end: `0x18000c8a8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c490`

## callees

- `0x18000c880`
- `0x18000d1c8`

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
0x18000c880  sub     rsp, 28h
0x18000c884  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000c889  test    al, al
0x18000c88b  jnz     short loc_18000C891
0x18000c88d  xor     al, al
0x18000c88f  jmp     short loc_18000C8A3
0x18000c891  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000c896  test    al, al
0x18000c898  jnz     short loc_18000C8A1
0x18000c89a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000c89f  jmp     short loc_18000C88D
0x18000c8a1  mov     al, 1
0x18000c8a3  add     rsp, 28h
0x18000c8a7  retn
```
