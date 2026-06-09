# __scrt_dllmain_after_initialize_c

- ea: `0x180001588`
- end: `0x1800015bc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800010e8`

## callees

- `0x180001588`
- `0x180001938`
- `0x180001bc4`
- `0x180001bd0`
- `0x180001c36`
- `0x180001c4e`

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
0x180001588  sub     rsp, 28h
0x18000158c  call    __scrt_is_ucrt_dll_in_use
0x180001591  test    eax, eax
0x180001593  jz      short loc_18000159C
0x180001595  call    __isa_available_init
0x18000159a  jmp     short loc_1800015B5
0x18000159c  call    _get_startup_argv_mode
0x1800015a1  mov     ecx, eax; mode
0x1800015a3  call    _o__configure_narrow_argv_0
0x1800015a8  test    eax, eax
0x1800015aa  jz      short loc_1800015B0
0x1800015ac  xor     al, al
0x1800015ae  jmp     short loc_1800015B7
0x1800015b0  call    _initialize_narrow_environment
0x1800015b5  mov     al, 1
0x1800015b7  add     rsp, 28h
0x1800015bb  retn
```
