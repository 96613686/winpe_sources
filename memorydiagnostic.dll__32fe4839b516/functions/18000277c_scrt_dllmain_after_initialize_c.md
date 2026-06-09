# __scrt_dllmain_after_initialize_c

- ea: `0x18000277c`
- end: `0x1800027b0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002388`

## callees

- `0x18000277c`
- `0x18000304c`
- `0x180003200`
- `0x18000320c`
- `0x1800032ca`
- `0x1800032ee`

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
0x18000277c  sub     rsp, 28h
0x180002780  call    __scrt_is_ucrt_dll_in_use
0x180002785  test    eax, eax
0x180002787  jz      short loc_180002790
0x180002789  call    __isa_available_init
0x18000278e  jmp     short loc_1800027A9
0x180002790  call    _get_startup_argv_mode
0x180002795  mov     ecx, eax; mode
0x180002797  call    _o__configure_narrow_argv_0
0x18000279c  test    eax, eax
0x18000279e  jz      short loc_1800027A4
0x1800027a0  xor     al, al
0x1800027a2  jmp     short loc_1800027AB
0x1800027a4  call    _initialize_narrow_environment
0x1800027a9  mov     al, 1
0x1800027ab  add     rsp, 28h
0x1800027af  retn
```
