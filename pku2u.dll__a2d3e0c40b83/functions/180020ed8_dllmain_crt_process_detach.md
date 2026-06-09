# dllmain_crt_process_detach

- ea: `0x180020ed8`
- end: `0x180020f5b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180020d80`

## callees

- `0x180020ed8`
- `0x1800211e4`
- `0x18002121c`
- `0x180021344`
- `0x18002137c`
- `0x18002150c`
- `0x180021538`
- `0x1800215d8`
- `0x180021628`

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

  if ( dword_180054950 <= 0 )
    return 0;
  --dword_180054950;
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
0x180020ed8  mov     [rsp+arg_0], rbx
0x180020edd  push    rdi
0x180020ede  sub     rsp, 30h
0x180020ee2  mov     dil, cl
0x180020ee5  mov     eax, cs:dword_180054950
0x180020eeb  test    eax, eax
0x180020eed  jg      short loc_180020EFC
0x180020eef  xor     eax, eax
0x180020ef1  mov     rbx, [rsp+38h+arg_0]
0x180020ef6  add     rsp, 30h
0x180020efa  pop     rdi
0x180020efb  retn
0x180020efc  dec     eax
0x180020efe  mov     cs:dword_180054950, eax
0x180020f04  call    __scrt_acquire_startup_lock
0x180020f09  mov     bl, al
0x180020f0b  mov     [rsp+38h+var_18], al
0x180020f0f  cmp     cs:__scrt_current_native_startup_state, 2
0x180020f16  jnz     short loc_180020F4E
0x180020f18  call    __scrt_dllmain_uninitialize_c
0x180020f1d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180020f22  call    _RTC_Terminate
0x180020f27  mov     cs:__scrt_current_native_startup_state, 0
0x180020f31  mov     cl, bl
0x180020f33  call    __scrt_release_startup_lock
0x180020f38  xor     edx, edx
0x180020f3a  mov     cl, dil
0x180020f3d  call    __scrt_uninitialize_crt
0x180020f42  movzx   ebx, al
0x180020f45  call    __scrt_dllmain_uninitialize_critical
0x180020f4a  mov     eax, ebx
0x180020f4c  jmp     short loc_180020EF1
0x180020f4e  mov     ecx, 7
0x180020f53  call    __scrt_fastfail
0x180045073  push    rbp
0x180045075  sub     rsp, 20h
0x180045079  mov     rbp, rdx
0x18004507c  mov     cl, [rbp+20h]
0x18004507f  call    __scrt_release_startup_lock
0x180045084  nop
0x180045085  add     rsp, 20h
0x180045089  pop     rbp
0x18004508a  retn
0x18004508c  push    rbp
0x18004508e  sub     rsp, 20h
0x180045092  mov     rbp, rdx
0x180045095  add     rsp, 20h
0x180045099  pop     rbp
0x18004509a  jmp     __scrt_dllmain_uninitialize_critical
```
