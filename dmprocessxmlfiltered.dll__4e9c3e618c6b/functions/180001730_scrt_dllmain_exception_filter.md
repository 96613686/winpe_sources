# __scrt_dllmain_exception_filter

- ea: `0x180001730`
- end: `0x180001778`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001394`

## callees

- `0x180001730`
- `0x180001d4c`
- `0x180001e36`
- `0x180008010`

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
0x180001730  push    rbx
0x180001732  push    rbp
0x180001733  push    rsi
0x180001734  push    rdi
0x180001735  sub     rsp, 28h
0x180001739  mov     rdi, r9
0x18000173c  mov     rsi, r8
0x18000173f  mov     ebx, edx
0x180001741  mov     rbp, rcx
0x180001744  call    __scrt_is_ucrt_dll_in_use
0x180001749  test    eax, eax
0x18000174b  jnz     short loc_180001762
0x18000174d  cmp     ebx, 1
0x180001750  jnz     short loc_180001762
0x180001752  mov     r8, rsi
0x180001755  xor     edx, edx
0x180001757  mov     rcx, rbp
0x18000175a  mov     rax, rdi
0x18000175d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001762  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001767  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000176b  add     rsp, 28h
0x18000176f  pop     rdi
0x180001770  pop     rsi
0x180001771  pop     rbp
0x180001772  pop     rbx
0x180001773  jmp     _o__seh_filter_dll_0
```
