# dllmain_crt_process_detach

- ea: `0x1800012e8`
- end: `0x18000136b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001190`

## callees

- `0x1800012e8`
- `0x180001524`
- `0x18000164c`
- `0x180001684`
- `0x180001814`
- `0x180001840`
- `0x180001a70`
- `0x180001ac0`
- `0x180001b10`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180014248 <= 0 )
    return 0;
  --dword_180014248;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
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
0x1800012e8  mov     [rsp+arg_0], rbx
0x1800012ed  push    rdi
0x1800012ee  sub     rsp, 30h
0x1800012f2  mov     dil, cl
0x1800012f5  mov     eax, cs:dword_180014248
0x1800012fb  test    eax, eax
0x1800012fd  jg      short loc_18000130C
0x1800012ff  xor     eax, eax
0x180001301  mov     rbx, [rsp+38h+arg_0]
0x180001306  add     rsp, 30h
0x18000130a  pop     rdi
0x18000130b  retn
0x18000130c  dec     eax
0x18000130e  mov     cs:dword_180014248, eax
0x180001314  call    __scrt_acquire_startup_lock
0x180001319  mov     bl, al
0x18000131b  mov     [rsp+38h+var_18], al
0x18000131f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001326  jnz     short loc_18000135E
0x180001328  call    __scrt_dllmain_uninitialize_c
0x18000132d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001332  call    _RTC_Terminate
0x180001337  mov     cs:__scrt_current_native_startup_state, 0
0x180001341  mov     cl, bl
0x180001343  call    __scrt_release_startup_lock
0x180001348  xor     edx, edx
0x18000134a  mov     cl, dil
0x18000134d  call    __scrt_uninitialize_crt
0x180001352  movzx   ebx, al
0x180001355  call    __scrt_dllmain_uninitialize_critical
0x18000135a  mov     eax, ebx
0x18000135c  jmp     short loc_180001301
0x18000135e  mov     ecx, 7
0x180001363  call    __scrt_fastfail
0x18000bc5d  push    rbp
0x18000bc5f  sub     rsp, 20h
0x18000bc63  mov     rbp, rdx
0x18000bc66  mov     cl, [rbp+20h]
0x18000bc69  call    __scrt_release_startup_lock
0x18000bc6e  nop
0x18000bc6f  add     rsp, 20h
0x18000bc73  pop     rbp
0x18000bc74  retn
0x18000bc76  push    rbp
0x18000bc78  sub     rsp, 20h
0x18000bc7c  mov     rbp, rdx
0x18000bc7f  add     rsp, 20h
0x18000bc83  pop     rbp
0x18000bc84  jmp     __scrt_dllmain_uninitialize_critical
```
