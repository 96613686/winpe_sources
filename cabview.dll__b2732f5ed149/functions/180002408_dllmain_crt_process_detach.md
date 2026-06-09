# dllmain_crt_process_detach

- ea: `0x180002408`
- end: `0x18000248b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800022b0`

## callees

- `0x180002408`
- `0x180002650`
- `0x180002778`
- `0x1800027b0`
- `0x180002940`
- `0x18000296c`
- `0x180002af0`
- `0x180002b38`
- `0x180002b88`

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

  if ( dword_18001A210 <= 0 )
    return 0;
  --dword_18001A210;
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
0x180002408  mov     [rsp+arg_0], rbx
0x18000240d  push    rdi
0x18000240e  sub     rsp, 30h
0x180002412  mov     dil, cl
0x180002415  mov     eax, cs:dword_18001A210
0x18000241b  test    eax, eax
0x18000241d  jg      short loc_18000242C
0x18000241f  xor     eax, eax
0x180002421  mov     rbx, [rsp+38h+arg_0]
0x180002426  add     rsp, 30h
0x18000242a  pop     rdi
0x18000242b  retn
0x18000242c  dec     eax
0x18000242e  mov     cs:dword_18001A210, eax
0x180002434  call    __scrt_acquire_startup_lock
0x180002439  mov     bl, al
0x18000243b  mov     [rsp+38h+var_18], al
0x18000243f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002446  jnz     short loc_18000247E
0x180002448  call    __scrt_dllmain_uninitialize_c
0x18000244d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002452  call    _RTC_Terminate
0x180002457  mov     cs:__scrt_current_native_startup_state, 0
0x180002461  mov     cl, bl
0x180002463  call    __scrt_release_startup_lock
0x180002468  xor     edx, edx
0x18000246a  mov     cl, dil
0x18000246d  call    __scrt_uninitialize_crt
0x180002472  movzx   ebx, al
0x180002475  call    __scrt_dllmain_uninitialize_critical
0x18000247a  mov     eax, ebx
0x18000247c  jmp     short loc_180002421
0x18000247e  mov     ecx, 7
0x180002483  call    __scrt_fastfail
0x180012b29  push    rbp
0x180012b2b  sub     rsp, 20h
0x180012b2f  mov     rbp, rdx
0x180012b32  mov     cl, [rbp+20h]
0x180012b35  call    __scrt_release_startup_lock
0x180012b3a  nop
0x180012b3b  add     rsp, 20h
0x180012b3f  pop     rbp
0x180012b40  retn
0x180012b42  push    rbp
0x180012b44  sub     rsp, 20h
0x180012b48  mov     rbp, rdx
0x180012b4b  add     rsp, 20h
0x180012b4f  pop     rbp
0x180012b50  jmp     __scrt_dllmain_uninitialize_critical
```
