# __scrt_dllmain_after_initialize_c

- ea: `0x180001734`
- end: `0x180001768`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800013b8`

## callees

- `0x180001734`
- `0x180001df8`
- `0x180002084`
- `0x18000210e`
- `0x180002132`
- `0x18000c4e0`

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
0x180001734  sub     rsp, 28h
0x180001738  call    __scrt_is_ucrt_dll_in_use
0x18000173d  test    eax, eax
0x18000173f  jz      short loc_180001748
0x180001741  call    __isa_available_init
0x180001746  jmp     short loc_180001761
0x180001748  call    _get_startup_argv_mode
0x18000174d  mov     ecx, eax; mode
0x18000174f  call    _o__configure_narrow_argv_0
0x180001754  test    eax, eax
0x180001756  jz      short loc_18000175C
0x180001758  xor     al, al
0x18000175a  jmp     short loc_180001763
0x18000175c  call    _initialize_narrow_environment
0x180001761  mov     al, 1
0x180001763  add     rsp, 28h
0x180001767  retn
```
