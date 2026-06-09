# dllmain_crt_process_detach

- ea: `0x180014ba8`
- end: `0x180014c2b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180014a50`

## callees

- `0x180014ba8`
- `0x180014ee0`
- `0x180014f18`
- `0x180015040`
- `0x180015078`
- `0x180015208`
- `0x180015234`
- `0x180015274`
- `0x1800152c4`

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

  if ( dword_180021090 <= 0 )
    return 0;
  --dword_180021090;
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
0x180014ba8  mov     [rsp+arg_0], rbx
0x180014bad  push    rdi
0x180014bae  sub     rsp, 30h
0x180014bb2  mov     dil, cl
0x180014bb5  mov     eax, cs:dword_180021090
0x180014bbb  test    eax, eax
0x180014bbd  jg      short loc_180014BCC
0x180014bbf  xor     eax, eax
0x180014bc1  mov     rbx, [rsp+38h+arg_0]
0x180014bc6  add     rsp, 30h
0x180014bca  pop     rdi
0x180014bcb  retn
0x180014bcc  dec     eax
0x180014bce  mov     cs:dword_180021090, eax
0x180014bd4  call    __scrt_acquire_startup_lock
0x180014bd9  mov     bl, al
0x180014bdb  mov     [rsp+38h+var_18], al
0x180014bdf  cmp     cs:__scrt_current_native_startup_state, 2
0x180014be6  jnz     short loc_180014C1E
0x180014be8  call    __scrt_dllmain_uninitialize_c
0x180014bed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180014bf2  call    _RTC_Terminate
0x180014bf7  mov     cs:__scrt_current_native_startup_state, 0
0x180014c01  mov     cl, bl
0x180014c03  call    __scrt_release_startup_lock
0x180014c08  xor     edx, edx
0x180014c0a  mov     cl, dil
0x180014c0d  call    __scrt_uninitialize_crt
0x180014c12  movzx   ebx, al
0x180014c15  call    __scrt_dllmain_uninitialize_critical
0x180014c1a  mov     eax, ebx
0x180014c1c  jmp     short loc_180014BC1
0x180014c1e  mov     ecx, 7
0x180014c23  call    __scrt_fastfail
0x18001b6c9  push    rbp
0x18001b6cb  sub     rsp, 20h
0x18001b6cf  mov     rbp, rdx
0x18001b6d2  mov     cl, [rbp+20h]
0x18001b6d5  call    __scrt_release_startup_lock
0x18001b6da  nop
0x18001b6db  add     rsp, 20h
0x18001b6df  pop     rbp
0x18001b6e0  retn
0x18001b6e2  push    rbp
0x18001b6e4  sub     rsp, 20h
0x18001b6e8  mov     rbp, rdx
0x18001b6eb  add     rsp, 20h
0x18001b6ef  pop     rbp
0x18001b6f0  jmp     __scrt_dllmain_uninitialize_critical
```
