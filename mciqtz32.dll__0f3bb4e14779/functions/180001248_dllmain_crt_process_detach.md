# dllmain_crt_process_detach

- ea: `0x180001248`
- end: `0x1800012cb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800010f0`

## callees

- `0x180001248`
- `0x180001580`
- `0x1800015b8`
- `0x1800016e0`
- `0x180001718`
- `0x1800018a8`
- `0x1800018d4`
- `0x180001914`
- `0x180001964`

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

  if ( dword_18000A090 <= 0 )
    return 0;
  --dword_18000A090;
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
0x180001248  mov     [rsp+arg_0], rbx
0x18000124d  push    rdi
0x18000124e  sub     rsp, 30h
0x180001252  mov     dil, cl
0x180001255  mov     eax, cs:dword_18000A090
0x18000125b  test    eax, eax
0x18000125d  jg      short loc_18000126C
0x18000125f  xor     eax, eax
0x180001261  mov     rbx, [rsp+38h+arg_0]
0x180001266  add     rsp, 30h
0x18000126a  pop     rdi
0x18000126b  retn
0x18000126c  dec     eax
0x18000126e  mov     cs:dword_18000A090, eax
0x180001274  call    __scrt_acquire_startup_lock
0x180001279  mov     bl, al
0x18000127b  mov     [rsp+38h+var_18], al
0x18000127f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001286  jnz     short loc_1800012BE
0x180001288  call    __scrt_dllmain_uninitialize_c
0x18000128d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001292  call    _RTC_Terminate
0x180001297  mov     cs:__scrt_current_native_startup_state, 0
0x1800012a1  mov     cl, bl
0x1800012a3  call    __scrt_release_startup_lock
0x1800012a8  xor     edx, edx
0x1800012aa  mov     cl, dil
0x1800012ad  call    __scrt_uninitialize_crt
0x1800012b2  movzx   ebx, al
0x1800012b5  call    __scrt_dllmain_uninitialize_critical
0x1800012ba  mov     eax, ebx
0x1800012bc  jmp     short loc_180001261
0x1800012be  mov     ecx, 7
0x1800012c3  call    __scrt_fastfail
0x1800065f9  push    rbp
0x1800065fb  sub     rsp, 20h
0x1800065ff  mov     rbp, rdx
0x180006602  mov     cl, [rbp+20h]
0x180006605  call    __scrt_release_startup_lock
0x18000660a  nop
0x18000660b  add     rsp, 20h
0x18000660f  pop     rbp
0x180006610  retn
0x180006612  push    rbp
0x180006614  sub     rsp, 20h
0x180006618  mov     rbp, rdx
0x18000661b  add     rsp, 20h
0x18000661f  pop     rbp
0x180006620  jmp     __scrt_dllmain_uninitialize_critical
```
