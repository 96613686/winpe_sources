# __scrt_dllmain_exception_filter

- ea: `0x180009490`
- end: `0x1800094d8`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800090e4`

## callees

- `0x180009490`
- `0x180009a40`
- `0x180009aee`
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
  if ( !_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180009490  push    rbx
0x180009492  push    rbp
0x180009493  push    rsi
0x180009494  push    rdi
0x180009495  sub     rsp, 28h
0x180009499  mov     rdi, r9
0x18000949c  mov     rsi, r8
0x18000949f  mov     ebx, edx
0x1800094a1  mov     rbp, rcx
0x1800094a4  call    __scrt_is_ucrt_dll_in_use
0x1800094a9  test    eax, eax
0x1800094ab  jnz     short loc_1800094C2
0x1800094ad  cmp     ebx, 1
0x1800094b0  jnz     short loc_1800094C2
0x1800094b2  mov     r8, rsi
0x1800094b5  xor     edx, edx
0x1800094b7  mov     rcx, rbp
0x1800094ba  mov     rax, rdi
0x1800094bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094c2  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800094c7  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800094cb  add     rsp, 28h
0x1800094cf  pop     rdi
0x1800094d0  pop     rsi
0x1800094d1  pop     rbp
0x1800094d2  pop     rbx
0x1800094d3  jmp     _o__seh_filter_dll_0
```
