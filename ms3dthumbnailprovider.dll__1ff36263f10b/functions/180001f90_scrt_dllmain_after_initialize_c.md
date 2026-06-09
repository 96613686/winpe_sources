# __scrt_dllmain_after_initialize_c

- ea: `0x180001f90`
- end: `0x180001fc4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001bd8`

## callees

- `0x180001f90`
- `0x180002504`
- `0x180002790`
- `0x18000279c`
- `0x1800028b4`
- `0x1800028d8`

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
0x180001f90  sub     rsp, 28h
0x180001f94  call    __scrt_is_ucrt_dll_in_use
0x180001f99  test    eax, eax
0x180001f9b  jz      short loc_180001FA4
0x180001f9d  call    __isa_available_init
0x180001fa2  jmp     short loc_180001FBD
0x180001fa4  call    _get_startup_argv_mode
0x180001fa9  mov     ecx, eax; mode
0x180001fab  call    _o__configure_narrow_argv_0
0x180001fb0  test    eax, eax
0x180001fb2  jz      short loc_180001FB8
0x180001fb4  xor     al, al
0x180001fb6  jmp     short loc_180001FBF
0x180001fb8  call    _initialize_narrow_environment
0x180001fbd  mov     al, 1
0x180001fbf  add     rsp, 28h
0x180001fc3  retn
```
