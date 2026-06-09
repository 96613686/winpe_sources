# __scrt_dllmain_after_initialize_c

- ea: `0x1800017a4`
- end: `0x1800017d8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001298`

## callees

- `0x1800017a4`
- `0x180001c20`
- `0x180001eac`
- `0x180001eb8`
- `0x180001f5e`
- `0x180001f82`

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
0x1800017a4  sub     rsp, 28h
0x1800017a8  call    __scrt_is_ucrt_dll_in_use
0x1800017ad  test    eax, eax
0x1800017af  jz      short loc_1800017B8
0x1800017b1  call    __isa_available_init
0x1800017b6  jmp     short loc_1800017D1
0x1800017b8  call    _get_startup_argv_mode
0x1800017bd  mov     ecx, eax; mode
0x1800017bf  call    _o__configure_narrow_argv_0
0x1800017c4  test    eax, eax
0x1800017c6  jz      short loc_1800017CC
0x1800017c8  xor     al, al
0x1800017ca  jmp     short loc_1800017D3
0x1800017cc  call    _initialize_narrow_environment
0x1800017d1  mov     al, 1
0x1800017d3  add     rsp, 28h
0x1800017d7  retn
```
