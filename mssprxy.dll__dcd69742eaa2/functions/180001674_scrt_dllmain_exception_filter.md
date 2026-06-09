# __scrt_dllmain_exception_filter

- ea: `0x180001674`
- end: `0x1800016bc`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800012e4`

## callees

- `0x180001674`
- `0x180001c48`
- `0x180001cd6`
- `0x180003010`

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
0x180001674  push    rbx
0x180001676  push    rbp
0x180001677  push    rsi
0x180001678  push    rdi
0x180001679  sub     rsp, 28h
0x18000167d  mov     rdi, r9
0x180001680  mov     rsi, r8
0x180001683  mov     ebx, edx
0x180001685  mov     rbp, rcx
0x180001688  call    __scrt_is_ucrt_dll_in_use
0x18000168d  test    eax, eax
0x18000168f  jnz     short loc_1800016A6
0x180001691  cmp     ebx, 1
0x180001694  jnz     short loc_1800016A6
0x180001696  mov     r8, rsi
0x180001699  xor     edx, edx
0x18000169b  mov     rcx, rbp
0x18000169e  mov     rax, rdi
0x1800016a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016a6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800016ab  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800016af  add     rsp, 28h
0x1800016b3  pop     rdi
0x1800016b4  pop     rsi
0x1800016b5  pop     rbp
0x1800016b6  pop     rbx
0x1800016b7  jmp     _o__seh_filter_dll_0
```
