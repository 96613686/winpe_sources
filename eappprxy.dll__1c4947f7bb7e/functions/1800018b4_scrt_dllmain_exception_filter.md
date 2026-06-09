# __scrt_dllmain_exception_filter

- ea: `0x1800018b4`
- end: `0x1800018fc`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800015f4`

## callees

- `0x1800018b4`
- `0x180001fe8`
- `0x1800020ee`
- `0x18000f010`

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
0x1800018b4  push    rbx
0x1800018b6  push    rbp
0x1800018b7  push    rsi
0x1800018b8  push    rdi
0x1800018b9  sub     rsp, 28h
0x1800018bd  mov     rdi, r9
0x1800018c0  mov     rsi, r8
0x1800018c3  mov     ebx, edx
0x1800018c5  mov     rbp, rcx
0x1800018c8  call    __scrt_is_ucrt_dll_in_use
0x1800018cd  test    eax, eax
0x1800018cf  jnz     short loc_1800018E6
0x1800018d1  cmp     ebx, 1
0x1800018d4  jnz     short loc_1800018E6
0x1800018d6  mov     r8, rsi
0x1800018d9  xor     edx, edx
0x1800018db  mov     rcx, rbp
0x1800018de  mov     rax, rdi
0x1800018e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018e6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800018eb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800018ef  add     rsp, 28h
0x1800018f3  pop     rdi
0x1800018f4  pop     rsi
0x1800018f5  pop     rbp
0x1800018f6  pop     rbx
0x1800018f7  jmp     _o__seh_filter_dll_0
```
