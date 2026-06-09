# CflApi::GetAllScenarioData

- ea: `0x18001dae0`
- end: `0x18001e555`
- name: `CflApi::GetAllScenarioData`
- size: `2677`
- prototype: `__int64 __fastcall(int, _QWORD *, BYTE **, DWORD *, OLECHAR **, _QWORD *, DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010a00`

## callees

- `0x180002490`
- `0x1800067a4`
- `0x1800067c4`
- `0x180010700`
- `0x180011130`
- `0x1800132a8`
- `0x18001332c`
- `0x18001dae0`
- `0x18001f948`
- `0x18002222c`
- `0x18002dffc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e30b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e30b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dea1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e17c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e31f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dea1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e17c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e31f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001dc04`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001dc97`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001de1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001def4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001dfdf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e09e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e1ec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e256`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001dc04`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001dc97`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001de1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001def4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001dfdf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e09e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e1ec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e256`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001e26b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001e26b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001db70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e1aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001db70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e1aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dbb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dd03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dd5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e035`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e173`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e3b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e44e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e4cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e51e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dbb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dd03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dd5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e035`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e173`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e3b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e44e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e4cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e51e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001dcac`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001dcac`
- `CRYPT32!CryptUnprotectData` at `0x18001e2f2`
- `CRYPT32!CryptUnprotectData` at `0x18001e2f2`

## string_xrefs

- `0x18001db9a`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001dce8`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001dd1a`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001dd34`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001dd72`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001dda5`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001ddc5`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001de4e`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001df09`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001df28`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001df4d`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001df6d`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001df8a`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001e00c`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001e0b3`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001e0e3`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001e116`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001e137`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001e299`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001e3ed`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001e407`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001e461`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001e496`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001e4e7`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001e53a`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CflApi::GetAllScenarioData(
        int a1,
        _QWORD *a2,
        BYTE **a3,
        DWORD *a4,
        OLECHAR **a5,
        _QWORD *a6,
        DWORD *a7)
{
  LSTATUS v10; // eax
  signed int v11; // ebx
  __int64 v12; // rdx
  LSTATUS ValueW; // eax
  int v15; // eax
  OLECHAR *v16; // rbx
  unsigned int v17; // eax
  HRESULT v18; // eax
  unsigned int v19; // edi
  PVOID v20; // rcx
  LSTATUS v21; // eax
  int v22; // eax
  unsigned int v23; // eax
  PVOID v24; // rdi
  LSTATUS v25; // eax
  signed int v26; // esi
  int v27; // eax
  unsigned int v28; // eax
  HKEY v29; // r15
  DWORD LastError; // r14d
  unsigned int v31; // eax
  BYTE *v32; // rsi
  unsigned int v33; // eax
  LSTATUS v34; // r14d
  unsigned __int64 v35; // r9
  const char *v36; // r9
  DWORD cbData; // eax
  DWORD v38; // r14d
  OLECHAR *v39; // rax
  PVOID v40; // rax
  __int64 v41; // rdx
  int v42; // eax
  unsigned int v43; // r14d
  __int64 v44; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-91h]
  unsigned int phkResulta; // [rsp+20h] [rbp-91h]
  unsigned int phkResultb; // [rsp+20h] [rbp-91h]
  int phkResultc; // [rsp+20h] [rbp-91h]
  unsigned int phkResultd; // [rsp+20h] [rbp-91h]
  unsigned int phkResulte; // [rsp+20h] [rbp-91h]
  unsigned int phkResultf; // [rsp+20h] [rbp-91h]
  HKEY hKey; // [rsp+40h] [rbp-71h] BYREF
  DWORD pdwType; // [rsp+48h] [rbp-69h] BYREF
  DWORD v54; // [rsp+4Ch] [rbp-65h] BYREF
  DWORD pcbData[2]; // [rsp+50h] [rbp-61h] BYREF
  DWORD v56; // [rsp+58h] [rbp-59h] BYREF
  PVOID hMem; // [rsp+60h] [rbp-51h] BYREF
  BYTE **v58; // [rsp+68h] [rbp-49h]
  DWORD *v59; // [rsp+70h] [rbp-41h]
  DWORD *v60; // [rsp+78h] [rbp-39h]
  DATA_BLOB pDataIn; // [rsp+80h] [rbp-31h] BYREF
  DATA_BLOB pDataOut; // [rsp+90h] [rbp-21h] BYREF
  GUID pclsid; // [rsp+A0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+47h]

  v59 = a4;
  v58 = a3;
  v60 = a7;
  if ( a3 )
  {
    *a3 = 0;
    *a4 = 0;
  }
  if ( a5 )
    *a5 = 0;
  if ( a6 )
  {
    *a6 = 0;
    *a7 = 0;
  }
  hKey = 0;
  v10 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ScenarioData",
          0,
          1u,
          &hKey);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 < 0 )
  {
    if ( v11 != -2147024894 )
    {
      v12 = 1697;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)(unsigned int)v11,
        phkResult);
LABEL_13:
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v11;
    }
    goto LABEL_34;
  }
  pdwType = 0;
  if ( a2 )
  {
    pclsid = 0;
    pcbData[0] = 0;
    ValueW = RegGetValueW(hKey, 0, L"ProviderId", 2u, &pdwType, 0, pcbData);
    v11 = ValueW;
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        if ( ValueW > 0 )
          v11 = (unsigned __int16)ValueW | 0x80070000;
        if ( v11 >= 0 )
          goto LABEL_13;
        v12 = 1721;
        goto LABEL_12;
      }
    }
    else
    {
      if ( pdwType != 1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6BE,
          (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
          (const char *)0x80070057LL,
          phkResult);
LABEL_150:
        if ( hKey )
          RegCloseKey(hKey);
        return 2147942487LL;
      }
      if ( !pcbData[0] || (pcbData[0] & 1) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6C1,
          (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
          (const char *)0x80070018LL,
          phkResult);
LABEL_143:
        if ( hKey )
          RegCloseKey(hKey);
        return 2147942424LL;
      }
      hMem = 0;
      v15 = CflApiNew::AllocBuffer_unsigned_short_((unsigned __int64)pcbData[0] >> 1, &hMem);
      v11 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6C4,
          (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
          (const char *)(unsigned int)v15,
          phkResult);
        v20 = hMem;
        goto LABEL_45;
      }
      v16 = (OLECHAR *)hMem;
      v17 = RegGetValueW(hKey, 0, L"ProviderId", 2u, 0, hMem, pcbData);
      if ( v17 )
      {
        v19 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x6CD,
                (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
                (const char *)v17,
                phkResult);
        goto LABEL_39;
      }
      v18 = CLSIDFromString(v16, &pclsid);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6CF,
          (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
          (const char *)(unsigned int)v18,
          phkResult);
        goto LABEL_39;
      }
      if ( v16 )
        CflFreeBuffer(v16);
    }
    if ( *a2 != *(_QWORD *)&pclsid.Data1 || a2[1] != *(_QWORD *)pclsid.Data4 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6D1,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)0x80070002LL,
        phkResult);
LABEL_34:
      if ( hKey )
        RegCloseKey(hKey);
      return 2147942402LL;
    }
  }
  v16 = 0;
  *(_QWORD *)&pclsid.Data1 = 0;
  if ( !a5 )
    goto LABEL_69;
  pdwType = 0;
  pcbData[0] = 0;
  v21 = RegGetValueW(hKey, 0, L"ScenarioId", 2u, &pdwType, 0, pcbData);
  v19 = v21;
  if ( a1 != 2 )
  {
    if ( v21 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x6EF,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
              (const char *)(unsigned int)v21,
              phkResulta);
      goto LABEL_13;
    }
    goto LABEL_59;
  }
  if ( !v21 )
  {
LABEL_59:
    if ( pdwType != 1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F1,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)0x80070057LL,
        phkResulta);
      goto LABEL_148;
    }
    if ( !pcbData[0] || (pcbData[0] & 1) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F4,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)0x80070018LL,
        phkResulta);
      goto LABEL_141;
    }
    *(_QWORD *)&pclsid.Data1 = 0;
    v22 = CflApiNew::AllocBuffer_unsigned_short_((unsigned __int64)pcbData[0] >> 1, &pclsid);
    v11 = v22;
    if ( v22 >= 0 )
    {
      v16 = *(OLECHAR **)&pclsid.Data1;
      v23 = RegGetValueW(hKey, 0, L"ScenarioId", 2u, 0, *(PVOID *)&pclsid.Data1, pcbData);
      if ( !v23 )
        goto LABEL_69;
      v19 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x6FF,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
              (const char *)v23,
              phkResultb);
LABEL_39:
      if ( v16 )
        CflFreeBuffer(v16);
      if ( hKey )
        RegCloseKey(hKey);
      return v19;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F6,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)v22,
      phkResulta);
    v20 = *(PVOID *)&pclsid.Data1;
LABEL_45:
    if ( v20 )
      CflFreeBuffer(v20);
    goto LABEL_13;
  }
  if ( v21 != 2 )
  {
    if ( v21 > 0 )
      v19 = (unsigned __int16)v21 | 0x80070000;
    if ( (v19 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E7,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)v19,
        phkResulta);
    goto LABEL_39;
  }
LABEL_69:
  v24 = 0;
  hMem = 0;
  v56 = 0;
  if ( !a6 )
    goto LABEL_92;
  pdwType = 0;
  v25 = RegGetValueW(hKey, 0, L"ScenarioContext", 8u, &pdwType, 0, &v56);
  v26 = v25;
  if ( v25 )
  {
    if ( v25 != 2 )
    {
      if ( v25 > 0 )
        v26 = (unsigned __int16)v25 | 0x80070000;
      if ( v26 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x714,
          (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
          (const char *)(unsigned int)v26,
          phkResultc);
LABEL_76:
      if ( v16 )
        CflFreeBuffer(v16);
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v26;
    }
    goto LABEL_92;
  }
  if ( pdwType != 3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x719,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)0x80070057LL,
      phkResultc);
LABEL_148:
    if ( v16 )
      CflFreeBuffer(v16);
    goto LABEL_150;
  }
  if ( !v56 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71C,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)0x80070018LL,
      phkResultc);
LABEL_141:
    if ( v16 )
      CflFreeBuffer(v16);
    goto LABEL_143;
  }
  hMem = 0;
  v27 = CflApiNew::AllocBuffer_unsigned_char_(v56);
  v19 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71E,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)v27,
      phkResultc);
    if ( hMem )
      CflSecureFreeBuffer(hMem);
    goto LABEL_39;
  }
  v24 = hMem;
  v28 = RegGetValueW(hKey, 0, L"ScenarioContext", 8u, 0, hMem, &v56);
  if ( v28 )
  {
    v26 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x727,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
            (const char *)v28,
            phkResultd);
    goto LABEL_86;
  }
LABEL_92:
  v54 = 0;
  if ( !a3 )
  {
LABEL_113:
    if ( a5 )
    {
      v39 = v16;
      v16 = 0;
      *a5 = v39;
    }
    if ( a6 )
    {
      v40 = v24;
      v24 = 0;
      *a6 = v40;
      *v60 = v56;
    }
    if ( v24 )
      CflSecureFreeBuffer(v24);
    if ( v16 )
      CflFreeBuffer(v16);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  v29 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v29);
    SetLastError(LastError);
  }
  hKey = 0;
  v31 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ScenarioData\\ProtectedData",
          0,
          3u,
          &hKey);
  if ( v31 )
  {
    v44 = 1850;
    goto LABEL_155;
  }
  pdwType = 0;
  v31 = RegGetValueW(hKey, 0, L"AuthBuffer", 8u, &pdwType, 0, &v54);
  if ( v31 )
  {
    v44 = 1861;
LABEL_155:
    v26 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v44,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
            (const char *)v31,
            phkResulte);
LABEL_86:
    if ( v24 )
      CflSecureFreeBuffer(v24);
    goto LABEL_76;
  }
  if ( pdwType != 3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x746,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)0x80070057LL,
      phkResulte);
    if ( v24 )
      CflSecureFreeBuffer(v24);
    goto LABEL_148;
  }
  if ( !v54 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x749,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)0x80070018LL,
      phkResulte);
    if ( v24 )
      CflSecureFreeBuffer(v24);
    goto LABEL_141;
  }
  *(_QWORD *)pcbData = 0;
  v26 = CflApiNew::AllocBuffer_unsigned_char_(v54);
  if ( v26 < 0 )
  {
    v41 = 1867;
LABEL_137:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)v26,
      phkResulte);
    if ( *(_QWORD *)pcbData )
      CflSecureFreeBuffer(*(HLOCAL *)pcbData);
    goto LABEL_86;
  }
  v32 = *(BYTE **)pcbData;
  v33 = RegGetValueW(hKey, 0, L"AuthBuffer", 8u, 0, *(PVOID *)pcbData, &v54);
  if ( v33 )
  {
    v42 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x754,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
            (const char *)v33,
            phkResultf);
  }
  else
  {
    v34 = RegDeleteValueW(hKey, L"AuthBuffer");
    if ( v34 > 0 )
      v35 = (unsigned __int16)v34 | 0x80070000;
    else
      v35 = (unsigned int)v34;
    if ( (v34 & 0xFFFFFFFD) != 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x75A,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)v35,
        phkResultf);
    if ( v34 == 2 )
      goto LABEL_112;
    *(&pDataIn.cbData + 1) = 0;
    pDataIn.pbData = v32;
    pDataIn.cbData = v54;
    pDataOut = 0;
    if ( CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
    {
      cbData = pDataOut.cbData;
      v54 = pDataOut.cbData;
      if ( v32 )
      {
        v38 = GetLastError();
        CflSecureFreeBuffer(v32);
        SetLastError(v38);
        cbData = v54;
      }
      *(_QWORD *)pcbData = 0;
      v26 = CflApiNew::AllocBuffer_unsigned_char_(cbData);
      if ( v26 >= 0 )
      {
        v32 = *(BYTE **)pcbData;
        memcpy_0(*(void **)pcbData, pDataOut.pbData, v54);
LABEL_112:
        *v58 = v32;
        *v59 = v54;
        goto LABEL_113;
      }
      v41 = 1903;
      goto LABEL_137;
    }
    v42 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x76C,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
            v36);
  }
  v43 = v42;
  if ( v32 )
    CflSecureFreeBuffer(v32);
  if ( v24 )
    CflSecureFreeBuffer(v24);
  if ( v16 )
    CflFreeBuffer(v16);
  if ( hKey )
    RegCloseKey(hKey);
  return v43;
}

```

## disassembly

```asm
0x18001dae0  mov     [rsp-8+arg_0], rbx
0x18001dae5  push    rbp
0x18001dae6  push    rsi
0x18001dae7  push    rdi
0x18001dae8  push    r12
0x18001daea  push    r13
0x18001daec  push    r14
0x18001daee  push    r15
0x18001daf0  lea     rbp, [rsp-0Fh]
0x18001daf5  sub     rsp, 0C0h
0x18001dafc  mov     rax, cs:__security_cookie
0x18001db03  xor     rax, rsp
0x18001db06  mov     [rbp+3Fh+var_40], rax
0x18001db0a  mov     [rbp+3Fh+var_80], r9
0x18001db0e  mov     r15, r8
0x18001db11  mov     [rbp+3Fh+var_88], r8
0x18001db15  mov     rsi, rdx
0x18001db18  mov     r14d, ecx
0x18001db1b  mov     r12, [rbp+3Fh+arg_20]
0x18001db1f  mov     r13, [rbp+3Fh+arg_28]
0x18001db23  mov     rcx, [rbp+3Fh+arg_30]
0x18001db27  mov     [rbp+3Fh+var_78], rcx
0x18001db2b  xor     edi, edi
0x18001db2d  test    r8, r8
0x18001db30  jz      short loc_18001DB38
0x18001db32  mov     [r8], rdi
0x18001db35  mov     [r9], edi
0x18001db38  test    r12, r12
0x18001db3b  jz      short loc_18001DB41
0x18001db3d  mov     [r12], rdi
0x18001db41  test    r13, r13
0x18001db44  jz      short loc_18001DB4C
0x18001db46  mov     [r13+0], rdi
0x18001db4a  mov     [rcx], edi
0x18001db4c  mov     [rbp+3Fh+hKey], rdi
0x18001db50  lea     rax, [rbp+3Fh+hKey]
0x18001db54  mov     [rsp+0F0h+phkResult], rax; int
0x18001db59  mov     r9d, 1; samDesired
0x18001db5f  xor     r8d, r8d; ulOptions
0x18001db62  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001db69  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001db70  call    cs:__imp_RegOpenKeyExW
0x18001db76  mov     ebx, eax
0x18001db78  test    eax, eax
0x18001db7a  jle     short loc_18001DB85
0x18001db7c  movzx   ebx, ax
0x18001db7f  or      ebx, 80070000h
0x18001db85  test    ebx, ebx
0x18001db87  jns     short loc_18001DBC4
0x18001db89  cmp     ebx, 80070002h
0x18001db8f  jz      loc_18001DCFA
0x18001db95  mov     edx, 6A1h; void *
0x18001db9a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001dba1  mov     r9d, ebx; char *
0x18001dba4  mov     rcx, [rbp+47h]; this
0x18001dba8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dbad  nop
0x18001dbae  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18001dbb2  test    rcx, rcx
0x18001dbb5  jz      short loc_18001DBBD
0x18001dbb7  call    cs:__imp_RegCloseKey
0x18001dbbd  mov     eax, ebx
0x18001dbbf  jmp     loc_18001E3BB
0x18001dbc4  mov     [rbp+3Fh+pdwType], edi
0x18001dbc7  test    rsi, rsi
0x18001dbca  jz      loc_18001DDDB
0x18001dbd0  xorps   xmm0, xmm0
0x18001dbd3  movups  xmmword ptr [rbp+3Fh+pclsid.Data1], xmm0
0x18001dbd7  mov     [rbp+3Fh+var_A0], edi
0x18001dbda  lea     rax, [rbp+3Fh+var_A0]
0x18001dbde  mov     [rsp+0F0h+pcbData], rax; pcbData
0x18001dbe3  mov     [rsp+0F0h+pvData], rdi; pvData
0x18001dbe8  lea     rax, [rbp+3Fh+pdwType]
0x18001dbec  mov     [rsp+0F0h+phkResult], rax; int
0x18001dbf1  mov     r9d, 2; dwFlags
0x18001dbf7  lea     r8, Value; "ProviderId"
0x18001dbfe  xor     edx, edx; lpSubKey
0x18001dc00  mov     rcx, [rbp+3Fh+hKey]; hkey
0x18001dc04  call    cs:__imp_RegGetValueW
0x18001dc0a  mov     ebx, eax
0x18001dc0c  test    eax, eax
0x18001dc0e  jz      short loc_18001DC34
0x18001dc10  cmp     eax, 2
0x18001dc13  jz      loc_18001DCC7
0x18001dc19  test    eax, eax
0x18001dc1b  jle     short loc_18001DC26
0x18001dc1d  movzx   ebx, ax
0x18001dc20  or      ebx, 80070000h
0x18001dc26  test    ebx, ebx
0x18001dc28  jns     short loc_18001DBAE
0x18001dc2a  mov     edx, 6B9h
0x18001dc2f  jmp     loc_18001DB9A
0x18001dc34  cmp     [rbp+3Fh+pdwType], 1
0x18001dc38  jnz     loc_18001DDBB
0x18001dc3e  mov     eax, [rbp+3Fh+var_A0]
0x18001dc41  test    eax, eax
0x18001dc43  jz      loc_18001DD9B
0x18001dc49  test    al, 1
0x18001dc4b  jnz     loc_18001DD9B
0x18001dc51  mov     [rbp+3Fh+hMem], rdi
0x18001dc55  mov     ecx, eax
0x18001dc57  shr     rcx, 1
0x18001dc5a  lea     rdx, [rbp+3Fh+hMem]
0x18001dc5e  call    CflApiNew__AllocBuffer_unsigned_short_
0x18001dc63  mov     ebx, eax
0x18001dc65  test    eax, eax
0x18001dc67  js      loc_18001DD6B
0x18001dc6d  lea     rax, [rbp+3Fh+var_A0]
0x18001dc71  mov     [rsp+0F0h+pcbData], rax; pcbData
0x18001dc76  mov     rbx, [rbp+3Fh+hMem]
0x18001dc7a  mov     [rsp+0F0h+pvData], rbx; pvData
0x18001dc7f  mov     [rsp+0F0h+phkResult], rdi; unsigned int
0x18001dc84  mov     r9d, 2; dwFlags
0x18001dc8a  lea     r8, Value; "ProviderId"
0x18001dc91  xor     edx, edx; lpSubKey
0x18001dc93  mov     rcx, [rbp+3Fh+hKey]; hkey
0x18001dc97  call    cs:__imp_RegGetValueW
0x18001dc9d  test    eax, eax
0x18001dc9f  jnz     loc_18001DD2D
0x18001dca5  lea     rdx, [rbp+3Fh+pclsid]; pclsid
0x18001dca9  mov     rcx, rbx; lpsz
0x18001dcac  call    cs:__imp_CLSIDFromString
0x18001dcb2  mov     edi, eax
0x18001dcb4  test    eax, eax
0x18001dcb6  js      short loc_18001DD13
0x18001dcb8  xor     edi, edi
0x18001dcba  test    rbx, rbx
0x18001dcbd  jz      short loc_18001DCC7
0x18001dcbf  mov     rcx, rbx; hMem
0x18001dcc2  call    CflFreeBuffer
0x18001dcc7  mov     rax, [rsi]
0x18001dcca  cmp     rax, qword ptr [rbp+3Fh+pclsid.Data1]
0x18001dcce  jnz     short loc_18001DCDE
0x18001dcd0  mov     rax, [rsi+8]
0x18001dcd4  cmp     rax, qword ptr [rbp+3Fh+pclsid.Data4]
0x18001dcd8  jz      loc_18001DDDB
0x18001dcde  mov     rcx, [rbp+47h]; this
0x18001dce2  mov     r9d, 80070002h; char *
0x18001dce8  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001dcef  mov     edx, 6D1h; void *
0x18001dcf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dcf9  nop
0x18001dcfa  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18001dcfe  test    rcx, rcx
0x18001dd01  jz      short loc_18001DD09
0x18001dd03  call    cs:__imp_RegCloseKey
0x18001dd09  mov     eax, 80070002h
0x18001dd0e  jmp     loc_18001E3BB
0x18001dd13  mov     rcx, [rbp+47h]; this
0x18001dd17  mov     r9d, edi; char *
0x18001dd1a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001dd21  mov     edx, 6CFh; void *
0x18001dd26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dd2b  jmp     short loc_18001DD47
0x18001dd2d  mov     rcx, [rbp+47h]; this
0x18001dd31  mov     r9d, eax; char *
0x18001dd34  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001dd3b  mov     edx, 6CDh; void *
0x18001dd40  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001dd45  mov     edi, eax
0x18001dd47  test    rbx, rbx
0x18001dd4a  jz      short loc_18001DD55
0x18001dd4c  mov     rcx, rbx; hMem
0x18001dd4f  call    CflFreeBuffer
0x18001dd54  nop
0x18001dd55  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18001dd59  test    rcx, rcx
0x18001dd5c  jz      short loc_18001DD64
0x18001dd5e  call    cs:__imp_RegCloseKey
0x18001dd64  mov     eax, edi
0x18001dd66  jmp     loc_18001E3BB
0x18001dd6b  mov     rcx, [rbp+47h]; this
0x18001dd6f  mov     r9d, ebx; char *
0x18001dd72  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001dd79  mov     edx, 6C4h; void *
0x18001dd7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dd83  nop
0x18001dd84  mov     rcx, [rbp+3Fh+hMem]; hMem
0x18001dd88  test    rcx, rcx
0x18001dd8b  jz      loc_18001DBAE
0x18001dd91  call    CflFreeBuffer
0x18001dd96  jmp     loc_18001DBAE
0x18001dd9b  mov     rcx, [rbp+47h]; this
0x18001dd9f  mov     r9d, 80070018h; char *
0x18001dda5  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001ddac  mov     edx, 6C1h; void *
0x18001ddb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ddb6  jmp     loc_18001E4C4
0x18001ddbb  mov     rcx, [rbp+47h]; this
0x18001ddbf  mov     r9d, 80070057h; char *
0x18001ddc5  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001ddcc  mov     edx, 6BEh; void *
0x18001ddd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ddd6  jmp     loc_18001E515
0x18001dddb  mov     rbx, rdi
0x18001ddde  mov     qword ptr [rbp+3Fh+pclsid.Data1], rbx
0x18001dde2  test    r12, r12
0x18001dde5  jz      loc_18001DFA2
0x18001ddeb  mov     [rbp+3Fh+pdwType], edi
0x18001ddee  mov     [rbp+3Fh+var_A0], edi
0x18001ddf1  lea     rax, [rbp+3Fh+var_A0]
0x18001ddf5  mov     [rsp+0F0h+pcbData], rax; pcbData
0x18001ddfa  mov     [rsp+0F0h+pvData], rdi; pvData
0x18001ddff  lea     rax, [rbp+3Fh+pdwType]
0x18001de03  mov     [rsp+0F0h+phkResult], rax; unsigned int
0x18001de08  mov     r9d, 2; dwFlags
0x18001de0e  lea     r8, aScenarioid; "ScenarioId"
0x18001de15  xor     edx, edx; lpSubKey
0x18001de17  mov     rcx, [rbp+3Fh+hKey]; hkey
0x18001de1b  call    cs:__imp_RegGetValueW
0x18001de21  mov     edi, eax
0x18001de23  cmp     r14d, 2
0x18001de27  jnz     short loc_18001DE65
0x18001de29  test    eax, eax
0x18001de2b  jz      short loc_18001DE6D
0x18001de2d  cmp     eax, r14d
0x18001de30  jz      loc_18001DFA2
0x18001de36  test    eax, eax
0x18001de38  jle     short loc_18001DE43
0x18001de3a  movzx   edi, ax
0x18001de3d  or      edi, 80070000h
0x18001de43  test    edi, edi
0x18001de45  jns     short loc_18001DE60
0x18001de47  mov     rcx, [rbp+47h]; this
0x18001de4b  mov     r9d, edi; char *
0x18001de4e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001de55  mov     edx, 6E7h; void *
0x18001de5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de5f  nop
0x18001de60  jmp     loc_18001DD47
0x18001de65  test    eax, eax
0x18001de67  jnz     loc_18001DF83
0x18001de6d  cmp     [rbp+3Fh+pdwType], 1
0x18001de71  jnz     loc_18001DF63
0x18001de77  mov     eax, [rbp+3Fh+var_A0]
0x18001de7a  test    eax, eax
0x18001de7c  jz      loc_18001DF43
0x18001de82  test    al, 1
0x18001de84  jnz     loc_18001DF43
0x18001de8a  test    rbx, rbx
0x18001de8d  jz      short loc_18001DEAA
0x18001de8f  call    cs:__imp_GetLastError
0x18001de95  mov     edi, eax
0x18001de97  mov     rcx, rbx; hMem
0x18001de9a  call    CflFreeBuffer
0x18001de9f  mov     ecx, edi; dwErrCode
0x18001dea1  call    cs:__imp_SetLastError
0x18001dea7  mov     eax, [rbp+3Fh+var_A0]
0x18001deaa  mov     qword ptr [rbp+3Fh+pclsid.Data1], 0
0x18001deb2  mov     ecx, eax
0x18001deb4  shr     rcx, 1
0x18001deb7  lea     rdx, [rbp+3Fh+pclsid]
0x18001debb  call    CflApiNew__AllocBuffer_unsigned_short_
0x18001dec0  mov     ebx, eax
0x18001dec2  test    eax, eax
0x18001dec4  js      short loc_18001DF21
0x18001dec6  lea     rax, [rbp+3Fh+var_A0]
0x18001deca  mov     [rsp+0F0h+pcbData], rax; pcbData
0x18001decf  mov     rbx, qword ptr [rbp+3Fh+pclsid.Data1]
0x18001ded3  mov     [rsp+0F0h+pvData], rbx; pvData
0x18001ded8  mov     [rsp+0F0h+phkResult], 0; unsigned int
0x18001dee1  mov     r9d, 2; dwFlags
0x18001dee7  lea     r8, aScenarioid; "ScenarioId"
0x18001deee  xor     edx, edx; lpSubKey
0x18001def0  mov     rcx, [rbp+3Fh+hKey]; hkey
0x18001def4  call    cs:__imp_RegGetValueW
0x18001defa  test    eax, eax
0x18001defc  jz      loc_18001DFA2
0x18001df02  mov     rcx, [rbp+47h]; this
0x18001df06  mov     r9d, eax; char *
0x18001df09  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001df10  mov     edx, 6FFh; void *
0x18001df15  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001df1a  mov     edi, eax
0x18001df1c  jmp     loc_18001DE60
0x18001df21  mov     rcx, [rbp+47h]; this
0x18001df25  mov     r9d, ebx; char *
0x18001df28  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001df2f  mov     edx, 6F6h; void *
0x18001df34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df39  nop
0x18001df3a  mov     rcx, qword ptr [rbp+3Fh+pclsid.Data1]
0x18001df3e  jmp     loc_18001DD88
0x18001df43  mov     rcx, [rbp+47h]; this
0x18001df47  mov     r9d, 80070018h; char *
0x18001df4d  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001df54  mov     edx, 6F4h; void *
0x18001df59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df5e  jmp     loc_18001E4B6
0x18001df63  mov     rcx, [rbp+47h]; this
0x18001df67  mov     r9d, 80070057h; char *
0x18001df6d  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001df74  mov     edx, 6F1h; void *
0x18001df79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df7e  jmp     loc_18001E507
0x18001df83  mov     rcx, [rbp+47h]; this
0x18001df87  mov     r9d, eax; char *
0x18001df8a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001df91  mov     edx, 6EFh; void *
0x18001df96  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
  ... truncated ...
```
