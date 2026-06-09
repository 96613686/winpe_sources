# __scrt_dllmain_exception_filter

- ea: `0x18001e2cc`
- end: `0x18001e314`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001e034`

## callees

- `0x18001e2cc`
- `0x18001ea38`
- `0x18001eb18`
- `0x180030010`

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
0x18001e2cc  push    rbx
0x18001e2ce  push    rbp
0x18001e2cf  push    rsi
0x18001e2d0  push    rdi
0x18001e2d1  sub     rsp, 28h
0x18001e2d5  mov     rdi, r9
0x18001e2d8  mov     rsi, r8
0x18001e2db  mov     ebx, edx
0x18001e2dd  mov     rbp, rcx
0x18001e2e0  call    __scrt_is_ucrt_dll_in_use
0x18001e2e5  test    eax, eax
0x18001e2e7  jnz     short loc_18001E2FE
0x18001e2e9  cmp     ebx, 1
0x18001e2ec  jnz     short loc_18001E2FE
0x18001e2ee  mov     r8, rsi
0x18001e2f1  xor     edx, edx
0x18001e2f3  mov     rcx, rbp
0x18001e2f6  mov     rax, rdi
0x18001e2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2fe  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18001e303  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18001e307  add     rsp, 28h
0x18001e30b  pop     rdi
0x18001e30c  pop     rsi
0x18001e30d  pop     rbp
0x18001e30e  pop     rbx
0x18001e30f  jmp     _o__seh_filter_dll_0
```
