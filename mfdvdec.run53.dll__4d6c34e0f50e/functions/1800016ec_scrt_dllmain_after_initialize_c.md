# __scrt_dllmain_after_initialize_c

- ea: `0x1800016ec`
- end: `0x180001720`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001268`

## callees

- `0x1800016ec`
- `0x180001b20`
- `0x180001dac`
- `0x180001db8`
- `0x180001e12`
- `0x180001e36`

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
0x1800016ec  sub     rsp, 28h
0x1800016f0  call    __scrt_is_ucrt_dll_in_use
0x1800016f5  test    eax, eax
0x1800016f7  jz      short loc_180001700
0x1800016f9  call    __isa_available_init
0x1800016fe  jmp     short loc_180001719
0x180001700  call    _get_startup_argv_mode
0x180001705  mov     ecx, eax; mode
0x180001707  call    _o__configure_narrow_argv_0
0x18000170c  test    eax, eax
0x18000170e  jz      short loc_180001714
0x180001710  xor     al, al
0x180001712  jmp     short loc_18000171B
0x180001714  call    _initialize_narrow_environment
0x180001719  mov     al, 1
0x18000171b  add     rsp, 28h
0x18000171f  retn
```
