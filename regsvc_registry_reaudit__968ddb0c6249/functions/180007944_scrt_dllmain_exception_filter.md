# __scrt_dllmain_exception_filter

- ea: `0x180007944`
- end: `0x18000798c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800075b4`

## callees

- `0x180007944`
- `0x180007f18`
- `0x180007fe2`
- `0x18001f010`

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
0x180007944  push    rbx
0x180007946  push    rbp
0x180007947  push    rsi
0x180007948  push    rdi
0x180007949  sub     rsp, 28h
0x18000794d  mov     rdi, r9
0x180007950  mov     rsi, r8
0x180007953  mov     ebx, edx
0x180007955  mov     rbp, rcx
0x180007958  call    __scrt_is_ucrt_dll_in_use
0x18000795d  test    eax, eax
0x18000795f  jnz     short loc_180007976
0x180007961  cmp     ebx, 1
0x180007964  jnz     short loc_180007976
0x180007966  mov     r8, rsi
0x180007969  xor     edx, edx
0x18000796b  mov     rcx, rbp
0x18000796e  mov     rax, rdi
0x180007971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007976  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000797b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000797f  add     rsp, 28h
0x180007983  pop     rdi
0x180007984  pop     rsi
0x180007985  pop     rbp
0x180007986  pop     rbx
0x180007987  jmp     _o__seh_filter_dll_0
```
