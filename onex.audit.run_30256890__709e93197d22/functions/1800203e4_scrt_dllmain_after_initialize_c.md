# __scrt_dllmain_after_initialize_c

- ea: `0x1800203e4`
- end: `0x180020418`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ff38`

## callees

- `0x1800203e4`
- `0x180020798`
- `0x180020a24`
- `0x180020a30`
- `0x180020a96`
- `0x180020aae`

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
0x1800203e4  sub     rsp, 28h
0x1800203e8  call    __scrt_is_ucrt_dll_in_use
0x1800203ed  test    eax, eax
0x1800203ef  jz      short loc_1800203F8
0x1800203f1  call    __isa_available_init
0x1800203f6  jmp     short loc_180020411
0x1800203f8  call    _get_startup_argv_mode
0x1800203fd  mov     ecx, eax; mode
0x1800203ff  call    _o__configure_narrow_argv_0
0x180020404  test    eax, eax
0x180020406  jz      short loc_18002040C
0x180020408  xor     al, al
0x18002040a  jmp     short loc_180020413
0x18002040c  call    _initialize_narrow_environment
0x180020411  mov     al, 1
0x180020413  add     rsp, 28h
0x180020417  retn
```
