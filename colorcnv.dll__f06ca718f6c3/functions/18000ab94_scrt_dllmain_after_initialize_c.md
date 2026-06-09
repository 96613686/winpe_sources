# __scrt_dllmain_after_initialize_c

- ea: `0x18000ab94`
- end: `0x18000abc8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a818`

## callees

- `0x18000ab94`
- `0x18000b0d0`
- `0x18000b35c`
- `0x18000b368`
- `0x18000b3ce`
- `0x18000b3f2`

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
0x18000ab94  sub     rsp, 28h
0x18000ab98  call    __scrt_is_ucrt_dll_in_use
0x18000ab9d  test    eax, eax
0x18000ab9f  jz      short loc_18000ABA8
0x18000aba1  call    __isa_available_init
0x18000aba6  jmp     short loc_18000ABC1
0x18000aba8  call    _get_startup_argv_mode
0x18000abad  mov     ecx, eax; mode
0x18000abaf  call    _o__configure_narrow_argv_0
0x18000abb4  test    eax, eax
0x18000abb6  jz      short loc_18000ABBC
0x18000abb8  xor     al, al
0x18000abba  jmp     short loc_18000ABC3
0x18000abbc  call    _initialize_narrow_environment
0x18000abc1  mov     al, 1
0x18000abc3  add     rsp, 28h
0x18000abc7  retn
```
