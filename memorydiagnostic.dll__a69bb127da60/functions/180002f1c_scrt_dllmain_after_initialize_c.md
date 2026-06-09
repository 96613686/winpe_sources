# __scrt_dllmain_after_initialize_c

- ea: `0x180002f1c`
- end: `0x180002f50`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002b38`

## callees

- `0x180002f1c`
- `0x180003368`
- `0x1800037e8`
- `0x1800037f4`
- `0x18000388a`
- `0x1800038ae`

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
0x180002f1c  sub     rsp, 28h
0x180002f20  call    __scrt_is_ucrt_dll_in_use
0x180002f25  test    eax, eax
0x180002f27  jz      short loc_180002F30
0x180002f29  call    __isa_available_init
0x180002f2e  jmp     short loc_180002F49
0x180002f30  call    _get_startup_argv_mode
0x180002f35  mov     ecx, eax; mode
0x180002f37  call    _o__configure_narrow_argv_0
0x180002f3c  test    eax, eax
0x180002f3e  jz      short loc_180002F44
0x180002f40  xor     al, al
0x180002f42  jmp     short loc_180002F4B
0x180002f44  call    _initialize_narrow_environment
0x180002f49  mov     al, 1
0x180002f4b  add     rsp, 28h
0x180002f4f  retn
```
