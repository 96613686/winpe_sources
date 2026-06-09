# __scrt_dllmain_after_initialize_c

- ea: `0x180001970`
- end: `0x1800019a4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800014c8`

## callees

- `0x180001970`
- `0x180001f84`
- `0x180002210`
- `0x18000221c`
- `0x1800022da`
- `0x1800022fe`

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
0x180001970  sub     rsp, 28h
0x180001974  call    __scrt_is_ucrt_dll_in_use
0x180001979  test    eax, eax
0x18000197b  jz      short loc_180001984
0x18000197d  call    __isa_available_init
0x180001982  jmp     short loc_18000199D
0x180001984  call    _get_startup_argv_mode
0x180001989  mov     ecx, eax; mode
0x18000198b  call    _o__configure_narrow_argv_0
0x180001990  test    eax, eax
0x180001992  jz      short loc_180001998
0x180001994  xor     al, al
0x180001996  jmp     short loc_18000199F
0x180001998  call    _initialize_narrow_environment
0x18000199d  mov     al, 1
0x18000199f  add     rsp, 28h
0x1800019a3  retn
```
