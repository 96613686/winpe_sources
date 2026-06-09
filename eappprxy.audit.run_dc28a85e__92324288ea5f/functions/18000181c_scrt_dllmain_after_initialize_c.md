# __scrt_dllmain_after_initialize_c

- ea: `0x18000181c`
- end: `0x180001850`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001468`

## callees

- `0x18000181c`
- `0x180001d50`
- `0x180001fdc`
- `0x180001fe8`
- `0x18000209a`
- `0x1800020be`

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
0x18000181c  sub     rsp, 28h
0x180001820  call    __scrt_is_ucrt_dll_in_use
0x180001825  test    eax, eax
0x180001827  jz      short loc_180001830
0x180001829  call    __isa_available_init
0x18000182e  jmp     short loc_180001849
0x180001830  call    _get_startup_argv_mode
0x180001835  mov     ecx, eax; mode
0x180001837  call    _o__configure_narrow_argv_0
0x18000183c  test    eax, eax
0x18000183e  jz      short loc_180001844
0x180001840  xor     al, al
0x180001842  jmp     short loc_18000184B
0x180001844  call    _initialize_narrow_environment
0x180001849  mov     al, 1
0x18000184b  add     rsp, 28h
0x18000184f  retn
```
