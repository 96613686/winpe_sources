# __scrt_dllmain_after_initialize_c

- ea: `0x1800016cc`
- end: `0x180001700`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001248`

## callees

- `0x1800016cc`
- `0x180001b00`
- `0x180001d8c`
- `0x180001d98`
- `0x180001e22`
- `0x180001e46`

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
0x1800016cc  sub     rsp, 28h
0x1800016d0  call    __scrt_is_ucrt_dll_in_use
0x1800016d5  test    eax, eax
0x1800016d7  jz      short loc_1800016E0
0x1800016d9  call    __isa_available_init
0x1800016de  jmp     short loc_1800016F9
0x1800016e0  call    _get_startup_argv_mode
0x1800016e5  mov     ecx, eax; mode
0x1800016e7  call    _o__configure_narrow_argv_0
0x1800016ec  test    eax, eax
0x1800016ee  jz      short loc_1800016F4
0x1800016f0  xor     al, al
0x1800016f2  jmp     short loc_1800016FB
0x1800016f4  call    _initialize_narrow_environment
0x1800016f9  mov     al, 1
0x1800016fb  add     rsp, 28h
0x1800016ff  retn
```
