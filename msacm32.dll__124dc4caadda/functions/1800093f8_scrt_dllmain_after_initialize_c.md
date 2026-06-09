# __scrt_dllmain_after_initialize_c

- ea: `0x1800093f8`
- end: `0x18000942c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180008f58`

## callees

- `0x1800093f8`
- `0x1800097a8`
- `0x180009a34`
- `0x180009a40`
- `0x180009abe`
- `0x180009ad6`

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
0x1800093f8  sub     rsp, 28h
0x1800093fc  call    __scrt_is_ucrt_dll_in_use
0x180009401  test    eax, eax
0x180009403  jz      short loc_18000940C
0x180009405  call    __isa_available_init
0x18000940a  jmp     short loc_180009425
0x18000940c  call    _get_startup_argv_mode
0x180009411  mov     ecx, eax; mode
0x180009413  call    _o__configure_narrow_argv_0
0x180009418  test    eax, eax
0x18000941a  jz      short loc_180009420
0x18000941c  xor     al, al
0x18000941e  jmp     short loc_180009427
0x180009420  call    _initialize_narrow_environment
0x180009425  mov     al, 1
0x180009427  add     rsp, 28h
0x18000942b  retn
```
