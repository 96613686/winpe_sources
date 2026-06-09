# __scrt_dllmain_after_initialize_c

- ea: `0x18001b978`
- end: `0x18001b9ac`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001b4c8`

## callees

- `0x18001b978`
- `0x18001bda0`
- `0x18001c02c`
- `0x18001c038`
- `0x18001c086`
- `0x18001c0aa`

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
0x18001b978  sub     rsp, 28h
0x18001b97c  call    __scrt_is_ucrt_dll_in_use
0x18001b981  test    eax, eax
0x18001b983  jz      short loc_18001B98C
0x18001b985  call    __isa_available_init
0x18001b98a  jmp     short loc_18001B9A5
0x18001b98c  call    _get_startup_argv_mode
0x18001b991  mov     ecx, eax; mode
0x18001b993  call    _o__configure_narrow_argv_0
0x18001b998  test    eax, eax
0x18001b99a  jz      short loc_18001B9A0
0x18001b99c  xor     al, al
0x18001b99e  jmp     short loc_18001B9A7
0x18001b9a0  call    _initialize_narrow_environment
0x18001b9a5  mov     al, 1
0x18001b9a7  add     rsp, 28h
0x18001b9ab  retn
```
