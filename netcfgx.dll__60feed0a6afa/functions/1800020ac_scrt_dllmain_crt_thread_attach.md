# __scrt_dllmain_crt_thread_attach

- ea: `0x1800020ac`
- end: `0x1800020d4`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001c20`

## callees

- `0x1800020ac`
- `0x180003024`

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
0x1800020ac  sub     rsp, 28h
0x1800020b0  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800020b5  test    al, al
0x1800020b7  jnz     short loc_1800020BD
0x1800020b9  xor     al, al
0x1800020bb  jmp     short loc_1800020CF
0x1800020bd  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800020c2  test    al, al
0x1800020c4  jnz     short loc_1800020CD
0x1800020c6  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800020cb  jmp     short loc_1800020B9
0x1800020cd  mov     al, 1
0x1800020cf  add     rsp, 28h
0x1800020d3  retn
```
