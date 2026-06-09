# dllmain_crt_process_detach

- ea: `0x180004e08`
- end: `0x180004e8b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180004cb0`

## callees

- `0x180004e08`
- `0x180005044`
- `0x18000516c`
- `0x1800051a4`
- `0x180005334`
- `0x180005360`
- `0x180005600`
- `0x180005648`
- `0x180005698`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180012BF0 <= 0 )
    return 0;
  --dword_180012BF0;
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
0x180004e08  mov     [rsp+arg_0], rbx
0x180004e0d  push    rdi
0x180004e0e  sub     rsp, 30h
0x180004e12  mov     dil, cl
0x180004e15  mov     eax, cs:dword_180012BF0
0x180004e1b  test    eax, eax
0x180004e1d  jg      short loc_180004E2C
0x180004e1f  xor     eax, eax
0x180004e21  mov     rbx, [rsp+38h+arg_0]
0x180004e26  add     rsp, 30h
0x180004e2a  pop     rdi
0x180004e2b  retn
0x180004e2c  dec     eax
0x180004e2e  mov     cs:dword_180012BF0, eax
0x180004e34  call    __scrt_acquire_startup_lock
0x180004e39  mov     bl, al
0x180004e3b  mov     [rsp+38h+var_18], al
0x180004e3f  cmp     cs:__scrt_current_native_startup_state, 2
0x180004e46  jnz     short loc_180004E7E
0x180004e48  call    __scrt_dllmain_uninitialize_c
0x180004e4d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180004e52  call    _RTC_Terminate
0x180004e57  mov     cs:__scrt_current_native_startup_state, 0
0x180004e61  mov     cl, bl
0x180004e63  call    __scrt_release_startup_lock
0x180004e68  xor     edx, edx
0x180004e6a  mov     cl, dil
0x180004e6d  call    __scrt_uninitialize_crt
0x180004e72  movzx   ebx, al
0x180004e75  call    __scrt_dllmain_uninitialize_critical
0x180004e7a  mov     eax, ebx
0x180004e7c  jmp     short loc_180004E21
0x180004e7e  mov     ecx, 7
0x180004e83  call    __scrt_fastfail
0x18000aa71  push    rbp
0x18000aa73  sub     rsp, 20h
0x18000aa77  mov     rbp, rdx
0x18000aa7a  mov     cl, [rbp+20h]
0x18000aa7d  call    __scrt_release_startup_lock
0x18000aa82  nop
0x18000aa83  add     rsp, 20h
0x18000aa87  pop     rbp
0x18000aa88  retn
0x18000aa8a  push    rbp
0x18000aa8c  sub     rsp, 20h
0x18000aa90  mov     rbp, rdx
0x18000aa93  add     rsp, 20h
0x18000aa97  pop     rbp
0x18000aa98  jmp     __scrt_dllmain_uninitialize_critical
```
