# __scrt_dllmain_exception_filter

- ea: `0x180002820`
- end: `0x18000287f`
- name: `__scrt_dllmain_exception_filter`
- size: `95`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002528`

## callees

- `0x180002820`
- `0x18000320c`
- `0x180003338`
- `0x180024010`

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
0x180002820  mov     [rsp+arg_0], rbx
0x180002825  mov     [rsp+arg_8], rbp
0x18000282a  mov     [rsp+arg_10], rsi
0x18000282f  push    rdi
0x180002830  sub     rsp, 20h
0x180002834  mov     rdi, r9
0x180002837  mov     rsi, r8
0x18000283a  mov     ebx, edx
0x18000283c  mov     rbp, rcx
0x18000283f  call    __scrt_is_ucrt_dll_in_use
0x180002844  test    eax, eax
0x180002846  jnz     short loc_18000285D
0x180002848  cmp     ebx, 1
0x18000284b  jnz     short loc_18000285D
0x18000284d  mov     r8, rsi
0x180002850  xor     edx, edx
0x180002852  mov     rcx, rbp
0x180002855  mov     rax, rdi
0x180002858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000285d  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x180002862  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x180002866  mov     rbx, [rsp+28h+arg_0]
0x18000286b  mov     rbp, [rsp+28h+arg_8]
0x180002870  mov     rsi, [rsp+28h+arg_10]
0x180002875  add     rsp, 20h
0x180002879  pop     rdi
0x18000287a  jmp     _o__seh_filter_dll_0
```
