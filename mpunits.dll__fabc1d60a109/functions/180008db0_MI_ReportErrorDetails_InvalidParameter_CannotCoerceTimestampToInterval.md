# MI_ReportErrorDetails_InvalidParameter_CannotCoerceTimestampToInterval

- ea: `0x180008db0`
- end: `0x180008e98`
- name: `MI_ReportErrorDetails_InvalidParameter_CannotCoerceTimestampToInterval`
- size: `232`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002550`
- `0x180002c80`
- `0x180005320`
- `0x180005c80`

## callees

- `0x180006e64`
- `0x180006ef8`
- `0x180007920`
- `0x180042c5c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180008dd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180008def`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180008e25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180008dd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180008def`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180008e25`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180008e78`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180008e78`

## string_xrefs

- `0x180008dcb`: `mpunits.dll`
- `0x180008de5`: `mpunits.dll`
- `0x180008e0c`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall MI_ReportErrorDetails_InvalidParameter_CannotCoerceTimestampToInterval(__int64 a1)
{
  HMODULE ModuleHandleA; // rax
  HMODULE v3; // rax
  HMODULE v4; // rax
  void *v5; // rbx
  MI_Instance *extendedError; // [rsp+48h] [rbp+10h] BYREF

  extendedError = 0;
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_GetString_LoadString(ModuleHandleA, 2084);
  v3 = GetModuleHandleA("mpunits.dll");
  Intlstr_GetString_LoadString(v3, 2083);
  v4 = GetModuleHandleA("mpunits.dll");
  v5 = (void *)Intlstr_FormatString_FormatMessage(v4, 2136, a1);
  CreateOMIError_shared((int)v5, 4, (int)L"MI", 5, (__int64)&OMI_Error_rtti, &extendedError);
  LocalFree(v5);
  return ReportErrorDetails(extendedError);
}

```

## disassembly

```asm
0x180008db0  mov     [rsp+arg_0], rbx
0x180008db5  mov     [rsp+arg_10], rsi
0x180008dba  push    rdi
0x180008dbb  sub     rsp, 30h
0x180008dbf  mov     rsi, rcx
0x180008dc2  mov     [rsp+38h+arg_8], 0
0x180008dcb  lea     rcx, ModuleName; "mpunits.dll"
0x180008dd2  call    cs:__imp_GetModuleHandleA
0x180008dd8  mov     rcx, rax
0x180008ddb  mov     edx, 824h
0x180008de0  call    _Intlstr_GetString_LoadString
0x180008de5  lea     rcx, ModuleName; "mpunits.dll"
0x180008dec  mov     rbx, rax
0x180008def  call    cs:__imp_GetModuleHandleA
0x180008df5  mov     rcx, rax
0x180008df8  mov     edx, 823h
0x180008dfd  call    _Intlstr_GetString_LoadString
0x180008e02  test    rbx, rbx
0x180008e05  lea     rdi, aTimestamp; "timestamp"
0x180008e0c  lea     rcx, ModuleName; "mpunits.dll"
0x180008e13  cmovnz  rdi, rbx
0x180008e17  test    rax, rax
0x180008e1a  lea     rbx, aInterval; "interval"
0x180008e21  cmovnz  rbx, rax
0x180008e25  call    cs:__imp_GetModuleHandleA
0x180008e2b  mov     r9, rdi
0x180008e2e  mov     [rsp+38h+var_18], rbx
0x180008e33  mov     rcx, rax
0x180008e36  mov     r8, rsi
0x180008e39  mov     edx, 858h
0x180008e3e  call    _Intlstr_FormatString_FormatMessage
0x180008e43  mov     rbx, rax
0x180008e46  lea     r8, aMi; "MI"
0x180008e4d  mov     r9d, 5; int
0x180008e53  lea     rax, [rsp+38h+arg_8]
0x180008e58  mov     [rsp+38h+extendedError], rax; extendedError
0x180008e5d  mov     rcx, rbx; int
0x180008e60  lea     rax, OMI_Error_rtti
0x180008e67  mov     [rsp+38h+var_18], rax; __int64
0x180008e6c  lea     edx, [r9-1]; int
0x180008e70  call    CreateOMIError_shared
0x180008e75  mov     rcx, rbx; hMem
0x180008e78  call    cs:__imp_LocalFree
0x180008e7e  mov     rcx, [rsp+38h+arg_8]; lpTlsValue
0x180008e83  call    ReportErrorDetails
0x180008e88  mov     rbx, [rsp+38h+arg_0]
0x180008e8d  mov     rsi, [rsp+38h+arg_10]
0x180008e92  add     rsp, 30h
0x180008e96  pop     rdi
0x180008e97  retn
```
