# SystemSleepDiagnosticsXmlReporter::WriteReportHeader(void)

- ea: `0x18008af14`
- end: `0x18008b1aa`
- name: `?WriteReportHeader@SystemSleepDiagnosticsXmlReporter@@IEAAKXZ`
- size: `662`
- prototype: `unsigned int __fastcall(SystemSleepDiagnosticsXmlReporter *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800424e0`

## callees

- `0x18000ff60`
- `0x18001107c`
- `0x180012020`
- `0x18002e418`
- `0x18002e498`
- `0x18002e514`
- `0x18002e594`
- `0x1800465e0`
- `0x18004ca90`
- `0x18008af14`
- `0x180090358`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18008af98`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18008af98`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18008af82`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18008af82`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18008af74`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18008af74`
- `RPCRT4!UuidCreate` at `0x18008af62`
- `RPCRT4!UuidCreate` at `0x18008af62`

## string_xrefs

- `0x18008afc5`: `<?xml version="1.0" encoding="utf-8"?>\n`
- `0x18008afdf`: `<SystemSleepDiagnostics xmlns="http://schemas.microsoft.com/systemsleepdiagnostics/2016">\n`

## pseudocode

```c
__int64 __fastcall SystemSleepDiagnosticsXmlReporter::WriteReportHeader(union _LARGE_INTEGER *this)
{
  bool v1; // zf
  unsigned int v3; // ebx
  union _LARGE_INTEGER v4; // rbx
  __int64 v5; // rdi
  struct _FILETIME FileTime; // [rsp+20h] [rbp-48h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+28h] [rbp-40h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-38h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-28h] BYREF

  v1 = this[1].LowPart == 1;
  LocalFileTime = 0;
  Uuid = 0;
  FileTime = 0;
  SystemTime = 0;
  v3 = 1627;
  if ( v1 && !UuidCreate(&Uuid) )
  {
    GetSystemTime(&SystemTime);
    if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      if ( FileTimeToLocalFileTime(&FileTime, &LocalFileTime) )
      {
        v4 = this[3];
        v5 = (*(_QWORD *)&LocalFileTime - *(_QWORD *)&FileTime) / 600000000LL;
        XmlReporter::WriteRawString((XmlReporter *)this, L"<?xml version=\"1.0\" encoding=\"utf-8\"?>\n");
        XmlReporter::WriteRawString(
          (XmlReporter *)this,
          L"<SystemSleepDiagnostics xmlns=\"http://schemas.microsoft.com/systemsleepdiagnostics/2016\">\n");
        XmlReporter::WriteRawString((XmlReporter *)this, L"  <ReportInformation>\n");
        XmlReporter::WriteRawString((XmlReporter *)this, L"    <ReportGuid>");
        XmlReporter::WriteGuid((XmlReporter *)this, &Uuid);
        XmlReporter::WriteRawString((XmlReporter *)this, L"</ReportGuid>\n");
        XmlReporter::WriteRawString((XmlReporter *)this, L"    <ReportVersion>1.0</ReportVersion>\n");
        XmlReporter::WriteRawString((XmlReporter *)this, L"    <ScanTime>");
        XmlReporter::WriteDateTime((XmlReporter *)this, &SystemTime);
        XmlReporter::WriteRawString((XmlReporter *)this, L"</ScanTime>\n");
        XmlReporter::WriteRawString((XmlReporter *)this, L"    <LocalScanTime>");
        XmlReporter::WriteLocalDateTime((XmlReporter *)this, &SystemTime);
        XmlReporter::WriteRawString((XmlReporter *)this, L"</LocalScanTime>\n");
        XmlReporter::WriteRawString((XmlReporter *)this, L"    <ReportStartTime>");
        XmlReporter::WriteDateTime((XmlReporter *)this, v4);
        XmlReporter::WriteRawString((XmlReporter *)this, L"</ReportStartTime>\n");
        XmlReporter::WriteRawString((XmlReporter *)this, L"    <LocalReportStartTime>");
        XmlReporter::WriteLocalDateTime((XmlReporter *)this, v4);
        XmlReporter::WriteRawString((XmlReporter *)this, L"</LocalReportStartTime>\n");
        XmlReporter::WriteRawString((XmlReporter *)this, L"    <ReportDuration>");
        XmlReporter::WriteInteger(
          (XmlReporter *)this,
          (this[4].QuadPart - v4.QuadPart) / 0x989680uLL / 0x3C / 0x3C / 0x18);
        XmlReporter::WriteRawString((XmlReporter *)this, L"</ReportDuration>\n");
        XmlReporter::WriteRawString((XmlReporter *)this, L"    <UtcOffset>");
        XmlReporter::WriteUtcOffset((XmlReporter *)this, v5);
        XmlReporter::WriteRawString((XmlReporter *)this, L"</UtcOffset>\n");
        XmlReporter::WriteRawString((XmlReporter *)this, L"  </ReportInformation>\n");
        return XmlReporter::UpdateReportState((XmlReporter *)this, 1u, 5u);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18008af14  push    rbp
0x18008af16  push    rbx
0x18008af17  push    rsi
0x18008af18  push    rdi
0x18008af19  mov     rbp, rsp
0x18008af1c  sub     rsp, 68h
0x18008af20  mov     rax, cs:__security_cookie
0x18008af27  xor     rax, rsp
0x18008af2a  mov     [rbp+var_18], rax
0x18008af2e  cmp     dword ptr [rcx+8], 1
0x18008af32  xorps   xmm0, xmm0
0x18008af35  xorps   xmm1, xmm1
0x18008af38  mov     qword ptr [rbp+LocalFileTime.dwLowDateTime], 0
0x18008af40  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18008af44  mov     rsi, rcx
0x18008af47  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x18008af4f  movups  xmmword ptr [rbp+SystemTime.wYear], xmm1
0x18008af53  mov     ebx, 65Bh
0x18008af58  jnz     loc_18008B193
0x18008af5e  lea     rcx, [rbp+Uuid]; Uuid
0x18008af62  call    cs:__imp_UuidCreate
0x18008af68  test    eax, eax
0x18008af6a  jnz     loc_18008B193
0x18008af70  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18008af74  call    cs:__imp_GetSystemTime
0x18008af7a  lea     rdx, [rbp+FileTime]; lpFileTime
0x18008af7e  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18008af82  call    cs:__imp_SystemTimeToFileTime
0x18008af88  test    eax, eax
0x18008af8a  jz      loc_18008B193
0x18008af90  lea     rdx, [rbp+LocalFileTime]; lpLocalFileTime
0x18008af94  lea     rcx, [rbp+FileTime]; lpFileTime
0x18008af98  call    cs:__imp_FileTimeToLocalFileTime
0x18008af9e  test    eax, eax
0x18008afa0  jz      loc_18008B193
0x18008afa6  mov     rcx, qword ptr [rbp+LocalFileTime.dwLowDateTime]
0x18008afaa  mov     rax, 1CA213D840BAF7D5h
0x18008afb4  sub     rcx, qword ptr [rbp+FileTime.dwLowDateTime]
0x18008afb8  mov     rbx, [rsi+18h]
0x18008afbc  imul    rcx
0x18008afbf  mov     rcx, rsi; this
0x18008afc2  mov     rdi, rdx
0x18008afc5  lea     rdx, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18008afcc  sar     rdi, 1Ah
0x18008afd0  mov     rax, rdi
0x18008afd3  shr     rax, 3Fh
0x18008afd7  add     rdi, rax
0x18008afda  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008afdf  lea     rdx, aSystemsleepdia; "<SystemSleepDiagnostics xmlns=\"http://"...
0x18008afe6  mov     rcx, rsi; this
0x18008afe9  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008afee  lea     rdx, aReportinformat_1; "  <ReportInformation>\n"
0x18008aff5  mov     rcx, rsi; this
0x18008aff8  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008affd  lea     rdx, aReportguid_1; "    <ReportGuid>"
0x18008b004  mov     rcx, rsi; this
0x18008b007  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b00c  lea     rdx, [rbp+Uuid]; struct _GUID *
0x18008b010  mov     rcx, rsi; this
0x18008b013  call    ?WriteGuid@XmlReporter@@IEAAKPEBU_GUID@@@Z; XmlReporter::WriteGuid(_GUID const *)
0x18008b018  lea     rdx, aReportguid_0; "</ReportGuid>\n"
0x18008b01f  mov     rcx, rsi; this
0x18008b022  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b027  lea     rdx, aReportversion1_0; "    <ReportVersion>1.0</ReportVersion>"...
0x18008b02e  mov     rcx, rsi; this
0x18008b031  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b036  lea     rdx, aScantime_0; "    <ScanTime>"
0x18008b03d  mov     rcx, rsi; this
0x18008b040  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b045  lea     rdx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x18008b049  mov     rcx, rsi; this
0x18008b04c  call    ?WriteDateTime@XmlReporter@@IEAAKAEAU_SYSTEMTIME@@@Z; XmlReporter::WriteDateTime(_SYSTEMTIME &)
0x18008b051  lea     rdx, aScantime; "</ScanTime>\n"
0x18008b058  mov     rcx, rsi; this
0x18008b05b  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b060  lea     rdx, aLocalscantime_0; "    <LocalScanTime>"
0x18008b067  mov     rcx, rsi; this
0x18008b06a  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b06f  lea     rdx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x18008b073  mov     rcx, rsi; this
0x18008b076  call    ?WriteLocalDateTime@XmlReporter@@IEAAKAEAU_SYSTEMTIME@@@Z; XmlReporter::WriteLocalDateTime(_SYSTEMTIME &)
0x18008b07b  lea     rdx, aLocalscantime; "</LocalScanTime>\n"
0x18008b082  mov     rcx, rsi; this
0x18008b085  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b08a  lea     rdx, aReportstarttim_1; "    <ReportStartTime>"
0x18008b091  mov     rcx, rsi; this
0x18008b094  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b099  mov     rdx, rbx; union _LARGE_INTEGER
0x18008b09c  mov     rcx, rsi; this
0x18008b09f  call    ?WriteDateTime@XmlReporter@@IEAAKT_LARGE_INTEGER@@@Z; XmlReporter::WriteDateTime(_LARGE_INTEGER)
0x18008b0a4  lea     rdx, aReportstarttim_2; "</ReportStartTime>\n"
0x18008b0ab  mov     rcx, rsi; this
0x18008b0ae  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b0b3  lea     rdx, aLocalreportsta; "    <LocalReportStartTime>"
0x18008b0ba  mov     rcx, rsi; this
0x18008b0bd  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b0c2  mov     rdx, rbx; union _LARGE_INTEGER
0x18008b0c5  mov     rcx, rsi; this
0x18008b0c8  call    ?WriteLocalDateTime@XmlReporter@@IEAAKT_LARGE_INTEGER@@@Z; XmlReporter::WriteLocalDateTime(_LARGE_INTEGER)
0x18008b0cd  lea     rdx, aLocalreportsta_0; "</LocalReportStartTime>\n"
0x18008b0d4  mov     rcx, rsi; this
0x18008b0d7  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b0dc  lea     rdx, aReportduration; "    <ReportDuration>"
0x18008b0e3  mov     rcx, rsi; this
0x18008b0e6  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b0eb  mov     rcx, [rsi+20h]
0x18008b0ef  mov     rax, 0D6BF94D5E57A42BDh
0x18008b0f9  sub     rcx, rbx
0x18008b0fc  mul     rcx
0x18008b0ff  mov     rcx, 8888888888888889h
0x18008b109  shr     rdx, 17h
0x18008b10d  mov     rax, rcx
0x18008b110  mul     rdx
0x18008b113  mov     rax, rcx
0x18008b116  shr     rdx, 5
0x18008b11a  mul     rdx
0x18008b11d  shr     rdx, 5
0x18008b121  mov     rax, 0AAAAAAAAAAAAAAABh
0x18008b12b  mul     rdx
0x18008b12e  mov     rcx, rsi; this
0x18008b131  shr     rdx, 4; unsigned int
0x18008b135  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x18008b13a  lea     rdx, aReportduration_0; "</ReportDuration>\n"
0x18008b141  mov     rcx, rsi; this
0x18008b144  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b149  lea     rdx, aUtcoffset_0; "    <UtcOffset>"
0x18008b150  mov     rcx, rsi; this
0x18008b153  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b158  mov     edx, edi; int
0x18008b15a  mov     rcx, rsi; this
0x18008b15d  call    ?WriteUtcOffset@XmlReporter@@IEAAKJ@Z; XmlReporter::WriteUtcOffset(long)
0x18008b162  lea     rdx, aUtcoffset; "</UtcOffset>\n"
0x18008b169  mov     rcx, rsi; this
0x18008b16c  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b171  lea     rdx, aReportinformat; "  </ReportInformation>\n"
0x18008b178  mov     rcx, rsi; this
0x18008b17b  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008b180  mov     edx, 1; unsigned int
0x18008b185  mov     rcx, rsi; this
0x18008b188  lea     r8d, [rdx+4]; unsigned int
0x18008b18c  call    ?UpdateReportState@XmlReporter@@IEAAKKK@Z; XmlReporter::UpdateReportState(ulong,ulong)
0x18008b191  mov     ebx, eax
0x18008b193  mov     eax, ebx
0x18008b195  mov     rcx, [rbp+var_18]
0x18008b199  xor     rcx, rsp; StackCookie
0x18008b19c  call    __security_check_cookie
0x18008b1a1  add     rsp, 68h
0x18008b1a5  pop     rdi
0x18008b1a6  pop     rsi
0x18008b1a7  pop     rbx
0x18008b1a8  pop     rbp
0x18008b1a9  retn
```
