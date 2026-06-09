# __scrt_dllmain_exception_filter

- ea: `0x180001f78`
- end: `0x180001fc0`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001cd4`

## callees

- `0x180001f78`
- `0x1800026f8`
- `0x1800028b8`
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
  if ( !_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180001f78  push    rbx
0x180001f7a  push    rbp
0x180001f7b  push    rsi
0x180001f7c  push    rdi
0x180001f7d  sub     rsp, 28h
0x180001f81  mov     rdi, r9
0x180001f84  mov     rsi, r8
0x180001f87  mov     ebx, edx
0x180001f89  mov     rbp, rcx
0x180001f8c  call    __scrt_is_ucrt_dll_in_use
0x180001f91  test    eax, eax
0x180001f93  jnz     short loc_180001FAA
0x180001f95  cmp     ebx, 1
0x180001f98  jnz     short loc_180001FAA
0x180001f9a  mov     r8, rsi
0x180001f9d  xor     edx, edx
0x180001f9f  mov     rcx, rbp
0x180001fa2  mov     rax, rdi
0x180001fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001faa  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001faf  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001fb3  add     rsp, 28h
0x180001fb7  pop     rdi
0x180001fb8  pop     rsi
0x180001fb9  pop     rbp
0x180001fba  pop     rbx
0x180001fbb  jmp     _o__seh_filter_dll_0
```
