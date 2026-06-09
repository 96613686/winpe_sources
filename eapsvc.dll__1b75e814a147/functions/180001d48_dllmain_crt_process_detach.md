# dllmain_crt_process_detach

- ea: `0x180001d48`
- end: `0x180001dcb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001bf0`

## callees

- `0x180001d48`
- `0x180001f84`
- `0x1800020ac`
- `0x1800020e4`
- `0x180002274`
- `0x1800022a0`
- `0x180002380`
- `0x180002484`
- `0x1800024d4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180020810 <= 0 )
    return 0;
  --dword_180020810;
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
0x180001d48  mov     [rsp+arg_0], rbx
0x180001d4d  push    rdi
0x180001d4e  sub     rsp, 30h
0x180001d52  mov     dil, cl
0x180001d55  mov     eax, cs:dword_180020810
0x180001d5b  test    eax, eax
0x180001d5d  jg      short loc_180001D6C
0x180001d5f  xor     eax, eax
0x180001d61  mov     rbx, [rsp+38h+arg_0]
0x180001d66  add     rsp, 30h
0x180001d6a  pop     rdi
0x180001d6b  retn
0x180001d6c  dec     eax
0x180001d6e  mov     cs:dword_180020810, eax
0x180001d74  call    __scrt_acquire_startup_lock
0x180001d79  mov     bl, al
0x180001d7b  mov     [rsp+38h+var_18], al
0x180001d7f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001d86  jnz     short loc_180001DBE
0x180001d88  call    __scrt_dllmain_uninitialize_c
0x180001d8d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001d92  call    _RTC_Terminate
0x180001d97  mov     cs:__scrt_current_native_startup_state, 0
0x180001da1  mov     cl, bl
0x180001da3  call    __scrt_release_startup_lock
0x180001da8  xor     edx, edx
0x180001daa  mov     cl, dil
0x180001dad  call    __scrt_uninitialize_crt
0x180001db2  movzx   ebx, al
0x180001db5  call    __scrt_dllmain_uninitialize_critical
0x180001dba  mov     eax, ebx
0x180001dbc  jmp     short loc_180001D61
0x180001dbe  mov     ecx, 7
0x180001dc3  call    __scrt_fastfail
0x180014f29  push    rbp
0x180014f2b  sub     rsp, 20h
0x180014f2f  mov     rbp, rdx
0x180014f32  mov     cl, [rbp+20h]
0x180014f35  call    __scrt_release_startup_lock
0x180014f3a  nop
0x180014f3b  add     rsp, 20h
0x180014f3f  pop     rbp
0x180014f40  retn
0x180014f42  push    rbp
0x180014f44  sub     rsp, 20h
0x180014f48  mov     rbp, rdx
0x180014f4b  add     rsp, 20h
0x180014f4f  pop     rbp
0x180014f50  jmp     __scrt_dllmain_uninitialize_critical
```
