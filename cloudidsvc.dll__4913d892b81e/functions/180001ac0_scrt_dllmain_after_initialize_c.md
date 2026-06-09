# __scrt_dllmain_after_initialize_c

- ea: `0x180001ac0`
- end: `0x180001af4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001738`

## callees

- `0x180001ac0`
- `0x18000207c`
- `0x180002308`
- `0x180002314`
- `0x18000243e`
- `0x180002462`

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
0x180001ac0  sub     rsp, 28h
0x180001ac4  call    __scrt_is_ucrt_dll_in_use
0x180001ac9  test    eax, eax
0x180001acb  jz      short loc_180001AD4
0x180001acd  call    __isa_available_init
0x180001ad2  jmp     short loc_180001AED
0x180001ad4  call    _get_startup_argv_mode
0x180001ad9  mov     ecx, eax; mode
0x180001adb  call    _o__configure_narrow_argv_0
0x180001ae0  test    eax, eax
0x180001ae2  jz      short loc_180001AE8
0x180001ae4  xor     al, al
0x180001ae6  jmp     short loc_180001AEF
0x180001ae8  call    _initialize_narrow_environment
0x180001aed  mov     al, 1
0x180001aef  add     rsp, 28h
0x180001af3  retn
```
