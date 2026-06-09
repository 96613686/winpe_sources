# FwProfileMgrInitialize

- ea: `0x180089520`
- end: `0x18008a203`
- name: `FwProfileMgrInitialize`
- size: `3299`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001518`
- `0x18000177c`
- `0x180001820`
- `0x180001c8c`
- `0x18000af3c`
- `0x180029b48`
- `0x18004d774`
- `0x180059384`
- `0x18005a47c`
- `0x18005cf9c`
- `0x18005ef14`
- `0x1800670c0`
- `0x18006f520`
- `0x180081ff4`
- `0x180083a70`
- `0x180083abc`
- `0x180084d70`
- `0x180084f10`
- `0x1800873dc`
- `0x180089520`
- `0x18008a260`
- `0x1800abfbc`
- `0x1800ac5dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008966e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800896ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008979e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008982f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008966e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800896ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008979e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008982f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008965c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008978c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008965c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008978c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800896ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008981d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800896ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008981d`
- `fwbase!FwRegNotifyCreate` at `0x180089b3a`
- `fwbase!FwRegNotifyCreate` at `0x180089b3a`
- `fwbase!FwRegQueryDWord` at `0x1800899ce`
- `fwbase!FwRegQueryDWord` at `0x180089a7c`
- `fwbase!FwRegQueryDWord` at `0x1800899ce`
- `fwbase!FwRegQueryDWord` at `0x180089a7c`
- `fwbase!FwReportReturnError` at `0x18008a1ad`
- `fwbase!FwReportReturnError` at `0x18008a1ad`
- `FWPolicyIOMgr!LoadGPExtensionDll` at `0x180089595`
- `FWPolicyIOMgr!LoadGPExtensionDll` at `0x180089595`

## string_xrefs

- `0x18008a15b`: `mpssvc.dll`
- `0x18008964f`: `fwpuclnt.dll`
- `0x18008977f`: `fwpuclnt.dll`
- `0x1800896e3`: `FwpmFilterCreatePreciseEnumHandle`
- `0x180089b46`: `FwRegNotifyCreate`
- `0x1800899c7`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x180089a75`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x180089b14`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy\RestrictedServices\Configurable`

## pseudocode

```c
__int64 FwProfileMgrInitialize()
{
  int *v0; // r14
  __int64 v1; // rbx
  unsigned int v2; // esi
  const char *v3; // rdi
  int GPExtensionDll; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  signed int inserted; // ebx
  unsigned __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v11; // rdx
  HMODULE Library; // rax
  signed int LastError; // eax
  signed int v14; // eax
  HMODULE v15; // rax
  signed int v16; // eax
  signed int v17; // eax
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // r8
  int v25; // edx
  int v26; // ecx
  unsigned int i; // edi
  int v28; // eax
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // r8
  int v33; // [rsp+50h] [rbp-29h] BYREF
  signed int v34; // [rsp+54h] [rbp-25h] BYREF
  int v35; // [rsp+58h] [rbp-21h] BYREF
  unsigned int v36; // [rsp+5Ch] [rbp-1Dh] BYREF
  int v37; // [rsp+60h] [rbp-19h] BYREF
  __int64 v38; // [rsp+68h] [rbp-11h] BYREF
  int v39; // [rsp+70h] [rbp-9h] BYREF
  signed int v40; // [rsp+74h] [rbp-5h] BYREF
  signed int v41; // [rsp+78h] [rbp-1h] BYREF

  v0 = &dword_180126458;
  v1 = 0;
  v41 = 0;
  v40 = 0;
  v2 = 0;
  v39 = 0;
  v3 = 0;
  if ( !dword_180126458 )
    v0 = 0;
  do
    FwInitializeStore((struct _tag_FW_STORE *)&qword_18012E2B8[121 * v1++]);
  while ( v1 != 13 );
  GPExtensionDll = LoadGPExtensionDll();
  inserted = GPExtensionDll;
  if ( !GPExtensionDll )
  {
LABEL_15:
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl) )
    {
      Library = LoadLibraryExW(L"fwpuclnt.dll", 0, 0x800u);
      hFwpuclntPrivate = Library;
      if ( !Library )
      {
        LastError = GetLastError();
        inserted = LastError;
        if ( LastError > 0 )
          inserted = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)dword_1801263B0 > 5 )
        {
          v34 = inserted;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (int)&dword_1801263B0,
            (int)byte_18010ECB5,
            v8,
            v9,
            (__int64)&v34);
        }
        if ( inserted < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_147;
          v11 = 25;
          goto LABEL_14;
        }
        Library = hFwpuclntPrivate;
      }
      pFuncFwpmFilterCreateEnumHandle = (unsigned int (*)(void *, struct FWPM_FILTER_ENUM_TEMPLATE0_ *, void **))GetProcAddress(Library, "FwpmFilterCreatePreciseEnumHandle");
      if ( !pFuncFwpmFilterCreateEnumHandle )
      {
        v14 = GetLastError();
        inserted = v14;
        if ( v14 > 0 )
          inserted = (unsigned __int16)v14 | 0x80070000;
        if ( (unsigned int)dword_1801263B0 > 5 )
        {
          v34 = inserted;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (int)&dword_1801263B0,
            (int)&unk_18010F4D0,
            v8,
            v9,
            (__int64)&v34);
        }
        if ( inserted < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_147;
          v11 = 26;
          goto LABEL_14;
        }
      }
    }
    v15 = hFwpuclntPrivate;
    if ( !hFwpuclntPrivate )
    {
      v15 = LoadLibraryExW(L"fwpuclnt.dll", 0, 0x800u);
      hFwpuclntPrivate = v15;
      if ( !v15 )
      {
        v16 = GetLastError();
        inserted = v16;
        if ( v16 > 0 )
          inserted = (unsigned __int16)v16 | 0x80070000;
        if ( (unsigned int)dword_1801263B0 > 5 )
        {
          v33 = inserted;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (int)&dword_1801263B0,
            (int)byte_18010F395,
            v8,
            v9,
            (__int64)&v33);
        }
        if ( inserted < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_147;
          v11 = 27;
          goto LABEL_14;
        }
        v15 = hFwpuclntPrivate;
      }
    }
    pFuncFwpmSetEngineOption1 = (unsigned int (__high *)(void *, enum FWPI_ENGINE_OPTION_, const struct FWP_VALUE0_ *))GetProcAddress(v15, "FwpmEngineSetOption1");
    if ( !pFuncFwpmSetEngineOption1 )
    {
      v17 = GetLastError();
      inserted = v17;
      if ( v17 > 0 )
        inserted = (unsigned __int16)v17 | 0x80070000;
      if ( (unsigned int)dword_1801263B0 > 5 )
      {
        v33 = inserted;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (int)&dword_1801263B0,
          (int)&unk_18010EA60,
          v8,
          v9,
          (__int64)&v33);
      }
      if ( inserted < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_147;
        v11 = 28;
        goto LABEL_14;
      }
    }
    dword_180129110 = 480;
    qword_1801315E8 = (__int64)&g_DefaultAuthSetPhase1;
    dword_180129780 = 1;
    qword_1801315F0 = (__int64)&g_DefaultAuthSetPhase2;
    v2 = 2;
    dword_180129104 = 2;
    qword_180131600 = (__int64)&g_DefaultCryptoSetPhase1;
    qword_180131608 = (struct _tag_FW_CRYPTO_SET *)&g_DefaultCryptoSetPhase2;
    qword_180129108 = (__int64)&g_DefaultCryptoSuitesPhase1;
    qword_180129788 = (__int64)&g_DefaultCryptoSuitesPhase2;
    dword_180129784 = 4;
    inserted = FwHardCodedSpecialRulesInit((struct _tag_FW_STORE *)qword_18012E2B8);
    if ( inserted < 0 )
    {
      v3 = "FwHardCodedSpecialRulesInit";
      v2 = 1;
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_147;
      v11 = 29;
      goto LABEL_14;
    }
    inserted = FwInsertHardcodedSetsToStore((struct _tag_FW_STORE *)qword_18012F5A0);
    if ( inserted < 0 )
    {
      v3 = "FwInsertHardcodedSetsToStore";
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_147;
      v11 = 30;
      goto LABEL_14;
    }
    dword_18012E2B0 = 0;
    v18 = FwRegQueryDWord(
            -2147483646,
            L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy",
            L"DiffRule",
            &v40,
            &v39);
    if ( v18 < 0 && (unsigned int)dword_1801263B0 > 5 )
    {
      v33 = v18;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (int)&dword_1801263B0,
        (int)word_18010F1EA,
        v19,
        v20,
        (__int64)&v33);
    }
    if ( v39 )
      dword_18012E2B0 = v40 != 0;
    if ( (unsigned int)dword_1801263B0 > 5 )
    {
      v33 = dword_18012E2B0;
      v34 = v40;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (int)&dword_1801263B0,
        (int)&word_18010EFAE,
        v19,
        v20,
        (__int64)&v34,
        (__int64)&v33);
    }
    dword_18012E2AC = 1;
    v21 = FwRegQueryDWord(
            -2147483646,
            L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy",
            L"IntfQuarantineEnabled",
            &v41,
            &v39);
    if ( v21 < 0 && (unsigned int)dword_1801263B0 > 5 )
    {
      v33 = v21;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (int)&dword_1801263B0,
        (int)&byte_18010F017,
        v22,
        v23,
        (__int64)&v33);
    }
    if ( v39 )
      dword_18012E2AC = v41 != 0;
    if ( (unsigned int)dword_1801263B0 > 5 )
    {
      v33 = dword_18012E2AC;
      v34 = v41;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (int)&dword_1801263B0,
        (int)&byte_18010ED77,
        v22,
        v23,
        (__int64)&v34,
        (__int64)&v33);
    }
    inserted = FwRegNotifyCreate(
                 -2147483646,
                 L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy\\RestrictedServices\\Configurable",
                 1,
                 5,
                 50,
                 FwProfileMgrOnConfigurableWSHChange,
                 0,
                 gFwProfileMgr);
    if ( inserted < 0 )
    {
      v3 = "FwRegNotifyCreate";
      v2 = 3;
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_147;
      v11 = 31;
      goto LABEL_14;
    }
    FwInitializeHistogramTelemetry();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetImpl'::`2'::impl) )
    {
      inserted = FwLoadStore(3, qword_18012EE10, 0);
      if ( inserted < 0 )
      {
        v3 = "FwLoadStore(FW_STORE_TYPE_WSH_STATIC)";
        v2 = 4;
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_147;
        v11 = 32;
        goto LABEL_14;
      }
      dword_18012E2A8 = 0;
      v2 = 8;
      inserted = FwLoadStore(8, qword_1801300F8, 0);
      if ( inserted < 0 )
      {
        v3 = "FwLoadStore(FW_STORE_TYPE_IF_ISO)";
        v2 = 5;
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_147;
        v11 = 33;
        goto LABEL_14;
      }
      inserted = FwLoadStore(10, qword_180130888, 0);
      if ( inserted < 0 )
      {
        v3 = "FwLoadStore(FW_STORE_TYPE_APP_ISO)";
        v2 = 6;
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_147;
        v11 = 34;
        goto LABEL_14;
      }
      inserted = FwLoadStore(11, qword_180130C50, 0);
      if ( inserted < 0 )
      {
        v3 = "FwLoadStore(FW_STORE_TYPE_MDM)";
        v2 = 7;
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_147;
        v11 = 35;
        goto LABEL_14;
      }
      inserted = FwLoadStore(12, qword_180131018, 0);
      if ( inserted < 0 )
      {
        v3 = "FwLoadStore(FW_STORE_TYPE_TENANT_RESTRICTIONS)";
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_147;
        v11 = 36;
        goto LABEL_14;
      }
    }
    else
    {
      LOBYTE(v24) = 1;
      inserted = FwLoadStore(3, qword_18012EE10, v24);
      if ( inserted < 0 )
      {
        v3 = "FwLoadStore(FW_STORE_TYPE_WSH_STATIC)";
        v2 = 4;
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_147;
        v11 = 37;
        goto LABEL_14;
      }
      v2 = 8;
      dword_18012E2A8 = 0;
      LOBYTE(v8) = 1;
      inserted = FwLoadStore(8, qword_1801300F8, v8);
      if ( inserted < 0 )
      {
        v3 = "FwLoadStore(FW_STORE_TYPE_IF_ISO)";
        v2 = 5;
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_147;
        v11 = 38;
        goto LABEL_14;
      }
      LOBYTE(v8) = 1;
      inserted = FwLoadStore(10, qword_180130888, v8);
      if ( inserted < 0 )
      {
        v3 = "FwLoadStore(FW_STORE_TYPE_APP_ISO)";
        v2 = 6;
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_147;
        v11 = 39;
        goto LABEL_14;
      }
      LOBYTE(v8) = 1;
      inserted = FwLoadStore(11, qword_180130C50, v8);
      if ( inserted < 0 )
      {
        v3 = "FwLoadStore(FW_STORE_TYPE_MDM)";
        v2 = 7;
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_147;
        v11 = 40;
        goto LABEL_14;
      }
      LOBYTE(v8) = 1;
      inserted = FwLoadStore(12, qword_180131018, v8);
      if ( inserted < 0 )
      {
        v3 = "FwLoadStore(FW_STORE_TYPE_TENANT_RESTRICTIONS)";
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_147;
        v11 = 41;
        goto LABEL_14;
      }
    }
    inserted = FwProfileMgrWSHOnChange(v26, v25, 1);
    if ( inserted >= 0 )
    {
      v2 = 10;
      v35 = 10;
      v3 = "FwProfileMgrOnPolicyChange";
      inserted = FwProfileMgrOnPolicyChange(1, 1, 1, 1, 0);
      if ( inserted >= 0 )
      {
        FwAuditProfileMgrStartup();
        FwUpdateConsecPresenceDataPoint();
        inserted = FwPerfMonInitialize();
        if ( inserted >= 0 )
        {
          if ( v0 )
          {
            for ( i = 0; i < 0xD; ++i )
            {
              if ( i <= 0xB )
              {
                v28 = 2148;
                if ( _bittest(&v28, i) )
                {
                  v8 = 968LL * i;
                  v9 = HIDWORD(gFwProfileMgr[v8 / 8 + 35]);
                  if ( (unsigned int)v9 >= 0x1F4
                    && (unsigned int)*v0 > 5
                    && (unsigned __int8)tlgKeywordOn(v0, 0x400000000000LL) )
                  {
                    v33 = HIDWORD(gFwProfileMgr[v8 / 8 + 122]);
                    v34 = gFwProfileMgr[v8 / 8 + 123];
                    v37 = v9;
                    v36 = i;
                    v38 = 0x1000000;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                      (int)v0,
                      (int)&dword_18010EF3C,
                      v8,
                      v9,
                      (__int64)&v38,
                      (__int64)&v36,
                      (__int64)&v37,
                      (__int64)&v34,
                      (__int64)&v33);
                  }
                }
              }
            }
            v2 = v35;
          }
          v3 = 0;
          goto LABEL_147;
        }
        if ( (unsigned int)dword_1801263B0 > 5 )
        {
          v33 = inserted;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (int)&dword_1801263B0,
            (int)byte_18010F53D,
            v8,
            v9,
            (__int64)&v33);
        }
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        {
LABEL_147:
          if ( (unsigned int)dword_1801263B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801263B0, 0x4000000000000LL) )
          {
            v35 = inserted;
            v38 = (__int64)v3;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (int)&dword_1801263B0,
              (int)&word_18010EE06,
              v8,
              v9,
              (const char **)&v38,
              (__int64)&v35);
          }
          if ( inserted >= 0 )
          {
            if ( (unsigned int)dword_1801263B0 > 5 )
            {
              v35 = inserted;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (int)&dword_1801263B0,
                (int)&unk_18010ED40,
                v8,
                v9,
                (__int64)&v35);
            }
          }
          else
          {
            if ( !bFwProfileMgrInitFail )
            {
              if ( (unsigned int)dword_180126458 >= 6
                && (unsigned __int8)tlgKeywordOn(&dword_180126458, 0x400000000000LL) )
              {
                v38 = 0x1000000;
                v35 = v2;
                v36 = inserted;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                  (int)&dword_180126458,
                  (int)byte_18010F589,
                  v29,
                  v30,
                  (__int64)&v36,
                  (__int64)&v35,
                  (__int64)&v38);
              }
              bFwProfileMgrInitFail = 1;
              MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v2, 0);
            }
            if ( (unsigned int)dword_1801263B0 > 5 )
            {
              v35 = inserted;
              v36 = v2;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (int)&dword_1801263B0,
                (int)word_18010F352,
                v8,
                v9,
                (__int64)&v36,
                (__int64)&v35);
            }
            FwProfileMgrShutdown();
            return (unsigned int)FwReportReturnError("FwProfileMgrInitialize", (unsigned int)inserted, v31);
          }
          return (unsigned int)inserted;
        }
        v11 = 44;
      }
      else
      {
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_147;
        v11 = 43;
      }
    }
    else
    {
      v3 = "FwProfileMgrWSHOnChange";
      v2 = 9;
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_147;
      v11 = 42;
    }
LABEL_14:
    WPP_SF_d(*(_QWORD *)(v10 + 16), v11, WPP_e2321870bb8f37110138dfc56d389809_Traceguids, (unsigned int)inserted);
    goto LABEL_147;
  }
  if ( GPExtensionDll > 0 )
    inserted = (unsigned __int16)GPExtensionDll | 0x80070000;
  if ( (unsigned int)dword_1801263B0 > 5 )
  {
    v37 = inserted;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (int)&dword_1801263B0,
      (int)&byte_18010F307,
      v5,
      v6,
      (__int64)&v37);
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl) )
  {
    if ( inserted < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_147;
      v11 = 24;
      goto LABEL_14;
    }
    goto LABEL_15;
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180089520  push    rbp
0x180089522  push    rbx
0x180089523  push    rsi
0x180089524  push    rdi
0x180089525  push    r12
0x180089527  push    r13
0x180089529  push    r14
0x18008952b  push    r15
0x18008952d  lea     rbp, [rsp-1Fh]
0x180089532  sub     rsp, 98h
0x180089539  mov     rax, cs:__security_cookie
0x180089540  xor     rax, rsp
0x180089543  mov     [rbp+57h+var_50], rax
0x180089547  mov     ecx, cs:dword_180126458
0x18008954d  lea     r14, dword_180126458
0x180089554  xor     r15d, r15d
0x180089557  mov     ebx, r15d
0x18008955a  mov     [rbp+57h+var_58], r15d
0x18008955e  test    ecx, ecx
0x180089560  mov     [rbp+57h+var_5C], r15d
0x180089564  mov     esi, r15d
0x180089567  mov     [rbp+57h+var_60], r15d
0x18008956b  mov     edi, r15d
0x18008956e  cmovz   r14, r15
0x180089572  lea     r12d, [rbx+1]
0x180089576  lea     r15, qword_18012E2B8
0x18008957d  imul    rcx, rbx, 3C8h
0x180089584  add     rcx, r15; struct _tag_FW_STORE *
0x180089587  call    ?FwInitializeStore@@YAXPEAU_tag_FW_STORE@@@Z; FwInitializeStore(_tag_FW_STORE *)
0x18008958c  add     rbx, r12
0x18008958f  cmp     rbx, 0Dh
0x180089593  jnz     short loc_18008957D
0x180089595  call    cs:__imp_LoadGPExtensionDll
0x18008959b  xor     r15d, r15d
0x18008959e  mov     r13d, 5
0x1800895a4  mov     ebx, eax
0x1800895a6  test    eax, eax
0x1800895a8  jz      loc_180089639
0x1800895ae  jle     short loc_1800895B9
0x1800895b0  movzx   ebx, ax
0x1800895b3  or      ebx, 80070000h
0x1800895b9  mov     eax, cs:dword_1801263B0
0x1800895bf  cmp     eax, r13d
0x1800895c2  jbe     short loc_1800895E3
0x1800895c4  lea     rax, [rbp+57h+var_70]
0x1800895c8  mov     [rbp+57h+var_70], ebx
0x1800895cb  lea     rdx, byte_18010F307
0x1800895d2  mov     [rsp+0D0h+var_B0], rax
0x1800895d7  lea     rcx, dword_1801263B0
0x1800895de  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800895e3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x1800895ea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x1800895ef  test    al, al
0x1800895f1  jz      loc_18008A1E1
0x1800895f7  test    ebx, ebx
0x1800895f9  jns     short loc_180089639
0x1800895fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180089602  lea     rax, WPP_GLOBAL_Control
0x180089609  cmp     rcx, rax
0x18008960c  jz      loc_18008A080
0x180089612  test    [rcx+1Ch], r12b
0x180089616  jz      loc_18008A080
0x18008961c  mov     edx, 18h
0x180089621  mov     rcx, [rcx+10h]
0x180089625  lea     r8, WPP_e2321870bb8f37110138dfc56d389809_Traceguids
0x18008962c  mov     r9d, ebx
0x18008962f  call    WPP_SF_d
0x180089634  jmp     loc_18008A080
0x180089639  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x180089640  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x180089645  test    al, al
0x180089647  jz      loc_18008976D
0x18008964d  xor     edx, edx; hFile
0x18008964f  lea     rcx, aFwpuclntDll_0; "fwpuclnt.dll"
0x180089656  mov     r8d, 800h; dwFlags
0x18008965c  call    cs:__imp_LoadLibraryExW
0x180089662  mov     cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * hFwpuclntPrivate
0x180089669  test    rax, rax
0x18008966c  jnz     short loc_1800896E3
0x18008966e  call    cs:__imp_GetLastError
0x180089674  mov     ebx, eax
0x180089676  test    eax, eax
0x180089678  jle     short loc_180089683
0x18008967a  movzx   ebx, ax
0x18008967d  or      ebx, 80070000h
0x180089683  mov     eax, cs:dword_1801263B0
0x180089689  cmp     eax, r13d
0x18008968c  jbe     short loc_1800896AD
0x18008968e  lea     rax, [rbp+57h+var_7C]
0x180089692  mov     [rbp+57h+var_7C], ebx
0x180089695  lea     rdx, byte_18010ECB5
0x18008969c  mov     [rsp+0D0h+var_B0], rax
0x1800896a1  lea     rcx, dword_1801263B0
0x1800896a8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800896ad  test    ebx, ebx
0x1800896af  jns     short loc_1800896DC
0x1800896b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800896b8  lea     rax, WPP_GLOBAL_Control
0x1800896bf  cmp     rcx, rax
0x1800896c2  jz      loc_18008A080
0x1800896c8  test    [rcx+1Ch], r12b
0x1800896cc  jz      loc_18008A080
0x1800896d2  mov     edx, 19h
0x1800896d7  jmp     loc_180089621
0x1800896dc  mov     rax, cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hFwpuclntPrivate
0x1800896e3  lea     rdx, aFwpmfiltercrea_0; "FwpmFilterCreatePreciseEnumHandle"
0x1800896ea  mov     rcx, rax; hModule
0x1800896ed  call    cs:__imp_GetProcAddress
0x1800896f3  mov     cs:?pFuncFwpmFilterCreateEnumHandle@@3P6AKPEAXPEAUFWPM_FILTER_ENUM_TEMPLATE0_@@PEAPEAX@ZEA, rax; ulong (*pFuncFwpmFilterCreateEnumHandle)(void *,FWPM_FILTER_ENUM_TEMPLATE0_ *,void * *)
0x1800896fa  test    rax, rax
0x1800896fd  jnz     short loc_18008976D
0x1800896ff  call    cs:__imp_GetLastError
0x180089705  mov     ebx, eax
0x180089707  test    eax, eax
0x180089709  jle     short loc_180089714
0x18008970b  movzx   ebx, ax
0x18008970e  or      ebx, 80070000h
0x180089714  mov     eax, cs:dword_1801263B0
0x18008971a  cmp     eax, r13d
0x18008971d  jbe     short loc_18008973E
0x18008971f  lea     rax, [rbp+57h+var_7C]
0x180089723  mov     [rbp+57h+var_7C], ebx
0x180089726  lea     rdx, unk_18010F4D0
0x18008972d  mov     [rsp+0D0h+var_B0], rax
0x180089732  lea     rcx, dword_1801263B0
0x180089739  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008973e  test    ebx, ebx
0x180089740  jns     short loc_18008976D
0x180089742  mov     rcx, cs:WPP_GLOBAL_Control
0x180089749  lea     rax, WPP_GLOBAL_Control
0x180089750  cmp     rcx, rax
0x180089753  jz      loc_18008A080
0x180089759  test    [rcx+1Ch], r12b
0x18008975d  jz      loc_18008A080
0x180089763  mov     edx, 1Ah
0x180089768  jmp     loc_180089621
0x18008976d  mov     rax, cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hFwpuclntPrivate
0x180089774  test    rax, rax
0x180089777  jnz     loc_180089813
0x18008977d  xor     edx, edx; hFile
0x18008977f  lea     rcx, aFwpuclntDll_0; "fwpuclnt.dll"
0x180089786  mov     r8d, 800h; dwFlags
0x18008978c  call    cs:__imp_LoadLibraryExW
0x180089792  mov     cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * hFwpuclntPrivate
0x180089799  test    rax, rax
0x18008979c  jnz     short loc_180089813
0x18008979e  call    cs:__imp_GetLastError
0x1800897a4  mov     ebx, eax
0x1800897a6  test    eax, eax
0x1800897a8  jle     short loc_1800897B3
0x1800897aa  movzx   ebx, ax
0x1800897ad  or      ebx, 80070000h
0x1800897b3  mov     eax, cs:dword_1801263B0
0x1800897b9  cmp     eax, r13d
0x1800897bc  jbe     short loc_1800897DD
0x1800897be  lea     rax, [rbp+57h+var_80]
0x1800897c2  mov     [rbp+57h+var_80], ebx
0x1800897c5  lea     rdx, byte_18010F395
0x1800897cc  mov     [rsp+0D0h+var_B0], rax
0x1800897d1  lea     rcx, dword_1801263B0
0x1800897d8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800897dd  test    ebx, ebx
0x1800897df  jns     short loc_18008980C
0x1800897e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800897e8  lea     rax, WPP_GLOBAL_Control
0x1800897ef  cmp     rcx, rax
0x1800897f2  jz      loc_18008A080
0x1800897f8  test    [rcx+1Ch], r12b
0x1800897fc  jz      loc_18008A080
0x180089802  mov     edx, 1Bh
0x180089807  jmp     loc_180089621
0x18008980c  mov     rax, cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hFwpuclntPrivate
0x180089813  lea     rdx, aFwpmengineseto_0; "FwpmEngineSetOption1"
0x18008981a  mov     rcx, rax; hModule
0x18008981d  call    cs:__imp_GetProcAddress
0x180089823  mov     cs:?pFuncFwpmSetEngineOption1@@3P6AKPEAXW4FWPI_ENGINE_OPTION_@@PEBUFWP_VALUE0_@@@ZEA, rax; ulong (*pFuncFwpmSetEngineOption1)(void *,FWPI_ENGINE_OPTION_,FWP_VALUE0_ const *)
0x18008982a  test    rax, rax
0x18008982d  jnz     short loc_18008989D
0x18008982f  call    cs:__imp_GetLastError
0x180089835  mov     ebx, eax
0x180089837  test    eax, eax
0x180089839  jle     short loc_180089844
0x18008983b  movzx   ebx, ax
0x18008983e  or      ebx, 80070000h
0x180089844  mov     eax, cs:dword_1801263B0
0x18008984a  cmp     eax, r13d
0x18008984d  jbe     short loc_18008986E
0x18008984f  lea     rax, [rbp+57h+var_80]
0x180089853  mov     [rbp+57h+var_80], ebx
0x180089856  lea     rdx, unk_18010EA60
0x18008985d  mov     [rsp+0D0h+var_B0], rax
0x180089862  lea     rcx, dword_1801263B0
0x180089869  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008986e  test    ebx, ebx
0x180089870  jns     short loc_18008989D
0x180089872  mov     rcx, cs:WPP_GLOBAL_Control
0x180089879  lea     rax, WPP_GLOBAL_Control
0x180089880  cmp     rcx, rax
0x180089883  jz      loc_18008A080
0x180089889  test    [rcx+1Ch], r12b
0x18008988d  jz      loc_18008A080
0x180089893  mov     edx, 1Ch
0x180089898  jmp     loc_180089621
0x18008989d  lea     rax, ?g_DefaultAuthSetPhase1@@3U_tag_FW_AUTH_SET@@A; _tag_FW_AUTH_SET g_DefaultAuthSetPhase1
0x1800898a4  mov     cs:dword_180129110, 1E0h
0x1800898ae  mov     cs:qword_1801315E8, rax
0x1800898b5  lea     rcx, qword_18012E2B8; struct _tag_FW_STORE *
0x1800898bc  lea     rax, ?g_DefaultAuthSetPhase2@@3U_tag_FW_AUTH_SET@@A; _tag_FW_AUTH_SET g_DefaultAuthSetPhase2
0x1800898c3  mov     cs:dword_180129780, r12d
0x1800898ca  mov     cs:qword_1801315F0, rax
0x1800898d1  mov     esi, 2
0x1800898d6  lea     rax, ?g_DefaultCryptoSetPhase1@@3U_tag_FW_CRYPTO_SET@@A; _tag_FW_CRYPTO_SET g_DefaultCryptoSetPhase1
0x1800898dd  mov     cs:dword_180129104, esi
0x1800898e3  mov     cs:qword_180131600, rax
0x1800898ea  lea     rax, ?g_DefaultCryptoSetPhase2@@3U_tag_FW_CRYPTO_SET@@A; _tag_FW_CRYPTO_SET g_DefaultCryptoSetPhase2
0x1800898f1  mov     cs:qword_180131608, rax
0x1800898f8  lea     rax, ?g_DefaultCryptoSuitesPhase1@@3PAU_tag_FW_PHASE1_CRYPTO_SUITE@@A; _tag_FW_PHASE1_CRYPTO_SUITE near * g_DefaultCryptoSuitesPhase1
0x1800898ff  mov     cs:qword_180129108, rax
0x180089906  lea     rax, ?g_DefaultCryptoSuitesPhase2@@3PAU_tag_FW_PHASE2_CRYPTO_SUITE@@A; _tag_FW_PHASE2_CRYPTO_SUITE near * g_DefaultCryptoSuitesPhase2
0x18008990d  mov     cs:qword_180129788, rax
0x180089914  mov     cs:dword_180129784, 4
0x18008991e  call    FwHardCodedSpecialRulesInit
0x180089923  mov     ebx, eax
0x180089925  test    eax, eax
0x180089927  jns     short loc_18008995E
0x180089929  lea     rdi, aFwhardcodedspe; "FwHardCodedSpecialRulesInit"
0x180089930  mov     esi, r12d
0x180089933  mov     rcx, cs:WPP_GLOBAL_Control
0x18008993a  lea     rax, WPP_GLOBAL_Control
0x180089941  cmp     rcx, rax
0x180089944  jz      loc_18008A080
0x18008994a  test    [rcx+1Ch], r12b
0x18008994e  jz      loc_18008A080
0x180089954  mov     edx, 1Dh
0x180089959  jmp     loc_180089621
0x18008995e  lea     rcx, qword_18012F5A0; struct _tag_FW_STORE *
0x180089965  call    ?FwInsertHardcodedSetsToStore@@YAJPEAU_tag_FW_STORE@@@Z; FwInsertHardcodedSetsToStore(_tag_FW_STORE *)
0x18008996a  mov     ebx, eax
0x18008996c  test    eax, eax
0x18008996e  jns     short loc_1800899A2
0x180089970  lea     rdi, aFwinserthardco; "FwInsertHardcodedSetsToStore"
0x180089977  mov     rcx, cs:WPP_GLOBAL_Control
0x18008997e  lea     rax, WPP_GLOBAL_Control
0x180089985  cmp     rcx, rax
0x180089988  jz      loc_18008A080
0x18008998e  test    [rcx+1Ch], r12b
0x180089992  jz      loc_18008A080
0x180089998  mov     edx, 1Eh
0x18008999d  jmp     loc_180089621
0x1800899a2  lea     rax, [rbp+57h+var_60]
0x1800899a6  mov     cs:dword_18012E2B0, r15d
0x1800899ad  mov     rbx, 0FFFFFFFF80000002h
0x1800899b4  mov     [rsp+0D0h+var_B0], rax
0x1800899b9  mov     rcx, rbx
0x1800899bc  lea     r9, [rbp+57h+var_5C]
0x1800899c0  lea     r8, aDiffrule; "DiffRule"
0x1800899c7  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x1800899ce  call    cs:__imp_FwRegQueryDWord
0x1800899d4  test    eax, eax
0x1800899d6  jns     short loc_180089A02
0x1800899d8  mov     ecx, cs:dword_1801263B0
0x1800899de  cmp     ecx, r13d
0x1800899e1  jbe     short loc_180089A02
0x1800899e3  mov     [rbp+57h+var_80], eax
0x1800899e6  lea     rdx, word_18010F1EA
0x1800899ed  lea     rax, [rbp+57h+var_80]
0x1800899f1  lea     rcx, dword_1801263B0
0x1800899f8  mov     [rsp+0D0h+var_B0], rax
0x1800899fd  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180089a02  cmp     [rbp+57h+var_60], r15d
0x180089a06  jz      short loc_180089A18
0x180089a08  cmp     [rbp+57h+var_5C], r15d
0x180089a0c  mov     eax, r15d
0x180089a0f  setnz   al
0x180089a12  mov     cs:dword_18012E2B0, eax
0x180089a18  mov     eax, cs:dword_1801263B0
0x180089a1e  cmp     eax, r13d
0x180089a21  jbe     short loc_180089A57
0x180089a23  mov     eax, cs:dword_18012E2B0
0x180089a29  lea     rdx, word_18010EFAE
0x180089a30  mov     [rbp+57h+var_80], eax
0x180089a33  lea     rcx, dword_1801263B0
0x180089a3a  mov     eax, [rbp+57h+var_5C]
0x180089a3d  mov     [rbp+57h+var_7C], eax
0x180089a40  lea     rax, [rbp+57h+var_80]
0x180089a44  mov     [rsp+0D0h+var_A8], rax
0x180089a49  lea     rax, [rbp+57h+var_7C]
0x180089a4d  mov     [rsp+0D0h+var_B0], rax
0x180089a52  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180089a57  lea     rax, [rbp+57h+var_60]
0x180089a5b  mov     cs:dword_18012E2AC, r12d
0x180089a62  lea     r9, [rbp+57h+var_58]
0x180089a66  mov     [rsp+0D0h+var_B0], rax
0x180089a6b  lea     r8, aIntfquarantine; "IntfQuarantineEnabled"
0x180089a72  mov     rcx, rbx
0x180089a75  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x180089a7c  call    cs:__imp_FwRegQueryDWord
0x180089a82  test    eax, eax
0x180089a84  jns     short loc_180089AB0
0x180089a86  mov     ecx, cs:dword_1801263B0
  ... truncated ...
```
