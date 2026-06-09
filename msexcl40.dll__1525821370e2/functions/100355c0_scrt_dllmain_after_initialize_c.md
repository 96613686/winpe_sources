# ___scrt_dllmain_after_initialize_c

- ea: `0x100355c0`
- end: `0x100355eb`
- name: `___scrt_dllmain_after_initialize_c`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x100351cb`

## callees

- `0x100355c0`
- `0x10035b49`
- `0x10035e6b`
- `0x10035e75`
- `0x10035ee0`
- `0x10035f04`

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
0x100355c0  call    ___scrt_is_ucrt_dll_in_use
0x100355c5  test    eax, eax
0x100355c7  jz      short loc_100355D0
0x100355c9  call    ___isa_available_init
0x100355ce  jmp     short loc_100355E8
0x100355d0  call    __get_startup_argv_mode
0x100355d5  push    eax; mode
0x100355d6  call    __o__configure_narrow_argv
0x100355db  pop     ecx
0x100355dc  test    eax, eax
0x100355de  jz      short loc_100355E3
0x100355e0  xor     al, al
0x100355e2  retn
0x100355e3  call    __o__initialize_narrow_environment
0x100355e8  mov     al, 1
0x100355ea  retn
```
