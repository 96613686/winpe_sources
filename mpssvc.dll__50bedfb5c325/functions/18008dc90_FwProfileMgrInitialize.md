# FwProfileMgrInitialize

- ea: `0x18008dc90`
- end: `0x18008e9c2`
- name: `FwProfileMgrInitialize`
- size: `3378`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000151c`
- `0x180001784`
- `0x18000182c`
- `0x180001dcc`
- `0x18000a710`
- `0x18002d340`
- `0x180050a9c`
- `0x18005e408`
- `0x18005f4e4`
- `0x180061c90`
- `0x1800632b8`
- `0x18006a710`
- `0x1800729c0`
- `0x1800861ac`
- `0x180087d4c`
- `0x180087d98`
- `0x180089090`
- `0x180089244`
- `0x18008ba34`
- `0x18008dc90`
- `0x18008ea20`
- `0x1800b24ec`
- `0x1800b2b58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ddea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008de87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008df32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008dfcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ddea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008de87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008df32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008dfcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008de6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008dfb7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008de6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008dfb7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008ddd2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008df1a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008ddd2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008df1a`
- `fwbase!FwRegNotifyCreate` at `0x18008e2ec`
- `fwbase!FwRegNotifyCreate` at `0x18008e2ec`
- `fwbase!FwRegQueryDWord` at `0x18008e174`
- `fwbase!FwRegQueryDWord` at `0x18008e228`
- `fwbase!FwRegQueryDWord` at `0x18008e174`
- `fwbase!FwRegQueryDWord` at `0x18008e228`
- `fwbase!FwReportReturnError` at `0x18008e965`
- `fwbase!FwReportReturnError` at `0x18008e965`
- `FWPolicyIOMgr!LoadGPExtensionDll` at `0x18008dd05`
- `FWPolicyIOMgr!LoadGPExtensionDll` at `0x18008dd05`

## string_xrefs

- `0x18008e913`: `mpssvc.dll`
- `0x18008ddc5`: `fwpuclnt.dll`
- `0x18008df0d`: `fwpuclnt.dll`
- `0x18008de65`: `FwpmFilterCreatePreciseEnumHandle`
- `0x18008e2fe`: `FwRegNotifyCreate`
- `0x18008e16d`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x18008e221`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x18008e2c6`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy\RestrictedServices\Configurable`

## pseudocode

```c
__int64 FwProfileMgrInitialize()
{
  int *v0; // r14
  __int64 v1; // rbx
  unsigned int v2; // esi
  const char *v3; // rdi
  int GPExtensionDll; // eax
  int v5; // r8d
  int v6; // r9d
  signed int inserted; // ebx
  unsigned __int64 v8; // r8
  unsigned int v9; // r9d
  __int64 v10; // rcx
  __int64 v11; // rdx
  HMODULE Library; // rax
  signed int LastError; // eax
  signed int v14; // eax
  HMODULE v15; // rax
  signed int v16; // eax
  signed int v17; // eax
  int v18; // eax
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // r8
  int v25; // edx
  int v26; // ecx
  unsigned int i; // edi
  int v28; // eax
  int v29; // r8d
  int v30; // r9d
  int v32; // [rsp+50h] [rbp-29h] BYREF
  signed int v33; // [rsp+54h] [rbp-25h] BYREF
  int v34; // [rsp+58h] [rbp-21h] BYREF
  unsigned int v35; // [rsp+5Ch] [rbp-1Dh] BYREF
  unsigned int v36; // [rsp+60h] [rbp-19h] BYREF
  __int64 v37; // [rsp+68h] [rbp-11h] BYREF
  int v38; // [rsp+70h] [rbp-9h] BYREF
  signed int v39; // [rsp+74h] [rbp-5h] BYREF
  signed int v40; // [rsp+78h] [rbp-1h] BYREF

  v0 = &dword_18012C458;
  v1 = 0;
  v40 = 0;
  v39 = 0;
  v2 = 0;
  v38 = 0;
  v3 = 0;
  if ( !dword_18012C458 )
    v0 = 0;
  do
    FwInitializeStore((struct _tag_FW_STORE *)&qword_180134478[121 * v1++]);
  while ( v1 != 13 );
  GPExtensionDll = LoadGPExtensionDll();
  inserted = GPExtensionDll;
  if ( !GPExtensionDll )
  {
LABEL_15:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl) )
    {
      Library = LoadLibraryExW(L"fwpuclnt.dll", 0, 0x800u);
      hFwpuclntPrivate = Library;
      if ( !Library )
      {
        LastError = GetLastError();
        inserted = LastError;
        if ( LastError > 0 )
          inserted = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)dword_18012C3B0 > 5 )
        {
          v33 = inserted;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18012C3B0,
            (unsigned int)&unk_180114B50,
            v8,
            v9,
            (__int64)&v33);
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
        if ( (unsigned int)dword_18012C3B0 > 5 )
        {
          v33 = inserted;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18012C3B0,
            (unsigned int)byte_18011536B,
            v8,
            v9,
            (__int64)&v33);
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
        if ( (unsigned int)dword_18012C3B0 > 5 )
        {
          v32 = inserted;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18012C3B0,
            (unsigned int)&unk_180115230,
            v8,
            v9,
            (__int64)&v32);
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
      if ( (unsigned int)dword_18012C3B0 > 5 )
      {
        v32 = inserted;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18012C3B0,
          (unsigned int)byte_1801148FB,
          v8,
          v9,
          (__int64)&v32);
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
    dword_18012F110 = 480;
    qword_1801377B8 = (__int64)&g_DefaultAuthSetPhase1;
    dword_18012F780 = 1;
    qword_1801377C0 = (__int64)&g_DefaultAuthSetPhase2;
    v2 = 2;
    dword_18012F104 = 2;
    qword_1801377D0 = (__int64)&g_DefaultCryptoSetPhase1;
    qword_1801377D8 = (struct _tag_FW_CRYPTO_SET *)&g_DefaultCryptoSetPhase2;
    qword_18012F108 = (__int64)&g_DefaultCryptoSuitesPhase1;
    qword_18012F788 = (__int64)&g_DefaultCryptoSuitesPhase2;
    dword_18012F784 = 4;
    inserted = FwHardCodedSpecialRulesInit((struct _tag_FW_STORE *)qword_180134478);
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
    inserted = FwInsertHardcodedSetsToStore((struct _tag_FW_STORE *)qword_180135760);
    if ( inserted < 0 )
    {
      v3 = "FwInsertHardcodedSetsToStore";
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_147;
      v11 = 30;
      goto LABEL_14;
    }
    dword_180134470 = 0;
    v18 = FwRegQueryDWord(
            -2147483646,
            L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy",
            L"DiffRule",
            &v39,
            &v38);
    if ( v18 < 0 && (unsigned int)dword_18012C3B0 > 5 )
    {
      v32 = v18;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18012C3B0,
        (unsigned int)byte_180115085,
        v19,
        v20,
        (__int64)&v32);
    }
    if ( v38 )
      dword_180134470 = v39 != 0;
    if ( (unsigned int)dword_18012C3B0 > 5 )
    {
      v32 = dword_180134470;
      v33 = v39;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18012C3B0,
        (unsigned int)byte_180114E49,
        v19,
        v20,
        (__int64)&v33,
        (__int64)&v32);
    }
    dword_18013446C = 1;
    v21 = FwRegQueryDWord(
            -2147483646,
            L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy",
            L"IntfQuarantineEnabled",
            &v40,
            &v38);
    if ( v21 < 0 && (unsigned int)dword_18012C3B0 > 5 )
    {
      v32 = v21;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18012C3B0,
        (unsigned int)word_180114EB2,
        v22,
        v23,
        (__int64)&v32);
    }
    if ( v38 )
      dword_18013446C = v40 != 0;
    if ( (unsigned int)dword_18012C3B0 > 5 )
    {
      v32 = dword_18013446C;
      v33 = v40;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18012C3B0,
        (unsigned int)word_180114C12,
        v22,
        v23,
        (__int64)&v33,
        (__int64)&v32);
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
      inserted = FwLoadStore(3, qword_180134FD0, 0);
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
      dword_180134468 = 0;
      v2 = 8;
      inserted = FwLoadStore(8, qword_1801362B8, 0);
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
      inserted = FwLoadStore(10, qword_180136A48, 0);
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
      inserted = FwLoadStore(11, qword_180136E10, 0);
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
      inserted = FwLoadStore(12, qword_1801371D8, 0);
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
      inserted = FwLoadStore(3, qword_180134FD0, v24);
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
      dword_180134468 = 0;
      LOBYTE(v8) = 1;
      inserted = FwLoadStore(8, qword_1801362B8, v8);
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
      inserted = FwLoadStore(10, qword_180136A48, v8);
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
      inserted = FwLoadStore(11, qword_180136E10, v8);
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
      inserted = FwLoadStore(12, qword_1801371D8, v8);
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
      v34 = 10;
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
                  if ( v9 >= 0x1F4 && (unsigned int)*v0 > 5 && (unsigned __int8)tlgKeywordOn(v0, 0x400000000000LL) )
                  {
                    v32 = HIDWORD(gFwProfileMgr[v8 / 8 + 122]);
                    v33 = gFwProfileMgr[v8 / 8 + 123];
                    v36 = v9;
                    v35 = i;
                    v37 = 0x1000000;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                      (_DWORD)v0,
                      (unsigned int)&byte_180114DD7,
                      v8,
                      v9,
                      (__int64)&v37,
                      (__int64)&v35,
                      (__int64)&v36,
                      (__int64)&v33,
                      (__int64)&v32);
                  }
                }
              }
            }
            v2 = v34;
          }
          v3 = 0;
          goto LABEL_147;
        }
        if ( (unsigned int)dword_18012C3B0 > 5 )
        {
          v32 = inserted;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18012C3B0,
            (unsigned int)&unk_1801153D8,
            v8,
            v9,
            (__int64)&v32);
        }
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        {
LABEL_147:
          if ( (unsigned int)dword_18012C3B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18012C3B0, 0x4000000000000LL) )
          {
            v34 = inserted;
            v37 = (__int64)v3;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (int)&dword_18012C3B0,
              (__int64)&v37,
              (__int64)&v34);
          }
          if ( inserted >= 0 )
          {
            if ( (unsigned int)dword_18012C3B0 > 5 )
            {
              v34 = inserted;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (unsigned int)&dword_18012C3B0,
                (unsigned int)byte_180114BDB,
                v8,
                v9,
                (__int64)&v34);
            }
          }
          else
          {
            if ( !bFwProfileMgrInitFail )
            {
              if ( (unsigned int)dword_18012C458 >= 6
                && (unsigned __int8)tlgKeywordOn(&dword_18012C458, 0x400000000000LL) )
              {
                v37 = 0x1000000;
                v34 = v2;
                v35 = inserted;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                  (unsigned int)&dword_18012C458,
                  (unsigned int)&dword_180115424,
                  v29,
                  v30,
                  (__int64)&v35,
                  (__int64)&v34,
                  (__int64)&v37);
              }
              bFwProfileMgrInitFail = 1;
              MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v2, 0);
            }
            if ( (unsigned int)dword_18012C3B0 > 5 )
            {
              v34 = inserted;
              v35 = v2;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_18012C3B0,
                (unsigned int)byte_1801151ED,
                v8,
                v9,
                (__int64)&v35,
                (__int64)&v34);
            }
            FwProfileMgrShutdown();
            return (unsigned int)FwReportReturnError("FwProfileMgrInitialize", (unsigned int)inserted);
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
    WPP_SF_d(*(_QWORD *)(v10 + 16), v11, WPP_3d9dabe50e6b3e70315acf6b635a3004_Traceguids, (unsigned int)inserted);
    goto LABEL_147;
  }
  if ( GPExtensionDll > 0 )
    inserted = (unsigned __int16)GPExtensionDll | 0x80070000;
  if ( (unsigned int)dword_18012C3B0 > 5 )
  {
    v36 = inserted;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18012C3B0,
      (unsigned int)word_1801151A2,
      v5,
      v6,
      (__int64)&v36);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl) )
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
0x18008dc90  push    rbp
0x18008dc92  push    rbx
0x18008dc93  push    rsi
0x18008dc94  push    rdi
0x18008dc95  push    r12
0x18008dc97  push    r13
0x18008dc99  push    r14
0x18008dc9b  push    r15
0x18008dc9d  lea     rbp, [rsp-1Fh]
0x18008dca2  sub     rsp, 98h
0x18008dca9  mov     rax, cs:__security_cookie
0x18008dcb0  xor     rax, rsp
0x18008dcb3  mov     [rbp+57h+var_50], rax
0x18008dcb7  mov     ecx, cs:dword_18012C458
0x18008dcbd  lea     r14, dword_18012C458
0x18008dcc4  xor     r15d, r15d
0x18008dcc7  mov     ebx, r15d
0x18008dcca  mov     [rbp+57h+var_58], r15d
0x18008dcce  test    ecx, ecx
0x18008dcd0  mov     [rbp+57h+var_5C], r15d
0x18008dcd4  mov     esi, r15d
0x18008dcd7  mov     [rbp+57h+var_60], r15d
0x18008dcdb  mov     edi, r15d
0x18008dcde  cmovz   r14, r15
0x18008dce2  lea     r12d, [rbx+1]
0x18008dce6  lea     r15, qword_180134478
0x18008dced  imul    rcx, rbx, 3C8h
0x18008dcf4  add     rcx, r15; struct _tag_FW_STORE *
0x18008dcf7  call    ?FwInitializeStore@@YAXPEAU_tag_FW_STORE@@@Z; FwInitializeStore(_tag_FW_STORE *)
0x18008dcfc  add     rbx, r12
0x18008dcff  cmp     rbx, 0Dh
0x18008dd03  jnz     short loc_18008DCED
0x18008dd05  call    cs:__imp_LoadGPExtensionDll
0x18008dd0c  nop     dword ptr [rax+rax+00h]
0x18008dd11  xor     r15d, r15d
0x18008dd14  mov     r13d, 5
0x18008dd1a  mov     ebx, eax
0x18008dd1c  test    eax, eax
0x18008dd1e  jz      loc_18008DDAF
0x18008dd24  jle     short loc_18008DD2F
0x18008dd26  movzx   ebx, ax
0x18008dd29  or      ebx, 80070000h
0x18008dd2f  mov     eax, cs:dword_18012C3B0
0x18008dd35  cmp     eax, r13d
0x18008dd38  jbe     short loc_18008DD59
0x18008dd3a  lea     rax, [rbp+57h+var_70]
0x18008dd3e  mov     [rbp+57h+var_70], ebx
0x18008dd41  lea     rdx, word_1801151A2
0x18008dd48  mov     [rsp+0D0h+var_B0], rax
0x18008dd4d  lea     rcx, dword_18012C3B0
0x18008dd54  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008dd59  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x18008dd60  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x18008dd65  test    al, al
0x18008dd67  jz      loc_18008E99F
0x18008dd6d  test    ebx, ebx
0x18008dd6f  jns     short loc_18008DDAF
0x18008dd71  mov     rcx, cs:WPP_GLOBAL_Control
0x18008dd78  lea     rax, WPP_GLOBAL_Control
0x18008dd7f  cmp     rcx, rax
0x18008dd82  jz      loc_18008E838
0x18008dd88  test    [rcx+1Ch], r12b
0x18008dd8c  jz      loc_18008E838
0x18008dd92  mov     edx, 18h
0x18008dd97  mov     rcx, [rcx+10h]
0x18008dd9b  lea     r8, WPP_3d9dabe50e6b3e70315acf6b635a3004_Traceguids
0x18008dda2  mov     r9d, ebx
0x18008dda5  call    WPP_SF_d
0x18008ddaa  jmp     loc_18008E838
0x18008ddaf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x18008ddb6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x18008ddbb  test    al, al
0x18008ddbd  jz      loc_18008DEFB
0x18008ddc3  xor     edx, edx; hFile
0x18008ddc5  lea     rcx, aFwpuclntDll_0; "fwpuclnt.dll"
0x18008ddcc  mov     r8d, 800h; dwFlags
0x18008ddd2  call    cs:__imp_LoadLibraryExW
0x18008ddd9  nop     dword ptr [rax+rax+00h]
0x18008ddde  mov     cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * hFwpuclntPrivate
0x18008dde5  test    rax, rax
0x18008dde8  jnz     short loc_18008DE65
0x18008ddea  call    cs:__imp_GetLastError
0x18008ddf1  nop     dword ptr [rax+rax+00h]
0x18008ddf6  mov     ebx, eax
0x18008ddf8  test    eax, eax
0x18008ddfa  jle     short loc_18008DE05
0x18008ddfc  movzx   ebx, ax
0x18008ddff  or      ebx, 80070000h
0x18008de05  mov     eax, cs:dword_18012C3B0
0x18008de0b  cmp     eax, r13d
0x18008de0e  jbe     short loc_18008DE2F
0x18008de10  lea     rax, [rbp+57h+var_7C]
0x18008de14  mov     [rbp+57h+var_7C], ebx
0x18008de17  lea     rdx, unk_180114B50
0x18008de1e  mov     [rsp+0D0h+var_B0], rax
0x18008de23  lea     rcx, dword_18012C3B0
0x18008de2a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008de2f  test    ebx, ebx
0x18008de31  jns     short loc_18008DE5E
0x18008de33  mov     rcx, cs:WPP_GLOBAL_Control
0x18008de3a  lea     rax, WPP_GLOBAL_Control
0x18008de41  cmp     rcx, rax
0x18008de44  jz      loc_18008E838
0x18008de4a  test    [rcx+1Ch], r12b
0x18008de4e  jz      loc_18008E838
0x18008de54  mov     edx, 19h
0x18008de59  jmp     loc_18008DD97
0x18008de5e  mov     rax, cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hFwpuclntPrivate
0x18008de65  lea     rdx, aFwpmfiltercrea_0; "FwpmFilterCreatePreciseEnumHandle"
0x18008de6c  mov     rcx, rax; hModule
0x18008de6f  call    cs:__imp_GetProcAddress
0x18008de76  nop     dword ptr [rax+rax+00h]
0x18008de7b  mov     cs:?pFuncFwpmFilterCreateEnumHandle@@3P6AKPEAXPEAUFWPM_FILTER_ENUM_TEMPLATE0_@@PEAPEAX@ZEA, rax; ulong (*pFuncFwpmFilterCreateEnumHandle)(void *,FWPM_FILTER_ENUM_TEMPLATE0_ *,void * *)
0x18008de82  test    rax, rax
0x18008de85  jnz     short loc_18008DEFB
0x18008de87  call    cs:__imp_GetLastError
0x18008de8e  nop     dword ptr [rax+rax+00h]
0x18008de93  mov     ebx, eax
0x18008de95  test    eax, eax
0x18008de97  jle     short loc_18008DEA2
0x18008de99  movzx   ebx, ax
0x18008de9c  or      ebx, 80070000h
0x18008dea2  mov     eax, cs:dword_18012C3B0
0x18008dea8  cmp     eax, r13d
0x18008deab  jbe     short loc_18008DECC
0x18008dead  lea     rax, [rbp+57h+var_7C]
0x18008deb1  mov     [rbp+57h+var_7C], ebx
0x18008deb4  lea     rdx, byte_18011536B
0x18008debb  mov     [rsp+0D0h+var_B0], rax
0x18008dec0  lea     rcx, dword_18012C3B0
0x18008dec7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008decc  test    ebx, ebx
0x18008dece  jns     short loc_18008DEFB
0x18008ded0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ded7  lea     rax, WPP_GLOBAL_Control
0x18008dede  cmp     rcx, rax
0x18008dee1  jz      loc_18008E838
0x18008dee7  test    [rcx+1Ch], r12b
0x18008deeb  jz      loc_18008E838
0x18008def1  mov     edx, 1Ah
0x18008def6  jmp     loc_18008DD97
0x18008defb  mov     rax, cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hFwpuclntPrivate
0x18008df02  test    rax, rax
0x18008df05  jnz     loc_18008DFAD
0x18008df0b  xor     edx, edx; hFile
0x18008df0d  lea     rcx, aFwpuclntDll_0; "fwpuclnt.dll"
0x18008df14  mov     r8d, 800h; dwFlags
0x18008df1a  call    cs:__imp_LoadLibraryExW
0x18008df21  nop     dword ptr [rax+rax+00h]
0x18008df26  mov     cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * hFwpuclntPrivate
0x18008df2d  test    rax, rax
0x18008df30  jnz     short loc_18008DFAD
0x18008df32  call    cs:__imp_GetLastError
0x18008df39  nop     dword ptr [rax+rax+00h]
0x18008df3e  mov     ebx, eax
0x18008df40  test    eax, eax
0x18008df42  jle     short loc_18008DF4D
0x18008df44  movzx   ebx, ax
0x18008df47  or      ebx, 80070000h
0x18008df4d  mov     eax, cs:dword_18012C3B0
0x18008df53  cmp     eax, r13d
0x18008df56  jbe     short loc_18008DF77
0x18008df58  lea     rax, [rbp+57h+var_80]
0x18008df5c  mov     [rbp+57h+var_80], ebx
0x18008df5f  lea     rdx, unk_180115230
0x18008df66  mov     [rsp+0D0h+var_B0], rax
0x18008df6b  lea     rcx, dword_18012C3B0
0x18008df72  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008df77  test    ebx, ebx
0x18008df79  jns     short loc_18008DFA6
0x18008df7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008df82  lea     rax, WPP_GLOBAL_Control
0x18008df89  cmp     rcx, rax
0x18008df8c  jz      loc_18008E838
0x18008df92  test    [rcx+1Ch], r12b
0x18008df96  jz      loc_18008E838
0x18008df9c  mov     edx, 1Bh
0x18008dfa1  jmp     loc_18008DD97
0x18008dfa6  mov     rax, cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hFwpuclntPrivate
0x18008dfad  lea     rdx, aFwpmengineseto_0; "FwpmEngineSetOption1"
0x18008dfb4  mov     rcx, rax; hModule
0x18008dfb7  call    cs:__imp_GetProcAddress
0x18008dfbe  nop     dword ptr [rax+rax+00h]
0x18008dfc3  mov     cs:?pFuncFwpmSetEngineOption1@@3P6AKPEAXW4FWPI_ENGINE_OPTION_@@PEBUFWP_VALUE0_@@@ZEA, rax; ulong (*pFuncFwpmSetEngineOption1)(void *,FWPI_ENGINE_OPTION_,FWP_VALUE0_ const *)
0x18008dfca  test    rax, rax
0x18008dfcd  jnz     short loc_18008E043
0x18008dfcf  call    cs:__imp_GetLastError
0x18008dfd6  nop     dword ptr [rax+rax+00h]
0x18008dfdb  mov     ebx, eax
0x18008dfdd  test    eax, eax
0x18008dfdf  jle     short loc_18008DFEA
0x18008dfe1  movzx   ebx, ax
0x18008dfe4  or      ebx, 80070000h
0x18008dfea  mov     eax, cs:dword_18012C3B0
0x18008dff0  cmp     eax, r13d
0x18008dff3  jbe     short loc_18008E014
0x18008dff5  lea     rax, [rbp+57h+var_80]
0x18008dff9  mov     [rbp+57h+var_80], ebx
0x18008dffc  lea     rdx, byte_1801148FB
0x18008e003  mov     [rsp+0D0h+var_B0], rax
0x18008e008  lea     rcx, dword_18012C3B0
0x18008e00f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008e014  test    ebx, ebx
0x18008e016  jns     short loc_18008E043
0x18008e018  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e01f  lea     rax, WPP_GLOBAL_Control
0x18008e026  cmp     rcx, rax
0x18008e029  jz      loc_18008E838
0x18008e02f  test    [rcx+1Ch], r12b
0x18008e033  jz      loc_18008E838
0x18008e039  mov     edx, 1Ch
0x18008e03e  jmp     loc_18008DD97
0x18008e043  lea     rax, ?g_DefaultAuthSetPhase1@@3U_tag_FW_AUTH_SET@@A; _tag_FW_AUTH_SET g_DefaultAuthSetPhase1
0x18008e04a  mov     cs:dword_18012F110, 1E0h
0x18008e054  mov     cs:qword_1801377B8, rax
0x18008e05b  lea     rcx, qword_180134478; struct _tag_FW_STORE *
0x18008e062  lea     rax, ?g_DefaultAuthSetPhase2@@3U_tag_FW_AUTH_SET@@A; _tag_FW_AUTH_SET g_DefaultAuthSetPhase2
0x18008e069  mov     cs:dword_18012F780, r12d
0x18008e070  mov     cs:qword_1801377C0, rax
0x18008e077  mov     esi, 2
0x18008e07c  lea     rax, ?g_DefaultCryptoSetPhase1@@3U_tag_FW_CRYPTO_SET@@A; _tag_FW_CRYPTO_SET g_DefaultCryptoSetPhase1
0x18008e083  mov     cs:dword_18012F104, esi
0x18008e089  mov     cs:qword_1801377D0, rax
0x18008e090  lea     rax, ?g_DefaultCryptoSetPhase2@@3U_tag_FW_CRYPTO_SET@@A; _tag_FW_CRYPTO_SET g_DefaultCryptoSetPhase2
0x18008e097  mov     cs:qword_1801377D8, rax
0x18008e09e  lea     rax, ?g_DefaultCryptoSuitesPhase1@@3PAU_tag_FW_PHASE1_CRYPTO_SUITE@@A; _tag_FW_PHASE1_CRYPTO_SUITE near * g_DefaultCryptoSuitesPhase1
0x18008e0a5  mov     cs:qword_18012F108, rax
0x18008e0ac  lea     rax, ?g_DefaultCryptoSuitesPhase2@@3PAU_tag_FW_PHASE2_CRYPTO_SUITE@@A; _tag_FW_PHASE2_CRYPTO_SUITE near * g_DefaultCryptoSuitesPhase2
0x18008e0b3  mov     cs:qword_18012F788, rax
0x18008e0ba  mov     cs:dword_18012F784, 4
0x18008e0c4  call    FwHardCodedSpecialRulesInit
0x18008e0c9  mov     ebx, eax
0x18008e0cb  test    eax, eax
0x18008e0cd  jns     short loc_18008E104
0x18008e0cf  lea     rdi, aFwhardcodedspe; "FwHardCodedSpecialRulesInit"
0x18008e0d6  mov     esi, r12d
0x18008e0d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e0e0  lea     rax, WPP_GLOBAL_Control
0x18008e0e7  cmp     rcx, rax
0x18008e0ea  jz      loc_18008E838
0x18008e0f0  test    [rcx+1Ch], r12b
0x18008e0f4  jz      loc_18008E838
0x18008e0fa  mov     edx, 1Dh
0x18008e0ff  jmp     loc_18008DD97
0x18008e104  lea     rcx, qword_180135760; struct _tag_FW_STORE *
0x18008e10b  call    ?FwInsertHardcodedSetsToStore@@YAJPEAU_tag_FW_STORE@@@Z; FwInsertHardcodedSetsToStore(_tag_FW_STORE *)
0x18008e110  mov     ebx, eax
0x18008e112  test    eax, eax
0x18008e114  jns     short loc_18008E148
0x18008e116  lea     rdi, aFwinserthardco; "FwInsertHardcodedSetsToStore"
0x18008e11d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e124  lea     rax, WPP_GLOBAL_Control
0x18008e12b  cmp     rcx, rax
0x18008e12e  jz      loc_18008E838
0x18008e134  test    [rcx+1Ch], r12b
0x18008e138  jz      loc_18008E838
0x18008e13e  mov     edx, 1Eh
0x18008e143  jmp     loc_18008DD97
0x18008e148  lea     rax, [rbp+57h+var_60]
0x18008e14c  mov     cs:dword_180134470, r15d
0x18008e153  mov     rbx, 0FFFFFFFF80000002h
0x18008e15a  mov     [rsp+0D0h+var_B0], rax
0x18008e15f  mov     rcx, rbx
0x18008e162  lea     r9, [rbp+57h+var_5C]
0x18008e166  lea     r8, aDiffrule; "DiffRule"
0x18008e16d  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18008e174  call    cs:__imp_FwRegQueryDWord
0x18008e17b  nop     dword ptr [rax+rax+00h]
0x18008e180  test    eax, eax
0x18008e182  jns     short loc_18008E1AE
0x18008e184  mov     ecx, cs:dword_18012C3B0
0x18008e18a  cmp     ecx, r13d
0x18008e18d  jbe     short loc_18008E1AE
0x18008e18f  mov     [rbp+57h+var_80], eax
0x18008e192  lea     rdx, byte_180115085
0x18008e199  lea     rax, [rbp+57h+var_80]
0x18008e19d  lea     rcx, dword_18012C3B0
0x18008e1a4  mov     [rsp+0D0h+var_B0], rax
0x18008e1a9  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008e1ae  cmp     [rbp+57h+var_60], r15d
0x18008e1b2  jz      short loc_18008E1C4
0x18008e1b4  cmp     [rbp+57h+var_5C], r15d
0x18008e1b8  mov     eax, r15d
0x18008e1bb  setnz   al
0x18008e1be  mov     cs:dword_180134470, eax
0x18008e1c4  mov     eax, cs:dword_18012C3B0
0x18008e1ca  cmp     eax, r13d
0x18008e1cd  jbe     short loc_18008E203
0x18008e1cf  mov     eax, cs:dword_180134470
0x18008e1d5  lea     rdx, byte_180114E49
0x18008e1dc  mov     [rbp+57h+var_80], eax
0x18008e1df  lea     rcx, dword_18012C3B0
0x18008e1e6  mov     eax, [rbp+57h+var_5C]
0x18008e1e9  mov     [rbp+57h+var_7C], eax
0x18008e1ec  lea     rax, [rbp+57h+var_80]
0x18008e1f0  mov     [rsp+0D0h+var_A8], rax
0x18008e1f5  lea     rax, [rbp+57h+var_7C]
0x18008e1f9  mov     [rsp+0D0h+var_B0], rax
0x18008e1fe  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008e203  lea     rax, [rbp+57h+var_60]
  ... truncated ...
```
