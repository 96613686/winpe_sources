# SleepstudyJsonReporter::WriteSystemInformation(SessionModel::SystemPowerReport const &,SleepstudyJsonWriter &)

- ea: `0x18007e004`
- end: `0x18007e37f`
- name: `?WriteSystemInformation@SleepstudyJsonReporter@@AEAAXAEBVSystemPowerReport@SessionModel@@AEAVSleepstudyJsonWriter@@@Z`
- size: `891`
- prototype: `void(SleepstudyJsonReporter *__hidden this, const struct SessionModel::SystemPowerReport *, struct SleepstudyJsonWriter *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004a360`

## callees

- `0x18000b6f0`
- `0x18001cf30`
- `0x18001f17c`
- `0x18001fcac`
- `0x180020208`
- `0x1800255ac`
- `0x1800256d0`
- `0x18002574c`
- `0x180025898`
- `0x180025c30`
- `0x18002ac08`
- `0x180035934`
- `0x180041e1c`
- `0x180042f00`
- `0x180048f68`
- `0x18004ca90`
- `0x180072bb4`
- `0x180073214`
- `0x1800781f8`
- `0x180078d4c`
- `0x18007b2bc`
- `0x18007dbc0`
- `0x18007e004`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18007e24a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18007e269`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18007e24a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18007e269`

## string_xrefs

- `0x18007e0d0`: `SystemProductName`
- `0x18007e0a4`: `ComputerName`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall SleepstudyJsonReporter::WriteSystemInformation(
        SleepstudyJsonReporter *this,
        const struct SessionModel::SystemPowerReport *a2,
        struct SleepstudyJsonWriter *a3)
{
  const unsigned __int16 *v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rsi
  int *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // ecx
  __int64 v14; // [rsp+28h] [rbp-108h]
  __int64 v15; // [rsp+38h] [rbp-F8h]
  __int64 v16; // [rsp+48h] [rbp-E8h]
  __int64 v17; // [rsp+58h] [rbp-D8h]
  __int64 v18; // [rsp+68h] [rbp-C8h]
  __int64 v19; // [rsp+78h] [rbp-B8h]
  __int64 v20; // [rsp+88h] [rbp-A8h]
  __int64 v21; // [rsp+98h] [rbp-98h]
  bool v22; // [rsp+B0h] [rbp-80h] BYREF
  bool v23; // [rsp+B1h] [rbp-7Fh] BYREF
  _BYTE v24[8]; // [rsp+C0h] [rbp-70h] BYREF
  _BYTE v25[112]; // [rsp+C8h] [rbp-68h] BYREF
  unsigned int v26; // [rsp+138h] [rbp+8h]
  _BYTE v27[32]; // [rsp+1B0h] [rbp+80h] BYREF
  _BYTE v28[32]; // [rsp+1D0h] [rbp+A0h] BYREF
  _BYTE v29[32]; // [rsp+1F0h] [rbp+C0h] BYREF
  _BYTE v30[32]; // [rsp+210h] [rbp+E0h] BYREF
  _BYTE v31[32]; // [rsp+230h] [rbp+100h] BYREF
  unsigned int v32; // [rsp+250h] [rbp+120h] BYREF
  _BYTE v33[16]; // [rsp+258h] [rbp+128h] BYREF
  __int64 v34; // [rsp+268h] [rbp+138h]
  _BYTE v35[16]; // [rsp+278h] [rbp+148h] BYREF
  __int64 v36; // [rsp+288h] [rbp+158h]
  int v37; // [rsp+298h] [rbp+168h]
  char v38; // [rsp+29Ch] [rbp+16Ch]
  int v39[2]; // [rsp+2A0h] [rbp+170h]
  __int64 v40; // [rsp+2A8h] [rbp+178h]
  int v41[2]; // [rsp+2C0h] [rbp+190h] BYREF
  __int64 v42; // [rsp+2D0h] [rbp+1A0h]
  unsigned __int64 v43; // [rsp+2D8h] [rbp+1A8h]

  SessionModel::SystemInformation::SystemInformation((SessionModel::SystemInformation *)v27);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v24);
  SessionModel::SystemInformation::operator=(v27, (char *)a2 + 64);
  if ( v37 < 0 || (unsigned __int64)v37 >= 9 )
    v5 = L"Unknown";
  else
    v5 = (const unsigned __int16 *)(&SleepstudyPlatformRoleStrings)[v37];
  SleepstudyJsonWriter::StartObject(a3, L"SystemInformation");
  v22 = v38 != 0;
  SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"ComputerName", (__int64)v27);
  SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"SystemManufacturer", (__int64)v28);
  SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"SystemProductName", (__int64)v29);
  SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"BIOSDate", (__int64)v30);
  SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"BIOSVersion", (__int64)v31);
  SleepstudyJsonWriter::WriteKeyValue<bool>(a3, L"ConnectedStandby", &v22);
  SleepstudyJsonWriter::WriteKeyValue(a3, L"PlatformRole", v5);
  if ( v34 )
    SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"OSBuild", (__int64)v33);
  else
    SleepstudyJsonWriter::WriteKeyValue<unsigned long const &>(a3, L"OSBuild", &v32);
  if ( v36 )
    SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"OSVer", (__int64)v35);
  else
    SleepstudyJsonWriter::WriteKeyValue(a3, L"OSVer", &qword_18009CA18);
  SleepstudyJsonWriter::EndObject(a3);
  SleepstudyJsonWriter::StartArray(a3, L"Batteries");
  v6 = *(_QWORD *)v39;
  v7 = v40;
  while ( v6 != v7 )
  {
    std::wstring::wstring((__int64)v41, (__int64)&qword_18009CA18);
    std::basic_stringbuf<unsigned short>::_Tidy(v25);
    v8 = v41;
    if ( v43 > 7 )
      v8 = *(int **)v41;
    std::basic_stringbuf<unsigned short>::_Init(v25, v8, v42, v26);
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v41);
    if ( (unsigned __int8)(*(_BYTE *)(v6 + 184) - 1) <= 0x1Eu && (unsigned __int8)(*(_BYTE *)(v6 + 185) - 1) <= 0xBu )
    {
      v9 = std::basic_ostream<unsigned short>::operator<<(v24, *(unsigned __int16 *)(v6 + 186));
      v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v9, (__int64)L"-");
      v11 = std::basic_ostream<unsigned short>::operator<<(v10, *(unsigned __int8 *)(v6 + 185));
      v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, (__int64)L"-");
      std::basic_ostream<unsigned short>::operator<<(v12, *(unsigned __int8 *)(v6 + 184));
    }
    SleepstudyJsonWriter::StartObject(a3, 0);
    v13 = *(_DWORD *)(v6 + 168);
    v22 = (v13 & 0x40000000) != 0;
    v23 = (v13 & 0x20000000) == 0;
    std::basic_stringbuf<unsigned short>::str(v25, v41);
    SleepstudyJsonWriter::WriteKeyValues<std::wstring &,unsigned short const (&)[13],std::wstring &,unsigned short const (&)[13],std::wstring &,unsigned short const (&)[16],std::wstring,unsigned short const (&)[10],std::string &,unsigned short const (&)[9],bool,unsigned short const (&)[17],bool,unsigned short const (&)[15],unsigned long &,unsigned short const (&)[19],unsigned long &,unsigned short const (&)[11],unsigned long &>(
      a3,
      v6 + 176,
      v6,
      v6 + 96,
      v6 + 64,
      v14,
      v6 + 96,
      v15,
      (__int64)v41,
      v16,
      v6 + 128,
      v17,
      &v23,
      v18,
      &v22,
      v19,
      (unsigned int *)(v6 + 176),
      v20,
      (unsigned int *)(v6 + 180),
      v21,
      (unsigned int *)(v6 + 172));
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v41);
    SleepstudyJsonWriter::EndObject(a3);
    v6 += 192;
  }
  SleepstudyJsonWriter::EndArray(a3);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v24);
  SessionModel::SystemInformation::~SystemInformation((SessionModel::SystemInformation *)v27);
}

```

## disassembly

```asm
0x18007e004  mov     [rsp-8+arg_0], rbx
0x18007e009  push    rbp
0x18007e00a  push    rsi
0x18007e00b  push    rdi
0x18007e00c  lea     rbp, [rsp-1C0h]
0x18007e014  sub     rsp, 2F0h
0x18007e01b  mov     rax, cs:__security_cookie
0x18007e022  xor     rax, rsp
0x18007e025  mov     [rbp+1D0h+var_20], rax
0x18007e02c  mov     rdi, r8
0x18007e02f  mov     rbx, rdx
0x18007e032  xor     esi, esi
0x18007e034  lea     rcx, [rbp+1D0h+var_150]; this
0x18007e03b  call    ??0SystemInformation@SessionModel@@QEAA@XZ; SessionModel::SystemInformation::SystemInformation(void)
0x18007e040  nop
0x18007e041  lea     rcx, [rbp+1D0h+var_240]
0x18007e045  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18007e04a  nop
0x18007e04b  lea     rdx, [rbx+40h]
0x18007e04f  lea     rcx, [rbp+1D0h+var_150]
0x18007e056  call    ??4SystemInformation@SessionModel@@QEAAAEAU01@AEBU01@@Z; SessionModel::SystemInformation::operator=(SessionModel::SystemInformation const &)
0x18007e05b  movsxd  rax, [rbp+1D0h+var_68]
0x18007e062  test    eax, eax
0x18007e064  js      short loc_18007E07C
0x18007e066  mov     rbx, rax
0x18007e069  cmp     rax, 9
0x18007e06d  jnb     short loc_18007E07C
0x18007e06f  lea     rax, ?SleepstudyPlatformRoleStrings@@3PAPEBGA; ushort const * near * SleepstudyPlatformRoleStrings
0x18007e076  mov     rbx, [rax+rbx*8]
0x18007e07a  jmp     short loc_18007E083
0x18007e07c  lea     rbx, aUnknown_1; "Unknown"
0x18007e083  lea     rdx, aSysteminformat_1; "SystemInformation"
0x18007e08a  mov     rcx, rdi; this
0x18007e08d  call    ?StartObject@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartObject(ushort const *)
0x18007e092  cmp     [rbp+1D0h+var_64], sil
0x18007e099  setnz   byte ptr [rbp+1D0h+var_250]
0x18007e09d  lea     r8, [rbp+1D0h+var_150]
0x18007e0a4  lea     rdx, aComputername_0; "ComputerName"
0x18007e0ab  mov     rcx, rdi; this
0x18007e0ae  call    ??$WriteKeyValue@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SleepstudyJsonWriter@@QEAAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(ushort const *,std::wstring &)
0x18007e0b3  lea     r8, [rbp+1D0h+var_130]
0x18007e0ba  lea     rdx, aSystemmanufact_0; "SystemManufacturer"
0x18007e0c1  mov     rcx, rdi; this
0x18007e0c4  call    ??$WriteKeyValue@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SleepstudyJsonWriter@@QEAAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(ushort const *,std::wstring &)
0x18007e0c9  lea     r8, [rbp+1D0h+var_110]
0x18007e0d0  lea     rdx, aSystemproductn_0; "SystemProductName"
0x18007e0d7  mov     rcx, rdi; this
0x18007e0da  call    ??$WriteKeyValue@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SleepstudyJsonWriter@@QEAAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(ushort const *,std::wstring &)
0x18007e0df  lea     r8, [rbp+1D0h+var_F0]
0x18007e0e6  lea     rdx, aBiosdate; "BIOSDate"
0x18007e0ed  mov     rcx, rdi; this
0x18007e0f0  call    ??$WriteKeyValue@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SleepstudyJsonWriter@@QEAAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(ushort const *,std::wstring &)
0x18007e0f5  lea     r8, [rbp+1D0h+var_D0]
0x18007e0fc  lea     rdx, aBiosversion; "BIOSVersion"
0x18007e103  mov     rcx, rdi; this
0x18007e106  call    ??$WriteKeyValue@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SleepstudyJsonWriter@@QEAAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(ushort const *,std::wstring &)
0x18007e10b  lea     r8, [rbp+1D0h+var_250]
0x18007e10f  lea     rdx, aConnectedstand_0; "ConnectedStandby"
0x18007e116  mov     rcx, rdi; this
0x18007e119  call    ??$WriteKeyValue@_N@SleepstudyJsonWriter@@QEAAXPEBG$$QEA_N@Z; SleepstudyJsonWriter::WriteKeyValue<bool>(ushort const *,bool &&)
0x18007e11e  mov     r8, rbx; unsigned __int16 *
0x18007e121  lea     rdx, aPlatformrole_1; "PlatformRole"
0x18007e128  mov     rcx, rdi; this
0x18007e12b  call    ?WriteKeyValue@SleepstudyJsonWriter@@QEAAXPEBG0@Z; SleepstudyJsonWriter::WriteKeyValue(ushort const *,ushort const *)
0x18007e130  lea     rdx, aOsbuild_1; "OSBuild"
0x18007e137  mov     rcx, rdi; this
0x18007e13a  cmp     [rbp+1D0h+var_98], rsi
0x18007e141  jnz     short loc_18007E151
0x18007e143  lea     r8, [rbp+1D0h+var_B0]
0x18007e14a  call    ??$WriteKeyValue@AEBK@SleepstudyJsonWriter@@QEAAXPEBGAEBK@Z; SleepstudyJsonWriter::WriteKeyValue<ulong const &>(ushort const *,ulong const &)
0x18007e14f  jmp     short loc_18007E15D
0x18007e151  lea     r8, [rbp+1D0h+var_A8]
0x18007e158  call    ??$WriteKeyValue@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SleepstudyJsonWriter@@QEAAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(ushort const *,std::wstring &)
0x18007e15d  lea     rdx, aOsver; "OSVer"
0x18007e164  mov     rcx, rdi; this
0x18007e167  cmp     [rbp+1D0h+var_78], rsi
0x18007e16e  jnz     short loc_18007E17E
0x18007e170  lea     r8, qword_18009CA18; unsigned __int16 *
0x18007e177  call    ?WriteKeyValue@SleepstudyJsonWriter@@QEAAXPEBG0@Z; SleepstudyJsonWriter::WriteKeyValue(ushort const *,ushort const *)
0x18007e17c  jmp     short loc_18007E18A
0x18007e17e  lea     r8, [rbp+1D0h+var_88]
0x18007e185  call    ??$WriteKeyValue@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SleepstudyJsonWriter@@QEAAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(ushort const *,std::wstring &)
0x18007e18a  mov     rcx, rdi; this
0x18007e18d  call    ?EndObject@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndObject(void)
0x18007e192  lea     rdx, aBatteries_0; "Batteries"
0x18007e199  mov     rcx, rdi; this
0x18007e19c  call    ?StartArray@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartArray(ushort const *)
0x18007e1a1  mov     rbx, qword ptr [rbp+1D0h+var_60]
0x18007e1a8  mov     rsi, [rbp+1D0h+var_58]
0x18007e1af  jmp     loc_18007E335
0x18007e1b4  lea     rdx, qword_18009CA18
0x18007e1bb  lea     rcx, [rbp+1D0h+var_40]
0x18007e1c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007e1c7  nop
0x18007e1c8  lea     rcx, [rbp+1D0h+var_238]
0x18007e1cc  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x18007e1d1  lea     rdx, [rbp+1D0h+var_40]
0x18007e1d8  cmp     [rbp+1D0h+var_28], 7
0x18007e1e0  cmova   rdx, qword ptr [rbp+1D0h+var_40]
0x18007e1e8  mov     r9d, [rbp+1D0h+var_1C8]
0x18007e1ec  mov     r8, [rbp+1D0h+var_30]
0x18007e1f3  lea     rcx, [rbp+1D0h+var_238]
0x18007e1f7  call    ?_Init@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXPEBG_KH@Z; std::basic_stringbuf<ushort>::_Init(ushort const *,unsigned __int64,int)
0x18007e1fc  nop
0x18007e1fd  lea     rcx, [rbp+1D0h+var_40]; void *
0x18007e204  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18007e209  mov     al, [rbx+0B8h]
0x18007e20f  dec     al
0x18007e211  cmp     al, 1Eh
0x18007e213  ja      short loc_18007E26F
0x18007e215  mov     al, [rbx+0B9h]
0x18007e21b  dec     al
0x18007e21d  cmp     al, 0Bh
0x18007e21f  ja      short loc_18007E26F
0x18007e221  movzx   edx, word ptr [rbx+0BAh]
0x18007e228  lea     rcx, [rbp+1D0h+var_240]
0x18007e22c  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x18007e231  mov     rcx, rax
0x18007e234  lea     rdx, asc_1800A008C; "-"
0x18007e23b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18007e240  movzx   edx, byte ptr [rbx+0B9h]
0x18007e247  mov     rcx, rax
0x18007e24a  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18007e250  mov     rcx, rax
0x18007e253  lea     rdx, asc_1800A008C; "-"
0x18007e25a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18007e25f  movzx   edx, byte ptr [rbx+0B8h]
0x18007e266  mov     rcx, rax
0x18007e269  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18007e26f  xor     edx, edx; unsigned __int16 *
0x18007e271  mov     rcx, rdi; this
0x18007e274  call    ?StartObject@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartObject(ushort const *)
0x18007e279  mov     ecx, [rbx+0A8h]
0x18007e27f  mov     eax, ecx
0x18007e281  shr     eax, 1Eh
0x18007e284  and     al, 1
0x18007e286  mov     byte ptr [rbp+1D0h+var_250], al
0x18007e289  shr     ecx, 1Dh
0x18007e28c  not     cl
0x18007e28e  and     cl, 1
0x18007e291  mov     byte ptr [rbp+1D0h+var_250+1], cl
0x18007e294  lea     rdx, [rbp+1D0h+var_40]
0x18007e29b  lea     rcx, [rbp+1D0h+var_238]
0x18007e29f  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18007e2a4  nop
0x18007e2a5  lea     rax, [rbx+0ACh]
0x18007e2ac  lea     rcx, [rbx+0B4h]
0x18007e2b3  lea     rdx, [rbx+0B0h]; __int64
0x18007e2ba  lea     r8, [rbx+80h]
0x18007e2c1  lea     r9, [rbx+60h]; __int64
0x18007e2c5  lea     r10, [rbx+40h]
0x18007e2c9  mov     [rsp+300h+var_260], rax
0x18007e2d1  mov     [rsp+300h+var_270], rcx
0x18007e2d9  mov     qword ptr [rsp+300h+var_280], rdx; int
0x18007e2e1  lea     rax, [rbp+1D0h+var_250]
0x18007e2e5  mov     qword ptr [rsp+300h+var_290], rax; int
0x18007e2ea  lea     rax, [rbp+1D0h+var_250+1]
0x18007e2ee  mov     qword ptr [rsp+300h+var_2A0], rax; int
0x18007e2f3  mov     qword ptr [rsp+300h+var_2B0], r8; int
0x18007e2f8  lea     rax, [rbp+1D0h+var_40]
0x18007e2ff  mov     qword ptr [rsp+300h+var_2C0], rax; int
0x18007e304  mov     qword ptr [rsp+300h+var_2D0], r9; int
0x18007e309  mov     qword ptr [rsp+300h+var_2E0], r10; int
0x18007e30e  mov     r8, rbx; int
0x18007e311  mov     rcx, rdi; this
0x18007e314  call    ??$WriteKeyValues@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY0N@$$CBGAEAV12@AEAY0N@$$CBGAEAV12@AEAY0BA@$$CBGV12@AEAY09$$CBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAY08$$CBG_NAEAY0BB@$$CBG_NAEAY0P@$$CBGAEAKAEAY0BD@$$CBGAEAKAEAY0L@$$CBGAEAK@SleepstudyJsonWriter@@QEAAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY0N@$$CBG121AEAY0BA@$$CBG$$QEAV12@AEAY09$$CBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAY08$$CBG$$QEA_NAEAY0BB@$$CBG8AEAY0P@$$CBGAEAKAEAY0BD@$$CBGAEAKAEAY0L@$$CBGAEAK@Z; SleepstudyJsonWriter::WriteKeyValues<std::wstring &,ushort const (&)[13],std::wstring &,ushort const (&)[13],std::wstring &,ushort const (&)[16],std::wstring,ushort const (&)[10],std::string &,ushort const (&)[9],bool,ushort const (&)[17],bool,ushort const (&)[15],ulong &,ushort const (&)[19],ulong &,ushort const (&)[11],ulong &>(ushort const *,std::wstring &,ushort const (&)[13],std::wstring &,ushort const (&)[13],std::wstring &,ushort const (&)[16],std::wstring &&,ushort const (&)[10],std::string &,ushort const (&)[9],bool &&,ushort const (&)[17],bool &&,ushort const (&)[15],ulong &,ushort const (&)[19],ulong &,ushort const (&)[11],ulong &)
0x18007e319  nop
0x18007e31a  lea     rcx, [rbp+1D0h+var_40]; void *
0x18007e321  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18007e326  mov     rcx, rdi; this
0x18007e329  call    ?EndObject@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndObject(void)
0x18007e32e  add     rbx, 0C0h
0x18007e335  cmp     rbx, rsi
0x18007e338  jnz     loc_18007E1B4
0x18007e33e  mov     rcx, rdi; this
0x18007e341  call    ?EndArray@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndArray(void)
0x18007e346  nop
0x18007e347  lea     rcx, [rbp+1D0h+var_240]
0x18007e34b  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x18007e350  nop
0x18007e351  lea     rcx, [rbp+1D0h+var_150]; this
0x18007e358  call    ??1SystemInformation@SessionModel@@QEAA@XZ; SessionModel::SystemInformation::~SystemInformation(void)
0x18007e35d  mov     rcx, [rbp+1D0h+var_20]
0x18007e364  xor     rcx, rsp; StackCookie
0x18007e367  call    __security_check_cookie
0x18007e36c  mov     rbx, [rsp+300h+arg_0]
0x18007e374  add     rsp, 2F0h
0x18007e37b  pop     rdi
0x18007e37c  pop     rsi
0x18007e37d  pop     rbp
0x18007e37e  retn
```
