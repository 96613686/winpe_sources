# __scrt_dllmain_exception_filter

- ea: `0x180001664`
- end: `0x1800016ac`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800012d4`

## callees

- `0x180001664`
- `0x180001c2c`
- `0x180001ccc`
- `0x18001f010`

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
0x180001664  push    rbx
0x180001666  push    rbp
0x180001667  push    rsi
0x180001668  push    rdi
0x180001669  sub     rsp, 28h
0x18000166d  mov     rdi, r9
0x180001670  mov     rsi, r8
0x180001673  mov     ebx, edx
0x180001675  mov     rbp, rcx
0x180001678  call    __scrt_is_ucrt_dll_in_use
0x18000167d  test    eax, eax
0x18000167f  jnz     short loc_180001696
0x180001681  cmp     ebx, 1
0x180001684  jnz     short loc_180001696
0x180001686  mov     r8, rsi
0x180001689  xor     edx, edx
0x18000168b  mov     rcx, rbp
0x18000168e  mov     rax, rdi
0x180001691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001696  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000169b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000169f  add     rsp, 28h
0x1800016a3  pop     rdi
0x1800016a4  pop     rsi
0x1800016a5  pop     rbp
0x1800016a6  pop     rbx
0x1800016a7  jmp     _o__seh_filter_dll_0
```
