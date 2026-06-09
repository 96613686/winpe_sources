# __scrt_dllmain_after_initialize_c

- ea: `0x180001c88`
- end: `0x180001cbc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800018c8`

## callees

- `0x180001c88`
- `0x180002268`
- `0x1800024f4`
- `0x180002500`
- `0x18000258e`
- `0x1800025b2`

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
0x180001c88  sub     rsp, 28h
0x180001c8c  call    __scrt_is_ucrt_dll_in_use
0x180001c91  test    eax, eax
0x180001c93  jz      short loc_180001C9C
0x180001c95  call    __isa_available_init
0x180001c9a  jmp     short loc_180001CB5
0x180001c9c  call    _get_startup_argv_mode
0x180001ca1  mov     ecx, eax; mode
0x180001ca3  call    _o__configure_narrow_argv_0
0x180001ca8  test    eax, eax
0x180001caa  jz      short loc_180001CB0
0x180001cac  xor     al, al
0x180001cae  jmp     short loc_180001CB7
0x180001cb0  call    _initialize_narrow_environment
0x180001cb5  mov     al, 1
0x180001cb7  add     rsp, 28h
0x180001cbb  retn
```
