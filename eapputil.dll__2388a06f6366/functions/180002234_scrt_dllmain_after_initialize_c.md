# __scrt_dllmain_after_initialize_c

- ea: `0x180002234`
- end: `0x180002268`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001eb8`

## callees

- `0x180002234`
- `0x1800027a0`
- `0x180002a2c`
- `0x180002a38`
- `0x180002ade`
- `0x180002b02`

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
0x180002234  sub     rsp, 28h
0x180002238  call    __scrt_is_ucrt_dll_in_use
0x18000223d  test    eax, eax
0x18000223f  jz      short loc_180002248
0x180002241  call    __isa_available_init
0x180002246  jmp     short loc_180002261
0x180002248  call    _get_startup_argv_mode
0x18000224d  mov     ecx, eax; mode
0x18000224f  call    _o__configure_narrow_argv_0
0x180002254  test    eax, eax
0x180002256  jz      short loc_18000225C
0x180002258  xor     al, al
0x18000225a  jmp     short loc_180002263
0x18000225c  call    _initialize_narrow_environment
0x180002261  mov     al, 1
0x180002263  add     rsp, 28h
0x180002267  retn
```
