# dllmain_crt_process_detach

- ea: `0x1800015e8`
- end: `0x18000166b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001490`

## callees

- `0x1800015e8`
- `0x180001950`
- `0x180001a78`
- `0x180001ab0`
- `0x180001c40`
- `0x180001c6c`
- `0x180001e1c`
- `0x180001e64`
- `0x180001eb4`

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

  if ( dword_180034D10 <= 0 )
    return 0;
  --dword_180034D10;
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
0x1800015e8  mov     [rsp+arg_0], rbx
0x1800015ed  push    rdi
0x1800015ee  sub     rsp, 30h
0x1800015f2  mov     dil, cl
0x1800015f5  mov     eax, cs:dword_180034D10
0x1800015fb  test    eax, eax
0x1800015fd  jg      short loc_18000160C
0x1800015ff  xor     eax, eax
0x180001601  mov     rbx, [rsp+38h+arg_0]
0x180001606  add     rsp, 30h
0x18000160a  pop     rdi
0x18000160b  retn
0x18000160c  dec     eax
0x18000160e  mov     cs:dword_180034D10, eax
0x180001614  call    __scrt_acquire_startup_lock
0x180001619  mov     bl, al
0x18000161b  mov     [rsp+38h+var_18], al
0x18000161f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001626  jnz     short loc_18000165E
0x180001628  call    __scrt_dllmain_uninitialize_c
0x18000162d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001632  call    _RTC_Terminate
0x180001637  mov     cs:__scrt_current_native_startup_state, 0
0x180001641  mov     cl, bl
0x180001643  call    __scrt_release_startup_lock
0x180001648  xor     edx, edx
0x18000164a  mov     cl, dil
0x18000164d  call    __scrt_uninitialize_crt
0x180001652  movzx   ebx, al
0x180001655  call    __scrt_dllmain_uninitialize_critical
0x18000165a  mov     eax, ebx
0x18000165c  jmp     short loc_180001601
0x18000165e  mov     ecx, 7
0x180001663  call    __scrt_fastfail
0x180025339  push    rbp
0x18002533b  sub     rsp, 20h
0x18002533f  mov     rbp, rdx
0x180025342  mov     cl, [rbp+20h]
0x180025345  call    __scrt_release_startup_lock
0x18002534a  nop
0x18002534b  add     rsp, 20h
0x18002534f  pop     rbp
0x180025350  retn
0x180025352  push    rbp
0x180025354  sub     rsp, 20h
0x180025358  mov     rbp, rdx
0x18002535b  add     rsp, 20h
0x18002535f  pop     rbp
0x180025360  jmp     __scrt_dllmain_uninitialize_critical
```
