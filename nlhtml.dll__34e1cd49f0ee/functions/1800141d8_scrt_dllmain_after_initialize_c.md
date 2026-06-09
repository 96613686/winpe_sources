# __scrt_dllmain_after_initialize_c

- ea: `0x1800141d8`
- end: `0x18001420c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180013e08`

## callees

- `0x1800141d8`
- `0x180014be8`
- `0x180014e74`
- `0x180014f0a`
- `0x180014f2e`
- `0x18001e590`

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
0x1800141d8  sub     rsp, 28h
0x1800141dc  call    __scrt_is_ucrt_dll_in_use
0x1800141e1  test    eax, eax
0x1800141e3  jz      short loc_1800141EC
0x1800141e5  call    __isa_available_init
0x1800141ea  jmp     short loc_180014205
0x1800141ec  call    _get_startup_argv_mode
0x1800141f1  mov     ecx, eax; mode
0x1800141f3  call    _o__configure_narrow_argv_0
0x1800141f8  test    eax, eax
0x1800141fa  jz      short loc_180014200
0x1800141fc  xor     al, al
0x1800141fe  jmp     short loc_180014207
0x180014200  call    _initialize_narrow_environment
0x180014205  mov     al, 1
0x180014207  add     rsp, 28h
0x18001420b  retn
```
