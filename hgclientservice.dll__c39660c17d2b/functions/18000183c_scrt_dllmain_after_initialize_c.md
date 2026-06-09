# __scrt_dllmain_after_initialize_c

- ea: `0x18000183c`
- end: `0x180001870`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001458`

## callees

- `0x18000183c`
- `0x180001e00`
- `0x18000208c`
- `0x180002098`
- `0x18000213e`
- `0x180002162`

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
0x18000183c  sub     rsp, 28h
0x180001840  call    __scrt_is_ucrt_dll_in_use
0x180001845  test    eax, eax
0x180001847  jz      short loc_180001850
0x180001849  call    __isa_available_init
0x18000184e  jmp     short loc_180001869
0x180001850  call    _get_startup_argv_mode
0x180001855  mov     ecx, eax; mode
0x180001857  call    _o__configure_narrow_argv_0
0x18000185c  test    eax, eax
0x18000185e  jz      short loc_180001864
0x180001860  xor     al, al
0x180001862  jmp     short loc_18000186B
0x180001864  call    _initialize_narrow_environment
0x180001869  mov     al, 1
0x18000186b  add     rsp, 28h
0x18000186f  retn
```
