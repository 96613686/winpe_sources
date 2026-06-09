# __scrt_dllmain_exception_filter

- ea: `0x1800021fc`
- end: `0x180002244`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001f74`

## callees

- `0x1800021fc`
- `0x180002998`
- `0x180002ab8`
- `0x18000a010`

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
0x1800021fc  push    rbx
0x1800021fe  push    rbp
0x1800021ff  push    rsi
0x180002200  push    rdi
0x180002201  sub     rsp, 28h
0x180002205  mov     rdi, r9
0x180002208  mov     rsi, r8
0x18000220b  mov     ebx, edx
0x18000220d  mov     rbp, rcx
0x180002210  call    __scrt_is_ucrt_dll_in_use
0x180002215  test    eax, eax
0x180002217  jnz     short loc_18000222E
0x180002219  cmp     ebx, 1
0x18000221c  jnz     short loc_18000222E
0x18000221e  mov     r8, rsi
0x180002221  xor     edx, edx
0x180002223  mov     rcx, rbp
0x180002226  mov     rax, rdi
0x180002229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000222e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002233  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002237  add     rsp, 28h
0x18000223b  pop     rdi
0x18000223c  pop     rsi
0x18000223d  pop     rbp
0x18000223e  pop     rbx
0x18000223f  jmp     _o__seh_filter_dll_0
```
