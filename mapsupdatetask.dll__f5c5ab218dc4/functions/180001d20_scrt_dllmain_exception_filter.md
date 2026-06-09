# __scrt_dllmain_exception_filter

- ea: `0x180001d20`
- end: `0x180001d68`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001a54`

## callees

- `0x180001d20`
- `0x180002500`
- `0x1800025e2`
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
  if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180001d20  push    rbx
0x180001d22  push    rbp
0x180001d23  push    rsi
0x180001d24  push    rdi
0x180001d25  sub     rsp, 28h
0x180001d29  mov     rdi, r9
0x180001d2c  mov     rsi, r8
0x180001d2f  mov     ebx, edx
0x180001d31  mov     rbp, rcx
0x180001d34  call    __scrt_is_ucrt_dll_in_use
0x180001d39  test    eax, eax
0x180001d3b  jnz     short loc_180001D52
0x180001d3d  cmp     ebx, 1
0x180001d40  jnz     short loc_180001D52
0x180001d42  mov     r8, rsi
0x180001d45  xor     edx, edx
0x180001d47  mov     rcx, rbp
0x180001d4a  mov     rax, rdi
0x180001d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d52  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001d57  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001d5b  add     rsp, 28h
0x180001d5f  pop     rdi
0x180001d60  pop     rsi
0x180001d61  pop     rbp
0x180001d62  pop     rbx
0x180001d63  jmp     _o__seh_filter_dll_0
```
