# __scrt_dllmain_after_initialize_c

- ea: `0x1800016c4`
- end: `0x1800016f8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001338`

## callees

- `0x1800016c4`
- `0x180001c38`
- `0x180001ec4`
- `0x180001ed0`
- `0x180001f72`
- `0x180001f96`

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
0x1800016c4  sub     rsp, 28h
0x1800016c8  call    __scrt_is_ucrt_dll_in_use
0x1800016cd  test    eax, eax
0x1800016cf  jz      short loc_1800016D8
0x1800016d1  call    __isa_available_init
0x1800016d6  jmp     short loc_1800016F1
0x1800016d8  call    _get_startup_argv_mode
0x1800016dd  mov     ecx, eax; mode
0x1800016df  call    _o__configure_narrow_argv_0
0x1800016e4  test    eax, eax
0x1800016e6  jz      short loc_1800016EC
0x1800016e8  xor     al, al
0x1800016ea  jmp     short loc_1800016F3
0x1800016ec  call    _initialize_narrow_environment
0x1800016f1  mov     al, 1
0x1800016f3  add     rsp, 28h
0x1800016f7  retn
```
