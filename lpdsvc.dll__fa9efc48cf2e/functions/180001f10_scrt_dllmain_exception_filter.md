# __scrt_dllmain_exception_filter

- ea: `0x180001f10`
- end: `0x180001f58`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001b54`

## callees

- `0x180001f10`
- `0x180002538`
- `0x1800025e6`
- `0x18000e010`

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
0x180001f10  push    rbx
0x180001f12  push    rbp
0x180001f13  push    rsi
0x180001f14  push    rdi
0x180001f15  sub     rsp, 28h
0x180001f19  mov     rdi, r9
0x180001f1c  mov     rsi, r8
0x180001f1f  mov     ebx, edx
0x180001f21  mov     rbp, rcx
0x180001f24  call    __scrt_is_ucrt_dll_in_use
0x180001f29  test    eax, eax
0x180001f2b  jnz     short loc_180001F42
0x180001f2d  cmp     ebx, 1
0x180001f30  jnz     short loc_180001F42
0x180001f32  mov     r8, rsi
0x180001f35  xor     edx, edx
0x180001f37  mov     rcx, rbp
0x180001f3a  mov     rax, rdi
0x180001f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f42  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001f47  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001f4b  add     rsp, 28h
0x180001f4f  pop     rdi
0x180001f50  pop     rsi
0x180001f51  pop     rbp
0x180001f52  pop     rbx
0x180001f53  jmp     _o__seh_filter_dll_0
```
