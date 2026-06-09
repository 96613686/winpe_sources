# __scrt_dllmain_exception_filter

- ea: `0x180001b58`
- end: `0x180001ba0`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800018c4`

## callees

- `0x180001b58`
- `0x180002314`
- `0x1800024a8`
- `0x180012010`

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
0x180001b58  push    rbx
0x180001b5a  push    rbp
0x180001b5b  push    rsi
0x180001b5c  push    rdi
0x180001b5d  sub     rsp, 28h
0x180001b61  mov     rdi, r9
0x180001b64  mov     rsi, r8
0x180001b67  mov     ebx, edx
0x180001b69  mov     rbp, rcx
0x180001b6c  call    __scrt_is_ucrt_dll_in_use
0x180001b71  test    eax, eax
0x180001b73  jnz     short loc_180001B8A
0x180001b75  cmp     ebx, 1
0x180001b78  jnz     short loc_180001B8A
0x180001b7a  mov     r8, rsi
0x180001b7d  xor     edx, edx
0x180001b7f  mov     rcx, rbp
0x180001b82  mov     rax, rdi
0x180001b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b8a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001b8f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001b93  add     rsp, 28h
0x180001b97  pop     rdi
0x180001b98  pop     rsi
0x180001b99  pop     rbp
0x180001b9a  pop     rbx
0x180001b9b  jmp     _o__seh_filter_dll_0
```
