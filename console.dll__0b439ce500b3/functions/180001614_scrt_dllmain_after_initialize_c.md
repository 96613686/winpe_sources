# __scrt_dllmain_after_initialize_c

- ea: `0x180001614`
- end: `0x180001648`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001298`

## callees

- `0x180001614`
- `0x180001c20`
- `0x180001eac`
- `0x180001eb8`
- `0x180001fea`
- `0x18000200e`

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
0x180001614  sub     rsp, 28h
0x180001618  call    __scrt_is_ucrt_dll_in_use
0x18000161d  test    eax, eax
0x18000161f  jz      short loc_180001628
0x180001621  call    __isa_available_init
0x180001626  jmp     short loc_180001641
0x180001628  call    _get_startup_argv_mode
0x18000162d  mov     ecx, eax; mode
0x18000162f  call    _o__configure_narrow_argv_0
0x180001634  test    eax, eax
0x180001636  jz      short loc_18000163C
0x180001638  xor     al, al
0x18000163a  jmp     short loc_180001643
0x18000163c  call    _initialize_narrow_environment
0x180001641  mov     al, 1
0x180001643  add     rsp, 28h
0x180001647  retn
```
