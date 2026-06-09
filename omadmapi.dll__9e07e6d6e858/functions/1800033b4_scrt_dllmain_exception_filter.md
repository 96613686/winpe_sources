# __scrt_dllmain_exception_filter

- ea: `0x1800033b4`
- end: `0x1800033fc`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003024`

## callees

- `0x1800033b4`
- `0x180003be0`
- `0x180003d58`
- `0x180024010`

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
0x1800033b4  push    rbx
0x1800033b6  push    rbp
0x1800033b7  push    rsi
0x1800033b8  push    rdi
0x1800033b9  sub     rsp, 28h
0x1800033bd  mov     rdi, r9
0x1800033c0  mov     rsi, r8
0x1800033c3  mov     ebx, edx
0x1800033c5  mov     rbp, rcx
0x1800033c8  call    __scrt_is_ucrt_dll_in_use
0x1800033cd  test    eax, eax
0x1800033cf  jnz     short loc_1800033E6
0x1800033d1  cmp     ebx, 1
0x1800033d4  jnz     short loc_1800033E6
0x1800033d6  mov     r8, rsi
0x1800033d9  xor     edx, edx
0x1800033db  mov     rcx, rbp
0x1800033de  mov     rax, rdi
0x1800033e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800033eb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800033ef  add     rsp, 28h
0x1800033f3  pop     rdi
0x1800033f4  pop     rsi
0x1800033f5  pop     rbp
0x1800033f6  pop     rbx
0x1800033f7  jmp     _o__seh_filter_dll_0
```
