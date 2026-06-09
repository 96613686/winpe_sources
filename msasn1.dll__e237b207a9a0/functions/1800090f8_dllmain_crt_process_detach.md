# dllmain_crt_process_detach

- ea: `0x1800090f8`
- end: `0x18000917b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180008fa0`

## callees

- `0x1800090f8`
- `0x180009404`
- `0x18000943c`
- `0x180009564`
- `0x18000959c`
- `0x18000972c`
- `0x180009758`
- `0x180009798`
- `0x1800097e8`

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

  if ( dword_18000F090 <= 0 )
    return 0;
  --dword_18000F090;
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
0x1800090f8  mov     [rsp+arg_0], rbx
0x1800090fd  push    rdi
0x1800090fe  sub     rsp, 30h
0x180009102  mov     dil, cl
0x180009105  mov     eax, cs:dword_18000F090
0x18000910b  test    eax, eax
0x18000910d  jg      short loc_18000911C
0x18000910f  xor     eax, eax
0x180009111  mov     rbx, [rsp+38h+arg_0]
0x180009116  add     rsp, 30h
0x18000911a  pop     rdi
0x18000911b  retn
0x18000911c  dec     eax
0x18000911e  mov     cs:dword_18000F090, eax
0x180009124  call    __scrt_acquire_startup_lock
0x180009129  mov     bl, al
0x18000912b  mov     [rsp+38h+var_18], al
0x18000912f  cmp     cs:__scrt_current_native_startup_state, 2
0x180009136  jnz     short loc_18000916E
0x180009138  call    __scrt_dllmain_uninitialize_c
0x18000913d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180009142  call    _RTC_Terminate
0x180009147  mov     cs:__scrt_current_native_startup_state, 0
0x180009151  mov     cl, bl
0x180009153  call    __scrt_release_startup_lock
0x180009158  xor     edx, edx
0x18000915a  mov     cl, dil
0x18000915d  call    __scrt_uninitialize_crt
0x180009162  movzx   ebx, al
0x180009165  call    __scrt_dllmain_uninitialize_critical
0x18000916a  mov     eax, ebx
0x18000916c  jmp     short loc_180009111
0x18000916e  mov     ecx, 7
0x180009173  call    __scrt_fastfail
0x18000ab79  push    rbp
0x18000ab7b  sub     rsp, 20h
0x18000ab7f  mov     rbp, rdx
0x18000ab82  mov     cl, [rbp+20h]
0x18000ab85  call    __scrt_release_startup_lock
0x18000ab8a  nop
0x18000ab8b  add     rsp, 20h
0x18000ab8f  pop     rbp
0x18000ab90  retn
0x18000ab92  push    rbp
0x18000ab94  sub     rsp, 20h
0x18000ab98  mov     rbp, rdx
0x18000ab9b  add     rsp, 20h
0x18000ab9f  pop     rbp
0x18000aba0  jmp     __scrt_dllmain_uninitialize_critical
```
