# __scrt_dllmain_after_initialize_c

- ea: `0x180002690`
- end: `0x1800026c4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002308`

## callees

- `0x180002690`
- `0x180002bd8`
- `0x180002e64`
- `0x180002e70`
- `0x180002ec2`
- `0x180002ee6`

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
0x180002690  sub     rsp, 28h
0x180002694  call    __scrt_is_ucrt_dll_in_use
0x180002699  test    eax, eax
0x18000269b  jz      short loc_1800026A4
0x18000269d  call    __isa_available_init
0x1800026a2  jmp     short loc_1800026BD
0x1800026a4  call    _get_startup_argv_mode
0x1800026a9  mov     ecx, eax; mode
0x1800026ab  call    _o__configure_narrow_argv_0
0x1800026b0  test    eax, eax
0x1800026b2  jz      short loc_1800026B8
0x1800026b4  xor     al, al
0x1800026b6  jmp     short loc_1800026BF
0x1800026b8  call    _initialize_narrow_environment
0x1800026bd  mov     al, 1
0x1800026bf  add     rsp, 28h
0x1800026c3  retn
```
