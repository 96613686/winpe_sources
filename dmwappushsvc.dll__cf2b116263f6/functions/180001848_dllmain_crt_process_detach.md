# dllmain_crt_process_detach

- ea: `0x180001848`
- end: `0x1800018cb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800016f0`

## callees

- `0x180001848`
- `0x180001c60`
- `0x180001c98`
- `0x180001dc0`
- `0x180001df8`
- `0x180001f88`
- `0x180001fb4`
- `0x180002054`
- `0x1800020a4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001C650 <= 0 )
    return 0;
  --dword_18001C650;
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
0x180001848  mov     [rsp+arg_0], rbx
0x18000184d  push    rdi
0x18000184e  sub     rsp, 30h
0x180001852  mov     dil, cl
0x180001855  mov     eax, cs:dword_18001C650
0x18000185b  test    eax, eax
0x18000185d  jg      short loc_18000186C
0x18000185f  xor     eax, eax
0x180001861  mov     rbx, [rsp+38h+arg_0]
0x180001866  add     rsp, 30h
0x18000186a  pop     rdi
0x18000186b  retn
0x18000186c  dec     eax
0x18000186e  mov     cs:dword_18001C650, eax
0x180001874  call    __scrt_acquire_startup_lock
0x180001879  mov     bl, al
0x18000187b  mov     [rsp+38h+var_18], al
0x18000187f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001886  jnz     short loc_1800018BE
0x180001888  call    __scrt_dllmain_uninitialize_c
0x18000188d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001892  call    _RTC_Terminate
0x180001897  mov     cs:__scrt_current_native_startup_state, 0
0x1800018a1  mov     cl, bl
0x1800018a3  call    __scrt_release_startup_lock
0x1800018a8  xor     edx, edx
0x1800018aa  mov     cl, dil
0x1800018ad  call    __scrt_uninitialize_crt
0x1800018b2  movzx   ebx, al
0x1800018b5  call    __scrt_dllmain_uninitialize_critical
0x1800018ba  mov     eax, ebx
0x1800018bc  jmp     short loc_180001861
0x1800018be  mov     ecx, 7
0x1800018c3  call    __scrt_fastfail
0x180011799  push    rbp
0x18001179b  sub     rsp, 20h
0x18001179f  mov     rbp, rdx
0x1800117a2  mov     cl, [rbp+20h]
0x1800117a5  call    __scrt_release_startup_lock
0x1800117aa  nop
0x1800117ab  add     rsp, 20h
0x1800117af  pop     rbp
0x1800117b0  retn
0x1800117b2  push    rbp
0x1800117b4  sub     rsp, 20h
0x1800117b8  mov     rbp, rdx
0x1800117bb  add     rsp, 20h
0x1800117bf  pop     rbp
0x1800117c0  jmp     __scrt_dllmain_uninitialize_critical
```
