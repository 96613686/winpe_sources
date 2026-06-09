# __scrt_dllmain_exception_filter

- ea: `0x180001ca4`
- end: `0x180001cec`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001914`

## callees

- `0x180001ca4`
- `0x180002278`
- `0x180002306`
- `0x18001e010`

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
0x180001ca4  push    rbx
0x180001ca6  push    rbp
0x180001ca7  push    rsi
0x180001ca8  push    rdi
0x180001ca9  sub     rsp, 28h
0x180001cad  mov     rdi, r9
0x180001cb0  mov     rsi, r8
0x180001cb3  mov     ebx, edx
0x180001cb5  mov     rbp, rcx
0x180001cb8  call    __scrt_is_ucrt_dll_in_use
0x180001cbd  test    eax, eax
0x180001cbf  jnz     short loc_180001CD6
0x180001cc1  cmp     ebx, 1
0x180001cc4  jnz     short loc_180001CD6
0x180001cc6  mov     r8, rsi
0x180001cc9  xor     edx, edx
0x180001ccb  mov     rcx, rbp
0x180001cce  mov     rax, rdi
0x180001cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cd6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001cdb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001cdf  add     rsp, 28h
0x180001ce3  pop     rdi
0x180001ce4  pop     rsi
0x180001ce5  pop     rbp
0x180001ce6  pop     rbx
0x180001ce7  jmp     _o__seh_filter_dll_0
```
