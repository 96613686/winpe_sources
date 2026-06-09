# __scrt_dllmain_exception_filter

- ea: `0x18002047c`
- end: `0x1800204c4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800200c4`

## callees

- `0x18002047c`
- `0x180020a30`
- `0x180020ac6`
- `0x180030010`

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
0x18002047c  push    rbx
0x18002047e  push    rbp
0x18002047f  push    rsi
0x180020480  push    rdi
0x180020481  sub     rsp, 28h
0x180020485  mov     rdi, r9
0x180020488  mov     rsi, r8
0x18002048b  mov     ebx, edx
0x18002048d  mov     rbp, rcx
0x180020490  call    __scrt_is_ucrt_dll_in_use
0x180020495  test    eax, eax
0x180020497  jnz     short loc_1800204AE
0x180020499  cmp     ebx, 1
0x18002049c  jnz     short loc_1800204AE
0x18002049e  mov     r8, rsi
0x1800204a1  xor     edx, edx
0x1800204a3  mov     rcx, rbp
0x1800204a6  mov     rax, rdi
0x1800204a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204ae  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800204b3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800204b7  add     rsp, 28h
0x1800204bb  pop     rdi
0x1800204bc  pop     rsi
0x1800204bd  pop     rbp
0x1800204be  pop     rbx
0x1800204bf  jmp     _o__seh_filter_dll_0
```
