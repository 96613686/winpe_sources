# __scrt_dllmain_after_initialize_c

- ea: `0x180001774`
- end: `0x1800017a8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800013f8`

## callees

- `0x180001774`
- `0x180001b8c`
- `0x180001ff8`
- `0x1800020ea`
- `0x18000211a`
- `0x180011790`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  GenClrDataTarget *v0; // rcx
  _crt_argv_mode v1; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    v1 = GenClrDataTarget::AddRef(v0);
    if ( o__configure_narrow_argv_0(v1) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180001774  sub     rsp, 28h
0x180001778  call    __scrt_is_ucrt_dll_in_use
0x18000177d  test    eax, eax
0x18000177f  jz      short loc_180001788
0x180001781  call    __isa_available_init
0x180001786  jmp     short loc_1800017A1
0x180001788  call    ?AddRef@GenClrDataTarget@@UEAAKXZ; GenClrDataTarget::AddRef(void)
0x18000178d  mov     ecx, eax; mode
0x18000178f  call    _o__configure_narrow_argv_0
0x180001794  test    eax, eax
0x180001796  jz      short loc_18000179C
0x180001798  xor     al, al
0x18000179a  jmp     short loc_1800017A3
0x18000179c  call    _initialize_narrow_environment
0x1800017a1  mov     al, 1
0x1800017a3  add     rsp, 28h
0x1800017a7  retn
```
