# __scrt_dllmain_crt_thread_attach

- ea: `0x180001694`
- end: `0x1800016bc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001140`

## callees

- `0x180001694`
- `0x180001e18`

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
0x180001694  sub     rsp, 28h
0x180001698  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000169d  test    al, al
0x18000169f  jnz     short loc_1800016A5
0x1800016a1  xor     al, al
0x1800016a3  jmp     short loc_1800016B7
0x1800016a5  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016aa  test    al, al
0x1800016ac  jnz     short loc_1800016B5
0x1800016ae  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016b3  jmp     short loc_1800016A1
0x1800016b5  mov     al, 1
0x1800016b7  add     rsp, 28h
0x1800016bb  retn
```
