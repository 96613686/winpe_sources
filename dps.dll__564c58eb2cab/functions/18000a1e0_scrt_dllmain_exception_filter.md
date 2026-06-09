# __scrt_dllmain_exception_filter

- ea: `0x18000a1e0`
- end: `0x18000a228`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180009e24`

## callees

- `0x18000a1e0`
- `0x18000a790`
- `0x18000a83e`
- `0x180019010`

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
0x18000a1e0  push    rbx
0x18000a1e2  push    rbp
0x18000a1e3  push    rsi
0x18000a1e4  push    rdi
0x18000a1e5  sub     rsp, 28h
0x18000a1e9  mov     rdi, r9
0x18000a1ec  mov     rsi, r8
0x18000a1ef  mov     ebx, edx
0x18000a1f1  mov     rbp, rcx
0x18000a1f4  call    __scrt_is_ucrt_dll_in_use
0x18000a1f9  test    eax, eax
0x18000a1fb  jnz     short loc_18000A212
0x18000a1fd  cmp     ebx, 1
0x18000a200  jnz     short loc_18000A212
0x18000a202  mov     r8, rsi
0x18000a205  xor     edx, edx
0x18000a207  mov     rcx, rbp
0x18000a20a  mov     rax, rdi
0x18000a20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a212  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000a217  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000a21b  add     rsp, 28h
0x18000a21f  pop     rdi
0x18000a220  pop     rsi
0x18000a221  pop     rbp
0x18000a222  pop     rbx
0x18000a223  jmp     _o__seh_filter_dll_0
```
