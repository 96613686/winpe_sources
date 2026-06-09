# dllmain_crt_process_detach

- ea: `0x180014118`
- end: `0x18001419b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180013fc0`

## callees

- `0x180014118`
- `0x1800147c0`
- `0x1800147f8`
- `0x180014920`
- `0x180014958`
- `0x180014ae8`
- `0x180014b14`
- `0x180014bb4`
- `0x180014c04`

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

  if ( dword_18003E990 <= 0 )
    return 0;
  --dword_18003E990;
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
0x180014118  mov     [rsp+arg_0], rbx
0x18001411d  push    rdi
0x18001411e  sub     rsp, 30h
0x180014122  mov     dil, cl
0x180014125  mov     eax, cs:dword_18003E990
0x18001412b  test    eax, eax
0x18001412d  jg      short loc_18001413C
0x18001412f  xor     eax, eax
0x180014131  mov     rbx, [rsp+38h+arg_0]
0x180014136  add     rsp, 30h
0x18001413a  pop     rdi
0x18001413b  retn
0x18001413c  dec     eax
0x18001413e  mov     cs:dword_18003E990, eax
0x180014144  call    __scrt_acquire_startup_lock
0x180014149  mov     bl, al
0x18001414b  mov     [rsp+38h+var_18], al
0x18001414f  cmp     cs:__scrt_current_native_startup_state, 2
0x180014156  jnz     short loc_18001418E
0x180014158  call    __scrt_dllmain_uninitialize_c
0x18001415d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180014162  call    _RTC_Terminate
0x180014167  mov     cs:__scrt_current_native_startup_state, 0
0x180014171  mov     cl, bl
0x180014173  call    __scrt_release_startup_lock
0x180014178  xor     edx, edx
0x18001417a  mov     cl, dil
0x18001417d  call    __scrt_uninitialize_crt
0x180014182  movzx   ebx, al
0x180014185  call    __scrt_dllmain_uninitialize_critical
0x18001418a  mov     eax, ebx
0x18001418c  jmp     short loc_180014131
0x18001418e  mov     ecx, 7
0x180014193  call    __scrt_fastfail
0x18002e725  push    rbp
0x18002e727  sub     rsp, 20h
0x18002e72b  mov     rbp, rdx
0x18002e72e  mov     cl, [rbp+20h]
0x18002e731  call    __scrt_release_startup_lock
0x18002e736  nop
0x18002e737  add     rsp, 20h
0x18002e73b  pop     rbp
0x18002e73c  retn
0x18002e73e  push    rbp
0x18002e740  sub     rsp, 20h
0x18002e744  mov     rbp, rdx
0x18002e747  add     rsp, 20h
0x18002e74b  pop     rbp
0x18002e74c  jmp     __scrt_dllmain_uninitialize_critical
```
