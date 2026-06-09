# __scrt_dllmain_after_initialize_c

- ea: `0x180001cd8`
- end: `0x180001d0c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001748`

## callees

- `0x180001cd8`
- `0x180002184`
- `0x180002410`
- `0x18000241c`
- `0x1800024ae`
- `0x1800024d2`

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
0x180001cd8  sub     rsp, 28h
0x180001cdc  call    __scrt_is_ucrt_dll_in_use
0x180001ce1  test    eax, eax
0x180001ce3  jz      short loc_180001CEC
0x180001ce5  call    __isa_available_init
0x180001cea  jmp     short loc_180001D05
0x180001cec  call    _get_startup_argv_mode
0x180001cf1  mov     ecx, eax; mode
0x180001cf3  call    _o__configure_narrow_argv_0
0x180001cf8  test    eax, eax
0x180001cfa  jz      short loc_180001D00
0x180001cfc  xor     al, al
0x180001cfe  jmp     short loc_180001D07
0x180001d00  call    _initialize_narrow_environment
0x180001d05  mov     al, 1
0x180001d07  add     rsp, 28h
0x180001d0b  retn
```
