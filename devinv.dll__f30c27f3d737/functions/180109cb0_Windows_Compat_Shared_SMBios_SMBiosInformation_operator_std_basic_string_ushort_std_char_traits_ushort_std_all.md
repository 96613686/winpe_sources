# Windows::Compat::Shared::SMBios::SMBiosInformation::operator std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180109cb0`
- end: `0x18010ac16`
- name: `??BSMBiosInformation@SMBios@Shared@Compat@Windows@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `3942`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180005e40`
- `0x18000fa50`
- `0x180038e7c`
- `0x18003924c`
- `0x1800393d0`
- `0x180039480`
- `0x180039700`
- `0x18003d1a0`
- `0x180107074`
- `0x180107288`
- `0x180108f20`
- `0x180109034`
- `0x180109148`
- `0x1801092a4`
- `0x1801096ac`
- `0x180109860`
- `0x180109a08`
- `0x180109bb0`
- `0x180109cb0`
- `0x18010ac1c`
- `0x18010ae4c`
- `0x18010b07c`
- `0x18010b2ac`
- `0x18010b3d8`
- `0x18010b7a0`
- `0x18010c214`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180109d09`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180109d71`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18010a1b5`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18010a434`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18010a4d1`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18010ab7f`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180109d09`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180109d71`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18010a1b5`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18010a434`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18010a4d1`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18010ab7f`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18010abe3`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18010abe3`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18010abd6`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18010abd6`

## string_xrefs

- `0x18010a0f9`: `RomSize`
- `0x18010a46a`: `CharacteristicsExtension1`
- `0x18010a4ac`: `CharacteristicsExtension1`
- `0x18010a3cd`: `CharacteristicsExtension0`
- `0x18010a40f`: `CharacteristicsExtension0`
- `0x18010ab30`: `ExtendedRomSizeUnits`
- `0x18010aa06`: `ExtendedRomSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Shared::SMBios::SMBiosInformation::operator std::wstring(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  _QWORD *v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rax
  char v9; // bl
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // rax
  char v13; // bl
  int v14; // eax
  __int64 v15; // rax
  char v16; // bl
  int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  const char *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  char v28; // bl
  int v29; // eax
  char v30; // bl
  int v31; // eax
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  const char *v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  const char *v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  char v52; // bl
  int v53; // eax
  char v54; // bl
  int v55; // eax
  char v56; // bl
  int v57; // eax
  char v58; // bl
  int v59; // eax
  char v60; // bl
  int v61; // eax
  char v62; // r15
  char v63; // bl
  int v64; // eax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rax
  const char *v69; // rdx
  __int64 v70; // rax
  _DWORD v72[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v73; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v74; // [rsp+50h] [rbp-B0h]
  __int128 v75; // [rsp+60h] [rbp-A0h]
  __int128 v76; // [rsp+70h] [rbp-90h]
  __int128 v77; // [rsp+80h] [rbp-80h]
  __int128 v78; // [rsp+90h] [rbp-70h]
  __int128 v79; // [rsp+A0h] [rbp-60h]
  __int128 v80; // [rsp+B0h] [rbp-50h]
  __int128 v81; // [rsp+C0h] [rbp-40h]
  __int128 v82; // [rsp+D0h] [rbp-30h]
  __int128 v83; // [rsp+E0h] [rbp-20h]
  __int128 v84; // [rsp+F0h] [rbp-10h]
  __int128 v85; // [rsp+100h] [rbp+0h]
  __int128 v86; // [rsp+110h] [rbp+10h]
  __int128 v87; // [rsp+120h] [rbp+20h]
  _OWORD v88[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v89; // [rsp+150h] [rbp+50h]
  int v90; // [rsp+15Ch] [rbp+5Ch]
  __int64 v91; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v92[8]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v93[120]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v94[104]; // [rsp+1E8h] [rbp+E8h] BYREF
  _QWORD v95[4]; // [rsp+250h] [rbp+150h] BYREF

  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v91);
  v4 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v91, "{");
  std::basic_ostream<unsigned short>::operator<<(v4, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v5 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v91, "\"Header\": ");
  Windows::Compat::Shared::SMBios::SmbStructHeader::operator std::wstring(a1 + 32, v95);
  v6 = v95;
  if ( v95[3] > 7u )
    v6 = (_QWORD *)v95[0];
  v7 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v5, v6, v95[2]);
  v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v7, ",");
  std::basic_ostream<unsigned short>::operator<<(v8, std::endl<unsigned short,std::char_traits<unsigned short>>);
  std::wstring::~wstring(v95);
  v9 = *(_BYTE *)(a1 + 131);
  v10 = std::vector<unsigned char>::vector<unsigned char>(v95, a1 + 8);
  v73 = *(_OWORD *)(a1 + 144);
  v74 = *(_OWORD *)(a1 + 160);
  v75 = *(_OWORD *)(a1 + 176);
  v76 = *(_OWORD *)(a1 + 192);
  v77 = *(_OWORD *)(a1 + 208);
  v78 = *(_OWORD *)(a1 + 224);
  v79 = *(_OWORD *)(a1 + 240);
  v80 = *(_OWORD *)(a1 + 256);
  v81 = *(_OWORD *)(a1 + 272);
  v82 = *(_OWORD *)(a1 + 288);
  v83 = *(_OWORD *)(a1 + 304);
  v84 = *(_OWORD *)(a1 + 320);
  v85 = *(_OWORD *)(a1 + 336);
  v86 = *(_OWORD *)(a1 + 352);
  v87 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned char,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (unsigned int)v72,
    (unsigned int)&v73,
    0,
    v10,
    v9);
  if ( BYTE1(v72[0]) )
  {
    LOBYTE(v11) = v72[0];
    Windows::Compat::Shared::SMBios::SMBiosStructBase::GetSMBiosString(a1, v88, v11);
  }
  else
  {
    memset(v88, 0, sizeof(v88));
    v89 = 0;
  }
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<std::wstring>,0>(&v91, L"Vendor", v88);
  if ( (_BYTE)v89 )
    std::wstring::~wstring(v88);
  v12 = Windows::Compat::Shared::SMBios::SMBiosInformation::Version(a1, v88);
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<std::wstring>,0>(&v91, L"Version", v12);
  if ( (_BYTE)v89 )
    std::wstring::~wstring(v88);
  v13 = *(_BYTE *)(a1 + 131);
  v14 = std::vector<unsigned char>::vector<unsigned char>(v95, a1 + 8);
  v73 = *(_OWORD *)(a1 + 144);
  v74 = *(_OWORD *)(a1 + 160);
  v75 = *(_OWORD *)(a1 + 176);
  v76 = *(_OWORD *)(a1 + 192);
  v77 = *(_OWORD *)(a1 + 208);
  v78 = *(_OWORD *)(a1 + 224);
  v79 = *(_OWORD *)(a1 + 240);
  v80 = *(_OWORD *)(a1 + 256);
  v81 = *(_OWORD *)(a1 + 272);
  v82 = *(_OWORD *)(a1 + 288);
  v83 = *(_OWORD *)(a1 + 304);
  v84 = *(_OWORD *)(a1 + 320);
  v85 = *(_OWORD *)(a1 + 336);
  v86 = *(_OWORD *)(a1 + 352);
  v87 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned short,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (unsigned int)v72,
    (unsigned int)&v73,
    2,
    v14,
    v13);
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned short>,0>(&v91, L"StartingAddressSegment", v72);
  v15 = Windows::Compat::Shared::SMBios::SMBiosInformation::ReleaseDate(a1, v88);
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<std::wstring>,0>(&v91, L"ReleaseDate", v15);
  if ( (_BYTE)v89 )
    std::wstring::~wstring(v88);
  v16 = *(_BYTE *)(a1 + 131);
  v17 = std::vector<unsigned char>::vector<unsigned char>(v95, a1 + 8);
  v73 = *(_OWORD *)(a1 + 144);
  v74 = *(_OWORD *)(a1 + 160);
  v75 = *(_OWORD *)(a1 + 176);
  v76 = *(_OWORD *)(a1 + 192);
  v77 = *(_OWORD *)(a1 + 208);
  v78 = *(_OWORD *)(a1 + 224);
  v79 = *(_OWORD *)(a1 + 240);
  v80 = *(_OWORD *)(a1 + 256);
  v81 = *(_OWORD *)(a1 + 272);
  v82 = *(_OWORD *)(a1 + 288);
  v83 = *(_OWORD *)(a1 + 304);
  v84 = *(_OWORD *)(a1 + 320);
  v85 = *(_OWORD *)(a1 + 336);
  v86 = *(_OWORD *)(a1 + 352);
  v87 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned char,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (unsigned int)v72,
    (unsigned int)&v73,
    4,
    v17,
    v16);
  if ( !BYTE1(v72[0]) || LOBYTE(v72[0]) == 0xFF )
    LOWORD(v72[0]) = 0;
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned char>,0>(&v91, L"RomSize", v72);
  v18 = Windows::Compat::Shared::SMBios::SMBiosInformation::Characteristics(a1, v72);
  if ( *(_BYTE *)(v18 + 4) )
  {
    v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v91, L"  ");
    v20 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v19, "\"");
    v21 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, L"Characteristics");
    v22 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v21, "\": \"");
    v23 = Windows::Compat::Shared::SMBios::operator<<(v22, v18);
    v24 = "\",";
  }
  else
  {
    v25 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v91, L"  ");
    v26 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v25, "\"");
    v23 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v26, L"Characteristics");
    v24 = "\": null,";
  }
  v27 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v23, v24);
  std::basic_ostream<unsigned short>::operator<<(v27, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v28 = *(_BYTE *)(a1 + 131);
  v29 = std::vector<unsigned char>::vector<unsigned char>(v95, a1 + 8);
  v73 = *(_OWORD *)(a1 + 144);
  v74 = *(_OWORD *)(a1 + 160);
  v75 = *(_OWORD *)(a1 + 176);
  v76 = *(_OWORD *)(a1 + 192);
  v77 = *(_OWORD *)(a1 + 208);
  v78 = *(_OWORD *)(a1 + 224);
  v79 = *(_OWORD *)(a1 + 240);
  v80 = *(_OWORD *)(a1 + 256);
  v81 = *(_OWORD *)(a1 + 272);
  v82 = *(_OWORD *)(a1 + 288);
  v83 = *(_OWORD *)(a1 + 304);
  v84 = *(_OWORD *)(a1 + 320);
  v85 = *(_OWORD *)(a1 + 336);
  v86 = *(_OWORD *)(a1 + 352);
  v87 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned short,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (unsigned int)v72,
    (unsigned int)&v73,
    6,
    v29,
    v28);
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned short>,0>(
    &v91,
    L"BiosVendorReservedCharacteristics",
    v72);
  v30 = *(_BYTE *)(a1 + 131);
  v31 = std::vector<unsigned char>::vector<unsigned char>(v95, a1 + 8);
  v73 = *(_OWORD *)(a1 + 144);
  v74 = *(_OWORD *)(a1 + 160);
  v75 = *(_OWORD *)(a1 + 176);
  v76 = *(_OWORD *)(a1 + 192);
  v77 = *(_OWORD *)(a1 + 208);
  v78 = *(_OWORD *)(a1 + 224);
  v79 = *(_OWORD *)(a1 + 240);
  v80 = *(_OWORD *)(a1 + 256);
  v81 = *(_OWORD *)(a1 + 272);
  v82 = *(_OWORD *)(a1 + 288);
  v83 = *(_OWORD *)(a1 + 304);
  v84 = *(_OWORD *)(a1 + 320);
  v85 = *(_OWORD *)(a1 + 336);
  v86 = *(_OWORD *)(a1 + 352);
  v87 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned short,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (unsigned int)v72,
    (unsigned int)&v73,
    7,
    v31,
    v30);
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned short>,0>(
    &v91,
    L"SystemVendorReservedCharacteristics",
    v72);
  v32 = Windows::Compat::Shared::SMBios::SMBiosInformation::CharacteristicsExtension0(a1, v72);
  if ( *(_BYTE *)(v32 + 1) )
  {
    v33 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v91, L"  ");
    v34 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v33, "\"");
    v35 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, L"CharacteristicsExtension0");
    v36 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v35, "\": \"");
    v37 = Windows::Compat::Shared::SMBios::operator<<(v36, v32);
    v38 = "\",";
  }
  else
  {
    v39 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v91, L"  ");
    v40 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v39, "\"");
    v37 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v40, L"CharacteristicsExtension0");
    v38 = "\": null,";
  }
  v41 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v37, v38);
  std::basic_ostream<unsigned short>::operator<<(v41, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v42 = Windows::Compat::Shared::SMBios::SMBiosInformation::CharacteristicsExtension1(a1, v72);
  if ( *(_BYTE *)(v42 + 1) )
  {
    v43 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v91, L"  ");
    v44 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v43, "\"");
    v45 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v44, L"CharacteristicsExtension1");
    v46 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v45, "\": \"");
    v47 = Windows::Compat::Shared::SMBios::operator<<(v46, v42);
    v48 = "\",";
  }
  else
  {
    v49 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v91, L"  ");
    v50 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v49, "\"");
    v47 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v50, L"CharacteristicsExtension1");
    v48 = "\": null,";
  }
  v51 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, v48);
  std::basic_ostream<unsigned short>::operator<<(v51, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v52 = *(_BYTE *)(a1 + 131);
  v53 = std::vector<unsigned char>::vector<unsigned char>(v95, a1 + 8);
  v73 = *(_OWORD *)(a1 + 144);
  v74 = *(_OWORD *)(a1 + 160);
  v75 = *(_OWORD *)(a1 + 176);
  v76 = *(_OWORD *)(a1 + 192);
  v77 = *(_OWORD *)(a1 + 208);
  v78 = *(_OWORD *)(a1 + 224);
  v79 = *(_OWORD *)(a1 + 240);
  v80 = *(_OWORD *)(a1 + 256);
  v81 = *(_OWORD *)(a1 + 272);
  v82 = *(_OWORD *)(a1 + 288);
  v83 = *(_OWORD *)(a1 + 304);
  v84 = *(_OWORD *)(a1 + 320);
  v85 = *(_OWORD *)(a1 + 336);
  v86 = *(_OWORD *)(a1 + 352);
  v87 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned char,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (unsigned int)v72,
    (unsigned int)&v73,
    10,
    v53,
    v52);
  if ( !BYTE1(v72[0]) || LOBYTE(v72[0]) == 0xFF )
    LOWORD(v72[0]) = 0;
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned char>,0>(&v91, L"SystemBiosMajorRelease", v72);
  v54 = *(_BYTE *)(a1 + 131);
  v55 = std::vector<unsigned char>::vector<unsigned char>(v95, a1 + 8);
  v73 = *(_OWORD *)(a1 + 144);
  v74 = *(_OWORD *)(a1 + 160);
  v75 = *(_OWORD *)(a1 + 176);
  v76 = *(_OWORD *)(a1 + 192);
  v77 = *(_OWORD *)(a1 + 208);
  v78 = *(_OWORD *)(a1 + 224);
  v79 = *(_OWORD *)(a1 + 240);
  v80 = *(_OWORD *)(a1 + 256);
  v81 = *(_OWORD *)(a1 + 272);
  v82 = *(_OWORD *)(a1 + 288);
  v83 = *(_OWORD *)(a1 + 304);
  v84 = *(_OWORD *)(a1 + 320);
  v85 = *(_OWORD *)(a1 + 336);
  v86 = *(_OWORD *)(a1 + 352);
  v87 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned char,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (unsigned int)v72,
    (unsigned int)&v73,
    11,
    v55,
    v54);
  if ( !BYTE1(v72[0]) || LOBYTE(v72[0]) == 0xFF )
    LOWORD(v72[0]) = 0;
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned char>,0>(&v91, L"SystemBiosMinorRelease", v72);
  v56 = *(_BYTE *)(a1 + 131);
  v57 = std::vector<unsigned char>::vector<unsigned char>(v95, a1 + 8);
  v73 = *(_OWORD *)(a1 + 144);
  v74 = *(_OWORD *)(a1 + 160);
  v75 = *(_OWORD *)(a1 + 176);
  v76 = *(_OWORD *)(a1 + 192);
  v77 = *(_OWORD *)(a1 + 208);
  v78 = *(_OWORD *)(a1 + 224);
  v79 = *(_OWORD *)(a1 + 240);
  v80 = *(_OWORD *)(a1 + 256);
  v81 = *(_OWORD *)(a1 + 272);
  v82 = *(_OWORD *)(a1 + 288);
  v83 = *(_OWORD *)(a1 + 304);
  v84 = *(_OWORD *)(a1 + 320);
  v85 = *(_OWORD *)(a1 + 336);
  v86 = *(_OWORD *)(a1 + 352);
  v87 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned char,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (unsigned int)v72,
    (unsigned int)&v73,
    12,
    v57,
    v56);
  if ( !BYTE1(v72[0]) || LOBYTE(v72[0]) == 0xFF )
    LOWORD(v72[0]) = 0;
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned char>,0>(&v91, L"ECFirmwareMajorRelease", v72);
  v58 = *(_BYTE *)(a1 + 131);
  v59 = std::vector<unsigned char>::vector<unsigned char>(v95, a1 + 8);
  v73 = *(_OWORD *)(a1 + 144);
  v74 = *(_OWORD *)(a1 + 160);
  v75 = *(_OWORD *)(a1 + 176);
  v76 = *(_OWORD *)(a1 + 192);
  v77 = *(_OWORD *)(a1 + 208);
  v78 = *(_OWORD *)(a1 + 224);
  v79 = *(_OWORD *)(a1 + 240);
  v80 = *(_OWORD *)(a1 + 256);
  v81 = *(_OWORD *)(a1 + 272);
  v82 = *(_OWORD *)(a1 + 288);
  v83 = *(_OWORD *)(a1 + 304);
  v84 = *(_OWORD *)(a1 + 320);
  v85 = *(_OWORD *)(a1 + 336);
  v86 = *(_OWORD *)(a1 + 352);
  v87 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned char,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (unsigned int)v72,
    (unsigned int)&v73,
    13,
    v59,
    v58);
  if ( !BYTE1(v72[0]) || LOBYTE(v72[0]) == 0xFF )
    LOWORD(v72[0]) = 0;
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned char>,0>(&v91, L"ECFirmwareMinorRelease", v72);
  v60 = *(_BYTE *)(a1 + 131);
  v61 = std::vector<unsigned char>::vector<unsigned char>(v95, a1 + 8);
  v73 = *(_OWORD *)(a1 + 144);
  v74 = *(_OWORD *)(a1 + 160);
  v75 = *(_OWORD *)(a1 + 176);
  v76 = *(_OWORD *)(a1 + 192);
  v77 = *(_OWORD *)(a1 + 208);
  v78 = *(_OWORD *)(a1 + 224);
  v79 = *(_OWORD *)(a1 + 240);
  v80 = *(_OWORD *)(a1 + 256);
  v81 = *(_OWORD *)(a1 + 272);
  v82 = *(_OWORD *)(a1 + 288);
  v83 = *(_OWORD *)(a1 + 304);
  v84 = *(_OWORD *)(a1 + 320);
  v85 = *(_OWORD *)(a1 + 336);
  v86 = *(_OWORD *)(a1 + 352);
  v87 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned short,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (unsigned int)v72,
    (unsigned int)&v73,
    14,
    v61,
    v60);
  v62 = 1;
  if ( BYTE2(v72[0]) )
  {
    LOWORD(v72[0]) &= 0x3FFFu;
    BYTE2(v72[0]) = 1;
  }
  else
  {
    v72[0] = 0;
  }
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned short>,0>(&v91, L"ExtendedRomSize", v72);
  v63 = *(_BYTE *)(a1 + 131);
  v64 = std::vector<unsigned char>::vector<unsigned char>(v95, a1 + 8);
  v73 = *(_OWORD *)(a1 + 144);
  v74 = *(_OWORD *)(a1 + 160);
  v75 = *(_OWORD *)(a1 + 176);
  v76 = *(_OWORD *)(a1 + 192);
  v77 = *(_OWORD *)(a1 + 208);
  v78 = *(_OWORD *)(a1 + 224);
  v79 = *(_OWORD *)(a1 + 240);
  v80 = *(_OWORD *)(a1 + 256);
  v81 = *(_OWORD *)(a1 + 272);
  v82 = *(_OWORD *)(a1 + 288);
  v83 = *(_OWORD *)(a1 + 304);
  v84 = *(_OWORD *)(a1 + 320);
  v85 = *(_OWORD *)(a1 + 336);
  v86 = *(_OWORD *)(a1 + 352);
  v87 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned short,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (unsigned int)v72,
    (unsigned int)&v73,
    14,
    v64,
    v63);
  if ( BYTE2(v72[0]) )
  {
    LOBYTE(v72[0]) = LOWORD(v72[0]) >> 14;
  }
  else
  {
    LOWORD(v72[0]) = 0;
    v62 = 0;
  }
  BYTE1(v72[0]) = v62;
  v65 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v91, L"  ");
  v66 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v65, "\"");
  v67 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v66, L"ExtendedRomSizeUnits");
  if ( v62 )
  {
    v68 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v67, "\": \"");
    v67 = Windows::Compat::Shared::SMBios::operator<<(v68, v72);
    v69 = "\",";
  }
  else
  {
    v69 = "\": null,";
  }
  v70 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v67, v69);
  std::basic_ostream<unsigned short>::operator<<(v70, std::endl<unsigned short,std::char_traits<unsigned short>>);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v91, "}");
  std::basic_stringbuf<unsigned short>::str(v92, a2);
  *(_QWORD *)&v92[*(int *)(v91 + 4) - 8] = &std::basic_ostringstream<unsigned short>::`vftable';
  *(int *)((char *)&v90 + *(int *)(v91 + 4)) = *(_DWORD *)(v91 + 4) - 136;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v92);
  std::basic_ostream<unsigned short>::~basic_ostream<unsigned short,std::char_traits<unsigned short>>(v93);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v94);
  return a2;
}

```

## disassembly

```asm
0x180109cb0  mov     [rsp-8+arg_10], rbx
0x180109cb5  push    rbp
0x180109cb6  push    rsi
0x180109cb7  push    rdi
0x180109cb8  push    r12
0x180109cba  push    r13
0x180109cbc  push    r14
0x180109cbe  push    r15
0x180109cc0  lea     rbp, [rsp-180h]
0x180109cc8  sub     rsp, 280h
0x180109ccf  mov     rax, cs:__security_cookie
0x180109cd6  xor     rax, rsp
0x180109cd9  mov     [rbp+1B0h+var_40], rax
0x180109ce0  mov     r13, rdx
0x180109ce3  mov     rdi, rcx
0x180109ce6  lea     rcx, [rbp+1B0h+var_150]
0x180109cea  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180109cef  lea     rdx, asc_18013D64C; "{"
0x180109cf6  lea     rcx, [rbp+1B0h+var_150]
0x180109cfa  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180109cff  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x180109d06  mov     rcx, rax
0x180109d09  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x180109d0f  lea     rdx, aHeader; "\"Header\": "
0x180109d16  lea     rcx, [rbp+1B0h+var_150]
0x180109d1a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180109d1f  mov     rbx, rax
0x180109d22  lea     rcx, [rdi+20h]
0x180109d26  lea     rdx, [rbp+1B0h+var_60]
0x180109d2d  call    ??BSmbStructHeader@SMBios@Shared@Compat@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Compat::Shared::SMBios::SmbStructHeader::operator std::wstring(void)
0x180109d32  lea     rdx, [rbp+1B0h+var_60]
0x180109d39  cmp     [rbp+1B0h+var_48], 7
0x180109d41  cmova   rdx, [rbp+1B0h+var_60]
0x180109d49  mov     r8, [rbp+1B0h+var_50]
0x180109d50  mov     rcx, rbx
0x180109d53  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x180109d58  lea     rdx, asc_180135380; ","
0x180109d5f  mov     rcx, rax
0x180109d62  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180109d67  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x180109d6e  mov     rcx, rax
0x180109d71  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x180109d77  lea     rcx, [rbp+1B0h+var_60]; void *
0x180109d7e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180109d83  nop
0x180109d84  mov     bl, [rdi+83h]
0x180109d8a  lea     r12, [rdi+8]
0x180109d8e  mov     rdx, r12
0x180109d91  lea     rcx, [rbp+1B0h+var_60]
0x180109d98  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180109d9d  movups  xmm0, xmmword ptr [rdi+90h]
0x180109da4  movups  [rsp+2B0h+var_270], xmm0
0x180109da9  movups  xmm1, xmmword ptr [rdi+0A0h]
0x180109db0  movups  [rsp+2B0h+var_260], xmm1
0x180109db5  movups  xmm0, xmmword ptr [rdi+0B0h]
0x180109dbc  movups  [rsp+2B0h+var_250], xmm0
0x180109dc1  movups  xmm1, xmmword ptr [rdi+0C0h]
0x180109dc8  movups  [rsp+2B0h+var_240], xmm1
0x180109dcd  movups  xmm0, xmmword ptr [rdi+0D0h]
0x180109dd4  movups  [rbp+1B0h+var_230], xmm0
0x180109dd8  movups  xmm1, xmmword ptr [rdi+0E0h]
0x180109ddf  movups  [rbp+1B0h+var_220], xmm1
0x180109de3  movups  xmm0, xmmword ptr [rdi+0F0h]
0x180109dea  movups  [rbp+1B0h+var_210], xmm0
0x180109dee  movups  xmm1, xmmword ptr [rdi+100h]
0x180109df5  movups  [rbp+1B0h+var_200], xmm1
0x180109df9  movups  xmm0, xmmword ptr [rdi+110h]
0x180109e00  movups  [rbp+1B0h+var_1F0], xmm0
0x180109e04  movups  xmm1, xmmword ptr [rdi+120h]
0x180109e0b  movups  [rbp+1B0h+var_1E0], xmm1
0x180109e0f  movups  xmm0, xmmword ptr [rdi+130h]
0x180109e16  movups  [rbp+1B0h+var_1D0], xmm0
0x180109e1a  movups  xmm1, xmmword ptr [rdi+140h]
0x180109e21  movups  [rbp+1B0h+var_1C0], xmm1
0x180109e25  movups  xmm0, xmmword ptr [rdi+150h]
0x180109e2c  movups  [rbp+1B0h+var_1B0], xmm0
0x180109e30  movups  xmm1, xmmword ptr [rdi+160h]
0x180109e37  movups  [rbp+1B0h+var_1A0], xmm1
0x180109e3b  movups  xmm0, xmmword ptr [rdi+170h]
0x180109e42  movups  [rbp+1B0h+var_190], xmm0
0x180109e46  mov     [rsp+2B0h+var_290], bl
0x180109e4a  mov     r9, rax
0x180109e4d  xor     r8d, r8d
0x180109e50  lea     rdx, [rsp+2B0h+var_270]
0x180109e55  lea     rcx, [rsp+2B0h+var_280]
0x180109e5a  call    ??$GetField@EV?$array@U?$StructField@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@$0P@@std@@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@YA?AV?$optional@E@utl@@V?$array@U?$StructField@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@$0P@@std@@W4BiosInformationField@SMBiosInformation@0123@V?$vector@EV?$allocator@E@std@@@7@_N@Z; Windows::Compat::Shared::SMBios::GetField<uchar,std::array<Windows::Compat::Shared::SMBios::StructField<Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(std::array<Windows::Compat::Shared::SMBios::StructField<Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField,std::vector<uchar>,bool)
0x180109e5f  xor     r15d, r15d
0x180109e62  cmp     byte ptr [rsp+2B0h+var_280+1], r15b
0x180109e67  jnz     short loc_180109E7C
0x180109e69  xorps   xmm0, xmm0
0x180109e6c  xor     eax, eax
0x180109e6e  movups  [rbp+1B0h+var_180], xmm0
0x180109e72  movups  [rbp+1B0h+var_170], xmm0
0x180109e76  mov     [rbp+1B0h+var_160], rax
0x180109e7a  jmp     short loc_180109E8E
0x180109e7c  mov     r8b, byte ptr [rsp+2B0h+var_280]
0x180109e81  lea     rdx, [rbp+1B0h+var_180]
0x180109e85  mov     rcx, rdi
0x180109e88  call    ?GetSMBiosString@SMBiosStructBase@SMBios@Shared@Compat@Windows@@IEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@E@Z; Windows::Compat::Shared::SMBios::SMBiosStructBase::GetSMBiosString(uchar)
0x180109e8d  nop
0x180109e8e  lea     r8, [rbp+1B0h+var_180]
0x180109e92  lea     rdx, aVendor; "Vendor"
0x180109e99  lea     rcx, [rbp+1B0h+var_150]
0x180109e9d  call    ??$FieldToStream@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@$0A@@SMBios@Shared@Compat@Windows@@YAXAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@PEBGAEBV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@@Z; Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<std::wstring>,0>(std::basic_ostream<ushort> &,ushort const *,utl::optional<std::wstring> const &)
0x180109ea2  cmp     byte ptr [rbp+1B0h+var_160], r15b
0x180109ea6  jz      short loc_180109EB1
0x180109ea8  lea     rcx, [rbp+1B0h+var_180]; void *
0x180109eac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180109eb1  lea     rdx, [rbp+1B0h+var_180]
0x180109eb5  mov     rcx, rdi
0x180109eb8  call    ?Version@SMBiosInformation@SMBios@Shared@Compat@Windows@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@XZ; Windows::Compat::Shared::SMBios::SMBiosInformation::Version(void)
0x180109ebd  mov     r8, rax
0x180109ec0  lea     rdx, aVersion; "Version"
0x180109ec7  lea     rcx, [rbp+1B0h+var_150]
0x180109ecb  call    ??$FieldToStream@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@$0A@@SMBios@Shared@Compat@Windows@@YAXAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@PEBGAEBV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@@Z; Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<std::wstring>,0>(std::basic_ostream<ushort> &,ushort const *,utl::optional<std::wstring> const &)
0x180109ed0  cmp     byte ptr [rbp+1B0h+var_160], r15b
0x180109ed4  jz      short loc_180109EE0
0x180109ed6  lea     rcx, [rbp+1B0h+var_180]; void *
0x180109eda  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180109edf  nop
0x180109ee0  mov     bl, [rdi+83h]
0x180109ee6  mov     rdx, r12
0x180109ee9  lea     rcx, [rbp+1B0h+var_60]
0x180109ef0  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180109ef5  movups  xmm0, xmmword ptr [rdi+90h]
0x180109efc  movups  [rsp+2B0h+var_270], xmm0
0x180109f01  movups  xmm1, xmmword ptr [rdi+0A0h]
0x180109f08  movups  [rsp+2B0h+var_260], xmm1
0x180109f0d  movups  xmm0, xmmword ptr [rdi+0B0h]
0x180109f14  movups  [rsp+2B0h+var_250], xmm0
0x180109f19  movups  xmm1, xmmword ptr [rdi+0C0h]
0x180109f20  movups  [rsp+2B0h+var_240], xmm1
0x180109f25  movups  xmm0, xmmword ptr [rdi+0D0h]
0x180109f2c  movups  [rbp+1B0h+var_230], xmm0
0x180109f30  movups  xmm1, xmmword ptr [rdi+0E0h]
0x180109f37  movups  [rbp+1B0h+var_220], xmm1
0x180109f3b  movups  xmm0, xmmword ptr [rdi+0F0h]
0x180109f42  movups  [rbp+1B0h+var_210], xmm0
0x180109f46  movups  xmm1, xmmword ptr [rdi+100h]
0x180109f4d  movups  [rbp+1B0h+var_200], xmm1
0x180109f51  movups  xmm0, xmmword ptr [rdi+110h]
0x180109f58  movups  [rbp+1B0h+var_1F0], xmm0
0x180109f5c  movups  xmm1, xmmword ptr [rdi+120h]
0x180109f63  movups  [rbp+1B0h+var_1E0], xmm1
0x180109f67  movups  xmm0, xmmword ptr [rdi+130h]
0x180109f6e  movups  [rbp+1B0h+var_1D0], xmm0
0x180109f72  movups  xmm1, xmmword ptr [rdi+140h]
0x180109f79  movups  [rbp+1B0h+var_1C0], xmm1
0x180109f7d  movups  xmm0, xmmword ptr [rdi+150h]
0x180109f84  movups  [rbp+1B0h+var_1B0], xmm0
0x180109f88  movups  xmm1, xmmword ptr [rdi+160h]
0x180109f8f  movups  [rbp+1B0h+var_1A0], xmm1
0x180109f93  movups  xmm0, xmmword ptr [rdi+170h]
0x180109f9a  movups  [rbp+1B0h+var_190], xmm0
0x180109f9e  mov     [rsp+2B0h+var_290], bl
0x180109fa2  mov     r9, rax
0x180109fa5  mov     r8d, 2
0x180109fab  lea     rdx, [rsp+2B0h+var_270]
0x180109fb0  lea     rcx, [rsp+2B0h+var_280]
0x180109fb5  call    ??$GetField@GV?$array@U?$StructField@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@$0P@@std@@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@YA?AV?$optional@G@utl@@V?$array@U?$StructField@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@$0P@@std@@W4BiosInformationField@SMBiosInformation@0123@V?$vector@EV?$allocator@E@std@@@7@_N@Z; Windows::Compat::Shared::SMBios::GetField<ushort,std::array<Windows::Compat::Shared::SMBios::StructField<Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(std::array<Windows::Compat::Shared::SMBios::StructField<Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField,std::vector<uchar>,bool)
0x180109fba  nop
0x180109fbb  lea     r8, [rsp+2B0h+var_280]
0x180109fc0  lea     rdx, aStartingaddres; "StartingAddressSegment"
0x180109fc7  lea     rcx, [rbp+1B0h+var_150]
0x180109fcb  call    ??$FieldToStream@V?$optional@G@utl@@$0A@@SMBios@Shared@Compat@Windows@@YAXAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@PEBGAEBV?$optional@G@utl@@@Z; Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<ushort>,0>(std::basic_ostream<ushort> &,ushort const *,utl::optional<ushort> const &)
0x180109fd0  lea     rdx, [rbp+1B0h+var_180]
0x180109fd4  mov     rcx, rdi
0x180109fd7  call    ?ReleaseDate@SMBiosInformation@SMBios@Shared@Compat@Windows@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@XZ; Windows::Compat::Shared::SMBios::SMBiosInformation::ReleaseDate(void)
0x180109fdc  mov     r8, rax
0x180109fdf  lea     rdx, aReleasedate; "ReleaseDate"
0x180109fe6  lea     rcx, [rbp+1B0h+var_150]
0x180109fea  call    ??$FieldToStream@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@$0A@@SMBios@Shared@Compat@Windows@@YAXAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@PEBGAEBV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@@Z; Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<std::wstring>,0>(std::basic_ostream<ushort> &,ushort const *,utl::optional<std::wstring> const &)
0x180109fef  cmp     byte ptr [rbp+1B0h+var_160], r15b
0x180109ff3  jz      short loc_180109FFF
0x180109ff5  lea     rcx, [rbp+1B0h+var_180]; void *
0x180109ff9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180109ffe  nop
0x180109fff  mov     bl, [rdi+83h]
0x18010a005  mov     rdx, r12
0x18010a008  lea     rcx, [rbp+1B0h+var_60]
0x18010a00f  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18010a014  movups  xmm0, xmmword ptr [rdi+90h]
0x18010a01b  movups  [rsp+2B0h+var_270], xmm0
0x18010a020  movups  xmm1, xmmword ptr [rdi+0A0h]
0x18010a027  movups  [rsp+2B0h+var_260], xmm1
0x18010a02c  movups  xmm0, xmmword ptr [rdi+0B0h]
0x18010a033  movups  [rsp+2B0h+var_250], xmm0
0x18010a038  movups  xmm1, xmmword ptr [rdi+0C0h]
0x18010a03f  movups  [rsp+2B0h+var_240], xmm1
0x18010a044  movups  xmm0, xmmword ptr [rdi+0D0h]
0x18010a04b  movups  [rbp+1B0h+var_230], xmm0
0x18010a04f  movups  xmm1, xmmword ptr [rdi+0E0h]
0x18010a056  movups  [rbp+1B0h+var_220], xmm1
0x18010a05a  movups  xmm0, xmmword ptr [rdi+0F0h]
0x18010a061  movups  [rbp+1B0h+var_210], xmm0
0x18010a065  movups  xmm1, xmmword ptr [rdi+100h]
0x18010a06c  movups  [rbp+1B0h+var_200], xmm1
0x18010a070  movups  xmm0, xmmword ptr [rdi+110h]
0x18010a077  movups  [rbp+1B0h+var_1F0], xmm0
0x18010a07b  movups  xmm1, xmmword ptr [rdi+120h]
0x18010a082  movups  [rbp+1B0h+var_1E0], xmm1
0x18010a086  movups  xmm0, xmmword ptr [rdi+130h]
0x18010a08d  movups  [rbp+1B0h+var_1D0], xmm0
0x18010a091  movups  xmm1, xmmword ptr [rdi+140h]
0x18010a098  movups  [rbp+1B0h+var_1C0], xmm1
0x18010a09c  movups  xmm0, xmmword ptr [rdi+150h]
0x18010a0a3  movups  [rbp+1B0h+var_1B0], xmm0
0x18010a0a7  movups  xmm1, xmmword ptr [rdi+160h]
0x18010a0ae  movups  [rbp+1B0h+var_1A0], xmm1
0x18010a0b2  movups  xmm0, xmmword ptr [rdi+170h]
0x18010a0b9  movups  [rbp+1B0h+var_190], xmm0
0x18010a0bd  mov     [rsp+2B0h+var_290], bl
0x18010a0c1  mov     r9, rax
0x18010a0c4  mov     r8d, 4
0x18010a0ca  lea     rdx, [rsp+2B0h+var_270]
0x18010a0cf  lea     rcx, [rsp+2B0h+var_280]
0x18010a0d4  call    ??$GetField@EV?$array@U?$StructField@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@$0P@@std@@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@YA?AV?$optional@E@utl@@V?$array@U?$StructField@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@$0P@@std@@W4BiosInformationField@SMBiosInformation@0123@V?$vector@EV?$allocator@E@std@@@7@_N@Z; Windows::Compat::Shared::SMBios::GetField<uchar,std::array<Windows::Compat::Shared::SMBios::StructField<Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(std::array<Windows::Compat::Shared::SMBios::StructField<Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField,std::vector<uchar>,bool)
0x18010a0d9  cmp     byte ptr [rsp+2B0h+var_280+1], r15b
0x18010a0de  jz      short loc_18010A0EE
0x18010a0e0  movzx   eax, word ptr [rsp+2B0h+var_280]
0x18010a0e5  cmp     al, 0FFh
0x18010a0e7  mov     word ptr [rsp+2B0h+var_280], ax
0x18010a0ec  jnz     short loc_18010A0F4
0x18010a0ee  mov     word ptr [rsp+2B0h+var_280], r15w
0x18010a0f4  lea     r8, [rsp+2B0h+var_280]
0x18010a0f9  lea     rdx, aRomsize; "RomSize"
0x18010a100  lea     rcx, [rbp+1B0h+var_150]
0x18010a104  call    ??$FieldToStream@V?$optional@E@utl@@$0A@@SMBios@Shared@Compat@Windows@@YAXAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@PEBGAEBV?$optional@E@utl@@@Z; Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<uchar>,0>(std::basic_ostream<ushort> &,ushort const *,utl::optional<uchar> const &)
0x18010a109  lea     rdx, [rsp+2B0h+var_280]
0x18010a10e  mov     rcx, rdi
0x18010a111  call    ?Characteristics@SMBiosInformation@SMBios@Shared@Compat@Windows@@QEBA?AV?$optional@W4BiosCharacteristics@SMBios@Shared@Compat@Windows@@@utl@@XZ; Windows::Compat::Shared::SMBios::SMBiosInformation::Characteristics(void)
0x18010a116  mov     rbx, rax
0x18010a119  lea     rsi, asc_18013D858; "  "
0x18010a120  lea     rcx, [rbp+1B0h+var_150]
0x18010a124  mov     rdx, rsi
0x18010a127  cmp     [rax+4], r15b
0x18010a12b  jz      short loc_18010A176
0x18010a12d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18010a132  mov     rcx, rax
0x18010a135  lea     r14, asc_18013D798; "\""
0x18010a13c  mov     rdx, r14
0x18010a13f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18010a144  mov     rcx, rax
0x18010a147  lea     rdx, aCharacteristic; "Characteristics"
0x18010a14e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18010a153  mov     rcx, rax
0x18010a156  lea     rdx, asc_18013D79C; "\": \""
0x18010a15d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18010a162  mov     rdx, rbx
0x18010a165  mov     rcx, rax
0x18010a168  call    ??6SMBios@Shared@Compat@Windows@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV45@AEBW4BiosCharacteristics@0123@@Z; Windows::Compat::Shared::SMBios::operator<<(std::basic_ostream<ushort> &,Windows::Compat::Shared::SMBios::BiosCharacteristics const &)
0x18010a16d  lea     rdx, asc_18013D794; "\","
0x18010a174  jmp     short loc_18010A1A3
0x18010a176  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18010a17b  mov     rcx, rax
0x18010a17e  lea     r14, asc_18013D798; "\""
0x18010a185  mov     rdx, r14
0x18010a188  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18010a18d  mov     rcx, rax
0x18010a190  lea     rdx, aCharacteristic; "Characteristics"
0x18010a197  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18010a19c  lea     rdx, aNull_3; "\": null,"
0x18010a1a3  mov     rcx, rax
0x18010a1a6  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18010a1ab  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x18010a1b2  mov     rcx, rax
0x18010a1b5  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x18010a1bb  nop
0x18010a1bc  mov     bl, [rdi+83h]
0x18010a1c2  mov     rdx, r12
0x18010a1c5  lea     rcx, [rbp+1B0h+var_60]
0x18010a1cc  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18010a1d1  movups  xmm0, xmmword ptr [rdi+90h]
0x18010a1d8  movups  [rsp+2B0h+var_270], xmm0
0x18010a1dd  movups  xmm1, xmmword ptr [rdi+0A0h]
0x18010a1e4  movups  [rsp+2B0h+var_260], xmm1
0x18010a1e9  movups  xmm0, xmmword ptr [rdi+0B0h]
0x18010a1f0  movups  [rsp+2B0h+var_250], xmm0
0x18010a1f5  movups  xmm1, xmmword ptr [rdi+0C0h]
0x18010a1fc  movups  [rsp+2B0h+var_240], xmm1
0x18010a201  movups  xmm0, xmmword ptr [rdi+0D0h]
0x18010a208  movups  [rbp+1B0h+var_230], xmm0
0x18010a20c  movups  xmm1, xmmword ptr [rdi+0E0h]
0x18010a213  movups  [rbp+1B0h+var_220], xmm1
0x18010a217  movups  xmm0, xmmword ptr [rdi+0F0h]
0x18010a21e  movups  [rbp+1B0h+var_210], xmm0
0x18010a222  movups  xmm1, xmmword ptr [rdi+100h]
0x18010a229  movups  [rbp+1B0h+var_200], xmm1
0x18010a22d  movups  xmm0, xmmword ptr [rdi+110h]
0x18010a234  movups  [rbp+1B0h+var_1F0], xmm0
0x18010a238  movups  xmm1, xmmword ptr [rdi+120h]
0x18010a23f  movups  [rbp+1B0h+var_1E0], xmm1
0x18010a243  movups  xmm0, xmmword ptr [rdi+130h]
0x18010a24a  movups  [rbp+1B0h+var_1D0], xmm0
0x18010a24e  movups  xmm1, xmmword ptr [rdi+140h]
0x18010a255  movups  [rbp+1B0h+var_1C0], xmm1
0x18010a259  movups  xmm0, xmmword ptr [rdi+150h]
0x18010a260  movups  [rbp+1B0h+var_1B0], xmm0
0x18010a264  movups  xmm1, xmmword ptr [rdi+160h]
0x18010a26b  movups  [rbp+1B0h+var_1A0], xmm1
  ... truncated ...
```
