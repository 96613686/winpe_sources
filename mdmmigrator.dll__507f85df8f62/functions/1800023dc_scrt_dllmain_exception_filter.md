# __scrt_dllmain_exception_filter

- ea: `0x1800023dc`
- end: `0x180002424`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002154`

## callees

- `0x1800023dc`
- `0x180002b48`
- `0x180002c68`
- `0x180020010`

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
0x1800023dc  push    rbx
0x1800023de  push    rbp
0x1800023df  push    rsi
0x1800023e0  push    rdi
0x1800023e1  sub     rsp, 28h
0x1800023e5  mov     rdi, r9
0x1800023e8  mov     rsi, r8
0x1800023eb  mov     ebx, edx
0x1800023ed  mov     rbp, rcx
0x1800023f0  call    __scrt_is_ucrt_dll_in_use
0x1800023f5  test    eax, eax
0x1800023f7  jnz     short loc_18000240E
0x1800023f9  cmp     ebx, 1
0x1800023fc  jnz     short loc_18000240E
0x1800023fe  mov     r8, rsi
0x180002401  xor     edx, edx
0x180002403  mov     rcx, rbp
0x180002406  mov     rax, rdi
0x180002409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000240e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002413  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002417  add     rsp, 28h
0x18000241b  pop     rdi
0x18000241c  pop     rsi
0x18000241d  pop     rbp
0x18000241e  pop     rbx
0x18000241f  jmp     _o__seh_filter_dll_0
```
