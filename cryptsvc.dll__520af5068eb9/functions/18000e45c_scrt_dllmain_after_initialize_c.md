# __scrt_dllmain_after_initialize_c

- ea: `0x18000e45c`
- end: `0x18000e490`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000dfd8`

## callees

- `0x18000e45c`
- `0x18000e8a0`
- `0x18000eb2c`
- `0x18000eb38`
- `0x18000eb9e`
- `0x18000ebc2`

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
0x18000e45c  sub     rsp, 28h
0x18000e460  call    __scrt_is_ucrt_dll_in_use
0x18000e465  test    eax, eax
0x18000e467  jz      short loc_18000E470
0x18000e469  call    __isa_available_init
0x18000e46e  jmp     short loc_18000E489
0x18000e470  call    _get_startup_argv_mode
0x18000e475  mov     ecx, eax; mode
0x18000e477  call    _o__configure_narrow_argv_0
0x18000e47c  test    eax, eax
0x18000e47e  jz      short loc_18000E484
0x18000e480  xor     al, al
0x18000e482  jmp     short loc_18000E48B
0x18000e484  call    _initialize_narrow_environment
0x18000e489  mov     al, 1
0x18000e48b  add     rsp, 28h
0x18000e48f  retn
```
