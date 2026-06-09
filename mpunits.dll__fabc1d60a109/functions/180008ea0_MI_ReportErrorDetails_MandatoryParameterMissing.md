# MI_ReportErrorDetails_MandatoryParameterMissing

- ea: `0x180008ea0`
- end: `0x180008f1a`
- name: `MI_ReportErrorDetails_MandatoryParameterMissing`
- size: `122`
- prototype: ``
- caller_count: `38`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001cc0`
- `0x180001e20`
- `0x180001f80`
- `0x180002090`
- `0x180002550`
- `0x180002670`
- `0x180002780`
- `0x1800029a0`
- `0x180002c80`
- `0x180002f10`
- `0x180003020`
- `0x180003160`
- `0x1800032d0`
- `0x180003440`
- `0x1800037d0`
- `0x180003ce0`
- `0x180003e50`
- `0x18000400c`
- `0x180004410`
- `0x180004710`
- `0x180004830`
- `0x180004950`
- `0x180004a90`
- `0x180004ba0`
- `0x180004dd0`
- `0x180004f10`
- `0x180005030`
- `0x1800051c0`
- `0x180005320`
- `0x1800055a0`
- `0x180005780`
- `0x1800058c0`
- `0x180005a10`
- `0x180005c80`
- `0x180033e34`
- `0x180036aa0`
- `0x180036c80`
- `0x180040980`

## callees

- `0x180006e64`
- `0x180007920`
- `0x180042c5c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180008eb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180008eb9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180008f04`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180008f04`

## string_xrefs

- `0x180008eb2`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall MI_ReportErrorDetails_MandatoryParameterMissing(__int64 a1)
{
  HMODULE ModuleHandleA; // rax
  void *v3; // rbx
  MI_Instance *extendedError; // [rsp+48h] [rbp+10h] BYREF

  extendedError = 0;
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  v3 = (void *)Intlstr_FormatString_FormatMessage(ModuleHandleA, 2001, a1);
  CreateOMIError_shared((int)v3, 4, (int)L"MI", 5, (__int64)&OMI_Error_rtti, &extendedError);
  LocalFree(v3);
  return ReportErrorDetails(extendedError);
}

```

## disassembly

```asm
0x180008ea0  push    rbx
0x180008ea2  sub     rsp, 30h
0x180008ea6  mov     rbx, rcx
0x180008ea9  mov     [rsp+38h+arg_8], 0
0x180008eb2  lea     rcx, ModuleName; "mpunits.dll"
0x180008eb9  call    cs:__imp_GetModuleHandleA
0x180008ebf  mov     r8, rbx
0x180008ec2  mov     edx, 7D1h
0x180008ec7  mov     rcx, rax
0x180008eca  call    _Intlstr_FormatString_FormatMessage
0x180008ecf  mov     rbx, rax
0x180008ed2  lea     r8, aMi; "MI"
0x180008ed9  mov     r9d, 5; int
0x180008edf  lea     rax, [rsp+38h+arg_8]
0x180008ee4  mov     [rsp+38h+extendedError], rax; extendedError
0x180008ee9  mov     rcx, rbx; int
0x180008eec  lea     rax, OMI_Error_rtti
0x180008ef3  mov     [rsp+38h+var_18], rax; __int64
0x180008ef8  lea     edx, [r9-1]; int
0x180008efc  call    CreateOMIError_shared
0x180008f01  mov     rcx, rbx; hMem
0x180008f04  call    cs:__imp_LocalFree
0x180008f0a  mov     rcx, [rsp+38h+arg_8]; lpTlsValue
0x180008f0f  call    ReportErrorDetails
0x180008f14  add     rsp, 30h
0x180008f18  pop     rbx
0x180008f19  retn
```
