# __scrt_dllmain_crt_thread_attach

- ea: `0x180001634`
- end: `0x18000165c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800010f0`

## callees

- `0x180001634`
- `0x180001df4`

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
0x180001634  sub     rsp, 28h
0x180001638  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000163d  test    al, al
0x18000163f  jnz     short loc_180001645
0x180001641  xor     al, al
0x180001643  jmp     short loc_180001657
0x180001645  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000164a  test    al, al
0x18000164c  jnz     short loc_180001655
0x18000164e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001653  jmp     short loc_180001641
0x180001655  mov     al, 1
0x180001657  add     rsp, 28h
0x18000165b  retn
```
