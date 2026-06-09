# __scrt_dllmain_after_initialize_c

- ea: `0x1800015f4`
- end: `0x180001628`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001228`

## callees

- `0x1800015f4`
- `0x180001bb8`
- `0x180001e44`
- `0x180001e50`
- `0x180001f0a`
- `0x180001f3a`

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
0x1800015f4  sub     rsp, 28h
0x1800015f8  call    __scrt_is_ucrt_dll_in_use
0x1800015fd  test    eax, eax
0x1800015ff  jz      short loc_180001608
0x180001601  call    __isa_available_init
0x180001606  jmp     short loc_180001621
0x180001608  call    _get_startup_argv_mode
0x18000160d  mov     ecx, eax; mode
0x18000160f  call    _o__configure_narrow_argv_0
0x180001614  test    eax, eax
0x180001616  jz      short loc_18000161C
0x180001618  xor     al, al
0x18000161a  jmp     short loc_180001623
0x18000161c  call    _initialize_narrow_environment
0x180001621  mov     al, 1
0x180001623  add     rsp, 28h
0x180001627  retn
```
