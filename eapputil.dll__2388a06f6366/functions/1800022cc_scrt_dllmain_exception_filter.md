# __scrt_dllmain_exception_filter

- ea: `0x1800022cc`
- end: `0x180002314`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002044`

## callees

- `0x1800022cc`
- `0x180002a38`
- `0x180002b48`
- `0x180033010`

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
0x1800022cc  push    rbx
0x1800022ce  push    rbp
0x1800022cf  push    rsi
0x1800022d0  push    rdi
0x1800022d1  sub     rsp, 28h
0x1800022d5  mov     rdi, r9
0x1800022d8  mov     rsi, r8
0x1800022db  mov     ebx, edx
0x1800022dd  mov     rbp, rcx
0x1800022e0  call    __scrt_is_ucrt_dll_in_use
0x1800022e5  test    eax, eax
0x1800022e7  jnz     short loc_1800022FE
0x1800022e9  cmp     ebx, 1
0x1800022ec  jnz     short loc_1800022FE
0x1800022ee  mov     r8, rsi
0x1800022f1  xor     edx, edx
0x1800022f3  mov     rcx, rbp
0x1800022f6  mov     rax, rdi
0x1800022f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022fe  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002303  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002307  add     rsp, 28h
0x18000230b  pop     rdi
0x18000230c  pop     rsi
0x18000230d  pop     rbp
0x18000230e  pop     rbx
0x18000230f  jmp     _o__seh_filter_dll_0
```
