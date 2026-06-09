# MigrateWinsockConfigurationEx

- ea: `0x1800328c0`
- end: `0x1800334fa`
- name: `MigrateWinsockConfigurationEx`
- size: `3130`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180032880`

## callees

- `0x1800222f0`
- `0x180022bd2`
- `0x180030b94`
- `0x180032294`
- `0x1800326d0`
- `0x18003273c`
- `0x1800327a8`
- `0x1800327cc`
- `0x1800327f0`
- `0x18003281c`
- `0x180032848`
- `0x180032864`
- `0x1800328c0`
- `0x180034098`
- `0x180034430`
- `0x180034690`
- `0x180034ae8`
- `0x180034da4`
- `0x180034ec4`
- `0x180034ff0`
- `0x180035440`
- `0x180035538`
- `0x180035838`
- `0x180035bc0`
- `0x180035f4c`
- `0x18003639c`
- `0x180037189`
- `0x18003847c`
- `0x180038570`
- `0x18003a8b0`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180032d5f`
- `ntdll!RtlFreeHeap` at `0x180032fb9`
- `ntdll!RtlFreeHeap` at `0x1800331d5`
- `ntdll!RtlFreeHeap` at `0x1800331fe`
- `ntdll!RtlFreeHeap` at `0x18003330b`
- `ntdll!RtlFreeHeap` at `0x180033353`
- `ntdll!RtlFreeHeap` at `0x1800333dd`
- `ntdll!RtlFreeHeap` at `0x1800333fe`
- `ntdll!RtlFreeHeap` at `0x18003341c`
- `ntdll!RtlFreeHeap` at `0x18003343d`
- `ntdll!RtlFreeHeap` at `0x18003345a`
- `ntdll!RtlFreeHeap` at `0x180033477`
- `ntdll!RtlFreeHeap` at `0x180033498`
- `ntdll!RtlFreeHeap` at `0x180032d5f`
- `ntdll!RtlFreeHeap` at `0x180032fb9`
- `ntdll!RtlFreeHeap` at `0x1800331d5`
- `ntdll!RtlFreeHeap` at `0x1800331fe`
- `ntdll!RtlFreeHeap` at `0x18003330b`
- `ntdll!RtlFreeHeap` at `0x180033353`
- `ntdll!RtlFreeHeap` at `0x1800333dd`
- `ntdll!RtlFreeHeap` at `0x1800333fe`
- `ntdll!RtlFreeHeap` at `0x18003341c`
- `ntdll!RtlFreeHeap` at `0x18003343d`
- `ntdll!RtlFreeHeap` at `0x18003345a`
- `ntdll!RtlFreeHeap` at `0x180033477`
- `ntdll!RtlFreeHeap` at `0x180033498`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003336a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003337f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033393`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800333a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800333bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003336a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003337f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033393`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800333a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800333bc`

## string_xrefs

- `0x1800329ce`: `OpenServicesRoot failed`
- `0x1800329fe`: `OpenWinsockRoot failed`
- `0x180032a41`: `OpenSetupMigrationRoot failed`
- `0x180032a68`: `ReadNewProviderList failed`
- `0x180032a8f`: `ReadOldProviderList failed`
- `0x180032ab1`: `ReadKnownStaticProviderList failed`
- `0x180032b71`: `Failed to remove old provider`
- `0x180032b3a`: `Successfully removed old provider`
- `0x180032b90`: `Enumerating new providers for updates`
- `0x180032bee`: `A new provider has been detected and will be installed`
- `0x180032d9c`: `ReadProtocolDataFromProvider failed`
- `0x180032c59`: `Non-offline-capable provider returned zero protocol entries`
- `0x180032cef`: `Successfully installed new provider; adding to updated provider list`
- `0x180032db6`: `Unable to add newly installed provider to updated provider list`
- `0x180032d19`: `Cannot install provider; skipping`
- `0x180032ddf`: `Updating the updated list in the online case`
- `0x180032e80`: `Adding static provider to updated list`
- `0x180032ea2`: `Failed to add provider to updated list`
- `0x180032ecb`: `Adding offline-capable provider to updated list`
- `0x180032f24`: `Failed to find protocol data in registry; continuing on`
- `0x18003325c`: `ReadProtocolDataFromRegistry failed`
- `0x180032fdd`: `Provider returned no protocol entries`
- `0x18003324d`: `RemoveProviderByName failed`
- `0x180033163`: `Successfully installed dynamic provider; adding it to updated list`
- `0x180033181`: `Failed to add to updated list`
- `0x180033190`: `Failed to install dynamic provider; skipping`
- `0x180033222`: `Successfully updated dynamic provider`
- `0x18003328d`: `Done populating the updated list`
- `0x1800332bd`: `Failed to write updated list to the old list registry key`
- `0x1800334a8`: `Exiting MigrateWinsockConfiguration with error`
- `0x1800334b8`: `Exiting MigrateWinsockConfiguration successfully`

## pseudocode

```c
__int64 __fastcall MigrateWinsockConfigurationEx(
        int *a1,
        unsigned int (__fastcall *a2)(__int64, _WORD *, _QWORD),
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  unsigned int (__fastcall *v5)(__int64, _WORD *, _QWORD); // r15
  unsigned int v7; // ebx
  HKEY v8; // r13
  __int64 v9; // rax
  void *v10; // r12
  unsigned int v11; // eax
  int v12; // ecx
  int v13; // r9d
  void *v14; // rsi
  HKEY v15; // r15
  unsigned int v16; // eax
  unsigned int v17; // edi
  unsigned int NewProviderList; // eax
  const wchar_t *v19; // rdx
  _WORD *v20; // rdi
  _WORD *v21; // r14
  unsigned int v22; // eax
  const wchar_t *v23; // rcx
  __int64 v24; // rax
  _WORD *v25; // rdi
  void *v26; // r14
  int v27; // esi
  const wchar_t *v28; // rcx
  unsigned int v29; // eax
  int v30; // eax
  __int64 v31; // r14
  unsigned int v32; // eax
  char v33; // bl
  unsigned int appended; // eax
  int v35; // ecx
  __int64 v36; // rax
  PVOID v37; // r14
  int updated; // eax
  _WORD *v39; // rdx
  const wchar_t *v40; // rcx
  unsigned int v41; // eax
  const wchar_t *v42; // rdx
  int v43; // eax
  unsigned int v44; // eax
  int v45; // esi
  unsigned int v46; // r15d
  int v47; // r14d
  bool v48; // zf
  PVOID v49; // r14
  unsigned int v50; // eax
  char v51; // bl
  int v52; // ecx
  __int64 v53; // rax
  int v54; // r8d
  unsigned int v55; // eax
  PVOID v56; // rdi
  PVOID v57; // rdi
  void *Buf1; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v60; // [rsp+68h] [rbp-98h]
  HKEY v61; // [rsp+70h] [rbp-90h]
  unsigned int v62; // [rsp+78h] [rbp-88h]
  unsigned int v63; // [rsp+7Ch] [rbp-84h] BYREF
  int v64; // [rsp+80h] [rbp-80h]
  _DWORD Size[3]; // [rsp+84h] [rbp-7Ch] BYREF
  void *Buf2; // [rsp+90h] [rbp-70h] BYREF
  int v67; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v68; // [rsp+9Ch] [rbp-64h] BYREF
  PVOID v69; // [rsp+A0h] [rbp-60h] BYREF
  HKEY v70; // [rsp+A8h] [rbp-58h]
  PVOID v71; // [rsp+B0h] [rbp-50h]
  HKEY hKey; // [rsp+B8h] [rbp-48h] BYREF
  HKEY v73; // [rsp+C0h] [rbp-40h]
  PVOID v74; // [rsp+C8h] [rbp-38h]
  PVOID v75; // [rsp+D0h] [rbp-30h]
  PVOID v76; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int (__fastcall *v77)(__int64, _WORD *, _QWORD); // [rsp+E0h] [rbp-20h]
  PVOID P[2]; // [rsp+E8h] [rbp-18h] BYREF
  PVOID v79[2]; // [rsp+F8h] [rbp-8h]
  __int64 v80; // [rsp+108h] [rbp+8h]
  int *v81; // [rsp+110h] [rbp+10h]
  __int128 v82; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v83[528]; // [rsp+130h] [rbp+30h] BYREF

  v62 = a3;
  v5 = a2;
  v77 = a2;
  v81 = a1;
  v60 = a4;
  memset_0(v83, 0, 0x208u);
  v76 = 0;
  v68 = 0;
  v80 = 0;
  v67 = 0;
  *(_OWORD *)P = 0;
  *(_OWORD *)v79 = 0;
  v82 = 0;
  if ( !a4 )
  {
    v7 = 87;
    LogError(87, L"Target information must be specified");
    return v7;
  }
  qword_180063FD0 = a5;
  v8 = 0;
  v9 = *(_QWORD *)(a4 + 8);
  v10 = 0;
  hKey = 0;
  v61 = 0;
  v70 = 0;
  v73 = 0;
  v71 = 0;
  v74 = 0;
  v69 = 0;
  v75 = 0;
  Buf2 = 0;
  Buf1 = 0;
  memset(Size, 0, sizeof(Size));
  v63 = 0;
  v64 = 0;
  DefaultTranslator = v9;
  ReadWs2Catalog(&v76, &v68, a4);
  v11 = OpenServicesRoot((PHKEY)&Size[1]);
  v7 = v11;
  if ( v11 )
  {
    LogError(v11, L"OpenServicesRoot failed");
    goto LABEL_5;
  }
  v16 = OpenWinsockRoot(*(HKEY *)&Size[1], &hKey);
  v17 = v16;
  if ( v16 )
  {
    LogError(v16, L"OpenWinsockRoot failed");
    v7 = 0;
    if ( v17 != 2 )
      v7 = v17;
    goto LABEL_5;
  }
  NewProviderList = OpenSetupMigrationRoot(hKey, (__int64)P, a4);
  v7 = NewProviderList;
  if ( !NewProviderList )
  {
    NewProviderList = ReadNewProviderList(hKey);
    v7 = NewProviderList;
    if ( NewProviderList )
    {
      v19 = L"ReadNewProviderList failed";
      goto LABEL_13;
    }
    NewProviderList = ReadMultiSz(v61, L"Provider List");
    v7 = NewProviderList;
    if ( NewProviderList )
    {
      v19 = L"ReadOldProviderList failed";
      goto LABEL_13;
    }
    NewProviderList = ReadMultiSz(v61, L"Known Static Providers");
    v7 = NewProviderList;
    if ( NewProviderList )
    {
      v19 = L"ReadKnownStaticProviderList failed";
      goto LABEL_13;
    }
    LogMsg(L"Enumerating old providers for potential deletion");
    v20 = v71;
    v8 = v70;
    v21 = v74;
    while ( *v20 )
    {
      if ( (unsigned int)IsStringInMultiSz(v21, v20) )
      {
        v23 = L"Keeping old provider";
      }
      else
      {
        if ( v5 && !v5(1, v20, v62) )
          goto LABEL_5;
        LogMsgWithProvider(L"Removing old provider", v20);
        v22 = RemoveProviderByName(v8, v20, P, a4);
        v7 = v22;
        if ( v22 )
        {
          LogErrorWithProvider(v22, L"Failed to remove old provider", v20);
          goto LABEL_5;
        }
        v64 = 1;
        v23 = L"Successfully removed old provider";
      }
      LogMsgWithProvider(v23, v20);
      v24 = -1;
      do
        ++v24;
      while ( v20[v24] );
      v20 += v24 + 1;
    }
    LogMsg(L"Done enumerating old providers");
    LogMsg(L"Enumerating new providers for updates");
    v25 = v21;
    v26 = 0;
    while ( *v25 )
    {
      if ( !(unsigned int)IsStringInMultiSz(v71, v25) )
      {
        if ( v5 && !v5(0, v25, v62) )
          goto LABEL_5;
        v27 = IsProviderOfflineCapable(*(_QWORD *)&Size[1], v25);
        LogMsgWithProvider(L"A new provider has been detected and will be installed", v25);
        v28 = L"This new provider is offline capable";
        if ( !v27 )
          v28 = L"This new provider is not offline capable";
        LogMsgWithProvider(v28, v25);
        if ( v27 )
          goto LABEL_44;
        v29 = ReadProtocolDataFromProvider(*(_QWORD *)&Size[1], v25, v83, &Buf2, Size, &v63);
        v7 = v29;
        if ( v29 )
        {
LABEL_56:
          LogErrorWithProvider(v29, L"ReadProtocolDataFromProvider failed", v25);
          v10 = Buf2;
          goto LABEL_5;
        }
        v10 = Buf2;
        if ( Buf2 )
        {
LABEL_44:
          v30 = IsStringInMultiSz(v75, v25);
          v31 = v60;
          v32 = InstallNewProvider(
                  (_DWORD)v73,
                  (_DWORD)v8,
                  Size[1],
                  v27,
                  (__int64)v25,
                  (__int64)v83,
                  v30,
                  (__int64)v10,
                  Size[0],
                  v63,
                  (__int64)P,
                  v60);
          v33 = v32;
          if ( v32 )
          {
            LogErrorWithProvider(v32, L"Cannot install provider; skipping", v25);
            if ( (xmmword_180063D60 & 2) != 0 )
              WPP_SF_Sd(v35, 11, (unsigned int)WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, (_DWORD)v25, v33);
            v26 = 0;
            v7 = 0;
          }
          else
          {
            LogMsgWithProvider(L"Successfully installed new provider; adding to updated provider list", v25);
            appended = AppendStringToMultiSz(&v69, v25);
            v7 = appended;
            if ( appended )
            {
              LogErrorWithProvider(appended, L"Unable to add newly installed provider to updated provider list", v25);
              v14 = Buf1;
              v15 = v61;
              goto LABEL_123;
            }
            v26 = 0;
          }
          if ( v10 )
          {
            RtlFreeHeap(SockPrivateHeap, 0, v10);
            v10 = 0;
            Buf2 = 0;
            v63 = 0;
          }
          v64 = 1;
        }
        else
        {
          LogMsgWithProvider(L"Non-offline-capable provider returned zero protocol entries", v25);
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_S(1025, 10, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, v25);
        }
      }
      v36 = -1;
      do
        ++v36;
      while ( v25[v36] );
      v25 += v36 + 1;
    }
    LogMsg(L"Done enumerating new providers");
    LogMsg(L"Updating the updated list in the online case");
    v25 = v74;
    v14 = Buf1;
    while ( 1 )
    {
      if ( !*v25 )
      {
        LogMsg(L"Done populating the updated list");
        v15 = v61;
        if ( v64 )
        {
          v55 = WriteMultiSz(v61);
          v7 = v55;
          if ( v55 )
            LogError(v55, L"Failed to write updated list to the old list registry key");
        }
        goto LABEL_122;
      }
      if ( (unsigned int)IsStringInMultiSz(v71, v25) )
      {
        if ( (unsigned int)IsStringInMultiSz(v75, v25) )
        {
          v37 = v76;
          if ( !v76 || (unsigned int)ReadProviderId(v8, v25, &v82) )
          {
            v26 = 0;
          }
          else
          {
            updated = UpdateMsafdToMswsock(v37, v68, &v82);
            v26 = 0;
            if ( !updated && v5 && !v5(3, v25, v62) )
              goto LABEL_6;
          }
          v39 = v25;
          v40 = L"Adding static provider to updated list";
LABEL_70:
          LogMsgWithProvider(v40, v39);
          v41 = AppendStringToMultiSz(&v69, v25);
          v7 = v41;
          if ( v41 )
          {
            v42 = L"Failed to add provider to updated list";
LABEL_72:
            LogErrorWithProvider(v41, v42, v25);
            goto LABEL_6;
          }
          goto LABEL_113;
        }
        v43 = IsProviderOfflineCapable(*(_QWORD *)&Size[1], v25);
        v39 = v25;
        if ( v43 )
        {
          v40 = L"Adding offline-capable provider to updated list";
          goto LABEL_70;
        }
        LogMsgWithProvider(L"Updating dynamic provider", v25);
        if ( v5 && !v5(2, v25, v62) )
          goto LABEL_6;
        v44 = ReadProtocolDataFromRegistry(v8, v25, &Buf1, &v67);
        v7 = v44;
        if ( v44 == 2 )
        {
          LogErrorWithProvider(2, L"Failed to find protocol data in registry; continuing on", v25);
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_S(1025, 12, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, v25);
          v45 = 0;
          Buf1 = 0;
          v67 = 0;
        }
        else
        {
          if ( v44 )
          {
            LogErrorWithProvider(v44, L"ReadProtocolDataFromRegistry failed", v25);
            if ( (xmmword_180063D60 & 2) != 0 )
              WPP_SF_SL(v12, 13, v54, (_DWORD)v25, v7);
            goto LABEL_5;
          }
          v45 = v67;
          v26 = Buf1;
        }
        v29 = ReadProtocolDataFromProvider(*(_QWORD *)&Size[1], v25, v83, &Buf2, Size, &v63);
        v7 = v29;
        if ( v29 )
          goto LABEL_56;
        v10 = Buf2;
        if ( Buf2 )
        {
          v46 = v63;
          MapProtocolInfoToSelfRelative(Buf2, v63);
          v47 = Size[0];
          v48 = v45 == Size[0];
          v14 = Buf1;
          if ( v48 && !memcmp_0(Buf1, v10, Size[0]) )
          {
            v49 = v76;
            if ( v76
              && !(unsigned int)ReadProviderId(v8, v25, &v82)
              && !(unsigned int)UpdateMsafdToMswsock(v49, v68, &v82)
              && v77
              && !v77(3, v25, v62) )
            {
              goto LABEL_6;
            }
            v41 = AppendStringToMultiSz(&v69, v25);
            v7 = v41;
            if ( v41 )
            {
              v42 = L"AppendStringToMultiSz failed";
              goto LABEL_72;
            }
          }
          else
          {
            if ( v77 && !v77(3, v25, v62) )
              goto LABEL_6;
            v41 = RemoveProviderByName(v8, v25, P, v60);
            v7 = v41;
            if ( v41 )
            {
              v42 = L"RemoveProviderByName failed";
              goto LABEL_72;
            }
            MapProtocolInfoToAbsolute(v10, v46);
            v50 = InstallNewProvider(
                    (_DWORD)v73,
                    (_DWORD)v8,
                    Size[1],
                    0,
                    (__int64)v25,
                    (__int64)v83,
                    0,
                    (__int64)v10,
                    v47,
                    v46,
                    (__int64)P,
                    v60);
            v51 = v50;
            if ( v50 )
            {
              LogErrorWithProvider(v50, L"Failed to install dynamic provider; skipping", v25);
              if ( (xmmword_180063D60 & 2) != 0 )
                WPP_SF_Sd(v52, 15, (unsigned int)WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, (_DWORD)v25, v51);
              v7 = 0;
            }
            else
            {
              LogMsgWithProvider(L"Successfully installed dynamic provider; adding it to updated list", v25);
              v41 = AppendStringToMultiSz(&v69, v25);
              v7 = v41;
              if ( v41 )
              {
                v42 = L"Failed to add to updated list";
                goto LABEL_72;
              }
            }
            v64 = 1;
          }
          RtlFreeHeap(SockPrivateHeap, 0, v10);
          v10 = 0;
          Buf2 = 0;
          if ( Buf1 )
          {
            RtlFreeHeap(SockPrivateHeap, 0, Buf1);
            v26 = 0;
            v14 = 0;
            Buf1 = 0;
          }
          else
          {
            v14 = 0;
            v26 = 0;
          }
          LogMsgWithProvider(L"Successfully updated dynamic provider", v25);
          v5 = v77;
        }
        else
        {
          if ( v26 )
          {
            RtlFreeHeap(SockPrivateHeap, 0, v26);
            v26 = 0;
            v14 = 0;
            Buf1 = 0;
          }
          else
          {
            v14 = Buf1;
            v26 = 0;
          }
          LogMsgWithProvider(L"Provider returned no protocol entries", v25);
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_S(1025, 14, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, v25);
        }
      }
LABEL_113:
      v53 = -1;
      do
        ++v53;
      while ( v25[v53] );
      v25 += v53 + 1;
    }
  }
  v19 = L"OpenSetupMigrationRoot failed";
LABEL_13:
  LogError(NewProviderList, v19);
  v8 = v70;
LABEL_5:
  v14 = Buf1;
LABEL_6:
  v15 = v61;
LABEL_122:
  v31 = v60;
LABEL_123:
  if ( LODWORD(P[0]) == 1297109836 )
  {
    v56 = P[1];
    if ( P[1] )
    {
      if ( HIDWORD(v79[0]) )
        MwcUpdateLSPChains(0, P[1], v79[0], v13, v31);
      RtlFreeHeap(SockPrivateHeap, 0, v56);
    }
    if ( ((*(_DWORD *)(v31 + 4) - 2) & 0xFFFFFFFD) == 0 )
    {
      v57 = v79[1];
      if ( v79[1] )
      {
        if ( HIDWORD(v80) )
        {
          LOBYTE(v12) = 1;
          MwcUpdateLSPChains(v12, v79[1], v80, v13, v31);
        }
        RtlFreeHeap(SockPrivateHeap, 0, v57);
      }
    }
  }
  if ( *(_QWORD *)&Size[1] )
    RegCloseKey(*(HKEY *)&Size[1]);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v15 )
    RegCloseKey(v15);
  if ( v8 )
    RegCloseKey(v8);
  if ( v73 )
    RegCloseKey(v73);
  if ( v71 )
    RtlFreeHeap(SockPrivateHeap, 0, v71);
  if ( v74 )
    RtlFreeHeap(SockPrivateHeap, 0, v74);
  if ( v69 )
    RtlFreeHeap(SockPrivateHeap, 0, v69);
  if ( v75 )
    RtlFreeHeap(SockPrivateHeap, 0, v75);
  if ( v10 )
    RtlFreeHeap(SockPrivateHeap, 0, v10);
  if ( v14 )
    RtlFreeHeap(SockPrivateHeap, 0, v14);
  if ( v76 )
    RtlFreeHeap(SockPrivateHeap, 0, v76);
  if ( v7 )
    LogError(v7, L"Exiting MigrateWinsockConfiguration with error");
  else
    LogMsg(L"Exiting MigrateWinsockConfiguration successfully");
  qword_180063FD0 = 0;
  *v81 = v64;
  return v7;
}

```

## disassembly

```asm
0x1800328c0  push    rbp
0x1800328c2  push    rbx
0x1800328c3  push    rsi
0x1800328c4  push    rdi
0x1800328c5  push    r12
0x1800328c7  push    r13
0x1800328c9  push    r14
0x1800328cb  push    r15
0x1800328cd  lea     rbp, [rsp-258h]
0x1800328d5  sub     rsp, 358h
0x1800328dc  mov     rax, cs:__security_cookie
0x1800328e3  xor     rax, rsp
0x1800328e6  mov     [rbp+290h+var_50], rax
0x1800328ed  mov     [rsp+390h+var_318], r8d
0x1800328f2  mov     r15, rdx
0x1800328f5  mov     [rbp+290h+var_2B0], rdx
0x1800328f9  mov     r8d, 208h; Size
0x1800328ff  mov     [rbp+290h+var_280], rcx
0x180032903  xor     edx, edx; Val
0x180032905  lea     rcx, [rbp+290h+var_260]; void *
0x180032909  mov     [rsp+390h+var_328], r9
0x18003290e  mov     rsi, r9
0x180032911  call    memset_0
0x180032916  xor     ecx, ecx
0x180032918  xorps   xmm0, xmm0
0x18003291b  xor     eax, eax
0x18003291d  mov     [rbp+290h+var_2B8], rcx
0x180032921  mov     [rbp+290h+var_2F4], ecx
0x180032924  mov     [rbp+290h+var_288], rax
0x180032928  mov     [rbp+290h+var_2F8], ecx
0x18003292b  movups  xmmword ptr [rbp+290h+P], xmm0
0x18003292f  movups  xmmword ptr [rbp+290h+var_298], xmm0
0x180032933  movups  [rbp+290h+var_278], xmm0
0x180032937  test    rsi, rsi
0x18003293a  jnz     short loc_180032952
0x18003293c  lea     ebx, [rsi+57h]
0x18003293f  mov     ecx, ebx
0x180032941  lea     rdx, aTargetInformat; "Target information must be specified"
0x180032948  call    LogError
0x18003294d  jmp     loc_1800334D4
0x180032952  mov     rax, [rbp+290h+arg_20]
0x180032959  lea     rdx, [rbp+290h+var_2F4]
0x18003295d  mov     cs:qword_180063FD0, rax
0x180032964  mov     r13, rcx
0x180032967  mov     rax, [rsi+8]
0x18003296b  mov     r12, rcx
0x18003296e  mov     qword ptr [rbp+290h+Size+4], rcx
0x180032972  mov     r8, rsi
0x180032975  mov     [rbp+290h+hKey], rcx
0x180032979  mov     [rsp+390h+var_320], rcx
0x18003297e  mov     [rbp+290h+var_2E8], rcx
0x180032982  mov     [rbp+290h+var_2D0], rcx
0x180032986  mov     [rbp+290h+var_2E0], rcx
0x18003298a  mov     [rbp+290h+var_2C8], rcx
0x18003298e  mov     [rbp+290h+var_2F0], rcx
0x180032992  mov     [rbp+290h+var_2C0], rcx
0x180032996  mov     [rbp+290h+Buf2], rcx
0x18003299a  mov     [rsp+390h+Buf1], rcx
0x18003299f  mov     dword ptr [rbp+290h+Size], ecx
0x1800329a2  mov     [rsp+390h+var_314], ecx
0x1800329a6  mov     [rbp+290h+var_310], ecx
0x1800329a9  lea     rcx, [rbp+290h+var_2B8]
0x1800329ad  mov     cs:DefaultTranslator, rax
0x1800329b4  call    ReadWs2Catalog
0x1800329b9  mov     rdx, rsi
0x1800329bc  lea     rcx, [rbp+290h+Size+4]; phkResult
0x1800329c0  call    OpenServicesRoot
0x1800329c5  xor     r14d, r14d
0x1800329c8  mov     ebx, eax
0x1800329ca  test    eax, eax
0x1800329cc  jz      short loc_1800329EB
0x1800329ce  lea     rdx, aOpenservicesro; "OpenServicesRoot failed"
0x1800329d5  mov     ecx, eax
0x1800329d7  call    LogError
0x1800329dc  mov     rsi, [rsp+390h+Buf1]
0x1800329e1  mov     r15, [rsp+390h+var_320]
0x1800329e6  jmp     loc_1800332CB
0x1800329eb  mov     rcx, qword ptr [rbp+290h+Size+4]; hKey
0x1800329ef  lea     rdx, [rbp+290h+hKey]; phkResult
0x1800329f3  call    OpenWinsockRoot
0x1800329f8  mov     edi, eax
0x1800329fa  test    eax, eax
0x1800329fc  jz      short loc_180032A17
0x1800329fe  lea     rdx, aOpenwinsockroo; "OpenWinsockRoot failed"
0x180032a05  mov     ecx, eax
0x180032a07  call    LogError
0x180032a0c  cmp     edi, 2
0x180032a0f  mov     ebx, r14d
0x180032a12  cmovnz  ebx, edi
0x180032a15  jmp     short loc_1800329DC
0x180032a17  mov     rcx, [rbp+290h+hKey]; hKey
0x180032a1b  lea     rax, [rbp+290h+P]
0x180032a1f  mov     [rsp+390h+var_368], rsi; __int64
0x180032a24  lea     r9, [rbp+290h+var_2D0]
0x180032a28  lea     r8, [rbp+290h+var_2E8]
0x180032a2c  mov     [rsp+390h+var_370], rax; __int64
0x180032a31  lea     rdx, [rsp+390h+var_320]
0x180032a36  call    OpenSetupMigrationRoot
0x180032a3b  mov     ebx, eax
0x180032a3d  test    eax, eax
0x180032a3f  jz      short loc_180032A55
0x180032a41  lea     rdx, aOpensetupmigra; "OpenSetupMigrationRoot failed"
0x180032a48  mov     ecx, eax
0x180032a4a  call    LogError
0x180032a4f  mov     r13, [rbp+290h+var_2E8]
0x180032a53  jmp     short loc_1800329DC
0x180032a55  mov     rcx, [rbp+290h+hKey]; hKey
0x180032a59  lea     rdx, [rbp+290h+var_2C8]
0x180032a5d  call    ReadNewProviderList
0x180032a62  mov     ebx, eax
0x180032a64  test    eax, eax
0x180032a66  jz      short loc_180032A71
0x180032a68  lea     rdx, aReadnewprovide; "ReadNewProviderList failed"
0x180032a6f  jmp     short loc_180032A48
0x180032a71  mov     rdi, [rsp+390h+var_320]
0x180032a76  lea     r8, [rbp+290h+var_2E0]
0x180032a7a  mov     rcx, rdi; hKey
0x180032a7d  lea     rdx, aProviderList; "Provider List"
0x180032a84  call    ReadMultiSz
0x180032a89  mov     ebx, eax
0x180032a8b  test    eax, eax
0x180032a8d  jz      short loc_180032A98
0x180032a8f  lea     rdx, aReadoldprovide; "ReadOldProviderList failed"
0x180032a96  jmp     short loc_180032A48
0x180032a98  lea     r8, [rbp+290h+var_2C0]
0x180032a9c  mov     rcx, rdi; hKey
0x180032a9f  lea     rdx, aKnownStaticPro; "Known Static Providers"
0x180032aa6  call    ReadMultiSz
0x180032aab  mov     ebx, eax
0x180032aad  test    eax, eax
0x180032aaf  jz      short loc_180032ABA
0x180032ab1  lea     rdx, aReadknownstati; "ReadKnownStaticProviderList failed"
0x180032ab8  jmp     short loc_180032A48
0x180032aba  lea     rcx, aEnumeratingOld; "Enumerating old providers for potential"...
0x180032ac1  call    LogMsg
0x180032ac6  mov     rdi, [rbp+290h+var_2E0]
0x180032aca  xor     ecx, ecx
0x180032acc  mov     r13, [rbp+290h+var_2E8]
0x180032ad0  mov     r14, [rbp+290h+var_2C8]
0x180032ad4  cmp     [rdi], cx
0x180032ad7  jz      loc_180032B84
0x180032add  mov     rdx, rdi
0x180032ae0  mov     rcx, r14
0x180032ae3  call    IsStringInMultiSz
0x180032ae8  test    eax, eax
0x180032aea  jnz     short loc_180032B43
0x180032aec  test    r15, r15
0x180032aef  jz      short loc_180032B0C
0x180032af1  mov     r8d, [rsp+390h+var_318]
0x180032af6  lea     ecx, [rax+1]
0x180032af9  mov     rax, r15
0x180032afc  mov     rdx, rdi
0x180032aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b04  test    eax, eax
0x180032b06  jz      loc_1800329DC
0x180032b0c  mov     rdx, rdi
0x180032b0f  lea     rcx, aRemovingOldPro; "Removing old provider"
0x180032b16  call    LogMsgWithProvider
0x180032b1b  mov     r9, rsi
0x180032b1e  lea     r8, [rbp+290h+P]
0x180032b22  mov     rdx, rdi
0x180032b25  mov     rcx, r13
0x180032b28  call    RemoveProviderByName
0x180032b2d  mov     ebx, eax
0x180032b2f  test    eax, eax
0x180032b31  jnz     short loc_180032B6E
0x180032b33  mov     [rbp+290h+var_310], 1
0x180032b3a  lea     rcx, aSuccessfullyRe; "Successfully removed old provider"
0x180032b41  jmp     short loc_180032B4A
0x180032b43  lea     rcx, aKeepingOldProv; "Keeping old provider"
0x180032b4a  mov     rdx, rdi
0x180032b4d  call    LogMsgWithProvider
0x180032b52  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032b56  xor     ecx, ecx
0x180032b58  inc     rax
0x180032b5b  cmp     [rdi+rax*2], cx
0x180032b5f  jnz     short loc_180032B58
0x180032b61  lea     rdi, [rdi+rax*2]
0x180032b65  add     rdi, 2
0x180032b69  jmp     loc_180032AD4
0x180032b6e  mov     r8, rdi
0x180032b71  lea     rdx, aFailedToRemove_0; "Failed to remove old provider"
0x180032b78  mov     ecx, eax
0x180032b7a  call    LogErrorWithProvider
0x180032b7f  jmp     loc_1800329DC
0x180032b84  lea     rcx, aDoneEnumeratin; "Done enumerating old providers"
0x180032b8b  call    LogMsg
0x180032b90  lea     rcx, aEnumeratingNew; "Enumerating new providers for updates"
0x180032b97  call    LogMsg
0x180032b9c  mov     rdi, r14
0x180032b9f  xor     r14d, r14d
0x180032ba2  cmp     [rdi], r14w
0x180032ba6  jz      loc_180032DD3
0x180032bac  mov     rcx, [rbp+290h+var_2E0]
0x180032bb0  mov     rdx, rdi
0x180032bb3  call    IsStringInMultiSz
0x180032bb8  test    eax, eax
0x180032bba  jnz     loc_180032D7E
0x180032bc0  test    r15, r15
0x180032bc3  jz      short loc_180032BDF
0x180032bc5  mov     r8d, [rsp+390h+var_318]
0x180032bca  mov     rdx, rdi
0x180032bcd  xor     ecx, ecx
0x180032bcf  mov     rax, r15
0x180032bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bd7  test    eax, eax
0x180032bd9  jz      loc_1800329DC
0x180032bdf  mov     rcx, qword ptr [rbp+290h+Size+4]
0x180032be3  mov     rdx, rdi
0x180032be6  call    IsProviderOfflineCapable
0x180032beb  mov     rdx, rdi
0x180032bee  lea     rcx, aANewProviderHa; "A new provider has been detected and wi"...
0x180032bf5  mov     esi, eax
0x180032bf7  call    LogMsgWithProvider
0x180032bfc  lea     rax, aThisNewProvide; "This new provider is not offline capabl"...
0x180032c03  test    esi, esi
0x180032c05  lea     rcx, aThisNewProvide_0; "This new provider is offline capable"
0x180032c0c  mov     rdx, rdi
0x180032c0f  cmovz   rcx, rax
0x180032c13  call    LogMsgWithProvider
0x180032c18  test    esi, esi
0x180032c1a  jnz     short loc_180032C8E
0x180032c1c  mov     rcx, qword ptr [rbp+290h+Size+4]
0x180032c20  lea     rax, [rsp+390h+var_314]
0x180032c25  mov     [rsp+390h+var_368], rax
0x180032c2a  lea     r9, [rbp+290h+Buf2]
0x180032c2e  lea     rax, [rbp+290h+Size]
0x180032c32  mov     rdx, rdi
0x180032c35  lea     r8, [rbp+290h+var_260]
0x180032c39  mov     [rsp+390h+var_370], rax
0x180032c3e  call    ReadProtocolDataFromProvider
0x180032c43  mov     ebx, eax
0x180032c45  test    eax, eax
0x180032c47  jnz     loc_180032D99
0x180032c4d  mov     r12, [rbp+290h+Buf2]
0x180032c51  test    r12, r12
0x180032c54  jnz     short loc_180032C8E
0x180032c56  mov     rdx, rdi
0x180032c59  lea     rcx, aNonOfflineCapa; "Non-offline-capable provider returned z"...
0x180032c60  call    LogMsgWithProvider
0x180032c65  test    byte ptr cs:xmmword_180063D60, 2
0x180032c6c  jz      loc_180032D7E
0x180032c72  lea     edx, [rsi+0Ah]
0x180032c75  mov     ecx, 401h
0x180032c7a  mov     r9, rdi
0x180032c7d  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180032c84  call    WPP_SF_S
0x180032c89  jmp     loc_180032D7E
0x180032c8e  mov     rcx, [rbp+290h+var_2C0]
0x180032c92  mov     rdx, rdi
0x180032c95  call    IsStringInMultiSz
0x180032c9a  mov     r14, [rsp+390h+var_328]
0x180032c9f  lea     rcx, [rbp+290h+P]
0x180032ca3  mov     r8, qword ptr [rbp+290h+Size+4]
0x180032ca7  mov     r9d, esi
0x180032caa  mov     [rsp+390h+var_338], r14
0x180032caf  mov     rdx, r13
0x180032cb2  mov     [rsp+390h+var_340], rcx
0x180032cb7  mov     ecx, [rsp+390h+var_314]
0x180032cbb  mov     [rsp+390h+var_348], ecx
0x180032cbf  mov     ecx, dword ptr [rbp+290h+Size]
0x180032cc2  mov     [rsp+390h+var_350], ecx
0x180032cc6  mov     rcx, [rbp+290h+var_2D0]
0x180032cca  mov     [rsp+390h+var_358], r12
0x180032ccf  mov     [rsp+390h+var_360], eax
0x180032cd3  lea     rax, [rbp+290h+var_260]
0x180032cd7  mov     [rsp+390h+var_368], rax
0x180032cdc  mov     [rsp+390h+var_370], rdi
0x180032ce1  call    InstallNewProvider
0x180032ce6  mov     ebx, eax
0x180032ce8  test    eax, eax
0x180032cea  jnz     short loc_180032D16
0x180032cec  mov     rdx, rdi
0x180032cef  lea     rcx, aSuccessfullyIn; "Successfully installed new provider; ad"...
0x180032cf6  call    LogMsgWithProvider
0x180032cfb  mov     rdx, rdi
0x180032cfe  lea     rcx, [rbp+290h+var_2F0]
0x180032d02  call    AppendStringToMultiSz
0x180032d07  mov     ebx, eax
0x180032d09  test    eax, eax
0x180032d0b  jnz     loc_180032DB3
0x180032d11  xor     r14d, r14d
0x180032d14  jmp     short loc_180032D4E
0x180032d16  mov     r8, rdi
0x180032d19  lea     rdx, aCannotInstallP; "Cannot install provider; skipping"
0x180032d20  mov     ecx, ebx
0x180032d22  call    LogErrorWithProvider
0x180032d27  test    byte ptr cs:xmmword_180063D60, 2
0x180032d2e  jz      short loc_180032D48
0x180032d30  mov     edx, 0Bh
0x180032d35  mov     dword ptr [rsp+390h+var_370], ebx
0x180032d39  mov     r9, rdi
0x180032d3c  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180032d43  call    WPP_SF_Sd
0x180032d48  xor     r14d, r14d
0x180032d4b  mov     ebx, r14d
0x180032d4e  test    r12, r12
0x180032d51  jz      short loc_180032D77
0x180032d53  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180032d5a  mov     r8, r12; P
  ... truncated ...
```
