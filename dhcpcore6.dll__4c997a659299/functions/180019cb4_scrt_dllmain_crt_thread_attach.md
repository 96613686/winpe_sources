# __scrt_dllmain_crt_thread_attach

- ea: `0x180019cb4`
- end: `0x180019cdc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180019760`

## callees

- `0x180019cb4`
- `0x18001b024`

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
0x180019cb4  sub     rsp, 28h
0x180019cb8  call    __scrt_stub_for_acrt_uninitialize_critical
0x180019cbd  test    al, al
0x180019cbf  jnz     short loc_180019CC5
0x180019cc1  xor     al, al
0x180019cc3  jmp     short loc_180019CD7
0x180019cc5  call    __scrt_stub_for_acrt_uninitialize_critical
0x180019cca  test    al, al
0x180019ccc  jnz     short loc_180019CD5
0x180019cce  call    __scrt_stub_for_acrt_uninitialize_critical
0x180019cd3  jmp     short loc_180019CC1
0x180019cd5  mov     al, 1
0x180019cd7  add     rsp, 28h
0x180019cdb  retn
```
