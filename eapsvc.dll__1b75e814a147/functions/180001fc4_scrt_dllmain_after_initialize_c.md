# __scrt_dllmain_after_initialize_c

- ea: `0x180001fc4`
- end: `0x180001ff8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001c48`

## callees

- `0x180001fc4`
- `0x180002530`
- `0x1800027bc`
- `0x18000284e`
- `0x180002872`
- `0x1800142d0`

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
0x180001fc4  sub     rsp, 28h
0x180001fc8  call    __scrt_is_ucrt_dll_in_use
0x180001fcd  test    eax, eax
0x180001fcf  jz      short loc_180001FD8
0x180001fd1  call    __isa_available_init
0x180001fd6  jmp     short loc_180001FF1
0x180001fd8  call    _get_startup_argv_mode
0x180001fdd  mov     ecx, eax; mode
0x180001fdf  call    _o__configure_narrow_argv_0
0x180001fe4  test    eax, eax
0x180001fe6  jz      short loc_180001FEC
0x180001fe8  xor     al, al
0x180001fea  jmp     short loc_180001FF3
0x180001fec  call    _initialize_narrow_environment
0x180001ff1  mov     al, 1
0x180001ff3  add     rsp, 28h
0x180001ff7  retn
```
