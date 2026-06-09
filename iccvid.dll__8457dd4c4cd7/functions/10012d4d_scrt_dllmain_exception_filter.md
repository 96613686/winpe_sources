# ___scrt_dllmain_exception_filter

- ea: `0x10012d4d`
- end: `0x10012d83`
- name: `___scrt_dllmain_exception_filter`
- size: `54`
- prototype: `int __cdecl(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x100129d8`

## callees

- `0x10012d4d`
- `0x100130b0`
- `0x100133f1`
- `0x1001346f`

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
0x10012d4d  mov     edi, edi
0x10012d4f  push    ebp
0x10012d50  mov     ebp, esp
0x10012d52  call    ___scrt_is_ucrt_dll_in_use
0x10012d57  test    eax, eax
0x10012d59  jnz     short loc_10012D74
0x10012d5b  cmp     [ebp+arg_4], 1
0x10012d5f  jnz     short loc_10012D74
0x10012d61  push    [ebp+arg_8]
0x10012d64  mov     ecx, [ebp+arg_C]
0x10012d67  push    eax
0x10012d68  push    [ebp+arg_0]
0x10012d6b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10012d71  call    [ebp+arg_C]
0x10012d74  push    [ebp+ExceptionPtr]; ExceptionPtr
0x10012d77  push    [ebp+ExceptionNum]; ExceptionNum
0x10012d7a  call    __seh_filter_dll
0x10012d7f  pop     ecx
0x10012d80  pop     ecx
0x10012d81  pop     ebp
0x10012d82  retn
```
