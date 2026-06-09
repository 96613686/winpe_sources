# dllmain_crt_process_detach

- ea: `0x180024008`
- end: `0x18002408b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180023eb0`

## callees

- `0x180024008`
- `0x180024244`
- `0x18002436c`
- `0x1800243a4`
- `0x180024534`
- `0x180024560`
- `0x1800246cc`
- `0x180024714`
- `0x180024764`

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

  if ( dword_18009CC10 <= 0 )
    return 0;
  --dword_18009CC10;
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
0x180024008  mov     [rsp+arg_0], rbx
0x18002400d  push    rdi
0x18002400e  sub     rsp, 30h
0x180024012  mov     dil, cl
0x180024015  mov     eax, cs:dword_18009CC10
0x18002401b  test    eax, eax
0x18002401d  jg      short loc_18002402C
0x18002401f  xor     eax, eax
0x180024021  mov     rbx, [rsp+38h+arg_0]
0x180024026  add     rsp, 30h
0x18002402a  pop     rdi
0x18002402b  retn
0x18002402c  dec     eax
0x18002402e  mov     cs:dword_18009CC10, eax
0x180024034  call    __scrt_acquire_startup_lock
0x180024039  mov     bl, al
0x18002403b  mov     [rsp+38h+var_18], al
0x18002403f  cmp     cs:__scrt_current_native_startup_state, 2
0x180024046  jnz     short loc_18002407E
0x180024048  call    __scrt_dllmain_uninitialize_c
0x18002404d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180024052  call    _RTC_Terminate
0x180024057  mov     cs:__scrt_current_native_startup_state, 0
0x180024061  mov     cl, bl
0x180024063  call    __scrt_release_startup_lock
0x180024068  xor     edx, edx
0x18002406a  mov     cl, dil
0x18002406d  call    __scrt_uninitialize_crt
0x180024072  movzx   ebx, al
0x180024075  call    __scrt_dllmain_uninitialize_critical
0x18002407a  mov     eax, ebx
0x18002407c  jmp     short loc_180024021
0x18002407e  mov     ecx, 7
0x180024083  call    __scrt_fastfail
0x18006f0b7  push    rbp
0x18006f0b9  sub     rsp, 20h
0x18006f0bd  mov     rbp, rdx
0x18006f0c0  mov     cl, [rbp+20h]
0x18006f0c3  call    __scrt_release_startup_lock
0x18006f0c8  nop
0x18006f0c9  add     rsp, 20h
0x18006f0cd  pop     rbp
0x18006f0ce  retn
0x18006f0d0  push    rbp
0x18006f0d2  sub     rsp, 20h
0x18006f0d6  mov     rbp, rdx
0x18006f0d9  add     rsp, 20h
0x18006f0dd  pop     rbp
0x18006f0de  jmp     __scrt_dllmain_uninitialize_critical
```
