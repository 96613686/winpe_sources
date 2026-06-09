# MI_ReportErrorDetails_OutOfRangeParameter

- ea: `0x180008fb0`
- end: `0x18000902a`
- name: `MI_ReportErrorDetails_OutOfRangeParameter`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800021a0`

## callees

- `0x180006e64`
- `0x180007920`
- `0x180042c5c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180008fc9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180008fc9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180009014`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180009014`

## string_xrefs

- `0x180008fc2`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall MI_ReportErrorDetails_OutOfRangeParameter(__int64 a1)
{
  HMODULE ModuleHandleA; // rax
  MI_Instance **v3; // rbx
  MI_Instance *extendedError; // [rsp+48h] [rbp+10h] BYREF

  extendedError = 0;
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  v3 = (MI_Instance **)Intlstr_FormatString_FormatMessage(ModuleHandleA, 2107, a1);
  CreateOMIError_shared(v3, 4, (MI_Instance **)L"MI", 5, (__int64)&OMI_Error_rtti, &extendedError);
  LocalFree(v3);
  return ReportErrorDetails(extendedError);
}

```

## disassembly

```asm
0x180008fb0  push    rbx
0x180008fb2  sub     rsp, 30h
0x180008fb6  mov     rbx, rcx
0x180008fb9  mov     [rsp+38h+arg_8], 0
0x180008fc2  lea     rcx, ModuleName; "mpunits.dll"
0x180008fc9  call    cs:__imp_GetModuleHandleA
0x180008fcf  mov     r8, rbx
0x180008fd2  mov     edx, 83Bh
0x180008fd7  mov     rcx, rax
0x180008fda  call    _Intlstr_FormatString_FormatMessage
0x180008fdf  mov     rbx, rax
0x180008fe2  lea     r8, aMi; "MI"
0x180008fe9  mov     r9d, 5; int
0x180008fef  lea     rax, [rsp+38h+arg_8]
0x180008ff4  mov     [rsp+38h+extendedError], rax; extendedError
0x180008ff9  mov     rcx, rbx; int
0x180008ffc  lea     rax, OMI_Error_rtti
0x180009003  mov     [rsp+38h+var_18], rax; __int64
0x180009008  lea     edx, [r9-1]; int
0x18000900c  call    CreateOMIError_shared
0x180009011  mov     rcx, rbx; hMem
0x180009014  call    cs:__imp_LocalFree
0x18000901a  mov     rcx, [rsp+38h+arg_8]; lpTlsValue
0x18000901f  call    ReportErrorDetails
0x180009024  add     rsp, 30h
0x180009028  pop     rbx
0x180009029  retn
```
