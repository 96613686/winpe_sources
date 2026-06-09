# __scrt_dllmain_exception_filter

- ea: `0x180001720`
- end: `0x180001768`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001364`

## callees

- `0x180001720`
- `0x180001cd0`
- `0x180001d46`
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
0x180001720  push    rbx
0x180001722  push    rbp
0x180001723  push    rsi
0x180001724  push    rdi
0x180001725  sub     rsp, 28h
0x180001729  mov     rdi, r9
0x18000172c  mov     rsi, r8
0x18000172f  mov     ebx, edx
0x180001731  mov     rbp, rcx
0x180001734  call    __scrt_is_ucrt_dll_in_use
0x180001739  test    eax, eax
0x18000173b  jnz     short loc_180001752
0x18000173d  cmp     ebx, 1
0x180001740  jnz     short loc_180001752
0x180001742  mov     r8, rsi
0x180001745  xor     edx, edx
0x180001747  mov     rcx, rbp
0x18000174a  mov     rax, rdi
0x18000174d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001752  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001757  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000175b  add     rsp, 28h
0x18000175f  pop     rdi
0x180001760  pop     rsi
0x180001761  pop     rbp
0x180001762  pop     rbx
0x180001763  jmp     _o__seh_filter_dll_0
```
