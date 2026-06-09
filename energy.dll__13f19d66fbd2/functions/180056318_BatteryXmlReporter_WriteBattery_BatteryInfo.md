# BatteryXmlReporter::WriteBattery(BatteryInfo &)

- ea: `0x180056318`
- end: `0x18005660a`
- name: `?WriteBattery@BatteryXmlReporter@@IEAAKAEAUBatteryInfo@@@Z`
- size: `754`
- prototype: `unsigned int __fastcall(BatteryXmlReporter *__hidden this, struct BatteryInfo *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x180056278`

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
- `0x180056318`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180056445`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180056464`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180056445`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180056464`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BatteryXmlReporter::WriteBattery(BatteryXmlReporter *this, struct BatteryInfo *a2)
{
  unsigned int updated; // ebx
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  _QWORD v14[4]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v15[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[232]; // [rsp+48h] [rbp-B8h] BYREF

  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v15);
  if ( *((_DWORD *)this + 2) == 7 )
  {
    XmlReporter::WriteRawString(this, L"    <Battery>\n");
    XmlReporter::WriteRawString(this, L"      <Id>");
    v5 = (_QWORD *)std::wstring::wstring((__int64)v14, a2);
    XmlReporter::WriteStlString(this, v5);
    XmlReporter::WriteRawString(this, L"</Id>\n");
    XmlReporter::WriteRawString(this, L"      <Manufacturer>");
    v6 = (_QWORD *)std::wstring::wstring((__int64)v14, (_QWORD *)a2 + 8);
    XmlReporter::WriteStlString(this, v6);
    XmlReporter::WriteRawString(this, L"</Manufacturer>\n");
    XmlReporter::WriteRawString(this, L"      <SerialNumber>");
    v7 = (_QWORD *)std::wstring::wstring((__int64)v14, (_QWORD *)a2 + 12);
    XmlReporter::WriteStlString(this, v7);
    XmlReporter::WriteRawString(this, L"</SerialNumber>\n");
    if ( (unsigned __int8)(*((_BYTE *)a2 + 184) - 1) <= 0x1Eu && (unsigned __int8)(*((_BYTE *)a2 + 185) - 1) <= 0xBu )
    {
      v8 = std::basic_ostream<unsigned short>::operator<<(v15, *((unsigned __int16 *)a2 + 93));
      v9 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, (__int64)L"-");
      v10 = std::basic_ostream<unsigned short>::operator<<(v9, *((unsigned __int8 *)a2 + 185));
      v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v10, (__int64)L"-");
      std::basic_ostream<unsigned short>::operator<<(v11, *((unsigned __int8 *)a2 + 184));
    }
    XmlReporter::WriteRawString(this, L"      <ManufactureDate>");
    std::basic_stringbuf<unsigned short>::str(v16, v14);
    XmlReporter::WriteStlString(this, v14);
    XmlReporter::WriteRawString(this, L"</ManufactureDate>\n");
    XmlReporter::WriteRawString(this, L"      <Chemistry>");
    v12 = std::string::string(v14, (char *)a2 + 128);
    XmlReporter::WriteStlString(this, v12);
    XmlReporter::WriteRawString(this, L"</Chemistry>\n");
    XmlReporter::WriteRawString(this, L"      <LongTerm>");
    XmlReporter::WriteBoolean(this, ~(*((_DWORD *)a2 + 42) >> 29) & 1);
    XmlReporter::WriteRawString(this, L"</LongTerm>\n");
    XmlReporter::WriteRawString(this, L"      <RelativeCapacity>");
    XmlReporter::WriteBoolean(this, (*((_DWORD *)a2 + 42) & 0x40000000) != 0);
    XmlReporter::WriteRawString(this, L"</RelativeCapacity>\n");
    XmlReporter::WriteRawString(this, L"      <DesignCapacity>");
    XmlReporter::WriteInteger(this, *((_DWORD *)a2 + 44));
    XmlReporter::WriteRawString(this, L"</DesignCapacity>\n");
    XmlReporter::WriteRawString(this, L"      <FullChargeCapacity>");
    XmlReporter::WriteInteger(this, *((_DWORD *)a2 + 45));
    XmlReporter::WriteRawString(this, L"</FullChargeCapacity>\n");
    XmlReporter::WriteRawString(this, L"      <CycleCount>");
    XmlReporter::WriteInteger(this, *((_DWORD *)a2 + 43));
    XmlReporter::WriteRawString(this, L"</CycleCount>\n");
    XmlReporter::WriteRawString(this, L"    </Battery>\n");
    updated = XmlReporter::UpdateReportState(this, 7, 7);
  }
  else
  {
    updated = 1627;
  }
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v15);
  return updated;
}

```

## disassembly

```asm
0x180056318  mov     [rsp-8+arg_8], rbx
0x18005631d  mov     [rsp-8+arg_10], rdi
0x180056322  push    rbp
0x180056323  lea     rbp, [rsp-30h]
0x180056328  sub     rsp, 130h
0x18005632f  mov     rdi, rdx
0x180056332  mov     rbx, rcx
0x180056335  lea     rcx, [rsp+130h+var_F0]
0x18005633a  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18005633f  nop
0x180056340  cmp     dword ptr [rbx+8], 7
0x180056344  jz      short loc_180056350
0x180056346  mov     ebx, 65Bh
0x18005634b  jmp     loc_1800565E9
0x180056350  lea     rdx, aBattery_1; "    <Battery>\n"
0x180056357  mov     rcx, rbx; this
0x18005635a  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18005635f  lea     rdx, aId_2; "      <Id>"
0x180056366  mov     rcx, rbx; this
0x180056369  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18005636e  mov     rdx, rdi
0x180056371  lea     rcx, [rsp+130h+var_110]
0x180056376  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005637b  mov     rdx, rax
0x18005637e  mov     rcx, rbx
0x180056381  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x180056386  lea     rdx, aId_4; "</Id>\n"
0x18005638d  mov     rcx, rbx; this
0x180056390  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056395  lea     rdx, aManufacturer; "      <Manufacturer>"
0x18005639c  mov     rcx, rbx; this
0x18005639f  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800563a4  lea     rdx, [rdi+40h]
0x1800563a8  lea     rcx, [rsp+130h+var_110]
0x1800563ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800563b2  mov     rdx, rax
0x1800563b5  mov     rcx, rbx
0x1800563b8  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x1800563bd  lea     rdx, aManufacturer_0; "</Manufacturer>\n"
0x1800563c4  mov     rcx, rbx; this
0x1800563c7  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800563cc  lea     rdx, aSerialnumber_1; "      <SerialNumber>"
0x1800563d3  mov     rcx, rbx; this
0x1800563d6  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800563db  lea     rdx, [rdi+60h]
0x1800563df  lea     rcx, [rsp+130h+var_110]
0x1800563e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800563e9  mov     rdx, rax
0x1800563ec  mov     rcx, rbx
0x1800563ef  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x1800563f4  lea     rdx, aSerialnumber_0; "</SerialNumber>\n"
0x1800563fb  mov     rcx, rbx; this
0x1800563fe  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056403  mov     al, [rdi+0B8h]
0x180056409  dec     al
0x18005640b  cmp     al, 1Eh
0x18005640d  ja      short loc_18005646A
0x18005640f  mov     al, [rdi+0B9h]
0x180056415  dec     al
0x180056417  cmp     al, 0Bh
0x180056419  ja      short loc_18005646A
0x18005641b  movzx   edx, word ptr [rdi+0BAh]
0x180056422  lea     rcx, [rsp+130h+var_F0]
0x180056427  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x18005642c  mov     rcx, rax
0x18005642f  lea     rdx, asc_1800A008C; "-"
0x180056436  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18005643b  movzx   edx, byte ptr [rdi+0B9h]
0x180056442  mov     rcx, rax
0x180056445  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18005644b  mov     rcx, rax
0x18005644e  lea     rdx, asc_1800A008C; "-"
0x180056455  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18005645a  movzx   edx, byte ptr [rdi+0B8h]
0x180056461  mov     rcx, rax
0x180056464  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18005646a  lea     rdx, aManufacturedat; "      <ManufactureDate>"
0x180056471  mov     rcx, rbx; this
0x180056474  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056479  lea     rdx, [rsp+130h+var_110]
0x18005647e  lea     rcx, [rsp+130h+var_E8]
0x180056483  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180056488  lea     rdx, [rsp+130h+var_110]
0x18005648d  mov     rcx, rbx
0x180056490  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x180056495  lea     rdx, aManufacturedat_1; "</ManufactureDate>\n"
0x18005649c  mov     rcx, rbx; this
0x18005649f  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800564a4  lea     rdx, aChemistry; "      <Chemistry>"
0x1800564ab  mov     rcx, rbx; this
0x1800564ae  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800564b3  lea     rdx, [rdi+80h]
0x1800564ba  lea     rcx, [rsp+130h+var_110]
0x1800564bf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800564c4  mov     rdx, rax
0x1800564c7  mov     rcx, rbx
0x1800564ca  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; XmlReporter::WriteStlString(std::string)
0x1800564cf  lea     rdx, aChemistry_0; "</Chemistry>\n"
0x1800564d6  mov     rcx, rbx; this
0x1800564d9  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800564de  lea     rdx, aLongterm_0; "      <LongTerm>"
0x1800564e5  mov     rcx, rbx; this
0x1800564e8  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800564ed  mov     edx, [rdi+0A8h]
0x1800564f3  shr     edx, 1Dh
0x1800564f6  not     dl
0x1800564f8  and     dl, 1; unsigned __int8
0x1800564fb  mov     rcx, rbx; this
0x1800564fe  call    ?WriteBoolean@XmlReporter@@IEAAKE@Z; XmlReporter::WriteBoolean(uchar)
0x180056503  lea     rdx, aLongterm; "</LongTerm>\n"
0x18005650a  mov     rcx, rbx; this
0x18005650d  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056512  lea     rdx, aRelativecapaci_1; "      <RelativeCapacity>"
0x180056519  mov     rcx, rbx; this
0x18005651c  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056521  mov     edx, [rdi+0A8h]
0x180056527  shr     edx, 1Eh
0x18005652a  and     dl, 1; unsigned __int8
0x18005652d  mov     rcx, rbx; this
0x180056530  call    ?WriteBoolean@XmlReporter@@IEAAKE@Z; XmlReporter::WriteBoolean(uchar)
0x180056535  lea     rdx, aRelativecapaci_0; "</RelativeCapacity>\n"
0x18005653c  mov     rcx, rbx; this
0x18005653f  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056544  lea     rdx, aDesigncapacity; "      <DesignCapacity>"
0x18005654b  mov     rcx, rbx; this
0x18005654e  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056553  mov     edx, [rdi+0B0h]; unsigned int
0x180056559  mov     rcx, rbx; this
0x18005655c  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180056561  lea     rdx, aDesigncapacity_1; "</DesignCapacity>\n"
0x180056568  mov     rcx, rbx; this
0x18005656b  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180056570  lea     rdx, aFullchargecapa_2; "      <FullChargeCapacity>"
0x180056577  mov     rcx, rbx; this
0x18005657a  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18005657f  mov     edx, [rdi+0B4h]; unsigned int
0x180056585  mov     rcx, rbx; this
0x180056588  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x18005658d  lea     rdx, aFullchargecapa_4; "</FullChargeCapacity>\n"
0x180056594  mov     rcx, rbx; this
0x180056597  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18005659c  lea     rdx, aCyclecount_0; "      <CycleCount>"
0x1800565a3  mov     rcx, rbx; this
0x1800565a6  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800565ab  mov     edx, [rdi+0ACh]; unsigned int
0x1800565b1  mov     rcx, rbx; this
0x1800565b4  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x1800565b9  lea     rdx, aCyclecount; "</CycleCount>\n"
0x1800565c0  mov     rcx, rbx; this
0x1800565c3  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800565c8  lea     rdx, aBattery; "    </Battery>\n"
0x1800565cf  mov     rcx, rbx; this
0x1800565d2  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800565d7  mov     edx, 7; unsigned int
0x1800565dc  mov     r8d, edx; unsigned int
0x1800565df  mov     rcx, rbx; this
0x1800565e2  call    ?UpdateReportState@XmlReporter@@IEAAKKK@Z; XmlReporter::UpdateReportState(ulong,ulong)
0x1800565e7  mov     ebx, eax
0x1800565e9  lea     rcx, [rsp+130h+var_F0]
0x1800565ee  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x1800565f3  mov     eax, ebx
0x1800565f5  lea     r11, [rsp+130h+var_s0]
0x1800565fd  mov     rbx, [r11+18h]
0x180056601  mov     rdi, [r11+20h]
0x180056605  mov     rsp, r11
0x180056608  pop     rbp
0x180056609  retn
```
