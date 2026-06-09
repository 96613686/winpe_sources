# __scrt_dllmain_after_initialize_c

- ea: `0x18000331c`
- end: `0x180003350`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002e98`

## callees

- `0x18000331c`
- `0x180003790`
- `0x180003bd4`
- `0x180003be0`
- `0x180003cea`
- `0x180003d0e`

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
0x18000331c  sub     rsp, 28h
0x180003320  call    __scrt_is_ucrt_dll_in_use
0x180003325  test    eax, eax
0x180003327  jz      short loc_180003330
0x180003329  call    __isa_available_init
0x18000332e  jmp     short loc_180003349
0x180003330  call    _get_startup_argv_mode
0x180003335  mov     ecx, eax; mode
0x180003337  call    _o__configure_narrow_argv_0
0x18000333c  test    eax, eax
0x18000333e  jz      short loc_180003344
0x180003340  xor     al, al
0x180003342  jmp     short loc_18000334B
0x180003344  call    _initialize_narrow_environment
0x180003349  mov     al, 1
0x18000334b  add     rsp, 28h
0x18000334f  retn
```
