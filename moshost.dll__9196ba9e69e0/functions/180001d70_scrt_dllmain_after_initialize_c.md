# __scrt_dllmain_after_initialize_c

- ea: `0x180001d70`
- end: `0x180001da4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800019d8`

## callees

- `0x180001d70`
- `0x180002320`
- `0x1800025ac`
- `0x1800025b8`
- `0x1800026aa`
- `0x1800026ce`

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
0x180001d70  sub     rsp, 28h
0x180001d74  call    __scrt_is_ucrt_dll_in_use
0x180001d79  test    eax, eax
0x180001d7b  jz      short loc_180001D84
0x180001d7d  call    __isa_available_init
0x180001d82  jmp     short loc_180001D9D
0x180001d84  call    _get_startup_argv_mode
0x180001d89  mov     ecx, eax; mode
0x180001d8b  call    _o__configure_narrow_argv_0
0x180001d90  test    eax, eax
0x180001d92  jz      short loc_180001D98
0x180001d94  xor     al, al
0x180001d96  jmp     short loc_180001D9F
0x180001d98  call    _initialize_narrow_environment
0x180001d9d  mov     al, 1
0x180001d9f  add     rsp, 28h
0x180001da3  retn
```
