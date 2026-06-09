# __scrt_dllmain_exception_filter

- ea: `0x180002728`
- end: `0x180002770`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002494`

## callees

- `0x180002728`
- `0x180002e70`
- `0x180002f28`
- `0x180013010`

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
0x180002728  push    rbx
0x18000272a  push    rbp
0x18000272b  push    rsi
0x18000272c  push    rdi
0x18000272d  sub     rsp, 28h
0x180002731  mov     rdi, r9
0x180002734  mov     rsi, r8
0x180002737  mov     ebx, edx
0x180002739  mov     rbp, rcx
0x18000273c  call    __scrt_is_ucrt_dll_in_use
0x180002741  test    eax, eax
0x180002743  jnz     short loc_18000275A
0x180002745  cmp     ebx, 1
0x180002748  jnz     short loc_18000275A
0x18000274a  mov     r8, rsi
0x18000274d  xor     edx, edx
0x18000274f  mov     rcx, rbp
0x180002752  mov     rax, rdi
0x180002755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000275a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000275f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002763  add     rsp, 28h
0x180002767  pop     rdi
0x180002768  pop     rsi
0x180002769  pop     rbp
0x18000276a  pop     rbx
0x18000276b  jmp     _o__seh_filter_dll_0
```
