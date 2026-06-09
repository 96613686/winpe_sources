# dllmain_crt_process_detach

- ea: `0x180009d98`
- end: `0x180009e1b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180009c40`

## callees

- `0x180009d98`
- `0x18000a0d0`
- `0x18000a108`
- `0x18000a230`
- `0x18000a268`
- `0x18000a3f8`
- `0x18000a424`
- `0x18000a464`
- `0x18000a4b4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180022090 <= 0 )
    return 0;
  --dword_180022090;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v4) = v3;
  _scrt_release_startup_lock(v4);
  LOBYTE(v5) = a1;
  v6 = (unsigned __int8)_scrt_uninitialize_crt(v5, 0);
  _scrt_dllmain_uninitialize_critical();
  return v6;
}

```

## disassembly

```asm
0x180009d98  mov     [rsp+arg_0], rbx
0x180009d9d  push    rdi
0x180009d9e  sub     rsp, 30h
0x180009da2  mov     dil, cl
0x180009da5  mov     eax, cs:dword_180022090
0x180009dab  test    eax, eax
0x180009dad  jg      short loc_180009DBC
0x180009daf  xor     eax, eax
0x180009db1  mov     rbx, [rsp+38h+arg_0]
0x180009db6  add     rsp, 30h
0x180009dba  pop     rdi
0x180009dbb  retn
0x180009dbc  dec     eax
0x180009dbe  mov     cs:dword_180022090, eax
0x180009dc4  call    __scrt_acquire_startup_lock
0x180009dc9  mov     bl, al
0x180009dcb  mov     [rsp+38h+var_18], al
0x180009dcf  cmp     cs:__scrt_current_native_startup_state, 2
0x180009dd6  jnz     short loc_180009E0E
0x180009dd8  call    __scrt_dllmain_uninitialize_c
0x180009ddd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180009de2  call    _RTC_Terminate
0x180009de7  mov     cs:__scrt_current_native_startup_state, 0
0x180009df1  mov     cl, bl
0x180009df3  call    __scrt_release_startup_lock
0x180009df8  xor     edx, edx
0x180009dfa  mov     cl, dil
0x180009dfd  call    __scrt_uninitialize_crt
0x180009e02  movzx   ebx, al
0x180009e05  call    __scrt_dllmain_uninitialize_critical
0x180009e0a  mov     eax, ebx
0x180009e0c  jmp     short loc_180009DB1
0x180009e0e  mov     ecx, 7
0x180009e13  call    __scrt_fastfail
0x180018bd9  push    rbp
0x180018bdb  sub     rsp, 20h
0x180018bdf  mov     rbp, rdx
0x180018be2  mov     cl, [rbp+20h]
0x180018be5  call    __scrt_release_startup_lock
0x180018bea  nop
0x180018beb  add     rsp, 20h
0x180018bef  pop     rbp
0x180018bf0  retn
0x180018bf2  push    rbp
0x180018bf4  sub     rsp, 20h
0x180018bf8  mov     rbp, rdx
0x180018bfb  add     rsp, 20h
0x180018bff  pop     rbp
0x180018c00  jmp     __scrt_dllmain_uninitialize_critical
```
