# __scrt_dllmain_after_initialize_c

- ea: `0x18000a148`
- end: `0x18000a17c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180009c98`

## callees

- `0x18000a148`
- `0x18000a4f8`
- `0x18000a784`
- `0x18000a790`
- `0x18000a802`
- `0x18000a81a`

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
0x18000a148  sub     rsp, 28h
0x18000a14c  call    __scrt_is_ucrt_dll_in_use
0x18000a151  test    eax, eax
0x18000a153  jz      short loc_18000A15C
0x18000a155  call    __isa_available_init
0x18000a15a  jmp     short loc_18000A175
0x18000a15c  call    _get_startup_argv_mode
0x18000a161  mov     ecx, eax; mode
0x18000a163  call    _o__configure_narrow_argv_0
0x18000a168  test    eax, eax
0x18000a16a  jz      short loc_18000A170
0x18000a16c  xor     al, al
0x18000a16e  jmp     short loc_18000A177
0x18000a170  call    _initialize_narrow_environment
0x18000a175  mov     al, 1
0x18000a177  add     rsp, 28h
0x18000a17b  retn
```
