# __scrt_dllmain_after_initialize_c

- ea: `0x18000947c`
- end: `0x1800094b0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180008ff8`

## callees

- `0x18000947c`
- `0x180009850`
- `0x180009adc`
- `0x180009ae8`
- `0x180009b42`
- `0x180009b5a`

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
0x18000947c  sub     rsp, 28h
0x180009480  call    __scrt_is_ucrt_dll_in_use
0x180009485  test    eax, eax
0x180009487  jz      short loc_180009490
0x180009489  call    __isa_available_init
0x18000948e  jmp     short loc_1800094A9
0x180009490  call    _get_startup_argv_mode
0x180009495  mov     ecx, eax; mode
0x180009497  call    _o__configure_narrow_argv_0
0x18000949c  test    eax, eax
0x18000949e  jz      short loc_1800094A4
0x1800094a0  xor     al, al
0x1800094a2  jmp     short loc_1800094AB
0x1800094a4  call    _initialize_narrow_environment
0x1800094a9  mov     al, 1
0x1800094ab  add     rsp, 28h
0x1800094af  retn
```
