# __scrt_dllmain_after_initialize_c

- ea: `0x180002d38`
- end: `0x180002d6c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002998`

## callees

- `0x180002d38`
- `0x1800032c4`
- `0x180003550`
- `0x18000355c`
- `0x1800037f0`
- `0x180003814`

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
0x180002d38  sub     rsp, 28h
0x180002d3c  call    __scrt_is_ucrt_dll_in_use
0x180002d41  test    eax, eax
0x180002d43  jz      short loc_180002D4C
0x180002d45  call    __isa_available_init
0x180002d4a  jmp     short loc_180002D65
0x180002d4c  call    _get_startup_argv_mode
0x180002d51  mov     ecx, eax; mode
0x180002d53  call    _o__configure_narrow_argv_0
0x180002d58  test    eax, eax
0x180002d5a  jz      short loc_180002D60
0x180002d5c  xor     al, al
0x180002d5e  jmp     short loc_180002D67
0x180002d60  call    _initialize_narrow_environment
0x180002d65  mov     al, 1
0x180002d67  add     rsp, 28h
0x180002d6b  retn
```
