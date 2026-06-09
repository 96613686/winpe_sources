# __scrt_dllmain_after_initialize_c

- ea: `0x180001648`
- end: `0x18000167c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001198`

## callees

- `0x180001648`
- `0x1800019f8`
- `0x180001c84`
- `0x180001c90`
- `0x180001d0e`
- `0x180001d26`

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
0x180001648  sub     rsp, 28h
0x18000164c  call    __scrt_is_ucrt_dll_in_use
0x180001651  test    eax, eax
0x180001653  jz      short loc_18000165C
0x180001655  call    __isa_available_init
0x18000165a  jmp     short loc_180001675
0x18000165c  call    _get_startup_argv_mode
0x180001661  mov     ecx, eax; mode
0x180001663  call    _o__configure_narrow_argv_0
0x180001668  test    eax, eax
0x18000166a  jz      short loc_180001670
0x18000166c  xor     al, al
0x18000166e  jmp     short loc_180001677
0x180001670  call    _initialize_narrow_environment
0x180001675  mov     al, 1
0x180001677  add     rsp, 28h
0x18000167b  retn
```
