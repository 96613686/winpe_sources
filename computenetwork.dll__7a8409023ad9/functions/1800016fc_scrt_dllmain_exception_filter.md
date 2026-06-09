# __scrt_dllmain_exception_filter

- ea: `0x1800016fc`
- end: `0x180001744`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001474`

## callees

- `0x1800016fc`
- `0x180001ed8`
- `0x18000203e`
- `0x18000f010`

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
0x1800016fc  push    rbx
0x1800016fe  push    rbp
0x1800016ff  push    rsi
0x180001700  push    rdi
0x180001701  sub     rsp, 28h
0x180001705  mov     rdi, r9
0x180001708  mov     rsi, r8
0x18000170b  mov     ebx, edx
0x18000170d  mov     rbp, rcx
0x180001710  call    __scrt_is_ucrt_dll_in_use
0x180001715  test    eax, eax
0x180001717  jnz     short loc_18000172E
0x180001719  cmp     ebx, 1
0x18000171c  jnz     short loc_18000172E
0x18000171e  mov     r8, rsi
0x180001721  xor     edx, edx
0x180001723  mov     rcx, rbp
0x180001726  mov     rax, rdi
0x180001729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000172e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001733  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001737  add     rsp, 28h
0x18000173b  pop     rdi
0x18000173c  pop     rsi
0x18000173d  pop     rbp
0x18000173e  pop     rbx
0x18000173f  jmp     _o__seh_filter_dll_0
```
