# ___scrt_dllmain_after_initialize_c

- ea: `0x1003ac98`
- end: `0x1003acc3`
- name: `___scrt_dllmain_after_initialize_c`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1003a81b`

## callees

- `0x1000d780`
- `0x1003ac98`
- `0x1003b19b`
- `0x1003b4bd`
- `0x1003b523`
- `0x1003b547`

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
0x1003ac98  call    ___scrt_is_ucrt_dll_in_use
0x1003ac9d  test    eax, eax
0x1003ac9f  jz      short loc_1003ACA8
0x1003aca1  call    ___isa_available_init
0x1003aca6  jmp     short loc_1003ACC0
0x1003aca8  call    __get_startup_argv_mode
0x1003acad  push    eax; mode
0x1003acae  call    __o__configure_narrow_argv
0x1003acb3  pop     ecx
0x1003acb4  test    eax, eax
0x1003acb6  jz      short loc_1003ACBB
0x1003acb8  xor     al, al
0x1003acba  retn
0x1003acbb  call    __o__initialize_narrow_environment
0x1003acc0  mov     al, 1
0x1003acc2  retn
```
