# __scrt_dllmain_after_initialize_c

- ea: `0x180002618`
- end: `0x18000264c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002178`

## callees

- `0x180002618`
- `0x180002f40`
- `0x1800031cc`
- `0x180003276`
- `0x18000329a`
- `0x18000bcb0`

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
0x180002618  sub     rsp, 28h
0x18000261c  call    __scrt_is_ucrt_dll_in_use
0x180002621  test    eax, eax
0x180002623  jz      short loc_18000262C
0x180002625  call    __isa_available_init
0x18000262a  jmp     short loc_180002645
0x18000262c  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x180002631  mov     ecx, eax; mode
0x180002633  call    _o__configure_narrow_argv_0
0x180002638  test    eax, eax
0x18000263a  jz      short loc_180002640
0x18000263c  xor     al, al
0x18000263e  jmp     short loc_180002647
0x180002640  call    _initialize_narrow_environment
0x180002645  mov     al, 1
0x180002647  add     rsp, 28h
0x18000264b  retn
```
