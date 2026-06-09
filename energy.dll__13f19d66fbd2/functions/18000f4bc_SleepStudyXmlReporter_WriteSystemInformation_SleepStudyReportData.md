# SleepStudyXmlReporter::WriteSystemInformation(SleepStudyReportData &)

- ea: `0x18000f4bc`
- end: `0x18000f6f1`
- name: `?WriteSystemInformation@SleepStudyXmlReporter@@IEAAKAEAUSleepStudyReportData@@@Z`
- size: `565`
- prototype: `unsigned int __fastcall(SleepStudyXmlReporter *__hidden this, struct SleepStudyReportData *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180084900`

## callees

- `0x180009b5c`
- `0x18000f4bc`
- `0x18001107c`
- `0x180012020`
- `0x18001c8cc`
- `0x180043b14`
- `0x1800465cc`
- `0x1800465e0`

## string_xrefs

- `0x18000f50d`: `    <ComputerName>`
- `0x18000f5a0`: `</SystemProductName>\n`
- `0x18000f534`: `</ComputerName>\n`
- `0x18000f579`: `    <SystemProductName>`

## pseudocode

```c
unsigned int __fastcall SleepStudyXmlReporter::WriteSystemInformation(
        SleepStudyXmlReporter *this,
        struct SleepStudyReportData *a2)
{
  XmlReporter *v5; // rbx
  XmlReporter *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  _BYTE v13[40]; // [rsp+20h] [rbp-28h] BYREF

  if ( *((_DWORD *)this + 6) != 5 )
    return 1627;
  v5 = (SleepStudyXmlReporter *)((char *)this + 16);
  v6 = (SleepStudyXmlReporter *)((char *)this + 16);
  if ( (*((_BYTE *)a2 + 392) & 1) == 0 )
    return XmlReporter::UpdateReportState(v6, 5u, 6u);
  XmlReporter::WriteRawString(v6, L"  <SystemInformation>\n");
  XmlReporter::WriteRawString(v5, L"    <ComputerName>");
  v7 = std::wstring::wstring((__int64)v13, (_QWORD *)a2 + 1);
  XmlReporter::WriteStlString(v5, v7);
  XmlReporter::WriteRawString(v5, L"</ComputerName>\n");
  XmlReporter::WriteRawString(v5, L"    <SystemManufacturer>");
  v8 = std::wstring::wstring((__int64)v13, (_QWORD *)a2 + 5);
  XmlReporter::WriteStlString(v5, v8);
  XmlReporter::WriteRawString(v5, L"</SystemManufacturer>\n");
  XmlReporter::WriteRawString(v5, L"    <SystemProductName>");
  v9 = std::wstring::wstring((__int64)v13, (_QWORD *)a2 + 9);
  XmlReporter::WriteStlString(v5, v9);
  XmlReporter::WriteRawString(v5, L"</SystemProductName>\n");
  XmlReporter::WriteRawString(v5, L"    <BIOSDate>");
  v10 = std::wstring::wstring((__int64)v13, (_QWORD *)a2 + 13);
  XmlReporter::WriteStlString(v5, v10);
  XmlReporter::WriteRawString(v5, L"</BIOSDate>\n");
  XmlReporter::WriteRawString(v5, L"    <BIOSVersion>");
  v11 = std::wstring::wstring((__int64)v13, (_QWORD *)a2 + 17);
  XmlReporter::WriteStlString(v5, v11);
  XmlReporter::WriteRawString(v5, L"</BIOSVersion>\n");
  XmlReporter::WriteRawString(v5, L"    <OSBuild>");
  if ( *((_QWORD *)a2 + 24) )
  {
    v12 = std::wstring::wstring((__int64)v13, (_QWORD *)a2 + 22);
    XmlReporter::WriteStlString(v5, v12);
  }
  else
  {
    XmlReporter::WriteInteger(v5, *((_DWORD *)a2 + 42));
  }
  XmlReporter::WriteRawString(v5, L"</OSBuild>\n");
  XmlReporter::WriteRawString(v5, L"    <PlatformRole>");
  SleepStudyXmlReporter::WritePlatformRole(this, *((enum _POWER_PLATFORM_ROLE *)a2 + 60));
  XmlReporter::WriteRawString(v5, L"</PlatformRole>\n");
  XmlReporter::WriteRawString(v5, L"    <ConnectedStandby>");
  XmlReporter::WriteBoolean(v5, *((_BYTE *)a2 + 244));
  XmlReporter::WriteRawString(v5, L"</ConnectedStandby>\n");
  XmlReporter::WriteRawString(v5, L"  </SystemInformation>\n");
  if ( *((_DWORD *)this + 6) != 5 )
    return 1627;
  *((_DWORD *)this + 6) = 6;
  return 0;
}

```

## disassembly

```asm
0x18000f4bc  push    rbp
0x18000f4be  push    rbx
0x18000f4bf  push    rsi
0x18000f4c0  push    rdi
0x18000f4c1  mov     rbp, rsp
0x18000f4c4  sub     rsp, 48h
0x18000f4c8  cmp     dword ptr [rcx+18h], 5
0x18000f4cc  mov     rsi, rdx
0x18000f4cf  mov     rdi, rcx
0x18000f4d2  jz      short loc_18000F4DE
0x18000f4d4  mov     eax, 65Bh
0x18000f4d9  jmp     loc_18000F6E8
0x18000f4de  test    byte ptr [rdx+188h], 1
0x18000f4e5  lea     rbx, [rcx+10h]
0x18000f4e9  mov     rcx, rbx; this
0x18000f4ec  jnz     short loc_18000F501
0x18000f4ee  mov     edx, 5; unsigned int
0x18000f4f3  lea     r8d, [rdx+1]; unsigned int
0x18000f4f7  call    ?UpdateReportState@XmlReporter@@IEAAKKK@Z; XmlReporter::UpdateReportState(ulong,ulong)
0x18000f4fc  jmp     loc_18000F6E8
0x18000f501  lea     rdx, aSysteminformat; "  <SystemInformation>\n"
0x18000f508  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f50d  lea     rdx, aComputername; "    <ComputerName>"
0x18000f514  mov     rcx, rbx; this
0x18000f517  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f51c  lea     rdx, [rsi+8]
0x18000f520  lea     rcx, [rbp+var_28]
0x18000f524  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f529  mov     rdx, rax
0x18000f52c  mov     rcx, rbx
0x18000f52f  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x18000f534  lea     rdx, aComputername_1; "</ComputerName>\n"
0x18000f53b  mov     rcx, rbx; this
0x18000f53e  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f543  lea     rdx, aSystemmanufact; "    <SystemManufacturer>"
0x18000f54a  mov     rcx, rbx; this
0x18000f54d  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f552  lea     rdx, [rsi+28h]
0x18000f556  lea     rcx, [rbp+var_28]
0x18000f55a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f55f  mov     rdx, rax
0x18000f562  mov     rcx, rbx
0x18000f565  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x18000f56a  lea     rdx, aSystemmanufact_1; "</SystemManufacturer>\n"
0x18000f571  mov     rcx, rbx; this
0x18000f574  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f579  lea     rdx, aSystemproductn_1; "    <SystemProductName>"
0x18000f580  mov     rcx, rbx; this
0x18000f583  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f588  lea     rdx, [rsi+48h]
0x18000f58c  lea     rcx, [rbp+var_28]
0x18000f590  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f595  mov     rdx, rax
0x18000f598  mov     rcx, rbx
0x18000f59b  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x18000f5a0  lea     rdx, aSystemproductn; "</SystemProductName>\n"
0x18000f5a7  mov     rcx, rbx; this
0x18000f5aa  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f5af  lea     rdx, aBiosdate_0; "    <BIOSDate>"
0x18000f5b6  mov     rcx, rbx; this
0x18000f5b9  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f5be  lea     rdx, [rsi+68h]
0x18000f5c2  lea     rcx, [rbp+var_28]
0x18000f5c6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f5cb  mov     rdx, rax
0x18000f5ce  mov     rcx, rbx
0x18000f5d1  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x18000f5d6  lea     rdx, aBiosdate_1; "</BIOSDate>\n"
0x18000f5dd  mov     rcx, rbx; this
0x18000f5e0  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f5e5  lea     rdx, aBiosversion_0; "    <BIOSVersion>"
0x18000f5ec  mov     rcx, rbx; this
0x18000f5ef  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f5f4  lea     rdx, [rsi+88h]
0x18000f5fb  lea     rcx, [rbp+var_28]
0x18000f5ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f604  mov     rdx, rax
0x18000f607  mov     rcx, rbx
0x18000f60a  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x18000f60f  lea     rdx, aBiosversion_2; "</BIOSVersion>\n"
0x18000f616  mov     rcx, rbx; this
0x18000f619  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f61e  lea     rdx, aOsbuild; "    <OSBuild>"
0x18000f625  mov     rcx, rbx; this
0x18000f628  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f62d  lea     rdx, [rsi+0B0h]
0x18000f634  cmp     qword ptr [rdx+10h], 0
0x18000f639  jnz     short loc_18000F64B
0x18000f63b  mov     edx, [rsi+0A8h]; unsigned int
0x18000f641  mov     rcx, rbx; this
0x18000f644  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x18000f649  jmp     short loc_18000F65F
0x18000f64b  lea     rcx, [rbp+var_28]
0x18000f64f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f654  mov     rdx, rax
0x18000f657  mov     rcx, rbx
0x18000f65a  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x18000f65f  lea     rdx, aOsbuild_0; "</OSBuild>\n"
0x18000f666  mov     rcx, rbx; this
0x18000f669  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f66e  lea     rdx, aPlatformrole; "    <PlatformRole>"
0x18000f675  mov     rcx, rbx; this
0x18000f678  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f67d  mov     edx, [rsi+0F0h]; enum _POWER_PLATFORM_ROLE
0x18000f683  mov     rcx, rdi; this
0x18000f686  call    ?WritePlatformRole@SleepStudyXmlReporter@@IEAAKW4_POWER_PLATFORM_ROLE@@@Z; SleepStudyXmlReporter::WritePlatformRole(_POWER_PLATFORM_ROLE)
0x18000f68b  lea     rdx, aPlatformrole_0; "</PlatformRole>\n"
0x18000f692  mov     rcx, rbx; this
0x18000f695  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f69a  lea     rdx, aConnectedstand; "    <ConnectedStandby>"
0x18000f6a1  mov     rcx, rbx; this
0x18000f6a4  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f6a9  mov     dl, [rsi+0F4h]; unsigned __int8
0x18000f6af  mov     rcx, rbx; this
0x18000f6b2  call    ?WriteBoolean@XmlReporter@@IEAAKE@Z; XmlReporter::WriteBoolean(uchar)
0x18000f6b7  lea     rdx, aConnectedstand_1; "</ConnectedStandby>\n"
0x18000f6be  mov     rcx, rbx; this
0x18000f6c1  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f6c6  lea     rdx, aSysteminformat_0; "  </SystemInformation>\n"
0x18000f6cd  mov     rcx, rbx; this
0x18000f6d0  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f6d5  cmp     dword ptr [rdi+18h], 5
0x18000f6d9  jnz     loc_18000F4D4
0x18000f6df  mov     dword ptr [rdi+18h], 6
0x18000f6e6  xor     eax, eax
0x18000f6e8  add     rsp, 48h
0x18000f6ec  pop     rdi
0x18000f6ed  pop     rsi
0x18000f6ee  pop     rbx
0x18000f6ef  pop     rbp
0x18000f6f0  retn
```
