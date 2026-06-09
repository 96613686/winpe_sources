# __scrt_dllmain_after_initialize_c

- ea: `0x18001e234`
- end: `0x18001e268`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001dea8`

## callees

- `0x18001e234`
- `0x18001e7a0`
- `0x18001ea2c`
- `0x18001ea38`
- `0x18001eaaa`
- `0x18001eace`

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
0x18001e234  sub     rsp, 28h
0x18001e238  call    __scrt_is_ucrt_dll_in_use
0x18001e23d  test    eax, eax
0x18001e23f  jz      short loc_18001E248
0x18001e241  call    __isa_available_init
0x18001e246  jmp     short loc_18001E261
0x18001e248  call    _get_startup_argv_mode
0x18001e24d  mov     ecx, eax; mode
0x18001e24f  call    _o__configure_narrow_argv_0
0x18001e254  test    eax, eax
0x18001e256  jz      short loc_18001E25C
0x18001e258  xor     al, al
0x18001e25a  jmp     short loc_18001E263
0x18001e25c  call    _initialize_narrow_environment
0x18001e261  mov     al, 1
0x18001e263  add     rsp, 28h
0x18001e267  retn
```
