# PreCachedBinaryLogReaderWithBookmark

- ea: `0x180029690`
- end: `0x180029717`
- name: `PreCachedBinaryLogReaderWithBookmark`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x1800292cc`
- `0x180029690`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800296a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800296a8`

## string_xrefs

- `0x18002969c`: `mpunits.dll`
- `0x1800296d1`: `BinaryLogReader`

## pseudocode

```c
__int64 __fastcall PreCachedBinaryLogReaderWithBookmark(
        const WCHAR *a1,
        wchar_t *a2,
        wchar_t *a3,
        __int64 a4,
        int a5,
        _QWORD *a6)
{
  HMODULE ModuleHandleA; // rax

  if ( a3 )
    return BinaryLogReader_shared(a1, a2, a3, a4, a5, a6);
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_FormatString_FormatMessage(ModuleHandleA, 2021, L"<null>");
  MI_ReportErrorDetails_ForCustomError(100, (int)L"BinaryLogReader", 0, 0);
  return 4;
}

```

## disassembly

```asm
0x180029690  sub     rsp, 48h
0x180029694  test    r8, r8
0x180029697  jnz     short loc_18002970E
0x180029699  xorps   xmm0, xmm0
0x18002969c  lea     rcx, ModuleName; "mpunits.dll"
0x1800296a3  movups  [rsp+48h+var_18], xmm0
0x1800296a8  call    cs:__imp_GetModuleHandleA
0x1800296ae  lea     r8, aNull; "<null>"
0x1800296b5  mov     edx, 7E5h
0x1800296ba  mov     rcx, rax
0x1800296bd  call    _Intlstr_FormatString_FormatMessage
0x1800296c2  mov     qword ptr [rsp+48h+var_18], rax
0x1800296c7  lea     r9, [rsp+48h+var_18]
0x1800296cc  mov     byte ptr [rsp+48h+var_18+8], 1
0x1800296d1  lea     rdx, aBinarylogreade_1; "BinaryLogReader"
0x1800296d8  movaps  xmm0, [rsp+48h+var_18]
0x1800296dd  mov     r8d, 5
0x1800296e3  mov     [rsp+48h+var_20], 0; __int64
0x1800296ec  movdqa  [rsp+48h+var_18], xmm0
0x1800296f2  mov     [rsp+48h+var_28], 0; __int64
0x1800296fb  lea     ecx, [r8+5Fh]; int
0x1800296ff  call    MI_ReportErrorDetails_ForCustomError
0x180029704  mov     eax, 4
0x180029709  add     rsp, 48h
0x18002970d  retn
0x18002970e  add     rsp, 48h
0x180029712  jmp     BinaryLogReader_shared
```
