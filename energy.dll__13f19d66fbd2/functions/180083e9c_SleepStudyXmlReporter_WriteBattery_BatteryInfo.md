# SleepStudyXmlReporter::WriteBattery(BatteryInfo &)

- ea: `0x180083e9c`
- end: `0x180084192`
- name: `?WriteBattery@SleepStudyXmlReporter@@IEAAKAEAUBatteryInfo@@@Z`
- size: `758`
- prototype: `unsigned int __fastcall(SleepStudyXmlReporter *__hidden this, struct BatteryInfo *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x180083dec`

## callees

- `0x180009b5c`
- `0x18001107c`
- `0x180012020`
- `0x18001c8cc`
- `0x18001f17c`
- `0x18001fcac`
- `0x180020208`
- `0x180025c30`
- `0x180035934`
- `0x180036058`
- `0x18004450c`
- `0x1800465cc`
- `0x1800465e0`
- `0x180083e9c`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180083fcd`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180083fec`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180083fcd`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180083fec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SleepStudyXmlReporter::WriteBattery(SleepStudyXmlReporter *this, struct BatteryInfo *a2)
{
  unsigned int updated; // ebx
  XmlReporter *v5; // rdi
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD v15[4]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v16[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[232]; // [rsp+48h] [rbp-B8h] BYREF

  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v16);
  if ( *((_DWORD *)this + 6) == 12 )
  {
    v5 = (SleepStudyXmlReporter *)((char *)this + 16);
    XmlReporter::WriteRawString(v5, L"    <Battery>\n");
    XmlReporter::WriteRawString(v5, L"      <Id>");
    v6 = (_QWORD *)std::wstring::wstring((__int64)v15, a2);
    XmlReporter::WriteStlString(v5, v6);
    XmlReporter::WriteRawString(v5, L"</Id>\n");
    XmlReporter::WriteRawString(v5, L"      <Manufacturer>");
    v7 = (_QWORD *)std::wstring::wstring((__int64)v15, (_QWORD *)a2 + 8);
    XmlReporter::WriteStlString(v5, v7);
    XmlReporter::WriteRawString(v5, L"</Manufacturer>\n");
    XmlReporter::WriteRawString(v5, L"      <SerialNumber>");
    v8 = (_QWORD *)std::wstring::wstring((__int64)v15, (_QWORD *)a2 + 12);
    XmlReporter::WriteStlString(v5, v8);
    XmlReporter::WriteRawString(v5, L"</SerialNumber>\n");
    if ( (unsigned __int8)(*((_BYTE *)a2 + 184) - 1) <= 0x1Eu && (unsigned __int8)(*((_BYTE *)a2 + 185) - 1) <= 0xBu )
    {
      v9 = std::basic_ostream<unsigned short>::operator<<(v16, *((unsigned __int16 *)a2 + 93));
      v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v9, (__int64)L"-");
      v11 = std::basic_ostream<unsigned short>::operator<<(v10, *((unsigned __int8 *)a2 + 185));
      v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, (__int64)L"-");
      std::basic_ostream<unsigned short>::operator<<(v12, *((unsigned __int8 *)a2 + 184));
    }
    XmlReporter::WriteRawString(v5, L"      <ManufactureDate>");
    std::basic_stringbuf<unsigned short>::str(v17, v15);
    XmlReporter::WriteStlString(v5, v15);
    XmlReporter::WriteRawString(v5, L"</ManufactureDate>\n");
    XmlReporter::WriteRawString(v5, L"      <Chemistry>");
    v13 = std::string::string(v15, (char *)a2 + 128);
    XmlReporter::WriteStlString(v5, v13);
    XmlReporter::WriteRawString(v5, L"</Chemistry>\n");
    XmlReporter::WriteRawString(v5, L"      <LongTerm>");
    XmlReporter::WriteBoolean(v5, ~(*((_DWORD *)a2 + 42) >> 29) & 1);
    XmlReporter::WriteRawString(v5, L"</LongTerm>\n");
    XmlReporter::WriteRawString(v5, L"      <RelativeCapacity>");
    XmlReporter::WriteBoolean(v5, (*((_DWORD *)a2 + 42) & 0x40000000) != 0);
    XmlReporter::WriteRawString(v5, L"</RelativeCapacity>\n");
    XmlReporter::WriteRawString(v5, L"      <DesignCapacity>");
    XmlReporter::WriteInteger(v5, *((_DWORD *)a2 + 44));
    XmlReporter::WriteRawString(v5, L"</DesignCapacity>\n");
    XmlReporter::WriteRawString(v5, L"      <FullChargeCapacity>");
    XmlReporter::WriteInteger(v5, *((_DWORD *)a2 + 45));
    XmlReporter::WriteRawString(v5, L"</FullChargeCapacity>\n");
    XmlReporter::WriteRawString(v5, L"      <CycleCount>");
    XmlReporter::WriteInteger(v5, *((_DWORD *)a2 + 43));
    XmlReporter::WriteRawString(v5, L"</CycleCount>\n");
    XmlReporter::WriteRawString(v5, L"    </Battery>\n");
    updated = XmlReporter::UpdateReportState(v5, 12, 12);
  }
  else
  {
    updated = 1627;
  }
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v16);
  return updated;
}

```

## disassembly

```asm
0x180083e9c  mov     [rsp-8+arg_8], rbx
0x180083ea1  mov     [rsp-8+arg_10], rdi
0x180083ea6  push    rbp
0x180083ea7  lea     rbp, [rsp-30h]
0x180083eac  sub     rsp, 130h
0x180083eb3  mov     rbx, rdx
0x180083eb6  mov     rdi, rcx
0x180083eb9  lea     rcx, [rsp+130h+var_F0]
0x180083ebe  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180083ec3  nop
0x180083ec4  cmp     dword ptr [rdi+18h], 0Ch
0x180083ec8  jz      short loc_180083ED4
0x180083eca  mov     ebx, 65Bh
0x180083ecf  jmp     loc_180084171
0x180083ed4  add     rdi, 10h
0x180083ed8  lea     rdx, aBattery_1; "    <Battery>\n"
0x180083edf  mov     rcx, rdi; this
0x180083ee2  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180083ee7  lea     rdx, aId_2; "      <Id>"
0x180083eee  mov     rcx, rdi; this
0x180083ef1  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180083ef6  mov     rdx, rbx
0x180083ef9  lea     rcx, [rsp+130h+var_110]
0x180083efe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180083f03  mov     rdx, rax
0x180083f06  mov     rcx, rdi
0x180083f09  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x180083f0e  lea     rdx, aId_4; "</Id>\n"
0x180083f15  mov     rcx, rdi; this
0x180083f18  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180083f1d  lea     rdx, aManufacturer; "      <Manufacturer>"
0x180083f24  mov     rcx, rdi; this
0x180083f27  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180083f2c  lea     rdx, [rbx+40h]
0x180083f30  lea     rcx, [rsp+130h+var_110]
0x180083f35  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180083f3a  mov     rdx, rax
0x180083f3d  mov     rcx, rdi
0x180083f40  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x180083f45  lea     rdx, aManufacturer_0; "</Manufacturer>\n"
0x180083f4c  mov     rcx, rdi; this
0x180083f4f  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180083f54  lea     rdx, aSerialnumber_1; "      <SerialNumber>"
0x180083f5b  mov     rcx, rdi; this
0x180083f5e  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180083f63  lea     rdx, [rbx+60h]
0x180083f67  lea     rcx, [rsp+130h+var_110]
0x180083f6c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180083f71  mov     rdx, rax
0x180083f74  mov     rcx, rdi
0x180083f77  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x180083f7c  lea     rdx, aSerialnumber_0; "</SerialNumber>\n"
0x180083f83  mov     rcx, rdi; this
0x180083f86  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180083f8b  mov     al, [rbx+0B8h]
0x180083f91  dec     al
0x180083f93  cmp     al, 1Eh
0x180083f95  ja      short loc_180083FF2
0x180083f97  mov     al, [rbx+0B9h]
0x180083f9d  dec     al
0x180083f9f  cmp     al, 0Bh
0x180083fa1  ja      short loc_180083FF2
0x180083fa3  movzx   edx, word ptr [rbx+0BAh]
0x180083faa  lea     rcx, [rsp+130h+var_F0]
0x180083faf  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x180083fb4  mov     rcx, rax
0x180083fb7  lea     rdx, asc_1800A008C; "-"
0x180083fbe  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180083fc3  movzx   edx, byte ptr [rbx+0B9h]
0x180083fca  mov     rcx, rax
0x180083fcd  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x180083fd3  mov     rcx, rax
0x180083fd6  lea     rdx, asc_1800A008C; "-"
0x180083fdd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180083fe2  movzx   edx, byte ptr [rbx+0B8h]
0x180083fe9  mov     rcx, rax
0x180083fec  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x180083ff2  lea     rdx, aManufacturedat; "      <ManufactureDate>"
0x180083ff9  mov     rcx, rdi; this
0x180083ffc  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084001  lea     rdx, [rsp+130h+var_110]
0x180084006  lea     rcx, [rsp+130h+var_E8]
0x18008400b  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180084010  lea     rdx, [rsp+130h+var_110]
0x180084015  mov     rcx, rdi
0x180084018  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x18008401d  lea     rdx, aManufacturedat_1; "</ManufactureDate>\n"
0x180084024  mov     rcx, rdi; this
0x180084027  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008402c  lea     rdx, aChemistry; "      <Chemistry>"
0x180084033  mov     rcx, rdi; this
0x180084036  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008403b  lea     rdx, [rbx+80h]
0x180084042  lea     rcx, [rsp+130h+var_110]
0x180084047  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18008404c  mov     rdx, rax
0x18008404f  mov     rcx, rdi
0x180084052  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; XmlReporter::WriteStlString(std::string)
0x180084057  lea     rdx, aChemistry_0; "</Chemistry>\n"
0x18008405e  mov     rcx, rdi; this
0x180084061  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084066  lea     rdx, aLongterm_0; "      <LongTerm>"
0x18008406d  mov     rcx, rdi; this
0x180084070  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084075  mov     edx, [rbx+0A8h]
0x18008407b  shr     edx, 1Dh
0x18008407e  not     dl
0x180084080  and     dl, 1; unsigned __int8
0x180084083  mov     rcx, rdi; this
0x180084086  call    ?WriteBoolean@XmlReporter@@IEAAKE@Z; XmlReporter::WriteBoolean(uchar)
0x18008408b  lea     rdx, aLongterm; "</LongTerm>\n"
0x180084092  mov     rcx, rdi; this
0x180084095  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008409a  lea     rdx, aRelativecapaci_1; "      <RelativeCapacity>"
0x1800840a1  mov     rcx, rdi; this
0x1800840a4  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800840a9  mov     edx, [rbx+0A8h]
0x1800840af  shr     edx, 1Eh
0x1800840b2  and     dl, 1; unsigned __int8
0x1800840b5  mov     rcx, rdi; this
0x1800840b8  call    ?WriteBoolean@XmlReporter@@IEAAKE@Z; XmlReporter::WriteBoolean(uchar)
0x1800840bd  lea     rdx, aRelativecapaci_0; "</RelativeCapacity>\n"
0x1800840c4  mov     rcx, rdi; this
0x1800840c7  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800840cc  lea     rdx, aDesigncapacity; "      <DesignCapacity>"
0x1800840d3  mov     rcx, rdi; this
0x1800840d6  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800840db  mov     edx, [rbx+0B0h]; unsigned int
0x1800840e1  mov     rcx, rdi; this
0x1800840e4  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x1800840e9  lea     rdx, aDesigncapacity_1; "</DesignCapacity>\n"
0x1800840f0  mov     rcx, rdi; this
0x1800840f3  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800840f8  lea     rdx, aFullchargecapa_2; "      <FullChargeCapacity>"
0x1800840ff  mov     rcx, rdi; this
0x180084102  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084107  mov     edx, [rbx+0B4h]; unsigned int
0x18008410d  mov     rcx, rdi; this
0x180084110  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180084115  lea     rdx, aFullchargecapa_4; "</FullChargeCapacity>\n"
0x18008411c  mov     rcx, rdi; this
0x18008411f  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084124  lea     rdx, aCyclecount_0; "      <CycleCount>"
0x18008412b  mov     rcx, rdi; this
0x18008412e  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084133  mov     edx, [rbx+0ACh]; unsigned int
0x180084139  mov     rcx, rdi; this
0x18008413c  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180084141  lea     rdx, aCyclecount; "</CycleCount>\n"
0x180084148  mov     rcx, rdi; this
0x18008414b  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180084150  lea     rdx, aBattery; "    </Battery>\n"
0x180084157  mov     rcx, rdi; this
0x18008415a  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008415f  mov     edx, 0Ch; unsigned int
0x180084164  mov     r8d, edx; unsigned int
0x180084167  mov     rcx, rdi; this
0x18008416a  call    ?UpdateReportState@XmlReporter@@IEAAKKK@Z; XmlReporter::UpdateReportState(ulong,ulong)
0x18008416f  mov     ebx, eax
0x180084171  lea     rcx, [rsp+130h+var_F0]
0x180084176  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x18008417b  mov     eax, ebx
0x18008417d  lea     r11, [rsp+130h+var_s0]
0x180084185  mov     rbx, [r11+18h]
0x180084189  mov     rdi, [r11+20h]
0x18008418d  mov     rsp, r11
0x180084190  pop     rbp
0x180084191  retn
```
