# __scrt_dllmain_exception_filter

- ea: `0x1800016cc`
- end: `0x180001714`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001444`

## callees

- `0x1800016cc`
- `0x180001e18`
- `0x180001ed8`
- `0x180010010`

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
0x1800016cc  push    rbx
0x1800016ce  push    rbp
0x1800016cf  push    rsi
0x1800016d0  push    rdi
0x1800016d1  sub     rsp, 28h
0x1800016d5  mov     rdi, r9
0x1800016d8  mov     rsi, r8
0x1800016db  mov     ebx, edx
0x1800016dd  mov     rbp, rcx
0x1800016e0  call    __scrt_is_ucrt_dll_in_use
0x1800016e5  test    eax, eax
0x1800016e7  jnz     short loc_1800016FE
0x1800016e9  cmp     ebx, 1
0x1800016ec  jnz     short loc_1800016FE
0x1800016ee  mov     r8, rsi
0x1800016f1  xor     edx, edx
0x1800016f3  mov     rcx, rbp
0x1800016f6  mov     rax, rdi
0x1800016f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016fe  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001703  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001707  add     rsp, 28h
0x18000170b  pop     rdi
0x18000170c  pop     rsi
0x18000170d  pop     rbp
0x18000170e  pop     rbx
0x18000170f  jmp     _o__seh_filter_dll_0
```
