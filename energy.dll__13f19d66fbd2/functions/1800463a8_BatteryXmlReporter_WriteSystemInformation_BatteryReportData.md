# BatteryXmlReporter::WriteSystemInformation(BatteryReportData &)

- ea: `0x1800463a8`
- end: `0x1800465c5`
- name: `?WriteSystemInformation@BatteryXmlReporter@@IEAAKAEAUBatteryReportData@@@Z`
- size: `541`
- prototype: `unsigned int __fastcall(BatteryXmlReporter *__hidden this, struct BatteryReportData *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800566b4`

## callees

- `0x180009b5c`
- `0x18001107c`
- `0x180012020`
- `0x18001c8cc`
- `0x1800463a8`
- `0x1800465cc`
- `0x1800465e0`
- `0x1800465f8`

## string_xrefs

- `0x1800463dc`: `    <ComputerName>`
- `0x18004646f`: `</SystemProductName>\n`
- `0x180046403`: `</ComputerName>\n`
- `0x180046448`: `    <SystemProductName>`

## pseudocode

```c
unsigned int __fastcall BatteryXmlReporter::WriteSystemInformation(
        BatteryXmlReporter *this,
        struct BatteryReportData *a2)
{
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  _BYTE v11[32]; // [rsp+20h] [rbp-20h] BYREF

  if ( *((_DWORD *)this + 2) != 5 )
    return 1627;
  XmlReporter::WriteRawString(this, L"  <SystemInformation>\n");
  XmlReporter::WriteRawString(this, L"    <ComputerName>");
  v5 = std::wstring::wstring((__int64)v11, (_QWORD *)a2 + 1);
  XmlReporter::WriteStlString(this, v5);
  XmlReporter::WriteRawString(this, L"</ComputerName>\n");
  XmlReporter::WriteRawString(this, L"    <SystemManufacturer>");
  v6 = std::wstring::wstring((__int64)v11, (_QWORD *)a2 + 5);
  XmlReporter::WriteStlString(this, v6);
  XmlReporter::WriteRawString(this, L"</SystemManufacturer>\n");
  XmlReporter::WriteRawString(this, L"    <SystemProductName>");
  v7 = std::wstring::wstring((__int64)v11, (_QWORD *)a2 + 9);
  XmlReporter::WriteStlString(this, v7);
  XmlReporter::WriteRawString(this, L"</SystemProductName>\n");
  XmlReporter::WriteRawString(this, L"    <BIOSDate>");
  v8 = std::wstring::wstring((__int64)v11, (_QWORD *)a2 + 13);
  XmlReporter::WriteStlString(this, v8);
  XmlReporter::WriteRawString(this, L"</BIOSDate>\n");
  XmlReporter::WriteRawString(this, L"    <BIOSVersion>");
  v9 = std::wstring::wstring((__int64)v11, (_QWORD *)a2 + 17);
  XmlReporter::WriteStlString(this, v9);
  XmlReporter::WriteRawString(this, L"</BIOSVersion>\n");
  XmlReporter::WriteRawString(this, L"    <OSBuild>");
  if ( *((_QWORD *)a2 + 24) )
  {
    v10 = std::wstring::wstring((__int64)v11, (_QWORD *)a2 + 22);
    XmlReporter::WriteStlString(this, v10);
  }
  else
  {
    XmlReporter::WriteInteger(this, *((_DWORD *)a2 + 42));
  }
  XmlReporter::WriteRawString(this, L"</OSBuild>\n");
  XmlReporter::WriteRawString(this, L"    <PlatformRole>");
  BatteryXmlReporter::WritePlatformRole(this, *((enum _POWER_PLATFORM_ROLE *)a2 + 60));
  XmlReporter::WriteRawString(this, L"</PlatformRole>\n");
  XmlReporter::WriteRawString(this, L"    <ConnectedStandby>");
  XmlReporter::WriteBoolean(this, *((_BYTE *)a2 + 244));
  XmlReporter::WriteRawString(this, L"</ConnectedStandby>\n");
  XmlReporter::WriteRawString(this, L"  </SystemInformation>\n");
  return XmlReporter::UpdateReportState(this, 5u, 6u);
}

```

## disassembly

```asm
0x1800463a8  mov     [rsp-8+arg_8], rbx
0x1800463ad  mov     [rsp-8+arg_10], rdi
0x1800463b2  push    rbp
0x1800463b3  mov     rbp, rsp
0x1800463b6  sub     rsp, 40h
0x1800463ba  cmp     dword ptr [rcx+8], 5
0x1800463be  mov     rdi, rdx
0x1800463c1  mov     rbx, rcx
0x1800463c4  jz      short loc_1800463D0
0x1800463c6  mov     eax, 65Bh
0x1800463cb  jmp     loc_1800465B5
0x1800463d0  lea     rdx, aSysteminformat; "  <SystemInformation>\n"
0x1800463d7  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800463dc  lea     rdx, aComputername; "    <ComputerName>"
0x1800463e3  mov     rcx, rbx; this
0x1800463e6  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800463eb  lea     rdx, [rdi+8]
0x1800463ef  lea     rcx, [rbp+var_20]
0x1800463f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800463f8  mov     rdx, rax
0x1800463fb  mov     rcx, rbx
0x1800463fe  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x180046403  lea     rdx, aComputername_1; "</ComputerName>\n"
0x18004640a  mov     rcx, rbx; this
0x18004640d  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180046412  lea     rdx, aSystemmanufact; "    <SystemManufacturer>"
0x180046419  mov     rcx, rbx; this
0x18004641c  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180046421  lea     rdx, [rdi+28h]
0x180046425  lea     rcx, [rbp+var_20]
0x180046429  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004642e  mov     rdx, rax
0x180046431  mov     rcx, rbx
0x180046434  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x180046439  lea     rdx, aSystemmanufact_1; "</SystemManufacturer>\n"
0x180046440  mov     rcx, rbx; this
0x180046443  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180046448  lea     rdx, aSystemproductn_1; "    <SystemProductName>"
0x18004644f  mov     rcx, rbx; this
0x180046452  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180046457  lea     rdx, [rdi+48h]
0x18004645b  lea     rcx, [rbp+var_20]
0x18004645f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180046464  mov     rdx, rax
0x180046467  mov     rcx, rbx
0x18004646a  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x18004646f  lea     rdx, aSystemproductn; "</SystemProductName>\n"
0x180046476  mov     rcx, rbx; this
0x180046479  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004647e  lea     rdx, aBiosdate_0; "    <BIOSDate>"
0x180046485  mov     rcx, rbx; this
0x180046488  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004648d  lea     rdx, [rdi+68h]
0x180046491  lea     rcx, [rbp+var_20]
0x180046495  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004649a  mov     rdx, rax
0x18004649d  mov     rcx, rbx
0x1800464a0  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x1800464a5  lea     rdx, aBiosdate_1; "</BIOSDate>\n"
0x1800464ac  mov     rcx, rbx; this
0x1800464af  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800464b4  lea     rdx, aBiosversion_0; "    <BIOSVersion>"
0x1800464bb  mov     rcx, rbx; this
0x1800464be  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800464c3  lea     rdx, [rdi+88h]
0x1800464ca  lea     rcx, [rbp+var_20]
0x1800464ce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800464d3  mov     rdx, rax
0x1800464d6  mov     rcx, rbx
0x1800464d9  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x1800464de  lea     rdx, aBiosversion_2; "</BIOSVersion>\n"
0x1800464e5  mov     rcx, rbx; this
0x1800464e8  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800464ed  lea     rdx, aOsbuild; "    <OSBuild>"
0x1800464f4  mov     rcx, rbx; this
0x1800464f7  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800464fc  lea     rdx, [rdi+0B0h]
0x180046503  cmp     qword ptr [rdx+10h], 0
0x180046508  jnz     short loc_18004651A
0x18004650a  mov     edx, [rdi+0A8h]; unsigned int
0x180046510  mov     rcx, rbx; this
0x180046513  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180046518  jmp     short loc_18004652E
0x18004651a  lea     rcx, [rbp+var_20]
0x18004651e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180046523  mov     rdx, rax
0x180046526  mov     rcx, rbx
0x180046529  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x18004652e  lea     rdx, aOsbuild_0; "</OSBuild>\n"
0x180046535  mov     rcx, rbx; this
0x180046538  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004653d  lea     rdx, aPlatformrole; "    <PlatformRole>"
0x180046544  mov     rcx, rbx; this
0x180046547  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004654c  mov     edx, [rdi+0F0h]; enum _POWER_PLATFORM_ROLE
0x180046552  mov     rcx, rbx; this
0x180046555  call    ?WritePlatformRole@BatteryXmlReporter@@IEAAKW4_POWER_PLATFORM_ROLE@@@Z; BatteryXmlReporter::WritePlatformRole(_POWER_PLATFORM_ROLE)
0x18004655a  lea     rdx, aPlatformrole_0; "</PlatformRole>\n"
0x180046561  mov     rcx, rbx; this
0x180046564  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180046569  lea     rdx, aConnectedstand; "    <ConnectedStandby>"
0x180046570  mov     rcx, rbx; this
0x180046573  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180046578  mov     dl, [rdi+0F4h]; unsigned __int8
0x18004657e  mov     rcx, rbx; this
0x180046581  call    ?WriteBoolean@XmlReporter@@IEAAKE@Z; XmlReporter::WriteBoolean(uchar)
0x180046586  lea     rdx, aConnectedstand_1; "</ConnectedStandby>\n"
0x18004658d  mov     rcx, rbx; this
0x180046590  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180046595  lea     rdx, aSysteminformat_0; "  </SystemInformation>\n"
0x18004659c  mov     rcx, rbx; this
0x18004659f  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800465a4  mov     edx, 5; unsigned int
0x1800465a9  mov     rcx, rbx; this
0x1800465ac  lea     r8d, [rdx+1]; unsigned int
0x1800465b0  call    ?UpdateReportState@XmlReporter@@IEAAKKK@Z; XmlReporter::UpdateReportState(ulong,ulong)
0x1800465b5  mov     rbx, [rsp+40h+arg_8]
0x1800465ba  mov     rdi, [rsp+40h+arg_10]
0x1800465bf  add     rsp, 40h
0x1800465c3  pop     rbp
0x1800465c4  retn
```
