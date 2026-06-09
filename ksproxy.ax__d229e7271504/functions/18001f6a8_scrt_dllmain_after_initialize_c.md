# __scrt_dllmain_after_initialize_c

- ea: `0x18001f6a8`
- end: `0x18001f6dc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001f308`

## callees

- `0x18001f6a8`
- `0x18001fbe0`
- `0x18001fe6c`
- `0x18001fe78`
- `0x18001ff06`
- `0x18001ff2a`

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
0x18001f6a8  sub     rsp, 28h
0x18001f6ac  call    __scrt_is_ucrt_dll_in_use
0x18001f6b1  test    eax, eax
0x18001f6b3  jz      short loc_18001F6BC
0x18001f6b5  call    __isa_available_init
0x18001f6ba  jmp     short loc_18001F6D5
0x18001f6bc  call    _get_startup_argv_mode
0x18001f6c1  mov     ecx, eax; mode
0x18001f6c3  call    _o__configure_narrow_argv_0
0x18001f6c8  test    eax, eax
0x18001f6ca  jz      short loc_18001F6D0
0x18001f6cc  xor     al, al
0x18001f6ce  jmp     short loc_18001F6D7
0x18001f6d0  call    _initialize_narrow_environment
0x18001f6d5  mov     al, 1
0x18001f6d7  add     rsp, 28h
0x18001f6db  retn
```
