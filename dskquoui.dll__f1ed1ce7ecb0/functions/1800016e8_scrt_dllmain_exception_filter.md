# __scrt_dllmain_exception_filter

- ea: `0x1800016e8`
- end: `0x180001730`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001384`

## callees

- `0x1800016e8`
- `0x180002184`
- `0x180002278`
- `0x18001f010`

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
0x1800016e8  push    rbx
0x1800016ea  push    rbp
0x1800016eb  push    rsi
0x1800016ec  push    rdi
0x1800016ed  sub     rsp, 28h
0x1800016f1  mov     rdi, r9
0x1800016f4  mov     rsi, r8
0x1800016f7  mov     ebx, edx
0x1800016f9  mov     rbp, rcx
0x1800016fc  call    __scrt_is_ucrt_dll_in_use
0x180001701  test    eax, eax
0x180001703  jnz     short loc_18000171A
0x180001705  cmp     ebx, 1
0x180001708  jnz     short loc_18000171A
0x18000170a  mov     r8, rsi
0x18000170d  xor     edx, edx
0x18000170f  mov     rcx, rbp
0x180001712  mov     rax, rdi
0x180001715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000171a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000171f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001723  add     rsp, 28h
0x180001727  pop     rdi
0x180001728  pop     rsi
0x180001729  pop     rbp
0x18000172a  pop     rbx
0x18000172b  jmp     _o__seh_filter_dll_0
```
