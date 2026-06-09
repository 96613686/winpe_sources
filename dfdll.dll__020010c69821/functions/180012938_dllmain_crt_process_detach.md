# dllmain_crt_process_detach

- ea: `0x180012938`
- end: `0x1800129bc`
- name: `dllmain_crt_process_detach`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800127d0`
- `0x1800129bc`

## callees

- `0x180012938`
- `0x180012c90`
- `0x180012db8`
- `0x180012de8`
- `0x180012f6c`
- `0x180012f90`
- `0x1800130cc`
- `0x180013114`
- `0x18001329c`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  __int64 v3; // rcx
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rcx
  BOOL v7; // ebx
  __int64 v8; // rcx
  DWORD v9; // edx
  HINSTANCE v10; // rcx
  LPVOID v11; // r8

  if ( dword_18002DA1C <= 0 )
    return 0;
  --dword_18002DA1C;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state == 2 )
  {
    _scrt_dllmain_uninitialize_c(v3);
    __scrt_uninitialize_type_info();
    RTC_Terminate();
    _scrt_current_native_startup_state = 0;
    LOBYTE(v5) = v4;
    _scrt_release_startup_lock(v5);
    LOBYTE(v6) = a1;
    v7 = (unsigned __int8)_scrt_uninitialize_crt(v6, 0) != 0;
    _scrt_dllmain_uninitialize_critical(v8);
    return v7;
  }
  else
  {
    _scrt_fastfail(7);
    __debugbreak();
    return dllmain_dispatch(v10, v9, v11);
  }
}

```

## disassembly

```asm
0x180012938  mov     [rsp+arg_0], rbx
0x18001293d  push    rdi
0x18001293e  sub     rsp, 30h
0x180012942  mov     dil, cl
0x180012945  mov     eax, cs:dword_18002DA1C
0x18001294b  test    eax, eax
0x18001294d  jg      short loc_18001295C
0x18001294f  xor     eax, eax
0x180012951  mov     rbx, [rsp+38h+arg_0]
0x180012956  add     rsp, 30h
0x18001295a  pop     rdi
0x18001295b  retn
0x18001295c  dec     eax
0x18001295e  mov     cs:dword_18002DA1C, eax
0x180012964  call    __scrt_acquire_startup_lock
0x180012969  mov     bl, al
0x18001296b  mov     [rsp+38h+var_18], al
0x18001296f  cmp     cs:__scrt_current_native_startup_state, 2
0x180012976  jnz     short loc_1800129AF
0x180012978  call    __scrt_dllmain_uninitialize_c
0x18001297d  call    ?__scrt_uninitialize_type_info@@YAXXZ
0x180012982  call    _RTC_Terminate
0x180012987  and     cs:__scrt_current_native_startup_state, 0
0x18001298e  mov     cl, bl
0x180012990  call    __scrt_release_startup_lock
0x180012995  xor     edx, edx
0x180012997  mov     cl, dil
0x18001299a  call    __scrt_uninitialize_crt
0x18001299f  neg     al
0x1800129a1  sbb     ebx, ebx
0x1800129a3  and     ebx, 1
0x1800129a6  call    __scrt_dllmain_uninitialize_critical
0x1800129ab  mov     eax, ebx
0x1800129ad  jmp     short loc_180012951
0x1800129af  mov     ecx, 7
0x1800129b4  call    __scrt_fastfail
0x1800129b9  nop
0x1800129ba  nop
0x1800129bb  int     3; Trap to Debugger
0x18001f451  push    rbp
0x18001f453  sub     rsp, 20h
0x18001f457  mov     rbp, rdx
0x18001f45a  mov     cl, [rbp+20h]
0x18001f45d  call    __scrt_release_startup_lock
0x18001f462  nop
0x18001f463  add     rsp, 20h
0x18001f467  pop     rbp
0x18001f468  retn
0x18001f46a  push    rbp
0x18001f46c  sub     rsp, 20h
0x18001f470  mov     rbp, rdx
0x18001f473  add     rsp, 20h
0x18001f477  pop     rbp
0x18001f478  jmp     __scrt_dllmain_uninitialize_critical
```
