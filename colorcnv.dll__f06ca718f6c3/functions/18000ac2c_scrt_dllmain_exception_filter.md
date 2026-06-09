# __scrt_dllmain_exception_filter

- ea: `0x18000ac2c`
- end: `0x18000ac74`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000a9a4`

## callees

- `0x18000ac2c`
- `0x18000b368`
- `0x18000b438`
- `0x18002b010`

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
0x18000ac2c  push    rbx
0x18000ac2e  push    rbp
0x18000ac2f  push    rsi
0x18000ac30  push    rdi
0x18000ac31  sub     rsp, 28h
0x18000ac35  mov     rdi, r9
0x18000ac38  mov     rsi, r8
0x18000ac3b  mov     ebx, edx
0x18000ac3d  mov     rbp, rcx
0x18000ac40  call    __scrt_is_ucrt_dll_in_use
0x18000ac45  test    eax, eax
0x18000ac47  jnz     short loc_18000AC5E
0x18000ac49  cmp     ebx, 1
0x18000ac4c  jnz     short loc_18000AC5E
0x18000ac4e  mov     r8, rsi
0x18000ac51  xor     edx, edx
0x18000ac53  mov     rcx, rbp
0x18000ac56  mov     rax, rdi
0x18000ac59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac5e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000ac63  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000ac67  add     rsp, 28h
0x18000ac6b  pop     rdi
0x18000ac6c  pop     rsi
0x18000ac6d  pop     rbp
0x18000ac6e  pop     rbx
0x18000ac6f  jmp     _o__seh_filter_dll_0
```
