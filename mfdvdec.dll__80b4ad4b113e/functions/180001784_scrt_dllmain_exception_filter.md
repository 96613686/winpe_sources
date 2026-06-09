# __scrt_dllmain_exception_filter

- ea: `0x180001784`
- end: `0x1800017cc`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800013f4`

## callees

- `0x180001784`
- `0x180001db8`
- `0x180001e68`
- `0x18001e010`

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
0x180001784  push    rbx
0x180001786  push    rbp
0x180001787  push    rsi
0x180001788  push    rdi
0x180001789  sub     rsp, 28h
0x18000178d  mov     rdi, r9
0x180001790  mov     rsi, r8
0x180001793  mov     ebx, edx
0x180001795  mov     rbp, rcx
0x180001798  call    __scrt_is_ucrt_dll_in_use
0x18000179d  test    eax, eax
0x18000179f  jnz     short loc_1800017B6
0x1800017a1  cmp     ebx, 1
0x1800017a4  jnz     short loc_1800017B6
0x1800017a6  mov     r8, rsi
0x1800017a9  xor     edx, edx
0x1800017ab  mov     rcx, rbp
0x1800017ae  mov     rax, rdi
0x1800017b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017b6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800017bb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800017bf  add     rsp, 28h
0x1800017c3  pop     rdi
0x1800017c4  pop     rsi
0x1800017c5  pop     rbp
0x1800017c6  pop     rbx
0x1800017c7  jmp     _o__seh_filter_dll_0
```
