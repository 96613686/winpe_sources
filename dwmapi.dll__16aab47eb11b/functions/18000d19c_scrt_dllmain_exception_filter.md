# __scrt_dllmain_exception_filter

- ea: `0x18000d19c`
- end: `0x18000d1e4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000d664`

## callees

- `0x18000d19c`
- `0x18000db1c`
- `0x18000dd88`
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
  if ( !_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x18000d19c  push    rbx
0x18000d19e  push    rbp
0x18000d19f  push    rsi
0x18000d1a0  push    rdi
0x18000d1a1  sub     rsp, 28h
0x18000d1a5  mov     rdi, r9
0x18000d1a8  mov     rsi, r8
0x18000d1ab  mov     ebx, edx
0x18000d1ad  mov     rbp, rcx
0x18000d1b0  call    __scrt_is_ucrt_dll_in_use
0x18000d1b5  test    eax, eax
0x18000d1b7  jnz     short loc_18000D1CE
0x18000d1b9  cmp     ebx, 1
0x18000d1bc  jnz     short loc_18000D1CE
0x18000d1be  mov     r8, rsi
0x18000d1c1  xor     edx, edx
0x18000d1c3  mov     rcx, rbp
0x18000d1c6  mov     rax, rdi
0x18000d1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1ce  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000d1d3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000d1d7  add     rsp, 28h
0x18000d1db  pop     rdi
0x18000d1dc  pop     rsi
0x18000d1dd  pop     rbp
0x18000d1de  pop     rbx
0x18000d1df  jmp     _o__seh_filter_dll_0
```
