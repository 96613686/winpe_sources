# __scrt_dllmain_after_initialize_c

- ea: `0x180001584`
- end: `0x1800015b8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001208`

## callees

- `0x180001584`
- `0x180001b70`
- `0x180001dfc`
- `0x180001e08`
- `0x180001f1a`
- `0x180001f3e`

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
0x180001584  sub     rsp, 28h
0x180001588  call    __scrt_is_ucrt_dll_in_use
0x18000158d  test    eax, eax
0x18000158f  jz      short loc_180001598
0x180001591  call    __isa_available_init
0x180001596  jmp     short loc_1800015B1
0x180001598  call    _get_startup_argv_mode
0x18000159d  mov     ecx, eax; mode
0x18000159f  call    _o__configure_narrow_argv_0
0x1800015a4  test    eax, eax
0x1800015a6  jz      short loc_1800015AC
0x1800015a8  xor     al, al
0x1800015aa  jmp     short loc_1800015B3
0x1800015ac  call    _initialize_narrow_environment
0x1800015b1  mov     al, 1
0x1800015b3  add     rsp, 28h
0x1800015b7  retn
```
