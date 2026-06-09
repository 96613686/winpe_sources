# __scrt_dllmain_exception_filter

- ea: `0x180001844`
- end: `0x18000188c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800014b4`

## callees

- `0x180001844`
- `0x180001e6c`
- `0x180001f48`
- `0x180028010`

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
0x180001844  push    rbx
0x180001846  push    rbp
0x180001847  push    rsi
0x180001848  push    rdi
0x180001849  sub     rsp, 28h
0x18000184d  mov     rdi, r9
0x180001850  mov     rsi, r8
0x180001853  mov     ebx, edx
0x180001855  mov     rbp, rcx
0x180001858  call    __scrt_is_ucrt_dll_in_use
0x18000185d  test    eax, eax
0x18000185f  jnz     short loc_180001876
0x180001861  cmp     ebx, 1
0x180001864  jnz     short loc_180001876
0x180001866  mov     r8, rsi
0x180001869  xor     edx, edx
0x18000186b  mov     rcx, rbp
0x18000186e  mov     rax, rdi
0x180001871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001876  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000187b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000187f  add     rsp, 28h
0x180001883  pop     rdi
0x180001884  pop     rsi
0x180001885  pop     rbp
0x180001886  pop     rbx
0x180001887  jmp     _o__seh_filter_dll_0
```
