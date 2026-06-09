# __scrt_dllmain_exception_filter

- ea: `0x180014ff0`
- end: `0x180015038`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180014c34`

## callees

- `0x180014ff0`
- `0x180015594`
- `0x180015606`
- `0x18001c010`

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
0x180014ff0  push    rbx
0x180014ff2  push    rbp
0x180014ff3  push    rsi
0x180014ff4  push    rdi
0x180014ff5  sub     rsp, 28h
0x180014ff9  mov     rdi, r9
0x180014ffc  mov     rsi, r8
0x180014fff  mov     ebx, edx
0x180015001  mov     rbp, rcx
0x180015004  call    __scrt_is_ucrt_dll_in_use
0x180015009  test    eax, eax
0x18001500b  jnz     short loc_180015022
0x18001500d  cmp     ebx, 1
0x180015010  jnz     short loc_180015022
0x180015012  mov     r8, rsi
0x180015015  xor     edx, edx
0x180015017  mov     rcx, rbp
0x18001501a  mov     rax, rdi
0x18001501d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015022  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180015027  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18001502b  add     rsp, 28h
0x18001502f  pop     rdi
0x180015030  pop     rsi
0x180015031  pop     rbp
0x180015032  pop     rbx
0x180015033  jmp     _o__seh_filter_dll_0
```
