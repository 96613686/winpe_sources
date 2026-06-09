# __scrt_dllmain_exception_filter

- ea: `0x180004ac4`
- end: `0x180004b0c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004734`

## callees

- `0x180004ac4`
- `0x180005098`
- `0x180005156`
- `0x180014010`

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
0x180004ac4  push    rbx
0x180004ac6  push    rbp
0x180004ac7  push    rsi
0x180004ac8  push    rdi
0x180004ac9  sub     rsp, 28h
0x180004acd  mov     rdi, r9
0x180004ad0  mov     rsi, r8
0x180004ad3  mov     ebx, edx
0x180004ad5  mov     rbp, rcx
0x180004ad8  call    __scrt_is_ucrt_dll_in_use
0x180004add  test    eax, eax
0x180004adf  jnz     short loc_180004AF6
0x180004ae1  cmp     ebx, 1
0x180004ae4  jnz     short loc_180004AF6
0x180004ae6  mov     r8, rsi
0x180004ae9  xor     edx, edx
0x180004aeb  mov     rcx, rbp
0x180004aee  mov     rax, rdi
0x180004af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004af6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180004afb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180004aff  add     rsp, 28h
0x180004b03  pop     rdi
0x180004b04  pop     rsi
0x180004b05  pop     rbp
0x180004b06  pop     rbx
0x180004b07  jmp     _o__seh_filter_dll_0
```
