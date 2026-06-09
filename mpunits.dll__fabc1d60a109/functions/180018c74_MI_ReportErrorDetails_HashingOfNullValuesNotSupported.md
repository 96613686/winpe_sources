# MI_ReportErrorDetails_HashingOfNullValuesNotSupported

- ea: `0x180018c74`
- end: `0x180018cd7`
- name: `MI_ReportErrorDetails_HashingOfNullValuesNotSupported`
- size: `99`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180018ce0`
- `0x180018d60`
- `0x180018e20`
- `0x180018ea0`
- `0x180018f50`
- `0x180019000`
- `0x180019090`

## callees

- `0x180006ef8`
- `0x180007c80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018c87`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018c87`

## string_xrefs

- `0x180018c7b`: `mpunits.dll`

## pseudocode

```c
__int64 MI_ReportErrorDetails_HashingOfNullValuesNotSupported()
{
  HMODULE ModuleHandleA; // rax

  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_GetString_LoadString(ModuleHandleA, 2110);
  return MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
}

```

## disassembly

```asm
0x180018c74  sub     rsp, 48h
0x180018c78  xorps   xmm0, xmm0
0x180018c7b  lea     rcx, ModuleName; "mpunits.dll"
0x180018c82  movups  [rsp+48h+var_18], xmm0
0x180018c87  call    cs:__imp_GetModuleHandleA
0x180018c8d  mov     rcx, rax
0x180018c90  mov     edx, 83Eh
0x180018c95  call    _Intlstr_GetString_LoadString
0x180018c9a  mov     qword ptr [rsp+48h+var_18], rax
0x180018c9f  lea     r9, [rsp+48h+var_18]
0x180018ca4  xor     eax, eax
0x180018ca6  lea     rdx, aMi; "MI"
0x180018cad  mov     byte ptr [rsp+48h+var_18+8], al
0x180018cb1  movaps  xmm0, [rsp+48h+var_18]
0x180018cb6  mov     [rsp+48h+var_20], rax; __int64
0x180018cbb  lea     r8d, [rax+5]
0x180018cbf  movdqa  [rsp+48h+var_18], xmm0
0x180018cc5  lea     ecx, [rax+4]; int
0x180018cc8  mov     [rsp+48h+var_28], rax; __int64
0x180018ccd  call    MI_ReportErrorDetails_ForCustomError
0x180018cd2  add     rsp, 48h
0x180018cd6  retn
```
