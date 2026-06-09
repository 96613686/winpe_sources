# __scrt_dllmain_exception_filter

- ea: `0x18000155c`
- end: `0x1800015a4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800012d4`

## callees

- `0x18000155c`
- `0x180001c98`
- `0x180001d66`
- `0x180004010`

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
0x18000155c  push    rbx
0x18000155e  push    rbp
0x18000155f  push    rsi
0x180001560  push    rdi
0x180001561  sub     rsp, 28h
0x180001565  mov     rdi, r9
0x180001568  mov     rsi, r8
0x18000156b  mov     ebx, edx
0x18000156d  mov     rbp, rcx
0x180001570  call    __scrt_is_ucrt_dll_in_use
0x180001575  test    eax, eax
0x180001577  jnz     short loc_18000158E
0x180001579  cmp     ebx, 1
0x18000157c  jnz     short loc_18000158E
0x18000157e  mov     r8, rsi
0x180001581  xor     edx, edx
0x180001583  mov     rcx, rbp
0x180001586  mov     rax, rdi
0x180001589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000158e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001593  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001597  add     rsp, 28h
0x18000159b  pop     rdi
0x18000159c  pop     rsi
0x18000159d  pop     rbp
0x18000159e  pop     rbx
0x18000159f  jmp     _o__seh_filter_dll_0
```
