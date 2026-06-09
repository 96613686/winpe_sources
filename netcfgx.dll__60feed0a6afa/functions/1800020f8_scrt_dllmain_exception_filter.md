# __scrt_dllmain_exception_filter

- ea: `0x1800020f8`
- end: `0x180002140`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001e04`

## callees

- `0x1800020f8`
- `0x180002924`
- `0x180002a28`
- `0x180013010`

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
0x1800020f8  push    rbx
0x1800020fa  push    rbp
0x1800020fb  push    rsi
0x1800020fc  push    rdi
0x1800020fd  sub     rsp, 28h
0x180002101  mov     rdi, r9
0x180002104  mov     rsi, r8
0x180002107  mov     ebx, edx
0x180002109  mov     rbp, rcx
0x18000210c  call    __scrt_is_ucrt_dll_in_use
0x180002111  test    eax, eax
0x180002113  jnz     short loc_18000212A
0x180002115  cmp     ebx, 1
0x180002118  jnz     short loc_18000212A
0x18000211a  mov     r8, rsi
0x18000211d  xor     edx, edx
0x18000211f  mov     rcx, rbp
0x180002122  mov     rax, rdi
0x180002125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000212a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000212f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002133  add     rsp, 28h
0x180002137  pop     rdi
0x180002138  pop     rsi
0x180002139  pop     rbp
0x18000213a  pop     rbx
0x18000213b  jmp     _o__seh_filter_dll_0
```
