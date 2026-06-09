# __scrt_dllmain_after_initialize_c

- ea: `0x180004dac`
- end: `0x180004de0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180004928`

## callees

- `0x180004dac`
- `0x180005180`
- `0x18000540c`
- `0x180005418`
- `0x180005476`
- `0x18000548e`

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
0x180004dac  sub     rsp, 28h
0x180004db0  call    __scrt_is_ucrt_dll_in_use
0x180004db5  test    eax, eax
0x180004db7  jz      short loc_180004DC0
0x180004db9  call    __isa_available_init
0x180004dbe  jmp     short loc_180004DD9
0x180004dc0  call    _get_startup_argv_mode
0x180004dc5  mov     ecx, eax; mode
0x180004dc7  call    _o__configure_narrow_argv_0
0x180004dcc  test    eax, eax
0x180004dce  jz      short loc_180004DD4
0x180004dd0  xor     al, al
0x180004dd2  jmp     short loc_180004DDB
0x180004dd4  call    _initialize_narrow_environment
0x180004dd9  mov     al, 1
0x180004ddb  add     rsp, 28h
0x180004ddf  retn
```
