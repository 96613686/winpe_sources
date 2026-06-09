# SleepStudyXmlReporter::WriteReportHeader(SleepStudyReportData &)

- ea: `0x1800849e0`
- end: `0x180084ccf`
- name: `?WriteReportHeader@SleepStudyXmlReporter@@IEAAKAEAUSleepStudyReportData@@@Z`
- size: `751`
- prototype: `unsigned int __fastcall(SleepStudyXmlReporter *__hidden this, struct SleepStudyReportData *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180084900`

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
- `0x1800849e0`
- `0x180090358`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180084a6e`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180084a6e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180084a58`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180084a58`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180084a4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180084a4a`
- `RPCRT4!UuidCreate` at `0x180084a38`
- `RPCRT4!UuidCreate` at `0x180084a38`

## string_xrefs

- `0x180084aa9`: `<?xml version="1.0" encoding="utf-8"?>\n`
- `0x180084ac3`: `<?xml-stylesheet type='text/xsl' href='C:\sleepstudy-stylesheet.xsl'?>\n`
- `0x180084ad2`: `<SleepStudy xmlns="http://schemas.microsoft.com/sleepstudy/2012">\n`

## pseudocode

```c
__int64 __fastcall SleepStudyXmlReporter::WriteReportHeader(
        SleepStudyXmlReporter *this,
        struct SleepStudyReportData *a2)
{
  bool v2; // zf
  unsigned int v5; // ebx
  XmlReporter *v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // r15
  __int64 v9; // r14
  union _LARGE_INTEGER v10; // rbx
  const unsigned __int16 *v11; // rdx
  struct _FILETIME FileTime; // [rsp+20h] [rbp-40h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+28h] [rbp-38h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-20h] BYREF

  v2 = *((_DWORD *)this + 6) == 1;
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
        v6 = (SleepStudyXmlReporter *)((char *)this + 16);
        v7 = *((_QWORD *)a2 + 39);
        v8 = *((_QWORD *)a2 + 40);
        v9 = (*(_QWORD *)&LocalFileTime - *(_QWORD *)&FileTime) / 600000000LL;
        XmlReporter::WriteRawString(v6, L"<?xml version=\"1.0\" encoding=\"utf-8\"?>\n");
        XmlReporter::WriteRawString(v6, L"<?xml-stylesheet type='text/xsl' href='C:\\sleepstudy-stylesheet.xsl'?>\n");
        XmlReporter::WriteRawString(v6, L"<SleepStudy xmlns=\"http://schemas.microsoft.com/sleepstudy/2012\">\n");
        XmlReporter::WriteRawString(v6, L"  <ReportInformation>\n");
        XmlReporter::WriteRawString(v6, L"    <ReportGuid>");
        XmlReporter::WriteGuid(v6, &Uuid);
        XmlReporter::WriteRawString(v6, L"</ReportGuid>\n");
        XmlReporter::WriteRawString(v6, L"    <ReportVersion>1.1</ReportVersion>\n");
        XmlReporter::WriteRawString(v6, L"    <ScanTime>");
        XmlReporter::WriteDateTime(v6, &SystemTime);
        XmlReporter::WriteRawString(v6, L"</ScanTime>\n");
        XmlReporter::WriteRawString(v6, L"    <LocalScanTime>");
        XmlReporter::WriteLocalDateTime(v6, &SystemTime);
        XmlReporter::WriteRawString(v6, L"</LocalScanTime>\n");
        if ( *((_QWORD *)a2 + 40) )
        {
          v10.QuadPart = v7 - v8;
          XmlReporter::WriteRawString(v6, L"    <ReportStartTime>");
          XmlReporter::WriteDateTime(v6, v10);
          XmlReporter::WriteRawString(v6, L"</ReportStartTime>\n");
          XmlReporter::WriteRawString(v6, L"    <LocalReportStartTime>");
          XmlReporter::WriteLocalDateTime(v6, v10);
          XmlReporter::WriteRawString(v6, L"</LocalReportStartTime>\n");
          XmlReporter::WriteRawString(v6, L"    <ReportDuration>");
          XmlReporter::WriteInteger(v6, *((_QWORD *)a2 + 40) / 0x989680uLL / 0x3C / 0x3C / 0x18);
          XmlReporter::WriteRawString(v6, L"</ReportDuration>\n");
          v11 = L"    <SingleTraceFile>false</SingleTraceFile>";
        }
        else
        {
          v11 = L"    <SingleTraceFile>true</SingleTraceFile>";
        }
        XmlReporter::WriteRawString(v6, v11);
        XmlReporter::WriteRawString(v6, L"    <UtcOffset>");
        XmlReporter::WriteUtcOffset(v6, v9);
        XmlReporter::WriteRawString(v6, L"</UtcOffset>\n");
        XmlReporter::WriteRawString(v6, L"  </ReportInformation>\n");
        return XmlReporter::UpdateReportState(v6, 1u, 5u);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800849e0  mov     [rsp-28h+arg_10], rbx
0x1800849e5  push    rbp
0x1800849e6  push    rsi
0x1800849e7  push    rdi
0x1800849e8  push    r14
0x1800849ea  push    r15
0x1800849ec  mov     rbp, rsp
0x1800849ef  sub     rsp, 60h
0x1800849f3  mov     rax, cs:__security_cookie
0x1800849fa  xor     rax, rsp
0x1800849fd  mov     [rbp+var_10], rax
0x180084a01  cmp     dword ptr [rcx+18h], 1
0x180084a05  xorps   xmm0, xmm0
0x180084a08  xorps   xmm1, xmm1
0x180084a0b  mov     qword ptr [rbp+LocalFileTime.dwLowDateTime], 0
0x180084a13  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180084a17  mov     rsi, rdx
0x180084a1a  mov     rdi, rcx
0x180084a1d  movups  xmmword ptr [rbp+SystemTime.wYear], xmm1
0x180084a21  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x180084a29  mov     ebx, 65Bh
0x180084a2e  jnz     loc_180084CAD
0x180084a34  lea     rcx, [rbp+Uuid]; Uuid
0x180084a38  call    cs:__imp_UuidCreate
0x180084a3e  test    eax, eax
0x180084a40  jnz     loc_180084CAD
0x180084a46  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180084a4a  call    cs:__imp_GetSystemTime
0x180084a50  lea     rdx, [rbp+FileTime]; lpFileTime
0x180084a54  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180084a58  call    cs:__imp_SystemTimeToFileTime
0x180084a5e  test    eax, eax
0x180084a60  jz      loc_180084CAD
0x180084a66  lea     rdx, [rbp+LocalFileTime]; lpLocalFileTime
0x180084a6a  lea     rcx, [rbp+FileTime]; lpFileTime
0x180084a6e  call    cs:__imp_FileTimeToLocalFileTime
0x180084a74  test    eax, eax
0x180084a76  jz      loc_180084CAD
0x180084a7c  mov     rcx, qword ptr [rbp+LocalFileTime.dwLowDateTime]
0x180084a80  mov     rax, 1CA213D840BAF7D5h
0x180084a8a  sub     rcx, qword ptr [rbp+FileTime.dwLowDateTime]
0x180084a8e  add     rdi, 10h
0x180084a92  mov     rbx, [rsi+138h]
0x180084a99  mov     r15, [rsi+140h]
0x180084aa0  imul    rcx
0x180084aa3  mov     rcx, rdi; this
0x180084aa6  mov     r14, rdx
0x180084aa9  lea     rdx, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180084ab0  sar     r14, 1Ah
0x180084ab4  mov     rax, r14
0x180084ab7  shr     rax, 3Fh
0x180084abb  add     r14, rax
0x180084abe  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084ac3  lea     rdx, aXmlStylesheetT; "<?xml-stylesheet type='text/xsl' href='"...
0x180084aca  mov     rcx, rdi; this
0x180084acd  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084ad2  lea     rdx, aSleepstudyXmln; "<SleepStudy xmlns=\"http://schemas.micr"...
0x180084ad9  mov     rcx, rdi; this
0x180084adc  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084ae1  lea     rdx, aReportinformat_1; "  <ReportInformation>\n"
0x180084ae8  mov     rcx, rdi; this
0x180084aeb  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084af0  lea     rdx, aReportguid_1; "    <ReportGuid>"
0x180084af7  mov     rcx, rdi; this
0x180084afa  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084aff  lea     rdx, [rbp+Uuid]; struct _GUID *
0x180084b03  mov     rcx, rdi; this
0x180084b06  call    ?WriteGuid@XmlReporter@@IEAAKPEBU_GUID@@@Z; XmlReporter::WriteGuid(_GUID const *)
0x180084b0b  lea     rdx, aReportguid_0; "</ReportGuid>\n"
0x180084b12  mov     rcx, rdi; this
0x180084b15  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084b1a  lea     rdx, aReportversion1; "    <ReportVersion>1.1</ReportVersion>"...
0x180084b21  mov     rcx, rdi; this
0x180084b24  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084b29  lea     rdx, aScantime_0; "    <ScanTime>"
0x180084b30  mov     rcx, rdi; this
0x180084b33  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084b38  lea     rdx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x180084b3c  mov     rcx, rdi; this
0x180084b3f  call    ?WriteDateTime@XmlReporter@@IEAAKAEAU_SYSTEMTIME@@@Z; XmlReporter::WriteDateTime(_SYSTEMTIME &)
0x180084b44  lea     rdx, aScantime; "</ScanTime>\n"
0x180084b4b  mov     rcx, rdi; this
0x180084b4e  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084b53  lea     rdx, aLocalscantime_0; "    <LocalScanTime>"
0x180084b5a  mov     rcx, rdi; this
0x180084b5d  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084b62  lea     rdx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x180084b66  mov     rcx, rdi; this
0x180084b69  call    ?WriteLocalDateTime@XmlReporter@@IEAAKAEAU_SYSTEMTIME@@@Z; XmlReporter::WriteLocalDateTime(_SYSTEMTIME &)
0x180084b6e  lea     rdx, aLocalscantime; "</LocalScanTime>\n"
0x180084b75  mov     rcx, rdi; this
0x180084b78  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084b7d  cmp     qword ptr [rsi+140h], 0
0x180084b85  jz      loc_180084C53
0x180084b8b  lea     rdx, aReportstarttim_1; "    <ReportStartTime>"
0x180084b92  mov     rcx, rdi; this
0x180084b95  sub     rbx, r15
0x180084b98  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084b9d  mov     rdx, rbx; union _LARGE_INTEGER
0x180084ba0  mov     rcx, rdi; this
0x180084ba3  call    ?WriteDateTime@XmlReporter@@IEAAKT_LARGE_INTEGER@@@Z; XmlReporter::WriteDateTime(_LARGE_INTEGER)
0x180084ba8  lea     rdx, aReportstarttim_2; "</ReportStartTime>\n"
0x180084baf  mov     rcx, rdi; this
0x180084bb2  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084bb7  lea     rdx, aLocalreportsta; "    <LocalReportStartTime>"
0x180084bbe  mov     rcx, rdi; this
0x180084bc1  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084bc6  mov     rdx, rbx; union _LARGE_INTEGER
0x180084bc9  mov     rcx, rdi; this
0x180084bcc  call    ?WriteLocalDateTime@XmlReporter@@IEAAKT_LARGE_INTEGER@@@Z; XmlReporter::WriteLocalDateTime(_LARGE_INTEGER)
0x180084bd1  lea     rdx, aLocalreportsta_0; "</LocalReportStartTime>\n"
0x180084bd8  mov     rcx, rdi; this
0x180084bdb  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084be0  lea     rdx, aReportduration; "    <ReportDuration>"
0x180084be7  mov     rcx, rdi; this
0x180084bea  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084bef  mov     rcx, 8888888888888889h
0x180084bf9  mov     rax, 0D6BF94D5E57A42BDh
0x180084c03  mul     qword ptr [rsi+140h]
0x180084c0a  mov     rax, rcx
0x180084c0d  shr     rdx, 17h
0x180084c11  mul     rdx
0x180084c14  mov     rax, rcx
0x180084c17  mov     rcx, rdi; this
0x180084c1a  shr     rdx, 5
0x180084c1e  mul     rdx
0x180084c21  mov     rax, 0AAAAAAAAAAAAAAABh
0x180084c2b  shr     rdx, 5
0x180084c2f  mul     rdx
0x180084c32  shr     rdx, 4; unsigned int
0x180084c36  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180084c3b  lea     rdx, aReportduration_0; "</ReportDuration>\n"
0x180084c42  mov     rcx, rdi; this
0x180084c45  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084c4a  lea     rdx, aSingletracefil; "    <SingleTraceFile>false</SingleTrace"...
0x180084c51  jmp     short loc_180084C5A
0x180084c53  lea     rdx, aSingletracefil_0; "    <SingleTraceFile>true</SingleTraceF"...
0x180084c5a  mov     rcx, rdi; this
0x180084c5d  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084c62  lea     rdx, aUtcoffset_0; "    <UtcOffset>"
0x180084c69  mov     rcx, rdi; this
0x180084c6c  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084c71  mov     edx, r14d; int
0x180084c74  mov     rcx, rdi; this
0x180084c77  call    ?WriteUtcOffset@XmlReporter@@IEAAKJ@Z; XmlReporter::WriteUtcOffset(long)
0x180084c7c  lea     rdx, aUtcoffset; "</UtcOffset>\n"
0x180084c83  mov     rcx, rdi; this
0x180084c86  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084c8b  lea     rdx, aReportinformat; "  </ReportInformation>\n"
0x180084c92  mov     rcx, rdi; this
0x180084c95  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084c9a  mov     edx, 1; unsigned int
0x180084c9f  mov     rcx, rdi; this
0x180084ca2  lea     r8d, [rdx+4]; unsigned int
0x180084ca6  call    ?UpdateReportState@XmlReporter@@IEAAKKK@Z; XmlReporter::UpdateReportState(ulong,ulong)
0x180084cab  mov     ebx, eax
0x180084cad  mov     eax, ebx
0x180084caf  mov     rcx, [rbp+var_10]
0x180084cb3  xor     rcx, rsp; StackCookie
0x180084cb6  call    __security_check_cookie
0x180084cbb  mov     rbx, [rsp+60h+arg_10]
0x180084cc3  add     rsp, 60h
0x180084cc7  pop     r15
0x180084cc9  pop     r14
0x180084ccb  pop     rdi
0x180084ccc  pop     rsi
0x180084ccd  pop     rbp
0x180084cce  retn
```
