# __scrt_dllmain_exception_filter

- ea: `0x18000fb0c`
- end: `0x18000fb54`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000f884`

## callees

- `0x18000fb0c`
- `0x180010278`
- `0x180010378`
- `0x180018010`

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
0x18000fb0c  push    rbx
0x18000fb0e  push    rbp
0x18000fb0f  push    rsi
0x18000fb10  push    rdi
0x18000fb11  sub     rsp, 28h
0x18000fb15  mov     rdi, r9
0x18000fb18  mov     rsi, r8
0x18000fb1b  mov     ebx, edx
0x18000fb1d  mov     rbp, rcx
0x18000fb20  call    __scrt_is_ucrt_dll_in_use
0x18000fb25  test    eax, eax
0x18000fb27  jnz     short loc_18000FB3E
0x18000fb29  cmp     ebx, 1
0x18000fb2c  jnz     short loc_18000FB3E
0x18000fb2e  mov     r8, rsi
0x18000fb31  xor     edx, edx
0x18000fb33  mov     rcx, rbp
0x18000fb36  mov     rax, rdi
0x18000fb39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb3e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000fb43  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000fb47  add     rsp, 28h
0x18000fb4b  pop     rdi
0x18000fb4c  pop     rsi
0x18000fb4d  pop     rbp
0x18000fb4e  pop     rbx
0x18000fb4f  jmp     _o__seh_filter_dll_0
```
