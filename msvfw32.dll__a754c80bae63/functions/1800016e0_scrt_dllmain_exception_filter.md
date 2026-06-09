# __scrt_dllmain_exception_filter

- ea: `0x1800016e0`
- end: `0x180001728`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001324`

## callees

- `0x1800016e0`
- `0x180001c90`
- `0x180001d3e`
- `0x180017010`

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
0x1800016e0  push    rbx
0x1800016e2  push    rbp
0x1800016e3  push    rsi
0x1800016e4  push    rdi
0x1800016e5  sub     rsp, 28h
0x1800016e9  mov     rdi, r9
0x1800016ec  mov     rsi, r8
0x1800016ef  mov     ebx, edx
0x1800016f1  mov     rbp, rcx
0x1800016f4  call    __scrt_is_ucrt_dll_in_use
0x1800016f9  test    eax, eax
0x1800016fb  jnz     short loc_180001712
0x1800016fd  cmp     ebx, 1
0x180001700  jnz     short loc_180001712
0x180001702  mov     r8, rsi
0x180001705  xor     edx, edx
0x180001707  mov     rcx, rbp
0x18000170a  mov     rax, rdi
0x18000170d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001712  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001717  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000171b  add     rsp, 28h
0x18000171f  pop     rdi
0x180001720  pop     rsi
0x180001721  pop     rbp
0x180001722  pop     rbx
0x180001723  jmp     _o__seh_filter_dll_0
```
