# __scrt_dllmain_exception_filter

- ea: `0x180001620`
- end: `0x180001668`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001274`

## callees

- `0x180001620`
- `0x180001bd0`
- `0x180001c66`
- `0x180009010`

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
0x180001620  push    rbx
0x180001622  push    rbp
0x180001623  push    rsi
0x180001624  push    rdi
0x180001625  sub     rsp, 28h
0x180001629  mov     rdi, r9
0x18000162c  mov     rsi, r8
0x18000162f  mov     ebx, edx
0x180001631  mov     rbp, rcx
0x180001634  call    __scrt_is_ucrt_dll_in_use
0x180001639  test    eax, eax
0x18000163b  jnz     short loc_180001652
0x18000163d  cmp     ebx, 1
0x180001640  jnz     short loc_180001652
0x180001642  mov     r8, rsi
0x180001645  xor     edx, edx
0x180001647  mov     rcx, rbp
0x18000164a  mov     rax, rdi
0x18000164d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001652  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001657  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000165b  add     rsp, 28h
0x18000165f  pop     rdi
0x180001660  pop     rsi
0x180001661  pop     rbp
0x180001662  pop     rbx
0x180001663  jmp     _o__seh_filter_dll_0
```
