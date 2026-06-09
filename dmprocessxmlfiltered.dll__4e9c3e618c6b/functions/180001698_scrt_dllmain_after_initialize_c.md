# __scrt_dllmain_after_initialize_c

- ea: `0x180001698`
- end: `0x1800016cc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001208`

## callees

- `0x180001698`
- `0x180001ac0`
- `0x180001d4c`
- `0x180001de2`
- `0x180001e06`
- `0x1800020e0`

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
0x180001698  sub     rsp, 28h
0x18000169c  call    __scrt_is_ucrt_dll_in_use
0x1800016a1  test    eax, eax
0x1800016a3  jz      short loc_1800016AC
0x1800016a5  call    __isa_available_init
0x1800016aa  jmp     short loc_1800016C5
0x1800016ac  call    _get_startup_argv_mode
0x1800016b1  mov     ecx, eax; mode
0x1800016b3  call    _o__configure_narrow_argv_0
0x1800016b8  test    eax, eax
0x1800016ba  jz      short loc_1800016C0
0x1800016bc  xor     al, al
0x1800016be  jmp     short loc_1800016C7
0x1800016c0  call    _initialize_narrow_environment
0x1800016c5  mov     al, 1
0x1800016c7  add     rsp, 28h
0x1800016cb  retn
```
