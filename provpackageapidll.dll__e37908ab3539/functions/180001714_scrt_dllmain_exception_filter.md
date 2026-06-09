# __scrt_dllmain_exception_filter

- ea: `0x180001714`
- end: `0x18000175c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001384`

## callees

- `0x180001714`
- `0x180001d48`
- `0x180001e36`
- `0x180019010`

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
0x180001714  push    rbx
0x180001716  push    rbp
0x180001717  push    rsi
0x180001718  push    rdi
0x180001719  sub     rsp, 28h
0x18000171d  mov     rdi, r9
0x180001720  mov     rsi, r8
0x180001723  mov     ebx, edx
0x180001725  mov     rbp, rcx
0x180001728  call    __scrt_is_ucrt_dll_in_use
0x18000172d  test    eax, eax
0x18000172f  jnz     short loc_180001746
0x180001731  cmp     ebx, 1
0x180001734  jnz     short loc_180001746
0x180001736  mov     r8, rsi
0x180001739  xor     edx, edx
0x18000173b  mov     rcx, rbp
0x18000173e  mov     rax, rdi
0x180001741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001746  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000174b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000174f  add     rsp, 28h
0x180001753  pop     rdi
0x180001754  pop     rsi
0x180001755  pop     rbp
0x180001756  pop     rbx
0x180001757  jmp     _o__seh_filter_dll_0
```
