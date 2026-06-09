# __scrt_dllmain_after_initialize_c

- ea: `0x180003bfc`
- end: `0x180003c30`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180003778`

## callees

- `0x180003bfc`
- `0x180003fd0`
- `0x18000425c`
- `0x180004268`
- `0x1800042c2`
- `0x1800042da`

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
0x180003bfc  sub     rsp, 28h
0x180003c00  call    __scrt_is_ucrt_dll_in_use
0x180003c05  test    eax, eax
0x180003c07  jz      short loc_180003C10
0x180003c09  call    __isa_available_init
0x180003c0e  jmp     short loc_180003C29
0x180003c10  call    _get_startup_argv_mode
0x180003c15  mov     ecx, eax; mode
0x180003c17  call    _o__configure_narrow_argv_0
0x180003c1c  test    eax, eax
0x180003c1e  jz      short loc_180003C24
0x180003c20  xor     al, al
0x180003c22  jmp     short loc_180003C2B
0x180003c24  call    _initialize_narrow_environment
0x180003c29  mov     al, 1
0x180003c2b  add     rsp, 28h
0x180003c2f  retn
```
