# Windows::Compat::Shared::SMBios::SMBiosInformation::operator std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180174ef0`
- end: `0x180175d78`
- name: `??BSMBiosInformation@SMBios@Shared@Compat@Windows@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `3720`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008dc0`
- `0x180016748`
- `0x1800167b4`
- `0x180019970`
- `0x18002b8fc`
- `0x180034188`
- `0x180067b58`
- `0x180068a84`
- `0x180069658`
- `0x180174054`
- `0x180174168`
- `0x18017427c`
- `0x18017433c`
- `0x180174498`
- `0x1801748e8`
- `0x180174a9c`
- `0x180174c44`
- `0x180174dec`
- `0x180174ef0`
- `0x180175d80`
- `0x180175fb0`
- `0x1801761e0`
- `0x180176410`
- `0x18017653c`
- `0x180176664`
- `0x180176938`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180174f49`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180174fb1`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180175317`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180175596`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180175633`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180175ce1`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180174f49`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180174fb1`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180175317`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180175596`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180175633`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180175ce1`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180175d45`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180175d45`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180175d38`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180175d38`

## string_xrefs

- `0x18017525b`: `RomSize`
- `0x18017552f`: `CharacteristicsExtension0`
- `0x180175571`: `CharacteristicsExtension0`
- `0x1801755cc`: `CharacteristicsExtension1`
- `0x18017560e`: `CharacteristicsExtension1`
- `0x180175b68`: `ExtendedRomSize`
- `0x180175c92`: `ExtendedRomSizeUnits`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Shared::SMBios::SMBiosInformation::operator std::wstring(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  char **v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  char v11; // bl
  __int64 *v12; // rax
  __int64 v13; // rax
  char v14; // bl
  __int64 *v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  const char *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  char v26; // bl
  __int64 *v27; // rax
  char v28; // bl
  __int64 *v29; // rax
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  const char *v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rbx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  const char *v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  char v50; // bl
  __int64 *v51; // rax
  char v52; // bl
  __int64 *v53; // rax
  char v54; // bl
  __int64 *v55; // rax
  char v56; // bl
  __int64 *v57; // rax
  char v58; // bl
  __int64 *v59; // rax
  char v60; // r15
  char v61; // bl
  __int64 *v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rcx
  __int64 v66; // rax
  const char *v67; // rdx
  __int64 v68; // rax
  _DWORD v70[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v71; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v72; // [rsp+50h] [rbp-B0h]
  __int128 v73; // [rsp+60h] [rbp-A0h]
  __int128 v74; // [rsp+70h] [rbp-90h]
  __int128 v75; // [rsp+80h] [rbp-80h]
  __int128 v76; // [rsp+90h] [rbp-70h]
  __int128 v77; // [rsp+A0h] [rbp-60h]
  __int128 v78; // [rsp+B0h] [rbp-50h]
  __int128 v79; // [rsp+C0h] [rbp-40h]
  __int128 v80; // [rsp+D0h] [rbp-30h]
  __int128 v81; // [rsp+E0h] [rbp-20h]
  __int128 v82; // [rsp+F0h] [rbp-10h]
  __int128 v83; // [rsp+100h] [rbp+0h]
  __int128 v84; // [rsp+110h] [rbp+10h]
  __int128 v85; // [rsp+120h] [rbp+20h]
  __int64 v86; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v87[8]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v88[120]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v89[104]; // [rsp+1B8h] [rbp+B8h] BYREF
  char *v90[4]; // [rsp+220h] [rbp+120h] BYREF
  char v91; // [rsp+240h] [rbp+140h]

  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v86);
  v4 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v86, "{");
  std::basic_ostream<unsigned short>::operator<<(v4, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v5 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v86, "\"Header\": ");
  Windows::Compat::Shared::SMBios::SmbStructHeader::operator std::wstring(a1 + 32, v90);
  v6 = v90;
  if ( v90[3] > (char *)7 )
    v6 = (char **)v90[0];
  v7 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v5, v6, v90[2]);
  v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v7, ",");
  std::basic_ostream<unsigned short>::operator<<(v8, std::endl<unsigned short,std::char_traits<unsigned short>>);
  std::wstring::~wstring(v90);
  v9 = Windows::Compat::Shared::SMBios::SMBiosInformation::Vendor(a1, v90);
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<std::wstring>,0>((__int64)&v86, (__int64)L"Vendor", v9);
  if ( v91 )
    std::wstring::~wstring(v90);
  v10 = Windows::Compat::Shared::SMBios::SMBiosInformation::Version(a1, v90);
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<std::wstring>,0>((__int64)&v86, (__int64)L"Version", v10);
  if ( v91 )
    std::wstring::~wstring(v90);
  v11 = *(_BYTE *)(a1 + 131);
  v12 = std::vector<unsigned char>::vector<unsigned char>((__int64 *)v90, a1 + 8);
  v71 = *(_OWORD *)(a1 + 144);
  v72 = *(_OWORD *)(a1 + 160);
  v73 = *(_OWORD *)(a1 + 176);
  v74 = *(_OWORD *)(a1 + 192);
  v75 = *(_OWORD *)(a1 + 208);
  v76 = *(_OWORD *)(a1 + 224);
  v77 = *(_OWORD *)(a1 + 240);
  v78 = *(_OWORD *)(a1 + 256);
  v79 = *(_OWORD *)(a1 + 272);
  v80 = *(_OWORD *)(a1 + 288);
  v81 = *(_OWORD *)(a1 + 304);
  v82 = *(_OWORD *)(a1 + 320);
  v83 = *(_OWORD *)(a1 + 336);
  v84 = *(_OWORD *)(a1 + 352);
  v85 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned short,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (__int64)v70,
    &v71,
    2,
    (__int64)v12,
    v11);
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned short>,0>(
    (__int64)&v86,
    (__int64)L"StartingAddressSegment",
    (unsigned __int16 *)v70);
  v13 = Windows::Compat::Shared::SMBios::SMBiosInformation::ReleaseDate(a1, v90);
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<std::wstring>,0>(
    (__int64)&v86,
    (__int64)L"ReleaseDate",
    v13);
  if ( v91 )
    std::wstring::~wstring(v90);
  v14 = *(_BYTE *)(a1 + 131);
  v15 = std::vector<unsigned char>::vector<unsigned char>((__int64 *)v90, a1 + 8);
  v71 = *(_OWORD *)(a1 + 144);
  v72 = *(_OWORD *)(a1 + 160);
  v73 = *(_OWORD *)(a1 + 176);
  v74 = *(_OWORD *)(a1 + 192);
  v75 = *(_OWORD *)(a1 + 208);
  v76 = *(_OWORD *)(a1 + 224);
  v77 = *(_OWORD *)(a1 + 240);
  v78 = *(_OWORD *)(a1 + 256);
  v79 = *(_OWORD *)(a1 + 272);
  v80 = *(_OWORD *)(a1 + 288);
  v81 = *(_OWORD *)(a1 + 304);
  v82 = *(_OWORD *)(a1 + 320);
  v83 = *(_OWORD *)(a1 + 336);
  v84 = *(_OWORD *)(a1 + 352);
  v85 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned char,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (__int64)v70,
    &v71,
    4,
    (__int64)v15,
    v14);
  if ( !BYTE1(v70[0]) || LOBYTE(v70[0]) == 0xFF )
    LOWORD(v70[0]) = 0;
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned char>,0>(
    (__int64)&v86,
    (__int64)L"RomSize",
    (unsigned __int8 *)v70);
  v16 = Windows::Compat::Shared::SMBios::SMBiosInformation::Characteristics(a1, v70);
  if ( *(_BYTE *)(v16 + 4) )
  {
    v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v86, L"  ");
    v18 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v17, "\"");
    v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, L"Characteristics");
    v20 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v19, "\": \"");
    v21 = Windows::Compat::Shared::SMBios::operator<<(v20, v16);
    v22 = "\",";
  }
  else
  {
    v23 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v86, L"  ");
    v24 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v23, "\"");
    v21 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v24, L"Characteristics");
    v22 = "\": null,";
  }
  v25 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v21, v22);
  std::basic_ostream<unsigned short>::operator<<(v25, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v26 = *(_BYTE *)(a1 + 131);
  v27 = std::vector<unsigned char>::vector<unsigned char>((__int64 *)v90, a1 + 8);
  v71 = *(_OWORD *)(a1 + 144);
  v72 = *(_OWORD *)(a1 + 160);
  v73 = *(_OWORD *)(a1 + 176);
  v74 = *(_OWORD *)(a1 + 192);
  v75 = *(_OWORD *)(a1 + 208);
  v76 = *(_OWORD *)(a1 + 224);
  v77 = *(_OWORD *)(a1 + 240);
  v78 = *(_OWORD *)(a1 + 256);
  v79 = *(_OWORD *)(a1 + 272);
  v80 = *(_OWORD *)(a1 + 288);
  v81 = *(_OWORD *)(a1 + 304);
  v82 = *(_OWORD *)(a1 + 320);
  v83 = *(_OWORD *)(a1 + 336);
  v84 = *(_OWORD *)(a1 + 352);
  v85 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned short,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (__int64)v70,
    &v71,
    6,
    (__int64)v27,
    v26);
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned short>,0>(
    (__int64)&v86,
    (__int64)L"BiosVendorReservedCharacteristics",
    (unsigned __int16 *)v70);
  v28 = *(_BYTE *)(a1 + 131);
  v29 = std::vector<unsigned char>::vector<unsigned char>((__int64 *)v90, a1 + 8);
  v71 = *(_OWORD *)(a1 + 144);
  v72 = *(_OWORD *)(a1 + 160);
  v73 = *(_OWORD *)(a1 + 176);
  v74 = *(_OWORD *)(a1 + 192);
  v75 = *(_OWORD *)(a1 + 208);
  v76 = *(_OWORD *)(a1 + 224);
  v77 = *(_OWORD *)(a1 + 240);
  v78 = *(_OWORD *)(a1 + 256);
  v79 = *(_OWORD *)(a1 + 272);
  v80 = *(_OWORD *)(a1 + 288);
  v81 = *(_OWORD *)(a1 + 304);
  v82 = *(_OWORD *)(a1 + 320);
  v83 = *(_OWORD *)(a1 + 336);
  v84 = *(_OWORD *)(a1 + 352);
  v85 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned short,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (__int64)v70,
    &v71,
    7,
    (__int64)v29,
    v28);
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned short>,0>(
    (__int64)&v86,
    (__int64)L"SystemVendorReservedCharacteristics",
    (unsigned __int16 *)v70);
  v30 = Windows::Compat::Shared::SMBios::SMBiosInformation::CharacteristicsExtension0(a1, v70);
  if ( *(_BYTE *)(v30 + 1) )
  {
    v31 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v86, L"  ");
    v32 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v31, "\"");
    v33 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v32, L"CharacteristicsExtension0");
    v34 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v33, "\": \"");
    v35 = Windows::Compat::Shared::SMBios::operator<<(v34, v30);
    v36 = "\",";
  }
  else
  {
    v37 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v86, L"  ");
    v38 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v37, "\"");
    v35 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v38, L"CharacteristicsExtension0");
    v36 = "\": null,";
  }
  v39 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v35, v36);
  std::basic_ostream<unsigned short>::operator<<(v39, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v40 = Windows::Compat::Shared::SMBios::SMBiosInformation::CharacteristicsExtension1(a1, v70);
  if ( *(_BYTE *)(v40 + 1) )
  {
    v41 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v86, L"  ");
    v42 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v41, "\"");
    v43 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v42, L"CharacteristicsExtension1");
    v44 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v43, "\": \"");
    v45 = Windows::Compat::Shared::SMBios::operator<<(v44, v40);
    v46 = "\",";
  }
  else
  {
    v47 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v86, L"  ");
    v48 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, "\"");
    v45 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v48, L"CharacteristicsExtension1");
    v46 = "\": null,";
  }
  v49 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v45, v46);
  std::basic_ostream<unsigned short>::operator<<(v49, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v50 = *(_BYTE *)(a1 + 131);
  v51 = std::vector<unsigned char>::vector<unsigned char>((__int64 *)v90, a1 + 8);
  v71 = *(_OWORD *)(a1 + 144);
  v72 = *(_OWORD *)(a1 + 160);
  v73 = *(_OWORD *)(a1 + 176);
  v74 = *(_OWORD *)(a1 + 192);
  v75 = *(_OWORD *)(a1 + 208);
  v76 = *(_OWORD *)(a1 + 224);
  v77 = *(_OWORD *)(a1 + 240);
  v78 = *(_OWORD *)(a1 + 256);
  v79 = *(_OWORD *)(a1 + 272);
  v80 = *(_OWORD *)(a1 + 288);
  v81 = *(_OWORD *)(a1 + 304);
  v82 = *(_OWORD *)(a1 + 320);
  v83 = *(_OWORD *)(a1 + 336);
  v84 = *(_OWORD *)(a1 + 352);
  v85 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned char,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (__int64)v70,
    &v71,
    10,
    (__int64)v51,
    v50);
  if ( !BYTE1(v70[0]) || LOBYTE(v70[0]) == 0xFF )
    LOWORD(v70[0]) = 0;
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned char>,0>(
    (__int64)&v86,
    (__int64)L"SystemBiosMajorRelease",
    (unsigned __int8 *)v70);
  v52 = *(_BYTE *)(a1 + 131);
  v53 = std::vector<unsigned char>::vector<unsigned char>((__int64 *)v90, a1 + 8);
  v71 = *(_OWORD *)(a1 + 144);
  v72 = *(_OWORD *)(a1 + 160);
  v73 = *(_OWORD *)(a1 + 176);
  v74 = *(_OWORD *)(a1 + 192);
  v75 = *(_OWORD *)(a1 + 208);
  v76 = *(_OWORD *)(a1 + 224);
  v77 = *(_OWORD *)(a1 + 240);
  v78 = *(_OWORD *)(a1 + 256);
  v79 = *(_OWORD *)(a1 + 272);
  v80 = *(_OWORD *)(a1 + 288);
  v81 = *(_OWORD *)(a1 + 304);
  v82 = *(_OWORD *)(a1 + 320);
  v83 = *(_OWORD *)(a1 + 336);
  v84 = *(_OWORD *)(a1 + 352);
  v85 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned char,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (__int64)v70,
    &v71,
    11,
    (__int64)v53,
    v52);
  if ( !BYTE1(v70[0]) || LOBYTE(v70[0]) == 0xFF )
    LOWORD(v70[0]) = 0;
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned char>,0>(
    (__int64)&v86,
    (__int64)L"SystemBiosMinorRelease",
    (unsigned __int8 *)v70);
  v54 = *(_BYTE *)(a1 + 131);
  v55 = std::vector<unsigned char>::vector<unsigned char>((__int64 *)v90, a1 + 8);
  v71 = *(_OWORD *)(a1 + 144);
  v72 = *(_OWORD *)(a1 + 160);
  v73 = *(_OWORD *)(a1 + 176);
  v74 = *(_OWORD *)(a1 + 192);
  v75 = *(_OWORD *)(a1 + 208);
  v76 = *(_OWORD *)(a1 + 224);
  v77 = *(_OWORD *)(a1 + 240);
  v78 = *(_OWORD *)(a1 + 256);
  v79 = *(_OWORD *)(a1 + 272);
  v80 = *(_OWORD *)(a1 + 288);
  v81 = *(_OWORD *)(a1 + 304);
  v82 = *(_OWORD *)(a1 + 320);
  v83 = *(_OWORD *)(a1 + 336);
  v84 = *(_OWORD *)(a1 + 352);
  v85 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned char,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (__int64)v70,
    &v71,
    12,
    (__int64)v55,
    v54);
  if ( !BYTE1(v70[0]) || LOBYTE(v70[0]) == 0xFF )
    LOWORD(v70[0]) = 0;
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned char>,0>(
    (__int64)&v86,
    (__int64)L"ECFirmwareMajorRelease",
    (unsigned __int8 *)v70);
  v56 = *(_BYTE *)(a1 + 131);
  v57 = std::vector<unsigned char>::vector<unsigned char>((__int64 *)v90, a1 + 8);
  v71 = *(_OWORD *)(a1 + 144);
  v72 = *(_OWORD *)(a1 + 160);
  v73 = *(_OWORD *)(a1 + 176);
  v74 = *(_OWORD *)(a1 + 192);
  v75 = *(_OWORD *)(a1 + 208);
  v76 = *(_OWORD *)(a1 + 224);
  v77 = *(_OWORD *)(a1 + 240);
  v78 = *(_OWORD *)(a1 + 256);
  v79 = *(_OWORD *)(a1 + 272);
  v80 = *(_OWORD *)(a1 + 288);
  v81 = *(_OWORD *)(a1 + 304);
  v82 = *(_OWORD *)(a1 + 320);
  v83 = *(_OWORD *)(a1 + 336);
  v84 = *(_OWORD *)(a1 + 352);
  v85 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned char,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (__int64)v70,
    &v71,
    13,
    (__int64)v57,
    v56);
  if ( !BYTE1(v70[0]) || LOBYTE(v70[0]) == 0xFF )
    LOWORD(v70[0]) = 0;
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned char>,0>(
    (__int64)&v86,
    (__int64)L"ECFirmwareMinorRelease",
    (unsigned __int8 *)v70);
  v58 = *(_BYTE *)(a1 + 131);
  v59 = std::vector<unsigned char>::vector<unsigned char>((__int64 *)v90, a1 + 8);
  v71 = *(_OWORD *)(a1 + 144);
  v72 = *(_OWORD *)(a1 + 160);
  v73 = *(_OWORD *)(a1 + 176);
  v74 = *(_OWORD *)(a1 + 192);
  v75 = *(_OWORD *)(a1 + 208);
  v76 = *(_OWORD *)(a1 + 224);
  v77 = *(_OWORD *)(a1 + 240);
  v78 = *(_OWORD *)(a1 + 256);
  v79 = *(_OWORD *)(a1 + 272);
  v80 = *(_OWORD *)(a1 + 288);
  v81 = *(_OWORD *)(a1 + 304);
  v82 = *(_OWORD *)(a1 + 320);
  v83 = *(_OWORD *)(a1 + 336);
  v84 = *(_OWORD *)(a1 + 352);
  v85 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned short,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (__int64)v70,
    &v71,
    14,
    (__int64)v59,
    v58);
  v60 = 1;
  if ( BYTE2(v70[0]) )
  {
    LOWORD(v70[0]) &= 0x3FFFu;
    BYTE2(v70[0]) = 1;
  }
  else
  {
    v70[0] = 0;
  }
  Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<unsigned short>,0>(
    (__int64)&v86,
    (__int64)L"ExtendedRomSize",
    (unsigned __int16 *)v70);
  v61 = *(_BYTE *)(a1 + 131);
  v62 = std::vector<unsigned char>::vector<unsigned char>((__int64 *)v90, a1 + 8);
  v71 = *(_OWORD *)(a1 + 144);
  v72 = *(_OWORD *)(a1 + 160);
  v73 = *(_OWORD *)(a1 + 176);
  v74 = *(_OWORD *)(a1 + 192);
  v75 = *(_OWORD *)(a1 + 208);
  v76 = *(_OWORD *)(a1 + 224);
  v77 = *(_OWORD *)(a1 + 240);
  v78 = *(_OWORD *)(a1 + 256);
  v79 = *(_OWORD *)(a1 + 272);
  v80 = *(_OWORD *)(a1 + 288);
  v81 = *(_OWORD *)(a1 + 304);
  v82 = *(_OWORD *)(a1 + 320);
  v83 = *(_OWORD *)(a1 + 336);
  v84 = *(_OWORD *)(a1 + 352);
  v85 = *(_OWORD *)(a1 + 368);
  Windows::Compat::Shared::SMBios::GetField<unsigned short,std::array<Windows::Compat::Shared::SMBios::StructField<enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,enum Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(
    (__int64)v70,
    &v71,
    14,
    (__int64)v62,
    v61);
  if ( BYTE2(v70[0]) )
  {
    LOBYTE(v70[0]) = LOWORD(v70[0]) >> 14;
  }
  else
  {
    LOWORD(v70[0]) = 0;
    v60 = 0;
  }
  BYTE1(v70[0]) = v60;
  v63 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v86, L"  ");
  v64 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v63, "\"");
  v65 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v64, L"ExtendedRomSizeUnits");
  if ( v60 )
  {
    v66 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v65, "\": \"");
    v65 = Windows::Compat::Shared::SMBios::operator<<(v66, v70);
    v67 = "\",";
  }
  else
  {
    v67 = "\": null,";
  }
  v68 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v65, v67);
  std::basic_ostream<unsigned short>::operator<<(v68, std::endl<unsigned short,std::char_traits<unsigned short>>);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v86, "}");
  std::basic_stringbuf<unsigned short>::str(v87, a2);
  *(_QWORD *)&v87[*(int *)(v86 + 4) - 8] = &std::basic_ostringstream<unsigned short>::`vftable';
  *(_DWORD *)((char *)&v85 + *(int *)(v86 + 4) + 12) = *(_DWORD *)(v86 + 4) - 136;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v87);
  std::basic_ostream<unsigned short>::~basic_ostream<unsigned short,std::char_traits<unsigned short>>(v88);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v89);
  return a2;
}

```

## disassembly

```asm
0x180174ef0  mov     [rsp-8+arg_10], rbx
0x180174ef5  push    rbp
0x180174ef6  push    rsi
0x180174ef7  push    rdi
0x180174ef8  push    r12
0x180174efa  push    r13
0x180174efc  push    r14
0x180174efe  push    r15
0x180174f00  lea     rbp, [rsp-150h]
0x180174f08  sub     rsp, 250h
0x180174f0f  mov     rax, cs:__security_cookie
0x180174f16  xor     rax, rsp
0x180174f19  mov     [rbp+180h+var_38], rax
0x180174f20  mov     r13, rdx
0x180174f23  mov     rdi, rcx
0x180174f26  lea     rcx, [rbp+180h+var_150]
0x180174f2a  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180174f2f  lea     rdx, asc_1801B7954; "{"
0x180174f36  lea     rcx, [rbp+180h+var_150]
0x180174f3a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180174f3f  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x180174f46  mov     rcx, rax
0x180174f49  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x180174f4f  lea     rdx, aHeader; "\"Header\": "
0x180174f56  lea     rcx, [rbp+180h+var_150]
0x180174f5a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180174f5f  mov     rbx, rax
0x180174f62  lea     rcx, [rdi+20h]
0x180174f66  lea     rdx, [rbp+180h+var_60]
0x180174f6d  call    ??BSmbStructHeader@SMBios@Shared@Compat@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Compat::Shared::SMBios::SmbStructHeader::operator std::wstring(void)
0x180174f72  lea     rdx, [rbp+180h+var_60]
0x180174f79  cmp     [rbp+180h+var_48], 7
0x180174f81  cmova   rdx, [rbp+180h+var_60]
0x180174f89  mov     r8, [rbp+180h+var_50]
0x180174f90  mov     rcx, rbx
0x180174f93  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x180174f98  lea     rdx, asc_1801BCDD4; ","
0x180174f9f  mov     rcx, rax
0x180174fa2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180174fa7  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x180174fae  mov     rcx, rax
0x180174fb1  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x180174fb7  lea     rcx, [rbp+180h+var_60]
0x180174fbe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180174fc3  lea     rdx, [rbp+180h+var_60]
0x180174fca  mov     rcx, rdi
0x180174fcd  call    ?Vendor@SMBiosInformation@SMBios@Shared@Compat@Windows@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@XZ; Windows::Compat::Shared::SMBios::SMBiosInformation::Vendor(void)
0x180174fd2  mov     r8, rax
0x180174fd5  lea     rdx, aVendor; "Vendor"
0x180174fdc  lea     rcx, [rbp+180h+var_150]
0x180174fe0  call    ??$FieldToStream@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@$0A@@SMBios@Shared@Compat@Windows@@YAXAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@PEBGAEBV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@@Z; Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<std::wstring>,0>(std::basic_ostream<ushort> &,ushort const *,utl::optional<std::wstring> const &)
0x180174fe5  xor     r15d, r15d
0x180174fe8  cmp     [rbp+180h+var_40], r15b
0x180174fef  jz      short loc_180174FFD
0x180174ff1  lea     rcx, [rbp+180h+var_60]
0x180174ff8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180174ffd  lea     rdx, [rbp+180h+var_60]
0x180175004  mov     rcx, rdi
0x180175007  call    ?Version@SMBiosInformation@SMBios@Shared@Compat@Windows@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@XZ; Windows::Compat::Shared::SMBios::SMBiosInformation::Version(void)
0x18017500c  mov     r8, rax
0x18017500f  lea     rdx, aVersion; "Version"
0x180175016  lea     rcx, [rbp+180h+var_150]
0x18017501a  call    ??$FieldToStream@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@$0A@@SMBios@Shared@Compat@Windows@@YAXAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@PEBGAEBV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@@Z; Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<std::wstring>,0>(std::basic_ostream<ushort> &,ushort const *,utl::optional<std::wstring> const &)
0x18017501f  cmp     [rbp+180h+var_40], r15b
0x180175026  jz      short loc_180175035
0x180175028  lea     rcx, [rbp+180h+var_60]
0x18017502f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180175034  nop
0x180175035  mov     bl, [rdi+83h]
0x18017503b  lea     r12, [rdi+8]
0x18017503f  mov     rdx, r12
0x180175042  lea     rcx, [rbp+180h+var_60]
0x180175049  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18017504e  movups  xmm0, xmmword ptr [rdi+90h]
0x180175055  movups  [rsp+280h+var_240], xmm0
0x18017505a  movups  xmm1, xmmword ptr [rdi+0A0h]
0x180175061  movups  [rsp+280h+var_230], xmm1
0x180175066  movups  xmm0, xmmword ptr [rdi+0B0h]
0x18017506d  movups  [rsp+280h+var_220], xmm0
0x180175072  movups  xmm1, xmmword ptr [rdi+0C0h]
0x180175079  movups  [rsp+280h+var_210], xmm1
0x18017507e  movups  xmm0, xmmword ptr [rdi+0D0h]
0x180175085  movups  [rbp+180h+var_200], xmm0
0x180175089  movups  xmm1, xmmword ptr [rdi+0E0h]
0x180175090  movups  [rbp+180h+var_1F0], xmm1
0x180175094  movups  xmm0, xmmword ptr [rdi+0F0h]
0x18017509b  movups  [rbp+180h+var_1E0], xmm0
0x18017509f  movups  xmm1, xmmword ptr [rdi+100h]
0x1801750a6  movups  [rbp+180h+var_1D0], xmm1
0x1801750aa  movups  xmm0, xmmword ptr [rdi+110h]
0x1801750b1  movups  [rbp+180h+var_1C0], xmm0
0x1801750b5  movups  xmm1, xmmword ptr [rdi+120h]
0x1801750bc  movups  [rbp+180h+var_1B0], xmm1
0x1801750c0  movups  xmm0, xmmword ptr [rdi+130h]
0x1801750c7  movups  [rbp+180h+var_1A0], xmm0
0x1801750cb  movups  xmm1, xmmword ptr [rdi+140h]
0x1801750d2  movups  [rbp+180h+var_190], xmm1
0x1801750d6  movups  xmm0, xmmword ptr [rdi+150h]
0x1801750dd  movups  [rbp+180h+var_180], xmm0
0x1801750e1  movups  xmm1, xmmword ptr [rdi+160h]
0x1801750e8  movups  [rbp+180h+var_170], xmm1
0x1801750ec  movups  xmm0, xmmword ptr [rdi+170h]
0x1801750f3  movups  [rbp+180h+var_160], xmm0
0x1801750f7  mov     [rsp+280h+var_260], bl
0x1801750fb  mov     r9, rax
0x1801750fe  mov     r8d, 2
0x180175104  lea     rdx, [rsp+280h+var_240]
0x180175109  lea     rcx, [rsp+280h+var_250]
0x18017510e  call    ??$GetField@GV?$array@U?$StructField@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@$0P@@std@@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@YA?AV?$optional@G@utl@@V?$array@U?$StructField@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@$0P@@std@@W4BiosInformationField@SMBiosInformation@0123@V?$vector@EV?$allocator@E@std@@@7@_N@Z; Windows::Compat::Shared::SMBios::GetField<ushort,std::array<Windows::Compat::Shared::SMBios::StructField<Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(std::array<Windows::Compat::Shared::SMBios::StructField<Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField,std::vector<uchar>,bool)
0x180175113  nop
0x180175114  lea     r8, [rsp+280h+var_250]
0x180175119  lea     rdx, aStartingaddres; "StartingAddressSegment"
0x180175120  lea     rcx, [rbp+180h+var_150]
0x180175124  call    ??$FieldToStream@V?$optional@G@utl@@$0A@@SMBios@Shared@Compat@Windows@@YAXAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@PEBGAEBV?$optional@G@utl@@@Z; Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<ushort>,0>(std::basic_ostream<ushort> &,ushort const *,utl::optional<ushort> const &)
0x180175129  lea     rdx, [rbp+180h+var_60]
0x180175130  mov     rcx, rdi
0x180175133  call    ?ReleaseDate@SMBiosInformation@SMBios@Shared@Compat@Windows@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@XZ; Windows::Compat::Shared::SMBios::SMBiosInformation::ReleaseDate(void)
0x180175138  mov     r8, rax
0x18017513b  lea     rdx, aReleasedate; "ReleaseDate"
0x180175142  lea     rcx, [rbp+180h+var_150]
0x180175146  call    ??$FieldToStream@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@$0A@@SMBios@Shared@Compat@Windows@@YAXAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@PEBGAEBV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@utl@@@Z; Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<std::wstring>,0>(std::basic_ostream<ushort> &,ushort const *,utl::optional<std::wstring> const &)
0x18017514b  cmp     [rbp+180h+var_40], r15b
0x180175152  jz      short loc_180175161
0x180175154  lea     rcx, [rbp+180h+var_60]
0x18017515b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180175160  nop
0x180175161  mov     bl, [rdi+83h]
0x180175167  mov     rdx, r12
0x18017516a  lea     rcx, [rbp+180h+var_60]
0x180175171  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180175176  movups  xmm0, xmmword ptr [rdi+90h]
0x18017517d  movups  [rsp+280h+var_240], xmm0
0x180175182  movups  xmm1, xmmword ptr [rdi+0A0h]
0x180175189  movups  [rsp+280h+var_230], xmm1
0x18017518e  movups  xmm0, xmmword ptr [rdi+0B0h]
0x180175195  movups  [rsp+280h+var_220], xmm0
0x18017519a  movups  xmm1, xmmword ptr [rdi+0C0h]
0x1801751a1  movups  [rsp+280h+var_210], xmm1
0x1801751a6  movups  xmm0, xmmword ptr [rdi+0D0h]
0x1801751ad  movups  [rbp+180h+var_200], xmm0
0x1801751b1  movups  xmm1, xmmword ptr [rdi+0E0h]
0x1801751b8  movups  [rbp+180h+var_1F0], xmm1
0x1801751bc  movups  xmm0, xmmword ptr [rdi+0F0h]
0x1801751c3  movups  [rbp+180h+var_1E0], xmm0
0x1801751c7  movups  xmm1, xmmword ptr [rdi+100h]
0x1801751ce  movups  [rbp+180h+var_1D0], xmm1
0x1801751d2  movups  xmm0, xmmword ptr [rdi+110h]
0x1801751d9  movups  [rbp+180h+var_1C0], xmm0
0x1801751dd  movups  xmm1, xmmword ptr [rdi+120h]
0x1801751e4  movups  [rbp+180h+var_1B0], xmm1
0x1801751e8  movups  xmm0, xmmword ptr [rdi+130h]
0x1801751ef  movups  [rbp+180h+var_1A0], xmm0
0x1801751f3  movups  xmm1, xmmword ptr [rdi+140h]
0x1801751fa  movups  [rbp+180h+var_190], xmm1
0x1801751fe  movups  xmm0, xmmword ptr [rdi+150h]
0x180175205  movups  [rbp+180h+var_180], xmm0
0x180175209  movups  xmm1, xmmword ptr [rdi+160h]
0x180175210  movups  [rbp+180h+var_170], xmm1
0x180175214  movups  xmm0, xmmword ptr [rdi+170h]
0x18017521b  movups  [rbp+180h+var_160], xmm0
0x18017521f  mov     [rsp+280h+var_260], bl
0x180175223  mov     r9, rax
0x180175226  mov     r8d, 4
0x18017522c  lea     rdx, [rsp+280h+var_240]
0x180175231  lea     rcx, [rsp+280h+var_250]
0x180175236  call    ??$GetField@EV?$array@U?$StructField@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@$0P@@std@@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@YA?AV?$optional@E@utl@@V?$array@U?$StructField@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@$0P@@std@@W4BiosInformationField@SMBiosInformation@0123@V?$vector@EV?$allocator@E@std@@@7@_N@Z; Windows::Compat::Shared::SMBios::GetField<uchar,std::array<Windows::Compat::Shared::SMBios::StructField<Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(std::array<Windows::Compat::Shared::SMBios::StructField<Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField,std::vector<uchar>,bool)
0x18017523b  cmp     byte ptr [rsp+280h+var_250+1], r15b
0x180175240  jz      short loc_180175250
0x180175242  movzx   eax, word ptr [rsp+280h+var_250]
0x180175247  cmp     al, 0FFh
0x180175249  mov     word ptr [rsp+280h+var_250], ax
0x18017524e  jnz     short loc_180175256
0x180175250  mov     word ptr [rsp+280h+var_250], r15w
0x180175256  lea     r8, [rsp+280h+var_250]
0x18017525b  lea     rdx, aRomsize; "RomSize"
0x180175262  lea     rcx, [rbp+180h+var_150]
0x180175266  call    ??$FieldToStream@V?$optional@E@utl@@$0A@@SMBios@Shared@Compat@Windows@@YAXAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@PEBGAEBV?$optional@E@utl@@@Z; Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<uchar>,0>(std::basic_ostream<ushort> &,ushort const *,utl::optional<uchar> const &)
0x18017526b  lea     rdx, [rsp+280h+var_250]
0x180175270  mov     rcx, rdi
0x180175273  call    ?Characteristics@SMBiosInformation@SMBios@Shared@Compat@Windows@@QEBA?AV?$optional@W4BiosCharacteristics@SMBios@Shared@Compat@Windows@@@utl@@XZ; Windows::Compat::Shared::SMBios::SMBiosInformation::Characteristics(void)
0x180175278  mov     rbx, rax
0x18017527b  lea     rsi, asc_1801D443C; "  "
0x180175282  lea     rcx, [rbp+180h+var_150]
0x180175286  mov     rdx, rsi
0x180175289  cmp     [rax+4], r15b
0x18017528d  jz      short loc_1801752D8
0x18017528f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180175294  mov     rcx, rax
0x180175297  lea     r14, asc_1801BD0F4; "\""
0x18017529e  mov     rdx, r14
0x1801752a1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x1801752a6  mov     rcx, rax
0x1801752a9  lea     rdx, aCharacteristic; "Characteristics"
0x1801752b0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801752b5  mov     rcx, rax
0x1801752b8  lea     rdx, asc_1801D41A8; "\": \""
0x1801752bf  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x1801752c4  mov     rdx, rbx
0x1801752c7  mov     rcx, rax
0x1801752ca  call    ??6SMBios@Shared@Compat@Windows@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV45@AEBW4BiosCharacteristics@0123@@Z; Windows::Compat::Shared::SMBios::operator<<(std::basic_ostream<ushort> &,Windows::Compat::Shared::SMBios::BiosCharacteristics const &)
0x1801752cf  lea     rdx, asc_1801D41A4; "\","
0x1801752d6  jmp     short loc_180175305
0x1801752d8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801752dd  mov     rcx, rax
0x1801752e0  lea     r14, asc_1801BD0F4; "\""
0x1801752e7  mov     rdx, r14
0x1801752ea  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x1801752ef  mov     rcx, rax
0x1801752f2  lea     rdx, aCharacteristic; "Characteristics"
0x1801752f9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801752fe  lea     rdx, aNull_2; "\": null,"
0x180175305  mov     rcx, rax
0x180175308  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18017530d  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x180175314  mov     rcx, rax
0x180175317  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x18017531d  nop
0x18017531e  mov     bl, [rdi+83h]
0x180175324  mov     rdx, r12
0x180175327  lea     rcx, [rbp+180h+var_60]
0x18017532e  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180175333  movups  xmm0, xmmword ptr [rdi+90h]
0x18017533a  movups  [rsp+280h+var_240], xmm0
0x18017533f  movups  xmm1, xmmword ptr [rdi+0A0h]
0x180175346  movups  [rsp+280h+var_230], xmm1
0x18017534b  movups  xmm0, xmmword ptr [rdi+0B0h]
0x180175352  movups  [rsp+280h+var_220], xmm0
0x180175357  movups  xmm1, xmmword ptr [rdi+0C0h]
0x18017535e  movups  [rsp+280h+var_210], xmm1
0x180175363  movups  xmm0, xmmword ptr [rdi+0D0h]
0x18017536a  movups  [rbp+180h+var_200], xmm0
0x18017536e  movups  xmm1, xmmword ptr [rdi+0E0h]
0x180175375  movups  [rbp+180h+var_1F0], xmm1
0x180175379  movups  xmm0, xmmword ptr [rdi+0F0h]
0x180175380  movups  [rbp+180h+var_1E0], xmm0
0x180175384  movups  xmm1, xmmword ptr [rdi+100h]
0x18017538b  movups  [rbp+180h+var_1D0], xmm1
0x18017538f  movups  xmm0, xmmword ptr [rdi+110h]
0x180175396  movups  [rbp+180h+var_1C0], xmm0
0x18017539a  movups  xmm1, xmmword ptr [rdi+120h]
0x1801753a1  movups  [rbp+180h+var_1B0], xmm1
0x1801753a5  movups  xmm0, xmmword ptr [rdi+130h]
0x1801753ac  movups  [rbp+180h+var_1A0], xmm0
0x1801753b0  movups  xmm1, xmmword ptr [rdi+140h]
0x1801753b7  movups  [rbp+180h+var_190], xmm1
0x1801753bb  movups  xmm0, xmmword ptr [rdi+150h]
0x1801753c2  movups  [rbp+180h+var_180], xmm0
0x1801753c6  movups  xmm1, xmmword ptr [rdi+160h]
0x1801753cd  movups  [rbp+180h+var_170], xmm1
0x1801753d1  movups  xmm0, xmmword ptr [rdi+170h]
0x1801753d8  movups  [rbp+180h+var_160], xmm0
0x1801753dc  mov     [rsp+280h+var_260], bl
0x1801753e0  mov     r9, rax
0x1801753e3  mov     r8d, 6
0x1801753e9  lea     rdx, [rsp+280h+var_240]
0x1801753ee  lea     rcx, [rsp+280h+var_250]
0x1801753f3  call    ??$GetField@GV?$array@U?$StructField@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@$0P@@std@@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@YA?AV?$optional@G@utl@@V?$array@U?$StructField@W4BiosInformationField@SMBiosInformation@SMBios@Shared@Compat@Windows@@@SMBios@Shared@Compat@Windows@@$0P@@std@@W4BiosInformationField@SMBiosInformation@0123@V?$vector@EV?$allocator@E@std@@@7@_N@Z; Windows::Compat::Shared::SMBios::GetField<ushort,std::array<Windows::Compat::Shared::SMBios::StructField<Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>(std::array<Windows::Compat::Shared::SMBios::StructField<Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField>,15>,Windows::Compat::Shared::SMBios::SMBiosInformation::BiosInformationField,std::vector<uchar>,bool)
0x1801753f8  nop
0x1801753f9  lea     r8, [rsp+280h+var_250]
0x1801753fe  lea     rdx, aBiosvendorrese; "BiosVendorReservedCharacteristics"
0x180175405  lea     rcx, [rbp+180h+var_150]
0x180175409  call    ??$FieldToStream@V?$optional@G@utl@@$0A@@SMBios@Shared@Compat@Windows@@YAXAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@PEBGAEBV?$optional@G@utl@@@Z; Windows::Compat::Shared::SMBios::FieldToStream<utl::optional<ushort>,0>(std::basic_ostream<ushort> &,ushort const *,utl::optional<ushort> const &)
0x18017540e  nop
0x18017540f  mov     bl, [rdi+83h]
0x180175415  mov     rdx, r12
0x180175418  lea     rcx, [rbp+180h+var_60]
0x18017541f  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180175424  movups  xmm0, xmmword ptr [rdi+90h]
0x18017542b  movups  [rsp+280h+var_240], xmm0
0x180175430  movups  xmm1, xmmword ptr [rdi+0A0h]
0x180175437  movups  [rsp+280h+var_230], xmm1
0x18017543c  movups  xmm0, xmmword ptr [rdi+0B0h]
0x180175443  movups  [rsp+280h+var_220], xmm0
0x180175448  movups  xmm1, xmmword ptr [rdi+0C0h]
0x18017544f  movups  [rsp+280h+var_210], xmm1
0x180175454  movups  xmm0, xmmword ptr [rdi+0D0h]
0x18017545b  movups  [rbp+180h+var_200], xmm0
0x18017545f  movups  xmm1, xmmword ptr [rdi+0E0h]
0x180175466  movups  [rbp+180h+var_1F0], xmm1
0x18017546a  movups  xmm0, xmmword ptr [rdi+0F0h]
0x180175471  movups  [rbp+180h+var_1E0], xmm0
0x180175475  movups  xmm1, xmmword ptr [rdi+100h]
0x18017547c  movups  [rbp+180h+var_1D0], xmm1
0x180175480  movups  xmm0, xmmword ptr [rdi+110h]
0x180175487  movups  [rbp+180h+var_1C0], xmm0
0x18017548b  movups  xmm1, xmmword ptr [rdi+120h]
0x180175492  movups  [rbp+180h+var_1B0], xmm1
0x180175496  movups  xmm0, xmmword ptr [rdi+130h]
0x18017549d  movups  [rbp+180h+var_1A0], xmm0
0x1801754a1  movups  xmm1, xmmword ptr [rdi+140h]
0x1801754a8  movups  [rbp+180h+var_190], xmm1
0x1801754ac  movups  xmm0, xmmword ptr [rdi+150h]
0x1801754b3  movups  [rbp+180h+var_180], xmm0
0x1801754b7  movups  xmm1, xmmword ptr [rdi+160h]
0x1801754be  movups  [rbp+180h+var_170], xmm1
0x1801754c2  movups  xmm0, xmmword ptr [rdi+170h]
0x1801754c9  movups  [rbp+180h+var_160], xmm0
0x1801754cd  mov     [rsp+280h+var_260], bl
0x1801754d1  mov     r9, rax
0x1801754d4  mov     r8d, 7
  ... truncated ...
```
