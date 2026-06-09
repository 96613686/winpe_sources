# __scrt_dllmain_exception_filter

- ea: `0x18001632c`
- end: `0x180016374`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180015f04`

## callees

- `0x18001632c`
- `0x180016964`
- `0x180016a42`
- `0x180026010`

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
0x18001632c  push    rbx
0x18001632e  push    rbp
0x18001632f  push    rsi
0x180016330  push    rdi
0x180016331  sub     rsp, 28h
0x180016335  mov     rdi, r9
0x180016338  mov     rsi, r8
0x18001633b  mov     ebx, edx
0x18001633d  mov     rbp, rcx
0x180016340  call    __scrt_is_ucrt_dll_in_use
0x180016345  test    eax, eax
0x180016347  jnz     short loc_18001635E
0x180016349  cmp     ebx, 1
0x18001634c  jnz     short loc_18001635E
0x18001634e  mov     r8, rsi
0x180016351  xor     edx, edx
0x180016353  mov     rcx, rbp
0x180016356  mov     rax, rdi
0x180016359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001635e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180016363  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180016367  add     rsp, 28h
0x18001636b  pop     rdi
0x18001636c  pop     rsi
0x18001636d  pop     rbp
0x18001636e  pop     rbx
0x18001636f  jmp     _o__seh_filter_dll_0
```
