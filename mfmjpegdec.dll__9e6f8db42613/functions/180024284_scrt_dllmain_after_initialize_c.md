# __scrt_dllmain_after_initialize_c

- ea: `0x180024284`
- end: `0x1800242b8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180023f08`

## callees

- `0x180024284`
- `0x1800247d0`
- `0x180024a5c`
- `0x180024a68`
- `0x180024b26`
- `0x180024b4a`

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
0x180024284  sub     rsp, 28h
0x180024288  call    __scrt_is_ucrt_dll_in_use
0x18002428d  test    eax, eax
0x18002428f  jz      short loc_180024298
0x180024291  call    __isa_available_init
0x180024296  jmp     short loc_1800242B1
0x180024298  call    _get_startup_argv_mode
0x18002429d  mov     ecx, eax; mode
0x18002429f  call    _o__configure_narrow_argv_0
0x1800242a4  test    eax, eax
0x1800242a6  jz      short loc_1800242AC
0x1800242a8  xor     al, al
0x1800242aa  jmp     short loc_1800242B3
0x1800242ac  call    _initialize_narrow_environment
0x1800242b1  mov     al, 1
0x1800242b3  add     rsp, 28h
0x1800242b7  retn
```
