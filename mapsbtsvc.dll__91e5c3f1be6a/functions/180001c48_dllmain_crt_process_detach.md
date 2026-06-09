# dllmain_crt_process_detach

- ea: `0x180001c48`
- end: `0x180001ccb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001af0`

## callees

- `0x180001c48`
- `0x180001ea0`
- `0x180001fc8`
- `0x180002000`
- `0x180002190`
- `0x1800021bc`
- `0x180002360`
- `0x1800023a8`
- `0x1800023f8`

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

  if ( dword_18001D590 <= 0 )
    return 0;
  --dword_18001D590;
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
0x180001c48  mov     [rsp+arg_0], rbx
0x180001c4d  push    rdi
0x180001c4e  sub     rsp, 30h
0x180001c52  mov     dil, cl
0x180001c55  mov     eax, cs:dword_18001D590
0x180001c5b  test    eax, eax
0x180001c5d  jg      short loc_180001C6C
0x180001c5f  xor     eax, eax
0x180001c61  mov     rbx, [rsp+38h+arg_0]
0x180001c66  add     rsp, 30h
0x180001c6a  pop     rdi
0x180001c6b  retn
0x180001c6c  dec     eax
0x180001c6e  mov     cs:dword_18001D590, eax
0x180001c74  call    __scrt_acquire_startup_lock
0x180001c79  mov     bl, al
0x180001c7b  mov     [rsp+38h+var_18], al
0x180001c7f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001c86  jnz     short loc_180001CBE
0x180001c88  call    __scrt_dllmain_uninitialize_c
0x180001c8d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001c92  call    _RTC_Terminate
0x180001c97  mov     cs:__scrt_current_native_startup_state, 0
0x180001ca1  mov     cl, bl
0x180001ca3  call    __scrt_release_startup_lock
0x180001ca8  xor     edx, edx
0x180001caa  mov     cl, dil
0x180001cad  call    __scrt_uninitialize_crt
0x180001cb2  movzx   ebx, al
0x180001cb5  call    __scrt_dllmain_uninitialize_critical
0x180001cba  mov     eax, ebx
0x180001cbc  jmp     short loc_180001C61
0x180001cbe  mov     ecx, 7
0x180001cc3  call    __scrt_fastfail
0x180013a89  push    rbp
0x180013a8b  sub     rsp, 20h
0x180013a8f  mov     rbp, rdx
0x180013a92  mov     cl, [rbp+20h]
0x180013a95  call    __scrt_release_startup_lock
0x180013a9a  nop
0x180013a9b  add     rsp, 20h
0x180013a9f  pop     rbp
0x180013aa0  retn
0x180013aa2  push    rbp
0x180013aa4  sub     rsp, 20h
0x180013aa8  mov     rbp, rdx
0x180013aab  add     rsp, 20h
0x180013aaf  pop     rbp
0x180013ab0  jmp     __scrt_dllmain_uninitialize_critical
```
