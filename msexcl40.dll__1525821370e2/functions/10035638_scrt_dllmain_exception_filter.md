# ___scrt_dllmain_exception_filter

- ea: `0x10035638`
- end: `0x1003566e`
- name: `___scrt_dllmain_exception_filter`
- size: `54`
- prototype: `int __cdecl(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x10035398`

## callees

- `0x10035638`
- `0x10035b40`
- `0x10035e75`
- `0x10035f28`

## pseudocode

```c
int __cdecl __scrt_dllmain_exception_filter(
        int a1,
        int a2,
        int a3,
        void (__thiscall *a4)(_DWORD, int, _DWORD, int),
        unsigned int ExceptionNum,
        struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  if ( !__scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a4, a1, 0, a3);
  return _seh_filter_dll(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x10035638  mov     edi, edi
0x1003563a  push    ebp
0x1003563b  mov     ebp, esp
0x1003563d  call    ___scrt_is_ucrt_dll_in_use
0x10035642  test    eax, eax
0x10035644  jnz     short loc_1003565F
0x10035646  cmp     [ebp+arg_4], 1
0x1003564a  jnz     short loc_1003565F
0x1003564c  push    [ebp+arg_8]
0x1003564f  mov     ecx, [ebp+arg_C]
0x10035652  push    eax
0x10035653  push    [ebp+arg_0]
0x10035656  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1003565c  call    [ebp+arg_C]
0x1003565f  push    [ebp+ExceptionPtr]; ExceptionPtr
0x10035662  push    [ebp+ExceptionNum]; ExceptionNum
0x10035665  call    __seh_filter_dll
0x1003566a  pop     ecx
0x1003566b  pop     ecx
0x1003566c  pop     ebp
0x1003566d  retn
```
