# __scrt_dllmain_after_initialize_c

- ea: `0x18000fe54`
- end: `0x18000fe88`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f9a8`

## callees

- `0x18000e330`
- `0x18000fe54`
- `0x180010748`
- `0x1800109d4`
- `0x180010a76`
- `0x180010a9a`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  CWinRtUrlAccessor *v0; // rcx
  _crt_argv_mode IsDirectory; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    IsDirectory = (unsigned int)CWinRtUrlAccessor::IsDirectory(v0);
    if ( o__configure_narrow_argv_0(IsDirectory) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x18000fe54  sub     rsp, 28h
0x18000fe58  call    __scrt_is_ucrt_dll_in_use
0x18000fe5d  test    eax, eax
0x18000fe5f  jz      short loc_18000FE68
0x18000fe61  call    __isa_available_init
0x18000fe66  jmp     short loc_18000FE81
0x18000fe68  call    ?IsDirectory@CWinRtUrlAccessor@@UEAAJXZ; CWinRtUrlAccessor::IsDirectory(void)
0x18000fe6d  mov     ecx, eax; mode
0x18000fe6f  call    _o__configure_narrow_argv_0
0x18000fe74  test    eax, eax
0x18000fe76  jz      short loc_18000FE7C
0x18000fe78  xor     al, al
0x18000fe7a  jmp     short loc_18000FE83
0x18000fe7c  call    _initialize_narrow_environment
0x18000fe81  mov     al, 1
0x18000fe83  add     rsp, 28h
0x18000fe87  retn
```
