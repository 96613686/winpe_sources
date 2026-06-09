# __scrt_dllmain_after_initialize_c

- ea: `0x18000fa74`
- end: `0x18000faa8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000f6f8`

## callees

- `0x18000fa74`
- `0x18000ffe0`
- `0x18001026c`
- `0x180010278`
- `0x180010312`
- `0x180010336`

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
0x18000fa74  sub     rsp, 28h
0x18000fa78  call    __scrt_is_ucrt_dll_in_use
0x18000fa7d  test    eax, eax
0x18000fa7f  jz      short loc_18000FA88
0x18000fa81  call    __isa_available_init
0x18000fa86  jmp     short loc_18000FAA1
0x18000fa88  call    _get_startup_argv_mode
0x18000fa8d  mov     ecx, eax; mode
0x18000fa8f  call    _o__configure_narrow_argv_0
0x18000fa94  test    eax, eax
0x18000fa96  jz      short loc_18000FA9C
0x18000fa98  xor     al, al
0x18000fa9a  jmp     short loc_18000FAA3
0x18000fa9c  call    _initialize_narrow_environment
0x18000faa1  mov     al, 1
0x18000faa3  add     rsp, 28h
0x18000faa7  retn
```
