# __scrt_dllmain_exception_filter

- ea: `0x180001d54`
- end: `0x180001d9c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001a24`

## callees

- `0x180001d54`
- `0x1800025f4`
- `0x180002708`
- `0x18002d010`

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
0x180001d54  push    rbx
0x180001d56  push    rbp
0x180001d57  push    rsi
0x180001d58  push    rdi
0x180001d59  sub     rsp, 28h
0x180001d5d  mov     rdi, r9
0x180001d60  mov     rsi, r8
0x180001d63  mov     ebx, edx
0x180001d65  mov     rbp, rcx
0x180001d68  call    __scrt_is_ucrt_dll_in_use
0x180001d6d  test    eax, eax
0x180001d6f  jnz     short loc_180001D86
0x180001d71  cmp     ebx, 1
0x180001d74  jnz     short loc_180001D86
0x180001d76  mov     r8, rsi
0x180001d79  xor     edx, edx
0x180001d7b  mov     rcx, rbp
0x180001d7e  mov     rax, rdi
0x180001d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d86  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001d8b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001d8f  add     rsp, 28h
0x180001d93  pop     rdi
0x180001d94  pop     rsi
0x180001d95  pop     rbp
0x180001d96  pop     rbx
0x180001d97  jmp     _o__seh_filter_dll_0
```
