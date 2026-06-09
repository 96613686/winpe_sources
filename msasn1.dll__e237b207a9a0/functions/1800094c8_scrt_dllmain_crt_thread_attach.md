# __scrt_dllmain_crt_thread_attach

- ea: `0x1800094c8`
- end: `0x1800094f0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008fa0`

## callees

- `0x1800094c8`
- `0x180009bec`

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
0x1800094c8  sub     rsp, 28h
0x1800094cc  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800094d1  test    al, al
0x1800094d3  jnz     short loc_1800094D9
0x1800094d5  xor     al, al
0x1800094d7  jmp     short loc_1800094EB
0x1800094d9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800094de  test    al, al
0x1800094e0  jnz     short loc_1800094E9
0x1800094e2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800094e7  jmp     short loc_1800094D5
0x1800094e9  mov     al, 1
0x1800094eb  add     rsp, 28h
0x1800094ef  retn
```
