# __scrt_dllmain_crt_thread_attach

- ea: `0x180020430`
- end: `0x180020458`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001fee0`

## callees

- `0x180020430`
- `0x18002134c`

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
0x180020430  sub     rsp, 28h
0x180020434  call    __scrt_stub_for_acrt_uninitialize_critical
0x180020439  test    al, al
0x18002043b  jnz     short loc_180020441
0x18002043d  xor     al, al
0x18002043f  jmp     short loc_180020453
0x180020441  call    __scrt_stub_for_acrt_uninitialize_critical
0x180020446  test    al, al
0x180020448  jnz     short loc_180020451
0x18002044a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18002044f  jmp     short loc_18002043D
0x180020451  mov     al, 1
0x180020453  add     rsp, 28h
0x180020457  retn
```
