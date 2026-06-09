# __scrt_dllmain_after_initialize_c

- ea: `0x18000a584`
- end: `0x18000a5b8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a208`

## callees

- `0x18000a584`
- `0x18000aaf0`
- `0x18000ad7c`
- `0x18000ad88`
- `0x18000ae2e`
- `0x18000ae52`

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
0x18000a584  sub     rsp, 28h
0x18000a588  call    __scrt_is_ucrt_dll_in_use
0x18000a58d  test    eax, eax
0x18000a58f  jz      short loc_18000A598
0x18000a591  call    __isa_available_init
0x18000a596  jmp     short loc_18000A5B1
0x18000a598  call    _get_startup_argv_mode
0x18000a59d  mov     ecx, eax; mode
0x18000a59f  call    _o__configure_narrow_argv_0
0x18000a5a4  test    eax, eax
0x18000a5a6  jz      short loc_18000A5AC
0x18000a5a8  xor     al, al
0x18000a5aa  jmp     short loc_18000A5B3
0x18000a5ac  call    _initialize_narrow_environment
0x18000a5b1  mov     al, 1
0x18000a5b3  add     rsp, 28h
0x18000a5b7  retn
```
