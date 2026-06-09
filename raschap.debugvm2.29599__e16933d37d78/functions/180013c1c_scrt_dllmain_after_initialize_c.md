# __scrt_dllmain_after_initialize_c

- ea: `0x180013c1c`
- end: `0x180013c50`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180013808`

## callees

- `0x180013c1c`
- `0x180014208`
- `0x180014494`
- `0x1800144a0`
- `0x18001455e`
- `0x180014582`

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
0x180013c1c  sub     rsp, 28h
0x180013c20  call    __scrt_is_ucrt_dll_in_use
0x180013c25  test    eax, eax
0x180013c27  jz      short loc_180013C30
0x180013c29  call    __isa_available_init
0x180013c2e  jmp     short loc_180013C49
0x180013c30  call    _get_startup_argv_mode
0x180013c35  mov     ecx, eax; mode
0x180013c37  call    _o__configure_narrow_argv_0
0x180013c3c  test    eax, eax
0x180013c3e  jz      short loc_180013C44
0x180013c40  xor     al, al
0x180013c42  jmp     short loc_180013C4B
0x180013c44  call    _initialize_narrow_environment
0x180013c49  mov     al, 1
0x180013c4b  add     rsp, 28h
0x180013c4f  retn
```
