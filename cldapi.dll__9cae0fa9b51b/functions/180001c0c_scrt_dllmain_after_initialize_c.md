# __scrt_dllmain_after_initialize_c

- ea: `0x180001c0c`
- end: `0x180001c40`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001788`

## callees

- `0x180001c0c`
- `0x180001fe0`
- `0x18000226c`
- `0x180002278`
- `0x1800022d6`
- `0x1800022ee`

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
0x180001c0c  sub     rsp, 28h
0x180001c10  call    __scrt_is_ucrt_dll_in_use
0x180001c15  test    eax, eax
0x180001c17  jz      short loc_180001C20
0x180001c19  call    __isa_available_init
0x180001c1e  jmp     short loc_180001C39
0x180001c20  call    _get_startup_argv_mode
0x180001c25  mov     ecx, eax; mode
0x180001c27  call    _o__configure_narrow_argv_0
0x180001c2c  test    eax, eax
0x180001c2e  jz      short loc_180001C34
0x180001c30  xor     al, al
0x180001c32  jmp     short loc_180001C3B
0x180001c34  call    _initialize_narrow_environment
0x180001c39  mov     al, 1
0x180001c3b  add     rsp, 28h
0x180001c3f  retn
```
