# GenerateAttestationClaims(IX509PrivateKey *,bool,bool,uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x1800344c8`
- end: `0x180034b78`
- name: `?GenerateAttestationClaims@@YAJPEAUIX509PrivateKey@@_N1PEAPEAEPEAK23@Z`
- size: `1712`
- prototype: `__int64 __fastcall(struct IX509PrivateKey *, bool, bool, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180034b80`

## callees

- `0x18000b0f4`
- `0x180012fcc`
- `0x1800141b0`
- `0x1800344c8`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800348b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800349e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800348b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800349e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034962`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034a92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034ab3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034962`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034a92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034ab3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034899`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003494e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800349cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034a7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034a9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034899`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003494e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800349cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034a7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034a9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800346fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800347b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800346fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800347b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034592`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034695`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003471b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800347d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034592`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034695`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003471b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800347d7`
- `DMCmnUtils!DmSetWindowsAIKStorageLocationOld` at `0x180034778`
- `DMCmnUtils!DmSetWindowsAIKStorageLocationOld` at `0x180034778`
- `OLEAUT32!__imp_SysFreeString` at `0x1800345f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18003460f`
- `OLEAUT32!__imp_SysFreeString` at `0x180034687`
- `OLEAUT32!__imp_SysFreeString` at `0x180034aea`
- `OLEAUT32!__imp_SysFreeString` at `0x180034b00`
- `OLEAUT32!__imp_SysFreeString` at `0x1800345f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18003460f`
- `OLEAUT32!__imp_SysFreeString` at `0x180034687`
- `OLEAUT32!__imp_SysFreeString` at `0x180034aea`
- `OLEAUT32!__imp_SysFreeString` at `0x180034b00`
- `ncrypt!NCryptCreateClaim` at `0x18003485f`
- `ncrypt!NCryptCreateClaim` at `0x180034912`
- `ncrypt!NCryptCreateClaim` at `0x18003485f`
- `ncrypt!NCryptCreateClaim` at `0x180034912`
- `ncrypt!NCryptExportKey` at `0x18003499b`
- `ncrypt!NCryptExportKey` at `0x180034a42`
- `ncrypt!NCryptExportKey` at `0x18003499b`
- `ncrypt!NCryptExportKey` at `0x180034a42`
- `ncrypt!NCryptFreeObject` at `0x180034584`
- `ncrypt!NCryptFreeObject` at `0x180034625`
- `ncrypt!NCryptFreeObject` at `0x18003463b`
- `ncrypt!NCryptFreeObject` at `0x180034655`
- `ncrypt!NCryptFreeObject` at `0x18003470d`
- `ncrypt!NCryptFreeObject` at `0x1800347c9`
- `ncrypt!NCryptFreeObject` at `0x180034b16`
- `ncrypt!NCryptFreeObject` at `0x180034b2c`
- `ncrypt!NCryptFreeObject` at `0x180034b42`
- `ncrypt!NCryptFreeObject` at `0x180034584`
- `ncrypt!NCryptFreeObject` at `0x180034625`
- `ncrypt!NCryptFreeObject` at `0x18003463b`
- `ncrypt!NCryptFreeObject` at `0x180034655`
- `ncrypt!NCryptFreeObject` at `0x18003470d`
- `ncrypt!NCryptFreeObject` at `0x1800347c9`
- `ncrypt!NCryptFreeObject` at `0x180034b16`
- `ncrypt!NCryptFreeObject` at `0x180034b2c`
- `ncrypt!NCryptFreeObject` at `0x180034b42`
- `ncrypt!NCryptOpenKey` at `0x18003473d`
- `ncrypt!NCryptOpenKey` at `0x1800347fe`
- `ncrypt!NCryptOpenKey` at `0x18003473d`
- `ncrypt!NCryptOpenKey` at `0x1800347fe`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800345b0`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800345b0`

## string_xrefs

- `0x1800345d7`: `NCryptOpenStorageProvider`
- `0x180034768`: `NCryptOpenKey(dmKey)`
- `0x18003488a`: `NCryptCreateClaim(size)`
- `0x180034829`: `NCryptOpenKey(hAIK)`
- `0x180034935`: `NCryptCreateClaim`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GenerateAttestationClaims(
        struct IX509PrivateKey *a1,
        unsigned __int8 a2,
        char a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  int v9; // r12d
  SECURITY_STATUS Claim; // eax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  const wchar_t *v14; // r8
  HRESULT (__stdcall *get_ContainerName)(IX509PrivateKey *, BSTR *); // r15
  OLECHAR *v16; // rsi
  DWORD LastError; // ebx
  const WCHAR *v18; // r15
  NCRYPT_HANDLE v19; // r14
  DWORD v20; // ebx
  int v21; // eax
  __int64 v22; // rcx
  HANDLE ProcessHeap; // rax
  void *v24; // rsi
  SECURITY_STATUS v25; // eax
  __int64 v26; // rcx
  const wchar_t *v27; // r8
  HANDLE v28; // rax
  DWORD v29; // ebx
  HANDLE v30; // rax
  BYTE *v31; // r14
  SECURITY_STATUS v32; // eax
  __int64 v33; // rcx
  HANDLE v34; // rax
  HANDLE v35; // rax
  int dwFlags; // [rsp+20h] [rbp-61h]
  NCRYPT_HANDLE hKey; // [rsp+40h] [rbp-41h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+48h] [rbp-39h] BYREF
  NCRYPT_HANDLE phKey; // [rsp+50h] [rbp-31h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-29h] BYREF
  LPCWSTR pszProviderName; // [rsp+60h] [rbp-21h] BYREF
  DWORD pcbResult; // [rsp+68h] [rbp-19h] BYREF
  _QWORD v44[10]; // [rsp+70h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]
  SECURITY_STATUS v46; // [rsp+D8h] [rbp+57h] BYREF

  v9 = a2;
  v46 = 0;
  v44[0] = "GenerateAttestationClaims";
  v44[1] = &v46;
  hObject = 0;
  phKey = 0;
  hKey = 0;
  bstrString = 0;
  v44[2] = 0;
  v44[3] = 0;
  pcbResult = 0;
  pszProviderName = 0;
  Claim = ((__int64 (__fastcall *)(struct IX509PrivateKey *, LPCWSTR *))a1->lpVtbl->get_ProviderName)(
            a1,
            &pszProviderName);
  v13 = Claim;
  v46 = Claim;
  if ( Claim < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_10;
    v14 = L"key->get_ProviderName";
    goto LABEL_9;
  }
  hObject = 0;
  Claim = NCryptOpenStorageProvider(&hObject, pszProviderName, 0);
  v13 = Claim;
  v46 = Claim;
  if ( Claim < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_10;
    v14 = L"NCryptOpenStorageProvider";
    goto LABEL_9;
  }
  get_ContainerName = a1->lpVtbl->get_ContainerName;
  v16 = bstrString;
  if ( bstrString )
  {
    LastError = GetLastError();
    SysFreeString(v16);
    SetLastError(LastError);
  }
  bstrString = 0;
  Claim = ((__int64 (__fastcall *)(struct IX509PrivateKey *, BSTR *))get_ContainerName)(a1, &bstrString);
  v13 = Claim;
  v46 = Claim;
  if ( Claim < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_10;
    v14 = L"key->get_ContainerName";
    goto LABEL_9;
  }
  v18 = bstrString;
  v19 = phKey;
  if ( phKey )
  {
    v20 = GetLastError();
    NCryptFreeObject(v19);
    SetLastError(v20);
  }
  phKey = 0;
  Claim = NCryptOpenKey(hObject, &phKey, v18, 0, (32 * v9) | 0x40);
  v13 = Claim;
  v46 = Claim;
  if ( Claim < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_10;
    v14 = L"NCryptOpenKey(dmKey)";
    goto LABEL_9;
  }
  v21 = DmSetWindowsAIKStorageLocationOld(hObject);
  v46 = v21;
  if ( v21 < 0 && a3 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    McTemplateU0zd_EventWriteTransfer(
      v22,
      EnterpriseDiagnosticsTPMFunctionFailure,
      L"SetWindowsAIKStorageLocation",
      (unsigned int)v21);
  hKey = 0;
  Claim = NCryptOpenKey(hObject, &hKey, L"Windows AIK", 0, 0);
  v13 = Claim;
  v46 = Claim;
  if ( Claim < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_10;
    v14 = L"NCryptOpenKey(hAIK)";
    goto LABEL_9;
  }
  Claim = NCryptCreateClaim(phKey, hKey, 2);
  v13 = Claim;
  v46 = Claim;
  if ( Claim < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_10;
    v14 = L"NCryptCreateClaim(size)";
LABEL_9:
    McTemplateU0zd_EventWriteTransfer(v12, EnterpriseDiagnosticsTPMFunctionFailure, v14, (unsigned int)Claim);
    v13 = v46;
LABEL_10:
    if ( pszProviderName )
      SysFreeString((BSTR)pszProviderName);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( hKey )
      NCryptFreeObject(hKey);
    if ( phKey )
      NCryptFreeObject(phKey);
    if ( hObject )
      NCryptFreeObject(hObject);
    goto LABEL_74;
  }
  ProcessHeap = GetProcessHeap();
  v24 = HeapAlloc(ProcessHeap, 8u, 0);
  if ( !v24 )
  {
    v13 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5BE,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)0x8007000ELL,
      0);
    goto LABEL_10;
  }
  v25 = NCryptCreateClaim(phKey, hKey, 2);
  v13 = v25;
  v46 = v25;
  if ( v25 < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_51;
    v27 = L"NCryptCreateClaim";
    goto LABEL_50;
  }
  v25 = NCryptExportKey(hKey, 0, L"RSAPUBLICBLOB", 0, 0, 0, &pcbResult, 0);
  v13 = v25;
  v46 = v25;
  if ( v25 < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_51;
    v27 = L"NCryptExportKey(hAIK size)";
LABEL_50:
    McTemplateU0zd_EventWriteTransfer(v26, EnterpriseDiagnosticsTPMFunctionFailure, v27, (unsigned int)v25);
    v13 = v46;
LABEL_51:
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v24);
    goto LABEL_10;
  }
  v29 = pcbResult;
  v30 = GetProcessHeap();
  v31 = (BYTE *)HeapAlloc(v30, 8u, v29);
  if ( !v31 )
  {
    v13 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
    goto LABEL_51;
  }
  v32 = NCryptExportKey(hKey, 0, L"RSAPUBLICBLOB", 0, v31, pcbResult, &pcbResult, 0);
  v13 = v32;
  v46 = v32;
  if ( v32 < 0 )
  {
    if ( a3 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(
        v33,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"NCryptExportKey(hAIK)",
        (unsigned int)v32);
      v13 = v46;
    }
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v24);
    v35 = GetProcessHeap();
    HeapFree(v35, 0, v31);
    goto LABEL_10;
  }
  *a4 = (unsigned __int8 *)v24;
  *a5 = 0;
  *a6 = v31;
  *a7 = pcbResult;
  if ( pszProviderName )
    SysFreeString((BSTR)pszProviderName);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( hKey )
    NCryptFreeObject(hKey);
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( hObject )
    NCryptFreeObject(hObject);
  v13 = 0;
LABEL_74:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v44);
  return v13;
}

```

## disassembly

```asm
0x1800344c8  mov     [rsp-8+arg_10], rbx
0x1800344cd  push    rbp
0x1800344ce  push    rsi
0x1800344cf  push    rdi
0x1800344d0  push    r12
0x1800344d2  push    r13
0x1800344d4  push    r14
0x1800344d6  push    r15
0x1800344d8  lea     rbp, [rsp-0Fh]
0x1800344dd  sub     rsp, 90h
0x1800344e4  mov     r13, r9
0x1800344e7  mov     dil, r8b
0x1800344ea  movzx   r12d, dl
0x1800344ee  mov     r14, rcx
0x1800344f1  xor     esi, esi
0x1800344f3  mov     [rbp+3Fh+arg_8], esi
0x1800344f6  lea     rax, aGenerateattest; "GenerateAttestationClaims"
0x1800344fd  mov     [rbp+3Fh+var_50], rax
0x180034501  lea     rax, [rbp+3Fh+arg_8]
0x180034505  mov     [rbp+3Fh+var_48], rax
0x180034509  mov     [rbp+3Fh+hObject], rsi
0x18003450d  mov     [rbp+3Fh+phKey], rsi
0x180034511  mov     [rbp+3Fh+hKey], rsi
0x180034515  mov     [rbp+3Fh+bstrString], rsi
0x180034519  mov     [rbp+3Fh+var_40], rsi
0x18003451d  mov     [rbp+3Fh+var_38], rsi
0x180034521  mov     [rbp+3Fh+var_58], esi
0x180034524  mov     dword ptr [rbp+3Fh+dwBytes], esi
0x180034527  mov     [rbp+3Fh+pszProviderName], rsi
0x18003452b  mov     rax, [rcx]
0x18003452e  lea     rdx, [rbp+3Fh+pszProviderName]
0x180034532  mov     rax, [rax+0C8h]
0x180034539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003453e  mov     ebx, eax
0x180034540  mov     [rbp+3Fh+arg_8], eax
0x180034543  test    eax, eax
0x180034545  jns     short loc_180034566
0x180034547  test    dil, dil
0x18003454a  jz      loc_1800345F0
0x180034550  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180034557  jz      loc_1800345F0
0x18003455d  lea     r8, aKeyGetProvider; "key->get_ProviderName"
0x180034564  jmp     short loc_1800345DE
0x180034566  mov     r15, [rbp+3Fh+pszProviderName]
0x18003456a  mov     rsi, [rbp+3Fh+hObject]
0x18003456e  test    rsi, rsi
0x180034571  jz      short loc_18003459E
0x180034573  call    cs:__imp_GetLastError
0x18003457a  nop     dword ptr [rax+rax+00h]
0x18003457f  mov     ebx, eax
0x180034581  mov     rcx, rsi; hObject
0x180034584  call    cs:__imp_NCryptFreeObject
0x18003458b  nop     dword ptr [rax+rax+00h]
0x180034590  mov     ecx, ebx; dwErrCode
0x180034592  call    cs:__imp_SetLastError
0x180034599  nop     dword ptr [rax+rax+00h]
0x18003459e  mov     [rbp+3Fh+hObject], 0
0x1800345a6  xor     r8d, r8d; dwFlags
0x1800345a9  mov     rdx, r15; pszProviderName
0x1800345ac  lea     rcx, [rbp+3Fh+hObject]; phProvider
0x1800345b0  call    cs:__imp_NCryptOpenStorageProvider
0x1800345b7  nop     dword ptr [rax+rax+00h]
0x1800345bc  mov     ebx, eax
0x1800345be  mov     [rbp+3Fh+arg_8], eax
0x1800345c1  test    eax, eax
0x1800345c3  jns     loc_180034666
0x1800345c9  test    dil, dil
0x1800345cc  jz      short loc_1800345F0
0x1800345ce  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x1800345d5  jz      short loc_1800345F0
0x1800345d7  lea     r8, aNcryptopenstor_0; "NCryptOpenStorageProvider"
0x1800345de  mov     r9d, eax
0x1800345e1  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x1800345e8  call    McTemplateU0zd_EventWriteTransfer
0x1800345ed  mov     ebx, [rbp+3Fh+arg_8]
0x1800345f0  mov     rcx, [rbp+3Fh+pszProviderName]; bstrString
0x1800345f4  test    rcx, rcx
0x1800345f7  jz      short loc_180034606
0x1800345f9  call    cs:__imp_SysFreeString
0x180034600  nop     dword ptr [rax+rax+00h]
0x180034605  nop
0x180034606  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x18003460a  test    rcx, rcx
0x18003460d  jz      short loc_18003461C
0x18003460f  call    cs:__imp_SysFreeString
0x180034616  nop     dword ptr [rax+rax+00h]
0x18003461b  nop
0x18003461c  mov     rcx, [rbp+3Fh+hKey]; hObject
0x180034620  test    rcx, rcx
0x180034623  jz      short loc_180034632
0x180034625  call    cs:__imp_NCryptFreeObject
0x18003462c  nop     dword ptr [rax+rax+00h]
0x180034631  nop
0x180034632  mov     rcx, [rbp+3Fh+phKey]; hObject
0x180034636  test    rcx, rcx
0x180034639  jz      short loc_180034648
0x18003463b  call    cs:__imp_NCryptFreeObject
0x180034642  nop     dword ptr [rax+rax+00h]
0x180034647  nop
0x180034648  mov     rcx, [rbp+3Fh+hObject]; hObject
0x18003464c  test    rcx, rcx
0x18003464f  jz      loc_180034B51
0x180034655  call    cs:__imp_NCryptFreeObject
0x18003465c  nop     dword ptr [rax+rax+00h]
0x180034661  jmp     loc_180034B51
0x180034666  mov     rax, [r14]
0x180034669  mov     r15, [rax+78h]
0x18003466d  mov     rsi, [rbp+3Fh+bstrString]
0x180034671  test    rsi, rsi
0x180034674  jz      short loc_1800346A1
0x180034676  call    cs:__imp_GetLastError
0x18003467d  nop     dword ptr [rax+rax+00h]
0x180034682  mov     ebx, eax
0x180034684  mov     rcx, rsi; bstrString
0x180034687  call    cs:__imp_SysFreeString
0x18003468e  nop     dword ptr [rax+rax+00h]
0x180034693  mov     ecx, ebx; dwErrCode
0x180034695  call    cs:__imp_SetLastError
0x18003469c  nop     dword ptr [rax+rax+00h]
0x1800346a1  mov     [rbp+3Fh+bstrString], 0
0x1800346a9  lea     rdx, [rbp+3Fh+bstrString]
0x1800346ad  mov     rcx, r14
0x1800346b0  mov     rax, r15
0x1800346b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800346b8  mov     ebx, eax
0x1800346ba  mov     [rbp+3Fh+arg_8], eax
0x1800346bd  test    eax, eax
0x1800346bf  jns     short loc_1800346E3
0x1800346c1  test    dil, dil
0x1800346c4  jz      loc_1800345F0
0x1800346ca  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x1800346d1  jz      loc_1800345F0
0x1800346d7  lea     r8, aKeyGetContaine; "key->get_ContainerName"
0x1800346de  jmp     loc_1800345DE
0x1800346e3  mov     esi, r12d
0x1800346e6  shl     esi, 5
0x1800346e9  or      esi, 40h
0x1800346ec  mov     r15, [rbp+3Fh+bstrString]
0x1800346f0  mov     r14, [rbp+3Fh+phKey]
0x1800346f4  xor     r12d, r12d
0x1800346f7  test    r14, r14
0x1800346fa  jz      short loc_180034727
0x1800346fc  call    cs:__imp_GetLastError
0x180034703  nop     dword ptr [rax+rax+00h]
0x180034708  mov     ebx, eax
0x18003470a  mov     rcx, r14; hObject
0x18003470d  call    cs:__imp_NCryptFreeObject
0x180034714  nop     dword ptr [rax+rax+00h]
0x180034719  mov     ecx, ebx; dwErrCode
0x18003471b  call    cs:__imp_SetLastError
0x180034722  nop     dword ptr [rax+rax+00h]
0x180034727  mov     [rbp+3Fh+phKey], r12
0x18003472b  mov     [rsp+0C0h+dwFlags], esi; dwFlags
0x18003472f  xor     r9d, r9d; dwLegacyKeySpec
0x180034732  mov     r8, r15; pszKeyName
0x180034735  lea     rdx, [rbp+3Fh+phKey]; phKey
0x180034739  mov     rcx, [rbp+3Fh+hObject]; hProvider
0x18003473d  call    cs:__imp_NCryptOpenKey
0x180034744  nop     dword ptr [rax+rax+00h]
0x180034749  mov     ebx, eax
0x18003474b  mov     [rbp+3Fh+arg_8], eax
0x18003474e  test    eax, eax
0x180034750  jns     short loc_180034774
0x180034752  test    dil, dil
0x180034755  jz      loc_1800345F0
0x18003475b  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180034762  jz      loc_1800345F0
0x180034768  lea     r8, aNcryptopenkeyD; "NCryptOpenKey(dmKey)"
0x18003476f  jmp     loc_1800345DE
0x180034774  mov     rcx, [rbp+3Fh+hObject]
0x180034778  call    cs:__imp_?DmSetWindowsAIKStorageLocationOld@@YAJ_K@Z; DmSetWindowsAIKStorageLocationOld(unsigned __int64)
0x18003477f  nop     dword ptr [rax+rax+00h]
0x180034784  mov     [rbp+3Fh+arg_8], eax
0x180034787  test    eax, eax
0x180034789  jns     short loc_1800347AF
0x18003478b  test    dil, dil
0x18003478e  jz      short loc_1800347AF
0x180034790  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180034797  jz      short loc_1800347AF
0x180034799  mov     r9d, eax
0x18003479c  lea     r8, aSetwindowsaiks; "SetWindowsAIKStorageLocation"
0x1800347a3  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x1800347aa  call    McTemplateU0zd_EventWriteTransfer
0x1800347af  mov     rsi, [rbp+3Fh+hKey]
0x1800347b3  test    rsi, rsi
0x1800347b6  jz      short loc_1800347E3
0x1800347b8  call    cs:__imp_GetLastError
0x1800347bf  nop     dword ptr [rax+rax+00h]
0x1800347c4  mov     ebx, eax
0x1800347c6  mov     rcx, rsi; hObject
0x1800347c9  call    cs:__imp_NCryptFreeObject
0x1800347d0  nop     dword ptr [rax+rax+00h]
0x1800347d5  mov     ecx, ebx; dwErrCode
0x1800347d7  call    cs:__imp_SetLastError
0x1800347de  nop     dword ptr [rax+rax+00h]
0x1800347e3  mov     [rbp+3Fh+hKey], r12
0x1800347e7  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x1800347ec  xor     r9d, r9d; dwLegacyKeySpec
0x1800347ef  lea     r8, pszKeyName; "Windows AIK"
0x1800347f6  lea     rdx, [rbp+3Fh+hKey]; phKey
0x1800347fa  mov     rcx, [rbp+3Fh+hObject]; hProvider
0x1800347fe  call    cs:__imp_NCryptOpenKey
0x180034805  nop     dword ptr [rax+rax+00h]
0x18003480a  mov     ebx, eax
0x18003480c  mov     [rbp+3Fh+arg_8], eax
0x18003480f  test    eax, eax
0x180034811  jns     short loc_180034835
0x180034813  test    dil, dil
0x180034816  jz      loc_1800345F0
0x18003481c  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180034823  jz      loc_1800345F0
0x180034829  lea     r8, aNcryptopenkeyH; "NCryptOpenKey(hAIK)"
0x180034830  jmp     loc_1800345DE
0x180034835  mov     [rsp+0C0h+var_88], r12d
0x18003483a  lea     rax, [rbp+3Fh+dwBytes]
0x18003483e  mov     [rsp+0C0h+pcbResult], rax
0x180034843  mov     [rsp+0C0h+cbOutput], r12d
0x180034848  mov     qword ptr [rsp+0C0h+dwFlags], r12; int
0x18003484d  xor     r9d, r9d
0x180034850  lea     r14d, [r9+2]
0x180034854  mov     r8d, r14d
0x180034857  mov     rdx, [rbp+3Fh+hKey]
0x18003485b  mov     rcx, [rbp+3Fh+phKey]
0x18003485f  call    cs:__imp_NCryptCreateClaim
0x180034866  nop     dword ptr [rax+rax+00h]
0x18003486b  mov     ebx, eax
0x18003486d  mov     [rbp+3Fh+arg_8], eax
0x180034870  test    eax, eax
0x180034872  jns     short loc_180034896
0x180034874  test    dil, dil
0x180034877  jz      loc_1800345F0
0x18003487d  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180034884  jz      loc_1800345F0
0x18003488a  lea     r8, aNcryptcreatecl_1; "NCryptCreateClaim(size)"
0x180034891  jmp     loc_1800345DE
0x180034896  mov     ebx, dword ptr [rbp+3Fh+dwBytes]
0x180034899  call    cs:__imp_GetProcessHeap
0x1800348a0  nop     dword ptr [rax+rax+00h]
0x1800348a5  mov     r8d, ebx; dwBytes
0x1800348a8  mov     r15d, 8
0x1800348ae  mov     edx, r15d; dwFlags
0x1800348b1  mov     rcx, rax; hHeap
0x1800348b4  call    cs:__imp_HeapAlloc
0x1800348bb  nop     dword ptr [rax+rax+00h]
0x1800348c0  mov     rsi, rax
0x1800348c3  test    rax, rax
0x1800348c6  jnz     short loc_1800348EA
0x1800348c8  mov     rcx, [rbp+47h]; this
0x1800348cc  mov     ebx, 8007000Eh
0x1800348d1  mov     r9d, ebx; char *
0x1800348d4  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800348db  mov     edx, 5BEh; void *
0x1800348e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800348e5  jmp     loc_1800345F0
0x1800348ea  mov     [rsp+0C0h+var_88], r12d
0x1800348ef  lea     rax, [rbp+3Fh+dwBytes]
0x1800348f3  mov     [rsp+0C0h+pcbResult], rax
0x1800348f8  mov     eax, dword ptr [rbp+3Fh+dwBytes]
0x1800348fb  mov     [rsp+0C0h+cbOutput], eax
0x1800348ff  mov     qword ptr [rsp+0C0h+dwFlags], rsi
0x180034904  xor     r9d, r9d
0x180034907  mov     r8d, r14d
0x18003490a  mov     rdx, [rbp+3Fh+hKey]
0x18003490e  mov     rcx, [rbp+3Fh+phKey]
0x180034912  call    cs:__imp_NCryptCreateClaim
0x180034919  nop     dword ptr [rax+rax+00h]
0x18003491e  mov     ebx, eax
0x180034920  mov     [rbp+3Fh+arg_8], eax
0x180034923  test    eax, eax
0x180034925  jns     short loc_180034973
0x180034927  test    dil, dil
0x18003492a  jz      short loc_18003494E
0x18003492c  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180034933  jz      short loc_18003494E
0x180034935  lea     r8, aNcryptcreatecl_0; "NCryptCreateClaim"
0x18003493c  mov     r9d, eax
0x18003493f  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180034946  call    McTemplateU0zd_EventWriteTransfer
0x18003494b  mov     ebx, [rbp+3Fh+arg_8]
0x18003494e  call    cs:__imp_GetProcessHeap
0x180034955  nop     dword ptr [rax+rax+00h]
0x18003495a  mov     rcx, rax; hHeap
0x18003495d  mov     r8, rsi; lpMem
0x180034960  xor     edx, edx; dwFlags
0x180034962  call    cs:__imp_HeapFree
0x180034969  nop     dword ptr [rax+rax+00h]
0x18003496e  jmp     loc_1800345F0
0x180034973  mov     [rsp+0C0h+var_88], r12d; dwFlags
0x180034978  lea     rax, [rbp+3Fh+var_58]
0x18003497c  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x180034981  mov     [rsp+0C0h+cbOutput], r12d; cbOutput
0x180034986  mov     qword ptr [rsp+0C0h+dwFlags], r12; int
0x18003498b  xor     r9d, r9d; pParameterList
0x18003498e  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x180034995  xor     edx, edx; hExportKey
0x180034997  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18003499b  call    cs:__imp_NCryptExportKey
0x1800349a2  nop     dword ptr [rax+rax+00h]
0x1800349a7  mov     ebx, eax
0x1800349a9  mov     [rbp+3Fh+arg_8], eax
  ... truncated ...
```
