# __scrt_dllmain_exception_filter

- ea: `0x18000236c`
- end: `0x1800023b4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800020e4`

## callees

- `0x18000236c`
- `0x180002aa8`
- `0x180002b88`
- `0x180015010`

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
0x18000236c  push    rbx
0x18000236e  push    rbp
0x18000236f  push    rsi
0x180002370  push    rdi
0x180002371  sub     rsp, 28h
0x180002375  mov     rdi, r9
0x180002378  mov     rsi, r8
0x18000237b  mov     ebx, edx
0x18000237d  mov     rbp, rcx
0x180002380  call    __scrt_is_ucrt_dll_in_use
0x180002385  test    eax, eax
0x180002387  jnz     short loc_18000239E
0x180002389  cmp     ebx, 1
0x18000238c  jnz     short loc_18000239E
0x18000238e  mov     r8, rsi
0x180002391  xor     edx, edx
0x180002393  mov     rcx, rbp
0x180002396  mov     rax, rdi
0x180002399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000239e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800023a3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800023a7  add     rsp, 28h
0x1800023ab  pop     rdi
0x1800023ac  pop     rsi
0x1800023ad  pop     rbp
0x1800023ae  pop     rbx
0x1800023af  jmp     _o__seh_filter_dll_0
```
