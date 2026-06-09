# __scrt_dllmain_after_initialize_c

- ea: `0x18000d104`
- end: `0x18000d138`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d4d8`

## callees

- `0x18000d104`
- `0x18000d868`
- `0x18000db10`
- `0x18000db1c`
- `0x18000dd22`
- `0x18000dd46`

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
0x18000d104  sub     rsp, 28h
0x18000d108  call    __scrt_is_ucrt_dll_in_use
0x18000d10d  test    eax, eax
0x18000d10f  jz      short loc_18000D118
0x18000d111  call    __isa_available_init
0x18000d116  jmp     short loc_18000D131
0x18000d118  call    _get_startup_argv_mode
0x18000d11d  mov     ecx, eax; mode
0x18000d11f  call    _o__configure_narrow_argv_0
0x18000d124  test    eax, eax
0x18000d126  jz      short loc_18000D12C
0x18000d128  xor     al, al
0x18000d12a  jmp     short loc_18000D133
0x18000d12c  call    _initialize_narrow_environment
0x18000d131  mov     al, 1
0x18000d133  add     rsp, 28h
0x18000d137  retn
```
