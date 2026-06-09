# SendAlertNotificationInProvisioning(ushort const *,OMADMALERTINFO * const,ushort const *)

- ea: `0x180011bc0`
- end: `0x180012686`
- name: `?SendAlertNotificationInProvisioning@@YAJPEBGQEAUOMADMALERTINFO@@0@Z`
- size: `2758`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct OMADMALERTINFO *const, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a6a0`
- `0x18001a7d0`
- `0x18001a940`

## callees

- `0x1800031b0`
- `0x180003688`
- `0x180003db8`
- `0x180006140`
- `0x18000979c`
- `0x180009e58`
- `0x180009ec8`
- `0x180009ff8`
- `0x180011bc0`
- `0x180013d44`
- `0x180013df4`
- `0x180014570`
- `0x180014698`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011f4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011f4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011cff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011cff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ce0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ce0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011cf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011d7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011f03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001264e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011cf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011d7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011f03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001264e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011cb0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011cb0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011dbb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011e8d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011dbb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011e8d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001200a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180012049`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180012089`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001200a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180012049`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180012089`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180012445`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180012491`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800124de`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180012445`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180012491`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800124de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800120f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001213d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180012186`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800122ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180012344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180012399`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800120f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001213d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180012186`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800122ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180012344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180012399`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011f6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011f6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800120cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012160`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012199`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012275`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800122bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012311`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012367`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800123ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800123c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800124f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012507`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800120cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012160`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012199`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012275`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800122bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012311`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012367`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800123ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800123c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800124f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012507`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125da`

## string_xrefs

- `0x180011dad`: `AlertListenerClassID`
- `0x180011e7f`: `AlertListenerClassID`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SendAlertNotificationInProvisioning(
        unsigned __int16 *a1,
        struct OMADMALERTINFO *const a2,
        const unsigned __int16 *a3)
{
  HSTRING v5; // r12
  const WCHAR *v6; // rdx
  __int64 v7; // rcx
  int v8; // edi
  HKEY v9; // r13
  HKEY v10; // r15
  HKEY v11; // r12
  DWORD LastError; // ebx
  __int64 v13; // r9
  __int64 v15; // rcx
  size_t v16; // rdi
  void *v17; // rax
  void *v18; // rcx
  _QWORD *v19; // rax
  char *v20; // rbx
  LSTATUS ValueW; // eax
  __int64 v22; // rcx
  int v23; // ebx
  __int64 v24; // r9
  const WCHAR *v25; // r15
  __int64 v26; // rbx
  unsigned __int64 v27; // rdi
  const OLECHAR *v28; // rcx
  const OLECHAR *v29; // rcx
  unsigned int v30; // eax
  __int64 v31; // rcx
  const OLECHAR *v32; // rcx
  const WCHAR *v33; // rcx
  __int64 v34; // rdx
  const WCHAR *v35; // rcx
  __int64 v36; // rdx
  unsigned int v37; // eax
  __int64 v38; // rcx
  const WCHAR *v39; // rcx
  unsigned int v40; // eax
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rdx
  unsigned int v44; // eax
  __int64 v45; // rcx
  __int64 v46; // rcx
  HSTRING v47; // rbx
  __int64 v48; // rcx
  unsigned int ActivationFactory; // eax
  __int64 v50; // rcx
  HSTRING v51; // rbx
  __int64 v52; // rcx
  __int64 v53; // rcx
  char v54; // al
  __int64 v55; // rcx
  __int64 v56; // [rsp+40h] [rbp-148h] BYREF
  HSTRING v57; // [rsp+48h] [rbp-140h] BYREF
  HSTRING v58; // [rsp+50h] [rbp-138h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-130h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-128h] BYREF
  DWORD pdwType; // [rsp+64h] [rbp-124h] BYREF
  PVOID pvData[2]; // [rsp+68h] [rbp-120h] BYREF
  char *v63; // [rsp+78h] [rbp-110h]
  __int64 v64; // [rsp+80h] [rbp-108h] BYREF
  _OWORD v65[2]; // [rsp+90h] [rbp-F8h] BYREF
  GUID pclsid; // [rsp+B0h] [rbp-D8h] BYREF
  __int128 v67; // [rsp+C0h] [rbp-C8h]
  LPCOLESTR lpsz[2]; // [rsp+D0h] [rbp-B8h] BYREF
  __int64 v69; // [rsp+E0h] [rbp-A8h]
  unsigned __int64 v70; // [rsp+E8h] [rbp-A0h]
  LPCWSTR lpSubKey[2]; // [rsp+F0h] [rbp-98h] BYREF
  __int64 v72; // [rsp+100h] [rbp-88h]
  unsigned __int64 v73; // [rsp+108h] [rbp-80h]
  HSTRING string; // [rsp+110h] [rbp-78h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+118h] [rbp-70h] BYREF
  HKEY phkResult[2]; // [rsp+130h] [rbp-58h] BYREF
  __int64 v77; // [rsp+140h] [rbp-48h]

  v5 = (HSTRING)a1;
  v58 = (HSTRING)a1;
  hKey = 0;
  pdwType = 1;
  pcbData = 0;
  *(_OWORD *)lpSubKey = 0;
  v72 = 0;
  v73 = 0;
  std::wstring::_Construct<1,unsigned short const *>(lpSubKey, L"software\\microsoft\\enrollments\\", 31);
  std::wstring::append(lpSubKey, v5);
  std::wstring::append(lpSubKey, L"\\AlertListener");
  phkResult[0] = (HKEY)&hKey;
  phkResult[1] = 0;
  LOBYTE(v77) = 1;
  v6 = (const WCHAR *)lpSubKey;
  if ( v73 > 7 )
    v6 = lpSubKey[0];
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20119u, &phkResult[1]);
  if ( (_BYTE)v77 )
  {
    v9 = phkResult[1];
    v10 = phkResult[0];
    v11 = *(HKEY *)phkResult[0];
    if ( *(_QWORD *)phkResult[0] )
    {
      LastError = GetLastError();
      RegCloseKey(v11);
      SetLastError(LastError);
    }
    *(_QWORD *)v10 = v9;
    v5 = v58;
  }
  if ( v8 )
  {
    if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
    {
      if ( v8 > 0 )
        v13 = (unsigned __int16)v8 | 0x80070000;
      else
        v13 = (unsigned int)v8;
      McTemplateU0zq_EventWriteTransfer(v7, FunctionReturnValueEvent, a3, v13);
    }
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    std::wstring::~wstring(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v8;
  }
  else if ( RegGetValueW(hKey, 0, L"AlertListenerClassID", 2u, &pdwType, 0, &pcbData) == 2 )
  {
    if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v15, FunctionReturnValueEvent, a3, 0);
    std::wstring::~wstring(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    v16 = pcbData;
    *(_OWORD *)pvData = 0;
    v63 = 0;
    if ( pcbData )
    {
      if ( pcbData < 0x1000uLL )
      {
        v19 = operator new(pcbData);
      }
      else
      {
        if ( (unsigned __int64)pcbData + 39 < pcbData )
          __scrt_throw_std_bad_array_new_length();
        v17 = operator new(pcbData + 39LL);
        v18 = v17;
        if ( !v17 )
          __fastfail(5u);
        v19 = (_QWORD *)(((unsigned __int64)v17 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v19 - 1) = v18;
      }
      pvData[0] = v19;
      v20 = (char *)v19 + v16;
      v63 = (char *)v19 + v16;
      memset_0(v19, 0, v16);
      pvData[1] = v20;
      v64 = 0;
      std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v64);
    }
    ValueW = RegGetValueW(hKey, 0, L"AlertListenerClassID", 2u, &pdwType, pvData[0], &pcbData);
    v23 = ValueW;
    if ( ValueW )
    {
      if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
      {
        if ( ValueW > 0 )
          v24 = (unsigned __int16)ValueW | 0x80070000;
        else
          v24 = (unsigned int)ValueW;
        McTemplateU0zq_EventWriteTransfer(v22, FunctionReturnValueEvent, a3, v24);
      }
      if ( v23 > 0 )
        v23 = (unsigned __int16)v23 | 0x80070000;
    }
    else
    {
      v56 = 0;
      v25 = (const WCHAR *)pvData[0];
      v26 = -1;
      v27 = -1;
      do
        ++v27;
      while ( *((_WORD *)pvData[0] + v27) );
      if ( v27 > 0xFFFFFFFF )
      {
        LODWORD(v27) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(v25, v27, &hstringHeader, &string);
      *(_OWORD *)lpsz = 0;
      v69 = 0;
      v70 = 0;
      std::wstring::_Construct<1,unsigned short const *>(lpsz, L"{", 1);
      std::wstring::append(lpsz, v5);
      std::wstring::append(lpsz, L"}");
      pclsid = 0;
      v67 = 0;
      v28 = (const OLECHAR *)lpsz;
      if ( v70 > 7 )
        v28 = lpsz[0];
      if ( CLSIDFromString(v28, &pclsid) >= 0 )
      {
        WindowsDeleteString(0);
        v57 = 0;
        v33 = (const WCHAR *)*((_QWORD *)a2 + 2);
        v34 = -1;
        do
          ++v34;
        while ( v33[v34] );
        if ( WindowsCreateString(v33, v34, &v57) >= 0 )
        {
          *(_QWORD *)&v67 = v57;
          *(_OWORD *)phkResult = 0;
          v77 = 0;
          if ( (int)StringCchPrintfW((unsigned __int16 *)phkResult, 0xCu, L"%i", *((unsigned int *)a2 + 12)) >= 0 )
          {
            v58 = 0;
            WindowsDeleteString(0);
            v58 = 0;
            v42 = -1;
            do
              ++v42;
            while ( *((_WORD *)phkResult + v42) );
            if ( WindowsCreateString((PCNZWCH)phkResult, v42, &v58) >= 0 )
            {
              *((_QWORD *)&v67 + 1) = v58;
              if ( (int)RoGetActivationFactory(string, &GUID_2596a876_8ba6_45c0_a7f4_76624f5e0f47, &v56) >= 0 )
              {
                v54 = Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits;
                if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 2) != 0 )
                {
                  McTemplateU0z_EventWriteTransfer(WP_OMADMAPI_PROVIDER_Context, InternalAlertOperation, v25);
                  v54 = Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits;
                }
                if ( (v54 & 1) != 0 )
                  McTemplateU0zq_EventWriteTransfer(v46, FunctionReturnValueEvent, a3, 0);
                v65[0] = pclsid;
                v65[1] = v67;
                v23 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v56 + 48LL))(v56, v65);
                WindowsDeleteString(v58);
                v58 = 0;
                WindowsDeleteString(v57);
                v57 = 0;
                std::wstring::~wstring(lpsz);
                v55 = v56;
                if ( v56 )
                {
                  v56 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
                }
              }
              else
              {
                if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
                {
                  v47 = string;
                  v48 = v56;
                  if ( v56 )
                  {
                    v56 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
                  }
                  ActivationFactory = RoGetActivationFactory(v47, &GUID_2596a876_8ba6_45c0_a7f4_76624f5e0f47, &v56);
                  McTemplateU0zq_EventWriteTransfer(v50, FunctionReturnValueEvent, a3, ActivationFactory);
                }
                v51 = string;
                v52 = v56;
                if ( v56 )
                {
                  v56 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
                }
                v23 = RoGetActivationFactory(v51, &GUID_2596a876_8ba6_45c0_a7f4_76624f5e0f47, &v56);
                WindowsDeleteString(v58);
                v58 = 0;
                WindowsDeleteString(v57);
                v57 = 0;
                std::wstring::~wstring(lpsz);
                v53 = v56;
                if ( v56 )
                {
                  v56 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
                }
              }
            }
            else
            {
              if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
              {
                WindowsDeleteString(v58);
                v58 = 0;
                v43 = -1;
                do
                  ++v43;
                while ( *((_WORD *)phkResult + v43) );
                v44 = WindowsCreateString((PCNZWCH)phkResult, v43, &v58);
                McTemplateU0zq_EventWriteTransfer(v45, FunctionReturnValueEvent, a3, v44);
              }
              WindowsDeleteString(v58);
              v58 = 0;
              do
                ++v26;
              while ( *((_WORD *)phkResult + v26) );
              v23 = WindowsCreateString((PCNZWCH)phkResult, v26, &v58);
              WindowsDeleteString(v58);
              v58 = 0;
              WindowsDeleteString(v57);
              v57 = 0;
              std::wstring::~wstring(lpsz);
            }
          }
          else
          {
            if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
            {
              v40 = StringCchPrintfW((unsigned __int16 *)phkResult, 0xCu, L"%i", *((unsigned int *)a2 + 12));
              McTemplateU0zq_EventWriteTransfer(v41, FunctionReturnValueEvent, a3, v40);
            }
            v23 = StringCchPrintfW((unsigned __int16 *)phkResult, 0xCu, L"%i", *((unsigned int *)a2 + 12));
            WindowsDeleteString(v57);
            v57 = 0;
            std::wstring::~wstring(lpsz);
          }
        }
        else
        {
          if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
          {
            WindowsDeleteString(v57);
            v57 = 0;
            v35 = (const WCHAR *)*((_QWORD *)a2 + 2);
            v36 = -1;
            do
              ++v36;
            while ( v35[v36] );
            v37 = WindowsCreateString(v35, v36, &v57);
            McTemplateU0zq_EventWriteTransfer(v38, FunctionReturnValueEvent, a3, v37);
          }
          WindowsDeleteString(v57);
          v57 = 0;
          v39 = (const WCHAR *)*((_QWORD *)a2 + 2);
          do
            ++v26;
          while ( v39[v26] );
          v23 = WindowsCreateString(v39, v26, &v57);
          WindowsDeleteString(v57);
          v57 = 0;
          std::wstring::~wstring(lpsz);
        }
      }
      else
      {
        if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
        {
          v29 = (const OLECHAR *)lpsz;
          if ( v70 > 7 )
            v29 = lpsz[0];
          v30 = CLSIDFromString(v29, &pclsid);
          McTemplateU0zq_EventWriteTransfer(v31, FunctionReturnValueEvent, a3, v30);
        }
        v32 = (const OLECHAR *)lpsz;
        if ( v70 > 7 )
          v32 = lpsz[0];
        v23 = CLSIDFromString(v32, &pclsid);
        std::wstring::~wstring(lpsz);
      }
    }
    std::vector<unsigned char>::~vector<unsigned char>(pvData);
    std::wstring::~wstring(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v23;
  }
}

```

## disassembly

```asm
0x180011bc0  mov     r11, rsp
0x180011bc3  push    rbx
0x180011bc4  push    rsi
0x180011bc5  push    rdi
0x180011bc6  push    r12
0x180011bc8  push    r13
0x180011bca  push    r14
0x180011bcc  push    r15
0x180011bce  sub     rsp, 150h
0x180011bd5  mov     rax, cs:__security_cookie
0x180011bdc  xor     rax, rsp
0x180011bdf  mov     [rsp+188h+var_40], rax
0x180011be7  mov     rsi, r8
0x180011bea  mov     r14, rdx
0x180011bed  mov     r12, rcx
0x180011bf0  mov     [rsp+188h+var_138], rcx
0x180011bf5  xor     r13d, r13d
0x180011bf8  mov     [rsp+188h+hKey], r13
0x180011bfd  mov     [rsp+188h+pdwType], 1
0x180011c05  mov     [rsp+188h+var_128], r13d
0x180011c0a  xorps   xmm0, xmm0
0x180011c0d  movups  xmmword ptr [rsp+188h+lpSubKey], xmm0
0x180011c15  mov     [r11-88h], r13
0x180011c1c  mov     [r11-80h], r13
0x180011c20  lea     r8d, [r13+1Fh]
0x180011c24  lea     rdx, aSoftwareMicros_4; "software\\microsoft\\enrollments\\"
0x180011c2b  lea     rcx, [r11-98h]
0x180011c32  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011c37  nop
0x180011c38  mov     rdx, r12; void *
0x180011c3b  lea     rcx, [rsp+188h+lpSubKey]; Src
0x180011c43  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180011c48  lea     rdx, aAlertlistener; "\\AlertListener"
0x180011c4f  lea     rcx, [rsp+188h+lpSubKey]; Src
0x180011c57  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180011c5c  lea     rax, [rsp+188h+hKey]
0x180011c61  mov     [rsp+188h+var_58], rax
0x180011c69  mov     [rsp+188h+var_58+8], r13
0x180011c71  mov     byte ptr [rsp+188h+var_48], 1
0x180011c79  lea     rdx, [rsp+188h+lpSubKey]
0x180011c81  cmp     [rsp+188h+var_80], 7
0x180011c8a  cmova   rdx, [rsp+188h+lpSubKey]; lpSubKey
0x180011c93  lea     rax, [rsp+188h+var_58+8]
0x180011c9b  mov     [rsp+188h+phkResult], rax; phkResult
0x180011ca0  mov     r9d, 20119h; samDesired
0x180011ca6  xor     r8d, r8d; ulOptions
0x180011ca9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011cb0  call    cs:__imp_RegOpenKeyExW
0x180011cb7  nop     dword ptr [rax+rax+00h]
0x180011cbc  mov     edi, eax
0x180011cbe  cmp     byte ptr [rsp+188h+var_48], r13b
0x180011cc6  jz      short loc_180011D16
0x180011cc8  mov     r13, [rsp+188h+var_58+8]
0x180011cd0  mov     r15, [rsp+188h+var_58]
0x180011cd8  mov     r12, [r15]
0x180011cdb  test    r12, r12
0x180011cde  jz      short loc_180011D0B
0x180011ce0  call    cs:__imp_GetLastError
0x180011ce7  nop     dword ptr [rax+rax+00h]
0x180011cec  mov     ebx, eax
0x180011cee  mov     rcx, r12; hKey
0x180011cf1  call    cs:__imp_RegCloseKey
0x180011cf8  nop     dword ptr [rax+rax+00h]
0x180011cfd  mov     ecx, ebx; dwErrCode
0x180011cff  call    cs:__imp_SetLastError
0x180011d06  nop     dword ptr [rax+rax+00h]
0x180011d0b  mov     [r15], r13
0x180011d0e  mov     r12, [rsp+188h+var_138]
0x180011d13  xor     r13d, r13d
0x180011d16  mov     r15d, 80070000h
0x180011d1c  test    edi, edi
0x180011d1e  jz      short loc_180011D8E
0x180011d20  jg      short loc_180011D26
0x180011d22  mov     eax, edi
0x180011d24  jmp     short loc_180011D2C
0x180011d26  movzx   eax, di
0x180011d29  or      eax, r15d
0x180011d2c  test    eax, eax
0x180011d2e  jns     short loc_180011D8E
0x180011d30  movzx   ebx, di
0x180011d33  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x180011d3a  jz      short loc_180011D5A
0x180011d3c  test    edi, edi
0x180011d3e  jg      short loc_180011D45
0x180011d40  mov     r9d, edi
0x180011d43  jmp     short loc_180011D4B
0x180011d45  mov     r9d, ebx
0x180011d48  or      r9d, r15d
0x180011d4b  mov     r8, rsi
0x180011d4e  lea     rdx, FunctionReturnValueEvent
0x180011d55  call    McTemplateU0zq_EventWriteTransfer
0x180011d5a  test    edi, edi
0x180011d5c  jle     short loc_180011D63
0x180011d5e  mov     edi, ebx
0x180011d60  or      edi, r15d
0x180011d63  lea     rcx, [rsp+188h+lpSubKey]
0x180011d6b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011d70  nop
0x180011d71  mov     rcx, [rsp+188h+hKey]; hKey
0x180011d76  test    rcx, rcx
0x180011d79  jz      short loc_180011D87
0x180011d7b  call    cs:__imp_RegCloseKey
0x180011d82  nop     dword ptr [rax+rax+00h]
0x180011d87  mov     eax, edi
0x180011d89  jmp     loc_18001265C
0x180011d8e  lea     rax, [rsp+188h+var_128]
0x180011d93  mov     [rsp+188h+pcbData], rax; pcbData
0x180011d98  mov     [rsp+188h+pvData], r13; pvData
0x180011d9d  lea     rax, [rsp+188h+pdwType]
0x180011da2  mov     [rsp+188h+phkResult], rax; pdwType
0x180011da7  mov     r9d, 2; dwFlags
0x180011dad  lea     r8, aAlertlistenerc; "AlertListenerClassID"
0x180011db4  xor     edx, edx; lpSubKey
0x180011db6  mov     rcx, [rsp+188h+hKey]; hkey
0x180011dbb  call    cs:__imp_RegGetValueW
0x180011dc2  nop     dword ptr [rax+rax+00h]
0x180011dc7  cmp     eax, 2
0x180011dca  jz      loc_18001261A
0x180011dd0  mov     edi, [rsp+188h+var_128]
0x180011dd4  xorps   xmm0, xmm0
0x180011dd7  movdqu  xmmword ptr [rsp+188h+var_120], xmm0
0x180011ddd  mov     [rsp+188h+var_110], r13
0x180011de2  test    rdi, rdi
0x180011de5  jz      short loc_180011E5B
0x180011de7  cmp     rdi, 1000h
0x180011dee  jb      short loc_180011E1D
0x180011df0  lea     rcx, [rdi+27h]; Size
0x180011df4  cmp     rcx, rdi
0x180011df7  jbe     loc_180012680
0x180011dfd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011e02  mov     rcx, rax
0x180011e05  test    rax, rax
0x180011e08  jnz     short loc_180011E0F
0x180011e0a  lea     ecx, [rax+5]
0x180011e0d  int     29h; Win8: RtlFailFast(ecx)
0x180011e0f  add     rax, 27h ; '''
0x180011e13  and     rax, 0FFFFFFFFFFFFFFE0h
0x180011e17  mov     [rax-8], rcx
0x180011e1b  jmp     short loc_180011E25
0x180011e1d  mov     rcx, rdi; Size
0x180011e20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011e25  mov     [rsp+188h+var_120], rax
0x180011e2a  lea     rbx, [rdi+rax]
0x180011e2e  mov     [rsp+188h+var_110], rbx
0x180011e33  mov     r8, rdi; Size
0x180011e36  xor     edx, edx; Val
0x180011e38  mov     rcx, rax; void *
0x180011e3b  call    memset_0
0x180011e40  mov     [rsp+188h+var_120+8], rbx
0x180011e45  mov     [rsp+188h+var_108], r13
0x180011e4d  lea     rcx, [rsp+188h+var_108]
0x180011e55  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x180011e5a  nop
0x180011e5b  mov     rax, [rsp+188h+var_120]
0x180011e60  lea     rcx, [rsp+188h+var_128]
0x180011e65  mov     [rsp+188h+pcbData], rcx; pcbData
0x180011e6a  mov     [rsp+188h+pvData], rax; pvData
0x180011e6f  lea     rax, [rsp+188h+pdwType]
0x180011e74  mov     [rsp+188h+phkResult], rax; pdwType
0x180011e79  mov     r9d, 2; dwFlags
0x180011e7f  lea     r8, aAlertlistenerc; "AlertListenerClassID"
0x180011e86  xor     edx, edx; lpSubKey
0x180011e88  mov     rcx, [rsp+188h+hKey]; hkey
0x180011e8d  call    cs:__imp_RegGetValueW
0x180011e94  nop     dword ptr [rax+rax+00h]
0x180011e99  mov     ebx, eax
0x180011e9b  test    eax, eax
0x180011e9d  jz      short loc_180011F16
0x180011e9f  test    eax, eax
0x180011ea1  jle     short loc_180011EA9
0x180011ea3  movzx   eax, bx
0x180011ea6  or      eax, r15d
0x180011ea9  test    eax, eax
0x180011eab  jns     short loc_180011F16
0x180011ead  movzx   edi, bx
0x180011eb0  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x180011eb7  jz      short loc_180011ED7
0x180011eb9  test    ebx, ebx
0x180011ebb  jg      short loc_180011EC2
0x180011ebd  mov     r9d, ebx
0x180011ec0  jmp     short loc_180011EC8
0x180011ec2  mov     r9d, edi
0x180011ec5  or      r9d, r15d
0x180011ec8  mov     r8, rsi
0x180011ecb  lea     rdx, FunctionReturnValueEvent
0x180011ed2  call    McTemplateU0zq_EventWriteTransfer
0x180011ed7  test    ebx, ebx
0x180011ed9  jle     short loc_180011EE0
0x180011edb  mov     ebx, edi
0x180011edd  or      ebx, r15d
0x180011ee0  lea     rcx, [rsp+188h+var_120]
0x180011ee5  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011eea  nop
0x180011eeb  lea     rcx, [rsp+188h+lpSubKey]
0x180011ef3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011ef8  nop
0x180011ef9  mov     rcx, [rsp+188h+hKey]; hKey
0x180011efe  test    rcx, rcx
0x180011f01  jz      short loc_180011F0F
0x180011f03  call    cs:__imp_RegCloseKey
0x180011f0a  nop     dword ptr [rax+rax+00h]
0x180011f0f  mov     eax, ebx
0x180011f11  jmp     loc_18001265C
0x180011f16  mov     [rsp+188h+var_148], r13
0x180011f1b  mov     r15, [rsp+188h+var_120]
0x180011f20  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011f24  mov     rdi, rbx
0x180011f27  inc     rdi
0x180011f2a  cmp     [r15+rdi*2], r13w
0x180011f2f  jnz     short loc_180011F27
0x180011f31  mov     eax, 0FFFFFFFFh
0x180011f36  cmp     rdi, rax
0x180011f39  jbe     short loc_180011F58
0x180011f3b  mov     edi, eax
0x180011f3d  xor     r9d, r9d; lpArguments
0x180011f40  xor     r8d, r8d; nNumberOfArguments
0x180011f43  lea     edx, [r9+1]; dwExceptionFlags
0x180011f47  mov     ecx, 0C000000Dh; dwExceptionCode
0x180011f4c  call    cs:__imp_RaiseException
0x180011f53  nop     dword ptr [rax+rax+00h]
0x180011f58  lea     r9, [rsp+188h+string]; string
0x180011f60  lea     r8, [rsp+188h+hstringHeader]; hstringHeader
0x180011f68  mov     edx, edi; length
0x180011f6a  mov     rcx, r15; sourceString
0x180011f6d  call    cs:__imp_WindowsCreateStringReference
0x180011f74  nop     dword ptr [rax+rax+00h]
0x180011f79  xorps   xmm0, xmm0
0x180011f7c  movups  xmmword ptr [rsp+188h+lpsz], xmm0
0x180011f84  mov     [rsp+188h+var_A8], r13
0x180011f8c  mov     [rsp+188h+var_A0], r13
0x180011f94  mov     edi, 1
0x180011f99  mov     r8d, edi
0x180011f9c  lea     rdx, asc_18002A0CC; "{"
0x180011fa3  lea     rcx, [rsp+188h+lpsz]
0x180011fab  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011fb0  nop
0x180011fb1  mov     rdx, r12; void *
0x180011fb4  lea     rcx, [rsp+188h+lpsz]; Src
0x180011fbc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180011fc1  lea     rdx, asc_18002A0D0; "}"
0x180011fc8  lea     rcx, [rsp+188h+lpsz]; Src
0x180011fd0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180011fd5  xorps   xmm0, xmm0
0x180011fd8  movups  xmmword ptr [rsp+188h+pclsid.Data1], xmm0
0x180011fe0  movups  [rsp+188h+var_C8], xmm0
0x180011fe8  lea     rcx, [rsp+188h+lpsz]
0x180011ff0  cmp     [rsp+188h+var_A0], 7
0x180011ff9  cmova   rcx, [rsp+188h+lpsz]; lpsz
0x180012002  lea     rdx, [rsp+188h+pclsid]; pclsid
0x18001200a  call    cs:__imp_CLSIDFromString
0x180012011  nop     dword ptr [rax+rax+00h]
0x180012016  test    eax, eax
0x180012018  jns     loc_1800120C6
0x18001201e  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, dil
0x180012025  jz      short loc_180012067
0x180012027  lea     rcx, [rsp+188h+lpsz]
0x18001202f  cmp     [rsp+188h+var_A0], 7
0x180012038  cmova   rcx, [rsp+188h+lpsz]; lpsz
0x180012041  lea     rdx, [rsp+188h+pclsid]; pclsid
0x180012049  call    cs:__imp_CLSIDFromString
0x180012050  nop     dword ptr [rax+rax+00h]
0x180012055  mov     r9d, eax
0x180012058  mov     r8, rsi
0x18001205b  lea     rdx, FunctionReturnValueEvent
0x180012062  call    McTemplateU0zq_EventWriteTransfer
0x180012067  lea     rcx, [rsp+188h+lpsz]
0x18001206f  cmp     [rsp+188h+var_A0], 7
0x180012078  cmova   rcx, [rsp+188h+lpsz]; lpsz
0x180012081  lea     rdx, [rsp+188h+pclsid]; pclsid
0x180012089  call    cs:__imp_CLSIDFromString
0x180012090  nop     dword ptr [rax+rax+00h]
0x180012095  mov     ebx, eax
0x180012097  lea     rcx, [rsp+188h+lpsz]
0x18001209f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800120a4  nop
0x1800120a5  mov     rcx, [rsp+188h+var_148]
0x1800120aa  test    rcx, rcx
0x1800120ad  jz      short loc_1800120C1
0x1800120af  mov     [rsp+188h+var_148], r13
0x1800120b4  mov     rdx, [rcx]
0x1800120b7  mov     rax, [rdx+10h]
0x1800120bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120c0  nop
0x1800120c1  jmp     loc_180011EE0
0x1800120c6  mov     [rsp+188h+var_140], r13
0x1800120cb  xor     ecx, ecx; string
0x1800120cd  call    cs:__imp_WindowsDeleteString
0x1800120d4  nop     dword ptr [rax+rax+00h]
0x1800120d9  mov     [rsp+188h+var_140], r13
0x1800120de  mov     rcx, [r14+10h]; sourceString
0x1800120e2  mov     rdx, rbx
0x1800120e5  inc     rdx; length
0x1800120e8  cmp     [rcx+rdx*2], r13w
0x1800120ed  jnz     short loc_1800120E5
0x1800120ef  lea     r8, [rsp+188h+var_140]; string
0x1800120f4  call    cs:__imp_WindowsCreateString
0x1800120fb  nop     dword ptr [rax+rax+00h]
0x180012100  test    eax, eax
0x180012102  jns     loc_1800121D9
0x180012108  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, dil
  ... truncated ...
```
