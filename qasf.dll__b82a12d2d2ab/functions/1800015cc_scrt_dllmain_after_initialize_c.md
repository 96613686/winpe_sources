# __scrt_dllmain_after_initialize_c

- ea: `0x1800015cc`
- end: `0x180001600`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001148`

## callees

- `0x1800015cc`
- `0x1800019a0`
- `0x180001c2c`
- `0x180001c8e`
- `0x180001ca6`
- `0x18000fea0`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  CWMWriter *v0; // rcx
  _crt_argv_mode MiscFlags; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    MiscFlags = CWMWriter::GetMiscFlags(v0);
    if ( o__configure_narrow_argv_0(MiscFlags) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x1800015cc  sub     rsp, 28h
0x1800015d0  call    __scrt_is_ucrt_dll_in_use
0x1800015d5  test    eax, eax
0x1800015d7  jz      short loc_1800015E0
0x1800015d9  call    __isa_available_init
0x1800015de  jmp     short loc_1800015F9
0x1800015e0  call    ?GetMiscFlags@CWMWriter@@EEAAKXZ; CWMWriter::GetMiscFlags(void)
0x1800015e5  mov     ecx, eax; mode
0x1800015e7  call    _o__configure_narrow_argv_0
0x1800015ec  test    eax, eax
0x1800015ee  jz      short loc_1800015F4
0x1800015f0  xor     al, al
0x1800015f2  jmp     short loc_1800015FB
0x1800015f4  call    _initialize_narrow_environment
0x1800015f9  mov     al, 1
0x1800015fb  add     rsp, 28h
0x1800015ff  retn
```
