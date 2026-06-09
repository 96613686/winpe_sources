# __scrt_dllmain_exception_filter

- ea: `0x180004450`
- end: `0x180004498`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004174`

## callees

- `0x180004450`
- `0x180004c24`
- `0x180004d18`
- `0x18000c010`

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
0x180004450  push    rbx
0x180004452  push    rbp
0x180004453  push    rsi
0x180004454  push    rdi
0x180004455  sub     rsp, 28h
0x180004459  mov     rdi, r9
0x18000445c  mov     rsi, r8
0x18000445f  mov     ebx, edx
0x180004461  mov     rbp, rcx
0x180004464  call    __scrt_is_ucrt_dll_in_use
0x180004469  test    eax, eax
0x18000446b  jnz     short loc_180004482
0x18000446d  cmp     ebx, 1
0x180004470  jnz     short loc_180004482
0x180004472  mov     r8, rsi
0x180004475  xor     edx, edx
0x180004477  mov     rcx, rbp
0x18000447a  mov     rax, rdi
0x18000447d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004482  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180004487  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000448b  add     rsp, 28h
0x18000448f  pop     rdi
0x180004490  pop     rsi
0x180004491  pop     rbp
0x180004492  pop     rbx
0x180004493  jmp     _o__seh_filter_dll_0
```
