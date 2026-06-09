# __scrt_dllmain_exception_filter

- ea: `0x180012d58`
- end: `0x180012db8`
- name: `__scrt_dllmain_exception_filter`
- size: `96`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800129bc`

## callees

- `0x180012d58`
- `0x180013724`
- `0x1800173b4`
- `0x18001efd0`

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
  return seh_filter_dll(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180012d58  mov     [rsp+arg_0], rbx
0x180012d5d  mov     [rsp+arg_8], rbp
0x180012d62  mov     [rsp+arg_10], rsi
0x180012d67  push    rdi
0x180012d68  sub     rsp, 20h
0x180012d6c  mov     rdi, r9
0x180012d6f  mov     rsi, r8
0x180012d72  mov     ebx, edx
0x180012d74  mov     rbp, rcx
0x180012d77  call    __scrt_is_ucrt_dll_in_use
0x180012d7c  test    eax, eax
0x180012d7e  jnz     short loc_180012D96
0x180012d80  cmp     ebx, 1
0x180012d83  jnz     short loc_180012D96
0x180012d85  mov     r8, rsi
0x180012d88  xor     edx, edx
0x180012d8a  mov     rcx, rbp
0x180012d8d  mov     rax, rdi
0x180012d90  call    cs:__guard_dispatch_icall_fptr
0x180012d96  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x180012d9b  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x180012d9f  mov     rbx, [rsp+28h+arg_0]
0x180012da4  mov     rbp, [rsp+28h+arg_8]
0x180012da9  mov     rsi, [rsp+28h+arg_10]
0x180012dae  add     rsp, 20h
0x180012db2  pop     rdi
0x180012db3  jmp     _seh_filter_dll
```
