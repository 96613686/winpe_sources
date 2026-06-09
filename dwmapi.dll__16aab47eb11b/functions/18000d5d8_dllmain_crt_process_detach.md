# dllmain_crt_process_detach

- ea: `0x18000d5d8`
- end: `0x18000d65b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000d480`

## callees

- `0x18000d0c4`
- `0x18000d1ec`
- `0x18000d224`
- `0x18000d3b4`
- `0x18000d3e0`
- `0x18000d5d8`
- `0x18000db30`
- `0x18000dc18`
- `0x18000dca4`

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

  if ( dword_18001F594 <= 0 )
    return 0;
  --dword_18001F594;
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
0x18000d5d8  mov     [rsp+arg_0], rbx
0x18000d5dd  push    rdi
0x18000d5de  sub     rsp, 30h
0x18000d5e2  mov     dil, cl
0x18000d5e5  mov     eax, cs:dword_18001F594
0x18000d5eb  test    eax, eax
0x18000d5ed  jg      short loc_18000D5FC
0x18000d5ef  xor     eax, eax
0x18000d5f1  mov     rbx, [rsp+38h+arg_0]
0x18000d5f6  add     rsp, 30h
0x18000d5fa  pop     rdi
0x18000d5fb  retn
0x18000d5fc  dec     eax
0x18000d5fe  mov     cs:dword_18001F594, eax
0x18000d604  call    __scrt_acquire_startup_lock
0x18000d609  mov     bl, al
0x18000d60b  mov     [rsp+38h+var_18], al
0x18000d60f  cmp     cs:__scrt_current_native_startup_state, 2
0x18000d616  jnz     short loc_18000D64E
0x18000d618  call    __scrt_dllmain_uninitialize_c
0x18000d61d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000d622  call    _RTC_Terminate
0x18000d627  mov     cs:__scrt_current_native_startup_state, 0
0x18000d631  mov     cl, bl
0x18000d633  call    __scrt_release_startup_lock
0x18000d638  xor     edx, edx
0x18000d63a  mov     cl, dil
0x18000d63d  call    __scrt_uninitialize_crt
0x18000d642  movzx   ebx, al
0x18000d645  call    __scrt_dllmain_uninitialize_critical
0x18000d64a  mov     eax, ebx
0x18000d64c  jmp     short loc_18000D5F1
0x18000d64e  mov     ecx, 7
0x18000d653  call    __scrt_fastfail
0x1800167f7  push    rbp
0x1800167f9  sub     rsp, 20h
0x1800167fd  mov     rbp, rdx
0x180016800  mov     cl, [rbp+20h]
0x180016803  call    __scrt_release_startup_lock
0x180016808  nop
0x180016809  add     rsp, 20h
0x18001680d  pop     rbp
0x18001680e  retn
0x180016810  push    rbp
0x180016812  sub     rsp, 20h
0x180016816  mov     rbp, rdx
0x180016819  add     rsp, 20h
0x18001681d  pop     rbp
0x18001681e  jmp     __scrt_dllmain_uninitialize_critical
```
