# dllmain_crt_process_detach

- ea: `0x180002a98`
- end: `0x180002b1b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002940`

## callees

- `0x180002a98`
- `0x180002cf8`
- `0x180002e20`
- `0x180002e58`
- `0x180002fe8`
- `0x180003014`
- `0x180003180`
- `0x1800031c8`
- `0x180003218`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  __int64 v3; // rcx
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rcx

  if ( dword_18000A1D0 <= 0 )
    return 0;
  --dword_18000A1D0;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
  _scrt_dllmain_uninitialize_c(v3);
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v5) = v4;
  _scrt_release_startup_lock(v5);
  LOBYTE(v6) = a1;
  v7 = (unsigned __int8)_scrt_uninitialize_crt(v6, 0);
  _scrt_dllmain_uninitialize_critical(v8);
  return v7;
}

```

## disassembly

```asm
0x180002a98  mov     [rsp+arg_0], rbx
0x180002a9d  push    rdi
0x180002a9e  sub     rsp, 30h
0x180002aa2  mov     dil, cl
0x180002aa5  mov     eax, cs:dword_18000A1D0
0x180002aab  test    eax, eax
0x180002aad  jg      short loc_180002ABC
0x180002aaf  xor     eax, eax
0x180002ab1  mov     rbx, [rsp+38h+arg_0]
0x180002ab6  add     rsp, 30h
0x180002aba  pop     rdi
0x180002abb  retn
0x180002abc  dec     eax
0x180002abe  mov     cs:dword_18000A1D0, eax
0x180002ac4  call    __scrt_acquire_startup_lock
0x180002ac9  mov     bl, al
0x180002acb  mov     [rsp+38h+var_18], al
0x180002acf  cmp     cs:__scrt_current_native_startup_state, 2
0x180002ad6  jnz     short loc_180002B0E
0x180002ad8  call    __scrt_dllmain_uninitialize_c
0x180002add  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002ae2  call    _RTC_Terminate
0x180002ae7  mov     cs:__scrt_current_native_startup_state, 0
0x180002af1  mov     cl, bl
0x180002af3  call    __scrt_release_startup_lock
0x180002af8  xor     edx, edx
0x180002afa  mov     cl, dil
0x180002afd  call    __scrt_uninitialize_crt
0x180002b02  movzx   ebx, al
0x180002b05  call    __scrt_dllmain_uninitialize_critical
0x180002b0a  mov     eax, ebx
0x180002b0c  jmp     short loc_180002AB1
0x180002b0e  mov     ecx, 7
0x180002b13  call    __scrt_fastfail
0x1800050c9  push    rbp
0x1800050cb  sub     rsp, 20h
0x1800050cf  mov     rbp, rdx
0x1800050d2  mov     cl, [rbp+20h]
0x1800050d5  call    __scrt_release_startup_lock
0x1800050da  nop
0x1800050db  add     rsp, 20h
0x1800050df  pop     rbp
0x1800050e0  retn
0x1800050e2  push    rbp
0x1800050e4  sub     rsp, 20h
0x1800050e8  mov     rbp, rdx
0x1800050eb  add     rsp, 20h
0x1800050ef  pop     rbp
0x1800050f0  jmp     __scrt_dllmain_uninitialize_critical
```
