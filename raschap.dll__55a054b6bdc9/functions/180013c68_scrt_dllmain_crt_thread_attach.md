# __scrt_dllmain_crt_thread_attach

- ea: `0x180013c68`
- end: `0x180013c90`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800137b0`

## callees

- `0x180013c68`
- `0x180014bcc`

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
0x180013c68  sub     rsp, 28h
0x180013c6c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180013c71  test    al, al
0x180013c73  jnz     short loc_180013C79
0x180013c75  xor     al, al
0x180013c77  jmp     short loc_180013C8B
0x180013c79  call    __scrt_stub_for_acrt_uninitialize_critical
0x180013c7e  test    al, al
0x180013c80  jnz     short loc_180013C89
0x180013c82  call    __scrt_stub_for_acrt_uninitialize_critical
0x180013c87  jmp     short loc_180013C75
0x180013c89  mov     al, 1
0x180013c8b  add     rsp, 28h
0x180013c8f  retn
```
