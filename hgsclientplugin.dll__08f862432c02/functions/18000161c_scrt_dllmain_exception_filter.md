# __scrt_dllmain_exception_filter

- ea: `0x18000161c`
- end: `0x180001664`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001394`

## callees

- `0x18000161c`
- `0x180001e08`
- `0x180001f6e`
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
  if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x18000161c  push    rbx
0x18000161e  push    rbp
0x18000161f  push    rsi
0x180001620  push    rdi
0x180001621  sub     rsp, 28h
0x180001625  mov     rdi, r9
0x180001628  mov     rsi, r8
0x18000162b  mov     ebx, edx
0x18000162d  mov     rbp, rcx
0x180001630  call    __scrt_is_ucrt_dll_in_use
0x180001635  test    eax, eax
0x180001637  jnz     short loc_18000164E
0x180001639  cmp     ebx, 1
0x18000163c  jnz     short loc_18000164E
0x18000163e  mov     r8, rsi
0x180001641  xor     edx, edx
0x180001643  mov     rcx, rbp
0x180001646  mov     rax, rdi
0x180001649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000164e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001653  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001657  add     rsp, 28h
0x18000165b  pop     rdi
0x18000165c  pop     rsi
0x18000165d  pop     rbp
0x18000165e  pop     rbx
0x18000165f  jmp     _o__seh_filter_dll_0
```
