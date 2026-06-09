# __scrt_dllmain_after_initialize_c

- ea: `0x180002b74`
- end: `0x180002ba8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800027f8`

## callees

- `0x180002b74`
- `0x180003160`
- `0x1800033ec`
- `0x1800034ee`
- `0x180003512`
- `0x18000be70`

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
0x180002b74  sub     rsp, 28h
0x180002b78  call    __scrt_is_ucrt_dll_in_use
0x180002b7d  test    eax, eax
0x180002b7f  jz      short loc_180002B88
0x180002b81  call    __isa_available_init
0x180002b86  jmp     short loc_180002BA1
0x180002b88  call    _get_startup_argv_mode
0x180002b8d  mov     ecx, eax; mode
0x180002b8f  call    _o__configure_narrow_argv_0
0x180002b94  test    eax, eax
0x180002b96  jz      short loc_180002B9C
0x180002b98  xor     al, al
0x180002b9a  jmp     short loc_180002BA3
0x180002b9c  call    _initialize_narrow_environment
0x180002ba1  mov     al, 1
0x180002ba3  add     rsp, 28h
0x180002ba7  retn
```
