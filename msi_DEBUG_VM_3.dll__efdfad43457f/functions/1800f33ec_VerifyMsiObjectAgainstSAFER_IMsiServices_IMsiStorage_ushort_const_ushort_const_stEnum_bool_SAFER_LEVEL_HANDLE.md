# VerifyMsiObjectAgainstSAFER(IMsiServices &,IMsiStorage *,ushort const *,ushort const *,stEnum,bool,SAFER_LEVEL_HANDLE__ * *)

- ea: `0x1800f33ec`
- end: `0x1800f4618`
- name: `?VerifyMsiObjectAgainstSAFER@@YA?AW4iesSaferResult@@AEAVIMsiServices@@PEAVIMsiStorage@@PEBG2W4stEnum@@_NPEAPEAUSAFER_LEVEL_HANDLE__@@@Z`
- size: `4652`
- prototype: `enum iesSaferResult __high(struct IMsiServices *, struct IMsiStorage *, const unsigned __int16 *, const unsigned __int16 *, enum stEnum, bool, struct SAFER_LEVEL_HANDLE__ **)`
- caller_count: `5`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180039ec8`
- `0x1801247d8`
- `0x18013331c`
- `0x18013ae34`
- `0x180140708`

## callees

- `0x180022120`
- `0x180025a18`
- `0x18002684c`
- `0x180061334`
- `0x1800620e4`
- `0x180064b4c`
- `0x180064f18`
- `0x180066074`
- `0x180076e28`
- `0x1800b7800`
- `0x1800f33ec`
- `0x1800f4620`
- `0x180138d98`
- `0x180140708`
- `0x1801cc6ac`
- `0x180252354`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x1800f3b65`
- `ADVAPI32!GetTokenInformation` at `0x1800f3b65`
- `KERNEL32!CloseHandle` at `0x1800f3bc0`
- `KERNEL32!CloseHandle` at `0x1800f3bc0`
- `KERNEL32!GetLastError` at `0x1800f3a94`
- `KERNEL32!GetLastError` at `0x1800f3b6f`
- `KERNEL32!GetLastError` at `0x1800f3c69`
- `KERNEL32!GetLastError` at `0x1800f3cd1`
- `KERNEL32!GetLastError` at `0x1800f3f3e`
- `KERNEL32!GetLastError` at `0x1800f3a94`
- `KERNEL32!GetLastError` at `0x1800f3b6f`
- `KERNEL32!GetLastError` at `0x1800f3c69`
- `KERNEL32!GetLastError` at `0x1800f3cd1`
- `KERNEL32!GetLastError` at `0x1800f3f3e`

## string_xrefs

- `0x1800f3b83`: `GetTokenInformation failed with error %d`
- `0x1800f3a12`: `SOFTWARE RESTRICTION POLICY: %s is a URL that maps to URL security zone %d (%s)`
- `0x1800f3a9a`: `SAFER: Unable to create a fully trusted authorization level.  GetLastError returned %d`
- `0x1800f3ab4`: `SOFTWARE RESTRICTION POLICY: %s is permitted to run because the user token authorizes execution (system or service token).`
- `0x1800f3c0c`: `SOFTWARE RESTRICTION POLICY: %s is permitted to run because the user token authorizes execution (marked SANDBOX_INERT).`
- `0x1800f3c74`: `SOFTWARE RESTRICTION POLICY: Unable to reload software restriction policy. %s is not considered to be trusted. GetLastError = %d`
- `0x1800f40a6`: `Configured`
- `0x1800f40b2`: `SOFTWARE RESTRICTION POLICY: The %s software restriction %s policy default security level disallows execution. The returned execution level was %d`
- `0x1800f4230`: `configured`
- `0x1800f4393`: `configured`
- `0x1800f4412`: `configured`
- `0x1800f4485`: `configured`
- `0x1800f44c0`: `SOFTWARE RESTRICTION POLICY: The path rule '%s' with image name '%s' in the %s software restriction %s policy disallows execution. The returned execution level was %d`

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
          qword_180284610,
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
0x1800f33ec  push    rbp
0x1800f33ee  push    rbx
0x1800f33ef  push    rsi
0x1800f33f0  push    rdi
0x1800f33f1  push    r12
0x1800f33f3  push    r13
0x1800f33f5  push    r14
0x1800f33f7  push    r15
0x1800f33f9  lea     rbp, [rsp-318h]
0x1800f3401  sub     rsp, 418h
0x1800f3408  mov     rax, cs:__security_cookie
0x1800f340f  xor     rax, rsp
0x1800f3412  mov     [rbp+350h+var_50], rax
0x1800f3419  mov     ebx, [rbp+350h+arg_20]
0x1800f341f  xor     r12d, r12d
0x1800f3422  mov     r15, [rbp+350h+arg_30]
0x1800f3429  test    r9, r9
0x1800f342c  mov     r14, r9
0x1800f342f  mov     [rbp+350h+var_3C0], rcx
0x1800f3433  cmovz   r14, r8
0x1800f3437  mov     [rbp+350h+var_380], rdx
0x1800f343b  mov     r13, r8
0x1800f343e  mov     ecx, ebx
0x1800f3440  test    ebx, ebx
0x1800f3442  jz      short loc_1800F3485
0x1800f3444  sub     ecx, 1
0x1800f3447  jz      short loc_1800F347C
0x1800f3449  sub     ecx, 1
0x1800f344c  jz      short loc_1800F3473
0x1800f344e  cmp     ecx, 1
0x1800f3451  jz      short loc_1800F346A
0x1800f3453  lea     esi, [r12+1]
0x1800f3458  mov     r8d, 3F0h
0x1800f345e  lea     rdi, aNull; "(NULL)"
0x1800f3465  jmp     loc_1800F45BC
0x1800f346a  lea     rax, aObject_0; "object"
0x1800f3471  jmp     short loc_1800F348C
0x1800f3473  lea     rax, aTransform_0; "transform"
0x1800f347a  jmp     short loc_1800F348C
0x1800f347c  lea     rax, aPatch_7; "patch"
0x1800f3483  jmp     short loc_1800F348C
0x1800f3485  lea     rax, aPackage; "package"
0x1800f348c  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x1800f3493  lea     rdi, aNull; "(NULL)"
0x1800f349a  jz      short loc_1800F34D8
0x1800f349c  mov     [rsp+450h+var_3F8], r12; void *
0x1800f34a1  lea     r9, aSoftwareRestri_12; "SOFTWARE RESTRICTION POLICY: Verifying "...
0x1800f34a8  mov     [rsp+450h+var_400], r12d; unsigned int
0x1800f34ad  xor     edx, edx; unsigned __int16
0x1800f34af  mov     [rsp+450h+var_408], rdi; unsigned __int16 *
0x1800f34b4  xor     r8d, r8d; int
0x1800f34b7  mov     [rsp+450h+var_410], rdi; unsigned __int16 *
0x1800f34bc  mov     [rsp+450h+var_418], rdi; unsigned __int16 *
0x1800f34c1  mov     [rsp+450h+var_420], rdi; unsigned __int16 *
0x1800f34c6  lea     ecx, [rdx+9]; int
0x1800f34c9  mov     [rsp+450h+var_428], r14; unsigned __int16 *
0x1800f34ce  mov     [rsp+450h+ReturnLength], rax; unsigned __int16 *
0x1800f34d3  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800f34d8  lea     rdx, [rsp+450h+var_3F0]; bool *
0x1800f34dd  mov     [rsp+450h+var_3F0], r12b
0x1800f34e2  mov     rcx, r14; unsigned __int16 *
0x1800f34e5  call    ?IsURL@@YA_NPEBGAEA_N@Z; IsURL(ushort const *,bool &)
0x1800f34ea  test    al, al
0x1800f34ec  mov     [rsp+450h+var_3F0], al
0x1800f34f0  mov     rcx, r14
0x1800f34f3  mov     [rbp+350h+var_388], r12d
0x1800f34f7  cmovnz  rcx, r13
0x1800f34fb  mov     [rbp+350h+var_364], 6
0x1800f3502  xor     eax, eax
0x1800f3504  mov     [rbp+350h+var_360], rcx
0x1800f3508  mov     [rbp+350h+var_358], rax
0x1800f350c  lea     rdx, [rbp+350h+var_388]
0x1800f3510  mov     rax, cs:?WldpGetLockdownPolicy@WLDP@@3P6AJPEAUWLDP_HOST_INFORMATION@@PEAKK@ZEA; long (*WLDP::WldpGetLockdownPolicy)(WLDP_HOST_INFORMATION *,ulong *,ulong)
0x1800f3517  lea     rcx, [rbp+350h+var_368]
0x1800f351b  mov     esi, 1
0x1800f3520  xor     r8d, r8d
0x1800f3523  mov     [rbp+350h+var_368], esi
0x1800f3526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f352b  test    eax, eax
0x1800f352d  js      loc_1800F45B6
0x1800f3533  mov     eax, [rbp+350h+var_388]
0x1800f3536  and     eax, 8000001Ch
0x1800f353b  cmp     eax, 80000004h
0x1800f3540  jz      loc_1800F45B6
0x1800f3546  mov     rcx, [rbp+350h+var_380]
0x1800f354a  test    rcx, rcx
0x1800f354d  jnz     short loc_1800F3589
0x1800f354f  mov     r8, [rbp+350h+var_3C0]
0x1800f3553  lea     r9, [rbp+350h+var_380]
0x1800f3557  mov     [rsp+450h+var_420], r12
0x1800f355c  mov     edx, ebx
0x1800f355e  mov     [rsp+450h+var_428], r12
0x1800f3563  mov     rcx, r13
0x1800f3566  mov     byte ptr [rsp+450h+ReturnLength], r12b
0x1800f356b  call    ?OpenAndValidateMsiStorageRec@@YAPEAVIMsiRecord@@PEBGW4stEnum@@AEAVIMsiServices@@AEAPEAVIMsiStorage@@_N0PEAPEAUSAFER_LEVEL_HANDLE__@@@Z; OpenAndValidateMsiStorageRec(ushort const *,stEnum,IMsiServices &,IMsiStorage * &,bool,ushort const *,SAFER_LEVEL_HANDLE__ * *)
0x1800f3570  mov     [rbp+350h+var_3D0], rax
0x1800f3574  lea     rcx, [rbp+350h+var_3D0]
0x1800f3578  test    rax, rax
0x1800f357b  jnz     short loc_1800F35F2
0x1800f357d  mov     r12b, sil
0x1800f3580  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800f3585  mov     rcx, [rbp+350h+var_380]
0x1800f3589  mov     [rbp+350h+var_3B0], 0
0x1800f3591  lea     r9, [rbp+350h+var_3B0]
0x1800f3595  mov     rax, [rcx]
0x1800f3598  lea     rdx, qword_180284610
0x1800f359f  xor     r8d, r8d
0x1800f35a2  mov     rax, [rax+38h]
0x1800f35a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f35ab  mov     rcx, [rbp+350h+var_3B0]
0x1800f35af  mov     rbx, rax
0x1800f35b2  mov     [rbp+350h+var_3D0], rax
0x1800f35b6  test    rcx, rcx
0x1800f35b9  jz      short loc_1800F35C7
0x1800f35bb  mov     rax, [rcx]
0x1800f35be  mov     rax, [rax+10h]
0x1800f35c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f35c7  mov     [rbp+350h+var_3B0], 0
0x1800f35cf  test    r12b, r12b
0x1800f35d2  jz      short loc_1800F3644
0x1800f35d4  mov     rcx, [rbp+350h+var_380]
0x1800f35d8  xor     r12d, r12d
0x1800f35db  test    rcx, rcx
0x1800f35de  jz      short loc_1800F3647
0x1800f35e0  mov     rax, [rcx]
0x1800f35e3  mov     rax, [rax+10h]
0x1800f35e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f35ec  mov     [rbp+350h+var_380], r12
0x1800f35f0  jmp     short loc_1800F3647
0x1800f35f2  xor     edx, edx
0x1800f35f4  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800f35f9  mov     [rsp+450h+var_3F8], r12; void *
0x1800f35fe  mov     edx, esi; unsigned __int16
0x1800f3600  mov     [rsp+450h+var_400], r12d; unsigned int
0x1800f3605  mov     r9, r14; unsigned __int16 *
0x1800f3608  mov     [rsp+450h+var_408], rdi; unsigned __int16 *
0x1800f360d  mov     ecx, 15h; int
0x1800f3612  mov     [rsp+450h+var_410], rdi; unsigned __int16 *
0x1800f3617  mov     r8d, 3F0h; int
0x1800f361d  mov     [rsp+450h+var_418], rdi; unsigned __int16 *
0x1800f3622  mov     [rsp+450h+var_420], rdi; unsigned __int16 *
0x1800f3627  mov     [rsp+450h+var_428], rdi; unsigned __int16 *
0x1800f362c  mov     [rsp+450h+ReturnLength], rdi; unsigned __int16 *
0x1800f3631  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800f3636  lea     rcx, [rbp+350h+var_3D0]
0x1800f363a  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800f363f  jmp     loc_1800F45F3
0x1800f3644  xor     r12d, r12d
0x1800f3647  test    rbx, rbx
0x1800f364a  jz      loc_1800F3720
0x1800f3650  mov     rax, [rbx]
0x1800f3653  mov     edx, esi
0x1800f3655  mov     rcx, rbx
0x1800f3658  mov     rax, [rax+38h]
0x1800f365c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3661  cmp     eax, 8D6h
0x1800f3666  jnz     short loc_1800F36C1
0x1800f3668  xor     eax, eax
0x1800f366a  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x1800f3670  jz      short loc_1800F36AD
0x1800f3672  mov     [rsp+450h+var_3F8], rax; void *
0x1800f3677  lea     r9, aSoftwareRestri_5; "SOFTWARE RESTRICTION POLICY: %s is not "...
0x1800f367e  mov     [rsp+450h+var_400], eax; unsigned int
0x1800f3682  lea     ecx, [rax+9]; int
0x1800f3685  mov     [rsp+450h+var_408], rdi; unsigned __int16 *
0x1800f368a  xor     edx, edx; unsigned __int16
0x1800f368c  mov     [rsp+450h+var_410], rdi; unsigned __int16 *
0x1800f3691  xor     r8d, r8d; int
0x1800f3694  mov     [rsp+450h+var_418], rdi; unsigned __int16 *
0x1800f3699  mov     [rsp+450h+var_420], rdi; unsigned __int16 *
0x1800f369e  mov     [rsp+450h+var_428], rdi; unsigned __int16 *
0x1800f36a3  mov     [rsp+450h+ReturnLength], r14; unsigned __int16 *
0x1800f36a8  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800f36ad  xor     edx, edx
0x1800f36af  lea     rcx, [rbp+350h+var_3D0]
0x1800f36b3  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800f36b8  mov     rbx, [rbp+350h+var_3D0]
0x1800f36bc  jmp     loc_1800F3768
0x1800f36c1  xor     edx, edx
0x1800f36c3  lea     rcx, [rbp+350h+var_3D0]
0x1800f36c7  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800f36cc  mov     [rsp+450h+var_3F8], r12; void *
0x1800f36d1  mov     edx, esi; unsigned __int16
0x1800f36d3  mov     [rsp+450h+var_400], r12d; unsigned int
0x1800f36d8  mov     r9, r14; unsigned __int16 *
0x1800f36db  mov     [rsp+450h+var_408], rdi; unsigned __int16 *
0x1800f36e0  mov     ecx, 15h; int
0x1800f36e5  mov     [rsp+450h+var_410], rdi; unsigned __int16 *
0x1800f36ea  mov     r8d, 3F0h; int
0x1800f36f0  mov     [rsp+450h+var_418], rdi; unsigned __int16 *
0x1800f36f5  mov     [rsp+450h+var_420], rdi; unsigned __int16 *
0x1800f36fa  mov     [rsp+450h+var_428], rdi; unsigned __int16 *
0x1800f36ff  mov     [rsp+450h+ReturnLength], rdi; unsigned __int16 *
0x1800f3704  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800f3709  lea     rcx, [rbp+350h+var_3D0]
0x1800f370d  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800f3712  lea     rcx, [rbp+350h+var_3B0]
0x1800f3716  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800f371b  jmp     loc_1800F45F3
0x1800f3720  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x1800f3727  jz      short loc_1800F3765
0x1800f3729  mov     [rsp+450h+var_3F8], r12; void *
0x1800f372e  lea     r9, aSoftwareRestri_1; "SOFTWARE RESTRICTION POLICY: %s has a d"...
0x1800f3735  mov     [rsp+450h+var_400], r12d; unsigned int
0x1800f373a  xor     edx, edx; unsigned __int16
0x1800f373c  mov     [rsp+450h+var_408], rdi; unsigned __int16 *
0x1800f3741  xor     r8d, r8d; int
0x1800f3744  mov     [rsp+450h+var_410], rdi; unsigned __int16 *
0x1800f3749  mov     [rsp+450h+var_418], rdi; unsigned __int16 *
0x1800f374e  mov     [rsp+450h+var_420], rdi; unsigned __int16 *
0x1800f3753  lea     ecx, [rdx+9]; int
0x1800f3756  mov     [rsp+450h+var_428], rdi; unsigned __int16 *
0x1800f375b  mov     [rsp+450h+ReturnLength], r14; unsigned __int16 *
0x1800f3760  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800f3765  mov     r12b, sil
0x1800f3768  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoIdentityGenerationHook@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoIdentityGenerationHook@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoIdentityGenerationHook> `wil::Feature<__WilFeatureTraits_Feature_AutoIdentityGenerationHook>::GetImpl(void)'::`2'::impl
0x1800f376f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoIdentityGenerationHook@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoIdentityGenerationHook>::__private_IsEnabled(void)
0x1800f3774  test    al, al
0x1800f3776  jz      short loc_1800F37AF
0x1800f3778  cmp     cs:?g_pAppIdHelper@@3PEAVAppIdHelper@@EA, 0; AppIdHelper * g_pAppIdHelper
0x1800f3780  jnz     short loc_1800F37A0
0x1800f3782  mov     ecx, 88h; unsigned __int64
0x1800f3787  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f378c  test    rax, rax
0x1800f378f  jz      short loc_1800F3799
0x1800f3791  mov     rcx, rax; this
0x1800f3794  call    ??0AppIdHelper@@QEAA@XZ; AppIdHelper::AppIdHelper(void)
0x1800f3799  mov     cs:?g_pAppIdHelper@@3PEAVAppIdHelper@@EA, rax; AppIdHelper * g_pAppIdHelper
0x1800f37a0  call    ?ResetPackageData@AppIdHelper@@QEAAXXZ; AppIdHelper::ResetPackageData(void)
0x1800f37a5  mov     rax, cs:?g_pAppIdHelper@@3PEAVAppIdHelper@@EA; AppIdHelper * g_pAppIdHelper
0x1800f37ac  mov     [rax], r12b
0x1800f37af  xor     edx, edx; Val
0x1800f37b1  lea     rcx, [rbp+350h+var_350]; void *
0x1800f37b5  mov     r8d, 0B0h; Size
0x1800f37bb  call    memset_0
0x1800f37c0  movzx   ecx, [rbp+350h+arg_28]
0x1800f37c7  mov     eax, ecx
0x1800f37c9  mov     [rbp+350h+var_350], 0B0h
0x1800f37d0  xor     eax, esi
0x1800f37d2  lea     eax, ds:1[rax*4]
0x1800f37d9  mov     [rbp+350h+var_34C], eax
0x1800f37dc  test    r12b, r12b
0x1800f37df  jz      short loc_1800F3802
0x1800f37e1  xor     r12d, r12d
0x1800f37e4  test    cl, cl
0x1800f37e6  jnz     short loc_1800F3805
0x1800f37e8  or      eax, 8
0x1800f37eb  mov     [rbp+350h+var_2D8], 0FFFFFFFFFFFFFFFFh
0x1800f37f3  mov     [rbp+350h+var_34C], eax
0x1800f37f6  mov     [rbp+350h+var_2D0], 2
0x1800f3800  jmp     short loc_1800F3805
0x1800f3802  xor     r12d, r12d
0x1800f3805  mov     [rbp+350h+var_348], r14
0x1800f3809  cmp     [rsp+450h+var_3F0], r12b
0x1800f380e  jz      loc_1800F3A42
0x1800f3814  or      eax, 10h
0x1800f3817  mov     [rbp+350h+var_3C8], 4
0x1800f381e  mov     [rbp+350h+var_34C], eax
0x1800f3821  lea     r9, IID_IInternetSecurityManager
0x1800f3828  lea     rax, [rbp+350h+var_3C0]
0x1800f382c  mov     [rbp+350h+var_3C0], r12
0x1800f3830  mov     [rsp+450h+ReturnLength], rax
0x1800f3835  lea     rcx, CLSID_InternetSecurityManager
0x1800f383c  mov     rax, cs:?CoCreateInstance@OLE32@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*OLE32::CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x1800f3843  mov     r8d, esi
0x1800f3846  xor     edx, edx
0x1800f3848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f384d  test    eax, eax
0x1800f384f  js      loc_1800F3A34
0x1800f3855  mov     rcx, [rbp+350h+var_3C0]
0x1800f3859  test    rcx, rcx
0x1800f385c  jz      loc_1800F3A34
0x1800f3862  mov     rax, [rcx]
0x1800f3865  lea     r8, [rbp+350h+var_3C8]
0x1800f3869  xor     r9d, r9d
0x1800f386c  mov     rdx, r14
0x1800f386f  mov     rax, [rax+28h]
0x1800f3873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3878  test    eax, eax
0x1800f387a  js      loc_1800F3A24
0x1800f3880  mov     eax, [rbp+350h+var_3C8]
0x1800f3883  test    eax, eax
0x1800f3885  jz      loc_1800F39D8
0x1800f388b  sub     eax, esi
0x1800f388d  jz      loc_1800F39A3
0x1800f3893  sub     eax, esi
0x1800f3895  jz      loc_1800F3966
0x1800f389b  sub     eax, esi
0x1800f389d  jz      loc_1800F3926
0x1800f38a3  cmp     eax, esi
0x1800f38a5  jz      short loc_1800F38E6
0x1800f38a7  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x1800f38ae  jz      loc_1800F3A24
0x1800f38b4  mov     eax, [rbp+350h+var_3C8]
0x1800f38b7  lea     rcx, aUnknownUserDef; "unknown / user-defined"
0x1800f38be  mov     [rsp+450h+var_3F8], r12
0x1800f38c3  mov     [rsp+450h+var_400], r12d
0x1800f38c8  mov     [rsp+450h+var_408], rdi
0x1800f38cd  mov     [rsp+450h+var_410], rdi
0x1800f38d2  mov     [rsp+450h+var_418], rdi
  ... truncated ...
```
