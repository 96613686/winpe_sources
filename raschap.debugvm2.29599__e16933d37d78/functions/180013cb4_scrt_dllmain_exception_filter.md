# __scrt_dllmain_exception_filter

- ea: `0x180013cb4`
- end: `0x180013cfc`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180013994`

## callees

- `0x180013cb4`
- `0x1800144a0`
- `0x1800145c8`
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
0x180013cb4  push    rbx
0x180013cb6  push    rbp
0x180013cb7  push    rsi
0x180013cb8  push    rdi
0x180013cb9  sub     rsp, 28h
0x180013cbd  mov     rdi, r9
0x180013cc0  mov     rsi, r8
0x180013cc3  mov     ebx, edx
0x180013cc5  mov     rbp, rcx
0x180013cc8  call    __scrt_is_ucrt_dll_in_use
0x180013ccd  test    eax, eax
0x180013ccf  jnz     short loc_180013CE6
0x180013cd1  cmp     ebx, 1
0x180013cd4  jnz     short loc_180013CE6
0x180013cd6  mov     r8, rsi
0x180013cd9  xor     edx, edx
0x180013cdb  mov     rcx, rbp
0x180013cde  mov     rax, rdi
0x180013ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ce6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180013ceb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180013cef  add     rsp, 28h
0x180013cf3  pop     rdi
0x180013cf4  pop     rsi
0x180013cf5  pop     rbp
0x180013cf6  pop     rbx
0x180013cf7  jmp     _o__seh_filter_dll_0
```
