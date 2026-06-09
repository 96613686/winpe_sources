# __scrt_dllmain_after_initialize_c

- ea: `0x180006488`
- end: `0x1800064bc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180006008`

## callees

- `0x180006488`
- `0x180006a40`
- `0x180006ccc`
- `0x180006cd8`
- `0x180006dde`
- `0x180006e02`

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
0x180006488  sub     rsp, 28h
0x18000648c  call    __scrt_is_ucrt_dll_in_use
0x180006491  test    eax, eax
0x180006493  jz      short loc_18000649C
0x180006495  call    __isa_available_init
0x18000649a  jmp     short loc_1800064B5
0x18000649c  call    _get_startup_argv_mode
0x1800064a1  mov     ecx, eax; mode
0x1800064a3  call    _o__configure_narrow_argv_0
0x1800064a8  test    eax, eax
0x1800064aa  jz      short loc_1800064B0
0x1800064ac  xor     al, al
0x1800064ae  jmp     short loc_1800064B7
0x1800064b0  call    _initialize_narrow_environment
0x1800064b5  mov     al, 1
0x1800064b7  add     rsp, 28h
0x1800064bb  retn
```
