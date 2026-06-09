# __scrt_dllmain_exception_filter

- ea: `0x18000183c`
- end: `0x180001884`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001424`

## callees

- `0x18000183c`
- `0x180001eb8`
- `0x180001fb2`
- `0x18000a010`

## pseudocode

```c
int __fastcall _scrt_dllmain_exception_filter(
        __int64 a1,
        int a2,
        __int64 a3,
        void (__fastcall *a4)(__int64, _QWORD, __int64),
        unsigned int ExceptionNum,
        struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x18000183c  push    rbx
0x18000183e  push    rbp
0x18000183f  push    rsi
0x180001840  push    rdi
0x180001841  sub     rsp, 28h
0x180001845  mov     rdi, r9
0x180001848  mov     rsi, r8
0x18000184b  mov     ebx, edx
0x18000184d  mov     rbp, rcx
0x180001850  call    __scrt_is_ucrt_dll_in_use
0x180001855  test    eax, eax
0x180001857  jnz     short loc_18000186E
0x180001859  cmp     ebx, 1
0x18000185c  jnz     short loc_18000186E
0x18000185e  mov     r8, rsi
0x180001861  xor     edx, edx
0x180001863  mov     rcx, rbp
0x180001866  mov     rax, rdi
0x180001869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000186e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001873  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001877  add     rsp, 28h
0x18000187b  pop     rdi
0x18000187c  pop     rsi
0x18000187d  pop     rbp
0x18000187e  pop     rbx
0x18000187f  jmp     _o__seh_filter_dll_0
```
