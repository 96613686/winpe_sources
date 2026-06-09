# __scrt_dllmain_after_initialize_c

- ea: `0x180019c68`
- end: `0x180019c9c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800197b8`

## callees

- `0x180019c68`
- `0x18001a078`
- `0x18001a304`
- `0x18001a310`
- `0x18001a38e`
- `0x18001a3b2`

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
0x180019c68  sub     rsp, 28h
0x180019c6c  call    __scrt_is_ucrt_dll_in_use
0x180019c71  test    eax, eax
0x180019c73  jz      short loc_180019C7C
0x180019c75  call    __isa_available_init
0x180019c7a  jmp     short loc_180019C95
0x180019c7c  call    _get_startup_argv_mode
0x180019c81  mov     ecx, eax; mode
0x180019c83  call    _o__configure_narrow_argv_0
0x180019c88  test    eax, eax
0x180019c8a  jz      short loc_180019C90
0x180019c8c  xor     al, al
0x180019c8e  jmp     short loc_180019C97
0x180019c90  call    _initialize_narrow_environment
0x180019c95  mov     al, 1
0x180019c97  add     rsp, 28h
0x180019c9b  retn
```
