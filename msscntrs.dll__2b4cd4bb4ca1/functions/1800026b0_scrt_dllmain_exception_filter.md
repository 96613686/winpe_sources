# __scrt_dllmain_exception_filter

- ea: `0x1800026b0`
- end: `0x1800026f8`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002304`

## callees

- `0x1800026b0`
- `0x1800031cc`
- `0x1800032d8`
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
0x1800026b0  push    rbx
0x1800026b2  push    rbp
0x1800026b3  push    rsi
0x1800026b4  push    rdi
0x1800026b5  sub     rsp, 28h
0x1800026b9  mov     rdi, r9
0x1800026bc  mov     rsi, r8
0x1800026bf  mov     ebx, edx
0x1800026c1  mov     rbp, rcx
0x1800026c4  call    __scrt_is_ucrt_dll_in_use
0x1800026c9  test    eax, eax
0x1800026cb  jnz     short loc_1800026E2
0x1800026cd  cmp     ebx, 1
0x1800026d0  jnz     short loc_1800026E2
0x1800026d2  mov     r8, rsi
0x1800026d5  xor     edx, edx
0x1800026d7  mov     rcx, rbp
0x1800026da  mov     rax, rdi
0x1800026dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026e2  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800026e7  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800026eb  add     rsp, 28h
0x1800026ef  pop     rdi
0x1800026f0  pop     rsi
0x1800026f1  pop     rbp
0x1800026f2  pop     rbx
0x1800026f3  jmp     _o__seh_filter_dll_0
```
