# CflApi::SetAllScenarioData

- ea: `0x180020378`
- end: `0x180020a4b`
- name: `CflApi::SetAllScenarioData`
- size: `1747`
- prototype: `__int64 __fastcall(IID *rclsid, BYTE *, DWORD, const BYTE *, BYTE *lpData, DWORD cbData)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180011770`

## callees

- `0x1800067a4`
- `0x1800067c4`
- `0x18001bf60`
- `0x18001e55c`
- `0x18001f2d8`
- `0x18001f948`
- `0x180020378`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800205b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020757`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800208b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800205b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020757`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800208b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002083e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020869`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020927`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020952`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800209bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800209f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002083e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020869`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020927`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020952`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800209bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800209f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a1f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020663`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020663`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020413`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020798`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800208fb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020413`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020798`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800208fb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800204ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020532`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002056f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800207e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002098f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800204ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020532`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002056f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800207e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002098f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800205df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800205df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020440`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800205ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002074f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020879`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800208ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020962`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020a2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020440`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800205ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002074f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020879`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800208ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020962`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020a2f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002084c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180020935`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800209c9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180020a02`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002084c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180020935`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800209c9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180020a02`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180020460`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180020460`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002048d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800204f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002048d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800204f9`
- `CRYPT32!CryptProtectData` at `0x1800206f2`
- `CRYPT32!CryptProtectData` at `0x1800206f2`

## string_xrefs

- `0x1800203c0`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x180020429`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x180020473`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x1800204db`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18002060e`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x180020704`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x180020824`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18002090c`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x1800209a0`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CflApi::SetAllScenarioData(
        IID *rclsid,
        BYTE *a2,
        DWORD a3,
        const BYTE *a4,
        BYTE *lpData,
        DWORD cbData)
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
  int dwOptions; // [rsp+20h] [rbp-79h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-79h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-79h]
  int dwOptionsc; // [rsp+20h] [rbp-79h]
  int dwOptionsd; // [rsp+20h] [rbp-79h]
  unsigned int dwOptionse; // [rsp+20h] [rbp-79h]
  unsigned int dwOptionsf; // [rsp+20h] [rbp-79h]
  DWORD pcbData; // [rsp+50h] [rbp-49h] BYREF
  HLOCAL pvData; // [rsp+58h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-39h] BYREF
  DATA_BLOB pDataOut; // [rsp+68h] [rbp-31h] BYREF
  DATA_BLOB pDataIn; // [rsp+78h] [rbp-21h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+88h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]
  LPOLESTR lpsz; // [rsp+F0h] [rbp+57h] BYREF

  v10 = CflApi::ClearScenarioDataWithReason((char *)(2 - (unsigned int)(rclsid != 0)));
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57F,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
    v14 = 1420;
LABEL_6:
    v15 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v14,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
        (void *)0x591,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
              (void *)0x599,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
      v14 = 1446;
      goto LABEL_6;
    }
  }
  if ( lpData )
  {
    v13 = RegSetValueExW(hKey, L"ScenarioContext", 0, 3u, lpData, cbData);
    if ( v13 )
    {
      v14 = 1458;
      goto LABEL_6;
    }
  }
  if ( (unsigned __int8)CflApi::InCamSession() )
    goto LABEL_48;
  if ( !rclsid )
  {
    v25 = 0;
    goto LABEL_54;
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
        goto LABEL_48;
      if ( ValueW > 0 )
        v11 = (unsigned __int16)ValueW | 0x80070000;
      if ( v11 >= 0 )
        goto LABEL_8;
      v23 = 1500;
LABEL_38:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
      v23 = 1505;
      goto LABEL_38;
    }
    if ( pcbData != 4 )
    {
      v11 = -2147024872;
      v23 = 1508;
      goto LABEL_38;
    }
    v25 = (_DWORD)pvData == 1;
    if ( (_DWORD)pvData != 1 )
      goto LABEL_48;
LABEL_54:
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
      v14 = 1527;
      goto LABEL_6;
    }
    LODWORD(lpsz) = 1;
    if ( !rclsid || (v29 = L"LaunchCflScenario", !v25) )
      v29 = L"TransitionCflScenario";
    v13 = RegSetValueExW(hKey, v29, 0, 4u, (const BYTE *)&lpsz, 4u);
    if ( v13 )
    {
      v14 = 1537;
      goto LABEL_6;
    }
    goto LABEL_48;
  }
  if ( v22 != 2 )
  {
    if ( v22 > 0 )
      v11 = (unsigned __int16)v22 | 0x80070000;
    if ( v11 >= 0 )
      goto LABEL_8;
    v23 = 1481;
    goto LABEL_38;
  }
LABEL_48:
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
              (void *)0x614,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
              v26);
      goto LABEL_7;
    }
    pbData = pDataOut.pbData;
    pDataOut.pbData = 0;
    pvData = 0;
    ProtectedScenarioDataSecurityDescriptor = CflApi::GetProtectedScenarioDataSecurityDescriptor(&pvData, &lpsz);
    v32 = ProtectedScenarioDataSecurityDescriptor;
    if ( ProtectedScenarioDataSecurityDescriptor < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61B,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
              (void *)0x62C,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
              (const char *)v38,
              dwOptionse);
      if ( v35 )
        LocalFree(v35);
      if ( !pbData )
        goto LABEL_82;
      v40 = LocalSize(pbData);
      for ( j = pbData; v40; --v40 )
        *j++ = 0;
LABEL_81:
      LocalFree(pbData);
LABEL_82:
      if ( hKey )
        RegCloseKey(hKey);
      return v39;
    }
    v42 = RegSetValueExW(hKey, L"AuthBuffer", 0, 3u, pbData, pDataOut.cbData);
    if ( v42 )
    {
      v39 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x635,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
              (const char *)v42,
              dwOptionsf);
      if ( v35 )
        LocalFree(v35);
      if ( !pbData )
        goto LABEL_82;
      v43 = LocalSize(pbData);
      for ( k = pbData; v43; --v43 )
        *k++ = 0;
      goto LABEL_81;
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
0x180020378  push    rbp
0x18002037a  push    rbx
0x18002037b  push    rsi
0x18002037c  push    rdi
0x18002037d  push    r12
0x18002037f  push    r13
0x180020381  push    r14
0x180020383  push    r15
0x180020385  lea     rbp, [rsp-0Fh]
0x18002038a  sub     rsp, 0A8h
0x180020391  mov     r14, r9
0x180020394  mov     r12d, r8d
0x180020397  mov     r15, rdx
0x18002039a  mov     rsi, rcx
0x18002039d  mov     rax, rcx
0x1800203a0  neg     rax
0x1800203a3  sbb     ecx, ecx
0x1800203a5  add     ecx, 2; char *
0x1800203a8  mov     rdx, rsi
0x1800203ab  call    CflApi__ClearScenarioDataWithReason
0x1800203b0  mov     ebx, eax
0x1800203b2  xor     r13d, r13d
0x1800203b5  test    eax, eax
0x1800203b7  jns     short loc_1800203D8
0x1800203b9  mov     rcx, [rbp+4Fh]; this
0x1800203bd  mov     r9d, eax; char *
0x1800203c0  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x1800203c7  mov     edx, 57Fh; void *
0x1800203cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800203d1  mov     eax, ebx
0x1800203d3  jmp     loc_180020A37
0x1800203d8  mov     [rbp+47h+hKey], r13
0x1800203dc  mov     [rsp+0E0h+lpdwDisposition], r13; lpdwDisposition
0x1800203e1  lea     rax, [rbp+47h+hKey]
0x1800203e5  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800203ea  mov     [rsp+0E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800203ef  mov     [rsp+0E0h+samDesired], 20006h; samDesired
0x1800203f7  mov     [rsp+0E0h+dwOptions], 1; int
0x1800203ff  xor     r9d, r9d; lpClass
0x180020402  xor     r8d, r8d; Reserved
0x180020405  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002040c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020413  call    cs:__imp_RegCreateKeyExW
0x180020419  test    eax, eax
0x18002041b  jz      short loc_180020448
0x18002041d  mov     edx, 58Ch; void *
0x180020422  mov     rcx, [rbp+4Fh]; this
0x180020426  mov     r9d, eax; char *
0x180020429  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180020430  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180020435  mov     ebx, eax
0x180020437  mov     rcx, [rbp+47h+hKey]; hKey
0x18002043b  test    rcx, rcx
0x18002043e  jz      short loc_1800203D1
0x180020440  call    cs:__imp_RegCloseKey
0x180020446  jmp     short loc_1800203D1
0x180020448  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002044c  test    rsi, rsi
0x18002044f  jz      loc_1800204FF
0x180020455  mov     [rbp+47h+lpsz], r13
0x180020459  lea     rdx, [rbp+47h+lpsz]; lplpsz
0x18002045d  mov     rcx, rsi; rclsid
0x180020460  call    cs:__imp_StringFromCLSID
0x180020466  mov     ebx, eax
0x180020468  test    eax, eax
0x18002046a  jns     short loc_180020495
0x18002046c  mov     rcx, [rbp+4Fh]; this
0x180020470  mov     r9d, eax; char *
0x180020473  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002047a  mov     edx, 591h; void *
0x18002047f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020484  mov     rcx, [rbp+47h+lpsz]; pv
0x180020488  test    rcx, rcx
0x18002048b  jz      short loc_180020437
0x18002048d  call    cs:__imp_CoTaskMemFree
0x180020493  jmp     short loc_180020437
0x180020495  mov     rax, [rbp+47h+lpsz]
0x180020499  mov     rdx, rdi
0x18002049c  inc     rdx
0x18002049f  cmp     [rax+rdx*2], r13w
0x1800204a4  jnz     short loc_18002049C
0x1800204a6  lea     edx, ds:2[rdx*2]
0x1800204ad  mov     [rsp+0E0h+samDesired], edx; cbData
0x1800204b1  mov     qword ptr [rsp+0E0h+dwOptions], rax; unsigned int
0x1800204b6  mov     r9d, 1; dwType
0x1800204bc  xor     r8d, r8d; Reserved
0x1800204bf  lea     rdx, Value; "ProviderId"
0x1800204c6  mov     rcx, [rbp+47h+hKey]; hKey
0x1800204ca  call    cs:__imp_RegSetValueExW
0x1800204d0  test    eax, eax
0x1800204d2  jz      short loc_1800204F0
0x1800204d4  mov     rcx, [rbp+4Fh]; this
0x1800204d8  mov     r9d, eax; char *
0x1800204db  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x1800204e2  mov     edx, 599h; void *
0x1800204e7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800204ec  mov     ebx, eax
0x1800204ee  jmp     short loc_180020484
0x1800204f0  mov     rcx, [rbp+47h+lpsz]; pv
0x1800204f4  test    rcx, rcx
0x1800204f7  jz      short loc_1800204FF
0x1800204f9  call    cs:__imp_CoTaskMemFree
0x1800204ff  test    r14, r14
0x180020502  jz      short loc_180020546
0x180020504  inc     rdi
0x180020507  cmp     [r14+rdi*2], r13w
0x18002050c  jnz     short loc_180020504
0x18002050e  lea     eax, ds:2[rdi*2]
0x180020515  mov     [rsp+0E0h+samDesired], eax; cbData
0x180020519  mov     qword ptr [rsp+0E0h+dwOptions], r14; lpData
0x18002051e  mov     r9d, 1; dwType
0x180020524  xor     r8d, r8d; Reserved
0x180020527  lea     rdx, aScenarioid; "ScenarioId"
0x18002052e  mov     rcx, [rbp+47h+hKey]; hKey
0x180020532  call    cs:__imp_RegSetValueExW
0x180020538  test    eax, eax
0x18002053a  jz      short loc_180020546
0x18002053c  mov     edx, 5A6h
0x180020541  jmp     loc_180020422
0x180020546  mov     rcx, [rbp+47h+lpData]
0x18002054a  test    rcx, rcx
0x18002054d  jz      short loc_180020583
0x18002054f  mov     eax, [rbp+47h+cbData]
0x180020552  mov     [rsp+0E0h+samDesired], eax; cbData
0x180020556  mov     qword ptr [rsp+0E0h+dwOptions], rcx; lpData
0x18002055b  mov     r9d, 3; dwType
0x180020561  xor     r8d, r8d; Reserved
0x180020564  lea     rdx, aScenariocontex; "ScenarioContext"
0x18002056b  mov     rcx, [rbp+47h+hKey]; hKey
0x18002056f  call    cs:__imp_RegSetValueExW
0x180020575  test    eax, eax
0x180020577  jz      short loc_180020583
0x180020579  mov     edx, 5B2h
0x18002057e  jmp     loc_180020422
0x180020583  call    CflApi__InCamSession
0x180020588  test    al, al
0x18002058a  jnz     loc_1800206B4
0x180020590  test    rsi, rsi
0x180020593  jz      loc_180020738
0x180020599  mov     rdi, [rbp+47h+hKey]
0x18002059d  test    rdi, rdi
0x1800205a0  jz      short loc_1800205BB
0x1800205a2  call    cs:__imp_GetLastError
0x1800205a8  mov     ebx, eax
0x1800205aa  mov     rcx, rdi; hKey
0x1800205ad  call    cs:__imp_RegCloseKey
0x1800205b3  mov     ecx, ebx; dwErrCode
0x1800205b5  call    cs:__imp_SetLastError
0x1800205bb  mov     [rbp+47h+hKey], r13
0x1800205bf  lea     rax, [rbp+47h+hKey]
0x1800205c3  mov     qword ptr [rsp+0E0h+dwOptions], rax; int
0x1800205c8  mov     r9d, 1; samDesired
0x1800205ce  xor     r8d, r8d; ulOptions
0x1800205d1  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800205d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800205df  call    cs:__imp_RegOpenKeyExW
0x1800205e5  mov     ebx, eax
0x1800205e7  test    eax, eax
0x1800205e9  jz      short loc_180020626
0x1800205eb  cmp     eax, 2
0x1800205ee  jz      loc_1800206B4
0x1800205f4  test    eax, eax
0x1800205f6  jle     short loc_180020601
0x1800205f8  movzx   ebx, ax
0x1800205fb  or      ebx, 80070000h
0x180020601  test    ebx, ebx
0x180020603  jns     loc_180020437
0x180020609  mov     edx, 5C9h; void *
0x18002060e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180020615  mov     r9d, ebx; char *
0x180020618  mov     rcx, [rbp+4Fh]; this
0x18002061c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020621  jmp     loc_180020437
0x180020626  mov     dword ptr [rbp+47h+lpsz], r13d
0x18002062a  mov     dword ptr [rbp+47h+pvData], r13d
0x18002062e  mov     [rbp+47h+pcbData], 4
0x180020635  lea     rax, [rbp+47h+pcbData]
0x180020639  mov     [rsp+0E0h+lpSecurityAttributes], rax; pcbData
0x18002063e  lea     rax, [rbp+47h+pvData]
0x180020642  mov     qword ptr [rsp+0E0h+samDesired], rax; pvData
0x180020647  lea     rax, [rbp+47h+lpsz]
0x18002064b  mov     qword ptr [rsp+0E0h+dwOptions], rax; pdwType
0x180020650  mov     r9d, 10h; dwFlags
0x180020656  lea     r8, aDefaultaccount; "DefaultAccountAction"
0x18002065d  xor     edx, edx; lpSubKey
0x18002065f  mov     rcx, [rbp+47h+hKey]; hkey
0x180020663  call    cs:__imp_RegGetValueW
0x180020669  mov     ebx, eax
0x18002066b  test    eax, eax
0x18002066d  jz      short loc_180020693
0x18002066f  cmp     eax, 2
0x180020672  jz      short loc_1800206B4
0x180020674  test    eax, eax
0x180020676  jle     short loc_180020681
0x180020678  movzx   ebx, ax
0x18002067b  or      ebx, 80070000h
0x180020681  test    ebx, ebx
0x180020683  jns     loc_180020437
0x180020689  mov     edx, 5DCh
0x18002068e  jmp     loc_18002060E
0x180020693  cmp     dword ptr [rbp+47h+lpsz], 4
0x180020697  jnz     loc_180020729
0x18002069d  cmp     [rbp+47h+pcbData], 4
0x1800206a1  jnz     short loc_18002071A
0x1800206a3  cmp     dword ptr [rbp+47h+pvData], 1
0x1800206a7  setz    dil
0x1800206ab  test    dil, dil
0x1800206ae  jnz     loc_18002073B
0x1800206b4  test    r15, r15
0x1800206b7  jz      loc_180020A26
0x1800206bd  mov     dword ptr [rbp+47h+pDataIn+4], r13d
0x1800206c1  mov     [rbp+47h+pDataIn.pbData], r15
0x1800206c5  mov     [rbp+47h+pDataIn.cbData], r12d
0x1800206c9  xorps   xmm0, xmm0
0x1800206cc  movups  xmmword ptr [rbp+47h+pDataOut.cbData], xmm0
0x1800206d0  lea     rax, [rbp+47h+pDataOut]
0x1800206d4  mov     [rsp+0E0h+lpSecurityAttributes], rax; pDataOut
0x1800206d9  mov     [rsp+0E0h+samDesired], 5; dwFlags
0x1800206e1  mov     qword ptr [rsp+0E0h+dwOptions], r13; int
0x1800206e6  xor     r9d, r9d; pvReserved
0x1800206e9  xor     r8d, r8d; pOptionalEntropy
0x1800206ec  xor     edx, edx; szDataDescr
0x1800206ee  lea     rcx, [rbp+47h+pDataIn]; pDataIn
0x1800206f2  call    cs:__imp_CryptProtectData
0x1800206f8  test    eax, eax
0x1800206fa  jnz     loc_1800207FE
0x180020700  mov     rcx, [rbp+4Fh]; this
0x180020704  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002070b  mov     edx, 614h; void *
0x180020710  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020715  jmp     loc_180020435
0x18002071a  mov     ebx, 80070018h
0x18002071f  mov     edx, 5E4h
0x180020724  jmp     loc_18002060E
0x180020729  mov     ebx, 80070057h
0x18002072e  mov     edx, 5E1h
0x180020733  jmp     loc_18002060E
0x180020738  mov     dil, r13b
0x18002073b  mov     r14, [rbp+47h+hKey]
0x18002073f  test    r14, r14
0x180020742  jz      short loc_18002075D
0x180020744  call    cs:__imp_GetLastError
0x18002074a  mov     ebx, eax
0x18002074c  mov     rcx, r14; hKey
0x18002074f  call    cs:__imp_RegCloseKey
0x180020755  mov     ecx, ebx; dwErrCode
0x180020757  call    cs:__imp_SetLastError
0x18002075d  mov     [rbp+47h+hKey], r13
0x180020761  mov     [rsp+0E0h+lpdwDisposition], r13; lpdwDisposition
0x180020766  lea     rax, [rbp+47h+hKey]
0x18002076a  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18002076f  mov     [rsp+0E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180020774  mov     [rsp+0E0h+samDesired], 20006h; samDesired
0x18002077c  mov     [rsp+0E0h+dwOptions], 1; dwOptions
0x180020784  xor     r9d, r9d; lpClass
0x180020787  xor     r8d, r8d; Reserved
0x18002078a  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180020791  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020798  call    cs:__imp_RegCreateKeyExW
0x18002079e  test    eax, eax
0x1800207a0  jz      short loc_1800207AC
0x1800207a2  mov     edx, 5F7h
0x1800207a7  jmp     loc_180020422
0x1800207ac  mov     dword ptr [rbp+47h+lpsz], 1
0x1800207b3  test    rsi, rsi
0x1800207b6  jz      short loc_1800207C4
0x1800207b8  test    dil, dil
0x1800207bb  lea     rdx, aLaunchcflscena; "LaunchCflScenario"
0x1800207c2  jnz     short loc_1800207CB
0x1800207c4  lea     rdx, aTransitioncfls; "TransitionCflScenario"
0x1800207cb  mov     r9d, 4; dwType
0x1800207d1  mov     [rsp+0E0h+samDesired], r9d; cbData
0x1800207d6  lea     rax, [rbp+47h+lpsz]
0x1800207da  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x1800207df  xor     r8d, r8d; Reserved
0x1800207e2  mov     rcx, [rbp+47h+hKey]; hKey
0x1800207e6  call    cs:__imp_RegSetValueExW
0x1800207ec  test    eax, eax
0x1800207ee  jz      loc_1800206B4
0x1800207f4  mov     edx, 601h
0x1800207f9  jmp     loc_180020422
0x1800207fe  mov     rbx, [rbp+47h+pDataOut.pbData]
0x180020802  mov     [rbp+47h+pDataOut.pbData], r13
0x180020806  mov     [rbp+47h+pvData], r13
0x18002080a  lea     rdx, [rbp+47h+lpsz]
0x18002080e  lea     rcx, [rbp+47h+pvData]
0x180020812  call    CflApi__GetProtectedScenarioDataSecurityDescriptor
0x180020817  mov     edi, eax
0x180020819  test    eax, eax
0x18002081b  jns     short loc_180020886
0x18002081d  mov     rcx, [rbp+4Fh]; this
0x180020821  mov     r9d, eax; char *
0x180020824  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002082b  mov     edx, 61Bh; void *
0x180020830  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020835  mov     rcx, [rbp+47h+pvData]; hMem
0x180020839  test    rcx, rcx
0x18002083c  jz      short loc_180020844
0x18002083e  call    cs:__imp_LocalFree
0x180020844  test    rbx, rbx
  ... truncated ...
```
