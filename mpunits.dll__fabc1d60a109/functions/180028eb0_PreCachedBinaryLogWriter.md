# PreCachedBinaryLogWriter

- ea: `0x180028eb0`
- end: `0x180028f6e`
- name: `PreCachedBinaryLogWriter`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x180028b00`
- `0x180028eb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180028ec8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180028ec8`

## string_xrefs

- `0x180028ebc`: `mpunits.dll`
- `0x180028ef1`: `BinaryLogReader`

## pseudocode

```c
__int64 __fastcall PreCachedBinaryLogWriter(
        void (__fastcall ***a1)(_QWORD, LPCWSTR *),
        const WCHAR *a2,
        const wchar_t *a3,
        wchar_t *a4,
        __int64 a5,
        int a6,
        int a7,
        __int64 a8)
{
  HMODULE ModuleHandleA; // rax

  if ( a4 )
    return BinaryLogWriter_shared(a1, a2, a3, a4, a5, a6, 0, a7, a8);
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_FormatString_FormatMessage(ModuleHandleA, 2021, L"<null>");
  MI_ReportErrorDetails_ForCustomError(100, (int)L"BinaryLogReader", 0, 0);
  return 4;
}

```

## disassembly

```asm
0x180028eb0  sub     rsp, 68h
0x180028eb4  test    r9, r9
0x180028eb7  jnz     short loc_180028F2B
0x180028eb9  xorps   xmm0, xmm0
0x180028ebc  lea     rcx, ModuleName; "mpunits.dll"
0x180028ec3  movups  [rsp+68h+var_18], xmm0
0x180028ec8  call    cs:__imp_GetModuleHandleA
0x180028ece  lea     r8, aNull; "<null>"
0x180028ed5  mov     edx, 7E5h
0x180028eda  mov     rcx, rax
0x180028edd  call    _Intlstr_FormatString_FormatMessage
0x180028ee2  mov     qword ptr [rsp+68h+var_18], rax
0x180028ee7  lea     r9, [rsp+68h+var_18]
0x180028eec  mov     byte ptr [rsp+68h+var_18+8], 1
0x180028ef1  lea     rdx, aBinarylogreade_1; "BinaryLogReader"
0x180028ef8  movaps  xmm0, [rsp+68h+var_18]
0x180028efd  mov     r8d, 5
0x180028f03  mov     [rsp+68h+var_40], 0; __int64
0x180028f0c  movdqa  [rsp+68h+var_18], xmm0
0x180028f12  mov     [rsp+68h+var_48], 0; __int64
0x180028f1b  lea     ecx, [r8+5Fh]; int
0x180028f1f  call    MI_ReportErrorDetails_ForCustomError
0x180028f24  mov     eax, 4
0x180028f29  jmp     short loc_180028F69
0x180028f2b  mov     rax, [rsp+68h+arg_38]
0x180028f33  mov     [rsp+68h+var_28], rax
0x180028f38  mov     eax, [rsp+68h+arg_30]
0x180028f3f  mov     [rsp+68h+var_30], eax
0x180028f43  mov     eax, [rsp+68h+arg_28]
0x180028f4a  mov     [rsp+68h+var_38], 0
0x180028f53  mov     dword ptr [rsp+68h+var_40], eax
0x180028f57  mov     rax, [rsp+68h+arg_20]
0x180028f5f  mov     [rsp+68h+var_48], rax
0x180028f64  call    BinaryLogWriter_shared
0x180028f69  add     rsp, 68h
0x180028f6d  retn
```
