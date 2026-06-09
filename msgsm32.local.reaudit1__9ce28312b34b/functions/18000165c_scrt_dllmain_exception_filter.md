# __scrt_dllmain_exception_filter

- ea: `0x18000165c`
- end: `0x1800016a4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001274`

## callees

- `0x18000165c`
- `0x180001c10`
- `0x180001cb2`
- `0x180007010`

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
0x18000165c  push    rbx
0x18000165e  push    rbp
0x18000165f  push    rsi
0x180001660  push    rdi
0x180001661  sub     rsp, 28h
0x180001665  mov     rdi, r9
0x180001668  mov     rsi, r8
0x18000166b  mov     ebx, edx
0x18000166d  mov     rbp, rcx
0x180001670  call    __scrt_is_ucrt_dll_in_use
0x180001675  test    eax, eax
0x180001677  jnz     short loc_18000168E
0x180001679  cmp     ebx, 1
0x18000167c  jnz     short loc_18000168E
0x18000167e  mov     r8, rsi
0x180001681  xor     edx, edx
0x180001683  mov     rcx, rbp
0x180001686  mov     rax, rdi
0x180001689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000168e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001693  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001697  add     rsp, 28h
0x18000169b  pop     rdi
0x18000169c  pop     rsi
0x18000169d  pop     rbp
0x18000169e  pop     rbx
0x18000169f  jmp     _o__seh_filter_dll_0
```
