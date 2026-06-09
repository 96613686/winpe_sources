# __scrt_dllmain_exception_filter

- ea: `0x18000205c`
- end: `0x1800020a4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001dd4`

## callees

- `0x18000205c`
- `0x1800027bc`
- `0x1800028b8`
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
  if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x18000205c  push    rbx
0x18000205e  push    rbp
0x18000205f  push    rsi
0x180002060  push    rdi
0x180002061  sub     rsp, 28h
0x180002065  mov     rdi, r9
0x180002068  mov     rsi, r8
0x18000206b  mov     ebx, edx
0x18000206d  mov     rbp, rcx
0x180002070  call    __scrt_is_ucrt_dll_in_use
0x180002075  test    eax, eax
0x180002077  jnz     short loc_18000208E
0x180002079  cmp     ebx, 1
0x18000207c  jnz     short loc_18000208E
0x18000207e  mov     r8, rsi
0x180002081  xor     edx, edx
0x180002083  mov     rcx, rbp
0x180002086  mov     rax, rdi
0x180002089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000208e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002093  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002097  add     rsp, 28h
0x18000209b  pop     rdi
0x18000209c  pop     rsi
0x18000209d  pop     rbp
0x18000209e  pop     rbx
0x18000209f  jmp     _o__seh_filter_dll_0
```
