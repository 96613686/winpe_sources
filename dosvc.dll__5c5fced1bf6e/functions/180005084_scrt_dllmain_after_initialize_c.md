# __scrt_dllmain_after_initialize_c

- ea: `0x180005084`
- end: `0x1800050b8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180004d08`

## callees

- `0x180005084`
- `0x180005700`
- `0x18000598c`
- `0x180005998`
- `0x180005a9e`
- `0x180005ac2`

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
0x180005084  sub     rsp, 28h
0x180005088  call    __scrt_is_ucrt_dll_in_use
0x18000508d  test    eax, eax
0x18000508f  jz      short loc_180005098
0x180005091  call    __isa_available_init
0x180005096  jmp     short loc_1800050B1
0x180005098  call    _get_startup_argv_mode
0x18000509d  mov     ecx, eax; mode
0x18000509f  call    _o__configure_narrow_argv_0
0x1800050a4  test    eax, eax
0x1800050a6  jz      short loc_1800050AC
0x1800050a8  xor     al, al
0x1800050aa  jmp     short loc_1800050B3
0x1800050ac  call    _initialize_narrow_environment
0x1800050b1  mov     al, 1
0x1800050b3  add     rsp, 28h
0x1800050b7  retn
```
