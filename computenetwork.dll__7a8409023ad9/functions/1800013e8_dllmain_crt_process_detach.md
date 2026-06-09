# dllmain_crt_process_detach

- ea: `0x1800013e8`
- end: `0x18000146b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001290`

## callees

- `0x1800013e8`
- `0x180001624`
- `0x18000174c`
- `0x180001784`
- `0x180001914`
- `0x180001940`
- `0x180001b4c`
- `0x180001b94`
- `0x180001be4`

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

  if ( dword_180018270 <= 0 )
    return 0;
  --dword_180018270;
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
0x1800013e8  mov     [rsp+arg_0], rbx
0x1800013ed  push    rdi
0x1800013ee  sub     rsp, 30h
0x1800013f2  mov     dil, cl
0x1800013f5  mov     eax, cs:dword_180018270
0x1800013fb  test    eax, eax
0x1800013fd  jg      short loc_18000140C
0x1800013ff  xor     eax, eax
0x180001401  mov     rbx, [rsp+38h+arg_0]
0x180001406  add     rsp, 30h
0x18000140a  pop     rdi
0x18000140b  retn
0x18000140c  dec     eax
0x18000140e  mov     cs:dword_180018270, eax
0x180001414  call    __scrt_acquire_startup_lock
0x180001419  mov     bl, al
0x18000141b  mov     [rsp+38h+var_18], al
0x18000141f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001426  jnz     short loc_18000145E
0x180001428  call    __scrt_dllmain_uninitialize_c
0x18000142d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001432  call    _RTC_Terminate
0x180001437  mov     cs:__scrt_current_native_startup_state, 0
0x180001441  mov     cl, bl
0x180001443  call    __scrt_release_startup_lock
0x180001448  xor     edx, edx
0x18000144a  mov     cl, dil
0x18000144d  call    __scrt_uninitialize_crt
0x180001452  movzx   ebx, al
0x180001455  call    __scrt_dllmain_uninitialize_critical
0x18000145a  mov     eax, ebx
0x18000145c  jmp     short loc_180001401
0x18000145e  mov     ecx, 7
0x180001463  call    __scrt_fastfail
0x18000cf79  push    rbp
0x18000cf7b  sub     rsp, 20h
0x18000cf7f  mov     rbp, rdx
0x18000cf82  mov     cl, [rbp+20h]
0x18000cf85  call    __scrt_release_startup_lock
0x18000cf8a  nop
0x18000cf8b  add     rsp, 20h
0x18000cf8f  pop     rbp
0x18000cf90  retn
0x18000cf92  push    rbp
0x18000cf94  sub     rsp, 20h
0x18000cf98  mov     rbp, rdx
0x18000cf9b  add     rsp, 20h
0x18000cf9f  pop     rbp
0x18000cfa0  jmp     __scrt_dllmain_uninitialize_critical
```
