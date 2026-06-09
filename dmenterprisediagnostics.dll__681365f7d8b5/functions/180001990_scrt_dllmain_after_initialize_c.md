# __scrt_dllmain_after_initialize_c

- ea: `0x180001990`
- end: `0x1800019c4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800014e8`

## callees

- `0x180001990`
- `0x180001fa4`
- `0x180002230`
- `0x18000223c`
- `0x1800022fa`
- `0x18000231e`

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
0x180001990  sub     rsp, 28h
0x180001994  call    __scrt_is_ucrt_dll_in_use
0x180001999  test    eax, eax
0x18000199b  jz      short loc_1800019A4
0x18000199d  call    __isa_available_init
0x1800019a2  jmp     short loc_1800019BD
0x1800019a4  call    _get_startup_argv_mode
0x1800019a9  mov     ecx, eax; mode
0x1800019ab  call    _o__configure_narrow_argv_0
0x1800019b0  test    eax, eax
0x1800019b2  jz      short loc_1800019B8
0x1800019b4  xor     al, al
0x1800019b6  jmp     short loc_1800019BF
0x1800019b8  call    _initialize_narrow_environment
0x1800019bd  mov     al, 1
0x1800019bf  add     rsp, 28h
0x1800019c3  retn
```
