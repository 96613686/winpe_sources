# __scrt_dllmain_exception_filter

- ea: `0x180014270`
- end: `0x1800142b8`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180013f94`

## callees

- `0x180014270`
- `0x180014e74`
- `0x180014f78`
- `0x180025010`

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
  if ( !_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180014270  push    rbx
0x180014272  push    rbp
0x180014273  push    rsi
0x180014274  push    rdi
0x180014275  sub     rsp, 28h
0x180014279  mov     rdi, r9
0x18001427c  mov     rsi, r8
0x18001427f  mov     ebx, edx
0x180014281  mov     rbp, rcx
0x180014284  call    __scrt_is_ucrt_dll_in_use
0x180014289  test    eax, eax
0x18001428b  jnz     short loc_1800142A2
0x18001428d  cmp     ebx, 1
0x180014290  jnz     short loc_1800142A2
0x180014292  mov     r8, rsi
0x180014295  xor     edx, edx
0x180014297  mov     rcx, rbp
0x18001429a  mov     rax, rdi
0x18001429d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142a2  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800142a7  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800142ab  add     rsp, 28h
0x1800142af  pop     rdi
0x1800142b0  pop     rsi
0x1800142b1  pop     rbp
0x1800142b2  pop     rbx
0x1800142b3  jmp     _o__seh_filter_dll_0
```
