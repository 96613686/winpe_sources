# dllmain_crt_process_detach

- ea: `0x180020038`
- end: `0x1800200bb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001fee0`

## callees

- `0x180020038`
- `0x18002036c`
- `0x1800203a4`
- `0x1800204cc`
- `0x180020504`
- `0x180020694`
- `0x1800206c0`
- `0x180020700`
- `0x180020750`

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

  if ( dword_18003A290 <= 0 )
    return 0;
  --dword_18003A290;
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
0x180020038  mov     [rsp+arg_0], rbx
0x18002003d  push    rdi
0x18002003e  sub     rsp, 30h
0x180020042  mov     dil, cl
0x180020045  mov     eax, cs:dword_18003A290
0x18002004b  test    eax, eax
0x18002004d  jg      short loc_18002005C
0x18002004f  xor     eax, eax
0x180020051  mov     rbx, [rsp+38h+arg_0]
0x180020056  add     rsp, 30h
0x18002005a  pop     rdi
0x18002005b  retn
0x18002005c  dec     eax
0x18002005e  mov     cs:dword_18003A290, eax
0x180020064  call    __scrt_acquire_startup_lock
0x180020069  mov     bl, al
0x18002006b  mov     [rsp+38h+var_18], al
0x18002006f  cmp     cs:__scrt_current_native_startup_state, 2
0x180020076  jnz     short loc_1800200AE
0x180020078  call    __scrt_dllmain_uninitialize_c
0x18002007d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180020082  call    _RTC_Terminate
0x180020087  mov     cs:__scrt_current_native_startup_state, 0
0x180020091  mov     cl, bl
0x180020093  call    __scrt_release_startup_lock
0x180020098  xor     edx, edx
0x18002009a  mov     cl, dil
0x18002009d  call    __scrt_uninitialize_crt
0x1800200a2  movzx   ebx, al
0x1800200a5  call    __scrt_dllmain_uninitialize_critical
0x1800200aa  mov     eax, ebx
0x1800200ac  jmp     short loc_180020051
0x1800200ae  mov     ecx, 7
0x1800200b3  call    __scrt_fastfail
0x18002f799  push    rbp
0x18002f79b  sub     rsp, 20h
0x18002f79f  mov     rbp, rdx
0x18002f7a2  mov     cl, [rbp+20h]
0x18002f7a5  call    __scrt_release_startup_lock
0x18002f7aa  nop
0x18002f7ab  add     rsp, 20h
0x18002f7af  pop     rbp
0x18002f7b0  retn
0x18002f7b2  push    rbp
0x18002f7b4  sub     rsp, 20h
0x18002f7b8  mov     rbp, rdx
0x18002f7bb  add     rsp, 20h
0x18002f7bf  pop     rbp
0x18002f7c0  jmp     __scrt_dllmain_uninitialize_critical
```
