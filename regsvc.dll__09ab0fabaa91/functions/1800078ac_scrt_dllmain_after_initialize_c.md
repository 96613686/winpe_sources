# __scrt_dllmain_after_initialize_c

- ea: `0x1800078ac`
- end: `0x1800078e0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180007428`

## callees

- `0x1800078ac`
- `0x180007c80`
- `0x180007f0c`
- `0x180007f18`
- `0x180007fa6`
- `0x180007fbe`

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
0x1800078ac  sub     rsp, 28h
0x1800078b0  call    __scrt_is_ucrt_dll_in_use
0x1800078b5  test    eax, eax
0x1800078b7  jz      short loc_1800078C0
0x1800078b9  call    __isa_available_init
0x1800078be  jmp     short loc_1800078D9
0x1800078c0  call    _get_startup_argv_mode
0x1800078c5  mov     ecx, eax; mode
0x1800078c7  call    _o__configure_narrow_argv_0
0x1800078cc  test    eax, eax
0x1800078ce  jz      short loc_1800078D4
0x1800078d0  xor     al, al
0x1800078d2  jmp     short loc_1800078DB
0x1800078d4  call    _initialize_narrow_environment
0x1800078d9  mov     al, 1
0x1800078db  add     rsp, 28h
0x1800078df  retn
```
