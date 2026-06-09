# dllmain_crt_process_detach

- ea: `0x1800034d8`
- end: `0x18000355b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180003380`

## callees

- `0x1800034d8`
- `0x180003758`
- `0x180003880`
- `0x1800038b8`
- `0x180003a48`
- `0x180003a74`
- `0x180003c1c`
- `0x180003c64`
- `0x180003cb4`

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

  if ( dword_18003C810 <= 0 )
    return 0;
  --dword_18003C810;
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
0x1800034d8  mov     [rsp+arg_0], rbx
0x1800034dd  push    rdi
0x1800034de  sub     rsp, 30h
0x1800034e2  mov     dil, cl
0x1800034e5  mov     eax, cs:dword_18003C810
0x1800034eb  test    eax, eax
0x1800034ed  jg      short loc_1800034FC
0x1800034ef  xor     eax, eax
0x1800034f1  mov     rbx, [rsp+38h+arg_0]
0x1800034f6  add     rsp, 30h
0x1800034fa  pop     rdi
0x1800034fb  retn
0x1800034fc  dec     eax
0x1800034fe  mov     cs:dword_18003C810, eax
0x180003504  call    __scrt_acquire_startup_lock
0x180003509  mov     bl, al
0x18000350b  mov     [rsp+38h+var_18], al
0x18000350f  cmp     cs:__scrt_current_native_startup_state, 2
0x180003516  jnz     short loc_18000354E
0x180003518  call    __scrt_dllmain_uninitialize_c
0x18000351d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180003522  call    _RTC_Terminate
0x180003527  mov     cs:__scrt_current_native_startup_state, 0
0x180003531  mov     cl, bl
0x180003533  call    __scrt_release_startup_lock
0x180003538  xor     edx, edx
0x18000353a  mov     cl, dil
0x18000353d  call    __scrt_uninitialize_crt
0x180003542  movzx   ebx, al
0x180003545  call    __scrt_dllmain_uninitialize_critical
0x18000354a  mov     eax, ebx
0x18000354c  jmp     short loc_1800034F1
0x18000354e  mov     ecx, 7
0x180003553  call    __scrt_fastfail
0x1800283e9  push    rbp
0x1800283eb  sub     rsp, 20h
0x1800283ef  mov     rbp, rdx
0x1800283f2  mov     cl, [rbp+20h]
0x1800283f5  call    __scrt_release_startup_lock
0x1800283fa  nop
0x1800283fb  add     rsp, 20h
0x1800283ff  pop     rbp
0x180028400  retn
0x180028402  push    rbp
0x180028404  sub     rsp, 20h
0x180028408  mov     rbp, rdx
0x18002840b  add     rsp, 20h
0x18002840f  pop     rbp
0x180028410  jmp     __scrt_dllmain_uninitialize_critical
```
