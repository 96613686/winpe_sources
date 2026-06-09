# __scrt_dllmain_exception_filter

- ea: `0x180004e44`
- end: `0x180004e8c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004ab4`

## callees

- `0x180004e44`
- `0x180005418`
- `0x1800054a6`
- `0x180009010`

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
0x180004e44  push    rbx
0x180004e46  push    rbp
0x180004e47  push    rsi
0x180004e48  push    rdi
0x180004e49  sub     rsp, 28h
0x180004e4d  mov     rdi, r9
0x180004e50  mov     rsi, r8
0x180004e53  mov     ebx, edx
0x180004e55  mov     rbp, rcx
0x180004e58  call    __scrt_is_ucrt_dll_in_use
0x180004e5d  test    eax, eax
0x180004e5f  jnz     short loc_180004E76
0x180004e61  cmp     ebx, 1
0x180004e64  jnz     short loc_180004E76
0x180004e66  mov     r8, rsi
0x180004e69  xor     edx, edx
0x180004e6b  mov     rcx, rbp
0x180004e6e  mov     rax, rdi
0x180004e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e76  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180004e7b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180004e7f  add     rsp, 28h
0x180004e83  pop     rdi
0x180004e84  pop     rsi
0x180004e85  pop     rbp
0x180004e86  pop     rbx
0x180004e87  jmp     _o__seh_filter_dll_0
```
