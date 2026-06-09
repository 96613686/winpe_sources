# VerifyMsiObjectAgainstSAFER(IMsiServices &,IMsiStorage *,ushort const *,ushort const *,stEnum,bool,SAFER_LEVEL_HANDLE__ * *)

- ea: `0x1800ff6a4`
- end: `0x1801008fb`
- name: `?VerifyMsiObjectAgainstSAFER@@YA?AW4iesSaferResult@@AEAVIMsiServices@@PEAVIMsiStorage@@PEBG2W4stEnum@@_NPEAPEAUSAFER_LEVEL_HANDLE__@@@Z`
- size: `4695`
- prototype: `enum iesSaferResult __high(struct IMsiServices *, struct IMsiStorage *, const unsigned __int16 *, const unsigned __int16 *, enum stEnum, bool, struct SAFER_LEVEL_HANDLE__ **)`
- caller_count: `5`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d730`
- `0x1800e7920`
- `0x18013882c`
- `0x180140058`
- `0x1801459d8`

## callees

- `0x180005af8`
- `0x18000c4bc`
- `0x180010ac0`
- `0x180013d64`
- `0x180014f18`
- `0x180015c14`
- `0x180018ee0`
- `0x180019cc0`
- `0x18002e870`
- `0x1800bfc6c`
- `0x1800ff6a4`
- `0x180100904`
- `0x18013def0`
- `0x1801459d8`
- `0x1801d4fac`
- `0x18025c7f0`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x1800ffe23`
- `ADVAPI32!GetTokenInformation` at `0x1800ffe23`
- `KERNEL32!CloseHandle` at `0x1800ffe8a`
- `KERNEL32!CloseHandle` at `0x1800ffe8a`
- `KERNEL32!GetLastError` at `0x1800ffd4c`
- `KERNEL32!GetLastError` at `0x1800ffe33`
- `KERNEL32!GetLastError` at `0x1800fff39`
- `KERNEL32!GetLastError` at `0x1800fffa7`
- `KERNEL32!GetLastError` at `0x18010021a`
- `KERNEL32!GetLastError` at `0x1800ffd4c`
- `KERNEL32!GetLastError` at `0x1800ffe33`
- `KERNEL32!GetLastError` at `0x1800fff39`
- `KERNEL32!GetLastError` at `0x1800fffa7`
- `KERNEL32!GetLastError` at `0x18010021a`

## string_xrefs

- `0x1800ffe4d`: `GetTokenInformation failed with error %d`
- `0x1800ffcca`: `SOFTWARE RESTRICTION POLICY: %s is a URL that maps to URL security zone %d (%s)`
- `0x1800ffd58`: `SAFER: Unable to create a fully trusted authorization level.  GetLastError returned %d`
- `0x1800ffd72`: `SOFTWARE RESTRICTION POLICY: %s is permitted to run because the user token authorizes execution (system or service token).`
- `0x1800ffedc`: `SOFTWARE RESTRICTION POLICY: %s is permitted to run because the user token authorizes execution (marked SANDBOX_INERT).`
- `0x1800fff4a`: `SOFTWARE RESTRICTION POLICY: Unable to reload software restriction policy. %s is not considered to be trusted. GetLastError = %d`
- `0x180100388`: `Configured`
- `0x180100394`: `SOFTWARE RESTRICTION POLICY: The %s software restriction %s policy default security level disallows execution. The returned execution level was %d`
- `0x180100512`: `configured`
- `0x180100675`: `configured`
- `0x1801006f4`: `configured`
- `0x180100767`: `configured`
- `0x1801007a2`: `SOFTWARE RESTRICTION POLICY: The path rule '%s' with image name '%s' in the %s software restriction %s policy disallows execution. The returned execution level was %d`

## pseudocode

```c
__int64 __fastcall VerifyMsiObjectAgainstSAFER(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int8 a6,
        _QWORD *a7)
{
  char v7; // r12
  const unsigned __int16 *v8; // r14
  unsigned int v10; // esi
  int v11; // r8d
  const unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rbx
  char v16; // r12
  AppIdHelper *v17; // rcx
  AppIdHelper *v18; // rax
  int v19; // eax
  bool *v20; // rdx
  DWORD v21; // eax
  const unsigned __int16 *v22; // r9
  DWORD LastError; // eax
  DWORD v25; // eax
  _DWORD *v26; // rax
  _DWORD *v27; // rbx
  _DWORD *v28; // rax
  _QWORD *v29; // r15
  __int64 v30; // rax
  const unsigned __int16 *v31; // r8
  const unsigned __int16 *v32; // rax
  __int64 v33; // rax
  const unsigned __int16 *v34; // r8
  const unsigned __int16 *v35; // r9
  const unsigned __int16 *v36; // r8
  const unsigned __int16 *v37; // r9
  const unsigned __int16 *v38; // r8
  const unsigned __int16 *v39; // r9
  const unsigned __int16 *v40; // r8
  const unsigned __int16 *v41; // r9
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  bool v43; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v44; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v45; // [rsp+68h] [rbp-98h] BYREF
  int v46; // [rsp+6Ch] [rbp-94h] BYREF
  int v47; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h] BYREF
  __int64 v49; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v50; // [rsp+88h] [rbp-78h] BYREF
  int v51; // [rsp+8Ch] [rbp-74h] BYREF
  __int64 v52; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v53; // [rsp+98h] [rbp-68h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v55; // [rsp+A8h] [rbp-58h]
  __int64 v56; // [rsp+B0h] [rbp-50h]
  __int64 v57; // [rsp+B8h] [rbp-48h]
  __int64 v58; // [rsp+C0h] [rbp-40h]
  int v59; // [rsp+C8h] [rbp-38h] BYREF
  int TokenInformation; // [rsp+CCh] [rbp-34h] BYREF
  __int64 v61; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE TokenHandle; // [rsp+D8h] [rbp-28h] BYREF
  DWORD v63; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v64[2]; // [rsp+E8h] [rbp-18h] BYREF
  const unsigned __int16 *v65; // [rsp+F0h] [rbp-10h]
  __int64 v66; // [rsp+F8h] [rbp-8h]
  int v67; // [rsp+100h] [rbp+0h] BYREF
  int v68; // [rsp+104h] [rbp+4h]
  const unsigned __int16 *v69; // [rsp+108h] [rbp+8h]
  unsigned int v70; // [rsp+118h] [rbp+18h]
  __int64 v71; // [rsp+178h] [rbp+78h]
  int v72; // [rsp+180h] [rbp+80h]
  unsigned __int16 v73[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v74[16]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v75[264]; // [rsp+1F0h] [rbp+F0h] BYREF

  v7 = 0;
  v8 = a4;
  v52 = a1;
  if ( !a4 )
    v8 = a3;
  v61 = a2;
  if ( a5 )
  {
    switch ( a5 )
    {
      case 1u:
        v12 = L"patch";
        break;
      case 2u:
        v12 = L"transform";
        break;
      case 3u:
        v12 = L"object";
        break;
      default:
        v10 = 1;
        v11 = 1008;
LABEL_185:
        DebugString(21, 1u, v11, v8, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        return v10;
    }
  }
  else
  {
    v12 = L"package";
  }
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"SOFTWARE RESTRICTION POLICY: Verifying %s --> '%s' against software restriction policy",
      v12,
      v8,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  v43 = 0;
  v43 = IsURL(v8, &v43);
  v13 = v8;
  v59 = 0;
  if ( v43 )
    v13 = a3;
  v64[1] = 6;
  v65 = v13;
  v66 = 0;
  v10 = 1;
  v64[0] = 1;
  if ( (int)((__int64 (__fastcall *)(_DWORD *, int *, _QWORD))WLDP::WldpGetLockdownPolicy)(v64, &v59, 0) < 0
    || (v59 & 0x8000001C) == 0x80000004 )
  {
    v11 = 1044;
    goto LABEL_185;
  }
  v14 = v61;
  if ( !v61 )
  {
    LOBYTE(ReturnLength) = 0;
    v49 = OpenAndValidateMsiStorageRec(a3, a5, v52, &v61, ReturnLength, 0, 0);
    if ( v49 )
    {
      CComPointer<IMsiDatabase>::operator=(&v49, 0);
      DebugString(21, 1u, 1008, v8, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v49);
      return v10;
    }
    v7 = 1;
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v49);
    v14 = v61;
  }
  v54 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, __int64 *))(*(_QWORD *)v14 + 56LL))(
          v14,
          qword_18028EA18,
          0,
          &v54);
  v49 = v15;
  if ( v54 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  v54 = 0;
  if ( v7 )
  {
    v16 = 0;
    if ( v61 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      v61 = 0;
    }
  }
  else
  {
    v16 = 0;
  }
  if ( v15 )
  {
    if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 56LL))(v15, 1) != 2262 )
    {
      CComPointer<IMsiDatabase>::operator=(&v49, 0);
      DebugString(21, 1u, 1008, v8, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
LABEL_34:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v49);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v54);
      return v10;
    }
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SOFTWARE RESTRICTION POLICY: %s is not digitally signed",
        v8,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    CComPointer<IMsiDatabase>::operator=(&v49, 0);
    v15 = v49;
  }
  else
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SOFTWARE RESTRICTION POLICY: %s has a digital signature",
        v8,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    v16 = 1;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoIdentityGenerationHook>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoIdentityGenerationHook>::GetImpl'::`2'::impl) )
  {
    if ( !g_pAppIdHelper )
    {
      v18 = (AppIdHelper *)operator new(0x88u);
      if ( v18 )
        v18 = AppIdHelper::AppIdHelper(v18);
      g_pAppIdHelper = v18;
    }
    AppIdHelper::ResetPackageData(v17);
    *(_BYTE *)g_pAppIdHelper = v16;
  }
  memset_0(&v67, 0, 0xB0u);
  v67 = 176;
  v19 = 4 * (a6 ^ 1) + 1;
  v68 = v19;
  if ( v16 && !a6 )
  {
    v19 |= 8u;
    v71 = -1;
    v68 = v19;
    v72 = 2;
  }
  v69 = v8;
  if ( v43 )
  {
    v50 = 4;
    v68 = v19 | 0x10;
    v52 = 0;
    if ( (int)((__int64 (__fastcall *)(GUID *, _QWORD, __int64, GUID *, __int64 *))OLE32::CoCreateInstance)(
                &CLSID_InternetSecurityManager,
                0,
                1,
                &IID_IInternetSecurityManager,
                &v52) >= 0
      && v52 )
    {
      if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)v52 + 40LL))(
             v52,
             v8,
             &v50,
             0) >= 0 )
      {
        if ( v50 )
        {
          switch ( v50 )
          {
            case 1u:
              if ( g_dmDiagnosticMode )
                DebugString(
                  9,
                  0,
                  0,
                  L"SOFTWARE RESTRICTION POLICY: %s is a URL that maps to URL security zone %d (%s)",
                  v8,
                  (const unsigned __int16 *)1,
                  L"URLZONE_INTRANET",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
              break;
            case 2u:
              if ( g_dmDiagnosticMode )
                DebugString(
                  9,
                  0,
                  0,
                  L"SOFTWARE RESTRICTION POLICY: %s is a URL that maps to URL security zone %d (%s)",
                  v8,
                  (const unsigned __int16 *)2,
                  L"URLZONE_TRUSTED",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
              break;
            case 3u:
              if ( g_dmDiagnosticMode )
                DebugString(
                  9,
                  0,
                  0,
                  L"SOFTWARE RESTRICTION POLICY: %s is a URL that maps to URL security zone %d (%s)",
                  v8,
                  (const unsigned __int16 *)3,
                  L"URLZONE_INTERNET",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
              break;
            case 4u:
              if ( g_dmDiagnosticMode )
                DebugString(
                  9,
                  0,
                  0,
                  L"SOFTWARE RESTRICTION POLICY: %s is a URL that maps to URL security zone %d (%s)",
                  v8,
                  (const unsigned __int16 *)4,
                  L"URLZONE_UNTRUSTED",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
              break;
            default:
              if ( g_dmDiagnosticMode )
                DebugString(
                  9,
                  0,
                  0,
                  L"SOFTWARE RESTRICTION POLICY: %s is a URL that maps to URL security zone %d (%s)",
                  v8,
                  (const unsigned __int16 *)v50,
                  L"unknown / user-defined",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
              break;
          }
        }
        else if ( g_dmDiagnosticMode )
        {
          DebugString(
            9,
            0,
            0,
            L"SOFTWARE RESTRICTION POLICY: %s is a URL that maps to URL security zone %d (%s)",
            v8,
            0,
            L"URLZONE_LOCAL_MACHINE",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    v68 &= ~1u;
    v70 = v50;
    v69 = a3;
  }
  v48 = 0;
  CImpersonate::CImpersonate((CImpersonate *)&v52, 1);
  if ( !IsPrimaryTokenSystemOrService() )
  {
    TokenInformation = 0;
    v63 = 0;
    TokenHandle = 0;
    if ( !OpenUserToken(&TokenHandle, v20) && TokenHandle )
    {
      if ( !GetTokenInformation(TokenHandle, TokenSandBoxInert, &TokenInformation, 4u, &v63) )
      {
        LastError = GetLastError();
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"GetTokenInformation failed with error %d",
            (const unsigned __int16 *)LastError,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
      }
      CloseHandle(TokenHandle);
      TokenHandle = 0;
      if ( TokenInformation == 1 )
      {
        if ( a7
          && !(unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD *, _QWORD))ADVAPI32::SaferCreateLevel)(
                              1,
                              0x40000,
                              1,
                              a7,
                              0) )
        {
LABEL_73:
          if ( g_dmDiagnosticMode )
          {
            v21 = GetLastError();
            v22 = L"SAFER: Unable to create a fully trusted authorization level.  GetLastError returned %d";
LABEL_98:
            DebugString(
              9,
              0,
              0,
              v22,
              (const unsigned __int16 *)v21,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
            goto LABEL_99;
          }
          goto LABEL_99;
        }
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SOFTWARE RESTRICTION POLICY: %s is permitted to run because the user token authorizes execution (marked SANDBOX_INERT).",
            v8,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
LABEL_106:
        v10 = 0;
        goto LABEL_116;
      }
    }
    if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))ADVAPI32::SaferiChangeRegistryScope)(0, 0) )
    {
      if ( g_dmDiagnosticMode )
      {
        v25 = GetLastError();
        DebugString(
          9,
          0,
          0,
          L"SOFTWARE RESTRICTION POLICY: Unable to reload software restriction policy. %s is not considered to be trusted."
           " GetLastError = %d",
          v8,
          (const unsigned __int16 *)v25,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      goto LABEL_99;
    }
    if ( !(unsigned int)((__int64 (__fastcall *)(__int64, int *, __int64 *, const WCHAR *))ADVAPI32::SaferIdentifyLevel)(
                          1,
                          &v67,
                          &v48,
                          L"MSI") )
    {
      if ( g_dmDiagnosticMode )
      {
        v21 = GetLastError();
        v22 = L"SOFTWARE RESTRICTION POLICY: SaferIdentifyLevel reported failure.  Assuming untrusted. . . (GetLastError returned %d)";
        goto LABEL_98;
      }
LABEL_99:
      DebugString(21, 1u, 1008, v8, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
LABEL_116:
      CImpersonate::~CImpersonate((CImpersonate *)&v52);
      goto LABEL_34;
    }
    v44 = 0;
    v51 = 0;
    ((void (__fastcall *)(__int64, __int64, unsigned int *, __int64, int *))ADVAPI32::SaferGetLevelInformation)(
      v48,
      1,
      &v44,
      4,
      &v51);
    if ( v44 == 0x40000 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"SOFTWARE RESTRICTION POLICY: %s is permitted to run at the 'unrestricted' authorization level.",
          v8,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      if ( a7 )
        *a7 = v48;
      else
        ((void (__fastcall *)(__int64))ADVAPI32::SaferCloseLevel)(v48);
      goto LABEL_106;
    }
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SOFTWARE RESTRICTION POLICY: %s is not permitted to run at the 'unrestricted' authorization level.",
        v8,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    v47 = 0;
    v46 = 0;
    v53 = 0;
    memset_0(v75, 0, 0x208u);
    v26 = operator new(0x20u);
    v27 = v26;
    if ( !v26 )
    {
LABEL_113:
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"SOFTWARE RESTRICTION POLICY: Memory allocation failed.",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      ((void (__fastcall *)(__int64))ADVAPI32::SaferCloseLevel)(v48);
      goto LABEL_116;
    }
    v45 = 32;
    *(_OWORD *)v26 = 0;
    *((_OWORD *)v26 + 1) = 0;
    v26[1] = v45;
    ((void (__fastcall *)(__int64, __int64, int *, __int64, int *))ADVAPI32::SaferGetLevelInformation)(
      v48,
      5,
      &v47,
      4,
      &v51);
    ((void (__fastcall *)(__int64, __int64, int *, __int64, int *))ADVAPI32::SaferGetLevelInformation)(
      v48,
      2,
      &v46,
      4,
      &v51);
    ((void (__fastcall *)(__int64, __int64, unsigned int *, __int64, int *))ADVAPI32::SaferGetLevelInformation)(
      v48,
      16,
      &v53,
      4,
      &v51);
    if ( !(unsigned int)((__int64 (__fastcall *)(__int64, __int64, _DWORD *, _QWORD, unsigned int *))ADVAPI32::SaferGetLevelInformation)(
                          v48,
                          15,
                          v27,
                          v45,
                          &v45) )
    {
      if ( GetLastError() != 122 )
        goto LABEL_181;
      operator delete(v27);
      v28 = operator new(v45);
      v27 = v28;
      if ( !v28 )
        goto LABEL_113;
      memset_0(v28, 0, v45);
      v27[1] = v45;
      if ( !(unsigned int)((__int64 (__fastcall *)(__int64, __int64, _DWORD *, _QWORD, unsigned int *))ADVAPI32::SaferGetLevelInformation)(
                            v48,
                            15,
                            v27,
                            v45,
                            &v45) )
      {
LABEL_181:
        operator delete(v27);
        ((void (__fastcall *)(__int64))ADVAPI32::SaferCloseLevel)(v48);
        memset(v74, 0, 30);
        memset(v73, 0, 30);
        if ( (int)StringCchPrintfW(v74, 0xFu, L"0x%x", v44) >= 0 && (int)StringCchPrintfW(v73, 0xFu, L"0x%x", v53) >= 0 )
          DebugString(21, 1u, 1007, v8, v74, v73, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        goto LABEL_116;
      }
    }
    v29 = v27 + 2;
    v57 = 0x4595AF71C59E7B5ALL;
    v58 = 0x790E891B446DBB8LL;
    v55 = 0x4F86D28211015445LL;
    v56 = 0x233595F489EA296LL;
    ((void (__fastcall *)(_DWORD *, unsigned __int16 *, __int64))OLE32::StringFromGUID2)(v27 + 2, v75, 260);
    v30 = *((_QWORD *)v27 + 1) - v55;
    if ( *((_QWORD *)v27 + 1) == v55 )
      v30 = *((_QWORD *)v27 + 2) - v56;
    if ( !v30 )
    {
      if ( g_dmDiagnosticMode )
      {
        v31 = L"machine";
        v32 = L"Configured";
        if ( v46 != 1 )
          v31 = L"user";
        if ( v47 )
          v32 = L"Default";
        DebugString(
          9,
          0,
          0,
          L"SOFTWARE RESTRICTION POLICY: The %s software restriction %s policy default security level disallows execution."
           " The returned execution level was %d",
          v32,
          v31,
          (const unsigned __int16 *)v44,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      goto LABEL_181;
    }
    v33 = *v29 - v57;
    if ( *v29 == v57 )
      v33 = *((_QWORD *)v27 + 2) - v58;
    if ( v33 )
    {
      if ( *v27 == 1 )
      {
        if ( v27[1] >= 0x230u && g_dmDiagnosticMode )
        {
          v40 = L"machine";
          v41 = L"configured";
          if ( v46 != 1 )
            v40 = L"user";
          if ( v47 )
            v41 = L"default";
          DebugString(
            9,
            0,
            0,
            L"SOFTWARE RESTRICTION POLICY: The path rule '%s' with image name '%s' in the %s software restriction %s polic"
             "y disallows execution. The returned execution level was %d",
            v75,
            *((const unsigned __int16 **)v27 + 68),
            v41,
            v40,
            (const unsigned __int16 *)v44,
            L"(NULL)",
            0,
            0);
        }
      }
      else if ( *v27 == 2 )
      {
        if ( v27[1] == 1216 && g_dmDiagnosticMode )
        {
          v38 = L"machine";
          v39 = L"configured";
          if ( v46 != 1 )
            v38 = L"user";
          if ( v47 )
            v39 = L"default";
          DebugString(
            9,
            0,
            0,
            L"SOFTWARE RESTRICTION POLICY: The hash rule '%s' in the %s software restriction %s policy disallows execution"
             ". The returned execution level was %d",
            v75,
            v39,
            v38,
            (const unsigned __int16 *)v44,
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
      }
      else if ( *v27 == 3 && v27[1] == 40 && g_dmDiagnosticMode )
      {
        v36 = L"machine";
        v37 = L"configured";
        if ( v46 != 1 )
          v36 = L"user";
        if ( v47 )
          v37 = L"default";
        DebugString(
          9,
          0,
          0,
          L"SOFTWARE RESTRICTION POLICY: A UrlZone rule for zone '%d' in the %s software restriction %s policy disallows e"
           "xecution. The returned execution level was %d",
          (const unsigned __int16 *)(unsigned int)v27[8],
          v37,
          v36,
          (const unsigned __int16 *)v44,
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      goto LABEL_181;
    }
    if ( v53 > 0x800B0003 )
    {
      if ( v53 != -2146762496 )
      {
        if ( v53 == -2146762495 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"SOFTWARE RESTRICTION POLICY: %s was disallowed because a required certificate in its digital signature has"
               " expired (status = 0x%X). The returned execution level was %d",
              v8,
              (const unsigned __int16 *)0x800B0101LL,
              (const unsigned __int16 *)v44,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          goto LABEL_181;
        }
        if ( v53 != -2146762488 )
        {
          if ( v53 == -2146762484 )
          {
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                L"SOFTWARE RESTRICTION POLICY: %s was disallowed because a required certificate in its digital signature h"
                 "as been revoked by its issuer (status = 0x%X). The returned execution level was %d",
                v8,
                (const unsigned __int16 *)v53,
                (const unsigned __int16 *)v44,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            goto LABEL_181;
          }
          goto LABEL_145;
        }
LABEL_153:
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SOFTWARE RESTRICTION POLICY: %s was disallowed because its digital signature is invalid (status = 0x%X). The"
             " returned execution level was %d",
            v8,
            (const unsigned __int16 *)v53,
            (const unsigned __int16 *)v44,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        goto LABEL_181;
      }
    }
    else if ( v53 != -2146762749 )
    {
      if ( v53 != -2146869246 && v53 != -2146869245 && v53 != -2146869244 )
      {
        if ( v53 == -2146869232 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"SOFTWARE RESTRICTION POLICY: %s was disallowed because its current contents do not match its digital signa"
               "ture (status = 0x%X). The returned execution level was %d",
              v8,
              (const unsigned __int16 *)v53,
              (const unsigned __int16 *)v44,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          goto LABEL_181;
        }
        if ( v53 == -2146762751 )
          goto LABEL_137;
LABEL_145:
        if ( g_dmDiagnosticMode )
        {
          v34 = L"machine";
          v35 = L"configured";
          if ( v46 != 1 )
            v34 = L"user";
          if ( v47 )
            v35 = L"default";
          DebugString(
            9,
            0,
            0,
            L"SOFTWARE RESTRICTION POLICY: A publisher (certificate) rule in the %s software restriction %s policy disallo"
             "ws execution of %s (status = 0x%X). The returned execution level was %d",
            v35,
            v34,
            v8,
            (const unsigned __int16 *)v53,
            (const unsigned __int16 *)v44,
            L"(NULL)",
            0,
            0);
        }
        goto LABEL_181;
      }
      goto LABEL_153;
    }
LABEL_137:
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SOFTWARE RESTRICTION POLICY: %s was disallowed because its digital signature is unrecognized (status = 0x%X). Th"
         "e returned execution level was %d",
        v8,
        (const unsigned __int16 *)v53,
        (const unsigned __int16 *)v44,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    goto LABEL_181;
  }
  if ( a7
    && !(unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD *, _QWORD))ADVAPI32::SaferCreateLevel)(
                        1,
                        0x40000,
                        1,
                        a7,
                        0) )
  {
    goto LABEL_73;
  }
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"SOFTWARE RESTRICTION POLICY: %s is permitted to run because the user token authorizes execution (system or service token).",
      v8,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  CImpersonate::~CImpersonate((CImpersonate *)&v52);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v54 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  return 0;
}

```

## disassembly

```asm
0x1800ff6a4  push    rbp
0x1800ff6a6  push    rbx
0x1800ff6a7  push    rsi
0x1800ff6a8  push    rdi
0x1800ff6a9  push    r12
0x1800ff6ab  push    r13
0x1800ff6ad  push    r14
0x1800ff6af  push    r15
0x1800ff6b1  lea     rbp, [rsp-318h]
0x1800ff6b9  sub     rsp, 418h
0x1800ff6c0  mov     rax, cs:__security_cookie
0x1800ff6c7  xor     rax, rsp
0x1800ff6ca  mov     [rbp+350h+var_50], rax
0x1800ff6d1  mov     ebx, [rbp+350h+arg_20]
0x1800ff6d7  xor     r12d, r12d
0x1800ff6da  mov     r15, [rbp+350h+arg_30]
0x1800ff6e1  test    r9, r9
0x1800ff6e4  mov     r14, r9
0x1800ff6e7  mov     [rbp+350h+var_3C0], rcx
0x1800ff6eb  cmovz   r14, r8
0x1800ff6ef  mov     [rbp+350h+var_380], rdx
0x1800ff6f3  mov     r13, r8
0x1800ff6f6  mov     ecx, ebx
0x1800ff6f8  test    ebx, ebx
0x1800ff6fa  jz      short loc_1800FF73D
0x1800ff6fc  sub     ecx, 1
0x1800ff6ff  jz      short loc_1800FF734
0x1800ff701  sub     ecx, 1
0x1800ff704  jz      short loc_1800FF72B
0x1800ff706  cmp     ecx, 1
0x1800ff709  jz      short loc_1800FF722
0x1800ff70b  lea     esi, [r12+1]
0x1800ff710  mov     r8d, 3F0h
0x1800ff716  lea     rdi, aNull; "(NULL)"
0x1800ff71d  jmp     loc_18010089E
0x1800ff722  lea     rax, aObject_0; "object"
0x1800ff729  jmp     short loc_1800FF744
0x1800ff72b  lea     rax, aTransform_0; "transform"
0x1800ff732  jmp     short loc_1800FF744
0x1800ff734  lea     rax, aPatch_7; "patch"
0x1800ff73b  jmp     short loc_1800FF744
0x1800ff73d  lea     rax, aPackage; "package"
0x1800ff744  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x1800ff74b  lea     rdi, aNull; "(NULL)"
0x1800ff752  jz      short loc_1800FF790
0x1800ff754  mov     [rsp+450h+var_3F8], r12; void *
0x1800ff759  lea     r9, aSoftwareRestri_12; "SOFTWARE RESTRICTION POLICY: Verifying "...
0x1800ff760  mov     [rsp+450h+var_400], r12d; unsigned int
0x1800ff765  xor     edx, edx; unsigned __int16
0x1800ff767  mov     [rsp+450h+var_408], rdi; unsigned __int16 *
0x1800ff76c  xor     r8d, r8d; int
0x1800ff76f  mov     [rsp+450h+var_410], rdi; unsigned __int16 *
0x1800ff774  mov     [rsp+450h+var_418], rdi; unsigned __int16 *
0x1800ff779  mov     [rsp+450h+var_420], rdi; unsigned __int16 *
0x1800ff77e  lea     ecx, [rdx+9]; int
0x1800ff781  mov     [rsp+450h+var_428], r14; unsigned __int16 *
0x1800ff786  mov     [rsp+450h+ReturnLength], rax; unsigned __int16 *
0x1800ff78b  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800ff790  lea     rdx, [rsp+450h+var_3F0]; bool *
0x1800ff795  mov     [rsp+450h+var_3F0], r12b
0x1800ff79a  mov     rcx, r14; unsigned __int16 *
0x1800ff79d  call    ?IsURL@@YA_NPEBGAEA_N@Z; IsURL(ushort const *,bool &)
0x1800ff7a2  test    al, al
0x1800ff7a4  mov     [rsp+450h+var_3F0], al
0x1800ff7a8  mov     rcx, r14
0x1800ff7ab  mov     [rbp+350h+var_388], r12d
0x1800ff7af  cmovnz  rcx, r13
0x1800ff7b3  mov     [rbp+350h+var_364], 6
0x1800ff7ba  xor     eax, eax
0x1800ff7bc  mov     [rbp+350h+var_360], rcx
0x1800ff7c0  mov     [rbp+350h+var_358], rax
0x1800ff7c4  lea     rdx, [rbp+350h+var_388]
0x1800ff7c8  mov     rax, cs:?WldpGetLockdownPolicy@WLDP@@3P6AJPEAUWLDP_HOST_INFORMATION@@PEAKK@ZEA; long (*WLDP::WldpGetLockdownPolicy)(WLDP_HOST_INFORMATION *,ulong *,ulong)
0x1800ff7cf  lea     rcx, [rbp+350h+var_368]
0x1800ff7d3  mov     esi, 1
0x1800ff7d8  xor     r8d, r8d
0x1800ff7db  mov     [rbp+350h+var_368], esi
0x1800ff7de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff7e3  test    eax, eax
0x1800ff7e5  js      loc_180100898
0x1800ff7eb  mov     eax, [rbp+350h+var_388]
0x1800ff7ee  and     eax, 8000001Ch
0x1800ff7f3  cmp     eax, 80000004h
0x1800ff7f8  jz      loc_180100898
0x1800ff7fe  mov     rcx, [rbp+350h+var_380]
0x1800ff802  test    rcx, rcx
0x1800ff805  jnz     short loc_1800FF841
0x1800ff807  mov     r8, [rbp+350h+var_3C0]
0x1800ff80b  lea     r9, [rbp+350h+var_380]
0x1800ff80f  mov     [rsp+450h+var_420], r12
0x1800ff814  mov     edx, ebx
0x1800ff816  mov     [rsp+450h+var_428], r12
0x1800ff81b  mov     rcx, r13
0x1800ff81e  mov     byte ptr [rsp+450h+ReturnLength], r12b
0x1800ff823  call    ?OpenAndValidateMsiStorageRec@@YAPEAVIMsiRecord@@PEBGW4stEnum@@AEAVIMsiServices@@AEAPEAVIMsiStorage@@_N0PEAPEAUSAFER_LEVEL_HANDLE__@@@Z; OpenAndValidateMsiStorageRec(ushort const *,stEnum,IMsiServices &,IMsiStorage * &,bool,ushort const *,SAFER_LEVEL_HANDLE__ * *)
0x1800ff828  mov     [rbp+350h+var_3D0], rax
0x1800ff82c  lea     rcx, [rbp+350h+var_3D0]
0x1800ff830  test    rax, rax
0x1800ff833  jnz     short loc_1800FF8AA
0x1800ff835  mov     r12b, sil
0x1800ff838  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800ff83d  mov     rcx, [rbp+350h+var_380]
0x1800ff841  mov     [rbp+350h+var_3B0], 0
0x1800ff849  lea     r9, [rbp+350h+var_3B0]
0x1800ff84d  mov     rax, [rcx]
0x1800ff850  lea     rdx, qword_18028EA18
0x1800ff857  xor     r8d, r8d
0x1800ff85a  mov     rax, [rax+38h]
0x1800ff85e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff863  mov     rcx, [rbp+350h+var_3B0]
0x1800ff867  mov     rbx, rax
0x1800ff86a  mov     [rbp+350h+var_3D0], rax
0x1800ff86e  test    rcx, rcx
0x1800ff871  jz      short loc_1800FF87F
0x1800ff873  mov     rax, [rcx]
0x1800ff876  mov     rax, [rax+10h]
0x1800ff87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff87f  mov     [rbp+350h+var_3B0], 0
0x1800ff887  test    r12b, r12b
0x1800ff88a  jz      short loc_1800FF8FC
0x1800ff88c  mov     rcx, [rbp+350h+var_380]
0x1800ff890  xor     r12d, r12d
0x1800ff893  test    rcx, rcx
0x1800ff896  jz      short loc_1800FF8FF
0x1800ff898  mov     rax, [rcx]
0x1800ff89b  mov     rax, [rax+10h]
0x1800ff89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff8a4  mov     [rbp+350h+var_380], r12
0x1800ff8a8  jmp     short loc_1800FF8FF
0x1800ff8aa  xor     edx, edx
0x1800ff8ac  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800ff8b1  mov     [rsp+450h+var_3F8], r12; void *
0x1800ff8b6  mov     edx, esi; unsigned __int16
0x1800ff8b8  mov     [rsp+450h+var_400], r12d; unsigned int
0x1800ff8bd  mov     r9, r14; unsigned __int16 *
0x1800ff8c0  mov     [rsp+450h+var_408], rdi; unsigned __int16 *
0x1800ff8c5  mov     ecx, 15h; int
0x1800ff8ca  mov     [rsp+450h+var_410], rdi; unsigned __int16 *
0x1800ff8cf  mov     r8d, 3F0h; int
0x1800ff8d5  mov     [rsp+450h+var_418], rdi; unsigned __int16 *
0x1800ff8da  mov     [rsp+450h+var_420], rdi; unsigned __int16 *
0x1800ff8df  mov     [rsp+450h+var_428], rdi; unsigned __int16 *
0x1800ff8e4  mov     [rsp+450h+ReturnLength], rdi; unsigned __int16 *
0x1800ff8e9  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800ff8ee  lea     rcx, [rbp+350h+var_3D0]
0x1800ff8f2  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800ff8f7  jmp     loc_1801008D5
0x1800ff8fc  xor     r12d, r12d
0x1800ff8ff  test    rbx, rbx
0x1800ff902  jz      loc_1800FF9D8
0x1800ff908  mov     rax, [rbx]
0x1800ff90b  mov     edx, esi
0x1800ff90d  mov     rcx, rbx
0x1800ff910  mov     rax, [rax+38h]
0x1800ff914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff919  cmp     eax, 8D6h
0x1800ff91e  jnz     short loc_1800FF979
0x1800ff920  xor     eax, eax
0x1800ff922  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x1800ff928  jz      short loc_1800FF965
0x1800ff92a  mov     [rsp+450h+var_3F8], rax; void *
0x1800ff92f  lea     r9, aSoftwareRestri_5; "SOFTWARE RESTRICTION POLICY: %s is not "...
0x1800ff936  mov     [rsp+450h+var_400], eax; unsigned int
0x1800ff93a  lea     ecx, [rax+9]; int
0x1800ff93d  mov     [rsp+450h+var_408], rdi; unsigned __int16 *
0x1800ff942  xor     edx, edx; unsigned __int16
0x1800ff944  mov     [rsp+450h+var_410], rdi; unsigned __int16 *
0x1800ff949  xor     r8d, r8d; int
0x1800ff94c  mov     [rsp+450h+var_418], rdi; unsigned __int16 *
0x1800ff951  mov     [rsp+450h+var_420], rdi; unsigned __int16 *
0x1800ff956  mov     [rsp+450h+var_428], rdi; unsigned __int16 *
0x1800ff95b  mov     [rsp+450h+ReturnLength], r14; unsigned __int16 *
0x1800ff960  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800ff965  xor     edx, edx
0x1800ff967  lea     rcx, [rbp+350h+var_3D0]
0x1800ff96b  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800ff970  mov     rbx, [rbp+350h+var_3D0]
0x1800ff974  jmp     loc_1800FFA20
0x1800ff979  xor     edx, edx
0x1800ff97b  lea     rcx, [rbp+350h+var_3D0]
0x1800ff97f  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800ff984  mov     [rsp+450h+var_3F8], r12; void *
0x1800ff989  mov     edx, esi; unsigned __int16
0x1800ff98b  mov     [rsp+450h+var_400], r12d; unsigned int
0x1800ff990  mov     r9, r14; unsigned __int16 *
0x1800ff993  mov     [rsp+450h+var_408], rdi; unsigned __int16 *
0x1800ff998  mov     ecx, 15h; int
0x1800ff99d  mov     [rsp+450h+var_410], rdi; unsigned __int16 *
0x1800ff9a2  mov     r8d, 3F0h; int
0x1800ff9a8  mov     [rsp+450h+var_418], rdi; unsigned __int16 *
0x1800ff9ad  mov     [rsp+450h+var_420], rdi; unsigned __int16 *
0x1800ff9b2  mov     [rsp+450h+var_428], rdi; unsigned __int16 *
0x1800ff9b7  mov     [rsp+450h+ReturnLength], rdi; unsigned __int16 *
0x1800ff9bc  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800ff9c1  lea     rcx, [rbp+350h+var_3D0]
0x1800ff9c5  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800ff9ca  lea     rcx, [rbp+350h+var_3B0]
0x1800ff9ce  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800ff9d3  jmp     loc_1801008D5
0x1800ff9d8  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x1800ff9df  jz      short loc_1800FFA1D
0x1800ff9e1  mov     [rsp+450h+var_3F8], r12; void *
0x1800ff9e6  lea     r9, aSoftwareRestri_1; "SOFTWARE RESTRICTION POLICY: %s has a d"...
0x1800ff9ed  mov     [rsp+450h+var_400], r12d; unsigned int
0x1800ff9f2  xor     edx, edx; unsigned __int16
0x1800ff9f4  mov     [rsp+450h+var_408], rdi; unsigned __int16 *
0x1800ff9f9  xor     r8d, r8d; int
0x1800ff9fc  mov     [rsp+450h+var_410], rdi; unsigned __int16 *
0x1800ffa01  mov     [rsp+450h+var_418], rdi; unsigned __int16 *
0x1800ffa06  mov     [rsp+450h+var_420], rdi; unsigned __int16 *
0x1800ffa0b  lea     ecx, [rdx+9]; int
0x1800ffa0e  mov     [rsp+450h+var_428], rdi; unsigned __int16 *
0x1800ffa13  mov     [rsp+450h+ReturnLength], r14; unsigned __int16 *
0x1800ffa18  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800ffa1d  mov     r12b, sil
0x1800ffa20  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoIdentityGenerationHook@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoIdentityGenerationHook@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoIdentityGenerationHook> `wil::Feature<__WilFeatureTraits_Feature_AutoIdentityGenerationHook>::GetImpl(void)'::`2'::impl
0x1800ffa27  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoIdentityGenerationHook@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoIdentityGenerationHook>::__private_IsEnabled(void)
0x1800ffa2c  test    al, al
0x1800ffa2e  jz      short loc_1800FFA67
0x1800ffa30  cmp     cs:?g_pAppIdHelper@@3PEAVAppIdHelper@@EA, 0; AppIdHelper * g_pAppIdHelper
0x1800ffa38  jnz     short loc_1800FFA58
0x1800ffa3a  mov     ecx, 88h; unsigned __int64
0x1800ffa3f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ffa44  test    rax, rax
0x1800ffa47  jz      short loc_1800FFA51
0x1800ffa49  mov     rcx, rax; this
0x1800ffa4c  call    ??0AppIdHelper@@QEAA@XZ; AppIdHelper::AppIdHelper(void)
0x1800ffa51  mov     cs:?g_pAppIdHelper@@3PEAVAppIdHelper@@EA, rax; AppIdHelper * g_pAppIdHelper
0x1800ffa58  call    ?ResetPackageData@AppIdHelper@@QEAAXXZ; AppIdHelper::ResetPackageData(void)
0x1800ffa5d  mov     rax, cs:?g_pAppIdHelper@@3PEAVAppIdHelper@@EA; AppIdHelper * g_pAppIdHelper
0x1800ffa64  mov     [rax], r12b
0x1800ffa67  xor     edx, edx; Val
0x1800ffa69  lea     rcx, [rbp+350h+var_350]; void *
0x1800ffa6d  mov     r8d, 0B0h; Size
0x1800ffa73  call    memset_0
0x1800ffa78  movzx   ecx, [rbp+350h+arg_28]
0x1800ffa7f  mov     eax, ecx
0x1800ffa81  mov     [rbp+350h+var_350], 0B0h
0x1800ffa88  xor     eax, esi
0x1800ffa8a  lea     eax, ds:1[rax*4]
0x1800ffa91  mov     [rbp+350h+var_34C], eax
0x1800ffa94  test    r12b, r12b
0x1800ffa97  jz      short loc_1800FFABA
0x1800ffa99  xor     r12d, r12d
0x1800ffa9c  test    cl, cl
0x1800ffa9e  jnz     short loc_1800FFABD
0x1800ffaa0  or      eax, 8
0x1800ffaa3  mov     [rbp+350h+var_2D8], 0FFFFFFFFFFFFFFFFh
0x1800ffaab  mov     [rbp+350h+var_34C], eax
0x1800ffaae  mov     [rbp+350h+var_2D0], 2
0x1800ffab8  jmp     short loc_1800FFABD
0x1800ffaba  xor     r12d, r12d
0x1800ffabd  mov     [rbp+350h+var_348], r14
0x1800ffac1  cmp     [rsp+450h+var_3F0], r12b
0x1800ffac6  jz      loc_1800FFCFA
0x1800ffacc  or      eax, 10h
0x1800ffacf  mov     [rbp+350h+var_3C8], 4
0x1800ffad6  mov     [rbp+350h+var_34C], eax
0x1800ffad9  lea     r9, IID_IInternetSecurityManager
0x1800ffae0  lea     rax, [rbp+350h+var_3C0]
0x1800ffae4  mov     [rbp+350h+var_3C0], r12
0x1800ffae8  mov     [rsp+450h+ReturnLength], rax
0x1800ffaed  lea     rcx, CLSID_InternetSecurityManager
0x1800ffaf4  mov     rax, cs:?CoCreateInstance@OLE32@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*OLE32::CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x1800ffafb  mov     r8d, esi
0x1800ffafe  xor     edx, edx
0x1800ffb00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffb05  test    eax, eax
0x1800ffb07  js      loc_1800FFCEC
0x1800ffb0d  mov     rcx, [rbp+350h+var_3C0]
0x1800ffb11  test    rcx, rcx
0x1800ffb14  jz      loc_1800FFCEC
0x1800ffb1a  mov     rax, [rcx]
0x1800ffb1d  lea     r8, [rbp+350h+var_3C8]
0x1800ffb21  xor     r9d, r9d
0x1800ffb24  mov     rdx, r14
0x1800ffb27  mov     rax, [rax+28h]
0x1800ffb2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffb30  test    eax, eax
0x1800ffb32  js      loc_1800FFCDC
0x1800ffb38  mov     eax, [rbp+350h+var_3C8]
0x1800ffb3b  test    eax, eax
0x1800ffb3d  jz      loc_1800FFC90
0x1800ffb43  sub     eax, esi
0x1800ffb45  jz      loc_1800FFC5B
0x1800ffb4b  sub     eax, esi
0x1800ffb4d  jz      loc_1800FFC1E
0x1800ffb53  sub     eax, esi
0x1800ffb55  jz      loc_1800FFBDE
0x1800ffb5b  cmp     eax, esi
0x1800ffb5d  jz      short loc_1800FFB9E
0x1800ffb5f  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x1800ffb66  jz      loc_1800FFCDC
0x1800ffb6c  mov     eax, [rbp+350h+var_3C8]
0x1800ffb6f  lea     rcx, aUnknownUserDef; "unknown / user-defined"
0x1800ffb76  mov     [rsp+450h+var_3F8], r12
0x1800ffb7b  mov     [rsp+450h+var_400], r12d
0x1800ffb80  mov     [rsp+450h+var_408], rdi
0x1800ffb85  mov     [rsp+450h+var_410], rdi
0x1800ffb8a  mov     [rsp+450h+var_418], rdi
  ... truncated ...
```
