# __scrt_dllmain_exception_filter

- ea: `0x180002028`
- end: `0x180002070`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001d64`

## callees

- `0x180002028`
- `0x18000279c`
- `0x180002918`
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
  if ( !_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180002028  push    rbx
0x18000202a  push    rbp
0x18000202b  push    rsi
0x18000202c  push    rdi
0x18000202d  sub     rsp, 28h
0x180002031  mov     rdi, r9
0x180002034  mov     rsi, r8
0x180002037  mov     ebx, edx
0x180002039  mov     rbp, rcx
0x18000203c  call    __scrt_is_ucrt_dll_in_use
0x180002041  test    eax, eax
0x180002043  jnz     short loc_18000205A
0x180002045  cmp     ebx, 1
0x180002048  jnz     short loc_18000205A
0x18000204a  mov     r8, rsi
0x18000204d  xor     edx, edx
0x18000204f  mov     rcx, rbp
0x180002052  mov     rax, rdi
0x180002055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000205a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000205f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002063  add     rsp, 28h
0x180002067  pop     rdi
0x180002068  pop     rsi
0x180002069  pop     rbp
0x18000206a  pop     rbx
0x18000206b  jmp     _o__seh_filter_dll_0
```
