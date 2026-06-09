# __scrt_dllmain_after_initialize_c

- ea: `0x180016294`
- end: `0x1800162c8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180015d78`

## callees

- `0x180016294`
- `0x1800166cc`
- `0x180016958`
- `0x180016964`
- `0x180016a06`
- `0x180016a1e`

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
0x180016294  sub     rsp, 28h
0x180016298  call    __scrt_is_ucrt_dll_in_use
0x18001629d  test    eax, eax
0x18001629f  jz      short loc_1800162A8
0x1800162a1  call    __isa_available_init
0x1800162a6  jmp     short loc_1800162C1
0x1800162a8  call    _get_startup_argv_mode
0x1800162ad  mov     ecx, eax; mode
0x1800162af  call    _o__configure_narrow_argv_0
0x1800162b4  test    eax, eax
0x1800162b6  jz      short loc_1800162BC
0x1800162b8  xor     al, al
0x1800162ba  jmp     short loc_1800162C3
0x1800162bc  call    _initialize_narrow_environment
0x1800162c1  mov     al, 1
0x1800162c3  add     rsp, 28h
0x1800162c7  retn
```
