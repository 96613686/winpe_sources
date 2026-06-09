# __scrt_dllmain_after_initialize_c

- ea: `0x180014f58`
- end: `0x180014f8c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180014aa8`

## callees

- `0x180014f58`
- `0x180015308`
- `0x180015594`
- `0x1800155d6`
- `0x1800155ee`
- `0x180017850`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  _crt_argv_mode v0; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    v0 = (unsigned int)NullStart();
    if ( o__configure_narrow_argv_0(v0) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180014f58  sub     rsp, 28h
0x180014f5c  call    __scrt_is_ucrt_dll_in_use
0x180014f61  test    eax, eax
0x180014f63  jz      short loc_180014F6C
0x180014f65  call    __isa_available_init
0x180014f6a  jmp     short loc_180014F85
0x180014f6c  call    NullStart
0x180014f71  mov     ecx, eax; mode
0x180014f73  call    _o__configure_narrow_argv_0
0x180014f78  test    eax, eax
0x180014f7a  jz      short loc_180014F80
0x180014f7c  xor     al, al
0x180014f7e  jmp     short loc_180014F87
0x180014f80  call    _initialize_narrow_environment
0x180014f85  mov     al, 1
0x180014f87  add     rsp, 28h
0x180014f8b  retn
```
