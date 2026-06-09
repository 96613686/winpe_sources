# __scrt_dllmain_after_initialize_c

- ea: `0x180001e78`
- end: `0x180001eac`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800019c8`

## callees

- `0x180001e78`
- `0x1800022a0`
- `0x18000252c`
- `0x180002538`
- `0x18000259e`
- `0x1800025c2`

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
0x180001e78  sub     rsp, 28h
0x180001e7c  call    __scrt_is_ucrt_dll_in_use
0x180001e81  test    eax, eax
0x180001e83  jz      short loc_180001E8C
0x180001e85  call    __isa_available_init
0x180001e8a  jmp     short loc_180001EA5
0x180001e8c  call    _get_startup_argv_mode
0x180001e91  mov     ecx, eax; mode
0x180001e93  call    _o__configure_narrow_argv_0
0x180001e98  test    eax, eax
0x180001e9a  jz      short loc_180001EA0
0x180001e9c  xor     al, al
0x180001e9e  jmp     short loc_180001EA7
0x180001ea0  call    _initialize_narrow_environment
0x180001ea5  mov     al, 1
0x180001ea7  add     rsp, 28h
0x180001eab  retn
```
