# __scrt_dllmain_crt_thread_attach

- ea: `0x18000abe0`
- end: `0x18000ac08`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a7c0`

## callees

- `0x18000abe0`
- `0x18000bfbc`

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
0x18000abe0  sub     rsp, 28h
0x18000abe4  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000abe9  test    al, al
0x18000abeb  jnz     short loc_18000ABF1
0x18000abed  xor     al, al
0x18000abef  jmp     short loc_18000AC03
0x18000abf1  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000abf6  test    al, al
0x18000abf8  jnz     short loc_18000AC01
0x18000abfa  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000abff  jmp     short loc_18000ABED
0x18000ac01  mov     al, 1
0x18000ac03  add     rsp, 28h
0x18000ac07  retn
```
