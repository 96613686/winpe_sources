# MI_ReportErrorDetails_HashingOfGivenTypeIncompatibleWithChoosenHashRoutine

- ea: `0x180018bf8`
- end: `0x180018c6e`
- name: `MI_ReportErrorDetails_HashingOfGivenTypeIncompatibleWithChoosenHashRoutine`
- size: `118`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018ce0`
- `0x180018d60`
- `0x180018e20`
- `0x180018ea0`
- `0x180018f50`
- `0x180019000`

## callees

- `0x180006e64`
- `0x180007c80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018c10`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018c10`

## string_xrefs

- `0x180018c04`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall MI_ReportErrorDetails_HashingOfGivenTypeIncompatibleWithChoosenHashRoutine(__int64 a1)
{
  HMODULE ModuleHandleA; // rax

  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_FormatString_FormatMessage(ModuleHandleA, 2112, a1);
  return MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
}

```

## disassembly

```asm
0x180018bf8  push    rbx
0x180018bfa  sub     rsp, 40h
0x180018bfe  mov     rbx, rcx
0x180018c01  xorps   xmm0, xmm0
0x180018c04  lea     rcx, ModuleName; "mpunits.dll"
0x180018c0b  movups  [rsp+48h+var_18], xmm0
0x180018c10  call    cs:__imp_GetModuleHandleA
0x180018c16  mov     r8, rbx
0x180018c19  mov     edx, 840h
0x180018c1e  mov     rcx, rax
0x180018c21  call    _Intlstr_FormatString_FormatMessage
0x180018c26  mov     qword ptr [rsp+48h+var_18], rax
0x180018c2b  lea     r9, [rsp+48h+var_18]
0x180018c30  mov     byte ptr [rsp+48h+var_18+8], 1
0x180018c35  lea     rdx, aMi; "MI"
0x180018c3c  movaps  xmm0, [rsp+48h+var_18]
0x180018c41  mov     r8d, 5
0x180018c47  mov     [rsp+48h+var_20], 0; __int64
0x180018c50  movdqa  [rsp+48h+var_18], xmm0
0x180018c56  mov     [rsp+48h+var_28], 0; __int64
0x180018c5f  lea     ecx, [r8-1]; int
0x180018c63  call    MI_ReportErrorDetails_ForCustomError
0x180018c68  add     rsp, 40h
0x180018c6c  pop     rbx
0x180018c6d  retn
```
