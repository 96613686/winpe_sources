# __scrt_dllmain_exception_filter

- ea: `0x18000511c`
- end: `0x180005164`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004e94`

## callees

- `0x18000511c`
- `0x180005998`
- `0x180005b08`
- `0x18000b010`

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
0x18000511c  push    rbx
0x18000511e  push    rbp
0x18000511f  push    rsi
0x180005120  push    rdi
0x180005121  sub     rsp, 28h
0x180005125  mov     rdi, r9
0x180005128  mov     rsi, r8
0x18000512b  mov     ebx, edx
0x18000512d  mov     rbp, rcx
0x180005130  call    __scrt_is_ucrt_dll_in_use
0x180005135  test    eax, eax
0x180005137  jnz     short loc_18000514E
0x180005139  cmp     ebx, 1
0x18000513c  jnz     short loc_18000514E
0x18000513e  mov     r8, rsi
0x180005141  xor     edx, edx
0x180005143  mov     rcx, rbp
0x180005146  mov     rax, rdi
0x180005149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000514e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180005153  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180005157  add     rsp, 28h
0x18000515b  pop     rdi
0x18000515c  pop     rsi
0x18000515d  pop     rbp
0x18000515e  pop     rbx
0x18000515f  jmp     _o__seh_filter_dll_0
```
