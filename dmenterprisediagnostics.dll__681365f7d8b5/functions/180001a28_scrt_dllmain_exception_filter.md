# __scrt_dllmain_exception_filter

- ea: `0x180001a28`
- end: `0x180001a70`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001674`

## callees

- `0x180001a28`
- `0x18000223c`
- `0x180002368`
- `0x180027010`

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
0x180001a28  push    rbx
0x180001a2a  push    rbp
0x180001a2b  push    rsi
0x180001a2c  push    rdi
0x180001a2d  sub     rsp, 28h
0x180001a31  mov     rdi, r9
0x180001a34  mov     rsi, r8
0x180001a37  mov     ebx, edx
0x180001a39  mov     rbp, rcx
0x180001a3c  call    __scrt_is_ucrt_dll_in_use
0x180001a41  test    eax, eax
0x180001a43  jnz     short loc_180001A5A
0x180001a45  cmp     ebx, 1
0x180001a48  jnz     short loc_180001A5A
0x180001a4a  mov     r8, rsi
0x180001a4d  xor     edx, edx
0x180001a4f  mov     rcx, rbp
0x180001a52  mov     rax, rdi
0x180001a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a5a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001a5f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001a63  add     rsp, 28h
0x180001a67  pop     rdi
0x180001a68  pop     rsi
0x180001a69  pop     rbp
0x180001a6a  pop     rbx
0x180001a6b  jmp     _o__seh_filter_dll_0
```
