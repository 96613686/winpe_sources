# dllmain_crt_process_detach

- ea: `0x180001558`
- end: `0x1800015db`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001400`

## callees

- `0x180001558`
- `0x1800017fc`
- `0x180001924`
- `0x18000195c`
- `0x180001aec`
- `0x180001b18`
- `0x180001cbc`
- `0x180001d04`
- `0x180001d54`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_1800202D0 <= 0 )
    return 0;
  --dword_1800202D0;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v4) = v3;
  _scrt_release_startup_lock(v4);
  LOBYTE(v5) = a1;
  v6 = (unsigned __int8)_scrt_uninitialize_crt(v5, 0);
  _scrt_dllmain_uninitialize_critical();
  return v6;
}

```

## disassembly

```asm
0x180001558  mov     [rsp+arg_0], rbx
0x18000155d  push    rdi
0x18000155e  sub     rsp, 30h
0x180001562  mov     dil, cl
0x180001565  mov     eax, cs:dword_1800202D0
0x18000156b  test    eax, eax
0x18000156d  jg      short loc_18000157C
0x18000156f  xor     eax, eax
0x180001571  mov     rbx, [rsp+38h+arg_0]
0x180001576  add     rsp, 30h
0x18000157a  pop     rdi
0x18000157b  retn
0x18000157c  dec     eax
0x18000157e  mov     cs:dword_1800202D0, eax
0x180001584  call    __scrt_acquire_startup_lock
0x180001589  mov     bl, al
0x18000158b  mov     [rsp+38h+var_18], al
0x18000158f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001596  jnz     short loc_1800015CE
0x180001598  call    __scrt_dllmain_uninitialize_c
0x18000159d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800015a2  call    _RTC_Terminate
0x1800015a7  mov     cs:__scrt_current_native_startup_state, 0
0x1800015b1  mov     cl, bl
0x1800015b3  call    __scrt_release_startup_lock
0x1800015b8  xor     edx, edx
0x1800015ba  mov     cl, dil
0x1800015bd  call    __scrt_uninitialize_crt
0x1800015c2  movzx   ebx, al
0x1800015c5  call    __scrt_dllmain_uninitialize_critical
0x1800015ca  mov     eax, ebx
0x1800015cc  jmp     short loc_180001571
0x1800015ce  mov     ecx, 7
0x1800015d3  call    __scrt_fastfail
0x1800152b9  push    rbp
0x1800152bb  sub     rsp, 20h
0x1800152bf  mov     rbp, rdx
0x1800152c2  mov     cl, [rbp+20h]
0x1800152c5  call    __scrt_release_startup_lock
0x1800152ca  nop
0x1800152cb  add     rsp, 20h
0x1800152cf  pop     rbp
0x1800152d0  retn
0x1800152d2  push    rbp
0x1800152d4  sub     rsp, 20h
0x1800152d8  mov     rbp, rdx
0x1800152db  add     rsp, 20h
0x1800152df  pop     rbp
0x1800152e0  jmp     __scrt_dllmain_uninitialize_critical
```
