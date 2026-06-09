# dllmain_crt_process_detach

- ea: `0x180006108`
- end: `0x18000618b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180005fb0`

## callees

- `0x180006108`
- `0x180006448`
- `0x180006570`
- `0x1800065a8`
- `0x180006738`
- `0x180006764`
- `0x180006940`
- `0x180006988`
- `0x1800069d8`

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

  if ( dword_180031330 <= 0 )
    return 0;
  --dword_180031330;
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
0x180006108  mov     [rsp+arg_0], rbx
0x18000610d  push    rdi
0x18000610e  sub     rsp, 30h
0x180006112  mov     dil, cl
0x180006115  mov     eax, cs:dword_180031330
0x18000611b  test    eax, eax
0x18000611d  jg      short loc_18000612C
0x18000611f  xor     eax, eax
0x180006121  mov     rbx, [rsp+38h+arg_0]
0x180006126  add     rsp, 30h
0x18000612a  pop     rdi
0x18000612b  retn
0x18000612c  dec     eax
0x18000612e  mov     cs:dword_180031330, eax
0x180006134  call    __scrt_acquire_startup_lock
0x180006139  mov     bl, al
0x18000613b  mov     [rsp+38h+var_18], al
0x18000613f  cmp     cs:__scrt_current_native_startup_state, 2
0x180006146  jnz     short loc_18000617E
0x180006148  call    __scrt_dllmain_uninitialize_c
0x18000614d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180006152  call    _RTC_Terminate
0x180006157  mov     cs:__scrt_current_native_startup_state, 0
0x180006161  mov     cl, bl
0x180006163  call    __scrt_release_startup_lock
0x180006168  xor     edx, edx
0x18000616a  mov     cl, dil
0x18000616d  call    __scrt_uninitialize_crt
0x180006172  movzx   ebx, al
0x180006175  call    __scrt_dllmain_uninitialize_critical
0x18000617a  mov     eax, ebx
0x18000617c  jmp     short loc_180006121
0x18000617e  mov     ecx, 7
0x180006183  call    __scrt_fastfail
0x18001ea19  push    rbp
0x18001ea1b  sub     rsp, 20h
0x18001ea1f  mov     rbp, rdx
0x18001ea22  mov     cl, [rbp+20h]
0x18001ea25  call    __scrt_release_startup_lock
0x18001ea2a  nop
0x18001ea2b  add     rsp, 20h
0x18001ea2f  pop     rbp
0x18001ea30  retn
0x18001ea32  push    rbp
0x18001ea34  sub     rsp, 20h
0x18001ea38  mov     rbp, rdx
0x18001ea3b  add     rsp, 20h
0x18001ea3f  pop     rbp
0x18001ea40  jmp     __scrt_dllmain_uninitialize_critical
```
