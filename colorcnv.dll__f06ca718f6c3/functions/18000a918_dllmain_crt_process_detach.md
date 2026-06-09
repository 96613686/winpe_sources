# dllmain_crt_process_detach

- ea: `0x18000a918`
- end: `0x18000a99b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000a7c0`

## callees

- `0x18000a918`
- `0x18000ab54`
- `0x18000ac7c`
- `0x18000acb4`
- `0x18000ae44`
- `0x18000ae70`
- `0x18000afd0`
- `0x18000b018`
- `0x18000b068`

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

  if ( dword_1800338D0 <= 0 )
    return 0;
  --dword_1800338D0;
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
0x18000a918  mov     [rsp+arg_0], rbx
0x18000a91d  push    rdi
0x18000a91e  sub     rsp, 30h
0x18000a922  mov     dil, cl
0x18000a925  mov     eax, cs:dword_1800338D0
0x18000a92b  test    eax, eax
0x18000a92d  jg      short loc_18000A93C
0x18000a92f  xor     eax, eax
0x18000a931  mov     rbx, [rsp+38h+arg_0]
0x18000a936  add     rsp, 30h
0x18000a93a  pop     rdi
0x18000a93b  retn
0x18000a93c  dec     eax
0x18000a93e  mov     cs:dword_1800338D0, eax
0x18000a944  call    __scrt_acquire_startup_lock
0x18000a949  mov     bl, al
0x18000a94b  mov     [rsp+38h+var_18], al
0x18000a94f  cmp     cs:__scrt_current_native_startup_state, 2
0x18000a956  jnz     short loc_18000A98E
0x18000a958  call    __scrt_dllmain_uninitialize_c
0x18000a95d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000a962  call    _RTC_Terminate
0x18000a967  mov     cs:__scrt_current_native_startup_state, 0
0x18000a971  mov     cl, bl
0x18000a973  call    __scrt_release_startup_lock
0x18000a978  xor     edx, edx
0x18000a97a  mov     cl, dil
0x18000a97d  call    __scrt_uninitialize_crt
0x18000a982  movzx   ebx, al
0x18000a985  call    __scrt_dllmain_uninitialize_critical
0x18000a98a  mov     eax, ebx
0x18000a98c  jmp     short loc_18000A931
0x18000a98e  mov     ecx, 7
0x18000a993  call    __scrt_fastfail
0x18002a059  push    rbp
0x18002a05b  sub     rsp, 20h
0x18002a05f  mov     rbp, rdx
0x18002a062  mov     cl, [rbp+20h]
0x18002a065  call    __scrt_release_startup_lock
0x18002a06a  nop
0x18002a06b  add     rsp, 20h
0x18002a06f  pop     rbp
0x18002a070  retn
0x18002a072  push    rbp
0x18002a074  sub     rsp, 20h
0x18002a078  mov     rbp, rdx
0x18002a07b  add     rsp, 20h
0x18002a07f  pop     rbp
0x18002a080  jmp     __scrt_dllmain_uninitialize_critical
```
