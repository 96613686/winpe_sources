# __scrt_dllmain_after_initialize_c

- ea: `0x1800011f4`
- end: `0x180001228`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002388`

## callees

- `0x1800011f4`
- `0x1800015fc`
- `0x1800018a0`
- `0x1800018ea`
- `0x18000190e`
- `0x1800058f0`

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
0x1800011f4  sub     rsp, 28h
0x1800011f8  call    __scrt_is_ucrt_dll_in_use
0x1800011fd  test    eax, eax
0x1800011ff  jz      short loc_180001208
0x180001201  call    __isa_available_init
0x180001206  jmp     short loc_180001221
0x180001208  call    _get_startup_argv_mode
0x18000120d  mov     ecx, eax; mode
0x18000120f  call    _o__configure_narrow_argv_0
0x180001214  test    eax, eax
0x180001216  jz      short loc_18000121C
0x180001218  xor     al, al
0x18000121a  jmp     short loc_180001223
0x18000121c  call    _initialize_narrow_environment
0x180001221  mov     al, 1
0x180001223  add     rsp, 28h
0x180001227  retn
```
