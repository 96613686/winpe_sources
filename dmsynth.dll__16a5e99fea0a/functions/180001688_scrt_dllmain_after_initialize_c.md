# __scrt_dllmain_after_initialize_c

- ea: `0x180001688`
- end: `0x1800016bc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800011d8`

## callees

- `0x180001688`
- `0x180001a38`
- `0x180001cc4`
- `0x180001cd0`
- `0x180001d16`
- `0x180001d2e`

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
0x180001688  sub     rsp, 28h
0x18000168c  call    __scrt_is_ucrt_dll_in_use
0x180001691  test    eax, eax
0x180001693  jz      short loc_18000169C
0x180001695  call    __isa_available_init
0x18000169a  jmp     short loc_1800016B5
0x18000169c  call    _get_startup_argv_mode
0x1800016a1  mov     ecx, eax; mode
0x1800016a3  call    _o__configure_narrow_argv_0
0x1800016a8  test    eax, eax
0x1800016aa  jz      short loc_1800016B0
0x1800016ac  xor     al, al
0x1800016ae  jmp     short loc_1800016B7
0x1800016b0  call    _initialize_narrow_environment
0x1800016b5  mov     al, 1
0x1800016b7  add     rsp, 28h
0x1800016bb  retn
```
