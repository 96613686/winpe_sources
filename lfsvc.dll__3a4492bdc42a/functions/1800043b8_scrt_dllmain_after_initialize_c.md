# __scrt_dllmain_after_initialize_c

- ea: `0x1800043b8`
- end: `0x1800043ec`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180003fe8`

## callees

- `0x1800043b8`
- `0x180004998`
- `0x180004c24`
- `0x180004cae`
- `0x180004cd2`
- `0x18000a580`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  const IID *v0; // rdx
  const IID *v1; // rcx
  LPVOID *v2; // r8
  HRESULT startup_argv_mode; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    startup_argv_mode = get_startup_argv_mode(v1, v0, v2);
    if ( o__configure_narrow_argv_0((_crt_argv_mode)startup_argv_mode) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x1800043b8  sub     rsp, 28h
0x1800043bc  call    __scrt_is_ucrt_dll_in_use
0x1800043c1  test    eax, eax
0x1800043c3  jz      short loc_1800043CC
0x1800043c5  call    __isa_available_init
0x1800043ca  jmp     short loc_1800043E5
0x1800043cc  call    _get_startup_argv_mode
0x1800043d1  mov     ecx, eax; mode
0x1800043d3  call    _o__configure_narrow_argv_0
0x1800043d8  test    eax, eax
0x1800043da  jz      short loc_1800043E0
0x1800043dc  xor     al, al
0x1800043de  jmp     short loc_1800043E7
0x1800043e0  call    _initialize_narrow_environment
0x1800043e5  mov     al, 1
0x1800043e7  add     rsp, 28h
0x1800043eb  retn
```
