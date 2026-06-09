# dllmain_crt_process_detach

- ea: `0x18000bc28`
- end: `0x18000bcab`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000bad0`

## callees

- `0x18000bc28`
- `0x18000be64`
- `0x18000bf8c`
- `0x18000bfc4`
- `0x18000c154`
- `0x18000c180`
- `0x18000c5ec`
- `0x18000c634`
- `0x18000c684`

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

  if ( dword_180031370 <= 0 )
    return 0;
  --dword_180031370;
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
0x18000bc28  mov     [rsp+arg_0], rbx
0x18000bc2d  push    rdi
0x18000bc2e  sub     rsp, 30h
0x18000bc32  mov     dil, cl
0x18000bc35  mov     eax, cs:dword_180031370
0x18000bc3b  test    eax, eax
0x18000bc3d  jg      short loc_18000BC4C
0x18000bc3f  xor     eax, eax
0x18000bc41  mov     rbx, [rsp+38h+arg_0]
0x18000bc46  add     rsp, 30h
0x18000bc4a  pop     rdi
0x18000bc4b  retn
0x18000bc4c  dec     eax
0x18000bc4e  mov     cs:dword_180031370, eax
0x18000bc54  call    __scrt_acquire_startup_lock
0x18000bc59  mov     bl, al
0x18000bc5b  mov     [rsp+38h+var_18], al
0x18000bc5f  cmp     cs:__scrt_current_native_startup_state, 2
0x18000bc66  jnz     short loc_18000BC9E
0x18000bc68  call    __scrt_dllmain_uninitialize_c
0x18000bc6d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000bc72  call    _RTC_Terminate
0x18000bc77  mov     cs:__scrt_current_native_startup_state, 0
0x18000bc81  mov     cl, bl
0x18000bc83  call    __scrt_release_startup_lock
0x18000bc88  xor     edx, edx
0x18000bc8a  mov     cl, dil
0x18000bc8d  call    __scrt_uninitialize_crt
0x18000bc92  movzx   ebx, al
0x18000bc95  call    __scrt_dllmain_uninitialize_critical
0x18000bc9a  mov     eax, ebx
0x18000bc9c  jmp     short loc_18000BC41
0x18000bc9e  mov     ecx, 7
0x18000bca3  call    __scrt_fastfail
0x18002169d  push    rbp
0x18002169f  sub     rsp, 20h
0x1800216a3  mov     rbp, rdx
0x1800216a6  mov     cl, [rbp+20h]
0x1800216a9  call    __scrt_release_startup_lock
0x1800216ae  nop
0x1800216af  add     rsp, 20h
0x1800216b3  pop     rbp
0x1800216b4  retn
0x1800216b6  push    rbp
0x1800216b8  sub     rsp, 20h
0x1800216bc  mov     rbp, rdx
0x1800216bf  add     rsp, 20h
0x1800216c3  pop     rbp
0x1800216c4  jmp     __scrt_dllmain_uninitialize_critical
```
