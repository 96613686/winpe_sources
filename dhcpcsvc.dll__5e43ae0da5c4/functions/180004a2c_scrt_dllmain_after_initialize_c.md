# __scrt_dllmain_after_initialize_c

- ea: `0x180004a2c`
- end: `0x180004a60`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800045a8`

## callees

- `0x180004a2c`
- `0x180004e00`
- `0x18000508c`
- `0x180005098`
- `0x18000511a`
- `0x180005132`

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
0x180004a2c  sub     rsp, 28h
0x180004a30  call    __scrt_is_ucrt_dll_in_use
0x180004a35  test    eax, eax
0x180004a37  jz      short loc_180004A40
0x180004a39  call    __isa_available_init
0x180004a3e  jmp     short loc_180004A59
0x180004a40  call    _get_startup_argv_mode
0x180004a45  mov     ecx, eax; mode
0x180004a47  call    _o__configure_narrow_argv_0
0x180004a4c  test    eax, eax
0x180004a4e  jz      short loc_180004A54
0x180004a50  xor     al, al
0x180004a52  jmp     short loc_180004A5B
0x180004a54  call    _initialize_narrow_environment
0x180004a59  mov     al, 1
0x180004a5b  add     rsp, 28h
0x180004a5f  retn
```
