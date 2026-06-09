# __scrt_dllmain_after_initialize_c

- ea: `0x1800015f8`
- end: `0x18000162c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001148`

## callees

- `0x1800015f8`
- `0x1800019c0`
- `0x180001c4c`
- `0x180001c58`
- `0x180001cc2`
- `0x180001cda`

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
0x1800015f8  sub     rsp, 28h
0x1800015fc  call    __scrt_is_ucrt_dll_in_use
0x180001601  test    eax, eax
0x180001603  jz      short loc_18000160C
0x180001605  call    __isa_available_init
0x18000160a  jmp     short loc_180001625
0x18000160c  call    _get_startup_argv_mode
0x180001611  mov     ecx, eax; mode
0x180001613  call    _o__configure_narrow_argv_0
0x180001618  test    eax, eax
0x18000161a  jz      short loc_180001620
0x18000161c  xor     al, al
0x18000161e  jmp     short loc_180001627
0x180001620  call    _initialize_narrow_environment
0x180001625  mov     al, 1
0x180001627  add     rsp, 28h
0x18000162b  retn
```
