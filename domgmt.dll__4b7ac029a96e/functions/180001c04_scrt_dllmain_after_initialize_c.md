# __scrt_dllmain_after_initialize_c

- ea: `0x180001c04`
- end: `0x180001c38`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001888`

## callees

- `0x180001c04`
- `0x180002550`
- `0x1800027dc`
- `0x1800027e8`
- `0x1800028da`
- `0x1800028fe`

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
0x180001c04  sub     rsp, 28h
0x180001c08  call    __scrt_is_ucrt_dll_in_use
0x180001c0d  test    eax, eax
0x180001c0f  jz      short loc_180001C18
0x180001c11  call    __isa_available_init
0x180001c16  jmp     short loc_180001C31
0x180001c18  call    _get_startup_argv_mode
0x180001c1d  mov     ecx, eax; mode
0x180001c1f  call    _o__configure_narrow_argv_0
0x180001c24  test    eax, eax
0x180001c26  jz      short loc_180001C2C
0x180001c28  xor     al, al
0x180001c2a  jmp     short loc_180001C33
0x180001c2c  call    _initialize_narrow_environment
0x180001c31  mov     al, 1
0x180001c33  add     rsp, 28h
0x180001c37  retn
```
