# __scrt_dllmain_exception_filter

- ea: `0x1800018d4`
- end: `0x18000191c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800015e4`

## callees

- `0x1800018d4`
- `0x180002098`
- `0x1800021a8`
- `0x180017010`

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
0x1800018d4  push    rbx
0x1800018d6  push    rbp
0x1800018d7  push    rsi
0x1800018d8  push    rdi
0x1800018d9  sub     rsp, 28h
0x1800018dd  mov     rdi, r9
0x1800018e0  mov     rsi, r8
0x1800018e3  mov     ebx, edx
0x1800018e5  mov     rbp, rcx
0x1800018e8  call    __scrt_is_ucrt_dll_in_use
0x1800018ed  test    eax, eax
0x1800018ef  jnz     short loc_180001906
0x1800018f1  cmp     ebx, 1
0x1800018f4  jnz     short loc_180001906
0x1800018f6  mov     r8, rsi
0x1800018f9  xor     edx, edx
0x1800018fb  mov     rcx, rbp
0x1800018fe  mov     rax, rdi
0x180001901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001906  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000190b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000190f  add     rsp, 28h
0x180001913  pop     rdi
0x180001914  pop     rsi
0x180001915  pop     rbp
0x180001916  pop     rbx
0x180001917  jmp     _o__seh_filter_dll_0
```
