# dllmain_crt_process_detach

- ea: `0x180001348`
- end: `0x1800013cb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800011f0`

## callees

- `0x180001348`
- `0x180001654`
- `0x18000168c`
- `0x1800017b4`
- `0x1800017ec`
- `0x18000197c`
- `0x1800019a8`
- `0x180001a48`
- `0x180001a98`

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

  if ( dword_18001D1D0 <= 0 )
    return 0;
  --dword_18001D1D0;
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
0x180001348  mov     [rsp+arg_0], rbx
0x18000134d  push    rdi
0x18000134e  sub     rsp, 30h
0x180001352  mov     dil, cl
0x180001355  mov     eax, cs:dword_18001D1D0
0x18000135b  test    eax, eax
0x18000135d  jg      short loc_18000136C
0x18000135f  xor     eax, eax
0x180001361  mov     rbx, [rsp+38h+arg_0]
0x180001366  add     rsp, 30h
0x18000136a  pop     rdi
0x18000136b  retn
0x18000136c  dec     eax
0x18000136e  mov     cs:dword_18001D1D0, eax
0x180001374  call    __scrt_acquire_startup_lock
0x180001379  mov     bl, al
0x18000137b  mov     [rsp+38h+var_18], al
0x18000137f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001386  jnz     short loc_1800013BE
0x180001388  call    __scrt_dllmain_uninitialize_c
0x18000138d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001392  call    _RTC_Terminate
0x180001397  mov     cs:__scrt_current_native_startup_state, 0
0x1800013a1  mov     cl, bl
0x1800013a3  call    __scrt_release_startup_lock
0x1800013a8  xor     edx, edx
0x1800013aa  mov     cl, dil
0x1800013ad  call    __scrt_uninitialize_crt
0x1800013b2  movzx   ebx, al
0x1800013b5  call    __scrt_dllmain_uninitialize_critical
0x1800013ba  mov     eax, ebx
0x1800013bc  jmp     short loc_180001361
0x1800013be  mov     ecx, 7
0x1800013c3  call    __scrt_fastfail
0x1800158d9  push    rbp
0x1800158db  sub     rsp, 20h
0x1800158df  mov     rbp, rdx
0x1800158e2  mov     cl, [rbp+20h]
0x1800158e5  call    __scrt_release_startup_lock
0x1800158ea  nop
0x1800158eb  add     rsp, 20h
0x1800158ef  pop     rbp
0x1800158f0  retn
0x1800158f2  push    rbp
0x1800158f4  sub     rsp, 20h
0x1800158f8  mov     rbp, rdx
0x1800158fb  add     rsp, 20h
0x1800158ff  pop     rbp
0x180015900  jmp     __scrt_dllmain_uninitialize_critical
```
