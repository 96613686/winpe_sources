# PreCachedBinaryLogWriterWithBookmark

- ea: `0x180028f80`
- end: `0x180029007`
- name: `PreCachedBinaryLogWriterWithBookmark`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x180028b00`
- `0x180028f80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180028f98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180028f98`

## string_xrefs

- `0x180028f8c`: `mpunits.dll`
- `0x180028fc1`: `BinaryLogReader`

## pseudocode

```c
__int64 __fastcall PreCachedBinaryLogWriterWithBookmark(
        void (__fastcall ***a1)(_QWORD, LPCWSTR *),
        const WCHAR *a2,
        const wchar_t *a3,
        wchar_t *a4,
        __int64 a5,
        int a6,
        void (__fastcall ***a7)(_QWORD, LPCWSTR *),
        int a8,
        __int64 a9)
{
  HMODULE ModuleHandleA; // rax

  if ( a4 )
    return BinaryLogWriter_shared(a1, a2, a3, a4, a5, a6, a7, a8, a9);
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_FormatString_FormatMessage(ModuleHandleA, 2021, L"<null>");
  MI_ReportErrorDetails_ForCustomError(100, (int)L"BinaryLogReader", 0, 0);
  return 4;
}

```

## disassembly

```asm
0x180028f80  sub     rsp, 68h
0x180028f84  test    r9, r9
0x180028f87  jnz     short loc_180028FFE
0x180028f89  xorps   xmm0, xmm0
0x180028f8c  lea     rcx, ModuleName; "mpunits.dll"
0x180028f93  movups  [rsp+68h+var_18], xmm0
0x180028f98  call    cs:__imp_GetModuleHandleA
0x180028f9e  lea     r8, aNull; "<null>"
0x180028fa5  mov     edx, 7E5h
0x180028faa  mov     rcx, rax
0x180028fad  call    _Intlstr_FormatString_FormatMessage
0x180028fb2  mov     qword ptr [rsp+68h+var_18], rax
0x180028fb7  lea     r9, [rsp+68h+var_18]
0x180028fbc  mov     byte ptr [rsp+68h+var_18+8], 1
0x180028fc1  lea     rdx, aBinarylogreade_1; "BinaryLogReader"
0x180028fc8  movaps  xmm0, [rsp+68h+var_18]
0x180028fcd  mov     r8d, 5
0x180028fd3  mov     [rsp+68h+var_40], 0; __int64
0x180028fdc  movdqa  [rsp+68h+var_18], xmm0
0x180028fe2  mov     [rsp+68h+var_48], 0; __int64
0x180028feb  lea     ecx, [r8+5Fh]; int
0x180028fef  call    MI_ReportErrorDetails_ForCustomError
0x180028ff4  mov     eax, 4
0x180028ff9  add     rsp, 68h
0x180028ffd  retn
0x180028ffe  add     rsp, 68h
0x180029002  jmp     BinaryLogWriter_shared
```
