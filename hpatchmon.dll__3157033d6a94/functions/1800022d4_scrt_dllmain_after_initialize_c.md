# __scrt_dllmain_after_initialize_c

- ea: `0x1800022d4`
- end: `0x180002308`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001f58`

## callees

- `0x1800022d4`
- `0x180002810`
- `0x180002a9c`
- `0x180002aa8`
- `0x180002b26`
- `0x180002b4a`

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
0x1800022d4  sub     rsp, 28h
0x1800022d8  call    __scrt_is_ucrt_dll_in_use
0x1800022dd  test    eax, eax
0x1800022df  jz      short loc_1800022E8
0x1800022e1  call    __isa_available_init
0x1800022e6  jmp     short loc_180002301
0x1800022e8  call    _get_startup_argv_mode
0x1800022ed  mov     ecx, eax; mode
0x1800022ef  call    _o__configure_narrow_argv_0
0x1800022f4  test    eax, eax
0x1800022f6  jz      short loc_1800022FC
0x1800022f8  xor     al, al
0x1800022fa  jmp     short loc_180002303
0x1800022fc  call    _initialize_narrow_environment
0x180002301  mov     al, 1
0x180002303  add     rsp, 28h
0x180002307  retn
```
