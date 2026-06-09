# dllmain_crt_process_detach

- ea: `0x180001598`
- end: `0x18000161b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001440`

## callees

- `0x180001598`
- `0x1800017d4`
- `0x1800018fc`
- `0x180001934`
- `0x180001ac4`
- `0x180001af0`
- `0x180001c8c`
- `0x180001cd4`
- `0x180001d24`

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

  if ( dword_1800AD5D0 <= 0 )
    return 0;
  --dword_1800AD5D0;
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
0x180001598  mov     [rsp+arg_0], rbx
0x18000159d  push    rdi
0x18000159e  sub     rsp, 30h
0x1800015a2  mov     dil, cl
0x1800015a5  mov     eax, cs:dword_1800AD5D0
0x1800015ab  test    eax, eax
0x1800015ad  jg      short loc_1800015BC
0x1800015af  xor     eax, eax
0x1800015b1  mov     rbx, [rsp+38h+arg_0]
0x1800015b6  add     rsp, 30h
0x1800015ba  pop     rdi
0x1800015bb  retn
0x1800015bc  dec     eax
0x1800015be  mov     cs:dword_1800AD5D0, eax
0x1800015c4  call    __scrt_acquire_startup_lock
0x1800015c9  mov     bl, al
0x1800015cb  mov     [rsp+38h+var_18], al
0x1800015cf  cmp     cs:__scrt_current_native_startup_state, 2
0x1800015d6  jnz     short loc_18000160E
0x1800015d8  call    __scrt_dllmain_uninitialize_c
0x1800015dd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800015e2  call    _RTC_Terminate
0x1800015e7  mov     cs:__scrt_current_native_startup_state, 0
0x1800015f1  mov     cl, bl
0x1800015f3  call    __scrt_release_startup_lock
0x1800015f8  xor     edx, edx
0x1800015fa  mov     cl, dil
0x1800015fd  call    __scrt_uninitialize_crt
0x180001602  movzx   ebx, al
0x180001605  call    __scrt_dllmain_uninitialize_critical
0x18000160a  mov     eax, ebx
0x18000160c  jmp     short loc_1800015B1
0x18000160e  mov     ecx, 7
0x180001613  call    __scrt_fastfail
0x18008879d  push    rbp
0x18008879f  sub     rsp, 20h
0x1800887a3  mov     rbp, rdx
0x1800887a6  mov     cl, [rbp+20h]
0x1800887a9  call    __scrt_release_startup_lock
0x1800887ae  nop
0x1800887af  add     rsp, 20h
0x1800887b3  pop     rbp
0x1800887b4  retn
0x1800887b6  push    rbp
0x1800887b8  sub     rsp, 20h
0x1800887bc  mov     rbp, rdx
0x1800887bf  add     rsp, 20h
0x1800887c3  pop     rbp
0x1800887c4  jmp     __scrt_dllmain_uninitialize_critical
```
