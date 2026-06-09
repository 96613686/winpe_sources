# dllmain_crt_process_detach

- ea: `0x180002f98`
- end: `0x18000301b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002e40`

## callees

- `0x180002f98`
- `0x1800032dc`
- `0x180003404`
- `0x18000343c`
- `0x1800035cc`
- `0x1800035f8`
- `0x180003aec`
- `0x180003b34`
- `0x180003b84`

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

  if ( dword_180032990 <= 0 )
    return 0;
  --dword_180032990;
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
0x180002f98  mov     [rsp+arg_0], rbx
0x180002f9d  push    rdi
0x180002f9e  sub     rsp, 30h
0x180002fa2  mov     dil, cl
0x180002fa5  mov     eax, cs:dword_180032990
0x180002fab  test    eax, eax
0x180002fad  jg      short loc_180002FBC
0x180002faf  xor     eax, eax
0x180002fb1  mov     rbx, [rsp+38h+arg_0]
0x180002fb6  add     rsp, 30h
0x180002fba  pop     rdi
0x180002fbb  retn
0x180002fbc  dec     eax
0x180002fbe  mov     cs:dword_180032990, eax
0x180002fc4  call    __scrt_acquire_startup_lock
0x180002fc9  mov     bl, al
0x180002fcb  mov     [rsp+38h+var_18], al
0x180002fcf  cmp     cs:__scrt_current_native_startup_state, 2
0x180002fd6  jnz     short loc_18000300E
0x180002fd8  call    __scrt_dllmain_uninitialize_c
0x180002fdd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002fe2  call    _RTC_Terminate
0x180002fe7  mov     cs:__scrt_current_native_startup_state, 0
0x180002ff1  mov     cl, bl
0x180002ff3  call    __scrt_release_startup_lock
0x180002ff8  xor     edx, edx
0x180002ffa  mov     cl, dil
0x180002ffd  call    __scrt_uninitialize_crt
0x180003002  movzx   ebx, al
0x180003005  call    __scrt_dllmain_uninitialize_critical
0x18000300a  mov     eax, ebx
0x18000300c  jmp     short loc_180002FB1
0x18000300e  mov     ecx, 7
0x180003013  call    __scrt_fastfail
0x180022a79  push    rbp
0x180022a7b  sub     rsp, 20h
0x180022a7f  mov     rbp, rdx
0x180022a82  mov     cl, [rbp+20h]
0x180022a85  call    __scrt_release_startup_lock
0x180022a8a  nop
0x180022a8b  add     rsp, 20h
0x180022a8f  pop     rbp
0x180022a90  retn
0x180022a92  push    rbp
0x180022a94  sub     rsp, 20h
0x180022a98  mov     rbp, rdx
0x180022a9b  add     rsp, 20h
0x180022a9f  pop     rbp
0x180022aa0  jmp     __scrt_dllmain_uninitialize_critical
```
