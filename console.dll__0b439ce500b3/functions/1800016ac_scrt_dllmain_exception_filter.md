# __scrt_dllmain_exception_filter

- ea: `0x1800016ac`
- end: `0x1800016f4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001424`

## callees

- `0x1800016ac`
- `0x180001eb8`
- `0x180002058`
- `0x18001a010`

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
0x1800016ac  push    rbx
0x1800016ae  push    rbp
0x1800016af  push    rsi
0x1800016b0  push    rdi
0x1800016b1  sub     rsp, 28h
0x1800016b5  mov     rdi, r9
0x1800016b8  mov     rsi, r8
0x1800016bb  mov     ebx, edx
0x1800016bd  mov     rbp, rcx
0x1800016c0  call    __scrt_is_ucrt_dll_in_use
0x1800016c5  test    eax, eax
0x1800016c7  jnz     short loc_1800016DE
0x1800016c9  cmp     ebx, 1
0x1800016cc  jnz     short loc_1800016DE
0x1800016ce  mov     r8, rsi
0x1800016d1  xor     edx, edx
0x1800016d3  mov     rcx, rbp
0x1800016d6  mov     rax, rdi
0x1800016d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016de  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800016e3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800016e7  add     rsp, 28h
0x1800016eb  pop     rdi
0x1800016ec  pop     rsi
0x1800016ed  pop     rbp
0x1800016ee  pop     rbx
0x1800016ef  jmp     _o__seh_filter_dll_0
```
