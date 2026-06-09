# __scrt_dllmain_exception_filter

- ea: `0x18000b50c`
- end: `0x18000b554`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000b274`

## callees

- `0x18000b50c`
- `0x18000bcc8`
- `0x18000be48`
- `0x180015010`

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
0x18000b50c  push    rbx
0x18000b50e  push    rbp
0x18000b50f  push    rsi
0x18000b510  push    rdi
0x18000b511  sub     rsp, 28h
0x18000b515  mov     rdi, r9
0x18000b518  mov     rsi, r8
0x18000b51b  mov     ebx, edx
0x18000b51d  mov     rbp, rcx
0x18000b520  call    __scrt_is_ucrt_dll_in_use
0x18000b525  test    eax, eax
0x18000b527  jnz     short loc_18000B53E
0x18000b529  cmp     ebx, 1
0x18000b52c  jnz     short loc_18000B53E
0x18000b52e  mov     r8, rsi
0x18000b531  xor     edx, edx
0x18000b533  mov     rcx, rbp
0x18000b536  mov     rax, rdi
0x18000b539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b53e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000b543  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000b547  add     rsp, 28h
0x18000b54b  pop     rdi
0x18000b54c  pop     rsi
0x18000b54d  pop     rbp
0x18000b54e  pop     rbx
0x18000b54f  jmp     _o__seh_filter_dll_0
```
