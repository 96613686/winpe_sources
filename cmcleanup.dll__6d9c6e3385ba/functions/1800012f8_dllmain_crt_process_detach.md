# dllmain_crt_process_detach

- ea: `0x1800012f8`
- end: `0x18000137b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800011a0`

## callees

- `0x1800012f8`
- `0x18000159c`
- `0x1800016c4`
- `0x1800016fc`
- `0x18000188c`
- `0x1800018b8`
- `0x180001a5c`
- `0x180001aa4`
- `0x180001af4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  unsigned int v5; // ebx

  if ( dword_18000E1F0 <= 0 )
    return 0;
  --dword_18000E1F0;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  _scrt_release_startup_lock(v3);
  LOBYTE(v4) = a1;
  v5 = (unsigned __int8)_scrt_uninitialize_crt(v4, 0);
  _scrt_dllmain_uninitialize_critical();
  return v5;
}

```

## disassembly

```asm
0x1800012f8  mov     [rsp+arg_0], rbx
0x1800012fd  push    rdi
0x1800012fe  sub     rsp, 30h
0x180001302  mov     dil, cl
0x180001305  mov     eax, cs:dword_18000E1F0
0x18000130b  test    eax, eax
0x18000130d  jg      short loc_18000131C
0x18000130f  xor     eax, eax
0x180001311  mov     rbx, [rsp+38h+arg_0]
0x180001316  add     rsp, 30h
0x18000131a  pop     rdi
0x18000131b  retn
0x18000131c  dec     eax
0x18000131e  mov     cs:dword_18000E1F0, eax
0x180001324  call    __scrt_acquire_startup_lock
0x180001329  mov     bl, al
0x18000132b  mov     [rsp+38h+var_18], al
0x18000132f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001336  jnz     short loc_18000136E
0x180001338  call    __scrt_dllmain_uninitialize_c
0x18000133d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001342  call    _RTC_Terminate
0x180001347  mov     cs:__scrt_current_native_startup_state, 0
0x180001351  mov     cl, bl
0x180001353  call    __scrt_release_startup_lock
0x180001358  xor     edx, edx
0x18000135a  mov     cl, dil
0x18000135d  call    __scrt_uninitialize_crt
0x180001362  movzx   ebx, al
0x180001365  call    __scrt_dllmain_uninitialize_critical
0x18000136a  mov     eax, ebx
0x18000136c  jmp     short loc_180001311
0x18000136e  mov     ecx, 7
0x180001373  call    __scrt_fastfail
0x180008169  push    rbp
0x18000816b  sub     rsp, 20h
0x18000816f  mov     rbp, rdx
0x180008172  mov     cl, [rbp+20h]
0x180008175  call    __scrt_release_startup_lock
0x18000817a  nop
0x18000817b  add     rsp, 20h
0x18000817f  pop     rbp
0x180008180  retn
0x180008182  push    rbp
0x180008184  sub     rsp, 20h
0x180008188  mov     rbp, rdx
0x18000818b  add     rsp, 20h
0x18000818f  pop     rbp
0x180008190  jmp     __scrt_dllmain_uninitialize_critical
```
