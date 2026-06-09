# __scrt_dllmain_after_initialize_c

- ea: `0x180002060`
- end: `0x180002094`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001c78`

## callees

- `0x180002060`
- `0x180002698`
- `0x180002924`
- `0x1800029ba`
- `0x1800029de`
- `0x1800035f0`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  ATL::CRegObject *v0; // rcx
  _crt_argv_mode v1; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    v1 = ATL::CRegObject::AddRef(v0);
    if ( o__configure_narrow_argv_0(v1) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180002060  sub     rsp, 28h
0x180002064  call    __scrt_is_ucrt_dll_in_use
0x180002069  test    eax, eax
0x18000206b  jz      short loc_180002074
0x18000206d  call    __isa_available_init
0x180002072  jmp     short loc_18000208D
0x180002074  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x180002079  mov     ecx, eax; mode
0x18000207b  call    _o__configure_narrow_argv_0
0x180002080  test    eax, eax
0x180002082  jz      short loc_180002088
0x180002084  xor     al, al
0x180002086  jmp     short loc_18000208F
0x180002088  call    _initialize_narrow_environment
0x18000208d  mov     al, 1
0x18000208f  add     rsp, 28h
0x180002093  retn
```
