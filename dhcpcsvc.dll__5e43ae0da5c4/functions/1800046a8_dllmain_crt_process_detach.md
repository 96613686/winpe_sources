# dllmain_crt_process_detach

- ea: `0x1800046a8`
- end: `0x18000472b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180004550`

## callees

- `0x1800046a8`
- `0x1800049b4`
- `0x1800049ec`
- `0x180004b14`
- `0x180004b4c`
- `0x180004cdc`
- `0x180004d08`
- `0x180004d48`
- `0x180004d98`

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

  if ( dword_18001E0D0 <= 0 )
    return 0;
  --dword_18001E0D0;
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
0x1800046a8  mov     [rsp+arg_0], rbx
0x1800046ad  push    rdi
0x1800046ae  sub     rsp, 30h
0x1800046b2  mov     dil, cl
0x1800046b5  mov     eax, cs:dword_18001E0D0
0x1800046bb  test    eax, eax
0x1800046bd  jg      short loc_1800046CC
0x1800046bf  xor     eax, eax
0x1800046c1  mov     rbx, [rsp+38h+arg_0]
0x1800046c6  add     rsp, 30h
0x1800046ca  pop     rdi
0x1800046cb  retn
0x1800046cc  dec     eax
0x1800046ce  mov     cs:dword_18001E0D0, eax
0x1800046d4  call    __scrt_acquire_startup_lock
0x1800046d9  mov     bl, al
0x1800046db  mov     [rsp+38h+var_18], al
0x1800046df  cmp     cs:__scrt_current_native_startup_state, 2
0x1800046e6  jnz     short loc_18000471E
0x1800046e8  call    __scrt_dllmain_uninitialize_c
0x1800046ed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800046f2  call    _RTC_Terminate
0x1800046f7  mov     cs:__scrt_current_native_startup_state, 0
0x180004701  mov     cl, bl
0x180004703  call    __scrt_release_startup_lock
0x180004708  xor     edx, edx
0x18000470a  mov     cl, dil
0x18000470d  call    __scrt_uninitialize_crt
0x180004712  movzx   ebx, al
0x180004715  call    __scrt_dllmain_uninitialize_critical
0x18000471a  mov     eax, ebx
0x18000471c  jmp     short loc_1800046C1
0x18000471e  mov     ecx, 7
0x180004723  call    __scrt_fastfail
0x180010c5f  push    rbp
0x180010c61  sub     rsp, 20h
0x180010c65  mov     rbp, rdx
0x180010c68  mov     cl, [rbp+20h]
0x180010c6b  call    __scrt_release_startup_lock
0x180010c70  nop
0x180010c71  add     rsp, 20h
0x180010c75  pop     rbp
0x180010c76  retn
0x180010c78  push    rbp
0x180010c7a  sub     rsp, 20h
0x180010c7e  mov     rbp, rdx
0x180010c81  add     rsp, 20h
0x180010c85  pop     rbp
0x180010c86  jmp     __scrt_dllmain_uninitialize_critical
```
