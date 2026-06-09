# __scrt_dllmain_exception_filter

- ea: `0x180009514`
- end: `0x18000955c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180009184`

## callees

- `0x180009514`
- `0x180009ae8`
- `0x180009b72`
- `0x18000b010`

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
0x180009514  push    rbx
0x180009516  push    rbp
0x180009517  push    rsi
0x180009518  push    rdi
0x180009519  sub     rsp, 28h
0x18000951d  mov     rdi, r9
0x180009520  mov     rsi, r8
0x180009523  mov     ebx, edx
0x180009525  mov     rbp, rcx
0x180009528  call    __scrt_is_ucrt_dll_in_use
0x18000952d  test    eax, eax
0x18000952f  jnz     short loc_180009546
0x180009531  cmp     ebx, 1
0x180009534  jnz     short loc_180009546
0x180009536  mov     r8, rsi
0x180009539  xor     edx, edx
0x18000953b  mov     rcx, rbp
0x18000953e  mov     rax, rdi
0x180009541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009546  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000954b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000954f  add     rsp, 28h
0x180009553  pop     rdi
0x180009554  pop     rsi
0x180009555  pop     rbp
0x180009556  pop     rbx
0x180009557  jmp     _o__seh_filter_dll_0
```
