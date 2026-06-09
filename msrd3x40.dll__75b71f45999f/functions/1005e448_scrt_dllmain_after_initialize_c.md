# ___scrt_dllmain_after_initialize_c

- ea: `0x1005e448`
- end: `0x1005e473`
- name: `___scrt_dllmain_after_initialize_c`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1005e06b`

## callees

- `0x1005e448`
- `0x1005ebc7`
- `0x1005eee9`
- `0x1005eef3`
- `0x1005f0d0`
- `0x1005f0f4`

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
0x1005e448  call    ___scrt_is_ucrt_dll_in_use
0x1005e44d  test    eax, eax
0x1005e44f  jz      short loc_1005E458
0x1005e451  call    ___isa_available_init
0x1005e456  jmp     short loc_1005E470
0x1005e458  call    __get_startup_argv_mode
0x1005e45d  push    eax; mode
0x1005e45e  call    __o__configure_narrow_argv
0x1005e463  pop     ecx
0x1005e464  test    eax, eax
0x1005e466  jz      short loc_1005E46B
0x1005e468  xor     al, al
0x1005e46a  retn
0x1005e46b  call    __o__initialize_narrow_environment
0x1005e470  mov     al, 1
0x1005e472  retn
```
