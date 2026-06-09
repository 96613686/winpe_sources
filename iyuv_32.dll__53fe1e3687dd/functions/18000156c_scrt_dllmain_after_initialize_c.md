# __scrt_dllmain_after_initialize_c

- ea: `0x18000156c`
- end: `0x1800015a0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800010e8`

## callees

- `0x18000156c`
- `0x180001940`
- `0x180001bcc`
- `0x180001bd8`
- `0x180001c36`
- `0x180001c4e`

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
0x18000156c  sub     rsp, 28h
0x180001570  call    __scrt_is_ucrt_dll_in_use
0x180001575  test    eax, eax
0x180001577  jz      short loc_180001580
0x180001579  call    __isa_available_init
0x18000157e  jmp     short loc_180001599
0x180001580  call    _get_startup_argv_mode
0x180001585  mov     ecx, eax; mode
0x180001587  call    _o__configure_narrow_argv_0
0x18000158c  test    eax, eax
0x18000158e  jz      short loc_180001594
0x180001590  xor     al, al
0x180001592  jmp     short loc_18000159B
0x180001594  call    _initialize_narrow_environment
0x180001599  mov     al, 1
0x18000159b  add     rsp, 28h
0x18000159f  retn
```
