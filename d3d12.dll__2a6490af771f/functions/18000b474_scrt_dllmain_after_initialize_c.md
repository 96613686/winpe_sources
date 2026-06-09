# __scrt_dllmain_after_initialize_c

- ea: `0x18000b474`
- end: `0x18000b4a8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b0e8`

## callees

- `0x18000b474`
- `0x18000ba30`
- `0x18000bcbc`
- `0x18000bcc8`
- `0x18000bde6`
- `0x18000be0a`

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
0x18000b474  sub     rsp, 28h
0x18000b478  call    __scrt_is_ucrt_dll_in_use
0x18000b47d  test    eax, eax
0x18000b47f  jz      short loc_18000B488
0x18000b481  call    __isa_available_init
0x18000b486  jmp     short loc_18000B4A1
0x18000b488  call    _get_startup_argv_mode
0x18000b48d  mov     ecx, eax; mode
0x18000b48f  call    _o__configure_narrow_argv_0
0x18000b494  test    eax, eax
0x18000b496  jz      short loc_18000B49C
0x18000b498  xor     al, al
0x18000b49a  jmp     short loc_18000B4A3
0x18000b49c  call    _initialize_narrow_environment
0x18000b4a1  mov     al, 1
0x18000b4a3  add     rsp, 28h
0x18000b4a7  retn
```
