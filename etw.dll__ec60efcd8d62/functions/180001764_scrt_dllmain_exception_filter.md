# __scrt_dllmain_exception_filter

- ea: `0x180001764`
- end: `0x1800017ac`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800013d4`

## callees

- `0x180001764`
- `0x180001d98`
- `0x180001e6a`
- `0x180016010`

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
0x180001764  push    rbx
0x180001766  push    rbp
0x180001767  push    rsi
0x180001768  push    rdi
0x180001769  sub     rsp, 28h
0x18000176d  mov     rdi, r9
0x180001770  mov     rsi, r8
0x180001773  mov     ebx, edx
0x180001775  mov     rbp, rcx
0x180001778  call    __scrt_is_ucrt_dll_in_use
0x18000177d  test    eax, eax
0x18000177f  jnz     short loc_180001796
0x180001781  cmp     ebx, 1
0x180001784  jnz     short loc_180001796
0x180001786  mov     r8, rsi
0x180001789  xor     edx, edx
0x18000178b  mov     rcx, rbp
0x18000178e  mov     rax, rdi
0x180001791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001796  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000179b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000179f  add     rsp, 28h
0x1800017a3  pop     rdi
0x1800017a4  pop     rsi
0x1800017a5  pop     rbp
0x1800017a6  pop     rbx
0x1800017a7  jmp     _o__seh_filter_dll_0
```
