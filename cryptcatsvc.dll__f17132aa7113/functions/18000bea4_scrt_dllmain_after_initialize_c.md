# __scrt_dllmain_after_initialize_c

- ea: `0x18000bea4`
- end: `0x18000bed8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000bb28`

## callees

- `0x18000bea4`
- `0x18000c290`
- `0x18000c6c8`
- `0x18000c752`
- `0x18000c776`
- `0x180013430`

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
0x18000bea4  sub     rsp, 28h
0x18000bea8  call    __scrt_is_ucrt_dll_in_use
0x18000bead  test    eax, eax
0x18000beaf  jz      short loc_18000BEB8
0x18000beb1  call    __isa_available_init
0x18000beb6  jmp     short loc_18000BED1
0x18000beb8  call    _get_startup_argv_mode
0x18000bebd  mov     ecx, eax; mode
0x18000bebf  call    _o__configure_narrow_argv_0
0x18000bec4  test    eax, eax
0x18000bec6  jz      short loc_18000BECC
0x18000bec8  xor     al, al
0x18000beca  jmp     short loc_18000BED3
0x18000becc  call    _initialize_narrow_environment
0x18000bed1  mov     al, 1
0x18000bed3  add     rsp, 28h
0x18000bed7  retn
```
