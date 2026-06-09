# __scrt_dllmain_after_initialize_c

- ea: `0x180003798`
- end: `0x1800037cc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800033d8`

## callees

- `0x180003798`
- `0x180003d60`
- `0x180003fec`
- `0x180003ff8`
- `0x1800040b2`
- `0x1800040d6`

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
0x180003798  sub     rsp, 28h
0x18000379c  call    __scrt_is_ucrt_dll_in_use
0x1800037a1  test    eax, eax
0x1800037a3  jz      short loc_1800037AC
0x1800037a5  call    __isa_available_init
0x1800037aa  jmp     short loc_1800037C5
0x1800037ac  call    _get_startup_argv_mode
0x1800037b1  mov     ecx, eax; mode
0x1800037b3  call    _o__configure_narrow_argv_0
0x1800037b8  test    eax, eax
0x1800037ba  jz      short loc_1800037C0
0x1800037bc  xor     al, al
0x1800037be  jmp     short loc_1800037C7
0x1800037c0  call    _initialize_narrow_environment
0x1800037c5  mov     al, 1
0x1800037c7  add     rsp, 28h
0x1800037cb  retn
```
