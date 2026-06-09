# __scrt_dllmain_after_initialize_c

- ea: `0x180001694`
- end: `0x1800016c8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001318`

## callees

- `0x180001694`
- `0x180001bd0`
- `0x180001e5c`
- `0x180001e68`
- `0x180001ef6`
- `0x180001f1a`

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
0x180001694  sub     rsp, 28h
0x180001698  call    __scrt_is_ucrt_dll_in_use
0x18000169d  test    eax, eax
0x18000169f  jz      short loc_1800016A8
0x1800016a1  call    __isa_available_init
0x1800016a6  jmp     short loc_1800016C1
0x1800016a8  call    _get_startup_argv_mode
0x1800016ad  mov     ecx, eax; mode
0x1800016af  call    _o__configure_narrow_argv_0
0x1800016b4  test    eax, eax
0x1800016b6  jz      short loc_1800016BC
0x1800016b8  xor     al, al
0x1800016ba  jmp     short loc_1800016C3
0x1800016bc  call    _initialize_narrow_environment
0x1800016c1  mov     al, 1
0x1800016c3  add     rsp, 28h
0x1800016c7  retn
```
