# __scrt_dllmain_exception_filter

- ea: `0x180001e24`
- end: `0x180001e6c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001b54`

## callees

- `0x180001e24`
- `0x180002588`
- `0x180002698`
- `0x180013010`

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
0x180001e24  push    rbx
0x180001e26  push    rbp
0x180001e27  push    rsi
0x180001e28  push    rdi
0x180001e29  sub     rsp, 28h
0x180001e2d  mov     rdi, r9
0x180001e30  mov     rsi, r8
0x180001e33  mov     ebx, edx
0x180001e35  mov     rbp, rcx
0x180001e38  call    __scrt_is_ucrt_dll_in_use
0x180001e3d  test    eax, eax
0x180001e3f  jnz     short loc_180001E56
0x180001e41  cmp     ebx, 1
0x180001e44  jnz     short loc_180001E56
0x180001e46  mov     r8, rsi
0x180001e49  xor     edx, edx
0x180001e4b  mov     rcx, rbp
0x180001e4e  mov     rax, rdi
0x180001e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e56  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001e5b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001e5f  add     rsp, 28h
0x180001e63  pop     rdi
0x180001e64  pop     rsi
0x180001e65  pop     rbp
0x180001e66  pop     rbx
0x180001e67  jmp     _o__seh_filter_dll_0
```
