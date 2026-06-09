# dllmain_crt_process_detach

- ea: `0x180009058`
- end: `0x1800090db`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180008f00`

## callees

- `0x180009058`
- `0x180009380`
- `0x1800093b8`
- `0x1800094e0`
- `0x180009518`
- `0x1800096a8`
- `0x1800096d4`
- `0x180009714`
- `0x180009764`

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

  if ( dword_18001A130 <= 0 )
    return 0;
  --dword_18001A130;
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
0x180009058  mov     [rsp+arg_0], rbx
0x18000905d  push    rdi
0x18000905e  sub     rsp, 30h
0x180009062  mov     dil, cl
0x180009065  mov     eax, cs:dword_18001A130
0x18000906b  test    eax, eax
0x18000906d  jg      short loc_18000907C
0x18000906f  xor     eax, eax
0x180009071  mov     rbx, [rsp+38h+arg_0]
0x180009076  add     rsp, 30h
0x18000907a  pop     rdi
0x18000907b  retn
0x18000907c  dec     eax
0x18000907e  mov     cs:dword_18001A130, eax
0x180009084  call    __scrt_acquire_startup_lock
0x180009089  mov     bl, al
0x18000908b  mov     [rsp+38h+var_18], al
0x18000908f  cmp     cs:__scrt_current_native_startup_state, 2
0x180009096  jnz     short loc_1800090CE
0x180009098  call    __scrt_dllmain_uninitialize_c
0x18000909d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800090a2  call    _RTC_Terminate
0x1800090a7  mov     cs:__scrt_current_native_startup_state, 0
0x1800090b1  mov     cl, bl
0x1800090b3  call    __scrt_release_startup_lock
0x1800090b8  xor     edx, edx
0x1800090ba  mov     cl, dil
0x1800090bd  call    __scrt_uninitialize_crt
0x1800090c2  movzx   ebx, al
0x1800090c5  call    __scrt_dllmain_uninitialize_critical
0x1800090ca  mov     eax, ebx
0x1800090cc  jmp     short loc_180009071
0x1800090ce  mov     ecx, 7
0x1800090d3  call    __scrt_fastfail
0x180012749  push    rbp
0x18001274b  sub     rsp, 20h
0x18001274f  mov     rbp, rdx
0x180012752  mov     cl, [rbp+20h]
0x180012755  call    __scrt_release_startup_lock
0x18001275a  nop
0x18001275b  add     rsp, 20h
0x18001275f  pop     rbp
0x180012760  retn
0x180012762  push    rbp
0x180012764  sub     rsp, 20h
0x180012768  mov     rbp, rdx
0x18001276b  add     rsp, 20h
0x18001276f  pop     rbp
0x180012770  jmp     __scrt_dllmain_uninitialize_critical
```
