# dllmain_crt_process_detach

- ea: `0x18000f7f8`
- end: `0x18000f87b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000f6a0`

## callees

- `0x18000f7f8`
- `0x18000fa34`
- `0x18000fb5c`
- `0x18000fb94`
- `0x18000fd24`
- `0x18000fd50`
- `0x18000feec`
- `0x18000ff34`
- `0x18000ff84`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180022230 <= 0 )
    return 0;
  --dword_180022230;
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
0x18000f7f8  mov     [rsp+arg_0], rbx
0x18000f7fd  push    rdi
0x18000f7fe  sub     rsp, 30h
0x18000f802  mov     dil, cl
0x18000f805  mov     eax, cs:dword_180022230
0x18000f80b  test    eax, eax
0x18000f80d  jg      short loc_18000F81C
0x18000f80f  xor     eax, eax
0x18000f811  mov     rbx, [rsp+38h+arg_0]
0x18000f816  add     rsp, 30h
0x18000f81a  pop     rdi
0x18000f81b  retn
0x18000f81c  dec     eax
0x18000f81e  mov     cs:dword_180022230, eax
0x18000f824  call    __scrt_acquire_startup_lock
0x18000f829  mov     bl, al
0x18000f82b  mov     [rsp+38h+var_18], al
0x18000f82f  cmp     cs:__scrt_current_native_startup_state, 2
0x18000f836  jnz     short loc_18000F86E
0x18000f838  call    __scrt_dllmain_uninitialize_c
0x18000f83d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000f842  call    _RTC_Terminate
0x18000f847  mov     cs:__scrt_current_native_startup_state, 0
0x18000f851  mov     cl, bl
0x18000f853  call    __scrt_release_startup_lock
0x18000f858  xor     edx, edx
0x18000f85a  mov     cl, dil
0x18000f85d  call    __scrt_uninitialize_crt
0x18000f862  movzx   ebx, al
0x18000f865  call    __scrt_dllmain_uninitialize_critical
0x18000f86a  mov     eax, ebx
0x18000f86c  jmp     short loc_18000F811
0x18000f86e  mov     ecx, 7
0x18000f873  call    __scrt_fastfail
0x1800171eb  push    rbp
0x1800171ed  sub     rsp, 20h
0x1800171f1  mov     rbp, rdx
0x1800171f4  mov     cl, [rbp+20h]
0x1800171f7  call    __scrt_release_startup_lock
0x1800171fc  nop
0x1800171fd  add     rsp, 20h
0x180017201  pop     rbp
0x180017202  retn
0x180017204  push    rbp
0x180017206  sub     rsp, 20h
0x18001720a  mov     rbp, rdx
0x18001720d  add     rsp, 20h
0x180017211  pop     rbp
0x180017212  jmp     __scrt_dllmain_uninitialize_critical
```
