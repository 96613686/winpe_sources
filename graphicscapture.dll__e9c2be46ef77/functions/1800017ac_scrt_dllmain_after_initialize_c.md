# __scrt_dllmain_after_initialize_c

- ea: `0x1800017ac`
- end: `0x1800017e0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001328`

## callees

- `0x1800017ac`
- `0x180001be0`
- `0x180001e6c`
- `0x180001ee6`
- `0x180001f0a`
- `0x180024670`

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
0x1800017ac  sub     rsp, 28h
0x1800017b0  call    __scrt_is_ucrt_dll_in_use
0x1800017b5  test    eax, eax
0x1800017b7  jz      short loc_1800017C0
0x1800017b9  call    __isa_available_init
0x1800017be  jmp     short loc_1800017D9
0x1800017c0  call    _get_startup_argv_mode
0x1800017c5  mov     ecx, eax; mode
0x1800017c7  call    _o__configure_narrow_argv_0
0x1800017cc  test    eax, eax
0x1800017ce  jz      short loc_1800017D4
0x1800017d0  xor     al, al
0x1800017d2  jmp     short loc_1800017DB
0x1800017d4  call    _initialize_narrow_environment
0x1800017d9  mov     al, 1
0x1800017db  add     rsp, 28h
0x1800017df  retn
```
