# ___scrt_dllmain_after_initialize_c

- ea: `0x10012cd5`
- end: `0x10012d00`
- name: `___scrt_dllmain_after_initialize_c`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1001280b`

## callees

- `0x10012cd5`
- `0x100130c5`
- `0x100133e7`
- `0x100133f1`
- `0x1001343f`
- `0x10013457`

## pseudocode

```c
char __scrt_dllmain_after_initialize_c()
{
  _crt_argv_mode startup_argv_mode; // eax

  if ( __scrt_is_ucrt_dll_in_use() )
  {
    __isa_available_init();
  }
  else
  {
    startup_argv_mode = _get_startup_argv_mode();
    if ( _o__configure_narrow_argv(startup_argv_mode) )
      return 0;
    _o__initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x10012cd5  call    ___scrt_is_ucrt_dll_in_use
0x10012cda  test    eax, eax
0x10012cdc  jz      short loc_10012CE5
0x10012cde  call    ___isa_available_init
0x10012ce3  jmp     short loc_10012CFD
0x10012ce5  call    __get_startup_argv_mode
0x10012cea  push    eax; mode
0x10012ceb  call    __o__configure_narrow_argv
0x10012cf0  pop     ecx
0x10012cf1  test    eax, eax
0x10012cf3  jz      short loc_10012CF8
0x10012cf5  xor     al, al
0x10012cf7  retn
0x10012cf8  call    __o__initialize_narrow_environment
0x10012cfd  mov     al, 1
0x10012cff  retn
```
