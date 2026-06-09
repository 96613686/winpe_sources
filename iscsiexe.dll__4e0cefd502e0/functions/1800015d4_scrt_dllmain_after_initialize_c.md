# __scrt_dllmain_after_initialize_c

- ea: `0x1800015d4`
- end: `0x180001608`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800010f8`

## callees

- `0x1800015d4`
- `0x180001988`
- `0x180001c14`
- `0x180001c20`
- `0x180001caa`
- `0x180001cc2`

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
0x1800015d4  sub     rsp, 28h
0x1800015d8  call    __scrt_is_ucrt_dll_in_use
0x1800015dd  test    eax, eax
0x1800015df  jz      short loc_1800015E8
0x1800015e1  call    __isa_available_init
0x1800015e6  jmp     short loc_180001601
0x1800015e8  call    _get_startup_argv_mode
0x1800015ed  mov     ecx, eax; mode
0x1800015ef  call    _o__configure_narrow_argv_0
0x1800015f4  test    eax, eax
0x1800015f6  jz      short loc_1800015FC
0x1800015f8  xor     al, al
0x1800015fa  jmp     short loc_180001603
0x1800015fc  call    _initialize_narrow_environment
0x180001601  mov     al, 1
0x180001603  add     rsp, 28h
0x180001607  retn
```
