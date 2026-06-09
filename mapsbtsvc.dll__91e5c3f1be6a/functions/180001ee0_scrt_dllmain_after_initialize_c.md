# __scrt_dllmain_after_initialize_c

- ea: `0x180001ee0`
- end: `0x180001f14`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001b48`

## callees

- `0x180001ee0`
- `0x180002460`
- `0x1800026ec`
- `0x1800026f8`
- `0x18000284a`
- `0x18000286e`

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
0x180001ee0  sub     rsp, 28h
0x180001ee4  call    __scrt_is_ucrt_dll_in_use
0x180001ee9  test    eax, eax
0x180001eeb  jz      short loc_180001EF4
0x180001eed  call    __isa_available_init
0x180001ef2  jmp     short loc_180001F0D
0x180001ef4  call    _get_startup_argv_mode
0x180001ef9  mov     ecx, eax; mode
0x180001efb  call    _o__configure_narrow_argv_0
0x180001f00  test    eax, eax
0x180001f02  jz      short loc_180001F08
0x180001f04  xor     al, al
0x180001f06  jmp     short loc_180001F0F
0x180001f08  call    _initialize_narrow_environment
0x180001f0d  mov     al, 1
0x180001f0f  add     rsp, 28h
0x180001f13  retn
```
