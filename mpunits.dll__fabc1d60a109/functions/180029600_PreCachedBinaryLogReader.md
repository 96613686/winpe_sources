# PreCachedBinaryLogReader

- ea: `0x180029600`
- end: `0x18002968a`
- name: `PreCachedBinaryLogReader`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x1800292cc`
- `0x180029600`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180029618`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180029618`

## string_xrefs

- `0x18002960c`: `mpunits.dll`
- `0x180029641`: `BinaryLogReader`

## pseudocode

```c
__int64 __fastcall PreCachedBinaryLogReader(const WCHAR *a1, wchar_t *a2, wchar_t *a3, __int64 a4, int a5, _QWORD *a6)
{
  HMODULE ModuleHandleA; // rax

  if ( a3 )
    return BinaryLogReader_shared(a1, a2, a3, 0, a5, a6);
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_FormatString_FormatMessage(ModuleHandleA, 2021, L"<null>");
  MI_ReportErrorDetails_ForCustomError(100, (int)L"BinaryLogReader", 0, 0);
  return 4;
}

```

## disassembly

```asm
0x180029600  sub     rsp, 48h
0x180029604  test    r8, r8
0x180029607  jnz     short loc_18002967E
0x180029609  xorps   xmm0, xmm0
0x18002960c  lea     rcx, ModuleName; "mpunits.dll"
0x180029613  movups  [rsp+48h+var_18], xmm0
0x180029618  call    cs:__imp_GetModuleHandleA
0x18002961e  lea     r8, aNull; "<null>"
0x180029625  mov     edx, 7E5h
0x18002962a  mov     rcx, rax
0x18002962d  call    _Intlstr_FormatString_FormatMessage
0x180029632  mov     qword ptr [rsp+48h+var_18], rax
0x180029637  lea     r9, [rsp+48h+var_18]
0x18002963c  mov     byte ptr [rsp+48h+var_18+8], 1
0x180029641  lea     rdx, aBinarylogreade_1; "BinaryLogReader"
0x180029648  movaps  xmm0, [rsp+48h+var_18]
0x18002964d  mov     r8d, 5
0x180029653  mov     [rsp+48h+var_20], 0; __int64
0x18002965c  movdqa  [rsp+48h+var_18], xmm0
0x180029662  mov     [rsp+48h+var_28], 0; __int64
0x18002966b  lea     ecx, [r8+5Fh]; int
0x18002966f  call    MI_ReportErrorDetails_ForCustomError
0x180029674  mov     eax, 4
0x180029679  add     rsp, 48h
0x18002967d  retn
0x18002967e  xor     r9d, r9d
0x180029681  add     rsp, 48h
0x180029685  jmp     BinaryLogReader_shared
```
