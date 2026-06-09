# __scrt_dllmain_exception_filter

- ea: `0x18000128c`
- end: `0x1800012d4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002514`

## callees

- `0x18000128c`
- `0x1800018a0`
- `0x18000193e`
- `0x18000c010`

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
0x18000128c  push    rbx
0x18000128e  push    rbp
0x18000128f  push    rsi
0x180001290  push    rdi
0x180001291  sub     rsp, 28h
0x180001295  mov     rdi, r9
0x180001298  mov     rsi, r8
0x18000129b  mov     ebx, edx
0x18000129d  mov     rbp, rcx
0x1800012a0  call    __scrt_is_ucrt_dll_in_use
0x1800012a5  test    eax, eax
0x1800012a7  jnz     short loc_1800012BE
0x1800012a9  cmp     ebx, 1
0x1800012ac  jnz     short loc_1800012BE
0x1800012ae  mov     r8, rsi
0x1800012b1  xor     edx, edx
0x1800012b3  mov     rcx, rbp
0x1800012b6  mov     rax, rdi
0x1800012b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012be  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800012c3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800012c7  add     rsp, 28h
0x1800012cb  pop     rdi
0x1800012cc  pop     rsi
0x1800012cd  pop     rbp
0x1800012ce  pop     rbx
0x1800012cf  jmp     _o__seh_filter_dll_0
```
