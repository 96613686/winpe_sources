# __scrt_dllmain_after_initialize_c

- ea: `0x18002125c`
- end: `0x180021290`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180020dd8`

## callees

- `0x18002125c`
- `0x180021690`
- `0x18002191c`
- `0x180021928`
- `0x1800219b2`
- `0x1800219d6`

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
0x18002125c  sub     rsp, 28h
0x180021260  call    __scrt_is_ucrt_dll_in_use
0x180021265  test    eax, eax
0x180021267  jz      short loc_180021270
0x180021269  call    __isa_available_init
0x18002126e  jmp     short loc_180021289
0x180021270  call    _get_startup_argv_mode
0x180021275  mov     ecx, eax; mode
0x180021277  call    _o__configure_narrow_argv_0
0x18002127c  test    eax, eax
0x18002127e  jz      short loc_180021284
0x180021280  xor     al, al
0x180021282  jmp     short loc_18002128B
0x180021284  call    _initialize_narrow_environment
0x180021289  mov     al, 1
0x18002128b  add     rsp, 28h
0x18002128f  retn
```
