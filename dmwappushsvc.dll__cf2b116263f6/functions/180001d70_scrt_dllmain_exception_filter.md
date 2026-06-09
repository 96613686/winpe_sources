# __scrt_dllmain_exception_filter

- ea: `0x180001d70`
- end: `0x180001db8`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800018d4`

## callees

- `0x180001d70`
- `0x18000241c`
- `0x180002518`
- `0x180012010`

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
0x180001d70  push    rbx
0x180001d72  push    rbp
0x180001d73  push    rsi
0x180001d74  push    rdi
0x180001d75  sub     rsp, 28h
0x180001d79  mov     rdi, r9
0x180001d7c  mov     rsi, r8
0x180001d7f  mov     ebx, edx
0x180001d81  mov     rbp, rcx
0x180001d84  call    __scrt_is_ucrt_dll_in_use
0x180001d89  test    eax, eax
0x180001d8b  jnz     short loc_180001DA2
0x180001d8d  cmp     ebx, 1
0x180001d90  jnz     short loc_180001DA2
0x180001d92  mov     r8, rsi
0x180001d95  xor     edx, edx
0x180001d97  mov     rcx, rbp
0x180001d9a  mov     rax, rdi
0x180001d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001da2  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001da7  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001dab  add     rsp, 28h
0x180001daf  pop     rdi
0x180001db0  pop     rsi
0x180001db1  pop     rbp
0x180001db2  pop     rbx
0x180001db3  jmp     _o__seh_filter_dll_0
```
