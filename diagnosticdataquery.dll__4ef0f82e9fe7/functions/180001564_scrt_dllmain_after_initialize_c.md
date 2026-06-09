# __scrt_dllmain_after_initialize_c

- ea: `0x180001564`
- end: `0x180001598`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800011e8`

## callees

- `0x180001564`
- `0x180001a40`
- `0x180001b70`
- `0x180001dfc`
- `0x1800050da`
- `0x1800050e6`

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
    if ( configure_narrow_argv_0(startup_argv_mode) )
      return 0;
    initialize_narrow_environment_0();
  }
  return 1;
}

```

## disassembly

```asm
0x180001564  sub     rsp, 28h
0x180001568  call    __scrt_is_ucrt_dll_in_use
0x18000156d  test    eax, eax
0x18000156f  jz      short loc_180001578
0x180001571  call    __isa_available_init
0x180001576  jmp     short loc_180001591
0x180001578  call    _get_startup_argv_mode
0x18000157d  mov     ecx, eax; mode
0x18000157f  call    _configure_narrow_argv_0
0x180001584  test    eax, eax
0x180001586  jz      short loc_18000158C
0x180001588  xor     al, al
0x18000158a  jmp     short loc_180001593
0x18000158c  call    _initialize_narrow_environment_0
0x180001591  mov     al, 1
0x180001593  add     rsp, 28h
0x180001597  retn
```
