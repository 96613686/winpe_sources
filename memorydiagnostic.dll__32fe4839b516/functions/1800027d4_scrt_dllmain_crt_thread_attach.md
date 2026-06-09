# __scrt_dllmain_crt_thread_attach

- ea: `0x1800027d4`
- end: `0x1800027fc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002330`

## callees

- `0x1800027d4`
- `0x1800034e0`

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
0x1800027d4  sub     rsp, 28h
0x1800027d8  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800027dd  test    al, al
0x1800027df  jnz     short loc_1800027E5
0x1800027e1  xor     al, al
0x1800027e3  jmp     short loc_1800027F7
0x1800027e5  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800027ea  test    al, al
0x1800027ec  jnz     short loc_1800027F5
0x1800027ee  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800027f3  jmp     short loc_1800027E1
0x1800027f5  mov     al, 1
0x1800027f7  add     rsp, 28h
0x1800027fb  retn
```
