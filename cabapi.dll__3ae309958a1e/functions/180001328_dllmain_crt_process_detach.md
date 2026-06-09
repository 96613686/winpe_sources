# dllmain_crt_process_detach

- ea: `0x180001328`
- end: `0x1800013ab`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800011d0`

## callees

- `0x180001328`
- `0x1800015b4`
- `0x1800016dc`
- `0x180001714`
- `0x1800018a4`
- `0x1800018d0`
- `0x180001a98`
- `0x180001ae0`
- `0x180001b30`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001F270 <= 0 )
    return 0;
  --dword_18001F270;
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
0x180001328  mov     [rsp+arg_0], rbx
0x18000132d  push    rdi
0x18000132e  sub     rsp, 30h
0x180001332  mov     dil, cl
0x180001335  mov     eax, cs:dword_18001F270
0x18000133b  test    eax, eax
0x18000133d  jg      short loc_18000134C
0x18000133f  xor     eax, eax
0x180001341  mov     rbx, [rsp+38h+arg_0]
0x180001346  add     rsp, 30h
0x18000134a  pop     rdi
0x18000134b  retn
0x18000134c  dec     eax
0x18000134e  mov     cs:dword_18001F270, eax
0x180001354  call    __scrt_acquire_startup_lock
0x180001359  mov     bl, al
0x18000135b  mov     [rsp+38h+var_18], al
0x18000135f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001366  jnz     short loc_18000139E
0x180001368  call    __scrt_dllmain_uninitialize_c
0x18000136d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001372  call    _RTC_Terminate
0x180001377  mov     cs:__scrt_current_native_startup_state, 0
0x180001381  mov     cl, bl
0x180001383  call    __scrt_release_startup_lock
0x180001388  xor     edx, edx
0x18000138a  mov     cl, dil
0x18000138d  call    __scrt_uninitialize_crt
0x180001392  movzx   ebx, al
0x180001395  call    __scrt_dllmain_uninitialize_critical
0x18000139a  mov     eax, ebx
0x18000139c  jmp     short loc_180001341
0x18000139e  mov     ecx, 7
0x1800013a3  call    __scrt_fastfail
0x180013e99  push    rbp
0x180013e9b  sub     rsp, 20h
0x180013e9f  mov     rbp, rdx
0x180013ea2  mov     cl, [rbp+20h]
0x180013ea5  call    __scrt_release_startup_lock
0x180013eaa  nop
0x180013eab  add     rsp, 20h
0x180013eaf  pop     rbp
0x180013eb0  retn
0x180013eb2  push    rbp
0x180013eb4  sub     rsp, 20h
0x180013eb8  mov     rbp, rdx
0x180013ebb  add     rsp, 20h
0x180013ebf  pop     rbp
0x180013ec0  jmp     __scrt_dllmain_uninitialize_critical
```
