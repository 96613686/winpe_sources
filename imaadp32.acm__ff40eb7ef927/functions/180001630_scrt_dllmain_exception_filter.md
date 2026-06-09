# __scrt_dllmain_exception_filter

- ea: `0x180001630`
- end: `0x180001678`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001274`

## callees

- `0x180001630`
- `0x180001bf8`
- `0x180001c92`
- `0x180006010`

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
0x180001630  push    rbx
0x180001632  push    rbp
0x180001633  push    rsi
0x180001634  push    rdi
0x180001635  sub     rsp, 28h
0x180001639  mov     rdi, r9
0x18000163c  mov     rsi, r8
0x18000163f  mov     ebx, edx
0x180001641  mov     rbp, rcx
0x180001644  call    __scrt_is_ucrt_dll_in_use
0x180001649  test    eax, eax
0x18000164b  jnz     short loc_180001662
0x18000164d  cmp     ebx, 1
0x180001650  jnz     short loc_180001662
0x180001652  mov     r8, rsi
0x180001655  xor     edx, edx
0x180001657  mov     rcx, rbp
0x18000165a  mov     rax, rdi
0x18000165d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001662  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001667  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000166b  add     rsp, 28h
0x18000166f  pop     rdi
0x180001670  pop     rsi
0x180001671  pop     rbp
0x180001672  pop     rbx
0x180001673  jmp     _o__seh_filter_dll_0
```
