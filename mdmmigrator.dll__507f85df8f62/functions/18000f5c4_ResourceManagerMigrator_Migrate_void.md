# ResourceManagerMigrator::Migrate(void)

- ea: `0x18000f5c4`
- end: `0x180010167`
- name: `?Migrate@ResourceManagerMigrator@@QEAAJXZ`
- size: `2979`
- prototype: `__int64 __fastcall(ResourceManagerMigrator *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000cb50`

## callees

- `0x1800018cc`
- `0x1800019e4`
- `0x1800022e0`
- `0x1800035f2`
- `0x180007720`
- `0x180007b38`
- `0x180007bec`
- `0x180009850`
- `0x18000d1b0`
- `0x18000f5c4`
- `0x180010170`
- `0x180010610`
- `0x180010864`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fba7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fa80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fbba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fa80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fbba`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000fa1f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000fb6b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000fcb7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180010105`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000fa1f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000fb6b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000fcb7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180010105`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f895`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f895`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f800`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f943`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f957`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fa30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fa44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fa78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fbb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fcc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fcdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010116`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001012a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f800`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f943`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f957`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fa30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fa44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fa78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fbb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fcc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fcdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010116`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001012a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fbe7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fbe7`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000fa9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000fa9b`
- `DMCmnUtils!DmRevertToSelf` at `0x18000fb5e`
- `DMCmnUtils!DmRevertToSelf` at `0x18000fcaa`
- `DMCmnUtils!DmRevertToSelf` at `0x1800100f8`
- `DMCmnUtils!DmRevertToSelf` at `0x18000fb5e`
- `DMCmnUtils!DmRevertToSelf` at `0x18000fcaa`
- `DMCmnUtils!DmRevertToSelf` at `0x1800100f8`
- `DMCmnUtils!DmImpersonate` at `0x18000f97b`
- `DMCmnUtils!DmImpersonate` at `0x18000f97b`

## string_xrefs

- `0x18000fcf3`: `MDM_WirelessProfileXml`
- `0x18000fcec`: `Profiles\MDM_WirelessProfileXml`
- `0x18000f79d`: `Unable to get UserSid`
- `0x18000f9bc`: `Error impersonating user`
- `0x18000faec`: `Opening HKCU for impersonated user`
- `0x18000ff61`: `WMI AppInstallJob Migration Failure`

## pseudocode

```c
__int64 __fastcall ResourceManagerMigrator::Migrate(ResourceManagerMigrator *this, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v5; // r8
  _QWORD *v6; // rbx
  const wchar_t *v7; // rdx
  size_t v8; // r12
  size_t v9; // r13
  const wchar_t *v10; // rcx
  size_t v11; // r8
  int v12; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  _QWORD *v16; // r9
  char *v17; // rsi
  unsigned __int64 v18; // rdx
  char *v19; // r12
  __int64 v20; // rbx
  HRESULT v21; // ebx
  __int64 v22; // r8
  __int64 v23; // r9
  const unsigned __int16 *v24; // rcx
  int v25; // ebx
  __int64 v26; // r8
  __int64 v27; // r9
  HKEY v28; // r12
  DWORD LastError; // ebx
  int v30; // ebx
  __int64 v31; // r8
  __int64 v32; // r9
  unsigned int v33; // eax
  HKEY v34; // r12
  DWORD v35; // ebx
  int v36; // ebx
  __int64 v37; // r8
  __int64 v38; // r9
  unsigned int v39; // eax
  int v40; // eax
  __int64 v41; // r9
  int v42; // eax
  __int64 v43; // r9
  int v44; // eax
  __int64 v45; // r9
  __int64 v46; // r8
  int v47; // eax
  __int64 v48; // r9
  __int64 v49; // r8
  int v50; // ebx
  __int64 v51; // r8
  __int64 v52; // r9
  int v53; // [rsp+50h] [rbp-B8h] BYREF
  const unsigned __int16 *v54; // [rsp+58h] [rbp-B0h] BYREF
  const char *v55; // [rsp+60h] [rbp-A8h] BYREF
  const unsigned __int16 *v56; // [rsp+68h] [rbp-A0h] BYREF
  const unsigned __int16 *v57; // [rsp+70h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-90h] BYREF
  const unsigned __int16 *v59; // [rsp+80h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp-80h] BYREF
  const unsigned __int16 *v61; // [rsp+90h] [rbp-78h] BYREF
  __int64 v62; // [rsp+98h] [rbp-70h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-60h]
  wchar_t *S1[2]; // [rsp+B0h] [rbp-58h] BYREF
  size_t v65; // [rsp+C0h] [rbp-48h]
  unsigned __int64 v66; // [rsp+C8h] [rbp-40h]

  phkResult = 0;
  hKey = 0;
  if ( (unsigned int)dword_18002B0C0 > 5
    && (qword_18002B0D0 & 0x400000000000LL) != 0
    && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
  {
    v54 = L"Started";
    v55 = "onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\resourcemanagermigrator.cpp";
    v53 = 51;
    v61 = L"ResourceManagerMigrator::Migrate";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      qword_18002B0D8,
      (__int64)&word_180025D4E,
      a3,
      a4,
      &v61,
      (__int64)&v53,
      (const unsigned __int16 **)&v55,
      &v54);
  }
  *(_OWORD *)S1 = 0;
  v65 = 0;
  v66 = 0;
  v5 = -1;
  do
    ++v5;
  while ( userSidRtv[v5] );
  std::wstring::_Construct<1,unsigned short const *>(S1, userSidRtv, v5);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
    (__int64)this,
    &v62,
    (__int64)S1);
  v6 = (_QWORD *)v63;
  if ( *(_BYTE *)(v63 + 25) )
    goto LABEL_16;
  v7 = (const wchar_t *)(v63 + 32);
  v8 = *(_QWORD *)(v63 + 48);
  if ( *(_QWORD *)(v63 + 56) > 7u )
    v7 = *(const wchar_t **)v7;
  v9 = v65;
  v10 = (const wchar_t *)S1;
  if ( v66 > 7 )
    v10 = S1[0];
  v11 = v65;
  if ( v8 < v65 )
    v11 = *(_QWORD *)(v63 + 48);
  v12 = wmemcmp(v10, v7, v11);
  if ( !v12 )
  {
    if ( v9 >= v8 )
      goto LABEL_17;
    goto LABEL_16;
  }
  if ( v12 < 0 )
LABEL_16:
    v6 = *(_QWORD **)this;
LABEL_17:
  std::wstring::~wstring((char **)S1);
  if ( v6 == *(_QWORD **)this )
  {
    if ( (unsigned int)dword_18002B0C0 > 5
      && (qword_18002B0D0 & 0x400000000000LL) != 0
      && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
    {
      v54 = L"Unable to get UserSid";
      v55 = "onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\resourcemanagermigrator.cpp";
      v53 = 58;
      v61 = L"ResourceManagerMigrator::Migrate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        qword_18002B0D8,
        (__int64)byte_180025CFB,
        v13,
        v14,
        &v61,
        (__int64)&v53,
        (const unsigned __int16 **)&v55,
        &v54);
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( phkResult )
      RegCloseKey(phkResult);
    return 2147500037LL;
  }
  else
  {
    v16 = v6 + 8;
    v17 = (char *)this + 16;
    if ( v17 != (char *)(v6 + 8) )
    {
      v18 = v6[10];
      if ( v6[11] > 7u )
        v16 = (_QWORD *)*v16;
      if ( v18 > *((_QWORD *)v17 + 3) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v17);
      }
      else
      {
        if ( *((_QWORD *)v17 + 3) <= 7u )
          v19 = v17;
        else
          v19 = *(char **)v17;
        *((_QWORD *)v17 + 2) = v18;
        v20 = 2 * v18;
        memmove_0(v19, v16, 2 * v18);
        *(_WORD *)&v19[v20] = 0;
      }
    }
    v21 = CoInitializeEx(0, 0);
    if ( v21 >= 0 )
    {
      BYTE1(v61) = 1;
      if ( *((_QWORD *)v17 + 3) <= 7u )
        v24 = (const unsigned __int16 *)v17;
      else
        v24 = *(const unsigned __int16 **)v17;
      v25 = DmImpersonate(v24);
      if ( v25 >= 0 )
      {
        byte_18002B7D8 = v25 != 1;
        BYTE1(v53) = 1;
        v28 = phkResult;
        if ( phkResult )
        {
          LastError = GetLastError();
          RegCloseKey(v28);
          SetLastError(LastError);
        }
        phkResult = 0;
        v30 = RegOpenCurrentUser(0x20019u, &phkResult);
        if ( v30 )
        {
          if ( (unsigned int)dword_18002B0C0 > 5
            && (qword_18002B0D0 & 0x400000000000LL) != 0
            && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
          {
            if ( v30 > 0 )
              v33 = (unsigned __int16)v30 | 0x80070000;
            else
              v33 = v30;
            v53 = v33;
            v56 = L"Opening HKCU for impersonated user";
            v54 = (const unsigned __int16 *)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\resourcemanagermigrator.cpp";
            LODWORD(v55) = 105;
            v57 = L"ResourceManagerMigrator::Migrate";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              qword_18002B0D8,
              (__int64)word_180025BD2,
              v31,
              v32,
              &v57,
              (__int64)&v55,
              &v54,
              &v56,
              (__int64)&v53);
          }
          if ( v30 > 0 )
            v30 = (unsigned __int16)v30 | 0x80070000;
          if ( byte_18002B7D8 )
            DmRevertToSelf();
          byte_18002B7D8 = 0;
          CoUninitialize();
          if ( hKey )
            RegCloseKey(hKey);
          if ( phkResult )
            RegCloseKey(phkResult);
          return (unsigned int)v30;
        }
        else
        {
          v34 = hKey;
          if ( hKey )
          {
            v35 = GetLastError();
            RegCloseKey(v34);
            SetLastError(v35);
          }
          hKey = 0;
          v36 = RegOpenKeyExW(phkResult, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM", 0, 0x20019u, &hKey);
          if ( v36 )
          {
            if ( (unsigned int)dword_18002B0C0 > 5
              && (qword_18002B0D0 & 0x400000000000LL) != 0
              && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
            {
              if ( v36 > 0 )
                v39 = (unsigned __int16)v36 | 0x80070000;
              else
                v39 = v36;
              LODWORD(v55) = v39;
              v57 = L"Blue MDM Root Not Found";
              v56 = (const unsigned __int16 *)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\resourcemanagermigrator.cpp";
              v53 = 115;
              v54 = L"ResourceManagerMigrator::Migrate";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                qword_18002B0D8,
                (__int64)byte_180025B73,
                v37,
                v38,
                &v54,
                (__int64)&v53,
                &v56,
                &v57,
                (__int64)&v55);
            }
            if ( v36 > 0 )
              v36 = (unsigned __int16)v36 | 0x80070000;
            if ( byte_18002B7D8 )
              DmRevertToSelf();
            byte_18002B7D8 = 0;
            CoUninitialize();
            if ( hKey )
              RegCloseKey(hKey);
            if ( phkResult )
              RegCloseKey(phkResult);
            return (unsigned int)v36;
          }
          else
          {
            v40 = MirgateWmiResource(hKey, L"MDM_WirelessProfileXml", L"Profiles\\MDM_WirelessProfileXml", v17);
            if ( v40 < 0
              && (unsigned int)dword_18002B0C0 > 5
              && (qword_18002B0D0 & 0x400000000000LL) != 0
              && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
            {
              LODWORD(v55) = v40;
              v57 = L"WMI WiFi Migration Failure";
              v56 = (const unsigned __int16 *)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\resourcemanagermigrator.cpp";
              LODWORD(v54) = 125;
              v59 = L"ResourceManagerMigrator::Migrate";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                qword_18002B0D0,
                (__int64)byte_180025B11,
                (unsigned int)v40,
                v41,
                &v59,
                (__int64)&v54,
                &v56,
                &v57,
                (__int64)&v55);
            }
            v42 = MirgateWmiResource(hKey, L"MSFT_VpnConnection", L"Profiles\\MSFT_VpnConnection", v17);
            if ( v42 < 0
              && (unsigned int)dword_18002B0C0 > 5
              && (qword_18002B0D0 & 0x400000000000LL) != 0
              && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
            {
              LODWORD(v54) = v42;
              v59 = L"WMI VPN Migration Failure";
              v57 = (const unsigned __int16 *)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\resourcemanagermigrator.cpp";
              LODWORD(v55) = 134;
              v56 = L"ResourceManagerMigrator::Migrate";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                qword_18002B0D0,
                (__int64)&unk_180025AB0,
                (unsigned int)v42,
                v43,
                &v56,
                (__int64)&v55,
                &v57,
                &v59,
                (__int64)&v54);
            }
            v44 = MirgateWmiResource(hKey, L"MDM_Certificate", L"Profiles\\MDM_Certificate", v17);
            v46 = (unsigned int)v44;
            if ( v44 < 0
              && (unsigned int)dword_18002B0C0 > 5
              && (qword_18002B0D0 & 0x400000000000LL) != 0
              && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
            {
              LODWORD(v54) = v44;
              v59 = L"WMI Certificate Migration Failure";
              v57 = (const unsigned __int16 *)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\resourcemanagermigrator.cpp";
              LODWORD(v55) = 143;
              v56 = L"ResourceManagerMigrator::Migrate";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                qword_18002B0D0,
                (__int64)&byte_180025A47,
                (unsigned int)v44,
                v45,
                &v56,
                (__int64)&v55,
                &v57,
                &v59,
                (__int64)&v54);
            }
            v47 = MigrateWmiAppInstallJob(hKey, v17, v46);
            v49 = (unsigned int)v47;
            if ( v47 < 0
              && (unsigned int)dword_18002B0C0 > 5
              && (qword_18002B0D0 & 0x400000000000LL) != 0
              && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
            {
              LODWORD(v54) = v47;
              v59 = L"WMI AppInstallJob Migration Failure";
              v57 = (const unsigned __int16 *)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\resourcemanagermigrator.cpp";
              LODWORD(v55) = 152;
              v56 = L"ResourceManagerMigrator::Migrate";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                qword_18002B0D0,
                (__int64)&dword_1800259DC,
                (unsigned int)v47,
                v48,
                &v56,
                (__int64)&v55,
                &v57,
                &v59,
                (__int64)&v54);
            }
            v50 = MigrateWmiScep(hKey, v17, v49);
            if ( v50 < 0
              && (unsigned int)dword_18002B0C0 > 5
              && (qword_18002B0D0 & 0x400000000000LL) != 0
              && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
            {
              LODWORD(v54) = v50;
              v59 = L"WMI SCEP Migration Failure";
              v57 = (const unsigned __int16 *)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\resourcemanagermigrator.cpp";
              LODWORD(v55) = 161;
              v56 = L"ResourceManagerMigrator::Migrate";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                qword_18002B0D8,
                (__int64)word_18002597A,
                v51,
                v52,
                &v56,
                (__int64)&v55,
                &v57,
                &v59,
                (__int64)&v54);
            }
            if ( (unsigned int)dword_18002B0C0 > 5
              && (qword_18002B0D0 & 0x400000000000LL) != 0
              && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
            {
              v59 = L"Finished";
              v57 = (const unsigned __int16 *)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\resourcemanagermigrator.cpp";
              LODWORD(v54) = 164;
              v56 = L"ResourceManagerMigrator::Migrate";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                qword_18002B0D8,
                (__int64)byte_18002593B,
                v51,
                v52,
                &v56,
                (__int64)&v54,
                &v57,
                &v59);
            }
            if ( byte_18002B7D8 )
              DmRevertToSelf();
            byte_18002B7D8 = 0;
            CoUninitialize();
            if ( hKey )
              RegCloseKey(hKey);
            if ( phkResult )
              RegCloseKey(phkResult);
            return (unsigned int)v50;
          }
        }
      }
      else
      {
        if ( (unsigned int)dword_18002B0C0 > 5
          && (qword_18002B0D0 & 0x400000000000LL) != 0
          && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
        {
          v53 = v25;
          v56 = L"Error impersonating user";
          v54 = (const unsigned __int16 *)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\resourcemanagermigrator.cpp";
          LODWORD(v61) = 84;
          v55 = (const char *)L"ResourceManagerMigrator::Migrate";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            qword_18002B0D0,
            (__int64)&dword_180025C3C,
            v26,
            v27,
            (const unsigned __int16 **)&v55,
            (__int64)&v61,
            &v54,
            &v56,
            (__int64)&v53);
        }
        CoUninitialize();
        if ( hKey )
          RegCloseKey(hKey);
        if ( phkResult )
          RegCloseKey(phkResult);
        return (unsigned int)v25;
      }
    }
    else
    {
      if ( (unsigned int)dword_18002B0C0 > 5
        && (qword_18002B0D0 & 0x400000000000LL) != 0
        && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
      {
        v53 = v21;
        v54 = L"Error in CoInitializeEx";
        v55 = "onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\resourcemanagermigrator.cpp";
        LODWORD(v61) = 69;
        v56 = L"ResourceManagerMigrator::Migrate";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          qword_18002B0D0,
          (__int64)&dword_180025C9C,
          v22,
          v23,
          &v56,
          (__int64)&v61,
          (const unsigned __int16 **)&v55,
          &v54,
          (__int64)&v53);
      }
      if ( hKey )
        RegCloseKey(hKey);
      if ( phkResult )
        RegCloseKey(phkResult);
      return (unsigned int)v21;
    }
  }
}

```

## disassembly

```asm
0x18000f5c4  mov     r11, rsp
0x18000f5c7  mov     [r11+10h], rbx
0x18000f5cb  mov     [r11+18h], rsi
0x18000f5cf  push    rdi
0x18000f5d0  push    r12
0x18000f5d2  push    r13
0x18000f5d4  push    r14
0x18000f5d6  push    r15
0x18000f5d8  sub     rsp, 0E0h
0x18000f5df  mov     rax, cs:__security_cookie
0x18000f5e6  xor     rax, rsp
0x18000f5e9  mov     [rsp+108h+var_38], rax
0x18000f5f1  mov     rsi, rcx
0x18000f5f4  xor     r13d, r13d
0x18000f5f7  mov     [r11-80h], r13
0x18000f5fb  mov     [rsp+108h+hKey], r13
0x18000f600  mov     eax, cs:dword_18002B0C0
0x18000f606  mov     rdi, 400000000000h
0x18000f610  cmp     eax, 5
0x18000f613  jbe     short loc_18000F693
0x18000f615  mov     rcx, cs:qword_18002B0D8
0x18000f61c  mov     rax, cs:qword_18002B0D0
0x18000f623  test    rdi, rax
0x18000f626  jz      short loc_18000F693
0x18000f628  mov     rax, rcx
0x18000f62b  and     rax, rdi
0x18000f62e  cmp     rax, rcx
0x18000f631  jnz     short loc_18000F693
0x18000f633  lea     rax, aStarted; "Started"
0x18000f63a  mov     [rsp+108h+var_B0], rax
0x18000f63f  lea     r14, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000f646  mov     [rsp+108h+var_A8], r14
0x18000f64b  mov     [rsp+108h+var_B8], 33h ; '3'
0x18000f653  lea     r15, aResourcemanage_0; "ResourceManagerMigrator::Migrate"
0x18000f65a  mov     [r11-78h], r15
0x18000f65e  lea     rax, [rsp+108h+var_B0]
0x18000f663  mov     [rsp+108h+var_D0], rax
0x18000f668  lea     rax, [rsp+108h+var_A8]
0x18000f66d  mov     [rsp+108h+var_D8], rax
0x18000f672  lea     rax, [rsp+108h+var_B8]
0x18000f677  mov     [rsp+108h+var_E0], rax
0x18000f67c  lea     rax, [r11-78h]
0x18000f680  mov     [rsp+108h+var_E8], rax
0x18000f685  lea     rdx, word_180025D4E
0x18000f68c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000f691  jmp     short loc_18000F6A1
0x18000f693  lea     r15, aResourcemanage_0; "ResourceManagerMigrator::Migrate"
0x18000f69a  lea     r14, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000f6a1  mov     rdx, cs:?userSidRtv@@3PEBGEB; ushort const * const userSidRtv
0x18000f6a8  xorps   xmm0, xmm0
0x18000f6ab  movups  xmmword ptr [rsp+108h+S1], xmm0
0x18000f6b3  mov     [rsp+108h+var_48], r13
0x18000f6bb  mov     [rsp+108h+var_40], r13
0x18000f6c3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f6c7  inc     r8
0x18000f6ca  cmp     [rdx+r8*2], r13w
0x18000f6cf  jnz     short loc_18000F6C7
0x18000f6d1  lea     rcx, [rsp+108h+S1]
0x18000f6d9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f6de  lea     r8, [rsp+108h+S1]
0x18000f6e6  lea     rdx, [rsp+108h+var_70]
0x18000f6ee  mov     rcx, rsi
0x18000f6f1  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18000f6f6  mov     rbx, [rsp+108h+var_60]
0x18000f6fe  cmp     [rbx+19h], r13b
0x18000f702  jnz     short loc_18000F75B
0x18000f704  lea     rdx, [rbx+20h]
0x18000f708  mov     r12, [rdx+10h]
0x18000f70c  cmp     qword ptr [rdx+18h], 7
0x18000f711  jbe     short loc_18000F716
0x18000f713  mov     rdx, [rdx]; S2
0x18000f716  mov     r13, [rsp+108h+var_48]
0x18000f71e  lea     rcx, [rsp+108h+S1]
0x18000f726  cmp     [rsp+108h+var_40], 7
0x18000f72f  cmova   rcx, [rsp+108h+S1]; S1
0x18000f738  mov     r8, r13
0x18000f73b  cmp     r12, r13
0x18000f73e  cmovb   r8, r12; N
0x18000f742  call    wmemcmp
0x18000f747  test    eax, eax
0x18000f749  jnz     loc_18000F851
0x18000f74f  cmp     r13, r12
0x18000f752  jnb     loc_18000F861
0x18000f758  xor     r13d, r13d
0x18000f75b  mov     rbx, [rsi]
0x18000f75e  lea     rcx, [rsp+108h+S1]; void *
0x18000f766  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f76b  cmp     rbx, [rsi]
0x18000f76e  jnz     loc_18000F824
0x18000f774  mov     eax, cs:dword_18002B0C0
0x18000f77a  cmp     eax, 5
0x18000f77d  jbe     short loc_18000F7F6
0x18000f77f  mov     rcx, cs:qword_18002B0D8
0x18000f786  mov     rax, cs:qword_18002B0D0
0x18000f78d  test    rdi, rax
0x18000f790  jz      short loc_18000F7F6
0x18000f792  mov     rax, rcx
0x18000f795  and     rax, rdi
0x18000f798  cmp     rax, rcx
0x18000f79b  jnz     short loc_18000F7F6
0x18000f79d  lea     rax, aUnableToGetUse; "Unable to get UserSid"
0x18000f7a4  mov     [rsp+108h+var_B0], rax
0x18000f7a9  mov     [rsp+108h+var_A8], r14
0x18000f7ae  mov     [rsp+108h+var_B8], 3Ah ; ':'
0x18000f7b6  mov     [rsp+108h+var_78], r15
0x18000f7be  lea     rax, [rsp+108h+var_B0]
0x18000f7c3  mov     [rsp+108h+var_D0], rax
0x18000f7c8  lea     rax, [rsp+108h+var_A8]
0x18000f7cd  mov     [rsp+108h+var_D8], rax
0x18000f7d2  lea     rax, [rsp+108h+var_B8]
0x18000f7d7  mov     [rsp+108h+var_E0], rax
0x18000f7dc  lea     rax, [rsp+108h+var_78]
0x18000f7e4  mov     [rsp+108h+var_E8], rax
0x18000f7e9  lea     rdx, byte_180025CFB
0x18000f7f0  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000f7f5  nop
0x18000f7f6  mov     rcx, [rsp+108h+hKey]; hKey
0x18000f7fb  test    rcx, rcx
0x18000f7fe  jz      short loc_18000F807
0x18000f800  call    cs:__imp_RegCloseKey
0x18000f806  nop
0x18000f807  mov     rcx, [rsp+108h+phkResult]; hKey
0x18000f80f  test    rcx, rcx
0x18000f812  jz      short loc_18000F81A
0x18000f814  call    cs:__imp_RegCloseKey
0x18000f81a  mov     eax, 80004005h
0x18000f81f  jmp     loc_180010139
0x18000f824  lea     r9, [rbx+40h]
0x18000f828  add     rsi, 10h
0x18000f82c  cmp     rsi, r9
0x18000f82f  jz      short loc_18000F891
0x18000f831  mov     rdx, [r9+10h]
0x18000f835  cmp     qword ptr [r9+18h], 7
0x18000f83a  jbe     short loc_18000F83F
0x18000f83c  mov     r9, [r9]
0x18000f83f  cmp     rdx, [rsi+18h]
0x18000f843  ja      short loc_18000F889
0x18000f845  cmp     qword ptr [rsi+18h], 7
0x18000f84a  jbe     short loc_18000F869
0x18000f84c  mov     r12, [rsi]
0x18000f84f  jmp     short loc_18000F86C
0x18000f851  xor     r13d, r13d
0x18000f854  test    eax, eax
0x18000f856  js      loc_18000F75B
0x18000f85c  jmp     loc_18000F75E
0x18000f861  xor     r13d, r13d
0x18000f864  jmp     loc_18000F75E
0x18000f869  mov     r12, rsi
0x18000f86c  mov     [rsi+10h], rdx
0x18000f870  lea     rbx, [rdx+rdx]
0x18000f874  mov     r8, rbx; Size
0x18000f877  mov     rdx, r9; Src
0x18000f87a  mov     rcx, r12; void *
0x18000f87d  call    memmove_0
0x18000f882  mov     [rbx+r12], r13w
0x18000f887  jmp     short loc_18000F891
0x18000f889  mov     rcx, rsi
0x18000f88c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000f891  xor     edx, edx; dwCoInit
0x18000f893  xor     ecx, ecx; pvReserved
0x18000f895  call    cs:__imp_CoInitializeEx
0x18000f89b  mov     ebx, eax
0x18000f89d  test    eax, eax
0x18000f89f  jns     loc_18000F964
0x18000f8a5  mov     ecx, cs:dword_18002B0C0
0x18000f8ab  cmp     ecx, 5
0x18000f8ae  jbe     loc_18000F939
0x18000f8b4  mov     rdx, cs:qword_18002B0D8
0x18000f8bb  mov     rcx, cs:qword_18002B0D0
0x18000f8c2  test    rdi, rcx
0x18000f8c5  jz      short loc_18000F939
0x18000f8c7  mov     rax, rdx
0x18000f8ca  and     rax, rdi
0x18000f8cd  cmp     rax, rdx
0x18000f8d0  jnz     short loc_18000F939
0x18000f8d2  mov     [rsp+108h+var_B8], ebx
0x18000f8d6  lea     rax, aErrorInCoiniti; "Error in CoInitializeEx"
0x18000f8dd  mov     [rsp+108h+var_B0], rax
0x18000f8e2  mov     [rsp+108h+var_A8], r14
0x18000f8e7  mov     dword ptr [rsp+108h+var_78], 45h ; 'E'
0x18000f8f2  mov     [rsp+108h+var_A0], r15
0x18000f8f7  lea     rax, [rsp+108h+var_B8]
0x18000f8fc  mov     [rsp+108h+var_C8], rax
0x18000f901  lea     rax, [rsp+108h+var_B0]
0x18000f906  mov     [rsp+108h+var_D0], rax
0x18000f90b  lea     rax, [rsp+108h+var_A8]
0x18000f910  mov     [rsp+108h+var_D8], rax
0x18000f915  lea     rax, [rsp+108h+var_78]
0x18000f91d  mov     [rsp+108h+var_E0], rax
0x18000f922  lea     rax, [rsp+108h+var_A0]
0x18000f927  mov     [rsp+108h+var_E8], rax
0x18000f92c  lea     rdx, dword_180025C9C
0x18000f933  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000f938  nop
0x18000f939  mov     rcx, [rsp+108h+hKey]; hKey
0x18000f93e  test    rcx, rcx
0x18000f941  jz      short loc_18000F94A
0x18000f943  call    cs:__imp_RegCloseKey
0x18000f949  nop
0x18000f94a  mov     rcx, [rsp+108h+phkResult]; hKey
0x18000f952  test    rcx, rcx
0x18000f955  jz      short loc_18000F95D
0x18000f957  call    cs:__imp_RegCloseKey
0x18000f95d  mov     eax, ebx
0x18000f95f  jmp     loc_180010139
0x18000f964  mov     byte ptr [rsp+108h+var_78+1], 1
0x18000f96c  cmp     qword ptr [rsi+18h], 7
0x18000f971  jbe     short loc_18000F978
0x18000f973  mov     rcx, [rsi]
0x18000f976  jmp     short loc_18000F97B
0x18000f978  mov     rcx, rsi
0x18000f97b  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18000f981  mov     ebx, eax
0x18000f983  test    eax, eax
0x18000f985  jns     loc_18000FA51
0x18000f98b  mov     ecx, cs:dword_18002B0C0
0x18000f991  cmp     ecx, 5
0x18000f994  jbe     loc_18000FA1F
0x18000f99a  mov     rdx, cs:qword_18002B0D8
0x18000f9a1  mov     rcx, cs:qword_18002B0D0
0x18000f9a8  test    rdi, rcx
0x18000f9ab  jz      short loc_18000FA1F
0x18000f9ad  mov     rax, rdx
0x18000f9b0  and     rax, rdi
0x18000f9b3  cmp     rax, rdx
0x18000f9b6  jnz     short loc_18000FA1F
0x18000f9b8  mov     [rsp+108h+var_B8], ebx
0x18000f9bc  lea     rax, aErrorImpersona; "Error impersonating user"
0x18000f9c3  mov     [rsp+108h+var_A0], rax
0x18000f9c8  mov     [rsp+108h+var_B0], r14
0x18000f9cd  mov     dword ptr [rsp+108h+var_78], 54h ; 'T'
0x18000f9d8  mov     [rsp+108h+var_A8], r15
0x18000f9dd  lea     rax, [rsp+108h+var_B8]
0x18000f9e2  mov     [rsp+108h+var_C8], rax
0x18000f9e7  lea     rax, [rsp+108h+var_A0]
0x18000f9ec  mov     [rsp+108h+var_D0], rax
0x18000f9f1  lea     rax, [rsp+108h+var_B0]
0x18000f9f6  mov     [rsp+108h+var_D8], rax
0x18000f9fb  lea     rax, [rsp+108h+var_78]
0x18000fa03  mov     [rsp+108h+var_E0], rax
0x18000fa08  lea     rax, [rsp+108h+var_A8]
0x18000fa0d  mov     [rsp+108h+var_E8], rax
0x18000fa12  lea     rdx, dword_180025C3C
0x18000fa19  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000fa1e  nop
0x18000fa1f  call    cs:__imp_CoUninitialize
0x18000fa25  nop
0x18000fa26  mov     rcx, [rsp+108h+hKey]; hKey
0x18000fa2b  test    rcx, rcx
0x18000fa2e  jz      short loc_18000FA37
0x18000fa30  call    cs:__imp_RegCloseKey
0x18000fa36  nop
0x18000fa37  mov     rcx, [rsp+108h+phkResult]; hKey
0x18000fa3f  test    rcx, rcx
0x18000fa42  jz      short loc_18000FA4A
0x18000fa44  call    cs:__imp_RegCloseKey
0x18000fa4a  mov     eax, ebx
0x18000fa4c  jmp     loc_180010139
0x18000fa51  cmp     ebx, 1
0x18000fa54  setnz   cs:byte_18002B7D8
0x18000fa5b  mov     byte ptr [rsp+108h+var_B8+1], 1
0x18000fa60  mov     r12, [rsp+108h+phkResult]
0x18000fa68  test    r12, r12
0x18000fa6b  jz      short loc_18000FA86
0x18000fa6d  call    cs:__imp_GetLastError
0x18000fa73  mov     ebx, eax
0x18000fa75  mov     rcx, r12; hKey
0x18000fa78  call    cs:__imp_RegCloseKey
0x18000fa7e  mov     ecx, ebx; dwErrCode
0x18000fa80  call    cs:__imp_SetLastError
0x18000fa86  mov     [rsp+108h+phkResult], r13
0x18000fa8e  lea     rdx, [rsp+108h+phkResult]; phkResult
0x18000fa96  mov     ecx, 20019h; samDesired
0x18000fa9b  call    cs:__imp_RegOpenCurrentUser
0x18000faa1  mov     ebx, eax
0x18000faa3  test    eax, eax
0x18000faa5  jz      loc_18000FB9D
0x18000faab  mov     eax, cs:dword_18002B0C0
0x18000fab1  cmp     eax, 5
0x18000fab4  jbe     loc_18000FB48
0x18000faba  mov     rcx, cs:qword_18002B0D8
0x18000fac1  mov     rax, cs:qword_18002B0D0
0x18000fac8  test    rdi, rax
0x18000facb  jz      short loc_18000FB48
0x18000facd  mov     rax, rcx
0x18000fad0  and     rax, rdi
0x18000fad3  cmp     rax, rcx
0x18000fad6  jnz     short loc_18000FB48
0x18000fad8  test    ebx, ebx
0x18000fada  jg      short loc_18000FAE0
0x18000fadc  mov     eax, ebx
0x18000fade  jmp     short loc_18000FAE8
0x18000fae0  movzx   eax, bx
0x18000fae3  or      eax, 80070000h
0x18000fae8  mov     [rsp+108h+var_B8], eax
0x18000faec  lea     rax, aOpeningHkcuFor; "Opening HKCU for impersonated user"
0x18000faf3  mov     [rsp+108h+var_A0], rax
0x18000faf8  mov     [rsp+108h+var_B0], r14
0x18000fafd  mov     dword ptr [rsp+108h+var_A8], 69h ; 'i'
0x18000fb05  mov     [rsp+108h+var_98], r15
  ... truncated ...
```
