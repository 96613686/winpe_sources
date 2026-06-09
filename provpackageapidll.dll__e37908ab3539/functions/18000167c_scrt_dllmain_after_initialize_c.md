# __scrt_dllmain_after_initialize_c

- ea: `0x18000167c`
- end: `0x1800016b0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800011f8`

## callees

- `0x18000167c`
- `0x180001ab0`
- `0x180001d3c`
- `0x180001d48`
- `0x180001de2`
- `0x180001e06`

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
0x18000167c  sub     rsp, 28h
0x180001680  call    __scrt_is_ucrt_dll_in_use
0x180001685  test    eax, eax
0x180001687  jz      short loc_180001690
0x180001689  call    __isa_available_init
0x18000168e  jmp     short loc_1800016A9
0x180001690  call    _get_startup_argv_mode
0x180001695  mov     ecx, eax; mode
0x180001697  call    _o__configure_narrow_argv_0
0x18000169c  test    eax, eax
0x18000169e  jz      short loc_1800016A4
0x1800016a0  xor     al, al
0x1800016a2  jmp     short loc_1800016AB
0x1800016a4  call    _initialize_narrow_environment
0x1800016a9  mov     al, 1
0x1800016ab  add     rsp, 28h
0x1800016af  retn
```
