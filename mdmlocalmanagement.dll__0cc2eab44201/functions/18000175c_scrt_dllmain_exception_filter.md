# __scrt_dllmain_exception_filter

- ea: `0x18000175c`
- end: `0x1800017a4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800014c4`

## callees

- `0x18000175c`
- `0x180001ed0`
- `0x180001fc6`
- `0x180007010`

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
0x18000175c  push    rbx
0x18000175e  push    rbp
0x18000175f  push    rsi
0x180001760  push    rdi
0x180001761  sub     rsp, 28h
0x180001765  mov     rdi, r9
0x180001768  mov     rsi, r8
0x18000176b  mov     ebx, edx
0x18000176d  mov     rbp, rcx
0x180001770  call    __scrt_is_ucrt_dll_in_use
0x180001775  test    eax, eax
0x180001777  jnz     short loc_18000178E
0x180001779  cmp     ebx, 1
0x18000177c  jnz     short loc_18000178E
0x18000177e  mov     r8, rsi
0x180001781  xor     edx, edx
0x180001783  mov     rcx, rbp
0x180001786  mov     rax, rdi
0x180001789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000178e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001793  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001797  add     rsp, 28h
0x18000179b  pop     rdi
0x18000179c  pop     rsi
0x18000179d  pop     rbp
0x18000179e  pop     rbx
0x18000179f  jmp     _o__seh_filter_dll_0
```
