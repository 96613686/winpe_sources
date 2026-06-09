# __scrt_dllmain_exception_filter

- ea: `0x180003c94`
- end: `0x180003cdc`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003904`

## callees

- `0x180003c94`
- `0x180004268`
- `0x1800042f2`
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
0x180003c94  push    rbx
0x180003c96  push    rbp
0x180003c97  push    rsi
0x180003c98  push    rdi
0x180003c99  sub     rsp, 28h
0x180003c9d  mov     rdi, r9
0x180003ca0  mov     rsi, r8
0x180003ca3  mov     ebx, edx
0x180003ca5  mov     rbp, rcx
0x180003ca8  call    __scrt_is_ucrt_dll_in_use
0x180003cad  test    eax, eax
0x180003caf  jnz     short loc_180003CC6
0x180003cb1  cmp     ebx, 1
0x180003cb4  jnz     short loc_180003CC6
0x180003cb6  mov     r8, rsi
0x180003cb9  xor     edx, edx
0x180003cbb  mov     rcx, rbp
0x180003cbe  mov     rax, rdi
0x180003cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cc6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180003ccb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180003ccf  add     rsp, 28h
0x180003cd3  pop     rdi
0x180003cd4  pop     rsi
0x180003cd5  pop     rbp
0x180003cd6  pop     rbx
0x180003cd7  jmp     _o__seh_filter_dll_0
```
