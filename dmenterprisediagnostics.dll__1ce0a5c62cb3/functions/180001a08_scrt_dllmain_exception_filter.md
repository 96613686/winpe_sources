# __scrt_dllmain_exception_filter

- ea: `0x180001a08`
- end: `0x180001a50`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001654`

## callees

- `0x180001a08`
- `0x18000221c`
- `0x180002348`
- `0x180026010`

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
0x180001a08  push    rbx
0x180001a0a  push    rbp
0x180001a0b  push    rsi
0x180001a0c  push    rdi
0x180001a0d  sub     rsp, 28h
0x180001a11  mov     rdi, r9
0x180001a14  mov     rsi, r8
0x180001a17  mov     ebx, edx
0x180001a19  mov     rbp, rcx
0x180001a1c  call    __scrt_is_ucrt_dll_in_use
0x180001a21  test    eax, eax
0x180001a23  jnz     short loc_180001A3A
0x180001a25  cmp     ebx, 1
0x180001a28  jnz     short loc_180001A3A
0x180001a2a  mov     r8, rsi
0x180001a2d  xor     edx, edx
0x180001a2f  mov     rcx, rbp
0x180001a32  mov     rax, rdi
0x180001a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a3a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001a3f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001a43  add     rsp, 28h
0x180001a47  pop     rdi
0x180001a48  pop     rsi
0x180001a49  pop     rbp
0x180001a4a  pop     rbx
0x180001a4b  jmp     _o__seh_filter_dll_0
```
