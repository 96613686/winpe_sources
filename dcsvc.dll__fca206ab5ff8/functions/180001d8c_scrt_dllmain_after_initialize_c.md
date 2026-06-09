# __scrt_dllmain_after_initialize_c

- ea: `0x180001d8c`
- end: `0x180001dc0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800019c8`

## callees

- `0x180001d8c`
- `0x1800022f0`
- `0x18000257c`
- `0x180002588`
- `0x18000262a`
- `0x18000264e`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  _crt_argv_mode startup_argv_mode; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    startup_argv_mode = get_startup_argv_mode();
    if ( o__configure_narrow_argv_0(startup_argv_mode) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180001d8c  sub     rsp, 28h
0x180001d90  call    __scrt_is_ucrt_dll_in_use
0x180001d95  test    eax, eax
0x180001d97  jz      short loc_180001DA0
0x180001d99  call    __isa_available_init
0x180001d9e  jmp     short loc_180001DB9
0x180001da0  call    _get_startup_argv_mode
0x180001da5  mov     ecx, eax; mode
0x180001da7  call    _o__configure_narrow_argv_0
0x180001dac  test    eax, eax
0x180001dae  jz      short loc_180001DB4
0x180001db0  xor     al, al
0x180001db2  jmp     short loc_180001DBB
0x180001db4  call    _initialize_narrow_environment
0x180001db9  mov     al, 1
0x180001dbb  add     rsp, 28h
0x180001dbf  retn
```
