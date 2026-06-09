# __scrt_dllmain_after_initialize_c

- ea: `0x180002344`
- end: `0x180002378`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001fc8`

## callees

- `0x180002344`
- `0x1800028b0`
- `0x180002b3c`
- `0x180002b48`
- `0x180002bfa`
- `0x180002c1e`

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
0x180002344  sub     rsp, 28h
0x180002348  call    __scrt_is_ucrt_dll_in_use
0x18000234d  test    eax, eax
0x18000234f  jz      short loc_180002358
0x180002351  call    __isa_available_init
0x180002356  jmp     short loc_180002371
0x180002358  call    _get_startup_argv_mode
0x18000235d  mov     ecx, eax; mode
0x18000235f  call    _o__configure_narrow_argv_0
0x180002364  test    eax, eax
0x180002366  jz      short loc_18000236C
0x180002368  xor     al, al
0x18000236a  jmp     short loc_180002373
0x18000236c  call    _initialize_narrow_environment
0x180002371  mov     al, 1
0x180002373  add     rsp, 28h
0x180002377  retn
```
