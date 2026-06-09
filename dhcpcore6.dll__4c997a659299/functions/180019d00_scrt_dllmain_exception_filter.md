# __scrt_dllmain_exception_filter

- ea: `0x180019d00`
- end: `0x180019d48`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180019944`

## callees

- `0x180019d00`
- `0x18001a310`
- `0x18001a3e2`
- `0x180035010`

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
0x180019d00  push    rbx
0x180019d02  push    rbp
0x180019d03  push    rsi
0x180019d04  push    rdi
0x180019d05  sub     rsp, 28h
0x180019d09  mov     rdi, r9
0x180019d0c  mov     rsi, r8
0x180019d0f  mov     ebx, edx
0x180019d11  mov     rbp, rcx
0x180019d14  call    __scrt_is_ucrt_dll_in_use
0x180019d19  test    eax, eax
0x180019d1b  jnz     short loc_180019D32
0x180019d1d  cmp     ebx, 1
0x180019d20  jnz     short loc_180019D32
0x180019d22  mov     r8, rsi
0x180019d25  xor     edx, edx
0x180019d27  mov     rcx, rbp
0x180019d2a  mov     rax, rdi
0x180019d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d32  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180019d37  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180019d3b  add     rsp, 28h
0x180019d3f  pop     rdi
0x180019d40  pop     rsi
0x180019d41  pop     rbp
0x180019d42  pop     rbx
0x180019d43  jmp     _o__seh_filter_dll_0
```
