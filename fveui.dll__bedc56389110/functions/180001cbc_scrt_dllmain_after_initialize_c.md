# __scrt_dllmain_after_initialize_c

- ea: `0x180001cbc`
- end: `0x180001cf0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001898`

## callees

- `0x180001cbc`
- `0x18000235c`
- `0x1800025e8`
- `0x1800025f4`
- `0x18000269a`
- `0x1800026be`

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
0x180001cbc  sub     rsp, 28h
0x180001cc0  call    __scrt_is_ucrt_dll_in_use
0x180001cc5  test    eax, eax
0x180001cc7  jz      short loc_180001CD0
0x180001cc9  call    __isa_available_init
0x180001cce  jmp     short loc_180001CE9
0x180001cd0  call    _get_startup_argv_mode
0x180001cd5  mov     ecx, eax; mode
0x180001cd7  call    _o__configure_narrow_argv_0
0x180001cdc  test    eax, eax
0x180001cde  jz      short loc_180001CE4
0x180001ce0  xor     al, al
0x180001ce2  jmp     short loc_180001CEB
0x180001ce4  call    _initialize_narrow_environment
0x180001ce9  mov     al, 1
0x180001ceb  add     rsp, 28h
0x180001cef  retn
```
