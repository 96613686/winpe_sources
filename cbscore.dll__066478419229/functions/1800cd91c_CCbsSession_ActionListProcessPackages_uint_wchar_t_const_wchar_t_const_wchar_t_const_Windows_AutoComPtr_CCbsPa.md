# CCbsSession::ActionListProcessPackages(uint,wchar_t const *,wchar_t const *,wchar_t const *,Windows::AutoComPtr<CCbsPackage> *)

- ea: `0x1800cd91c`
- end: `0x1800cf0ba`
- name: `?ActionListProcessPackages@CCbsSession@@AEAAJIPEB_W00PEAV?$AutoComPtr@VCCbsPackage@@@Windows@@@Z`
- size: `6046`
- prototype: ``
- caller_count: `1`
- callee_count: `44`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801d9584`

## callees

- `0x18000b46c`
- `0x18000e780`
- `0x180010cc0`
- `0x180013250`
- `0x18001387c`
- `0x1800138b8`
- `0x180015420`
- `0x1800194bc`
- `0x180019bdc`
- `0x180019c10`
- `0x180023f30`
- `0x1800261e0`
- `0x180026864`
- `0x18002a448`
- `0x18002c34c`
- `0x18002e280`
- `0x180043adc`
- `0x180045c24`
- `0x18004f454`
- `0x180055fc8`
- `0x180056e00`
- `0x180057c28`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad1f0`
- `0x1800bd218`
- `0x1800cd91c`
- `0x1800d1efc`
- `0x1800eb920`
- `0x1800f1eb4`
- `0x1801026fc`
- `0x180113730`
- `0x1801aead0`
- `0x1801c322c`
- `0x1801c9830`
- `0x1801c98ec`
- `0x1801c99cc`
- `0x1801c9d88`
- `0x1801cc018`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdfcd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdfcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cea58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ceb3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cea58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ceb3c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ce7df`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ce7df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ce795`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ce795`

## string_xrefs

- `0x1800cea7a`: `Failed to write file: {}`
- `0x1800ceb61`: `Failed to open payload file: {}`
- `0x1800cdcfa`: `Attempted to install a FOD or LP with a postponed LCU install pending, a reboot must be performed first`
- `0x1800ce94a`: `Failed to create package: {}`
- `0x1800cedea`: `Failed to allocate memory for manifest blob`
- `0x1800ced08`: `Failed to get directory`
- `0x1800cec3f`: `Failed to create directory {}`
- `0x1800cf00a`: `No entry in the ActionList: {} matched the FilePath: {}`
- `0x1800cdd8b`: `Failed to process RemoveFeature Action`
- `0x1800cdea6`: `Failed to process InstallFeature Action`
- `0x1800cef37`: `Evaluation of package path: {} for missing files is not allowed except for Express packages`

## pseudocode

```c
__int64 __fastcall CCbsSession::ActionListProcessPackages(
        CCbsSession *this,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  CCbsSession *v6; // r14
  int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rsi
  __int64 v13; // rbx
  char v14; // r9
  char v15; // r10
  char v16; // r11
  __int64 i; // rax
  signed int v18; // edi
  int v19; // edx
  __int64 v20; // rdx
  int IsSmartPended; // eax
  int v22; // edx
  int v23; // edx
  __int64 v24; // rbx
  __int64 j; // rbx
  int v26; // edx
  __int64 k; // rbx
  int v28; // edx
  __int64 m; // rbx
  int v30; // edx
  __int64 n; // rdi
  int v32; // r10d
  int v33; // esi
  int v34; // eax
  int v35; // eax
  __int128 *v36; // rbx
  __int64 v37; // r14
  int WindowsUpdatePackage; // esi
  wchar_t *v39; // r14
  __int64 v40; // rdx
  int v41; // edx
  unsigned __int64 v42; // r15
  __int64 v43; // rsi
  __int64 v44; // rdx
  int v45; // edx
  __int64 v46; // rbx
  __int64 v47; // r14
  __int64 v48; // rax
  __int64 v49; // rdx
  unsigned __int64 v50; // r14
  __int64 *v51; // rbx
  unsigned __int64 v52; // rax
  unsigned __int64 v53; // rsi
  unsigned __int64 v54; // r12
  __int64 v55; // rcx
  bool v56; // zf
  wchar_t *v57; // rax
  unsigned int v58; // esi
  __int64 v59; // r15
  const wchar_t *v60; // rax
  __int64 v61; // r14
  __int64 ii; // rbx
  __int64 v63; // rsi
  int v64; // eax
  __int64 v65; // rdx
  wchar_t *v66; // rbx
  int v67; // r14d
  LPCVOID v68; // r15
  const WCHAR *v69; // rbx
  wchar_t *v70; // r14
  int Directory; // eax
  HANDLE FileW; // rax
  __int64 v73; // rdx
  int v74; // edx
  const wchar_t *v75; // rax
  int v76; // edx
  signed int LastError; // edi
  int v78; // edx
  unsigned int v79; // eax
  __int64 v80; // rdx
  int v81; // edx
  unsigned int v82; // eax
  int v83; // edx
  int v84; // edx
  __int64 v85; // rdx
  __int64 v86; // rdx
  __int64 v87; // r9
  int v88; // edx
  int v89; // edx
  int v90; // edx
  int v91; // edx
  __int64 v92; // r9
  int v94; // edx
  void *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  __int64 v96; // [rsp+70h] [rbp-90h] BYREF
  char v97[8]; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-80h] BYREF
  LPCVOID lpBuffer; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v100; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v101[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v102[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v103[4]; // [rsp+B0h] [rbp-50h] BYREF
  int *v104; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *v105; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v106; // [rsp+D0h] [rbp-30h]
  int *v107; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v108; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v109; // [rsp+F0h] [rbp-10h]
  wchar_t **v110; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v111; // [rsp+100h] [rbp+0h] BYREF
  wchar_t *v112; // [rsp+108h] [rbp+8h] BYREF
  __int64 v113; // [rsp+110h] [rbp+10h] BYREF
  __int64 v114; // [rsp+118h] [rbp+18h] BYREF
  __int128 v115; // [rsp+120h] [rbp+20h] BYREF
  __int64 v116; // [rsp+130h] [rbp+30h]
  __int128 v117; // [rsp+138h] [rbp+38h]
  __int64 v118; // [rsp+148h] [rbp+48h]
  __int64 v119; // [rsp+150h] [rbp+50h]
  __int128 v120; // [rsp+158h] [rbp+58h]
  __int64 v121; // [rsp+168h] [rbp+68h]
  __int128 v122; // [rsp+170h] [rbp+70h]
  __int64 v123; // [rsp+180h] [rbp+80h]
  __int128 v124; // [rsp+188h] [rbp+88h]
  __int64 v125; // [rsp+198h] [rbp+98h]
  __int64 v126; // [rsp+1A0h] [rbp+A0h]
  __int64 v127; // [rsp+1A8h] [rbp+A8h]
  int v128; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t *v129; // [rsp+1B8h] [rbp+B8h] BYREF
  HANDLE hFile; // [rsp+1C0h] [rbp+C0h] BYREF
  int v131; // [rsp+1C8h] [rbp+C8h] BYREF
  int v132; // [rsp+1CCh] [rbp+CCh] BYREF
  int v133; // [rsp+1D0h] [rbp+D0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+1D4h] [rbp+D4h] BYREF
  DWORD nNumberOfBytesToWrite[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  _QWORD v136[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v137[24]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v138; // [rsp+218h] [rbp+118h]
  __int64 v139; // [rsp+228h] [rbp+128h]
  __int128 v140; // [rsp+240h] [rbp+140h] BYREF
  __int128 v141; // [rsp+250h] [rbp+150h] BYREF
  __int128 v142; // [rsp+260h] [rbp+160h] BYREF
  __int64 v143; // [rsp+270h] [rbp+170h]
  _BYTE v144[24]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int64 v145; // [rsp+298h] [rbp+198h]
  __int64 *v146; // [rsp+2A8h] [rbp+1A8h]
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  *(_QWORD *)v102 = a6;
  v6 = this;
  v113 = a5;
  v106 = a4;
  v109 = 0;
  v128 = a2;
  v104 = (int *)this;
  v114 = a3;
  v136[0] = &Windows::Rtl::PrivateHeapPool::`vftable';
  v108 = 0;
  v111 = 0;
  v136[1] = 0;
  v136[2] = 0;
  v132 = 0;
  v7 = ActionListParser::ReadActionList(a3, v136, &v111, &v108);
  v9 = v7;
  if ( v7 < 0 )
  {
    LODWORD(hFile) = v7;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to load actions from {}",
        (__int64)&v114);
      *(_QWORD *)v103 = &hFile;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        1,
        3,
        (unsigned int)": {}",
        (__int64)v103);
    }
    v10 = 2678;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
      (const char *)v9,
      (int)dwCreationDisposition);
    goto LABEL_241;
  }
  v11 = v111;
  v12 = *(_QWORD *)(v111 + 152);
  if ( !*(_QWORD *)(v12 + 64) )
  {
    v9 = -2146498222;
    v131 = -2146498222;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "ActionList: No package to process in actionList, this is not expected.");
      *(_QWORD *)v103 = &v131;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        1,
        3,
        (unsigned int)": {}",
        (__int64)v103);
    }
    v10 = 2683;
    goto LABEL_9;
  }
  v13 = *(_QWORD *)(v12 + 56);
  v14 = 0;
  v15 = 0;
  v16 = 0;
  for ( i = v13; i; i = *(_QWORD *)(i + 296) )
  {
    v8 = (unsigned int)(*(_DWORD *)(i + 140) - 2);
    if ( *(_DWORD *)(i + 140) == 2
      || (v8 = (unsigned int)(*(_DWORD *)(i + 140) - 3), *(_DWORD *)(i + 140) == 3)
      || (v8 = (unsigned int)(*(_DWORD *)(i + 140) - 4), *(_DWORD *)(i + 140) == 4) )
    {
LABEL_23:
      v14 = 1;
      continue;
    }
    v8 = (unsigned int)(*(_DWORD *)(i + 140) - 5);
    if ( *(_DWORD *)(i + 140) != 5 )
    {
      v8 = (unsigned int)(*(_DWORD *)(i + 140) - 6);
      if ( *(_DWORD *)(i + 140) != 6 )
      {
        v8 = (unsigned int)(*(_DWORD *)(i + 140) - 9);
        if ( *(_DWORD *)(i + 140) == 9 )
          goto LABEL_23;
        if ( *(_DWORD *)(i + 140) != 13 )
          continue;
      }
    }
    v15 = 1;
    if ( *(_DWORD *)(i + 144) == 2 || *(_QWORD *)(i + 264) && *(_DWORD *)(*(_QWORD *)(i + 256) + 48LL) == 2 )
      v16 = 1;
  }
  if ( v14 )
  {
    if ( v15 && v16 )
    {
      while ( v13 )
      {
        v112 = 0;
        if ( *(_DWORD *)(v13 + 140) == 2
          || *(_DWORD *)(v13 + 140) == 3
          || *(_DWORD *)(v13 + 140) == 4
          || *(_DWORD *)(v13 + 140) == 9 )
        {
          v18 = DuplicateParserString(
                  (struct Windows::Rtl::IPoolAllocator *)v136,
                  (const struct _LUTF8_STRING *)(v13 + 200),
                  &v112);
          if ( v18 < 0 )
          {
            v20 = 2739;
            goto LABEL_41;
          }
          if ( CCbsStringArray::Find(
                 (CCbsSession *)((char *)v6 + 1888),
                 v112,
                 (int (*)(wchar_t *const *, wchar_t *const *))StringArrayIsEqualCaseInsensitive) == 0xFFFFFFFF )
          {
            v18 = CCbsStringArray::CopyAndAdd((CCbsSession *)((char *)v6 + 1888), v112);
            if ( v18 < 0 )
            {
              v131 = v18;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed adding capability to array: {}",
                  (__int64)&v112);
                v105 = (wchar_t *)&v131;
                LOBYTE(v19) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v19,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v105);
              }
              v20 = 2746;
              goto LABEL_41;
            }
          }
        }
        v13 = *(_QWORD *)(v13 + 296);
      }
    }
    LODWORD(hFile) = 0;
    IsSmartPended = CCbsSession::LCUInstallIsSmartPended(v6, (int *const)&hFile);
    v9 = IsSmartPended;
    if ( IsSmartPended < 0 )
    {
      v133 = IsSmartPended;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting LCU smart pended state");
        v107 = &v133;
        LOBYTE(v22) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v22,
          3,
          (unsigned int)": {}",
          (__int64)&v107);
      }
      v10 = 2773;
      goto LABEL_9;
    }
    if ( (_DWORD)hFile )
    {
      v9 = -2146498554;
      v131 = -2146498554;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Attempted to install a FOD or LP with a postponed LCU install pending, a reboot must be performed first");
        *(_QWORD *)v103 = &v131;
        LOBYTE(v23) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v23,
          3,
          (unsigned int)": {}",
          (__int64)v103);
      }
      v10 = 2779;
      goto LABEL_9;
    }
    v11 = v111;
  }
  v24 = *(_QWORD *)(v11 + 136);
  if ( v24 )
  {
    for ( j = *(_QWORD *)(v24 + 16); j; j = *(_QWORD *)(j + 72) )
    {
      v18 = CCbsSession::AddFeatureToModify(v6, j, 0);
      if ( v18 < 0 )
      {
        NumberOfBytesWritten = v18;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to process RemoveFeature Action");
          *(_QWORD *)nNumberOfBytesToWrite = &NumberOfBytesWritten;
          LOBYTE(v26) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v26,
            3,
            (unsigned int)": {}",
            (__int64)nNumberOfBytesToWrite);
        }
        v20 = 2791;
        goto LABEL_41;
      }
    }
    for ( k = *(_QWORD *)(*(_QWORD *)(v111 + 136) + 32LL); k; k = *(_QWORD *)(k + 72) )
    {
      v18 = CCbsSession::AddFeatureToModify(v6, k, 64);
      if ( v18 < 0 )
      {
        LODWORD(v129) = v18;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to process DisableFeature Action");
          v110 = &v129;
          LOBYTE(v28) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v28,
            3,
            (unsigned int)": {}",
            (__int64)&v110);
        }
        v20 = 2796;
        goto LABEL_41;
      }
    }
    for ( m = **(_QWORD **)(v111 + 136); ; m = *(_QWORD *)(m + 72) )
    {
      if ( !m )
        goto LABEL_73;
      v18 = CCbsSession::AddFeatureToModify(v6, m, 112);
      if ( v18 < 0 )
        break;
    }
    v128 = v18;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to process InstallFeature Action");
      v104 = &v128;
      LOBYTE(v30) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v30,
        3,
        (unsigned int)": {}",
        (__int64)&v104);
    }
    v20 = 2801;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
      (const char *)(unsigned int)v18,
      (int)dwCreationDisposition);
    v9 = v18;
    goto LABEL_241;
  }
LABEL_73:
  for ( n = *(_QWORD *)(v12 + 56); n; n = *(_QWORD *)(n + 296) )
  {
    v100 = 0;
    lpBuffer = 0;
    v129 = 0;
    v96 = 0;
    CCbsArray<MultiplePayloadsforPackage>::CCbsArray<MultiplePayloadsforPackage>(v137, v8);
    if ( !v32 || *(_DWORD *)(n + 136) != 4 )
    {
      v33 = *(_DWORD *)(n + 144);
      if ( v32 )
        v33 = *(_DWORD *)(*(_QWORD *)(n + 256) + 48LL);
      v34 = DuplicateParserString(
              (struct Windows::Rtl::IPoolAllocator *)v136,
              (const struct _LUTF8_STRING *)(n + 40),
              (wchar_t **)&lpBuffer);
      v9 = v34;
      if ( v34 < 0 )
      {
        v44 = 2835;
LABEL_233:
        v92 = (unsigned int)v34;
LABEL_234:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v44,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
          (const char *)v92,
          (int)dwCreationDisposition);
LABEL_235:
        CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v137);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v96);
        goto LABEL_241;
      }
      if ( !v33 )
      {
        lpFileName = 0;
        v35 = SczAllocCombinePath2Sz(&lpFileName, v106, lpBuffer);
        v9 = v35;
        if ( v35 < 0 )
        {
          v73 = 2840;
          goto LABEL_166;
        }
        v35 = CCbsStringArray::CopyAndAdd((CCbsSession *)((char *)v6 + 1952), lpFileName);
        v9 = v35;
        if ( v35 < 0 )
        {
          v73 = 2842;
LABEL_166:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v73,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
            (const char *)(unsigned int)v35,
            (int)dwCreationDisposition);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
          goto LABEL_235;
        }
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
      }
      v133 = v128 & 0x40;
      if ( (v128 & 0x40) != 0 || !(unsigned int)_o__wcsicmp(lpBuffer, v113) )
      {
        if ( v33 != 2 )
        {
          v9 = -2146498557;
          v128 = -2146498557;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Evaluation of package path: {} for missing files is not allowed except for Express packages",
              (__int64)&v113);
            *(_QWORD *)v101 = &v128;
            LOBYTE(v91) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v91,
              3,
              (unsigned int)": {}",
              (__int64)v101);
          }
          v92 = 2148468739LL;
          v44 = 2861;
          goto LABEL_234;
        }
        v126 = 0;
        v116 = 0;
        v118 = 0;
        v115 = 0;
        v119 = 0;
        v117 = 0;
        v121 = 0;
        v120 = 0;
        v123 = 0;
        v122 = 0;
        v125 = 0;
        v124 = 0;
        v127 = 0;
        if ( *(_QWORD *)(n + 264) )
        {
          v36 = *(__int128 **)(n + 256);
        }
        else
        {
          v36 = &v115;
          BYTE3(v127) = *(_BYTE *)(n + 305);
          v120 = *(_OWORD *)(n + 40);
          v121 = *(_QWORD *)(n + 56);
          BYTE4(v127) = *(_BYTE *)(n + 307);
          v122 = *(_OWORD *)(n + 88);
          v123 = *(_QWORD *)(n + 104);
          BYTE5(v127) = *(_BYTE *)(n + 308);
          v124 = *(_OWORD *)(n + 112);
          v125 = *(_QWORD *)(n + 128);
        }
        v37 = v106;
        while ( v36 )
        {
          v143 = 0;
          v140 = 0;
          v141 = 0;
          v142 = 0;
          WindowsUpdatePackage = DuplicateParserString(
                                   (struct Windows::Rtl::IPoolAllocator *)v136,
                                   (const struct _LUTF8_STRING *)(n + 40),
                                   (wchar_t **)&lpBuffer);
          if ( WindowsUpdatePackage < 0 )
          {
            v40 = 2881;
            goto LABEL_177;
          }
          WindowsUpdatePackage = SczAllocFromSz((char *)&v140 + 8, lpBuffer);
          if ( WindowsUpdatePackage < 0 )
          {
            v40 = 2883;
            goto LABEL_177;
          }
          if ( *((_BYTE *)v36 + 140) )
          {
            WindowsUpdatePackage = DuplicateParserString(
                                     (struct Windows::Rtl::IPoolAllocator *)v136,
                                     (const struct _LUTF8_STRING *)(v36 + 5),
                                     &v100);
            if ( WindowsUpdatePackage < 0 )
            {
              v40 = 2894;
              goto LABEL_177;
            }
            v39 = v100;
            WindowsUpdatePackage = SczAllocFormatted(&v96, L"%ws%ws", v106, v100);
            if ( WindowsUpdatePackage < 0 )
            {
              v40 = 2895;
LABEL_177:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v40,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                (const char *)(unsigned int)WindowsUpdatePackage,
                (int)dwCreationDisposition);
              MultiplePayloadsforPackage::~MultiplePayloadsforPackage((MultiplePayloadsforPackage *)&v140);
              goto LABEL_178;
            }
          }
          else
          {
            WindowsUpdatePackage = DuplicateParserString(
                                     (struct Windows::Rtl::IPoolAllocator *)v136,
                                     (const struct _LUTF8_STRING *)(n + 40),
                                     &v100);
            if ( WindowsUpdatePackage < 0 )
            {
              v40 = 2899;
              goto LABEL_177;
            }
            v39 = v100;
            WindowsUpdatePackage = SczAllocFormatted(&v96, L"%ws%ws", v106, v100);
            if ( WindowsUpdatePackage < 0 )
            {
              v40 = 2900;
              goto LABEL_177;
            }
          }
          WindowsUpdatePackage = SczAllocFromSz(&v140, v39);
          if ( WindowsUpdatePackage < 0 )
          {
            v40 = 2903;
            goto LABEL_177;
          }
          v37 = v106;
          WindowsUpdatePackage = SczAllocFormatted(&v141, L"%ws%ws", v106, (_QWORD)v140);
          if ( WindowsUpdatePackage < 0 )
          {
            v40 = 2909;
            goto LABEL_177;
          }
          if ( *((_BYTE *)v36 + 141) )
          {
            WindowsUpdatePackage = DuplicateParserString(
                                     (struct Windows::Rtl::IPoolAllocator *)v136,
                                     (const struct _LUTF8_STRING *)((char *)v36 + 104),
                                     &v129);
            if ( WindowsUpdatePackage < 0 )
            {
              v40 = 2913;
              goto LABEL_177;
            }
            WindowsUpdatePackage = SczAllocFormatted((char *)&v142 + 8, L"%ws%ws", v37, v129);
            if ( WindowsUpdatePackage < 0 )
            {
              v40 = 2919;
              goto LABEL_177;
            }
            *(_QWORD *)v103 = *((_QWORD *)&v142 + 1);
            if ( LogAdapter::g_Logger )
            {
              LOBYTE(v41) = 1;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                v41,
                1,
                (unsigned int)"ActionList: Using TurboContainer: {}",
                (__int64)v103);
            }
          }
          CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::SwapOntoBack(v137, &v140);
          MultiplePayloadsforPackage::~MultiplePayloadsforPackage((MultiplePayloadsforPackage *)&v140);
          v36 = (__int128 *)*((_QWORD *)v36 + 16);
        }
        v42 = 0;
        if ( *(_BYTE *)(n + 308) )
        {
          v34 = DuplicateParserString(
                  (struct Windows::Rtl::IPoolAllocator *)v136,
                  (const struct _LUTF8_STRING *)(n + 112),
                  &v129);
          v9 = v34;
          if ( v34 < 0 )
          {
            v44 = 2931;
            goto LABEL_233;
          }
          v43 = (__int64)v104;
          v34 = SczAllocFormatted(v104 + 582, L"%ws%ws", v37, v129);
          v9 = v34;
          if ( v34 < 0 )
          {
            v44 = 2933;
            goto LABEL_233;
          }
        }
        else
        {
          v43 = (__int64)v104;
        }
        CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(v144);
        v46 = v139;
        v47 = v139 + 56 * v138;
        while ( v46 != v47 )
        {
          v48 = *(_QWORD *)(v46 + 16);
          v107 = 0;
          *(_QWORD *)v103 = v48;
          if ( LogAdapter::g_Logger )
          {
            LOBYTE(v45) = 1;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              v45,
              1,
              (unsigned int)"ActionList: Checking package: {} for missing files",
              (__int64)v103);
          }
          Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v107);
          v49 = *(_QWORD *)(v43 + 1128);
          dwCreationDisposition = v103;
          *(GUID *)v103 = GUID_NULL;
          WindowsUpdatePackage = CCbsSession::CreateWindowsUpdatePackage(v43, v49, 0, 0);
          if ( WindowsUpdatePackage < 0 )
          {
            v128 = WindowsUpdatePackage;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v102 = v96;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to create package: {}",
                (__int64)v102);
              *(_QWORD *)v103 = &v128;
              LOBYTE(v74) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v74,
                3,
                (unsigned int)": {}",
                (__int64)v103);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB8B,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
              (const char *)(unsigned int)WindowsUpdatePackage,
              (int)dwCreationDisposition);
            Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v107);
            goto LABEL_183;
          }
          *(_QWORD *)v103 = v107;
          CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::Add(v144, v103);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v107);
          v43 = (__int64)v104;
          v46 += 56;
        }
        v50 = v145;
        v51 = v146;
        if ( v145 > 1 )
        {
          v52 = v145 - 1;
          do
          {
            v53 = v42 + 1;
            v54 = v42;
            v42 = v53;
            if ( v53 < v50 )
            {
              do
              {
                if ( (int)PackageVersionComparator(v51[v54], v51[v53]) > 0 )
                {
                  v55 = v51[v54];
                  v51[v54] = v51[v53];
                  v51[v53] = v55;
                }
                ++v53;
              }
              while ( v53 < v50 );
              v52 = v50 - 1;
            }
          }
          while ( v42 < v52 );
        }
        v56 = *(_DWORD *)(n + 136) == 5;
        v57 = (wchar_t *)&v51[v50];
        v58 = 257;
        v105 = v57;
        if ( !v56 )
          v58 = 1;
        LODWORD(v129) = v58;
        while ( v51 != (__int64 *)v57 )
        {
          v59 = *v51;
          if ( v50 > 1 )
          {
            v60 = &qword_1802EB518;
            if ( *(_QWORD *)(v59 + 120) )
              v60 = *(const wchar_t **)(v59 + 120);
            *(_QWORD *)v103 = v60;
            if ( LogAdapter::g_Logger )
            {
              LOBYTE(v45) = 1;
              LogAdapter::Logger::LogNumObjects<unsigned long,wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                v45,
                1,
                (unsigned int)"MFL: Adding payload package index: {} package: {} for MFL generation",
                (__int64)&v132,
                (__int64)v103);
            }
          }
          ++v132;
          WindowsUpdatePackage = CCbsPackage::InitiateChanges(
                                   v59,
                                   (__int64)v104,
                                   *((void **)v104 + 141),
                                   v58,
                                   112,
                                   0,
                                   0,
                                   0);
          if ( WindowsUpdatePackage < 0 )
          {
            v131 = WindowsUpdatePackage;
            if ( LogAdapter::g_Logger )
            {
              v75 = &qword_1802EB518;
              if ( *(_QWORD *)(v59 + 120) )
                v75 = *(const wchar_t **)(v59 + 120);
              *(_QWORD *)v102 = v75;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed Initiating changes for package: {}",
                (__int64)v102);
              *(_QWORD *)v101 = &v131;
              LOBYTE(v76) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v76,
                3,
                (unsigned int)": {}",
                (__int64)v101);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xBAF,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
              (const char *)(unsigned int)WindowsUpdatePackage,
              (int)dwCreationDisposition);
LABEL_183:
            CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v144);
LABEL_178:
            CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v137);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v96);
            v9 = WindowsUpdatePackage;
            goto LABEL_241;
          }
          if ( !**(_QWORD **)v102 )
            Windows::AutoComPtr<CCbsUpdate>::operator=(*(_QWORD *)v102, v59);
          v58 = (unsigned int)v129;
          ++v51;
          v57 = v105;
        }
        v61 = *((_QWORD *)v104 + 296);
        *(_QWORD *)v103 = v61;
        if ( v61 )
        {
          for ( ii = **(_QWORD **)(v111 + 112); ii; ii = *(_QWORD *)(ii + 256) )
          {
            v97[0] = 0;
            if ( (int)Windows::StringUtil::Rtl::AreStringsEqualByOrdinalCaseInvariant<_LUTF8_STRING,_LUTF8_STRING>(
                        n + 176,
                        ii + 80,
                        v97) >= 0
              && v97[0] )
            {
              v63 = *(_QWORD *)(ii + 240);
              while ( 1 )
              {
                if ( !v63 )
                  goto LABEL_162;
                lpBuffer = 0;
                *(_QWORD *)nNumberOfBytesToWrite = 0;
                hFile = 0;
                v110 = 0;
                v105 = 0;
                lpFileName = 0;
                v100 = 0;
                v129 = 0;
                v64 = DuplicateParserString(
                        (struct Windows::Rtl::IPoolAllocator *)v136,
                        (const struct _LUTF8_STRING *)(v63 + 376),
                        (wchar_t **)&hFile);
                v9 = v64;
                if ( v64 < 0 )
                {
                  v86 = 3027;
                  goto LABEL_214;
                }
                v64 = DuplicateParserString(
                        (struct Windows::Rtl::IPoolAllocator *)v136,
                        (const struct _LUTF8_STRING *)(v63 + 72),
                        &v105);
                v9 = v64;
                if ( v64 < 0 )
                {
                  v86 = 3029;
                  goto LABEL_214;
                }
                v64 = SczAllocFormatted(&v100, L"%ws%ws", v106, v105);
                v9 = v64;
                if ( v64 < 0 )
                  break;
                v65 = FileFromPath(hFile);
                v66 = v100;
                v110 = (wchar_t **)v65;
                v105 = v100;
                if ( LogAdapter::g_Logger )
                {
                  LOBYTE(v65) = 1;
                  LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                    (_DWORD)LogAdapter::g_Logger,
                    v65,
                    1,
                    (unsigned int)"Extracting {} from container {} ....",
                    (__int64)&v110,
                    (__int64)&v105);
                  v65 = (__int64)v110;
                }
                v67 = (*(__int64 (__fastcall **)(__int64, __int64, DWORD *, wchar_t *))(*(_QWORD *)v61 + 16LL))(
                        v61,
                        v65,
                        nNumberOfBytesToWrite,
                        v66);
                if ( v67 < 0 )
                {
                  v128 = v67;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                      (_DWORD)LogAdapter::g_Logger,
                      0,
                      3,
                      (unsigned int)"Failed to get CIX file size: {}",
                      (__int64)&v110);
                    *(_QWORD *)v101 = &v128;
                    LOBYTE(v90) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v90,
                      3,
                      (unsigned int)": {}",
                      (__int64)v101);
                  }
                  v85 = 3039;
LABEL_225:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v85,
                    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                    (const char *)(unsigned int)v67,
                    (int)dwCreationDisposition);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v129);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v100);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
                  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&lpBuffer);
                  CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v144);
                  CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v137);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v96);
                  v9 = v67;
LABEL_241:
                  Windows::Rtl::PrivateHeapPool::~PrivateHeapPool((Windows::Rtl::PrivateHeapPool *)v136);
                  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v108);
                  return v9;
                }
                Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(
                  &lpBuffer,
                  *(_QWORD *)nNumberOfBytesToWrite);
                v68 = lpBuffer;
                if ( !lpBuffer )
                {
                  v9 = -2147024882;
                  v128 = -2147024882;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed to allocate memory for manifest blob");
                    *(_QWORD *)v101 = &v128;
                    LOBYTE(v89) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v89,
                      3,
                      (unsigned int)": {}",
                      (__int64)v101);
                  }
                  v87 = 2147942414LL;
                  v86 = 3042;
                  goto LABEL_215;
                }
                dwCreationDisposition = nNumberOfBytesToWrite;
                v9 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, LPCVOID, _QWORD))(**(_QWORD **)v103 + 8LL))(
                       *(_QWORD *)v103,
                       v110,
                       lpBuffer,
                       *(_QWORD *)nNumberOfBytesToWrite);
                if ( (v9 & 0x80000000) != 0 )
                {
                  v128 = v9;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                      (_DWORD)LogAdapter::g_Logger,
                      0,
                      3,
                      (unsigned int)"Failed to get blob from turbocontainer: {}",
                      (__int64)&v110);
                    *(_QWORD *)v101 = &v128;
                    LOBYTE(v88) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v88,
                      3,
                      (unsigned int)": {}",
                      (__int64)v101);
                  }
                  v87 = v9;
                  v86 = 3046;
                  goto LABEL_215;
                }
                v64 = SczAllocFormatted(&lpFileName, L"%wsmetadata\\%ws", v106, hFile);
                v9 = v64;
                if ( v64 < 0 )
                {
                  v86 = 3048;
LABEL_214:
                  v87 = (unsigned int)v64;
LABEL_215:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v86,
                    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                    (const char *)v87,
                    (int)dwCreationDisposition);
                  goto LABEL_197;
                }
                v69 = lpFileName;
                v67 = DirectoryFromPath((wchar_t *)lpFileName);
                if ( v67 < 0 )
                {
                  v128 = v67;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get directory");
                    *(_QWORD *)v101 = &v128;
                    LOBYTE(v84) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v84,
                      3,
                      (unsigned int)": {}",
                      (__int64)v101);
                  }
                  v85 = 3050;
                  goto LABEL_225;
                }
                v70 = v129;
                Directory = RecursivelyCreateDirectory(v129, 0);
                LODWORD(hFile) = Directory;
                if ( Directory < 0 )
                {
                  v128 = Directory;
                  if ( LogAdapter::g_Logger )
                  {
                    *(_QWORD *)v101 = v70;
                    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                      (_DWORD)LogAdapter::g_Logger,
                      0,
                      3,
                      (unsigned int)"Failed to create directory {}",
                      (__int64)v101);
                    *(_QWORD *)v102 = &v128;
                    LOBYTE(v83) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v83,
                      3,
                      (unsigned int)": {}",
                      (__int64)v102);
                    Directory = (int)hFile;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xBEE,
                    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                    (const char *)(unsigned int)Directory,
                    (int)dwCreationDisposition);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v129);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v100);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
                  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&lpBuffer);
                  CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v144);
                  CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v137);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v96);
                  v9 = (unsigned int)hFile;
                  goto LABEL_241;
                }
                hFile = 0;
                NumberOfBytesWritten = 0;
                FileW = CreateFileW(v69, 0x40000000u, 0, 0, 2u, 0x80u, 0);
                Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
                  &hFile,
                  FileW);
                if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
                {
                  LastError = GetLastError();
                  if ( LogAdapter::g_Logger )
                  {
                    *(_QWORD *)v101 = v69;
                    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                      (_DWORD)LogAdapter::g_Logger,
                      0,
                      3,
                      (unsigned int)"Failed to open payload file: {}",
                      (__int64)v101);
                    if ( LastError > 0 )
                      v82 = (unsigned __int16)LastError | 0x80070000;
                    else
                      v82 = LastError;
                    v128 = v82;
                    LOBYTE(v81) = 1;
                    *(_QWORD *)v102 = &v128;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v81,
                      3,
                      (unsigned int)": {0}",
                      (__int64)v102);
                  }
                  if ( LastError )
                  {
                    v80 = 3061;
LABEL_196:
                    v9 = wil::details::in1diag3::Return_Win32(
                           retaddr,
                           (void *)v80,
                           (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                           (const char *)(unsigned int)LastError,
                           (unsigned int)dwCreationDisposition);
                    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
LABEL_197:
                    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v129);
                    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v100);
                    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
                    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&lpBuffer);
                    CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v144);
                    goto LABEL_235;
                  }
LABEL_205:
                  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v129);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v100);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
                  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&lpBuffer);
                  CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v144);
LABEL_206:
                  CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v137);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v96);
                  v9 = 0;
                  goto LABEL_241;
                }
                if ( !WriteFile(hFile, v68, nNumberOfBytesToWrite[0], &NumberOfBytesWritten, 0) )
                {
                  LastError = GetLastError();
                  if ( LogAdapter::g_Logger )
                  {
                    *(_QWORD *)v101 = v69;
                    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                      (_DWORD)LogAdapter::g_Logger,
                      0,
                      3,
                      (unsigned int)"Failed to write file: {}",
                      (__int64)v101);
                    if ( LastError > 0 )
                      v79 = (unsigned __int16)LastError | 0x80070000;
                    else
                      v79 = LastError;
                    v128 = v79;
                    LOBYTE(v78) = 1;
                    *(_QWORD *)v102 = &v128;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v78,
                      3,
                      (unsigned int)": {0}",
                      (__int64)v102);
                  }
                  if ( LastError )
                  {
                    v80 = 3066;
                    goto LABEL_196;
                  }
                  goto LABEL_205;
                }
                Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
                Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v129);
                Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v100);
                Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
                Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&lpBuffer);
                v63 = *(_QWORD *)(v63 + 416);
                v61 = *(_QWORD *)v103;
              }
              v86 = 3031;
              goto LABEL_214;
            }
          }
        }
LABEL_162:
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v144);
        if ( !v133 )
          goto LABEL_206;
        v6 = (CCbsSession *)v104;
      }
    }
    CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v137);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v96);
  }
  if ( !v132 )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"No entry in the ActionList: {} matched the FilePath: {}",
        (__int64)&v114,
        (__int64)&v113);
      *(_QWORD *)v101 = &v128;
      v128 = -2147023728;
      LOBYTE(v94) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v94,
        3,
        (unsigned int)": {0}",
        (__int64)v101);
    }
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xC0D,
           (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
           (const char *)0x490,
           (unsigned int)dwCreationDisposition);
    goto LABEL_241;
  }
  LogAdapter::TraceAtLevel<unsigned long>(1, "{} packages are processed from the action list.", &v132);
  Windows::Rtl::PrivateHeapPool::~PrivateHeapPool((Windows::Rtl::PrivateHeapPool *)v136);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v108);
  return 0;
}

```

## disassembly

```asm
0x1800cd91c  mov     [rsp-8+arg_8], rbx
0x1800cd921  push    rbp
0x1800cd922  push    rsi
0x1800cd923  push    rdi
0x1800cd924  push    r12
0x1800cd926  push    r13
0x1800cd928  push    r14
0x1800cd92a  push    r15
0x1800cd92c  lea     rbp, [rsp-1D0h]
0x1800cd934  sub     rsp, 2D0h
0x1800cd93b  mov     rax, cs:__security_cookie
0x1800cd942  xor     rax, rsp
0x1800cd945  mov     [rbp+200h+var_40], rax
0x1800cd94c  mov     rax, [rbp+200h+arg_28]
0x1800cd953  xor     r15d, r15d
0x1800cd956  mov     qword ptr [rbp+200h+var_260], rax
0x1800cd95a  mov     r10, r8
0x1800cd95d  mov     rax, [rbp+200h+arg_20]
0x1800cd964  mov     r14, rcx
0x1800cd967  mov     [rbp+200h+var_1F0], rax
0x1800cd96b  xorps   xmm0, xmm0
0x1800cd96e  xor     eax, eax
0x1800cd970  mov     [rbp+200h+var_230], r9
0x1800cd974  mov     [rbp+200h+var_210], rax
0x1800cd978  lea     r9, [rbp+200h+var_220]
0x1800cd97c  lea     rax, ??_7PrivateHeapPool@Rtl@Windows@@6B@; const Windows::Rtl::PrivateHeapPool::`vftable'
0x1800cd983  mov     [rbp+200h+var_150], edx
0x1800cd989  mov     [rbp+200h+var_240], rcx
0x1800cd98d  lea     rdx, [rbp+200h+var_120]
0x1800cd994  mov     [rbp+200h+var_1E8], r8
0x1800cd998  mov     rcx, r10
0x1800cd99b  lea     r8, [rbp+200h+var_200]
0x1800cd99f  mov     [rbp+200h+var_120], rax
0x1800cd9a6  movups  [rbp+200h+var_220], xmm0
0x1800cd9aa  mov     [rbp+200h+var_200], r15
0x1800cd9ae  mov     [rbp+200h+var_118], r15
0x1800cd9b5  mov     [rbp+200h+var_110], r15
0x1800cd9bc  mov     [rbp+200h+var_134], r15d
0x1800cd9c3  call    ?ReadActionList@ActionListParser@@YAJQEB_WAEAVIPoolAllocator@Rtl@Windows@@PEAPEAUActionListDocument@1@PEAV?$Auto@U_LBLOB@@@4@@Z; ActionListParser::ReadActionList(wchar_t const * const,Windows::Rtl::IPoolAllocator &,ActionListParser::ActionListDocument * *,Windows::Auto<_LBLOB> *)
0x1800cd9c8  mov     ebx, eax
0x1800cd9ca  test    eax, eax
0x1800cd9cc  jns     short loc_1800CDA33
0x1800cd9ce  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cd9d5  mov     dword ptr [rbp+200h+hFile], eax
0x1800cd9db  test    rcx, rcx
0x1800cd9de  jz      short loc_1800CDA2C
0x1800cd9e0  lea     rax, [rbp+200h+var_1E8]
0x1800cd9e4  xor     edx, edx
0x1800cd9e6  lea     r12d, [r15+3]
0x1800cd9ea  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800cd9ef  mov     r8d, r12d
0x1800cd9f2  lea     r9, aFailedToLoadAc_2; "Failed to load actions from {}"
0x1800cd9f9  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800cd9fe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cda05  lea     rax, [rbp+200h+hFile]
0x1800cda0c  mov     qword ptr [rbp+200h+var_250], rax
0x1800cda10  lea     r9, asc_1802EE7AC; ": {}"
0x1800cda17  lea     rax, [rbp+200h+var_250]
0x1800cda1b  mov     r8d, r12d
0x1800cda1e  lea     edx, [r15+1]
0x1800cda22  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800cda27  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cda2c  mov     edx, 0A76h
0x1800cda31  jmp     short loc_1800CDAA6
0x1800cda33  mov     r8, [rbp+200h+var_200]
0x1800cda37  mov     rsi, [r8+98h]
0x1800cda3e  cmp     [rsi+40h], r15
0x1800cda42  jnz     short loc_1800CDAC1
0x1800cda44  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cda4b  mov     ebx, 800F0952h
0x1800cda50  mov     [rbp+200h+var_138], ebx
0x1800cda56  test    rcx, rcx
0x1800cda59  jz      short loc_1800CDAA1
0x1800cda5b  mov     r12d, 3
0x1800cda61  lea     r9, aActionlistNoPa; "ActionList: No package to process in ac"...
0x1800cda68  mov     r8d, r12d
0x1800cda6b  xor     edx, edx
0x1800cda6d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cda72  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cda79  lea     rax, [rbp+200h+var_138]
0x1800cda80  mov     qword ptr [rbp+200h+var_250], rax
0x1800cda84  lea     r9, asc_1802EE7AC; ": {}"
0x1800cda8b  lea     rax, [rbp+200h+var_250]
0x1800cda8f  mov     r8d, r12d
0x1800cda92  lea     edx, [r12-2]
0x1800cda97  mov     qword ptr [rsp+300h+dwCreationDisposition], rax; int
0x1800cda9c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cdaa1  mov     edx, 0A7Bh; void *
0x1800cdaa6  mov     rcx, [rbp+208h]; this
0x1800cdaad  lea     r8, aOnecoreBaseCbs_69; "onecore\\base\\cbs\\core\\cbssessionope"...
0x1800cdab4  mov     r9d, ebx; char *
0x1800cdab7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cdabc  jmp     loc_1800CF078
0x1800cdac1  mov     rbx, [rsi+38h]
0x1800cdac5  mov     r12d, 3
0x1800cdacb  mov     r9b, r15b
0x1800cdace  mov     r10b, r15b
0x1800cdad1  mov     r11b, r15b
0x1800cdad4  mov     rax, rbx
0x1800cdad7  lea     r13d, [r12-2]
0x1800cdadc  test    rax, rax
0x1800cdadf  jz      short loc_1800CDB3D
0x1800cdae1  mov     edx, [rax+8Ch]
0x1800cdae7  sub     edx, 2
0x1800cdaea  jz      short loc_1800CDB31
0x1800cdaec  sub     edx, r13d
0x1800cdaef  jz      short loc_1800CDB31
0x1800cdaf1  sub     edx, r13d
0x1800cdaf4  jz      short loc_1800CDB31
0x1800cdaf6  sub     edx, r13d
0x1800cdaf9  jz      short loc_1800CDB0A
0x1800cdafb  sub     edx, r13d
0x1800cdafe  jz      short loc_1800CDB0A
0x1800cdb00  sub     edx, r12d
0x1800cdb03  jz      short loc_1800CDB31
0x1800cdb05  cmp     edx, 4
0x1800cdb08  jnz     short loc_1800CDB34
0x1800cdb0a  cmp     dword ptr [rax+90h], 2
0x1800cdb11  mov     r10b, r13b
0x1800cdb14  jz      short loc_1800CDB2C
0x1800cdb16  cmp     [rax+108h], r15
0x1800cdb1d  jbe     short loc_1800CDB34
0x1800cdb1f  mov     rcx, [rax+100h]
0x1800cdb26  cmp     dword ptr [rcx+30h], 2
0x1800cdb2a  jnz     short loc_1800CDB34
0x1800cdb2c  mov     r11b, r13b
0x1800cdb2f  jmp     short loc_1800CDB34
0x1800cdb31  mov     r9b, r13b
0x1800cdb34  mov     rax, [rax+128h]
0x1800cdb3b  jmp     short loc_1800CDADC
0x1800cdb3d  test    r9b, r9b
0x1800cdb40  jz      loc_1800CDD46
0x1800cdb46  test    r10b, r10b
0x1800cdb49  jz      loc_1800CDC64
0x1800cdb4f  test    r11b, r11b
0x1800cdb52  jz      loc_1800CDC64
0x1800cdb58  test    rbx, rbx
0x1800cdb5b  jz      loc_1800CDC64
0x1800cdb61  mov     [rbp+200h+var_1F8], r15
0x1800cdb65  mov     ecx, [rbx+8Ch]
0x1800cdb6b  sub     ecx, 2
0x1800cdb6e  jz      short loc_1800CDB7F
0x1800cdb70  sub     ecx, r13d
0x1800cdb73  jz      short loc_1800CDB7F
0x1800cdb75  sub     ecx, r13d
0x1800cdb78  jz      short loc_1800CDB7F
0x1800cdb7a  cmp     ecx, 5
0x1800cdb7d  jnz     short loc_1800CDBD6
0x1800cdb7f  lea     rdx, [rbx+0C8h]; struct _LUTF8_STRING *
0x1800cdb86  lea     r8, [rbp+200h+var_1F8]; wchar_t **
0x1800cdb8a  lea     rcx, [rbp+200h+var_120]; struct Windows::Rtl::IPoolAllocator *
0x1800cdb91  call    ?DuplicateParserString@@YAJAEAVIPoolAllocator@Rtl@Windows@@AEBU_LUTF8_STRING@@PEAPEA_W@Z; DuplicateParserString(Windows::Rtl::IPoolAllocator &,_LUTF8_STRING const &,wchar_t * *)
0x1800cdb96  mov     edi, eax
0x1800cdb98  test    eax, eax
0x1800cdb9a  js      loc_1800CDC42
0x1800cdba0  mov     rdx, [rbp+200h+var_1F8]; wchar_t *
0x1800cdba4  lea     rdi, [r14+760h]
0x1800cdbab  mov     rcx, rdi; this
0x1800cdbae  lea     r8, ?StringArrayIsEqualCaseInsensitive@@YAHAEBQEA_W0@Z; int (*)(wchar_t *const *, wchar_t *const *)
0x1800cdbb5  call    ?Find@CCbsStringArray@@QEBA_KQEB_WP6AHAEBQEA_W1@Z@Z; CCbsStringArray::Find(wchar_t const * const,int (*)(wchar_t * const &,wchar_t * const &))
0x1800cdbba  mov     ecx, 0FFFFFFFFh
0x1800cdbbf  cmp     rax, rcx
0x1800cdbc2  jnz     short loc_1800CDBD6
0x1800cdbc4  mov     rdx, [rbp+200h+var_1F8]; wchar_t *
0x1800cdbc8  mov     rcx, rdi; this
0x1800cdbcb  call    ?CopyAndAdd@CCbsStringArray@@QEAAJPEB_W@Z; CCbsStringArray::CopyAndAdd(wchar_t const *)
0x1800cdbd0  mov     edi, eax
0x1800cdbd2  test    eax, eax
0x1800cdbd4  js      short loc_1800CDBE2
0x1800cdbd6  mov     rbx, [rbx+128h]
0x1800cdbdd  jmp     loc_1800CDB58
0x1800cdbe2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdbe9  mov     [rbp+200h+var_138], edi
0x1800cdbef  test    rcx, rcx
0x1800cdbf2  jz      short loc_1800CDC3B
0x1800cdbf4  lea     rax, [rbp+200h+var_1F8]
0x1800cdbf8  mov     r8d, r12d
0x1800cdbfb  lea     r9, aFailedAddingCa; "Failed adding capability to array: {}"
0x1800cdc02  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800cdc07  xor     edx, edx
0x1800cdc09  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800cdc0e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdc15  lea     rax, [rbp+200h+var_138]
0x1800cdc1c  mov     [rbp+200h+var_238], rax
0x1800cdc20  lea     r9, asc_1802EE7AC; ": {}"
0x1800cdc27  lea     rax, [rbp+200h+var_238]
0x1800cdc2b  mov     r8d, r12d
0x1800cdc2e  mov     dl, r13b
0x1800cdc31  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800cdc36  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cdc3b  mov     edx, 0ABAh
0x1800cdc40  jmp     short loc_1800CDC47
0x1800cdc42  mov     edx, 0AB3h; void *
0x1800cdc47  mov     rcx, [rbp+208h]; this
0x1800cdc4e  lea     r8, aOnecoreBaseCbs_69; "onecore\\base\\cbs\\core\\cbssessionope"...
0x1800cdc55  mov     r9d, edi; char *
0x1800cdc58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cdc5d  mov     ebx, edi
0x1800cdc5f  jmp     loc_1800CF078
0x1800cdc64  lea     rdx, [rbp+200h+hFile]; int *
0x1800cdc6b  mov     dword ptr [rbp+200h+hFile], r15d
0x1800cdc72  mov     rcx, r14; this
0x1800cdc75  call    ?LCUInstallIsSmartPended@CCbsSession@@QEAAJQEAH@Z; CCbsSession::LCUInstallIsSmartPended(int * const)
0x1800cdc7a  mov     ebx, eax
0x1800cdc7c  test    eax, eax
0x1800cdc7e  jns     short loc_1800CDCDA
0x1800cdc80  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdc87  mov     [rbp+200h+var_130], eax
0x1800cdc8d  test    rcx, rcx
0x1800cdc90  jz      short loc_1800CDCD0
0x1800cdc92  lea     r9, aFailedGettingL; "Failed getting LCU smart pended state"
0x1800cdc99  mov     r8d, r12d
0x1800cdc9c  xor     edx, edx
0x1800cdc9e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cdca3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdcaa  lea     rax, [rbp+200h+var_130]
0x1800cdcb1  mov     [rbp+200h+var_228], rax
0x1800cdcb5  lea     r9, asc_1802EE7AC; ": {}"
0x1800cdcbc  lea     rax, [rbp+200h+var_228]
0x1800cdcc0  mov     r8d, r12d
0x1800cdcc3  mov     dl, r13b
0x1800cdcc6  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800cdccb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cdcd0  mov     edx, 0AD5h
0x1800cdcd5  jmp     loc_1800CDAA6
0x1800cdcda  cmp     dword ptr [rbp+200h+hFile], r15d
0x1800cdce1  jz      short loc_1800CDD42
0x1800cdce3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdcea  mov     ebx, 800F0806h
0x1800cdcef  mov     [rbp+200h+var_138], ebx
0x1800cdcf5  test    rcx, rcx
0x1800cdcf8  jz      short loc_1800CDD38
0x1800cdcfa  lea     r9, aAttemptedToIns; "Attempted to install a FOD or LP with a"...
0x1800cdd01  mov     r8d, r12d
0x1800cdd04  xor     edx, edx
0x1800cdd06  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cdd0b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdd12  lea     rax, [rbp+200h+var_138]
0x1800cdd19  mov     qword ptr [rbp+200h+var_250], rax
0x1800cdd1d  lea     r9, asc_1802EE7AC; ": {}"
0x1800cdd24  lea     rax, [rbp+200h+var_250]
0x1800cdd28  mov     r8d, r12d
0x1800cdd2b  mov     dl, r13b
0x1800cdd2e  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800cdd33  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cdd38  mov     edx, 0ADBh
0x1800cdd3d  jmp     loc_1800CDAA6
0x1800cdd42  mov     r8, [rbp+200h+var_200]
0x1800cdd46  mov     rbx, [r8+88h]
0x1800cdd4d  test    rbx, rbx
0x1800cdd50  jz      loc_1800CDEEE
0x1800cdd56  mov     rbx, [rbx+10h]
0x1800cdd5a  test    rbx, rbx
0x1800cdd5d  jz      short loc_1800CDDD9
0x1800cdd5f  xor     r8d, r8d
0x1800cdd62  mov     rdx, rbx
0x1800cdd65  mov     rcx, r14
0x1800cdd68  call    ?AddFeatureToModify@CCbsSession@@AEAAJAEBU_LUTF8_STRING@@W4CbsState@@@Z; CCbsSession::AddFeatureToModify(_LUTF8_STRING const &,CbsState)
0x1800cdd6d  mov     edi, eax
0x1800cdd6f  test    eax, eax
0x1800cdd71  js      short loc_1800CDD79
0x1800cdd73  mov     rbx, [rbx+48h]
0x1800cdd77  jmp     short loc_1800CDD5A
0x1800cdd79  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdd80  mov     [rbp+200h+NumberOfBytesWritten], edi
0x1800cdd86  test    rcx, rcx
0x1800cdd89  jz      short loc_1800CDDCF
0x1800cdd8b  lea     r9, aFailedToProces_29; "Failed to process RemoveFeature Action"
0x1800cdd92  mov     r8d, r12d
0x1800cdd95  xor     edx, edx
0x1800cdd97  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cdd9c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdda3  lea     rax, [rbp+200h+NumberOfBytesWritten]
0x1800cddaa  mov     qword ptr [rbp+200h+nNumberOfBytesToWrite], rax
0x1800cddb1  lea     r9, asc_1802EE7AC; ": {}"
0x1800cddb8  lea     rax, [rbp+200h+nNumberOfBytesToWrite]
0x1800cddbf  mov     r8d, r12d
0x1800cddc2  mov     dl, r13b
0x1800cddc5  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800cddca  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cddcf  mov     edx, 0AE7h
0x1800cddd4  jmp     loc_1800CDC47
0x1800cddd9  mov     rax, [rbp+200h+var_200]
0x1800cdddd  mov     rbx, [rax+88h]
0x1800cdde4  mov     rbx, [rbx+20h]
0x1800cdde8  test    rbx, rbx
0x1800cddeb  jz      short loc_1800CDE64
0x1800cdded  mov     r8d, 40h ; '@'
0x1800cddf3  mov     rdx, rbx
0x1800cddf6  mov     rcx, r14
0x1800cddf9  call    ?AddFeatureToModify@CCbsSession@@AEAAJAEBU_LUTF8_STRING@@W4CbsState@@@Z; CCbsSession::AddFeatureToModify(_LUTF8_STRING const &,CbsState)
0x1800cddfe  mov     edi, eax
0x1800cde00  test    eax, eax
0x1800cde02  js      short loc_1800CDE0A
0x1800cde04  mov     rbx, [rbx+48h]
0x1800cde08  jmp     short loc_1800CDDE8
0x1800cde0a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cde11  mov     dword ptr [rbp+200h+var_148], edi
0x1800cde17  test    rcx, rcx
0x1800cde1a  jz      short loc_1800CDE5A
  ... truncated ...
```
