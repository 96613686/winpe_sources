# MI_ReportErrorDetails_MutuallyExclusiveParameters

- ea: `0x180008f20`
- end: `0x180008fa9`
- name: `MI_ReportErrorDetails_MutuallyExclusiveParameters`
- size: `137`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800029a0`
- `0x180003440`
- `0x1800037d0`

## callees

- `0x180006e64`
- `0x180007920`
- `0x180042c5c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180008f40`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180008f40`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180008f8e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180008f8e`

## string_xrefs

- `0x180008f36`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall MI_ReportErrorDetails_MutuallyExclusiveParameters(__int64 a1)
{
  HMODULE ModuleHandleA; // rax
  void *v3; // rbx
  MI_Instance *extendedError; // [rsp+50h] [rbp+18h] BYREF

  extendedError = 0;
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  v3 = (void *)Intlstr_FormatString_FormatMessage(ModuleHandleA, 2002, a1);
  CreateOMIError_shared((int)v3, 4, (int)L"MI", 5, (__int64)&OMI_Error_rtti, &extendedError);
  LocalFree(v3);
  return ReportErrorDetails(extendedError);
}

```

## disassembly

```asm
0x180008f20  mov     [rsp+arg_0], rbx
0x180008f25  push    rdi
0x180008f26  sub     rsp, 30h
0x180008f2a  mov     rdi, rcx
0x180008f2d  mov     [rsp+38h+arg_10], 0
0x180008f36  lea     rcx, ModuleName; "mpunits.dll"
0x180008f3d  mov     rbx, rdx
0x180008f40  call    cs:__imp_GetModuleHandleA
0x180008f46  mov     r9, rbx
0x180008f49  mov     r8, rdi
0x180008f4c  mov     rcx, rax
0x180008f4f  mov     edx, 7D2h
0x180008f54  call    _Intlstr_FormatString_FormatMessage
0x180008f59  mov     rbx, rax
0x180008f5c  lea     r8, aMi; "MI"
0x180008f63  mov     r9d, 5; int
0x180008f69  lea     rax, [rsp+38h+arg_10]
0x180008f6e  mov     [rsp+38h+extendedError], rax; extendedError
0x180008f73  mov     rcx, rbx; int
0x180008f76  lea     rax, OMI_Error_rtti
0x180008f7d  mov     [rsp+38h+var_18], rax; __int64
0x180008f82  lea     edx, [r9-1]; int
0x180008f86  call    CreateOMIError_shared
0x180008f8b  mov     rcx, rbx; hMem
0x180008f8e  call    cs:__imp_LocalFree
0x180008f94  mov     rcx, [rsp+38h+arg_10]; lpTlsValue
0x180008f99  call    ReportErrorDetails
0x180008f9e  mov     rbx, [rsp+38h+arg_0]
0x180008fa3  add     rsp, 30h
0x180008fa7  pop     rdi
0x180008fa8  retn
```
