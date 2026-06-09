# __scrt_dllmain_after_initialize_c

- ea: `0x1800015dc`
- end: `0x180001610`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001158`

## callees

- `0x1800015dc`
- `0x1800019b0`
- `0x180001c3c`
- `0x180001c48`
- `0x180001ca6`
- `0x180001cbe`

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
0x1800015dc  sub     rsp, 28h
0x1800015e0  call    __scrt_is_ucrt_dll_in_use
0x1800015e5  test    eax, eax
0x1800015e7  jz      short loc_1800015F0
0x1800015e9  call    __isa_available_init
0x1800015ee  jmp     short loc_180001609
0x1800015f0  call    _get_startup_argv_mode
0x1800015f5  mov     ecx, eax; mode
0x1800015f7  call    _o__configure_narrow_argv_0
0x1800015fc  test    eax, eax
0x1800015fe  jz      short loc_180001604
0x180001600  xor     al, al
0x180001602  jmp     short loc_18000160B
0x180001604  call    _initialize_narrow_environment
0x180001609  mov     al, 1
0x18000160b  add     rsp, 28h
0x18000160f  retn
```
