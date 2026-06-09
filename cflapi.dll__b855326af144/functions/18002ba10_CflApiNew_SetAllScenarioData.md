# CflApiNew::SetAllScenarioData

- ea: `0x18002ba10`
- end: `0x18002c116`
- name: `CflApiNew::SetAllScenarioData`
- size: `1798`
- prototype: `__int64 __usercall@<rax>(IID *rclsid@<rcx>, BYTE *lpData, DWORD cbData, BYTE Data)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180011940`
- `0x180011f20`

## callees

- `0x1800067a4`
- `0x1800067c4`
- `0x18001f948`
- `0x1800286d4`
- `0x18002a6a4`
- `0x18002ad54`
- `0x18002ba10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bc86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002be22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bf81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bc86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002be22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bf81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bff2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c01d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c086`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c0bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c0ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bff2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c01d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c086`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c0bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c0ea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002bd31`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002bd31`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002baab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002be63`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002bfc6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002baab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002be63`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002bfc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bb62`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bbca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bc07`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bc40`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002beb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c05a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bb62`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bbca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bc07`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bc40`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002beb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c05a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bcb0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bcb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bad8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bc7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002be1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bf44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bf79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c02d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c0fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bad8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bc7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002be1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bf44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bf79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c02d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c0fa`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002bf17`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002c000`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002c094`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002c0cd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002bf17`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002c000`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002c094`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002c0cd`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002baf8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002baf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb91`
- `CRYPT32!CryptProtectData` at `0x18002bdbd`
- `CRYPT32!CryptProtectData` at `0x18002bdbd`

## string_xrefs

- `0x18002ba58`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002baba`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002bb0b`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002bb73`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002bcdf`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002bdcf`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002beef`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002bfd7`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002c06b`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CflApiNew::SetAllScenarioData(IID *rclsid, BYTE *a2, DWORD a3, const BYTE *a4, BYTE *lpData, DWORD cbData, ...)
{
  int v10; // eax
  signed int v11; // ebx
  unsigned int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rdi
  HRESULT v17; // eax
  __int64 v18; // rdx
  unsigned int v19; // eax
  HKEY v20; // rdi
  DWORD LastError; // ebx
  LSTATUS v22; // eax
  __int64 v23; // rdx
  LSTATUS ValueW; // eax
  bool v25; // di
  const char *v26; // r9
  HKEY v27; // r14
  DWORD v28; // ebx
  const WCHAR *v29; // rdx
  BYTE *pbData; // rbx
  int ProtectedScenarioDataSecurityDescriptor; // eax
  unsigned int v32; // edi
  SIZE_T v33; // rax
  BYTE *i; // rcx
  HLOCAL v35; // rdi
  HKEY v36; // r14
  DWORD v37; // esi
  unsigned int v38; // eax
  unsigned int v39; // esi
  SIZE_T v40; // rax
  BYTE *j; // rcx
  unsigned int v42; // eax
  SIZE_T v43; // rax
  BYTE *k; // rcx
  SIZE_T v45; // rax
  BYTE *m; // rcx
  int dwOptions; // [rsp+20h] [rbp-81h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-81h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-81h]
  int dwOptionsc; // [rsp+20h] [rbp-81h]
  int dwOptionsd; // [rsp+20h] [rbp-81h]
  unsigned int dwOptionse; // [rsp+20h] [rbp-81h]
  unsigned int dwOptionsf; // [rsp+20h] [rbp-81h]
  DWORD pcbData; // [rsp+50h] [rbp-51h] BYREF
  HLOCAL pvData; // [rsp+58h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-41h] BYREF
  DATA_BLOB pDataOut; // [rsp+68h] [rbp-39h] BYREF
  DATA_BLOB pDataIn; // [rsp+78h] [rbp-29h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+88h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+47h]
  LPOLESTR lpsz; // [rsp+F0h] [rbp+4Fh] BYREF
  va_list va; // [rsp+120h] [rbp+7Fh] BYREF

  va_start(va, cbData);
  v10 = CflApiNew::ClearScenarioDataWithReason((char *)(2 - (unsigned int)(rclsid != 0)), rclsid);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C5,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)(unsigned int)v10,
      dwOptions);
    return (unsigned int)v11;
  }
  hKey = 0;
  v13 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ScenarioData",
          0,
          0,
          1u,
          0x20006u,
          0,
          &hKey,
          0);
  if ( v13 )
  {
    v14 = 722;
LABEL_6:
    v15 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v14,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
            (const char *)v13,
            dwOptionsa);
LABEL_7:
    v11 = v15;
    goto LABEL_8;
  }
  v16 = -1;
  if ( rclsid )
  {
    lpsz = 0;
    v17 = StringFromCLSID(rclsid, &lpsz);
    v11 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D7,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
        (const char *)(unsigned int)v17,
        dwOptionsa);
      goto LABEL_13;
    }
    v18 = -1;
    do
      ++v18;
    while ( lpsz[v18] );
    v19 = RegSetValueExW(hKey, L"ProviderId", 0, 1u, (const BYTE *)lpsz, 2 * v18 + 2);
    if ( v19 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x2DF,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
              (const char *)v19,
              dwOptionsb);
LABEL_13:
      if ( lpsz )
        CoTaskMemFree(lpsz);
      goto LABEL_8;
    }
    if ( lpsz )
      CoTaskMemFree(lpsz);
  }
  if ( a4 )
  {
    do
      ++v16;
    while ( *(_WORD *)&a4[2 * v16] );
    v13 = RegSetValueExW(hKey, L"ScenarioId", 0, 1u, a4, 2 * v16 + 2);
    if ( v13 )
    {
      v14 = 748;
      goto LABEL_6;
    }
  }
  if ( lpData )
  {
    v13 = RegSetValueExW(hKey, L"ScenarioContext", 0, 3u, lpData, cbData);
    if ( v13 )
    {
      v14 = 760;
      goto LABEL_6;
    }
  }
  v13 = RegSetValueExW(hKey, L"LastSessionId", 0, 4u, (const BYTE *)va, 4u);
  if ( v13 )
  {
    v14 = 770;
    goto LABEL_6;
  }
  if ( (unsigned __int8)CflApiNew::InCamSession() )
    goto LABEL_50;
  if ( !rclsid )
  {
    v25 = 0;
    goto LABEL_56;
  }
  v20 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v20);
    SetLastError(LastError);
  }
  hKey = 0;
  v22 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE", 0, 1u, &hKey);
  v11 = v22;
  if ( !v22 )
  {
    LODWORD(lpsz) = 0;
    LODWORD(pvData) = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hKey, 0, L"DefaultAccountAction", 0x10u, (LPDWORD)&lpsz, &pvData, &pcbData);
    v11 = ValueW;
    if ( ValueW )
    {
      if ( ValueW == 2 )
        goto LABEL_50;
      if ( ValueW > 0 )
        v11 = (unsigned __int16)ValueW | 0x80070000;
      if ( v11 >= 0 )
        goto LABEL_8;
      v23 = 811;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
        (const char *)(unsigned int)v11,
        dwOptionsc);
LABEL_8:
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v11;
    }
    if ( (_DWORD)lpsz != 4 )
    {
      v11 = -2147024809;
      v23 = 816;
      goto LABEL_40;
    }
    if ( pcbData != 4 )
    {
      v11 = -2147024872;
      v23 = 819;
      goto LABEL_40;
    }
    v25 = (_DWORD)pvData == 1;
    if ( (_DWORD)pvData != 1 )
      goto LABEL_50;
LABEL_56:
    v27 = hKey;
    if ( hKey )
    {
      v28 = GetLastError();
      RegCloseKey(v27);
      SetLastError(v28);
    }
    hKey = 0;
    v13 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ExperienceManagerData",
            0,
            0,
            1u,
            0x20006u,
            0,
            &hKey,
            0);
    if ( v13 )
    {
      v14 = 838;
      goto LABEL_6;
    }
    LODWORD(lpsz) = 1;
    if ( !rclsid || (v29 = L"LaunchCflScenario", !v25) )
      v29 = L"TransitionCflScenario";
    v13 = RegSetValueExW(hKey, v29, 0, 4u, (const BYTE *)&lpsz, 4u);
    if ( v13 )
    {
      v14 = 848;
      goto LABEL_6;
    }
    goto LABEL_50;
  }
  if ( v22 != 2 )
  {
    if ( v22 > 0 )
      v11 = (unsigned __int16)v22 | 0x80070000;
    if ( v11 >= 0 )
      goto LABEL_8;
    v23 = 792;
    goto LABEL_40;
  }
LABEL_50:
  if ( a2 )
  {
    *(&pDataIn.cbData + 1) = 0;
    pDataIn.pbData = a2;
    pDataIn.cbData = a3;
    pDataOut = 0;
    if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 5u, &pDataOut) )
    {
      v15 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x363,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
              v26);
      goto LABEL_7;
    }
    pbData = pDataOut.pbData;
    pDataOut.pbData = 0;
    pvData = 0;
    ProtectedScenarioDataSecurityDescriptor = CflApiNew::GetProtectedScenarioDataSecurityDescriptor(&pvData, &lpsz);
    v32 = ProtectedScenarioDataSecurityDescriptor;
    if ( ProtectedScenarioDataSecurityDescriptor < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36A,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
        (const char *)(unsigned int)ProtectedScenarioDataSecurityDescriptor,
        dwOptionsd);
      if ( pvData )
        LocalFree(pvData);
      if ( pbData )
      {
        v33 = LocalSize(pbData);
        for ( i = pbData; v33; --v33 )
          *i++ = 0;
        LocalFree(pbData);
      }
      if ( hKey )
        RegCloseKey(hKey);
      return v32;
    }
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    v35 = pvData;
    SecurityAttributes.lpSecurityDescriptor = pvData;
    v36 = hKey;
    if ( hKey )
    {
      v37 = GetLastError();
      RegCloseKey(v36);
      SetLastError(v37);
    }
    hKey = 0;
    v38 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ScenarioData\\ProtectedData",
            0,
            0,
            1u,
            0x20006u,
            &SecurityAttributes,
            &hKey,
            0);
    if ( v38 )
    {
      v39 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x37B,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
              (const char *)v38,
              dwOptionse);
      if ( v35 )
        LocalFree(v35);
      if ( !pbData )
        goto LABEL_84;
      v40 = LocalSize(pbData);
      for ( j = pbData; v40; --v40 )
        *j++ = 0;
LABEL_83:
      LocalFree(pbData);
LABEL_84:
      if ( hKey )
        RegCloseKey(hKey);
      return v39;
    }
    v42 = RegSetValueExW(hKey, L"AuthBuffer", 0, 3u, pbData, pDataOut.cbData);
    if ( v42 )
    {
      v39 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x384,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
              (const char *)v42,
              dwOptionsf);
      if ( v35 )
        LocalFree(v35);
      if ( !pbData )
        goto LABEL_84;
      v43 = LocalSize(pbData);
      for ( k = pbData; v43; --v43 )
        *k++ = 0;
      goto LABEL_83;
    }
    if ( v35 )
      LocalFree(v35);
    if ( pbData )
    {
      v45 = LocalSize(pbData);
      for ( m = pbData; v45; --v45 )
        *m++ = 0;
      LocalFree(pbData);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18002ba10  push    rbp
0x18002ba12  push    rbx
0x18002ba13  push    rsi
0x18002ba14  push    rdi
0x18002ba15  push    r12
0x18002ba17  push    r13
0x18002ba19  push    r14
0x18002ba1b  push    r15
0x18002ba1d  lea     rbp, [rsp-7]
0x18002ba22  sub     rsp, 0A8h
0x18002ba29  mov     r14, r9
0x18002ba2c  mov     r12d, r8d
0x18002ba2f  mov     r15, rdx
0x18002ba32  mov     rsi, rcx
0x18002ba35  mov     rax, rcx
0x18002ba38  neg     rax
0x18002ba3b  sbb     ecx, ecx
0x18002ba3d  add     ecx, 2; char *
0x18002ba40  mov     rdx, rsi
0x18002ba43  call    CflApiNew__ClearScenarioDataWithReason
0x18002ba48  mov     ebx, eax
0x18002ba4a  xor     r13d, r13d
0x18002ba4d  test    eax, eax
0x18002ba4f  jns     short loc_18002BA70
0x18002ba51  mov     rcx, [rbp+47h]; this
0x18002ba55  mov     r9d, eax; char *
0x18002ba58  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002ba5f  mov     edx, 2C5h; void *
0x18002ba64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ba69  mov     eax, ebx
0x18002ba6b  jmp     loc_18002C102
0x18002ba70  mov     [rbp+3Fh+hKey], r13
0x18002ba74  mov     [rsp+0E0h+lpdwDisposition], r13; lpdwDisposition
0x18002ba79  lea     rax, [rbp+3Fh+hKey]
0x18002ba7d  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18002ba82  mov     [rsp+0E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18002ba87  mov     [rsp+0E0h+samDesired], 20006h; samDesired
0x18002ba8f  mov     [rsp+0E0h+dwOptions], 1; int
0x18002ba97  xor     r9d, r9d; lpClass
0x18002ba9a  xor     r8d, r8d; Reserved
0x18002ba9d  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002baa4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002baab  call    cs:__imp_RegCreateKeyExW
0x18002bab1  test    eax, eax
0x18002bab3  jz      short loc_18002BAE0
0x18002bab5  mov     edx, 2D2h; void *
0x18002baba  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002bac1  mov     r9d, eax; char *
0x18002bac4  mov     rcx, [rbp+47h]; this
0x18002bac8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002bacd  mov     ebx, eax
0x18002bacf  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18002bad3  test    rcx, rcx
0x18002bad6  jz      short loc_18002BA69
0x18002bad8  call    cs:__imp_RegCloseKey
0x18002bade  jmp     short loc_18002BA69
0x18002bae0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002bae4  test    rsi, rsi
0x18002bae7  jz      loc_18002BB97
0x18002baed  mov     [rbp+3Fh+lpsz], r13
0x18002baf1  lea     rdx, [rbp+3Fh+lpsz]; lplpsz
0x18002baf5  mov     rcx, rsi; rclsid
0x18002baf8  call    cs:__imp_StringFromCLSID
0x18002bafe  mov     ebx, eax
0x18002bb00  test    eax, eax
0x18002bb02  jns     short loc_18002BB2D
0x18002bb04  mov     rcx, [rbp+47h]; this
0x18002bb08  mov     r9d, eax; char *
0x18002bb0b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002bb12  mov     edx, 2D7h; void *
0x18002bb17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bb1c  mov     rcx, [rbp+3Fh+lpsz]; pv
0x18002bb20  test    rcx, rcx
0x18002bb23  jz      short loc_18002BACF
0x18002bb25  call    cs:__imp_CoTaskMemFree
0x18002bb2b  jmp     short loc_18002BACF
0x18002bb2d  mov     rax, [rbp+3Fh+lpsz]
0x18002bb31  mov     rdx, rdi
0x18002bb34  inc     rdx
0x18002bb37  cmp     [rax+rdx*2], r13w
0x18002bb3c  jnz     short loc_18002BB34
0x18002bb3e  lea     edx, ds:2[rdx*2]
0x18002bb45  mov     [rsp+0E0h+samDesired], edx; cbData
0x18002bb49  mov     qword ptr [rsp+0E0h+dwOptions], rax; unsigned int
0x18002bb4e  mov     r9d, 1; dwType
0x18002bb54  xor     r8d, r8d; Reserved
0x18002bb57  lea     rdx, Value; "ProviderId"
0x18002bb5e  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18002bb62  call    cs:__imp_RegSetValueExW
0x18002bb68  test    eax, eax
0x18002bb6a  jz      short loc_18002BB88
0x18002bb6c  mov     rcx, [rbp+47h]; this
0x18002bb70  mov     r9d, eax; char *
0x18002bb73  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002bb7a  mov     edx, 2DFh; void *
0x18002bb7f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002bb84  mov     ebx, eax
0x18002bb86  jmp     short loc_18002BB1C
0x18002bb88  mov     rcx, [rbp+3Fh+lpsz]; pv
0x18002bb8c  test    rcx, rcx
0x18002bb8f  jz      short loc_18002BB97
0x18002bb91  call    cs:__imp_CoTaskMemFree
0x18002bb97  test    r14, r14
0x18002bb9a  jz      short loc_18002BBDE
0x18002bb9c  inc     rdi
0x18002bb9f  cmp     [r14+rdi*2], r13w
0x18002bba4  jnz     short loc_18002BB9C
0x18002bba6  lea     eax, ds:2[rdi*2]
0x18002bbad  mov     [rsp+0E0h+samDesired], eax; cbData
0x18002bbb1  mov     qword ptr [rsp+0E0h+dwOptions], r14; lpData
0x18002bbb6  mov     r9d, 1; dwType
0x18002bbbc  xor     r8d, r8d; Reserved
0x18002bbbf  lea     rdx, aScenarioid; "ScenarioId"
0x18002bbc6  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18002bbca  call    cs:__imp_RegSetValueExW
0x18002bbd0  test    eax, eax
0x18002bbd2  jz      short loc_18002BBDE
0x18002bbd4  mov     edx, 2ECh
0x18002bbd9  jmp     loc_18002BABA
0x18002bbde  mov     rcx, [rbp+3Fh+lpData]
0x18002bbe2  test    rcx, rcx
0x18002bbe5  jz      short loc_18002BC1B
0x18002bbe7  mov     eax, [rbp+3Fh+cbData]
0x18002bbea  mov     [rsp+0E0h+samDesired], eax; cbData
0x18002bbee  mov     qword ptr [rsp+0E0h+dwOptions], rcx; lpData
0x18002bbf3  mov     r9d, 3; dwType
0x18002bbf9  xor     r8d, r8d; Reserved
0x18002bbfc  lea     rdx, aScenariocontex; "ScenarioContext"
0x18002bc03  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18002bc07  call    cs:__imp_RegSetValueExW
0x18002bc0d  test    eax, eax
0x18002bc0f  jz      short loc_18002BC1B
0x18002bc11  mov     edx, 2F8h
0x18002bc16  jmp     loc_18002BABA
0x18002bc1b  mov     r14d, 4
0x18002bc21  mov     [rsp+0E0h+samDesired], r14d; cbData
0x18002bc26  lea     rax, [rbp+3Fh+Data]
0x18002bc2a  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x18002bc2f  mov     r9d, r14d; dwType
0x18002bc32  xor     r8d, r8d; Reserved
0x18002bc35  lea     rdx, aLastsessionid; "LastSessionId"
0x18002bc3c  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18002bc40  call    cs:__imp_RegSetValueExW
0x18002bc46  test    eax, eax
0x18002bc48  jz      short loc_18002BC54
0x18002bc4a  mov     edx, 302h
0x18002bc4f  jmp     loc_18002BABA
0x18002bc54  call    CflApiNew__InCamSession
0x18002bc59  test    al, al
0x18002bc5b  jnz     loc_18002BD7F
0x18002bc61  test    rsi, rsi
0x18002bc64  jz      loc_18002BE03
0x18002bc6a  mov     rdi, [rbp+3Fh+hKey]
0x18002bc6e  test    rdi, rdi
0x18002bc71  jz      short loc_18002BC8C
0x18002bc73  call    cs:__imp_GetLastError
0x18002bc79  mov     ebx, eax
0x18002bc7b  mov     rcx, rdi; hKey
0x18002bc7e  call    cs:__imp_RegCloseKey
0x18002bc84  mov     ecx, ebx; dwErrCode
0x18002bc86  call    cs:__imp_SetLastError
0x18002bc8c  mov     [rbp+3Fh+hKey], r13
0x18002bc90  lea     rax, [rbp+3Fh+hKey]
0x18002bc94  mov     qword ptr [rsp+0E0h+dwOptions], rax; int
0x18002bc99  mov     r9d, 1; samDesired
0x18002bc9f  xor     r8d, r8d; ulOptions
0x18002bca2  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002bca9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bcb0  call    cs:__imp_RegOpenKeyExW
0x18002bcb6  mov     ebx, eax
0x18002bcb8  test    eax, eax
0x18002bcba  jz      short loc_18002BCF7
0x18002bcbc  cmp     eax, 2
0x18002bcbf  jz      loc_18002BD7F
0x18002bcc5  test    eax, eax
0x18002bcc7  jle     short loc_18002BCD2
0x18002bcc9  movzx   ebx, ax
0x18002bccc  or      ebx, 80070000h
0x18002bcd2  test    ebx, ebx
0x18002bcd4  jns     loc_18002BACF
0x18002bcda  mov     edx, 318h; void *
0x18002bcdf  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002bce6  mov     r9d, ebx; char *
0x18002bce9  mov     rcx, [rbp+47h]; this
0x18002bced  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bcf2  jmp     loc_18002BACF
0x18002bcf7  mov     dword ptr [rbp+3Fh+lpsz], r13d
0x18002bcfb  mov     dword ptr [rbp+3Fh+pvData], r13d
0x18002bcff  mov     [rbp+3Fh+pcbData], r14d
0x18002bd03  lea     rax, [rbp+3Fh+pcbData]
0x18002bd07  mov     [rsp+0E0h+lpSecurityAttributes], rax; pcbData
0x18002bd0c  lea     rax, [rbp+3Fh+pvData]
0x18002bd10  mov     qword ptr [rsp+0E0h+samDesired], rax; pvData
0x18002bd15  lea     rax, [rbp+3Fh+lpsz]
0x18002bd19  mov     qword ptr [rsp+0E0h+dwOptions], rax; pdwType
0x18002bd1e  mov     r9d, 10h; dwFlags
0x18002bd24  lea     r8, aDefaultaccount; "DefaultAccountAction"
0x18002bd2b  xor     edx, edx; lpSubKey
0x18002bd2d  mov     rcx, [rbp+3Fh+hKey]; hkey
0x18002bd31  call    cs:__imp_RegGetValueW
0x18002bd37  mov     ebx, eax
0x18002bd39  test    eax, eax
0x18002bd3b  jz      short loc_18002BD5E
0x18002bd3d  cmp     eax, 2
0x18002bd40  jz      short loc_18002BD7F
0x18002bd42  test    eax, eax
0x18002bd44  jle     short loc_18002BD4F
0x18002bd46  movzx   ebx, ax
0x18002bd49  or      ebx, 80070000h
0x18002bd4f  test    ebx, ebx
0x18002bd51  jns     loc_18002BACF
0x18002bd57  mov     edx, 32Bh
0x18002bd5c  jmp     short loc_18002BCDF
0x18002bd5e  cmp     dword ptr [rbp+3Fh+lpsz], r14d
0x18002bd62  jnz     loc_18002BDF4
0x18002bd68  cmp     [rbp+3Fh+pcbData], r14d
0x18002bd6c  jnz     short loc_18002BDE5
0x18002bd6e  cmp     dword ptr [rbp+3Fh+pvData], 1
0x18002bd72  setz    dil
0x18002bd76  test    dil, dil
0x18002bd79  jnz     loc_18002BE06
0x18002bd7f  test    r15, r15
0x18002bd82  jz      loc_18002C0F1
0x18002bd88  mov     dword ptr [rbp+3Fh+pDataIn+4], r13d
0x18002bd8c  mov     [rbp+3Fh+pDataIn.pbData], r15
0x18002bd90  mov     [rbp+3Fh+pDataIn.cbData], r12d
0x18002bd94  xorps   xmm0, xmm0
0x18002bd97  movups  xmmword ptr [rbp+3Fh+pDataOut.cbData], xmm0
0x18002bd9b  lea     rax, [rbp+3Fh+pDataOut]
0x18002bd9f  mov     [rsp+0E0h+lpSecurityAttributes], rax; pDataOut
0x18002bda4  mov     [rsp+0E0h+samDesired], 5; dwFlags
0x18002bdac  mov     qword ptr [rsp+0E0h+dwOptions], r13; int
0x18002bdb1  xor     r9d, r9d; pvReserved
0x18002bdb4  xor     r8d, r8d; pOptionalEntropy
0x18002bdb7  xor     edx, edx; szDataDescr
0x18002bdb9  lea     rcx, [rbp+3Fh+pDataIn]; pDataIn
0x18002bdbd  call    cs:__imp_CryptProtectData
0x18002bdc3  test    eax, eax
0x18002bdc5  jnz     loc_18002BEC9
0x18002bdcb  mov     rcx, [rbp+47h]; this
0x18002bdcf  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002bdd6  mov     edx, 363h; void *
0x18002bddb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002bde0  jmp     loc_18002BACD
0x18002bde5  mov     ebx, 80070018h
0x18002bdea  mov     edx, 333h
0x18002bdef  jmp     loc_18002BCDF
0x18002bdf4  mov     ebx, 80070057h
0x18002bdf9  mov     edx, 330h
0x18002bdfe  jmp     loc_18002BCDF
0x18002be03  mov     dil, r13b
0x18002be06  mov     r14, [rbp+3Fh+hKey]
0x18002be0a  test    r14, r14
0x18002be0d  jz      short loc_18002BE28
0x18002be0f  call    cs:__imp_GetLastError
0x18002be15  mov     ebx, eax
0x18002be17  mov     rcx, r14; hKey
0x18002be1a  call    cs:__imp_RegCloseKey
0x18002be20  mov     ecx, ebx; dwErrCode
0x18002be22  call    cs:__imp_SetLastError
0x18002be28  mov     [rbp+3Fh+hKey], r13
0x18002be2c  mov     [rsp+0E0h+lpdwDisposition], r13; lpdwDisposition
0x18002be31  lea     rax, [rbp+3Fh+hKey]
0x18002be35  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18002be3a  mov     [rsp+0E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18002be3f  mov     [rsp+0E0h+samDesired], 20006h; samDesired
0x18002be47  mov     [rsp+0E0h+dwOptions], 1; dwOptions
0x18002be4f  xor     r9d, r9d; lpClass
0x18002be52  xor     r8d, r8d; Reserved
0x18002be55  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002be5c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002be63  call    cs:__imp_RegCreateKeyExW
0x18002be69  test    eax, eax
0x18002be6b  jz      short loc_18002BE77
0x18002be6d  mov     edx, 346h
0x18002be72  jmp     loc_18002BABA
0x18002be77  mov     dword ptr [rbp+3Fh+lpsz], 1
0x18002be7e  test    rsi, rsi
0x18002be81  jz      short loc_18002BE8F
0x18002be83  test    dil, dil
0x18002be86  lea     rdx, aLaunchcflscena; "LaunchCflScenario"
0x18002be8d  jnz     short loc_18002BE96
0x18002be8f  lea     rdx, aTransitioncfls; "TransitionCflScenario"
0x18002be96  mov     r9d, 4; dwType
0x18002be9c  mov     [rsp+0E0h+samDesired], r9d; cbData
0x18002bea1  lea     rax, [rbp+3Fh+lpsz]
0x18002bea5  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x18002beaa  xor     r8d, r8d; Reserved
0x18002bead  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18002beb1  call    cs:__imp_RegSetValueExW
0x18002beb7  test    eax, eax
0x18002beb9  jz      loc_18002BD7F
0x18002bebf  mov     edx, 350h
0x18002bec4  jmp     loc_18002BABA
0x18002bec9  mov     rbx, [rbp+3Fh+pDataOut.pbData]
0x18002becd  mov     [rbp+3Fh+pDataOut.pbData], r13
0x18002bed1  mov     [rbp+3Fh+pvData], r13
0x18002bed5  lea     rdx, [rbp+3Fh+lpsz]
0x18002bed9  lea     rcx, [rbp+3Fh+pvData]
0x18002bedd  call    CflApiNew__GetProtectedScenarioDataSecurityDescriptor
  ... truncated ...
```
