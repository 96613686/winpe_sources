# __scrt_dllmain_exception_filter

- ea: `0x180001c9c`
- end: `0x180001ce4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001a14`

## callees

- `0x180001c9c`
- `0x1800027e8`
- `0x180002948`
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
0x180001c9c  push    rbx
0x180001c9e  push    rbp
0x180001c9f  push    rsi
0x180001ca0  push    rdi
0x180001ca1  sub     rsp, 28h
0x180001ca5  mov     rdi, r9
0x180001ca8  mov     rsi, r8
0x180001cab  mov     ebx, edx
0x180001cad  mov     rbp, rcx
0x180001cb0  call    __scrt_is_ucrt_dll_in_use
0x180001cb5  test    eax, eax
0x180001cb7  jnz     short loc_180001CCE
0x180001cb9  cmp     ebx, 1
0x180001cbc  jnz     short loc_180001CCE
0x180001cbe  mov     r8, rsi
0x180001cc1  xor     edx, edx
0x180001cc3  mov     rcx, rbp
0x180001cc6  mov     rax, rdi
0x180001cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cce  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001cd3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001cd7  add     rsp, 28h
0x180001cdb  pop     rdi
0x180001cdc  pop     rsi
0x180001cdd  pop     rbp
0x180001cde  pop     rbx
0x180001cdf  jmp     _o__seh_filter_dll_0
```
