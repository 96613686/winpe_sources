# __scrt_dllmain_after_initialize_c

- ea: `0x180014838`
- end: `0x18001486c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180014018`

## callees

- `0x180014838`
- `0x180014cb0`
- `0x180014f3c`
- `0x180014f48`
- `0x1800150a0`
- `0x1800150c4`

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
0x180014838  sub     rsp, 28h
0x18001483c  call    __scrt_is_ucrt_dll_in_use
0x180014841  test    eax, eax
0x180014843  jz      short loc_18001484C
0x180014845  call    __isa_available_init
0x18001484a  jmp     short loc_180014865
0x18001484c  call    _get_startup_argv_mode
0x180014851  mov     ecx, eax; mode
0x180014853  call    _o__configure_narrow_argv_0
0x180014858  test    eax, eax
0x18001485a  jz      short loc_180014860
0x18001485c  xor     al, al
0x18001485e  jmp     short loc_180014867
0x180014860  call    _initialize_narrow_environment
0x180014865  mov     al, 1
0x180014867  add     rsp, 28h
0x18001486b  retn
```
