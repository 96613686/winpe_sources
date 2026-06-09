# EnergyXmlReporter::WriteReportHeader(_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong)

- ea: `0x180043fbc`
- end: `0x180044161`
- name: `?WriteReportHeader@EnergyXmlReporter@@QEAAKT_LARGE_INTEGER@@0KK@Z`
- size: `421`
- prototype: `unsigned int __usercall@<eax>(EnergyXmlReporter *__hidden this@<rcx>, union _LARGE_INTEGER@<rdx>, union _LARGE_INTEGER@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f788`

## callees

- `0x18000ff60`
- `0x18001107c`
- `0x180012020`
- `0x18002e418`
- `0x180043fbc`
- `0x18004ca90`
- `0x180090254`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180043ffe`
- `RPCRT4!UuidCreate` at `0x180043ffe`

## string_xrefs

- `0x18004400c`: `<?xml version="1.0" encoding="utf-8"?>\n`
- `0x18004401e`: `<EnergyReport xmlns="http://schemas.microsoft.com/energy/2007">\n`

## pseudocode

```c
__int64 __fastcall EnergyXmlReporter::WriteReportHeader(
        EnergyXmlReporter *this,
        union _LARGE_INTEGER a2,
        union _LARGE_INTEGER a3,
        unsigned int a4,
        unsigned int a5)
{
  bool v5; // zf
  unsigned int v10; // ebp
  UUID Uuid; // [rsp+20h] [rbp-48h] BYREF

  v5 = *((_DWORD *)this + 2) == 1;
  Uuid = 0;
  v10 = 1627;
  if ( v5 && !UuidCreate(&Uuid) )
  {
    XmlReporter::WriteRawString(this, L"<?xml version=\"1.0\" encoding=\"utf-8\"?>\n");
    XmlReporter::WriteRawString(this, L"<EnergyReport xmlns=\"http://schemas.microsoft.com/energy/2007\">\n");
    XmlReporter::WriteRawString(this, L"  <ReportInformation>\n");
    XmlReporter::WriteRawString(this, L"    <ReportGuid>");
    XmlReporter::WriteGuid(this, &Uuid);
    XmlReporter::WriteRawString(this, L"</ReportGuid>\n");
    XmlReporter::WriteRawString(this, L"    <ReportVersion>1.0</ReportVersion>\n");
    XmlReporter::WriteRawString(this, L"    <ScanTime>");
    XmlReporter::WriteDateTime(this, a2);
    XmlReporter::WriteRawString(this, L"</ScanTime>\n");
    XmlReporter::WriteRawString(this, L"    <ScanDuration>");
    XmlReporter::WriteDuration(this, (union _LARGE_INTEGER)(a3.QuadPart - a2.QuadPart));
    XmlReporter::WriteRawString(this, L"</ScanDuration>\n");
    if ( a4 )
    {
      XmlReporter::WriteRawString(this, L"    <DroppedEvents>");
      XmlReporter::WriteInteger(this, a4);
      XmlReporter::WriteRawString(this, L"</DroppedEvents>\n");
    }
    if ( a5 )
    {
      XmlReporter::WriteRawString(this, L"    <DroppedBuffers>");
      XmlReporter::WriteInteger(this, a5);
      XmlReporter::WriteRawString(this, L"</DroppedBuffers>\n");
    }
    XmlReporter::WriteRawString(this, L"  </ReportInformation>\n");
    if ( *((_DWORD *)this + 2) == 1 )
      *((_DWORD *)this + 2) = 5;
    return 0;
  }
  return v10;
}

```

## disassembly

```asm
0x180043fbc  push    rbx
0x180043fbe  push    rbp
0x180043fbf  push    rsi
0x180043fc0  push    rdi
0x180043fc1  push    r14
0x180043fc3  sub     rsp, 40h
0x180043fc7  mov     rax, cs:__security_cookie
0x180043fce  xor     rax, rsp
0x180043fd1  mov     [rsp+68h+var_38], rax
0x180043fd6  cmp     dword ptr [rcx+8], 1
0x180043fda  xorps   xmm0, xmm0
0x180043fdd  movups  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x180043fe2  mov     r14d, r9d
0x180043fe5  mov     rbx, r8
0x180043fe8  mov     rdi, rdx
0x180043feb  mov     rsi, rcx
0x180043fee  mov     ebp, 65Bh
0x180043ff3  jnz     loc_180044147
0x180043ff9  lea     rcx, [rsp+68h+Uuid]; Uuid
0x180043ffe  call    cs:__imp_UuidCreate
0x180044004  test    eax, eax
0x180044006  jnz     loc_180044147
0x18004400c  lea     rdx, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180044013  mov     rcx, rsi; this
0x180044016  sub     rbx, rdi
0x180044019  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004401e  lea     rdx, aEnergyreportXm; "<EnergyReport xmlns=\"http://schemas.mi"...
0x180044025  mov     rcx, rsi; this
0x180044028  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004402d  lea     rdx, aReportinformat_1; "  <ReportInformation>\n"
0x180044034  mov     rcx, rsi; this
0x180044037  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004403c  lea     rdx, aReportguid_1; "    <ReportGuid>"
0x180044043  mov     rcx, rsi; this
0x180044046  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004404b  lea     rdx, [rsp+68h+Uuid]; struct _GUID *
0x180044050  mov     rcx, rsi; this
0x180044053  call    ?WriteGuid@XmlReporter@@IEAAKPEBU_GUID@@@Z; XmlReporter::WriteGuid(_GUID const *)
0x180044058  lea     rdx, aReportguid_0; "</ReportGuid>\n"
0x18004405f  mov     rcx, rsi; this
0x180044062  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180044067  lea     rdx, aReportversion1_0; "    <ReportVersion>1.0</ReportVersion>"...
0x18004406e  mov     rcx, rsi; this
0x180044071  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180044076  lea     rdx, aScantime_0; "    <ScanTime>"
0x18004407d  mov     rcx, rsi; this
0x180044080  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180044085  mov     rdx, rdi; union _LARGE_INTEGER
0x180044088  mov     rcx, rsi; this
0x18004408b  call    ?WriteDateTime@XmlReporter@@IEAAKT_LARGE_INTEGER@@@Z; XmlReporter::WriteDateTime(_LARGE_INTEGER)
0x180044090  lea     rdx, aScantime; "</ScanTime>\n"
0x180044097  mov     rcx, rsi; this
0x18004409a  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004409f  lea     rdx, aScanduration; "    <ScanDuration>"
0x1800440a6  mov     rcx, rsi; this
0x1800440a9  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800440ae  mov     rdx, rbx; union _LARGE_INTEGER
0x1800440b1  mov     rcx, rsi; this
0x1800440b4  call    ?WriteDuration@XmlReporter@@IEAAKT_LARGE_INTEGER@@@Z; XmlReporter::WriteDuration(_LARGE_INTEGER)
0x1800440b9  lea     rdx, aScanduration_0; "</ScanDuration>\n"
0x1800440c0  mov     rcx, rsi; this
0x1800440c3  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800440c8  test    r14d, r14d
0x1800440cb  jz      short loc_1800440F6
0x1800440cd  lea     rdx, aDroppedevents; "    <DroppedEvents>"
0x1800440d4  mov     rcx, rsi; this
0x1800440d7  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800440dc  mov     edx, r14d; unsigned int
0x1800440df  mov     rcx, rsi; this
0x1800440e2  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x1800440e7  lea     rdx, aDroppedevents_0; "</DroppedEvents>\n"
0x1800440ee  mov     rcx, rsi; this
0x1800440f1  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800440f6  mov     ebx, [rsp+68h+arg_20]
0x1800440fd  test    ebx, ebx
0x1800440ff  jz      short loc_180044129
0x180044101  lea     rdx, aDroppedbuffers_0; "    <DroppedBuffers>"
0x180044108  mov     rcx, rsi; this
0x18004410b  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180044110  mov     edx, ebx; unsigned int
0x180044112  mov     rcx, rsi; this
0x180044115  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x18004411a  lea     rdx, aDroppedbuffers; "</DroppedBuffers>\n"
0x180044121  mov     rcx, rsi; this
0x180044124  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180044129  lea     rdx, aReportinformat; "  </ReportInformation>\n"
0x180044130  mov     rcx, rsi; this
0x180044133  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180044138  cmp     dword ptr [rsi+8], 1
0x18004413c  jnz     short loc_180044145
0x18004413e  mov     dword ptr [rsi+8], 5
0x180044145  xor     ebp, ebp
0x180044147  mov     eax, ebp
0x180044149  mov     rcx, [rsp+68h+var_38]
0x18004414e  xor     rcx, rsp; StackCookie
0x180044151  call    __security_check_cookie
0x180044156  add     rsp, 40h
0x18004415a  pop     r14
0x18004415c  pop     rdi
0x18004415d  pop     rsi
0x18004415e  pop     rbp
0x18004415f  pop     rbx
0x180044160  retn
```
