# __scrt_dllmain_exception_filter

- ea: `0x18000e4f4`
- end: `0x18000e53c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000e164`

## callees

- `0x18000e4f4`
- `0x18000eb38`
- `0x18000ebf8`
- `0x180018010`

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
0x18000e4f4  push    rbx
0x18000e4f6  push    rbp
0x18000e4f7  push    rsi
0x18000e4f8  push    rdi
0x18000e4f9  sub     rsp, 28h
0x18000e4fd  mov     rdi, r9
0x18000e500  mov     rsi, r8
0x18000e503  mov     ebx, edx
0x18000e505  mov     rbp, rcx
0x18000e508  call    __scrt_is_ucrt_dll_in_use
0x18000e50d  test    eax, eax
0x18000e50f  jnz     short loc_18000E526
0x18000e511  cmp     ebx, 1
0x18000e514  jnz     short loc_18000E526
0x18000e516  mov     r8, rsi
0x18000e519  xor     edx, edx
0x18000e51b  mov     rcx, rbp
0x18000e51e  mov     rax, rdi
0x18000e521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e526  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000e52b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000e52f  add     rsp, 28h
0x18000e533  pop     rdi
0x18000e534  pop     rsi
0x18000e535  pop     rbp
0x18000e536  pop     rbx
0x18000e537  jmp     _o__seh_filter_dll_0
```
