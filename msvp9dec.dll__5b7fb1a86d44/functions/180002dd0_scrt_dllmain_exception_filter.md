# __scrt_dllmain_exception_filter

- ea: `0x180002dd0`
- end: `0x180002e18`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002b24`

## callees

- `0x180002dd0`
- `0x18000355c`
- `0x180003848`
- `0x180006010`

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
0x180002dd0  push    rbx
0x180002dd2  push    rbp
0x180002dd3  push    rsi
0x180002dd4  push    rdi
0x180002dd5  sub     rsp, 28h
0x180002dd9  mov     rdi, r9
0x180002ddc  mov     rsi, r8
0x180002ddf  mov     ebx, edx
0x180002de1  mov     rbp, rcx
0x180002de4  call    __scrt_is_ucrt_dll_in_use
0x180002de9  test    eax, eax
0x180002deb  jnz     short loc_180002E02
0x180002ded  cmp     ebx, 1
0x180002df0  jnz     short loc_180002E02
0x180002df2  mov     r8, rsi
0x180002df5  xor     edx, edx
0x180002df7  mov     rcx, rbp
0x180002dfa  mov     rax, rdi
0x180002dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e02  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002e07  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002e0b  add     rsp, 28h
0x180002e0f  pop     rdi
0x180002e10  pop     rsi
0x180002e11  pop     rbp
0x180002e12  pop     rbx
0x180002e13  jmp     _o__seh_filter_dll_0
```
