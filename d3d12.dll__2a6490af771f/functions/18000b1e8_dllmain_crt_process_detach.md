# dllmain_crt_process_detach

- ea: `0x18000b1e8`
- end: `0x18000b26b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000b090`

## callees

- `0x18000b1e8`
- `0x18000b434`
- `0x18000b55c`
- `0x18000b594`
- `0x18000b724`
- `0x18000b750`
- `0x18000b93c`
- `0x18000b984`
- `0x18000b9d4`

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

  if ( dword_18001C510 <= 0 )
    return 0;
  --dword_18001C510;
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
0x18000b1e8  mov     [rsp+arg_0], rbx
0x18000b1ed  push    rdi
0x18000b1ee  sub     rsp, 30h
0x18000b1f2  mov     dil, cl
0x18000b1f5  mov     eax, cs:dword_18001C510
0x18000b1fb  test    eax, eax
0x18000b1fd  jg      short loc_18000B20C
0x18000b1ff  xor     eax, eax
0x18000b201  mov     rbx, [rsp+38h+arg_0]
0x18000b206  add     rsp, 30h
0x18000b20a  pop     rdi
0x18000b20b  retn
0x18000b20c  dec     eax
0x18000b20e  mov     cs:dword_18001C510, eax
0x18000b214  call    __scrt_acquire_startup_lock
0x18000b219  mov     bl, al
0x18000b21b  mov     [rsp+38h+var_18], al
0x18000b21f  cmp     cs:__scrt_current_native_startup_state, 2
0x18000b226  jnz     short loc_18000B25E
0x18000b228  call    __scrt_dllmain_uninitialize_c
0x18000b22d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000b232  call    _RTC_Terminate
0x18000b237  mov     cs:__scrt_current_native_startup_state, 0
0x18000b241  mov     cl, bl
0x18000b243  call    __scrt_release_startup_lock
0x18000b248  xor     edx, edx
0x18000b24a  mov     cl, dil
0x18000b24d  call    __scrt_uninitialize_crt
0x18000b252  movzx   ebx, al
0x18000b255  call    __scrt_dllmain_uninitialize_critical
0x18000b25a  mov     eax, ebx
0x18000b25c  jmp     short loc_18000B201
0x18000b25e  mov     ecx, 7
0x18000b263  call    __scrt_fastfail
0x180013e4b  push    rbp
0x180013e4d  sub     rsp, 20h
0x180013e51  mov     rbp, rdx
0x180013e54  mov     cl, [rbp+20h]
0x180013e57  call    __scrt_release_startup_lock
0x180013e5c  nop
0x180013e5d  add     rsp, 20h
0x180013e61  pop     rbp
0x180013e62  retn
0x180013e64  push    rbp
0x180013e66  sub     rsp, 20h
0x180013e6a  mov     rbp, rdx
0x180013e6d  add     rsp, 20h
0x180013e71  pop     rbp
0x180013e72  jmp     __scrt_dllmain_uninitialize_critical
```
