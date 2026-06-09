# HandleProvToolArguments(ushort *)

- ea: `0x1400059ac`
- end: `0x140006862`
- name: `?HandleProvToolArguments@@YAJPEAG@Z`
- size: `3766`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, int, int)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140009c8c`

## callees

- `0x140001008`
- `0x140001130`
- `0x140001ebf`
- `0x140003210`
- `0x140003a0c`
- `0x140003ce4`
- `0x1400041b0`
- `0x1400045c8`
- `0x1400045f0`
- `0x1400059ac`
- `0x140006868`
- `0x140006b04`
- `0x140006b70`
- `0x140007564`
- `0x140007734`
- `0x140007844`
- `0x140008820`
- `0x140009398`
- `0x140009de4`
- `0x14000a3d4`
- `0x14000de9e`
- `0x14000ded0`
- `0x140010010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140005a2e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140005a2e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140005b8e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140005b8e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400060fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400060fd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140005c9b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140005e18`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140005fd1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006095`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006178`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006257`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400067ee`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140005c9b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140005e18`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140005fd1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006095`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006178`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006257`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400067ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006405`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006405`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140006471`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140006471`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400064d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400064d5`
- `dmcommandlineutils!ProcessCommandLine` at `0x140005c60`
- `dmcommandlineutils!ProcessCommandLine` at `0x140005c60`
- `dmcommandlineutils!FreeCommandLineOptions` at `0x140005e03`
- `dmcommandlineutils!FreeCommandLineOptions` at `0x140005fbc`
- `dmcommandlineutils!FreeCommandLineOptions` at `0x140006080`
- `dmcommandlineutils!FreeCommandLineOptions` at `0x140006163`
- `dmcommandlineutils!FreeCommandLineOptions` at `0x140006242`
- `dmcommandlineutils!FreeCommandLineOptions` at `0x1400067d9`
- `dmcommandlineutils!FreeCommandLineOptions` at `0x140005e03`
- `dmcommandlineutils!FreeCommandLineOptions` at `0x140005fbc`
- `dmcommandlineutils!FreeCommandLineOptions` at `0x140006080`
- `dmcommandlineutils!FreeCommandLineOptions` at `0x140006163`
- `dmcommandlineutils!FreeCommandLineOptions` at `0x140006242`
- `dmcommandlineutils!FreeCommandLineOptions` at `0x1400067d9`
- `ntdll!NtQuerySystemInformation` at `0x1400065cf`
- `ntdll!NtQuerySystemInformation` at `0x1400065cf`
- `ext-ms-win-provisioning-platform-l1-1-1!InitiateMgmtRefresh` at `0x1400065f0`
- `ext-ms-win-provisioning-platform-l1-1-1!InitiateMgmtRefresh` at `0x1400065f0`

## string_xrefs

- `0x140006433`: `OSData\SOFTWARE\Microsoft\Provisioning\LogonTaskCompleted`
- `0x14000642c`: `SOFTWARE\Microsoft\Provisioning\LogonTaskCompleted`
- `0x140005eaa`: `LogonIdleTask`
- `0x1400063bd`: `LogonIdleTask`
- `0x140006730`: `WcosProvisioningTask`

## pseudocode

```c
__int64 __fastcall HandleProvToolArguments(unsigned __int16 *a1, __int64 a2, int a3, int a4)
{
  HKEY v4; // r14
  HRESULT v5; // eax
  unsigned int v6; // esi
  int v8; // eax
  int v9; // edx
  int v10; // ecx
  unsigned int v11; // esi
  const wchar_t *v12; // r8
  const wchar_t *v13; // rax
  const wchar_t *v14; // r9
  int v15; // esi
  wchar_t *v16; // r14
  int v17; // eax
  int v18; // eax
  int v19; // eax
  unsigned int v20; // esi
  HRESULT Instance; // eax
  unsigned int v22; // esi
  struct IProvOperations *v23; // rcx
  wchar_t *v24; // rdx
  int v25; // eax
  __int64 v26; // rcx
  unsigned int v27; // esi
  struct IProvOperations *v28; // rcx
  void *p_phkResult; // rax
  char *v30; // rdx
  const WCHAR *v31; // rdx
  LSTATUS v32; // eax
  int v33; // r14d
  int v34; // eax
  unsigned int v35; // esi
  struct IProvOperations *v36; // rcx
  int ppv; // [rsp+20h] [rbp-1C8h]
  int *ppva; // [rsp+20h] [rbp-1C8h]
  int ppvb; // [rsp+20h] [rbp-1C8h]
  int v40; // [rsp+50h] [rbp-198h] BYREF
  int v41; // [rsp+54h] [rbp-194h] BYREF
  struct IProvOperations *v42; // [rsp+58h] [rbp-190h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-188h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-180h] BYREF
  char v45; // [rsp+71h] [rbp-177h]
  int v46; // [rsp+80h] [rbp-168h] BYREF
  int v47[2]; // [rsp+88h] [rbp-160h]
  int v48; // [rsp+A0h] [rbp-148h]
  int v49; // [rsp+A4h] [rbp-144h]
  int v50; // [rsp+A8h] [rbp-140h]
  __int64 v51; // [rsp+B0h] [rbp-138h]
  int v52; // [rsp+B8h] [rbp-130h]
  int v53; // [rsp+BCh] [rbp-12Ch]
  int v54; // [rsp+C4h] [rbp-124h]
  int v55; // [rsp+C8h] [rbp-120h]
  wchar_t *String2; // [rsp+D0h] [rbp-118h]
  int v57; // [rsp+D8h] [rbp-110h]
  int v58; // [rsp+DCh] [rbp-10Ch]
  __int128 v59; // [rsp+E0h] [rbp-108h] BYREF
  __int64 v60; // [rsp+F0h] [rbp-F8h]
  int v61; // [rsp+100h] [rbp-E8h] BYREF
  char v62; // [rsp+104h] [rbp-E4h]
  GUID v63; // [rsp+108h] [rbp-E0h] BYREF
  void *p_hKey; // [rsp+150h] [rbp-98h]
  __int64 v65; // [rsp+158h] [rbp-90h]
  int *v66; // [rsp+160h] [rbp-88h]
  __int64 v67; // [rsp+168h] [rbp-80h]
  _QWORD v68[2]; // [rsp+170h] [rbp-78h] BYREF
  char v69; // [rsp+180h] [rbp-68h]
  int *v70; // [rsp+190h] [rbp-58h]
  char v71; // [rsp+198h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v4 = (HKEY)a1;
  v61 = 0;
  v62 = 0;
  if ( (unsigned int)dword_140017048 > 5
    && (LODWORD(a1) = qword_140017060, (qword_140017058 & 0x200000000000LL) != 0)
    && (qword_140017060 & 0x200000000000LL) == qword_140017060 )
  {
    EventActivityIdControl(3u, &v63);
  }
  else
  {
    v63 = 0;
  }
  v61 = 1;
  if ( (unsigned int)dword_140017048 > 5 )
  {
    LODWORD(a1) = qword_140017060;
    if ( (qword_140017058 & 0x200000000000LL) != 0 && (qword_140017060 & 0x200000000000LL) == qword_140017060 )
    {
      ppv = 2;
      tlgWriteTransfer_EventWriteTransfer(&dword_140017048, word_140013412, &v63, 0);
    }
  }
  if ( (unsigned int)dword_140017048 > 4 )
  {
    ppv = 2;
    tlgWriteTransfer_EventWriteTransfer(&dword_140017048, &word_1400131A6, &v63, 0);
  }
  if ( (unsigned int)dword_140017048 > 4 )
  {
    hKey = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)a1,
      (unsigned int)byte_14001316B,
      a3,
      a4,
      (__int64)&hKey);
  }
  v41 = 0;
  v68[0] = &v41;
  v68[1] = &v61;
  v69 = 1;
  v5 = CoInitializeEx(0, 0);
  v6 = v5;
  v41 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17B,
      (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
      (const char *)(unsigned int)v5,
      ppv);
    v69 = 0;
    lambda_2f7c2ae10654b2fe2b2dd527a095e1af_::operator()(v68);
    if ( v61 == 1 )
    {
      v61 = 2;
      _tlgWriteActivityAutoStop<35184372088832,5>(&dword_140017048, &v63);
    }
    return v6;
  }
  v45 = 1;
  v49 = 0;
  v54 = 0;
  memset_0(&v46, 0, 0x60u);
  v59 = 0;
  v60 = 0;
  ppva = &v46;
  v8 = ProcessCommandLine(&off_1400112E0, 9, CommandLineHandler, v4);
  v11 = v8;
  v41 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x185,
      (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
      (const char *)(unsigned int)v8,
      (int)&v46);
    std::vector<std::wstring>::_Tidy(&v59);
    CoUninitialize();
    v69 = 0;
    lambda_2f7c2ae10654b2fe2b2dd527a095e1af_::operator()(v68);
    if ( v61 == 1 )
    {
      v61 = 2;
      _tlgWriteActivityAutoStop<35184372088832,5>(&dword_140017048, &v63);
    }
    return v11;
  }
  v70 = &v46;
  v71 = 1;
  if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
  {
    v12 = L"<Not Present>";
    v13 = L"<Not Present>";
    if ( v46 )
      v13 = *(const wchar_t **)v47;
    v14 = L"<Not Present>";
    if ( v50 )
      LODWORD(v14) = v51;
    if ( v55 )
      LODWORD(v12) = (_DWORD)String2;
    McTemplateU0zzz_EventWriteTransfer(v10, v9, (_DWORD)v12, (_DWORD)v14, (__int64)v13);
  }
  v15 = v55;
  if ( v55 )
  {
    v16 = String2;
    if ( !wcscmp_0(L"ProvResetBoot", String2) )
    {
      v40 = 0;
      v17 = CheckResetStateAtBoot(&v40);
      if ( v17 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x198,
          (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
          (const char *)(unsigned int)v17,
          (int)ppva);
      if ( !v40 )
      {
        if ( (unsigned int)dword_140017048 > 5 )
          tlgWriteTransfer_EventWriteTransfer(&dword_140017048, qword_140013378, &v63, 0);
        FreeCommandLineOptions(&off_1400112E0, 9, &v46);
        std::vector<std::wstring>::_Tidy(&v59);
        CoUninitialize();
        v69 = 0;
        lambda_2f7c2ae10654b2fe2b2dd527a095e1af_::operator()(v68);
        if ( v61 == 1 )
        {
          v61 = 2;
          _tlgWriteActivityAutoStop<35184372088832,5>(&dword_140017048, &v63);
        }
        return 1;
      }
      if ( (unsigned int)dword_140017048 > 5 )
      {
        LODWORD(ppva) = 2;
        tlgWriteTransfer_EventWriteTransfer(&dword_140017048, qword_140013330, &v63, 0);
      }
      v16 = String2;
      v15 = v55;
    }
    if ( v15 && !wcscmp_0(L"LogonIdleTask", v16) )
    {
      v18 = ProvRemoveLockScreenText();
      if ( (unsigned int)dword_140017048 > 4 )
      {
        v40 = v18;
        p_hKey = &v40;
        v65 = 4;
        LODWORD(ppva) = 3;
        tlgWriteTransfer_EventWriteTransfer(&dword_140017048, byte_1400131C5, 0, 0);
      }
      if ( !(unsigned int)HasLogonTaskExecuted() )
      {
        if ( (unsigned int)dword_140017048 > 5
          && (qword_140017058 & 0x400000000000LL) != 0
          && (qword_140017060 & 0x400000000000LL) == qword_140017060 )
        {
          hKey = (HKEY)0x2000000;
          p_hKey = &hKey;
          v65 = 8;
          tlgWriteTransfer_EventWriteTransfer(&dword_140017048, byte_140013133, &v63, 0);
        }
        FreeCommandLineOptions(&off_1400112E0, 9, &v46);
        std::vector<std::wstring>::_Tidy(&v59);
        CoUninitialize();
        v69 = 0;
        lambda_2f7c2ae10654b2fe2b2dd527a095e1af_::operator()(v68);
        if ( v61 == 1 )
        {
          v61 = 2;
          _tlgWriteActivityAutoStop<35184372088832,5>(&dword_140017048, &v63);
        }
        return 0;
      }
    }
  }
  if ( v58 )
    v58 &= -(v57 != 0);
  v19 = SetComSecurity();
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
      (const char *)(unsigned int)v19,
      (int)ppva);
    FreeCommandLineOptions(&off_1400112E0, 9, &v46);
    std::vector<std::wstring>::_Tidy(&v59);
    CoUninitialize();
    v69 = 0;
    lambda_2f7c2ae10654b2fe2b2dd527a095e1af_::operator()(v68);
    if ( v61 == 1 )
    {
      v61 = 2;
      _tlgWriteActivityAutoStop<35184372088832,5>(&dword_140017048, &v63);
    }
    return v20;
  }
  v42 = 0;
  Instance = CoCreateInstance(
               &GUID_5b89deeb_4df1_4cf6_9979_c79185cb95a0,
               0,
               1u,
               &GUID_9051683d_92ab_4ffd_bb73_1f80a11ae5c2,
               (LPVOID *)&v42);
  v22 = Instance;
  v41 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C3,
      (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
      (const char *)(unsigned int)Instance,
      ppvb);
    v23 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(struct IProvOperations *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    FreeCommandLineOptions(&off_1400112E0, 9, &v46);
    std::vector<std::wstring>::_Tidy(&v59);
    CoUninitialize();
    v69 = 0;
    lambda_2f7c2ae10654b2fe2b2dd527a095e1af_::operator()(v68);
    if ( v61 == 1 )
    {
      v61 = 2;
      _tlgWriteActivityAutoStop<35184372088832,5>(&dword_140017048, &v63);
    }
    return v22;
  }
  v24 = L"ProvToolUnidentified";
  if ( v55 )
    v24 = String2;
  v25 = (*(__int64 (__fastcall **)(struct IProvOperations *, wchar_t *))(*(_QWORD *)v42 + 72LL))(v42, v24);
  v27 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
      (const char *)(unsigned int)v25,
      ppvb);
    v28 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(struct IProvOperations *))(*(_QWORD *)v28 + 16LL))(v28);
    }
    FreeCommandLineOptions(&off_1400112E0, 9, &v46);
    std::vector<std::wstring>::_Tidy(&v59);
    CoUninitialize();
    v69 = 0;
    lambda_2f7c2ae10654b2fe2b2dd527a095e1af_::operator()(v68);
    if ( v61 == 1 )
    {
      v61 = 2;
      _tlgWriteActivityAutoStop<35184372088832,5>(&dword_140017048, &v63);
    }
    return v27;
  }
  if ( v50 )
  {
    if ( (unsigned int)dword_140017048 > 5 )
      tlgWriteTransfer_EventWriteTransfer(&dword_140017048, byte_140013225, &v63, 0);
    v41 = RemovePackage(v42, (const struct _ProvToolCommandSettings *)&v46);
    if ( (unsigned int)dword_140017048 <= 4 )
      goto LABEL_119;
    v40 = v41;
    p_phkResult = &v40;
    v30 = byte_14001334D;
    goto LABEL_117;
  }
  if ( v52 && !v46 )
  {
    if ( (unsigned int)dword_140017048 > 5 )
    {
      v40 = v53;
      p_hKey = &v40;
      v65 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_140017048, byte_1400131F3, &v63, 0);
    }
    v41 = ApplyTurn(v42, (const struct _ProvToolCommandSettings *)&v46);
    if ( v55 && !wcscmp_0(L"LogonIdleTask", String2) )
    {
      hKey = 0;
      if ( !`ProvIsStateSeparationEnabled'::`2'::s_HasRun )
      {
        phkResult = 0;
        `ProvIsStateSeparationEnabled'::`2'::s_Redirection = RegOpenKeyExW(
                                                               HKEY_LOCAL_MACHINE,
                                                               L"Software\\Microsoft\\Provisioning\\StateSeparationMode",
                                                               0,
                                                               0x20119u,
                                                               &phkResult) == 0;
        RegCloseKey(phkResult);
        `ProvIsStateSeparationEnabled'::`2'::s_HasRun = 1;
      }
      v31 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\LogonTaskCompleted";
      if ( !`ProvIsStateSeparationEnabled'::`2'::s_Redirection )
        v31 = L"SOFTWARE\\Microsoft\\Provisioning\\LogonTaskCompleted";
      v32 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v31, 0, 0, 1u, 0x20019u, 0, &hKey, 0);
      if ( (unsigned int)dword_140017048 > 4 )
      {
        v40 = v32;
        p_hKey = &v40;
        v65 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_140017048, byte_140013305, &v63, 0);
      }
      if ( hKey )
        RegCloseKey(hKey);
    }
    if ( (unsigned int)dword_140017048 <= 4 )
      goto LABEL_119;
    v40 = v41;
    p_phkResult = &v40;
    v30 = byte_1400132BD;
    goto LABEL_117;
  }
  if ( v48 )
  {
    v41 = ListPackages();
    goto LABEL_119;
  }
  if ( v57 )
  {
    if ( (unsigned int)dword_140017048 > 5 )
    {
      v26 = qword_140017060;
      if ( (qword_140017058 & 0x400000000000LL) != 0 && (qword_140017060 & 0x400000000000LL) == qword_140017060 )
      {
        v40 = v58;
        p_hKey = &v40;
        v65 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_140017048, byte_14001328B, &v63, 0);
      }
    }
    v33 = 0;
    if ( v58 )
    {
      hKey = 0;
      if ( NtQuerySystemInformation(SystemSessionPoolTagInformation|0x80, &hKey, 8u, 0) >= 0
        && ((unsigned __int8)hKey & 4) != 0 )
      {
        v34 = InitiateTimeloop();
        v33 = 1;
        goto LABEL_109;
      }
      v33 = 0;
    }
    v34 = InitiateMgmtRefresh(v26);
LABEL_109:
    v41 = v34;
    if ( (unsigned int)dword_140017048 <= 4
      || (qword_140017058 & 0x400000000000LL) == 0
      || (qword_140017060 & 0x400000000000LL) != qword_140017060 )
    {
      goto LABEL_119;
    }
    v40 = v33;
    LODWORD(phkResult) = v41;
    v66 = &v40;
    v67 = 4;
    p_hKey = &phkResult;
    v30 = byte_140013249;
    goto LABEL_118;
  }
  if ( (unsigned int)dword_140017048 > 5 )
    tlgWriteTransfer_EventWriteTransfer(&dword_140017048, &dword_1400132E4, &v63, 0);
  v41 = AddPackage(v42, (const struct _ProvToolCommandSettings *)&v46);
  if ( (unsigned int)dword_140017048 <= 4 )
    goto LABEL_119;
  LODWORD(phkResult) = v41;
  p_phkResult = &phkResult;
  v30 = (char *)qword_140013398;
LABEL_117:
  p_hKey = p_phkResult;
LABEL_118:
  v65 = 4;
  tlgWriteTransfer_EventWriteTransfer(&dword_140017048, v30, &v63, 0);
LABEL_119:
  if ( v55 && !wcscmp_0(L"WcosProvisioningTask", String2) )
    DisableBootTrigger();
  v61 = 2;
  if ( (unsigned int)dword_140017048 > 5
    && (qword_140017058 & 0x200000000000LL) != 0
    && (qword_140017060 & 0x200000000000LL) == qword_140017060 )
  {
    tlgWriteTransfer_EventWriteTransfer(&dword_140017048, byte_140013111, &v63, 0);
  }
  v35 = v41;
  v36 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(struct IProvOperations *))(*(_QWORD *)v36 + 16LL))(v36);
  }
  FreeCommandLineOptions(&off_1400112E0, 9, &v46);
  std::vector<std::wstring>::_Tidy(&v59);
  CoUninitialize();
  v69 = 0;
  lambda_2f7c2ae10654b2fe2b2dd527a095e1af_::operator()(v68);
  if ( v61 == 1 )
  {
    v61 = 2;
    _tlgWriteActivityAutoStop<35184372088832,5>(&dword_140017048, &v63);
  }
  return v35;
}

```

## disassembly

```asm
0x1400059ac  mov     r11, rsp
0x1400059af  mov     [r11+10h], rbx
0x1400059b3  mov     [r11+18h], rsi
0x1400059b7  push    rdi
0x1400059b8  push    r12
0x1400059ba  push    r13
0x1400059bc  push    r14
0x1400059be  push    r15
0x1400059c0  sub     rsp, 1C0h
0x1400059c7  mov     rax, cs:__security_cookie
0x1400059ce  xor     rax, rsp
0x1400059d1  mov     [rsp+1E8h+var_38], rax
0x1400059d9  mov     r14, rcx
0x1400059dc  xor     r13d, r13d
0x1400059df  mov     [r11-0E8h], r13d
0x1400059e6  mov     [r11-0E4h], r13b
0x1400059ed  mov     eax, cs:dword_140017048
0x1400059f3  mov     r12, 200000000000h
0x1400059fd  cmp     eax, 5
0x140005a00  jbe     short loc_140005A36
0x140005a02  mov     rcx, cs:qword_140017060
0x140005a09  mov     rax, cs:qword_140017058
0x140005a10  test    r12, rax
0x140005a13  jz      short loc_140005A36
0x140005a15  mov     rax, rcx
0x140005a18  and     rax, r12
0x140005a1b  cmp     rax, rcx
0x140005a1e  jnz     short loc_140005A36
0x140005a20  lea     rdx, [r11-0E0h]; ActivityId
0x140005a27  lea     r15d, [r13+3]
0x140005a2b  mov     ecx, r15d; ControlCode
0x140005a2e  call    cs:__imp_EventActivityIdControl
0x140005a34  jmp     short loc_140005A47
0x140005a36  xorps   xmm0, xmm0
0x140005a39  movups  [rsp+1E8h+var_E0], xmm0
0x140005a41  mov     r15d, 3
0x140005a47  mov     [rsp+1E8h+var_E8], 1
0x140005a52  mov     eax, cs:dword_140017048
0x140005a58  cmp     eax, 5
0x140005a5b  jbe     loc_140005AF8
0x140005a61  mov     rcx, cs:qword_140017060
0x140005a68  mov     rax, cs:qword_140017058
0x140005a6f  test    r12, rax
0x140005a72  jz      loc_140005AF8
0x140005a78  mov     rax, rcx
0x140005a7b  and     rax, r12
0x140005a7e  cmp     rax, rcx
0x140005a81  jnz     short loc_140005AF8
0x140005a83  cmp     [rsp+1E8h+var_E4], r13b
0x140005a8b  jz      short loc_140005ABF
0x140005a8d  cmp     [rsp+1E8h+var_D0], r13d
0x140005a95  jnz     short loc_140005AB5
0x140005a97  cmp     [rsp+1E8h+var_CC], r13d
0x140005a9f  jnz     short loc_140005AB5
0x140005aa1  cmp     [rsp+1E8h+var_C8], r13d
0x140005aa9  jnz     short loc_140005AB5
0x140005aab  cmp     [rsp+1E8h+var_C4], r13d
0x140005ab3  jz      short loc_140005ABF
0x140005ab5  lea     r9, [rsp+1E8h+var_D0]
0x140005abd  jmp     short loc_140005AC2
0x140005abf  mov     r9, r13
0x140005ac2  lea     rax, [rsp+1E8h+var_78]
0x140005aca  mov     qword ptr [rsp+1E8h+samDesired], rax
0x140005acf  mov     edi, 2
0x140005ad4  mov     dword ptr [rsp+1E8h+ppv], edi
0x140005ad8  lea     r8, [rsp+1E8h+var_E0]
0x140005ae0  lea     rdx, word_140013412
0x140005ae7  lea     rbx, dword_140017048
0x140005aee  mov     rcx, rbx
0x140005af1  call    _tlgWriteTransfer_EventWriteTransfer
0x140005af6  jmp     short loc_140005B04
0x140005af8  mov     edi, 2
0x140005afd  lea     rbx, dword_140017048
0x140005b04  mov     eax, cs:dword_140017048
0x140005b0a  cmp     eax, 4
0x140005b0d  jbe     short loc_140005B3A
0x140005b0f  lea     rax, [rsp+1E8h+var_78]
0x140005b17  mov     qword ptr [rsp+1E8h+samDesired], rax
0x140005b1c  mov     dword ptr [rsp+1E8h+ppv], edi
0x140005b20  xor     r9d, r9d
0x140005b23  lea     r8, [rsp+1E8h+var_E0]
0x140005b2b  lea     rdx, word_1400131A6
0x140005b32  mov     rcx, rbx
0x140005b35  call    _tlgWriteTransfer_EventWriteTransfer
0x140005b3a  mov     eax, cs:dword_140017048
0x140005b40  cmp     eax, 4
0x140005b43  jbe     short loc_140005B60
0x140005b45  mov     [rsp+1E8h+hKey], r14
0x140005b4a  lea     rax, [rsp+1E8h+hKey]
0x140005b4f  mov     [rsp+1E8h+ppv], rax; int
0x140005b54  lea     rdx, byte_14001316B
0x140005b5b  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x140005b60  mov     [rsp+1E8h+var_194], r13d
0x140005b65  lea     rax, [rsp+1E8h+var_194]
0x140005b6a  mov     [rsp+1E8h+var_78], rax
0x140005b72  lea     rax, [rsp+1E8h+var_E8]
0x140005b7a  mov     [rsp+1E8h+var_70], rax
0x140005b82  mov     [rsp+1E8h+var_68], 1
0x140005b8a  xor     edx, edx; dwCoInit
0x140005b8c  xor     ecx, ecx; pvReserved
0x140005b8e  call    cs:__imp_CoInitializeEx
0x140005b94  mov     esi, eax
0x140005b96  mov     [rsp+1E8h+var_194], eax
0x140005b9a  test    eax, eax
0x140005b9c  jns     short loc_140005BF9
0x140005b9e  mov     rcx, [rsp+1E8h]; this
0x140005ba6  mov     r9d, eax; char *
0x140005ba9  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x140005bb0  mov     edx, 17Bh; void *
0x140005bb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005bba  nop
0x140005bbb  mov     [rsp+1E8h+var_68], r13b
0x140005bc3  lea     rcx, [rsp+1E8h+var_78]
0x140005bcb  call    _lambda_2f7c2ae10654b2fe2b2dd527a095e1af___operator__
0x140005bd0  nop
0x140005bd1  cmp     [rsp+1E8h+var_E8], 1
0x140005bd9  jnz     short loc_140005BF2
0x140005bdb  mov     [rsp+1E8h+var_E8], edi
0x140005be2  lea     rdx, [rsp+1E8h+var_E0]
0x140005bea  mov     rcx, rbx
0x140005bed  call    ??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)
0x140005bf2  mov     eax, esi
0x140005bf4  jmp     loc_140006834
0x140005bf9  mov     [rsp+1E8h+var_177], 1
0x140005bfe  xor     eax, eax
0x140005c00  mov     [rsp+1E8h+var_144], eax
0x140005c07  mov     [rsp+1E8h+var_124], eax
0x140005c0e  xor     edx, edx; Val
0x140005c10  lea     r8d, [rax+60h]; Size
0x140005c14  lea     rcx, [rsp+1E8h+var_168]; void *
0x140005c1c  call    memset_0
0x140005c21  xorps   xmm0, xmm0
0x140005c24  movdqa  [rsp+1E8h+var_108], xmm0
0x140005c2d  mov     [rsp+1E8h+var_F8], r13
0x140005c35  mov     [rsp+1E8h+samDesired], 78h ; 'x'
0x140005c3d  lea     rax, [rsp+1E8h+var_168]
0x140005c45  mov     [rsp+1E8h+ppv], rax; int
0x140005c4a  mov     r9, r14
0x140005c4d  lea     r8, ?CommandLineHandler@@YAJPEBGPEAE@Z; CommandLineHandler(ushort const *,uchar *)
0x140005c54  mov     edx, 9
0x140005c59  lea     rcx, off_1400112E0; "add"
0x140005c60  call    cs:__imp_ProcessCommandLine
0x140005c66  mov     esi, eax
0x140005c68  mov     [rsp+1E8h+var_194], eax
0x140005c6c  test    eax, eax
0x140005c6e  jns     short loc_140005CE0
0x140005c70  mov     rcx, [rsp+1E8h]; this
0x140005c78  mov     r9d, eax; char *
0x140005c7b  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x140005c82  mov     edx, 185h; void *
0x140005c87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005c8c  nop
0x140005c8d  lea     rcx, [rsp+1E8h+var_108]
0x140005c95  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x140005c9a  nop
0x140005c9b  call    cs:__imp_CoUninitialize
0x140005ca1  nop
0x140005ca2  mov     [rsp+1E8h+var_68], r13b
0x140005caa  lea     rcx, [rsp+1E8h+var_78]
0x140005cb2  call    _lambda_2f7c2ae10654b2fe2b2dd527a095e1af___operator__
0x140005cb7  nop
0x140005cb8  cmp     [rsp+1E8h+var_E8], 1
0x140005cc0  jnz     short loc_140005CD9
0x140005cc2  mov     [rsp+1E8h+var_E8], edi
0x140005cc9  lea     rdx, [rsp+1E8h+var_E0]
0x140005cd1  mov     rcx, rbx
0x140005cd4  call    ??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)
0x140005cd9  mov     eax, esi
0x140005cdb  jmp     loc_140006834
0x140005ce0  lea     rax, [rsp+1E8h+var_168]
0x140005ce8  mov     [rsp+1E8h+var_58], rax
0x140005cf0  mov     [rsp+1E8h+var_50], 1
0x140005cf8  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 1
0x140005cff  jz      short loc_140005D4B
0x140005d01  lea     r8, aNotPresent; "<Not Present>"
0x140005d08  mov     rax, r8
0x140005d0b  cmp     [rsp+1E8h+var_168], r13d
0x140005d13  cmovnz  rax, qword ptr [rsp+1E8h+var_160]
0x140005d1c  mov     r9, r8
0x140005d1f  cmp     [rsp+1E8h+var_140], r13d
0x140005d27  cmovnz  r9, [rsp+1E8h+var_138]
0x140005d30  cmp     [rsp+1E8h+var_120], r13d
0x140005d38  cmovnz  r8, [rsp+1E8h+String2]
0x140005d41  mov     [rsp+1E8h+ppv], rax; int
0x140005d46  call    McTemplateU0zzz_EventWriteTransfer
0x140005d4b  mov     esi, [rsp+1E8h+var_120]
0x140005d52  test    esi, esi
0x140005d54  jz      loc_140006016
0x140005d5a  mov     r14, [rsp+1E8h+String2]
0x140005d62  mov     rdx, r14; String2
0x140005d65  lea     rcx, aProvresetboot; "ProvResetBoot"
0x140005d6c  call    wcscmp_0
0x140005d71  test    eax, eax
0x140005d73  jnz     loc_140005E9F
0x140005d79  mov     [rsp+1E8h+var_198], r13d
0x140005d7e  lea     rcx, [rsp+1E8h+var_198]; int *
0x140005d83  call    ?CheckResetStateAtBoot@@YAJPEAH@Z; CheckResetStateAtBoot(int *)
0x140005d88  mov     rcx, [rsp+1E8h]; this
0x140005d90  test    eax, eax
0x140005d92  jns     short loc_140005DA8
0x140005d94  mov     r9d, eax; char *
0x140005d97  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x140005d9e  mov     edx, 198h; void *
0x140005da3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140005da8  cmp     [rsp+1E8h+var_198], r13d
0x140005dad  mov     eax, cs:dword_140017048
0x140005db3  jnz     loc_140005E60
0x140005db9  cmp     eax, 5
0x140005dbc  jbe     short loc_140005DEA
0x140005dbe  lea     rax, [rsp+1E8h+var_58]
0x140005dc6  mov     qword ptr [rsp+1E8h+samDesired], rax
0x140005dcb  mov     dword ptr [rsp+1E8h+ppv], edi
0x140005dcf  xor     r9d, r9d
0x140005dd2  lea     r8, [rsp+1E8h+var_E0]
0x140005dda  lea     rdx, qword_140013378
0x140005de1  mov     rcx, rbx
0x140005de4  call    _tlgWriteTransfer_EventWriteTransfer
0x140005de9  nop
0x140005dea  mov     r9d, 78h ; 'x'
0x140005df0  lea     r8, [rsp+1E8h+var_168]
0x140005df8  lea     edx, [r9-6Fh]
0x140005dfc  lea     rcx, off_1400112E0; "add"
0x140005e03  call    cs:__imp_FreeCommandLineOptions
0x140005e09  nop
0x140005e0a  lea     rcx, [rsp+1E8h+var_108]
0x140005e12  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x140005e17  nop
0x140005e18  call    cs:__imp_CoUninitialize
0x140005e1e  nop
0x140005e1f  mov     [rsp+1E8h+var_68], r13b
0x140005e27  lea     rcx, [rsp+1E8h+var_78]
0x140005e2f  call    _lambda_2f7c2ae10654b2fe2b2dd527a095e1af___operator__
0x140005e34  nop
0x140005e35  cmp     [rsp+1E8h+var_E8], 1
0x140005e3d  jnz     short loc_140005E56
0x140005e3f  mov     [rsp+1E8h+var_E8], edi
0x140005e46  lea     rdx, [rsp+1E8h+var_E0]
0x140005e4e  mov     rcx, rbx
0x140005e51  call    ??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)
0x140005e56  mov     eax, 1
0x140005e5b  jmp     loc_140006834
0x140005e60  cmp     eax, 5
0x140005e63  jbe     short loc_140005E90
0x140005e65  lea     rax, [rsp+1E8h+var_B8]
0x140005e6d  mov     qword ptr [rsp+1E8h+samDesired], rax
0x140005e72  mov     dword ptr [rsp+1E8h+ppv], edi
0x140005e76  xor     r9d, r9d
0x140005e79  lea     r8, [rsp+1E8h+var_E0]
0x140005e81  lea     rdx, qword_140013330
0x140005e88  mov     rcx, rbx
0x140005e8b  call    _tlgWriteTransfer_EventWriteTransfer
0x140005e90  mov     r14, [rsp+1E8h+String2]
0x140005e98  mov     esi, [rsp+1E8h+var_120]
0x140005e9f  test    esi, esi
0x140005ea1  jz      loc_140006016
0x140005ea7  mov     rdx, r14; String2
0x140005eaa  lea     rcx, aLogonidletask; "LogonIdleTask"
0x140005eb1  call    wcscmp_0
0x140005eb6  test    eax, eax
0x140005eb8  jnz     loc_140006016
0x140005ebe  call    ?ProvRemoveLockScreenText@@YAJXZ; ProvRemoveLockScreenText(void)
0x140005ec3  mov     ecx, cs:dword_140017048
0x140005ec9  mov     r14d, 4
0x140005ecf  cmp     ecx, r14d
0x140005ed2  jbe     short loc_140005F14
0x140005ed4  mov     [rsp+1E8h+var_198], eax
0x140005ed8  lea     rax, [rsp+1E8h+var_198]
0x140005edd  mov     [rsp+1E8h+var_98], rax
0x140005ee5  mov     [rsp+1E8h+var_90], r14
0x140005eed  lea     rax, [rsp+1E8h+var_B8]
0x140005ef5  mov     qword ptr [rsp+1E8h+samDesired], rax
0x140005efa  mov     dword ptr [rsp+1E8h+ppv], r15d
0x140005eff  xor     r9d, r9d
0x140005f02  xor     r8d, r8d
0x140005f05  lea     rdx, byte_1400131C5
0x140005f0c  mov     rcx, rbx
0x140005f0f  call    _tlgWriteTransfer_EventWriteTransfer
0x140005f14  call    ?HasLogonTaskExecuted@@YAJXZ; HasLogonTaskExecuted(void)
0x140005f19  test    eax, eax
0x140005f1b  jnz     loc_14000601C
0x140005f21  mov     eax, cs:dword_140017048
0x140005f27  cmp     eax, 5
0x140005f2a  jbe     short loc_140005FA3
0x140005f2c  mov     rcx, cs:qword_140017060
0x140005f33  mov     rax, cs:qword_140017058
0x140005f3a  mov     rsi, 400000000000h
0x140005f44  test    rsi, rax
0x140005f47  jz      short loc_140005FA3
0x140005f49  mov     rax, rcx
0x140005f4c  and     rax, rsi
0x140005f4f  cmp     rax, rcx
0x140005f52  jnz     short loc_140005FA3
0x140005f54  mov     [rsp+1E8h+hKey], 2000000h
0x140005f5d  lea     rax, [rsp+1E8h+hKey]
0x140005f62  mov     [rsp+1E8h+var_98], rax
0x140005f6a  mov     [rsp+1E8h+var_90], 8
0x140005f76  lea     rax, [rsp+1E8h+var_B8]
0x140005f7e  mov     qword ptr [rsp+1E8h+samDesired], rax
0x140005f83  mov     dword ptr [rsp+1E8h+ppv], r15d
0x140005f88  xor     r9d, r9d
  ... truncated ...
```
