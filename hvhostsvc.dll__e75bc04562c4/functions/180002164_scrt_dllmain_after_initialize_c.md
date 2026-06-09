# __scrt_dllmain_after_initialize_c

- ea: `0x180002164`
- end: `0x180002198`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001de8`

## callees

- `0x180002164`
- `0x180002700`
- `0x18000298c`
- `0x180002998`
- `0x180002a4a`
- `0x180002a6e`

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
0x180002164  sub     rsp, 28h
0x180002168  call    __scrt_is_ucrt_dll_in_use
0x18000216d  test    eax, eax
0x18000216f  jz      short loc_180002178
0x180002171  call    __isa_available_init
0x180002176  jmp     short loc_180002191
0x180002178  call    _get_startup_argv_mode
0x18000217d  mov     ecx, eax; mode
0x18000217f  call    _o__configure_narrow_argv_0
0x180002184  test    eax, eax
0x180002186  jz      short loc_18000218C
0x180002188  xor     al, al
0x18000218a  jmp     short loc_180002193
0x18000218c  call    _initialize_narrow_environment
0x180002191  mov     al, 1
0x180002193  add     rsp, 28h
0x180002197  retn
```
