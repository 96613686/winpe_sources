# BatteryXmlReporter::WriteReportHeader(BatteryReportData &)

- ea: `0x180056798`
- end: `0x180056a8e`
- name: `?WriteReportHeader@BatteryXmlReporter@@IEAAKAEAUBatteryReportData@@@Z`
- size: `758`
- prototype: `unsigned int __fastcall(BatteryXmlReporter *__hidden this, struct BatteryReportData *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800566b4`

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
- `0x180056798`
- `0x180090358`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180056828`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180056828`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180056812`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180056812`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180056804`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180056804`
- `RPCRT4!UuidCreate` at `0x1800567f2`
- `RPCRT4!UuidCreate` at `0x1800567f2`

## string_xrefs

- `0x18005685f`: `<?xml version="1.0" encoding="utf-8"?>\n`
- `0x180056879`: `<?xml-stylesheet type='text/xsl' href='C:\battery-stylesheet.xsl'?>\n`
- `0x180056888`: `<BatteryReport xmlns="http://schemas.microsoft.com/battery/2012">\n`

## pseudocode

```c
__int64 __fastcall BatteryXmlReporter::WriteReportHeader(BatteryXmlReporter *this, struct BatteryReportData *a2)
{
  bool v2; // zf
  unsigned int v5; // ebx
  union _LARGE_INTEGER v6; // rbx
  __int64 v7; // rdi
  struct _FILETIME FileTime; // [rsp+20h] [rbp-40h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+28h] [rbp-38h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-20h] BYREF

  v2 = *((_DWORD *)this + 2) == 1;
  LocalFileTime = 0;
  Uuid = 0;
  SystemTime = 0;
  FileTime = 0;
  v5 = 1627;
  if ( v2 && !UuidCreate(&Uuid) )
  {
    GetSystemTime(&SystemTime);
    if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      if ( FileTimeToLocalFileTime(&FileTime, &LocalFileTime) )
      {
        v6.QuadPart = *((_QWORD *)a2 + 39) - *((_QWORD *)a2 + 40);
        v7 = (*(_QWORD *)&LocalFileTime - *(_QWORD *)&FileTime) / 600000000LL;
        XmlReporter::WriteRawString(this, L"<?xml version=\"1.0\" encoding=\"utf-8\"?>\n");
        XmlReporter::WriteRawString(this, L"<?xml-stylesheet type='text/xsl' href='C:\\battery-stylesheet.xsl'?>\n");
        XmlReporter::WriteRawString(this, L"<BatteryReport xmlns=\"http://schemas.microsoft.com/battery/2012\">\n");
        XmlReporter::WriteRawString(this, L"  <ReportInformation>\n");
        XmlReporter::WriteRawString(this, L"    <ReportGuid>");
        XmlReporter::WriteGuid(this, &Uuid);
        XmlReporter::WriteRawString(this, L"</ReportGuid>\n");
        XmlReporter::WriteRawString(this, L"    <ReportVersion>1.1</ReportVersion>\n");
        XmlReporter::WriteRawString(this, L"    <ScanTime>");
        XmlReporter::WriteDateTime(this, &SystemTime);
        XmlReporter::WriteRawString(this, L"</ScanTime>\n");
        XmlReporter::WriteRawString(this, L"    <LocalScanTime>");
        XmlReporter::WriteLocalDateTime(this, &SystemTime);
        XmlReporter::WriteRawString(this, L"</LocalScanTime>\n");
        XmlReporter::WriteRawString(this, L"    <ReportStartTime>");
        XmlReporter::WriteDateTime(this, v6);
        XmlReporter::WriteRawString(this, L"</ReportStartTime>\n");
        XmlReporter::WriteRawString(this, L"    <LocalReportStartTime>");
        XmlReporter::WriteLocalDateTime(this, v6);
        XmlReporter::WriteRawString(this, L"</LocalReportStartTime>\n");
        XmlReporter::WriteRawString(this, L"    <ReportDuration>");
        XmlReporter::WriteInteger(this, *((_QWORD *)a2 + 40) / 0x989680uLL / 0x3C / 0x3C / 0x18);
        XmlReporter::WriteRawString(this, L"</ReportDuration>\n");
        XmlReporter::WriteRawString(this, L"    <UtcOffset>");
        XmlReporter::WriteUtcOffset(this, v7);
        XmlReporter::WriteRawString(this, L"</UtcOffset>\n");
        XmlReporter::WriteRawString(this, L"    <Verbose>");
        XmlReporter::WriteInteger(this, *((_BYTE *)a2 + 376) != 0);
        XmlReporter::WriteRawString(this, L"</Verbose>\n");
        XmlReporter::WriteRawString(this, L"  </ReportInformation>\n");
        return XmlReporter::UpdateReportState(this, 1u, 5u);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180056798  mov     [rsp-18h+arg_10], rbx
0x18005679d  mov     [rsp-18h+arg_18], rsi
0x1800567a2  push    rbp
0x1800567a3  push    rdi
0x1800567a4  push    r14
0x1800567a6  mov     rbp, rsp
0x1800567a9  sub     rsp, 60h
0x1800567ad  mov     rax, cs:__security_cookie
0x1800567b4  xor     rax, rsp
0x1800567b7  mov     [rbp+var_10], rax
0x1800567bb  cmp     dword ptr [rcx+8], 1
0x1800567bf  xorps   xmm0, xmm0
0x1800567c2  xorps   xmm1, xmm1
0x1800567c5  mov     qword ptr [rbp+LocalFileTime.dwLowDateTime], 0
0x1800567cd  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x1800567d1  mov     r14, rdx
0x1800567d4  mov     rsi, rcx
0x1800567d7  movups  xmmword ptr [rbp+SystemTime.wYear], xmm1
0x1800567db  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x1800567e3  mov     ebx, 65Bh
0x1800567e8  jnz     loc_180056A6B
0x1800567ee  lea     rcx, [rbp+Uuid]; Uuid
0x1800567f2  call    cs:__imp_UuidCreate
0x1800567f8  test    eax, eax
0x1800567fa  jnz     loc_180056A6B
0x180056800  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180056804  call    cs:__imp_GetSystemTime
0x18005680a  lea     rdx, [rbp+FileTime]; lpFileTime
0x18005680e  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180056812  call    cs:__imp_SystemTimeToFileTime
0x180056818  test    eax, eax
0x18005681a  jz      loc_180056A6B
0x180056820  lea     rdx, [rbp+LocalFileTime]; lpLocalFileTime
0x180056824  lea     rcx, [rbp+FileTime]; lpFileTime
0x180056828  call    cs:__imp_FileTimeToLocalFileTime
0x18005682e  test    eax, eax
0x180056830  jz      loc_180056A6B
0x180056836  mov     rcx, qword ptr [rbp+LocalFileTime.dwLowDateTime]
0x18005683a  mov     rax, 1CA213D840BAF7D5h
0x180056844  sub     rcx, qword ptr [rbp+FileTime.dwLowDateTime]
0x180056848  mov     rbx, [r14+138h]
0x18005684f  sub     rbx, [r14+140h]
0x180056856  imul    rcx
0x180056859  mov     rcx, rsi; this
0x18005685c  mov     rdi, rdx
0x18005685f  lea     rdx, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180056866  sar     rdi, 1Ah
0x18005686a  mov     rax, rdi
0x18005686d  shr     rax, 3Fh
0x180056871  add     rdi, rax
0x180056874  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056879  lea     rdx, aXmlStylesheetT_0; "<?xml-stylesheet type='text/xsl' href='"...
0x180056880  mov     rcx, rsi; this
0x180056883  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056888  lea     rdx, aBatteryreportX; "<BatteryReport xmlns=\"http://schemas.m"...
0x18005688f  mov     rcx, rsi; this
0x180056892  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056897  lea     rdx, aReportinformat_1; "  <ReportInformation>\n"
0x18005689e  mov     rcx, rsi; this
0x1800568a1  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800568a6  lea     rdx, aReportguid_1; "    <ReportGuid>"
0x1800568ad  mov     rcx, rsi; this
0x1800568b0  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800568b5  lea     rdx, [rbp+Uuid]; struct _GUID *
0x1800568b9  mov     rcx, rsi; this
0x1800568bc  call    ?WriteGuid@XmlReporter@@IEAAKPEBU_GUID@@@Z; XmlReporter::WriteGuid(_GUID const *)
0x1800568c1  lea     rdx, aReportguid_0; "</ReportGuid>\n"
0x1800568c8  mov     rcx, rsi; this
0x1800568cb  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800568d0  lea     rdx, aReportversion1; "    <ReportVersion>1.1</ReportVersion>"...
0x1800568d7  mov     rcx, rsi; this
0x1800568da  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800568df  lea     rdx, aScantime_0; "    <ScanTime>"
0x1800568e6  mov     rcx, rsi; this
0x1800568e9  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800568ee  lea     rdx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x1800568f2  mov     rcx, rsi; this
0x1800568f5  call    ?WriteDateTime@XmlReporter@@IEAAKAEAU_SYSTEMTIME@@@Z; XmlReporter::WriteDateTime(_SYSTEMTIME &)
0x1800568fa  lea     rdx, aScantime; "</ScanTime>\n"
0x180056901  mov     rcx, rsi; this
0x180056904  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056909  lea     rdx, aLocalscantime_0; "    <LocalScanTime>"
0x180056910  mov     rcx, rsi; this
0x180056913  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056918  lea     rdx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x18005691c  mov     rcx, rsi; this
0x18005691f  call    ?WriteLocalDateTime@XmlReporter@@IEAAKAEAU_SYSTEMTIME@@@Z; XmlReporter::WriteLocalDateTime(_SYSTEMTIME &)
0x180056924  lea     rdx, aLocalscantime; "</LocalScanTime>\n"
0x18005692b  mov     rcx, rsi; this
0x18005692e  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056933  lea     rdx, aReportstarttim_1; "    <ReportStartTime>"
0x18005693a  mov     rcx, rsi; this
0x18005693d  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056942  mov     rdx, rbx; union _LARGE_INTEGER
0x180056945  mov     rcx, rsi; this
0x180056948  call    ?WriteDateTime@XmlReporter@@IEAAKT_LARGE_INTEGER@@@Z; XmlReporter::WriteDateTime(_LARGE_INTEGER)
0x18005694d  lea     rdx, aReportstarttim_2; "</ReportStartTime>\n"
0x180056954  mov     rcx, rsi; this
0x180056957  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18005695c  lea     rdx, aLocalreportsta; "    <LocalReportStartTime>"
0x180056963  mov     rcx, rsi; this
0x180056966  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18005696b  mov     rdx, rbx; union _LARGE_INTEGER
0x18005696e  mov     rcx, rsi; this
0x180056971  call    ?WriteLocalDateTime@XmlReporter@@IEAAKT_LARGE_INTEGER@@@Z; XmlReporter::WriteLocalDateTime(_LARGE_INTEGER)
0x180056976  lea     rdx, aLocalreportsta_0; "</LocalReportStartTime>\n"
0x18005697d  mov     rcx, rsi; this
0x180056980  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056985  lea     rdx, aReportduration; "    <ReportDuration>"
0x18005698c  mov     rcx, rsi; this
0x18005698f  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056994  mov     rax, 0D6BF94D5E57A42BDh
0x18005699e  mov     rcx, 8888888888888889h
0x1800569a8  mul     qword ptr [r14+140h]
0x1800569af  mov     rax, rcx
0x1800569b2  shr     rdx, 17h
0x1800569b6  mul     rdx
0x1800569b9  shr     rdx, 5
0x1800569bd  mov     rax, rcx
0x1800569c0  mov     rcx, rsi; this
0x1800569c3  mul     rdx
0x1800569c6  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800569d0  shr     rdx, 5
0x1800569d4  mul     rdx
0x1800569d7  shr     rdx, 4; unsigned int
0x1800569db  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x1800569e0  lea     rdx, aReportduration_0; "</ReportDuration>\n"
0x1800569e7  mov     rcx, rsi; this
0x1800569ea  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800569ef  lea     rdx, aUtcoffset_0; "    <UtcOffset>"
0x1800569f6  mov     rcx, rsi; this
0x1800569f9  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800569fe  mov     edx, edi; int
0x180056a00  mov     rcx, rsi; this
0x180056a03  call    ?WriteUtcOffset@XmlReporter@@IEAAKJ@Z; XmlReporter::WriteUtcOffset(long)
0x180056a08  lea     rdx, aUtcoffset; "</UtcOffset>\n"
0x180056a0f  mov     rcx, rsi; this
0x180056a12  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056a17  lea     rdx, aVerbose_0; "    <Verbose>"
0x180056a1e  mov     rcx, rsi; this
0x180056a21  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056a26  xor     edx, edx
0x180056a28  mov     rcx, rsi; this
0x180056a2b  cmp     [r14+178h], dl
0x180056a32  setnz   dl; unsigned int
0x180056a35  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180056a3a  lea     rdx, aVerbose; "</Verbose>\n"
0x180056a41  mov     rcx, rsi; this
0x180056a44  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056a49  lea     rdx, aReportinformat; "  </ReportInformation>\n"
0x180056a50  mov     rcx, rsi; this
0x180056a53  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056a58  mov     edx, 1; unsigned int
0x180056a5d  mov     rcx, rsi; this
0x180056a60  lea     r8d, [rdx+4]; unsigned int
0x180056a64  call    ?UpdateReportState@XmlReporter@@IEAAKKK@Z; XmlReporter::UpdateReportState(ulong,ulong)
0x180056a69  mov     ebx, eax
0x180056a6b  mov     eax, ebx
0x180056a6d  mov     rcx, [rbp+var_10]
0x180056a71  xor     rcx, rsp; StackCookie
0x180056a74  call    __security_check_cookie
0x180056a79  lea     r11, [rsp+60h+var_s0]
0x180056a7e  mov     rbx, [r11+30h]
0x180056a82  mov     rsi, [r11+38h]
0x180056a86  mov     rsp, r11
0x180056a89  pop     r14
0x180056a8b  pop     rdi
0x180056a8c  pop     rbp
0x180056a8d  retn
```
