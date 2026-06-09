# __scrt_dllmain_exception_filter

- ea: `0x1800017cc`
- end: `0x180001814`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001544`

## callees

- `0x1800017cc`
- `0x180002084`
- `0x180002178`
- `0x180022010`

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
0x1800017cc  push    rbx
0x1800017ce  push    rbp
0x1800017cf  push    rsi
0x1800017d0  push    rdi
0x1800017d1  sub     rsp, 28h
0x1800017d5  mov     rdi, r9
0x1800017d8  mov     rsi, r8
0x1800017db  mov     ebx, edx
0x1800017dd  mov     rbp, rcx
0x1800017e0  call    __scrt_is_ucrt_dll_in_use
0x1800017e5  test    eax, eax
0x1800017e7  jnz     short loc_1800017FE
0x1800017e9  cmp     ebx, 1
0x1800017ec  jnz     short loc_1800017FE
0x1800017ee  mov     r8, rsi
0x1800017f1  xor     edx, edx
0x1800017f3  mov     rcx, rbp
0x1800017f6  mov     rax, rdi
0x1800017f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017fe  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001803  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001807  add     rsp, 28h
0x18000180b  pop     rdi
0x18000180c  pop     rsi
0x18000180d  pop     rbp
0x18000180e  pop     rbx
0x18000180f  jmp     _o__seh_filter_dll_0
```
