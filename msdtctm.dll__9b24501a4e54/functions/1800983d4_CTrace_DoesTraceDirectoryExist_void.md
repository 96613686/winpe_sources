# CTrace::DoesTraceDirectoryExist(void)

- ea: `0x1800983d4`
- end: `0x1800984ef`
- name: `?DoesTraceDirectoryExist@CTrace@@AEAAJXZ`
- size: `283`
- prototype: `__int64 __fastcall(CTrace *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800984f8`

## callees

- `0x1800063b0`
- `0x180008a50`
- `0x18001d268`
- `0x1800983d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009844b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009844b`

## string_xrefs

- `0x1800983ff`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x180098498`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x1800984bf`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x180098478`: `Either the TraceDirectory does not exist or could not access it`
- `0x1800983f0`: `CTrace::DoesTraceDirectoryExist`
- `0x18009845c`: `TraceDirectory already exists`

## pseudocode

```c
__int64 __fastcall CTrace::DoesTraceDirectoryExist(CTrace *this)
{
  unsigned __int16 *DefaultLogPath; // rax
  DWORD FileAttributesW; // eax
  unsigned int v3; // ebx

  TraceStringInline(
    14,
    6,
    L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
    432,
    L"CTrace::DoesTraceDirectoryExist",
    0,
    L"In");
  DefaultLogPath = GetDefaultLogPath();
  StringCchPrintfW(&word_18015CE58, 0x304u, L"%s\\%s", DefaultLogPath, L"trace");
  FileAttributesW = GetFileAttributesW(&word_18015CE58);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    v3 = -2147467259;
    TraceStringInline(
      14,
      1,
      L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
      450,
      L"CTrace::DoesTraceDirectoryExist",
      -2147467259,
      L"Either the TraceDirectory does not exist or could not access it");
  }
  else
  {
    v3 = 0;
    TraceStringInline(
      14,
      3,
      L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
      444,
      L"CTrace::DoesTraceDirectoryExist",
      0,
      L"TraceDirectory already exists");
  }
  TraceStringInline(
    14,
    6,
    L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
    455,
    L"CTrace::DoesTraceDirectoryExist",
    0,
    L"Out");
  return v3;
}

```

## disassembly

```asm
0x1800983d4  mov     r11, rsp
0x1800983d7  mov     [r11+8], rbx
0x1800983db  push    rbp
0x1800983dc  sub     rsp, 40h
0x1800983e0  mov     edx, 6
0x1800983e5  lea     rax, aIn_0; "In"
0x1800983ec  mov     [r11-18h], rax
0x1800983f0  lea     rbp, aCtraceDoestrac; "CTrace::DoesTraceDirectoryExist"
0x1800983f7  mov     qword ptr [r11-20h], 0
0x1800983ff  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x180098406  mov     r9d, 1B0h
0x18009840c  mov     [r11-28h], rbp
0x180098410  lea     ecx, [rdx+8]
0x180098413  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180098418  call    ?GetDefaultLogPath@@YAPEAGXZ; GetDefaultLogPath(void)
0x18009841d  lea     rcx, aTrace; "trace"
0x180098424  mov     r9, rax
0x180098427  mov     [rsp+48h+var_28], rcx
0x18009842c  lea     r8, aSS_1; "%s\\%s"
0x180098433  lea     rcx, word_18015CE58; unsigned __int16 *
0x18009843a  mov     edx, 304h; unsigned __int64
0x18009843f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180098444  lea     rcx, word_18015CE58; lpFileName
0x18009844b  call    cs:__imp_GetFileAttributesW
0x180098451  cmp     eax, 0FFFFFFFFh
0x180098454  jz      short loc_180098478
0x180098456  test    al, 10h
0x180098458  jz      short loc_180098478
0x18009845a  xor     ebx, ebx
0x18009845c  lea     rax, aTracedirectory; "TraceDirectory already exists"
0x180098463  mov     [rsp+48h+var_18], rax
0x180098468  mov     r9d, 1BCh
0x18009846e  mov     [rsp+48h+var_20], rbx
0x180098473  lea     edx, [rbx+3]
0x180098476  jmp     short loc_180098498
0x180098478  lea     rax, aEitherTheTrace; "Either the TraceDirectory does not exis"...
0x18009847f  mov     ebx, 80004005h
0x180098484  mov     [rsp+48h+var_18], rax
0x180098489  mov     r9d, 1C2h
0x18009848f  mov     dword ptr [rsp+48h+var_20], ebx
0x180098493  mov     edx, 1
0x180098498  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x18009849f  mov     [rsp+48h+var_28], rbp
0x1800984a4  mov     ecx, 0Eh
0x1800984a9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800984ae  mov     edx, 6
0x1800984b3  lea     rax, aOut; "Out"
0x1800984ba  mov     [rsp+48h+var_18], rax
0x1800984bf  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x1800984c6  mov     [rsp+48h+var_20], 0
0x1800984cf  mov     r9d, 1C7h
0x1800984d5  mov     [rsp+48h+var_28], rbp
0x1800984da  lea     ecx, [rdx+8]
0x1800984dd  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800984e2  mov     eax, ebx
0x1800984e4  mov     rbx, [rsp+48h+arg_0]
0x1800984e9  add     rsp, 40h
0x1800984ed  pop     rbp
0x1800984ee  retn
```
