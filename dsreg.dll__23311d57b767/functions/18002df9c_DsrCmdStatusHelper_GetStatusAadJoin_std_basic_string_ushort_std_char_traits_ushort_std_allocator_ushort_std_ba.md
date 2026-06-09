# DsrCmdStatusHelper::GetStatusAadJoin(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool &,bool &)

- ea: `0x18002df9c`
- end: `0x18002fe8a`
- name: `?GetStatusAadJoin@DsrCmdStatusHelper@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0000AEA_N1@Z`
- size: `7918`
- prototype: ``
- caller_count: `4`
- callee_count: `43`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a523c`
- `0x1800a674c`
- `0x1800aee10`
- `0x1800b0bf8`

## callees

- `0x18000ab70`
- `0x18000bd20`
- `0x180012948`
- `0x180012c7c`
- `0x18001378c`
- `0x1800154f8`
- `0x1800155a4`
- `0x180015f3c`
- `0x180016190`
- `0x180016ae0`
- `0x180016b90`
- `0x180017ad8`
- `0x18001a7e8`
- `0x18001a900`
- `0x18001f624`
- `0x18001fc10`
- `0x180025db0`
- `0x18002927c`
- `0x1800292ac`
- `0x180029360`
- `0x1800294cc`
- `0x180029554`
- `0x180029c78`
- `0x18002b9b4`
- `0x18002b9f4`
- `0x18002dde4`
- `0x18002deec`
- `0x18002df9c`
- `0x18002fe90`
- `0x180031930`
- `0x1800319ac`
- `0x180031d10`
- `0x180032254`
- `0x180036b74`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x180079ec0`
- `0x1800a1e6c`
- `0x1800a1f84`
- `0x1800a2010`
- `0x1800a250c`
- `0x1800aa97c`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18002ef85`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18002ef85`

## string_xrefs

- `0x18002f2e1`: `MdmComplianceUrl`
- `0x18002f1c7`: `AccessTokenUrl`
- `0x18002e097`: `AzureAdJoined`
- `0x18002e140`: `AzureAdJoined`
- `0x18002e377`: `AzureAdJoined`
- `0x18002e6b8`: `FAILED. Device is either disabled or deleted`
- `0x18002e9f4`: `Last HostName Update`

## pseudocode

```c
// Hidden C++ exception states: #wind=37
__int64 __fastcall DsrCmdStatusHelper::GetStatusAadJoin(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _BYTE *a6,
        _BYTE *a7)
{
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 CurrentRef; // rax
  int JoinInfo; // ebx
  _QWORD *ErrorMsgRow; // rax
  __int64 v16; // rcx
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  _QWORD *MsgRow; // rax
  _QWORD *v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rbx
  _QWORD *v27; // rax
  int CertificateThumbprint; // ebx
  _QWORD *v29; // rax
  __int64 v30; // rbx
  _QWORD *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rbx
  _QWORD *v34; // rax
  __int64 v35; // rax
  _QWORD *v36; // rax
  int v37; // ebx
  unsigned int v38; // edi
  const wchar_t *v39; // rdx
  __int64 v40; // rbx
  _QWORD *ErrorCode; // rax
  _QWORD *v42; // rax
  unsigned int i; // edi
  int IsAttributeUpdateNeeded; // esi
  const wchar_t *v45; // rbx
  __int64 v46; // rax
  _QWORD *v47; // rax
  __int64 AttributeUpdateStateKey; // rbx
  _QWORD *v49; // rax
  bool v50; // bl
  int HostNameStatus; // ebx
  _QWORD *v52; // rax
  wchar_t **v53; // rcx
  __int64 v54; // rdi
  _QWORD *v55; // rax
  int v56; // ebx
  _QWORD *v57; // rax
  wchar_t **v58; // rcx
  _QWORD *v59; // rax
  __int64 v60; // rbx
  _QWORD *v61; // rax
  _QWORD *TimeMsgRow; // rax
  _QWORD *MsgRowIfNotEmpty; // rax
  _QWORD *v64; // rax
  _QWORD *v65; // rax
  _QWORD *v66; // rax
  _QWORD *v67; // rax
  _QWORD *v68; // rax
  int v69; // edi
  _QWORD *v70; // rax
  wchar_t **v71; // rcx
  __int64 v72; // rbx
  _QWORD *v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  int v77; // ebx
  int v78; // ebx
  __int64 v79; // r8
  const wchar_t *v80; // rdx
  __int64 v81; // rax
  __int64 v82; // rbx
  _QWORD *v83; // rax
  __int64 v84; // rbx
  _QWORD *v85; // rax
  __int64 v86; // rbx
  _QWORD *v87; // rax
  __int64 v88; // rbx
  _QWORD *v89; // rax
  __int64 v90; // rbx
  _QWORD *v91; // rax
  __int64 v92; // rbx
  _QWORD *v93; // rax
  __int64 v94; // rbx
  _QWORD *v95; // rax
  __int64 v96; // rbx
  _QWORD *v97; // rax
  __int64 v98; // rbx
  _QWORD *v99; // rax
  __int64 v100; // rbx
  _QWORD *v101; // rax
  __int64 v102; // rbx
  _QWORD *v103; // rax
  __int64 v104; // rbx
  _QWORD *v105; // rax
  __int64 v106; // rbx
  _QWORD *v107; // rax
  __int64 v108; // rbx
  _QWORD *v109; // rax
  __int64 v110; // rbx
  _QWORD *v111; // rax
  __int64 v112; // rbx
  _QWORD *v113; // rax
  __int64 v114; // rbx
  _QWORD *v115; // rax
  __int64 v116; // rbx
  _QWORD *v117; // rax
  __int64 v118; // rbx
  _QWORD *v119; // rax
  __int64 v120; // rbx
  _QWORD *v121; // rax
  __int64 v122; // rbx
  _QWORD *v123; // rax
  __int64 v124; // rbx
  _QWORD *v125; // rax
  __int64 v126; // rbx
  _QWORD *v127; // rax
  __int64 v128; // rbx
  _QWORD *v129; // rax
  __int64 v130; // rbx
  _QWORD *v131; // rax
  __int64 v132; // rbx
  _QWORD *v133; // rax
  int v134; // ebx
  _QWORD *v135; // rax
  __int64 v136; // rbx
  _QWORD *v137; // rax
  _WORD *v138; // rcx
  int v139; // ebx
  _QWORD *v140; // rax
  __int64 v141; // rdx
  __int64 v142; // rcx
  const wchar_t *v143; // rcx
  __int64 v144; // rdx
  __int64 v145; // rcx
  _QWORD *v146; // rax
  __int64 v147; // rdx
  __int64 v148; // rdx
  __int64 v149; // rcx
  const wchar_t *v150; // rbx
  __int64 v151; // rax
  const unsigned __int16 *v152; // rcx
  void *v154; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v155; // [rsp+28h] [rbp-D8h] BYREF
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v157; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v158; // [rsp+40h] [rbp-C0h] BYREF
  int v159; // [rsp+48h] [rbp-B8h]
  __int64 v160; // [rsp+50h] [rbp-B0h]
  __int64 v161; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v162; // [rsp+60h] [rbp-A0h]
  int v163; // [rsp+68h] [rbp-98h]
  int v164; // [rsp+6Ch] [rbp-94h]
  unsigned __int64 v165; // [rsp+70h] [rbp-90h]
  __int64 v166; // [rsp+78h] [rbp-88h]
  unsigned __int64 v167; // [rsp+80h] [rbp-80h]
  __int64 v168; // [rsp+88h] [rbp-78h]
  __int64 v169; // [rsp+90h] [rbp-70h]
  __int64 v170; // [rsp+98h] [rbp-68h] BYREF
  __int128 v171; // [rsp+A0h] [rbp-60h]
  _BYTE v172[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v173[232]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v174[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v175[232]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v176[8]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v177[232]; // [rsp+298h] [rbp+198h] BYREF
  _BYTE v178[8]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v179[232]; // [rsp+388h] [rbp+288h] BYREF
  _BYTE v180[8]; // [rsp+470h] [rbp+370h] BYREF
  _BYTE v181[232]; // [rsp+478h] [rbp+378h] BYREF
  _BYTE v182[240]; // [rsp+560h] [rbp+460h] BYREF
  _BYTE v183[8]; // [rsp+650h] [rbp+550h] BYREF
  _BYTE v184[232]; // [rsp+658h] [rbp+558h] BYREF
  _BYTE v185[240]; // [rsp+740h] [rbp+640h] BYREF
  _BYTE v186[32]; // [rsp+830h] [rbp+730h] BYREF
  wchar_t *Format[3]; // [rsp+850h] [rbp+750h] BYREF
  unsigned __int64 v188; // [rsp+868h] [rbp+768h]
  _BYTE v189[16]; // [rsp+870h] [rbp+770h] BYREF
  __int128 v190; // [rsp+880h] [rbp+780h]
  _BYTE v191[32]; // [rsp+8A8h] [rbp+7A8h] BYREF
  _QWORD v192[4]; // [rsp+8C8h] [rbp+7C8h] BYREF
  _BYTE v193[40]; // [rsp+8E8h] [rbp+7E8h] BYREF
  void **v194; // [rsp+910h] [rbp+810h] BYREF
  __int16 v195; // [rsp+918h] [rbp+818h]
  __int128 v196; // [rsp+980h] [rbp+880h]
  __int128 v197; // [rsp+990h] [rbp+890h]
  __int128 v198; // [rsp+9A0h] [rbp+8A0h]
  __int64 v199; // [rsp+9B0h] [rbp+8B0h]

  v169 = a5;
  v170 = 1;
  v171 = 0;
  v154 = 0;
  Block = 0;
  v157 = 0;
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v178);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v180);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v172);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v176);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v183);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v174);
  std::wstring::wstring((__int64)v192);
  v155 = 0;
  CurrentRef = CmdOptions::GetCurrentRef(v12, v11);
  JoinInfo = DsrGetJoinInfoEx((unsigned int)(*(_BYTE *)(*(_QWORD *)CurrentRef + 7LL) != 0) + 2, &v170, &v154);
  if ( JoinInfo < 0 )
  {
    std::wstring::wstring((__int64)Format, (__int64)L"AzureAdJoined");
    ErrorMsgRow = (_QWORD *)DsrCmdStatusHelper::CreateErrorMsgRow(v186, Format, (unsigned int)JoinInfo);
    std::operator<<<unsigned short>((__int64)v178, ErrorMsgRow);
    std::wstring::_Tidy_deallocate((__int64)v186);
    std::wstring::_Tidy_deallocate((__int64)Format);
    std::wstring::wstring((__int64)Format, (__int64)L"IsAadJoined");
    DsrCmdStatusHelper::PrintError(v176, Format, (unsigned int)JoinInfo);
LABEL_12:
    std::wstring::_Tidy_deallocate((__int64)Format);
    goto LABEL_13;
  }
  if ( !v154 || !*((_DWORD *)v154 + 4) || (v16 = *((_QWORD *)v154 + 1)) == 0 )
  {
    std::wstring::wstring((__int64)Format, (__int64)L"AzureAdJoined");
    MsgRow = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, L"NO");
    std::operator<<<unsigned short>((__int64)v178, MsgRow);
    std::wstring::_Tidy_deallocate((__int64)v186);
    std::wstring::_Tidy_deallocate((__int64)Format);
    std::wstring::wstring((__int64)Format, (__int64)L"EnterpriseJoined");
    v24 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, L"NO");
    std::operator<<<unsigned short>((__int64)v178, v24);
    std::wstring::_Tidy_deallocate((__int64)v186);
    goto LABEL_12;
  }
  if ( *(_DWORD *)(v16 + 60) )
  {
    if ( *(_DWORD *)(v16 + 60) == 1 )
    {
      std::wstring::wstring((__int64)Format, (__int64)L"AzureAdJoined");
      v19 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, L"NO");
      std::operator<<<unsigned short>((__int64)v178, v19);
      std::wstring::_Tidy_deallocate((__int64)v186);
      std::wstring::_Tidy_deallocate((__int64)Format);
      std::wstring::wstring((__int64)Format, (__int64)L"EnterpriseJoined");
      v20 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, L"YES");
      std::operator<<<unsigned short>((__int64)v178, v20);
      std::wstring::_Tidy_deallocate((__int64)v186);
      std::wstring::_Tidy_deallocate((__int64)Format);
      *a7 = 1;
    }
    else
    {
      std::wstring::wstring((__int64)Format, (__int64)L"AzureAdJoined");
      v21 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, L"ERROR [UNKNOWN_ERROR]");
      std::operator<<<unsigned short>((__int64)v178, v21);
      std::wstring::_Tidy_deallocate((__int64)v186);
      std::wstring::_Tidy_deallocate((__int64)Format);
      std::wstring::wstring((__int64)Format, (__int64)L"EnterpriseJoined");
      v22 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, L"ERROR [UNKNOWN_ERROR]");
      std::operator<<<unsigned short>((__int64)v178, v22);
      std::wstring::_Tidy_deallocate((__int64)v186);
      std::wstring::_Tidy_deallocate((__int64)Format);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(
        (__int64)v176,
        (__int64)L"ERROR DsrGetJoinInfoEx returned unexpected data.");
    }
  }
  else
  {
    std::wstring::wstring((__int64)Format, (__int64)L"AzureAdJoined");
    v17 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, L"YES");
    std::operator<<<unsigned short>((__int64)v178, v17);
    std::wstring::_Tidy_deallocate((__int64)v186);
    std::wstring::_Tidy_deallocate((__int64)Format);
    std::wstring::wstring((__int64)Format, (__int64)L"EnterpriseJoined");
    v18 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, L"NO");
    std::operator<<<unsigned short>((__int64)v178, v18);
    std::wstring::_Tidy_deallocate((__int64)v186);
    std::wstring::_Tidy_deallocate((__int64)Format);
    *a6 = 1;
  }
LABEL_13:
  if ( !v154 )
    goto LABEL_84;
  if ( !*((_DWORD *)v154 + 4) )
    goto LABEL_84;
  v25 = *((_QWORD *)v154 + 1);
  if ( !v25 )
    goto LABEL_84;
  v26 = *(_QWORD *)(v25 + 16);
  std::wstring::wstring((__int64)Format, (__int64)L"DeviceId");
  v27 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, v26);
  std::operator<<<unsigned short>((__int64)v180, v27);
  std::wstring::_Tidy_deallocate((__int64)v186);
  std::wstring::_Tidy_deallocate((__int64)Format);
  CertificateThumbprint = GetCertificateThumbprint(*(_QWORD *)(*((_QWORD *)v154 + 1) + 8LL), v192);
  if ( CertificateThumbprint < 0 )
  {
    std::wstring::wstring((__int64)Format, (__int64)L"GetCertificateThumbprint");
    DsrCmdStatusHelper::PrintError(v176, Format, (unsigned int)CertificateThumbprint);
  }
  else
  {
    std::wstring::wstring((__int64)Format, (__int64)L"Thumbprint");
    v29 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, v192);
    std::operator<<<unsigned short>((__int64)v180, v29);
    std::wstring::_Tidy_deallocate((__int64)v186);
  }
  std::wstring::_Tidy_deallocate((__int64)Format);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v185);
  v30 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v185, (__int64)L"[ ");
  v31 = (_QWORD *)TimeUtils::FileTimeToString(
                    Format,
                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v154 + 1) + 8LL) + 24LL) + 64LL));
  v32 = std::operator<<<unsigned short>(v30, v31);
  v33 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v32, (__int64)L" -- ");
  v34 = (_QWORD *)TimeUtils::FileTimeToString(
                    v186,
                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v154 + 1) + 8LL) + 24LL) + 72LL));
  v35 = std::operator<<<unsigned short>(v33, v34);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v35, (__int64)L" ]");
  std::wstring::_Tidy_deallocate((__int64)v186);
  std::wstring::_Tidy_deallocate((__int64)Format);
  std::wstring::wstring((__int64)Format, (__int64)L"DeviceCertificateValidity");
  v36 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, v185);
  std::operator<<<unsigned short>((__int64)v180, v36);
  std::wstring::_Tidy_deallocate((__int64)v186);
  std::wstring::_Tidy_deallocate((__int64)Format);
  DsrCmdStatusHelper::GetJoinCertInfo(*((_QWORD *)v154 + 1), v180, v176);
  if ( *a6 )
  {
    v37 = AadPluginController::DoDeviceValidityCheck((int *)&v155);
    if ( v37 < 0 )
    {
      std::wstring::wstring((__int64)Format, (__int64)L"DeviceAuthStatus");
      DsrCmdStatusHelper::PrintError(v176, Format, (unsigned int)v37);
      std::wstring::_Tidy_deallocate((__int64)Format);
      goto LABEL_29;
    }
    std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v182);
    v38 = v155;
    if ( v155 )
    {
      if ( v155 != -1073741715 )
      {
        v40 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64)v182,
                (__int64)L"FAILED. Error: ");
        ErrorCode = (_QWORD *)DsrCmdStatusHelper::GetErrorCode(v186, v38 | 0x10000000);
        std::operator<<<unsigned short>(v40, ErrorCode);
        std::wstring::_Tidy_deallocate((__int64)v186);
        goto LABEL_27;
      }
      v39 = L"FAILED. Device is either disabled or deleted";
    }
    else
    {
      v39 = L"SUCCESS";
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v182, (__int64)v39);
LABEL_27:
    std::wstring::wstring((__int64)Format, (__int64)L"DeviceAuthStatus");
    v42 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, v182);
    std::operator<<<unsigned short>((__int64)v180, v42);
    std::wstring::_Tidy_deallocate((__int64)v186);
    std::wstring::_Tidy_deallocate((__int64)Format);
    std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v182);
LABEL_29:
    v196 = 0;
    v197 = 0;
    v198 = 0;
    v195 = 0;
    v194 = &MdmDeviceInfo::`vftable';
    v199 = 0;
    for ( i = 1; (int)i <= 3; ++i )
    {
      v155 = 0;
      IsAttributeUpdateNeeded = DeviceInfo::IsAttributeUpdateNeeded(&v194, i, *((_QWORD *)v154 + 1), &v155);
      if ( IsAttributeUpdateNeeded < 0 )
      {
        AttributeUpdateStateKey = GetAttributeUpdateStateKey(i);
        std::wstring::wstring((__int64)Format, AttributeUpdateStateKey);
        v49 = (_QWORD *)DsrCmdStatusHelper::CreateErrorMsgRow(v186, Format, (unsigned int)IsAttributeUpdateNeeded);
        std::operator<<<unsigned short>((__int64)v174, v49);
        std::wstring::_Tidy_deallocate((__int64)v186);
        std::wstring::_Tidy_deallocate((__int64)Format);
        std::wstring::wstring((__int64)Format, AttributeUpdateStateKey);
        DsrCmdStatusHelper::PrintError(v176, Format, (unsigned int)IsAttributeUpdateNeeded);
        std::wstring::_Tidy_deallocate((__int64)Format);
      }
      else
      {
        if ( v155 )
        {
          switch ( v155 )
          {
            case 1u:
              v45 = L"NO";
              break;
            case 2u:
              v45 = L"Managed by MDM";
              break;
            case 3u:
              v45 = L"Disabled";
              break;
            default:
              v45 = L"UNKNOWN";
              break;
          }
        }
        else
        {
          v45 = L"YES";
        }
        v46 = GetAttributeUpdateStateKey(i);
        std::wstring::wstring((__int64)Format, v46);
        v47 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, v45);
        std::operator<<<unsigned short>((__int64)v174, v47);
        std::wstring::_Tidy_deallocate((__int64)v186);
        std::wstring::_Tidy_deallocate((__int64)Format);
      }
    }
    std::basic_stringbuf<unsigned short>::str(v175, Format);
    v50 = Format[2] != 0;
    std::wstring::_Tidy_deallocate((__int64)Format);
    if ( v50 )
      std::basic_ostream<unsigned short>::operator<<(v174, 10);
    v158 = 0;
    v159 = 0;
    v160 = 0;
    v190 = 0;
    v161 = 0;
    v162 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v163 = 0;
    v164 = 0;
    v165 = v162;
    v166 = 0;
    v167 = v162;
    v168 = 0;
    HostNameStatus = DeviceInfo::GetHostNameStatus(
                       *((struct _DSREG_ACCOUNT_INFO_2 **)v154 + 1),
                       (struct _HOSTNAME_STATUS *)&v158);
    if ( HostNameStatus >= 0 )
    {
      v54 = v160;
      if ( v160 > 0 )
      {
        v56 = v159;
        std::wstring::wstring((__int64)Format, (__int64)L"Last HostName Update");
        if ( v56 < 0 )
        {
          v59 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, L"FAIL");
          std::operator<<<unsigned short>((__int64)v174, v59);
          std::wstring::_Tidy_deallocate((__int64)v186);
          std::wstring::_Tidy_deallocate((__int64)Format);
          v60 = DsrCmdStatusHelper::GetErrorCode(v191, (unsigned int)v56);
          std::wstring::wstring((__int64)Format, (__int64)L"Client ErrorCode");
          v61 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, v60);
          std::operator<<<unsigned short>((__int64)v174, v61);
          std::wstring::_Tidy_deallocate((__int64)v186);
          std::wstring::_Tidy_deallocate((__int64)Format);
          v58 = (wchar_t **)v191;
        }
        else
        {
          v57 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, L"SUCCESS");
          std::operator<<<unsigned short>((__int64)v174, v57);
          std::wstring::_Tidy_deallocate((__int64)v186);
          v58 = Format;
        }
        std::wstring::_Tidy_deallocate((__int64)v58);
        std::wstring::wstring((__int64)Format, (__int64)L"Client Time");
        TimeMsgRow = (_QWORD *)DsrCmdStatusHelper::CreateTimeMsgRow(v191, Format, v54);
        std::operator<<<unsigned short>((__int64)v174, TimeMsgRow);
        std::wstring::_Tidy_deallocate((__int64)v191);
        std::wstring::_Tidy_deallocate((__int64)Format);
        std::wstring::wstring((__int64)Format, (__int64)L"Request ID");
        MsgRowIfNotEmpty = (_QWORD *)DsrCmdStatusHelper::CreateMsgRowIfNotEmpty(v191, Format, v161);
        std::operator<<<unsigned short>((__int64)v174, MsgRowIfNotEmpty);
        std::wstring::_Tidy_deallocate((__int64)v191);
        std::wstring::_Tidy_deallocate((__int64)Format);
        std::wstring::wstring((__int64)Format, (__int64)L"Server Time");
        v64 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRowIfNotEmpty(v191, Format, v162);
        std::operator<<<unsigned short>((__int64)v174, v64);
        std::wstring::_Tidy_deallocate((__int64)v191);
        std::wstring::_Tidy_deallocate((__int64)Format);
        std::wstring::wstring((__int64)v186, (__int64)L"HTTP Status");
        if ( v163 )
          DsrCmdStatusHelper::CreateMsgRow(Format, v186);
        else
          std::wstring::wstring((__int64)Format, (__int64)&cchOriginalDestLength);
        std::operator<<<unsigned short>((__int64)v174, Format);
        std::wstring::_Tidy_deallocate((__int64)Format);
        std::wstring::_Tidy_deallocate((__int64)v186);
        std::wstring::wstring((__int64)v186, (__int64)L"Server ErrorCode");
        v65 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRowIfNotEmpty(v191, v186, v165);
        std::operator<<<unsigned short>((__int64)v174, v65);
        std::wstring::_Tidy_deallocate((__int64)v191);
        std::wstring::_Tidy_deallocate((__int64)v186);
        std::wstring::wstring((__int64)v186, (__int64)L"Server ErrorSubcode");
        v66 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRowIfNotEmpty(v191, v186, v166);
        std::operator<<<unsigned short>((__int64)v174, v66);
        std::wstring::_Tidy_deallocate((__int64)v191);
        std::wstring::_Tidy_deallocate((__int64)v186);
        std::wstring::wstring((__int64)v186, (__int64)L"Server Operation");
        v67 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRowIfNotEmpty(v191, v186, v168);
        std::operator<<<unsigned short>((__int64)v174, v67);
        std::wstring::_Tidy_deallocate((__int64)v191);
        std::wstring::_Tidy_deallocate((__int64)v186);
        std::wstring::wstring((__int64)v186, (__int64)L"Server Message");
        v68 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRowIfNotEmpty(v191, v186, v167);
        std::operator<<<unsigned short>((__int64)v174, v68);
        std::wstring::_Tidy_deallocate((__int64)v191);
        v53 = (wchar_t **)v186;
        goto LABEL_57;
      }
      std::wstring::wstring((__int64)Format, (__int64)L"Last HostName Update");
      v55 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v186, Format, L"NONE");
      std::operator<<<unsigned short>((__int64)v174, v55);
      std::wstring::_Tidy_deallocate((__int64)v186);
    }
    else
    {
      std::wstring::wstring((__int64)Format, (__int64)L"Last HostName Update");
      v52 = (_QWORD *)DsrCmdStatusHelper::CreateErrorMsgRow(v186, Format, (unsigned int)HostNameStatus);
      std::operator<<<unsigned short>((__int64)v174, v52);
      std::wstring::_Tidy_deallocate((__int64)v186);
      std::wstring::_Tidy_deallocate((__int64)Format);
      std::wstring::wstring((__int64)Format, (__int64)L"GetHostNameStatus");
      DsrCmdStatusHelper::PrintError(v176, Format, (unsigned int)HostNameStatus);
    }
    v53 = Format;
LABEL_57:
    std::wstring::_Tidy_deallocate((__int64)v53);
    _HOSTNAME_STATUS::~_HOSTNAME_STATUS((_HOSTNAME_STATUS *)&v158);
    v194 = &DeviceInfo::`vftable';
    DeviceInfo::Cleanup((DeviceInfo *)&v194);
  }
  v155 = 0;
  v69 = DsrCmdRecovery::TryPrivateKeyAquireTestCloudAP(&v155);
  if ( v69 < 0 )
  {
    std::wstring::wstring((__int64)Format, (__int64)L"unknown");
    v72 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64)v176,
            (__int64)L"ERROR PrivateKeySignTest ");
    v73 = (_QWORD *)DsrCmdStatusHelper::GetErrorCode(v191, (unsigned int)v69);
    v74 = std::operator<<<unsigned short>(v72, v73);
    v75 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v74, (__int64)L" (failed key type: ");
    LODWORD(v72) = v155;
    v76 = std::basic_ostream<unsigned short>::operator<<(v75, v155);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v76, (__int64)L")\n");
    std::wstring::_Tidy_deallocate((__int64)v191);
    v77 = v72 - 1;
    if ( v77 )
    {
      v78 = v77 - 1;
      if ( v78 )
      {
        if ( v78 != 1 )
        {
LABEL_67:
          v81 = std::operator+<unsigned short>(v189, L"FAILED (", Format);
          v82 = std::operator+<unsigned short>(v193, v81, L" key)");
          std::wstring::wstring((__int64)v186, (__int64)L"KeySignTest");
          v83 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v191, v186, v82);
          std::operator<<<unsigned short>((__int64)v183, v83);
          std::wstring::_Tidy_deallocate((__int64)v191);
          std::wstring::_Tidy_deallocate((__int64)v186);
          std::wstring::_Tidy_deallocate((__int64)v193);
          std::wstring::_Tidy_deallocate((__int64)v189);
          v71 = Format;
          goto LABEL_68;
        }
        v79 = 16;
        v80 = L"resource account";
      }
      else
      {
        v79 = 9;
        v80 = L"transport";
      }
    }
    else
    {
      v79 = 6;
      v80 = L"device";
    }
    std::wstring::_Assign<unsigned short>((char **)Format, v80, (char *)v79);
    goto LABEL_67;
  }
  std::wstring::wstring((__int64)v186, (__int64)L"KeySignTest");
  v70 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v191, v186, L"PASSED");
  std::operator<<<unsigned short>((__int64)v183, v70);
  std::wstring::_Tidy_deallocate((__int64)v191);
  v71 = (wchar_t **)v186;
LABEL_68:
  std::wstring::_Tidy_deallocate((__int64)v71);
  v84 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 64LL);
  std::wstring::wstring((__int64)v186, (__int64)L"TenantName");
  v85 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v84);
  std::operator<<<unsigned short>((__int64)v172, v85);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v86 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 32LL);
  std::wstring::wstring((__int64)v186, (__int64)L"TenantId");
  v87 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v86);
  std::operator<<<unsigned short>((__int64)v172, v87);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v88 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 128LL);
  std::wstring::wstring((__int64)v186, (__int64)L"AuthCodeUrl");
  v89 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v88);
  std::operator<<<unsigned short>((__int64)v172, v89);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v90 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 136LL);
  std::wstring::wstring((__int64)v186, (__int64)L"AccessTokenUrl");
  v91 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v90);
  std::operator<<<unsigned short>((__int64)v172, v91);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v92 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 72LL);
  std::wstring::wstring((__int64)v186, (__int64)L"MdmUrl");
  v93 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v92);
  std::operator<<<unsigned short>((__int64)v172, v93);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v94 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 80LL);
  std::wstring::wstring((__int64)v186, (__int64)L"MdmTouUrl");
  v95 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v94);
  std::operator<<<unsigned short>((__int64)v172, v95);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v96 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 88LL);
  std::wstring::wstring((__int64)v186, (__int64)L"MdmComplianceUrl");
  v97 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v96);
  std::operator<<<unsigned short>((__int64)v172, v97);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v98 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 96LL);
  std::wstring::wstring((__int64)v186, (__int64)L"SettingsUrl");
  v99 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v98);
  std::operator<<<unsigned short>((__int64)v172, v99);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v100 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 144LL);
  std::wstring::wstring((__int64)v186, (__int64)L"JoinSrvVersion");
  v101 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v100);
  std::operator<<<unsigned short>((__int64)v172, v101);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v102 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 152LL);
  std::wstring::wstring((__int64)v186, (__int64)L"JoinSrvUrl");
  v103 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v102);
  std::operator<<<unsigned short>((__int64)v172, v103);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v104 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 160LL);
  std::wstring::wstring((__int64)v186, (__int64)L"JoinSrvId");
  v105 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v104);
  std::operator<<<unsigned short>((__int64)v172, v105);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v106 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 168LL);
  std::wstring::wstring((__int64)v186, (__int64)L"KeySrvVersion");
  v107 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v106);
  std::operator<<<unsigned short>((__int64)v172, v107);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v108 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 176LL);
  std::wstring::wstring((__int64)v186, (__int64)L"KeySrvUrl");
  v109 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v108);
  std::operator<<<unsigned short>((__int64)v172, v109);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v110 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 184LL);
  std::wstring::wstring((__int64)v186, (__int64)L"KeySrvId");
  v111 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v110);
  std::operator<<<unsigned short>((__int64)v172, v111);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v112 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 192LL);
  std::wstring::wstring((__int64)v186, (__int64)L"WebAuthNSrvVersion");
  v113 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v112);
  std::operator<<<unsigned short>((__int64)v172, v113);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v114 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 200LL);
  std::wstring::wstring((__int64)v186, (__int64)L"WebAuthNSrvUrl");
  v115 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v114);
  std::operator<<<unsigned short>((__int64)v172, v115);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v116 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 208LL);
  std::wstring::wstring((__int64)v186, (__int64)L"WebAuthNSrvId");
  v117 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v116);
  std::operator<<<unsigned short>((__int64)v172, v117);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v118 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 216LL);
  std::wstring::wstring((__int64)v186, (__int64)L"DeviceManagementSrvVer");
  v119 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v118);
  std::operator<<<unsigned short>((__int64)v172, v119);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v120 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 224LL);
  std::wstring::wstring((__int64)v186, (__int64)L"DeviceManagementSrvUrl");
  v121 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v120);
  std::operator<<<unsigned short>((__int64)v172, v121);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  v122 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 232LL);
  std::wstring::wstring((__int64)v186, (__int64)L"DeviceManagementSrvId");
  v123 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v122);
  std::operator<<<unsigned short>((__int64)v172, v123);
  std::wstring::_Tidy_deallocate((__int64)v189);
  std::wstring::_Tidy_deallocate((__int64)v186);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADCloudKerbHaadj>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AADCloudKerbHaadj>::GetImpl'::`2'::impl) )
  {
    v124 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 296LL);
    std::wstring::wstring((__int64)v186, (__int64)L"KerbSpn");
    v125 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v124);
    std::operator<<<unsigned short>((__int64)v172, v125);
    std::wstring::_Tidy_deallocate((__int64)v189);
    std::wstring::_Tidy_deallocate((__int64)v186);
    v126 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 304LL);
    std::wstring::wstring((__int64)v186, (__int64)L"KerbUrl");
    v127 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v126);
    std::operator<<<unsigned short>((__int64)v172, v127);
    std::wstring::_Tidy_deallocate((__int64)v189);
    std::wstring::_Tidy_deallocate((__int64)v186);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::GetImpl'::`2'::impl) )
  {
    v128 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 312LL);
    std::wstring::wstring((__int64)v186, (__int64)L"JoinSrvTlsUrl");
    v129 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v128);
    std::operator<<<unsigned short>((__int64)v172, v129);
    std::wstring::_Tidy_deallocate((__int64)v189);
    std::wstring::_Tidy_deallocate((__int64)v186);
    v130 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 320LL);
    std::wstring::wstring((__int64)v186, (__int64)L"DeviceManagementSrvTlsUrl");
    v131 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v130);
    std::operator<<<unsigned short>((__int64)v172, v131);
    std::wstring::_Tidy_deallocate((__int64)v189);
    std::wstring::_Tidy_deallocate((__int64)v186);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RAforMTRW>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RAforMTRW>::GetImpl'::`2'::impl) )
  {
    v132 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 328LL);
    std::wstring::wstring((__int64)v186, (__int64)L"JoinResourceSrvTlsUrl");
    v133 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v132);
    std::operator<<<unsigned short>((__int64)v172, v133);
    std::wstring::_Tidy_deallocate((__int64)v189);
    std::wstring::_Tidy_deallocate((__int64)v186);
  }
  v157 = *(_QWORD *)(*((_QWORD *)v154 + 1) + 32LL);
  v134 = DsrGetJoinInfoEx(0xFFFFFFFFLL, &v157, &Block);
  if ( v134 >= 0 )
  {
    if ( Block )
    {
      v136 = *((_QWORD *)Block + 2);
      std::wstring::wstring((__int64)v186, (__int64)L"RecoveryDeviceId");
      v137 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v136);
      std::operator<<<unsigned short>((__int64)v180, v137);
      std::wstring::_Tidy_deallocate((__int64)v189);
      std::wstring::_Tidy_deallocate((__int64)v186);
      v192[2] = 0;
      v138 = v192;
      if ( v192[3] > 7u )
        v138 = (_WORD *)v192[0];
      *v138 = 0;
      v139 = GetCertificateThumbprint(*((_QWORD *)Block + 1), v192);
      if ( v139 < 0 )
      {
        std::wstring::wstring((__int64)v186, (__int64)L"GetDeviceRecoveryCertificateThumbprint");
        DsrCmdStatusHelper::PrintError(v176, v186, (unsigned int)v139);
      }
      else
      {
        std::wstring::wstring((__int64)v186, (__int64)L"RecoveryThumbprint");
        v140 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v189, v186, v192);
        std::operator<<<unsigned short>((__int64)v180, v140);
        std::wstring::_Tidy_deallocate((__int64)v189);
      }
      std::wstring::_Tidy_deallocate((__int64)v186);
      DsrFreeJoinInfoEx(Block);
    }
  }
  else
  {
    std::wstring::wstring((__int64)v186, (__int64)L"RecoveryDeviceId");
    v135 = (_QWORD *)DsrCmdStatusHelper::CreateErrorMsgRow(v189, v186, (unsigned int)v134);
    std::operator<<<unsigned short>((__int64)v180, v135);
    std::wstring::_Tidy_deallocate((__int64)v189);
    std::wstring::_Tidy_deallocate((__int64)v186);
    std::wstring::wstring((__int64)v186, (__int64)L"GetDeviceRecoveryInfo");
    DsrCmdStatusHelper::PrintError(v176, v186, (unsigned int)v134);
    std::wstring::_Tidy_deallocate((__int64)v186);
  }
  std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v185);
LABEL_84:
  std::basic_stringbuf<unsigned short>::str(v179, v186);
  std::wstring::operator=(a1, (__int64)v186);
  std::wstring::_Tidy_deallocate((__int64)v186);
  std::basic_stringbuf<unsigned short>::str(v181, v186);
  std::wstring::operator=(a2, (__int64)v186);
  std::wstring::_Tidy_deallocate((__int64)v186);
  std::basic_stringbuf<unsigned short>::str(v173, v186);
  std::wstring::operator=(a3, (__int64)v186);
  std::wstring::_Tidy_deallocate((__int64)v186);
  std::basic_stringbuf<unsigned short>::str(v184, v186);
  std::wstring::operator=(a4, (__int64)v186);
  std::wstring::_Tidy_deallocate((__int64)v186);
  std::basic_stringbuf<unsigned short>::str(v175, v186);
  std::wstring::operator=(v169, (__int64)v186);
  std::wstring::_Tidy_deallocate((__int64)v186);
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v142, v141) )
  {
    std::basic_stringbuf<unsigned short>::str(v177, Format);
    v143 = (const wchar_t *)Format;
    if ( v188 > 7 )
      v143 = Format[0];
    wprintf(v143);
    std::wstring::_Tidy_deallocate((__int64)Format);
    v146 = (_QWORD *)CmdOptions::GetCurrentRef(v145, v144);
    if ( *(_BYTE *)(*v146 + 12LL) && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v146, v147) + 184LL) )
    {
      std::basic_stringbuf<unsigned short>::str(v177, Format);
      v150 = (const wchar_t *)Format;
      if ( v188 > 7 )
        v150 = Format[0];
      v151 = CmdOptions::GetCurrentRef(v149, v148);
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v151 + 184LL), v150);
      std::wstring::_Tidy_deallocate((__int64)Format);
    }
  }
  std::basic_stringbuf<unsigned short>::str(v177, Format);
  v152 = (const unsigned __int16 *)Format;
  if ( v188 > 7 )
    v152 = Format[0];
  Logger::TraceInformation(v152);
  std::wstring::_Tidy_deallocate((__int64)Format);
  DsrFreeJoinInfoEx(v154);
  std::wstring::_Tidy_deallocate((__int64)v192);
  std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v174);
  std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v183);
  std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v176);
  std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v172);
  std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v180);
  return std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v178);
}

```

## disassembly

```asm
0x18002df9c  push    rbp
0x18002df9e  push    rbx
0x18002df9f  push    rsi
0x18002dfa0  push    rdi
0x18002dfa1  push    r12
0x18002dfa3  push    r13
0x18002dfa5  push    r14
0x18002dfa7  push    r15
0x18002dfa9  lea     rbp, [rsp-8D8h]
0x18002dfb1  sub     rsp, 9D8h
0x18002dfb8  mov     rax, cs:__security_cookie
0x18002dfbf  xor     rax, rsp
0x18002dfc2  mov     [rbp+910h+var_50], rax
0x18002dfc9  mov     r13, r9
0x18002dfcc  mov     r12, r8
0x18002dfcf  mov     r15, rdx
0x18002dfd2  mov     r14, rcx
0x18002dfd5  mov     rax, [rbp+910h+arg_20]
0x18002dfdc  mov     [rbp+910h+var_980], rax
0x18002dfe0  mov     rdi, [rbp+910h+arg_28]
0x18002dfe7  mov     rsi, [rbp+910h+arg_30]
0x18002dfee  xor     ebx, ebx
0x18002dff0  mov     [rbp+910h+var_978], 1
0x18002dff8  xorps   xmm0, xmm0
0x18002dffb  movdqu  [rbp+910h+var_970], xmm0
0x18002e000  mov     [rsp+0A10h+var_9F0], rbx
0x18002e005  mov     [rsp+0A10h+Block], rbx
0x18002e00a  mov     [rsp+0A10h+var_9D8], rbx
0x18002e00f  lea     rcx, [rbp+910h+var_690]
0x18002e016  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002e01b  nop
0x18002e01c  lea     rcx, [rbp+910h+var_5A0]
0x18002e023  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002e028  nop
0x18002e029  lea     rcx, [rbp+910h+var_960]
0x18002e02d  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002e032  nop
0x18002e033  lea     rcx, [rbp+910h+var_780]
0x18002e03a  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002e03f  nop
0x18002e040  lea     rcx, [rbp+910h+var_3C0]
0x18002e047  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002e04c  nop
0x18002e04d  lea     rcx, [rbp+910h+var_870]
0x18002e054  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002e059  nop
0x18002e05a  lea     rcx, [rbp+910h+var_148]
0x18002e061  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002e066  nop
0x18002e067  mov     [rsp+0A10h+var_9E8], ebx
0x18002e06b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002e070  mov     rcx, [rax]
0x18002e073  mov     al, [rcx+7]
0x18002e076  neg     al
0x18002e078  sbb     ecx, ecx
0x18002e07a  neg     ecx
0x18002e07c  add     ecx, 2
0x18002e07f  lea     r8, [rsp+0A10h+var_9F0]
0x18002e084  lea     rdx, [rbp+910h+var_978]
0x18002e088  call    DsrGetJoinInfoEx
0x18002e08d  mov     ebx, eax
0x18002e08f  test    eax, eax
0x18002e091  jns     loc_18002E11B
0x18002e097  lea     rdx, aAzureadjoined; "AzureAdJoined"
0x18002e09e  lea     rcx, [rbp+910h+Format]
0x18002e0a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e0aa  nop
0x18002e0ab  mov     r8d, ebx
0x18002e0ae  lea     rdx, [rbp+910h+Format]
0x18002e0b5  lea     rcx, [rbp+910h+var_1E0]
0x18002e0bc  call    ?CreateErrorMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@J@Z; DsrCmdStatusHelper::CreateErrorMsgRow(std::wstring const &,long)
0x18002e0c1  nop
0x18002e0c2  mov     rdx, rax
0x18002e0c5  lea     rcx, [rbp+910h+var_690]
0x18002e0cc  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18002e0d1  nop
0x18002e0d2  lea     rcx, [rbp+910h+var_1E0]
0x18002e0d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e0de  nop
0x18002e0df  lea     rcx, [rbp+910h+Format]
0x18002e0e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e0eb  lea     rdx, aIsaadjoined; "IsAadJoined"
0x18002e0f2  lea     rcx, [rbp+910h+Format]
0x18002e0f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e0fe  nop
0x18002e0ff  mov     r8d, ebx
0x18002e102  lea     rdx, [rbp+910h+Format]
0x18002e109  lea     rcx, [rbp+910h+var_780]
0x18002e110  call    ?PrintError@DsrCmdStatusHelper@@CAXAEAV?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@J@Z; DsrCmdStatusHelper::PrintError(std::basic_ostringstream<ushort> &,std::wstring const &,long)
0x18002e115  nop
0x18002e116  jmp     loc_18002E41B
0x18002e11b  mov     rax, [rsp+0A10h+var_9F0]
0x18002e120  test    rax, rax
0x18002e123  jz      loc_18002E377
0x18002e129  cmp     dword ptr [rax+10h], 0
0x18002e12d  jz      loc_18002E377
0x18002e133  mov     rcx, [rax+8]
0x18002e137  test    rcx, rcx
0x18002e13a  jz      loc_18002E377
0x18002e140  lea     rdx, aAzureadjoined; "AzureAdJoined"
0x18002e147  cmp     dword ptr [rcx+3Ch], 0
0x18002e14b  jnz     loc_18002E202
0x18002e151  lea     rcx, [rbp+910h+Format]
0x18002e158  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e15d  nop
0x18002e15e  lea     r8, aYes; "YES"
0x18002e165  lea     rdx, [rbp+910h+Format]
0x18002e16c  lea     rcx, [rbp+910h+var_1E0]
0x18002e173  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x18002e178  nop
0x18002e179  mov     rdx, rax
0x18002e17c  lea     rcx, [rbp+910h+var_690]
0x18002e183  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18002e188  nop
0x18002e189  lea     rcx, [rbp+910h+var_1E0]
0x18002e190  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e195  nop
0x18002e196  lea     rcx, [rbp+910h+Format]
0x18002e19d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e1a2  lea     rdx, aEnterprisejoin; "EnterpriseJoined"
0x18002e1a9  lea     rcx, [rbp+910h+Format]
0x18002e1b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e1b5  nop
0x18002e1b6  lea     r8, aNo_0; "NO"
0x18002e1bd  lea     rdx, [rbp+910h+Format]
0x18002e1c4  lea     rcx, [rbp+910h+var_1E0]
0x18002e1cb  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x18002e1d0  nop
0x18002e1d1  mov     rdx, rax
0x18002e1d4  lea     rcx, [rbp+910h+var_690]
0x18002e1db  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18002e1e0  nop
0x18002e1e1  lea     rcx, [rbp+910h+var_1E0]
0x18002e1e8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e1ed  nop
0x18002e1ee  lea     rcx, [rbp+910h+Format]
0x18002e1f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e1fa  mov     byte ptr [rdi], 1
0x18002e1fd  jmp     loc_18002E427
0x18002e202  cmp     dword ptr [rcx+3Ch], 1
0x18002e206  lea     rcx, [rbp+910h+Format]
0x18002e20d  jnz     loc_18002E2BD
0x18002e213  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e218  nop
0x18002e219  lea     r8, aNo_0; "NO"
0x18002e220  lea     rdx, [rbp+910h+Format]
0x18002e227  lea     rcx, [rbp+910h+var_1E0]
0x18002e22e  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x18002e233  nop
0x18002e234  mov     rdx, rax
0x18002e237  lea     rcx, [rbp+910h+var_690]
0x18002e23e  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18002e243  nop
0x18002e244  lea     rcx, [rbp+910h+var_1E0]
0x18002e24b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e250  nop
0x18002e251  lea     rcx, [rbp+910h+Format]
0x18002e258  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e25d  lea     rdx, aEnterprisejoin; "EnterpriseJoined"
0x18002e264  lea     rcx, [rbp+910h+Format]
0x18002e26b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e270  nop
0x18002e271  lea     r8, aYes; "YES"
0x18002e278  lea     rdx, [rbp+910h+Format]
0x18002e27f  lea     rcx, [rbp+910h+var_1E0]
0x18002e286  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x18002e28b  nop
0x18002e28c  mov     rdx, rax
0x18002e28f  lea     rcx, [rbp+910h+var_690]
0x18002e296  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18002e29b  nop
0x18002e29c  lea     rcx, [rbp+910h+var_1E0]
0x18002e2a3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e2a8  nop
0x18002e2a9  lea     rcx, [rbp+910h+Format]
0x18002e2b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e2b5  mov     byte ptr [rsi], 1
0x18002e2b8  jmp     loc_18002E427
0x18002e2bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e2c2  nop
0x18002e2c3  lea     r8, aErrorUnknownEr; "ERROR [UNKNOWN_ERROR]"
0x18002e2ca  lea     rdx, [rbp+910h+Format]
0x18002e2d1  lea     rcx, [rbp+910h+var_1E0]
0x18002e2d8  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x18002e2dd  nop
0x18002e2de  mov     rdx, rax
0x18002e2e1  lea     rcx, [rbp+910h+var_690]
0x18002e2e8  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18002e2ed  nop
0x18002e2ee  lea     rcx, [rbp+910h+var_1E0]
0x18002e2f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e2fa  nop
0x18002e2fb  lea     rcx, [rbp+910h+Format]
0x18002e302  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e307  lea     rdx, aEnterprisejoin; "EnterpriseJoined"
0x18002e30e  lea     rcx, [rbp+910h+Format]
0x18002e315  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e31a  nop
0x18002e31b  lea     r8, aErrorUnknownEr; "ERROR [UNKNOWN_ERROR]"
0x18002e322  lea     rdx, [rbp+910h+Format]
0x18002e329  lea     rcx, [rbp+910h+var_1E0]
0x18002e330  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x18002e335  nop
0x18002e336  mov     rdx, rax
0x18002e339  lea     rcx, [rbp+910h+var_690]
0x18002e340  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18002e345  nop
0x18002e346  lea     rcx, [rbp+910h+var_1E0]
0x18002e34d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e352  nop
0x18002e353  lea     rcx, [rbp+910h+Format]
0x18002e35a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e35f  lea     rdx, aErrorDsrgetjoi; "ERROR DsrGetJoinInfoEx returned unexpec"...
0x18002e366  lea     rcx, [rbp+910h+var_780]
0x18002e36d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002e372  jmp     loc_18002E427
0x18002e377  lea     rdx, aAzureadjoined; "AzureAdJoined"
0x18002e37e  lea     rcx, [rbp+910h+Format]
0x18002e385  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e38a  nop
0x18002e38b  lea     r8, aNo_0; "NO"
0x18002e392  lea     rdx, [rbp+910h+Format]
0x18002e399  lea     rcx, [rbp+910h+var_1E0]
0x18002e3a0  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x18002e3a5  nop
0x18002e3a6  mov     rdx, rax
0x18002e3a9  lea     rcx, [rbp+910h+var_690]
0x18002e3b0  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18002e3b5  nop
0x18002e3b6  lea     rcx, [rbp+910h+var_1E0]
0x18002e3bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e3c2  nop
0x18002e3c3  lea     rcx, [rbp+910h+Format]
0x18002e3ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e3cf  lea     rdx, aEnterprisejoin; "EnterpriseJoined"
0x18002e3d6  lea     rcx, [rbp+910h+Format]
0x18002e3dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e3e2  nop
0x18002e3e3  lea     r8, aNo_0; "NO"
0x18002e3ea  lea     rdx, [rbp+910h+Format]
0x18002e3f1  lea     rcx, [rbp+910h+var_1E0]
0x18002e3f8  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x18002e3fd  nop
0x18002e3fe  mov     rdx, rax
0x18002e401  lea     rcx, [rbp+910h+var_690]
0x18002e408  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18002e40d  nop
0x18002e40e  lea     rcx, [rbp+910h+var_1E0]
0x18002e415  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e41a  nop
0x18002e41b  lea     rcx, [rbp+910h+Format]
0x18002e422  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e427  mov     rax, [rsp+0A10h+var_9F0]
0x18002e42c  xor     esi, esi
0x18002e42e  test    rax, rax
0x18002e431  jz      loc_18002FC2E
0x18002e437  cmp     [rax+10h], esi
0x18002e43a  jz      loc_18002FC2E
0x18002e440  mov     rbx, [rax+8]
0x18002e444  test    rbx, rbx
0x18002e447  jz      loc_18002FC2E
0x18002e44d  mov     rbx, [rbx+10h]
0x18002e451  lea     rdx, aDeviceid; "DeviceId"
0x18002e458  lea     rcx, [rbp+910h+Format]
0x18002e45f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e464  nop
0x18002e465  mov     r8, rbx
0x18002e468  lea     rdx, [rbp+910h+Format]
0x18002e46f  lea     rcx, [rbp+910h+var_1E0]
0x18002e476  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x18002e47b  nop
0x18002e47c  mov     rdx, rax
0x18002e47f  lea     rcx, [rbp+910h+var_5A0]
0x18002e486  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18002e48b  nop
0x18002e48c  lea     rcx, [rbp+910h+var_1E0]
0x18002e493  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e498  nop
0x18002e499  lea     rcx, [rbp+910h+Format]
0x18002e4a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e4a5  mov     rax, [rsp+0A10h+var_9F0]
0x18002e4aa  mov     rcx, [rax+8]
0x18002e4ae  lea     rdx, [rbp+910h+var_148]
0x18002e4b5  mov     rcx, [rcx+8]
0x18002e4b9  call    ?GetCertificateThumbprint@@YAJPEBU_CERT_CONTEXT@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetCertificateThumbprint(_CERT_CONTEXT const *,std::wstring &)
0x18002e4be  mov     ebx, eax
0x18002e4c0  lea     rcx, [rbp+910h+Format]
0x18002e4c7  test    eax, eax
0x18002e4c9  js      short loc_18002E512
0x18002e4cb  lea     rdx, aThumbprint; "Thumbprint"
0x18002e4d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e4d7  nop
0x18002e4d8  lea     r8, [rbp+910h+var_148]
0x18002e4df  lea     rdx, [rbp+910h+Format]
0x18002e4e6  lea     rcx, [rbp+910h+var_1E0]
0x18002e4ed  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@0@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,std::wstring const &)
0x18002e4f2  nop
0x18002e4f3  mov     rdx, rax
0x18002e4f6  lea     rcx, [rbp+910h+var_5A0]
0x18002e4fd  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
  ... truncated ...
```
