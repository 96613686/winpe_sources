# __scrt_dllmain_exception_filter

- ea: `0x18000c8cc`
- end: `0x18000c914`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000c674`

## callees

- `0x18000c8cc`
- `0x18000cf70`
- `0x18000d088`
- `0x180019010`

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
0x18000c8cc  push    rbx
0x18000c8ce  push    rbp
0x18000c8cf  push    rsi
0x18000c8d0  push    rdi
0x18000c8d1  sub     rsp, 28h
0x18000c8d5  mov     rdi, r9
0x18000c8d8  mov     rsi, r8
0x18000c8db  mov     ebx, edx
0x18000c8dd  mov     rbp, rcx
0x18000c8e0  call    __scrt_is_ucrt_dll_in_use
0x18000c8e5  test    eax, eax
0x18000c8e7  jnz     short loc_18000C8FE
0x18000c8e9  cmp     ebx, 1
0x18000c8ec  jnz     short loc_18000C8FE
0x18000c8ee  mov     r8, rsi
0x18000c8f1  xor     edx, edx
0x18000c8f3  mov     rcx, rbp
0x18000c8f6  mov     rax, rdi
0x18000c8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8fe  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000c903  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000c907  add     rsp, 28h
0x18000c90b  pop     rdi
0x18000c90c  pop     rsi
0x18000c90d  pop     rbp
0x18000c90e  pop     rbx
0x18000c90f  jmp     _o__seh_filter_dll_0
```
