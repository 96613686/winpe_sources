# __scrt_dllmain_exception_filter

- ea: `0x180001e08`
- end: `0x180001e50`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001b64`

## callees

- `0x180001e08`
- `0x1800025b8`
- `0x1800026fe`
- `0x18000d010`

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
0x180001e08  push    rbx
0x180001e0a  push    rbp
0x180001e0b  push    rsi
0x180001e0c  push    rdi
0x180001e0d  sub     rsp, 28h
0x180001e11  mov     rdi, r9
0x180001e14  mov     rsi, r8
0x180001e17  mov     ebx, edx
0x180001e19  mov     rbp, rcx
0x180001e1c  call    __scrt_is_ucrt_dll_in_use
0x180001e21  test    eax, eax
0x180001e23  jnz     short loc_180001E3A
0x180001e25  cmp     ebx, 1
0x180001e28  jnz     short loc_180001E3A
0x180001e2a  mov     r8, rsi
0x180001e2d  xor     edx, edx
0x180001e2f  mov     rcx, rbp
0x180001e32  mov     rax, rdi
0x180001e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e3a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001e3f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001e43  add     rsp, 28h
0x180001e47  pop     rdi
0x180001e48  pop     rsi
0x180001e49  pop     rbp
0x180001e4a  pop     rbx
0x180001e4b  jmp     _o__seh_filter_dll_0
```
