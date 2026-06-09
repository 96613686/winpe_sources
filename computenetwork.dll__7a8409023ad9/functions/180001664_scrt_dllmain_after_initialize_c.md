# __scrt_dllmain_after_initialize_c

- ea: `0x180001664`
- end: `0x180001698`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800012e8`

## callees

- `0x180001664`
- `0x180001c40`
- `0x180001ecc`
- `0x180001ed8`
- `0x180001fea`
- `0x18000200e`

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
0x180001664  sub     rsp, 28h
0x180001668  call    __scrt_is_ucrt_dll_in_use
0x18000166d  test    eax, eax
0x18000166f  jz      short loc_180001678
0x180001671  call    __isa_available_init
0x180001676  jmp     short loc_180001691
0x180001678  call    _get_startup_argv_mode
0x18000167d  mov     ecx, eax; mode
0x18000167f  call    _o__configure_narrow_argv_0
0x180001684  test    eax, eax
0x180001686  jz      short loc_18000168C
0x180001688  xor     al, al
0x18000168a  jmp     short loc_180001693
0x18000168c  call    _initialize_narrow_environment
0x180001691  mov     al, 1
0x180001693  add     rsp, 28h
0x180001697  retn
```
