# __scrt_dllmain_after_initialize_c

- ea: `0x18000c834`
- end: `0x18000c868`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c4e8`

## callees

- `0x18000c834`
- `0x18000ccd8`
- `0x18000cf64`
- `0x18000cf70`
- `0x18000d01a`
- `0x18000d03e`

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
0x18000c834  sub     rsp, 28h
0x18000c838  call    __scrt_is_ucrt_dll_in_use
0x18000c83d  test    eax, eax
0x18000c83f  jz      short loc_18000C848
0x18000c841  call    __isa_available_init
0x18000c846  jmp     short loc_18000C861
0x18000c848  call    _get_startup_argv_mode
0x18000c84d  mov     ecx, eax; mode
0x18000c84f  call    _o__configure_narrow_argv_0
0x18000c854  test    eax, eax
0x18000c856  jz      short loc_18000C85C
0x18000c858  xor     al, al
0x18000c85a  jmp     short loc_18000C863
0x18000c85c  call    _initialize_narrow_environment
0x18000c861  mov     al, 1
0x18000c863  add     rsp, 28h
0x18000c867  retn
```
