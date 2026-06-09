# __scrt_dllmain_after_initialize_c

- ea: `0x180012ccc`
- end: `0x180012d00`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180012820`

## callees

- `0x180003e60`
- `0x180012ccc`
- `0x180013580`
- `0x180013724`
- `0x1800179d4`
- `0x180017d68`

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
    v0 = (unsigned int)Dfdll::CBuffer<char>::SizeOfElement();
    if ( configure_narrow_argv(v0) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180012ccc  sub     rsp, 28h
0x180012cd0  call    __scrt_is_ucrt_dll_in_use
0x180012cd5  test    eax, eax
0x180012cd7  jz      short loc_180012CE0
0x180012cd9  call    __isa_available_init
0x180012cde  jmp     short loc_180012CF9
0x180012ce0  call    ?SizeOfElement@?$CBuffer@D@Dfdll@@MEAAIXZ
0x180012ce5  mov     ecx, eax; mode
0x180012ce7  call    _configure_narrow_argv
0x180012cec  test    eax, eax
0x180012cee  jz      short loc_180012CF4
0x180012cf0  xor     al, al
0x180012cf2  jmp     short loc_180012CFB
0x180012cf4  call    _initialize_narrow_environment
0x180012cf9  mov     al, 1
0x180012cfb  add     rsp, 28h
0x180012cff  retn
```
