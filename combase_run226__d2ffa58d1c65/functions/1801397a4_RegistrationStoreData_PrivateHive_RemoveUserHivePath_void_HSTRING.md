# RegistrationStoreData::PrivateHive::RemoveUserHivePath(void *,HSTRING__ *)

- ea: `0x1801397a4`
- end: `0x180139b9e`
- name: `?RemoveUserHivePath@PrivateHive@RegistrationStoreData@@SAJPEAXPEAUHSTRING__@@@Z`
- size: `1018`
- prototype: `__int64 __fastcall(void *userToken, HSTRING packageId)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180139670`

## callees

- `0x180086714`
- `0x180087660`
- `0x18008db2c`
- `0x180090780`
- `0x1800c4250`
- `0x1800d92b8`
- `0x18012281c`
- `0x1801397a4`
- `0x18018b1e0`
- `0x1801999b0`
- `0x18019a654`
- `0x18019c220`
- `0x18019c59c`
- `0x1801a317c`
- `0x1801a3264`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801399d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801399f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801399d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801399f2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180139a91`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180139a91`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x180139867`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x180139867`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x1801398fb`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x1801398fb`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateRootFolderBase` at `0x180139919`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateRootFolderBase` at `0x180139919`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseState` at `0x1801399ea`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseState` at `0x1801399ea`

## string_xrefs

- `0x1801398dd`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x180139b04`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x180139b6a`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x1801398cb`: `RegistrationStoreData::PrivateHive::RemoveUserHivePath`
- `0x180139af2`: `RegistrationStoreData::PrivateHive::RemoveUserHivePath`
- `0x180139b63`: `RegistrationStoreData::PrivateHive::RemoveUserHivePath`

## pseudocode

```c
__int64 __fastcall RegistrationStoreData::PrivateHive::RemoveUserHivePath(void *userToken, HSTRING packageId)
{
  const wchar_t *StringRawBuffer; // rax
  LONG v5; // eax
  HRESULT v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rdi
  const wchar_t *v9; // rax
  signed int LastError; // eax
  unsigned int v11; // edx
  int (__fastcall *v12)(const wchar_t *); // r8
  int (__fastcall *v13)(const wchar_t *, const ActionType, const int, void *); // r9
  signed int v14; // eax
  int v15; // eax
  int v16; // edi
  int v17; // esi
  TraceLevel v18; // ecx
  wchar_t *format; // [rsp+20h] [rbp-E0h]
  __int64 dwFlags; // [rsp+28h] [rbp-D8h]
  bool Succeeded; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int retryCount; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int64 cchRemaining; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *pszEnd[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int cchStateRootPath; // [rsp+50h] [rbp-B0h] BYREF
  UnbiasedTimer timer; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t szPackageFamilyName[72]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t szStateRootPath[264]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t szUserHivePath[264]; // [rsp+310h] [rbp+210h] BYREF

  if ( !IsPackageFullNameFromIdPresent()
    || !IsOpenStateExplicitPresent()
    || !IsOpenStateExplicitPresent()
    || !IsOpenStateExplicitPresent() )
  {
    v6 = -2147023728;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<long>(
        "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
        "RegistrationStoreData::PrivateHive::RemoveUserHivePath",
        270,
        ERRORS,
        L"hr:%!HRESULT!",
        -2147023728);
    return (unsigned int)v6;
  }
  memset_0(szStateRootPath, 0, 0x208u);
  cchStateRootPath = 260;
  memset_0(szUserHivePath, 0, 0x208u);
  memset_0(szPackageFamilyName, 0, 0x82u);
  retryCount = 65;
  StringRawBuffer = WindowsGetStringRawBuffer(packageId, 0);
  v5 = PackageFamilyNameFromFullName(StringRawBuffer, &retryCount, szPackageFamilyName);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
    if ( !gfEnableTracing || !IsWppLevelEnabled(VERBOSE) )
      goto LABEL_15;
  }
  else if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
  {
    return (unsigned int)v6;
  }
  ComTraceHr(
    v6,
    "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
    "RegistrationStoreData::PrivateHive::RemoveUserHivePath",
    287,
    L"hr:%!HRESULT!",
    v6);
  if ( v6 < 0 )
    return (unsigned int)v6;
LABEL_15:
  v7 = OpenStateExplicit(userToken, szPackageFamilyName);
  v8 = v7;
  if ( v7 )
  {
    if ( (unsigned int)GetStateRootFolderBase(v7, szStateRootPath, &cchStateRootPath) )
    {
      pszEnd[0] = 0;
      cchRemaining = 0;
      v6 = StringCchCopyExW(szUserHivePath, 0x104u, szStateRootPath, pszEnd, &cchRemaining, 0);
      if ( v6 >= 0 )
      {
        v6 = StringCchCopyExW(pszEnd[0], cchRemaining, L"\\", pszEnd, &cchRemaining, 0);
        if ( v6 >= 0 )
        {
          v9 = WindowsGetStringRawBuffer(packageId, 0);
          v6 = StringCchCopyExW(pszEnd[0], cchRemaining, v9, pszEnd, &cchRemaining, 0);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseState(v8);
  }
  else
  {
    v14 = GetLastError();
    v6 = v14;
    if ( v14 > 0 )
      v6 = (unsigned __int16)v14 | 0x80070000;
  }
  if ( v6 >= 0 )
  {
    v15 = RemoveDirectoryTree(szUserHivePath, v11, v12, v13, format);
    v6 = v15;
    if ( v15 > 0 )
      v6 = (unsigned __int16)v15 | 0x80070000;
    if ( (unsigned int)(v6 + 2147024894) <= 1 )
      return 0;
    if ( v6 < 0 )
    {
      retryCount = 0;
      timer._dwTimeout = 2000;
      timer._startTime = GetUnbiasedInterruptTimeInMilliseconds();
      v16 = 0;
      timer._isStarted = 1;
      do
      {
        pszEnd[0] = szStateRootPath;
        pszEnd[1] = szUserHivePath;
        v6 = RegistrationStoreData::PrivilegedAction__lambda_4ad815d377d0a4db042d95d3845689d5___((const RegistrationStoreData::PrivateHive::RemoveUserHivePath::__l43::<lambda_4ad815d377d0a4db042d95d3845689d5> *)pszEnd);
        v17 = v16;
        if ( v6 != -2147024864 )
          break;
        retryCount = ++v16;
        Sleep(0x64u);
        v17 = v16;
      }
      while ( UnbiasedTimer::GetRemainingTime(&timer) );
      if ( v17 )
      {
        Succeeded = v6 >= 0;
        ComTelemetry::PrivateHiveSharingViolation<unsigned int &,bool>(&retryCount, &Succeeded);
      }
      if ( v6 >= 0 )
      {
        if ( !gfEnableTracing )
          return (unsigned int)v6;
        v18 = VERBOSE;
      }
      else
      {
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 )
          goto LABEL_40;
        if ( !gfEnableTracing )
          return (unsigned int)v6;
        v18 = ERRORS;
      }
      if ( !IsWppLevelEnabled(v18) )
        return (unsigned int)v6;
LABEL_40:
      LODWORD(dwFlags) = v6;
      ComTraceHr(
        v6,
        "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
        "RegistrationStoreData::PrivateHive::RemoveUserHivePath",
        407,
        L"hr:%!HRESULT!",
        dwFlags);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801397a4  mov     [rsp-8+arg_10], rbx
0x1801397a9  push    rbp
0x1801397aa  push    rsi
0x1801397ab  push    rdi
0x1801397ac  push    r12
0x1801397ae  push    r14
0x1801397b0  lea     rbp, [rsp-430h]
0x1801397b8  sub     rsp, 530h
0x1801397bf  mov     rax, cs:__security_cookie
0x1801397c6  xor     rax, rsp
0x1801397c9  mov     [rbp+450h+var_30], rax
0x1801397d0  mov     rsi, packageId
0x1801397d3  mov     rdi, userToken
0x1801397d6  call    IsPackageFullNameFromIdPresent
0x1801397db  test    al, al
0x1801397dd  jz      loc_180139B28
0x1801397e3  call    IsOpenStateExplicitPresent
0x1801397e8  test    al, al
0x1801397ea  jz      loc_180139B28
0x1801397f0  call    IsOpenStateExplicitPresent
0x1801397f5  test    al, al
0x1801397f7  jz      loc_180139B28
0x1801397fd  call    IsOpenStateExplicitPresent
0x180139802  test    al, al
0x180139804  jz      loc_180139B28
0x18013980a  mov     ebx, 208h
0x18013980f  lea     userToken, [rbp+450h+szStateRootPath]; void *
0x180139813  mov     r8d, ebx; Size
0x180139816  xor     edx, edx; Val
0x180139818  call    memset_0
0x18013981d  mov     r8d, ebx; Size
0x180139820  mov     [rsp+550h+cchStateRootPath], 104h
0x180139828  xor     edx, edx; Val
0x18013982a  lea     userToken, [rbp+450h+szUserHivePath]; void *
0x180139831  call    memset_0
0x180139836  xor     edx, edx; Val
0x180139838  lea     userToken, [rsp+550h+szPackageFamilyName]; void *
0x18013983d  mov     r8d, 82h; Size
0x180139843  call    memset_0
0x180139848  xor     edx, edx; length
0x18013984a  mov     [rsp+550h+retryCount], 41h ; 'A'
0x180139852  mov     userToken, rsi; string
0x180139855  call    WindowsGetStringRawBuffer
0x18013985a  mov     userToken, rax; packageFullName
0x18013985d  lea     r8, [rsp+550h+szPackageFamilyName]; packageFamilyName
0x180139862  lea     packageId, [rsp+550h+retryCount]; packageFamilyNameLength
0x180139867  call    cs:__imp_PackageFamilyNameFromFullName
0x18013986d  mov     ebx, eax
0x18013986f  mov     r12d, 80070000h
0x180139875  test    eax, eax
0x180139877  jle     short loc_18013987F
0x180139879  movzx   ebx, ax
0x18013987c  or      ebx, r12d
0x18013987f  lea     r14, aHrHresult; "hr:%!HRESULT!"
0x180139886  test    ebx, ebx
0x180139888  jns     short loc_1801398B0
0x18013988a  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180139890  test    eax, eax
0x180139892  jnz     short loc_1801398C7
0x180139894  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18013989a  jz      loc_180139B76
0x1801398a0  xor     ecx, ecx; level
0x1801398a2  call    IsWppLevelEnabled
0x1801398a7  test    al, al
0x1801398a9  jnz     short loc_1801398C7
0x1801398ab  jmp     loc_180139B76
0x1801398b0  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1801398b7  jz      short loc_1801398F3
0x1801398b9  mov     ecx, 3; level
0x1801398be  call    IsWppLevelEnabled
0x1801398c3  test    al, al
0x1801398c5  jz      short loc_1801398F3
0x1801398c7  mov     dword ptr [rsp+550h+dwFlags], ebx
0x1801398cb  lea     r8, aRegistrationst_9; "RegistrationStoreData::PrivateHive::Rem"...
0x1801398d2  mov     r9d, 11Fh; line
0x1801398d8  mov     [rsp+550h+format], r14; fnReportReturnValue
0x1801398dd  lea     packageId, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x1801398e4  mov     ecx, ebx; hr
0x1801398e6  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801398eb  test    ebx, ebx
0x1801398ed  js      loc_180139B76
0x1801398f3  lea     packageId, [rsp+550h+szPackageFamilyName]
0x1801398f8  mov     userToken, rdi
0x1801398fb  call    cs:__imp_OpenStateExplicit
0x180139901  mov     rdi, rax
0x180139904  test    rax, rax
0x180139907  jz      loc_1801399F2
0x18013990d  lea     r8, [rsp+550h+cchStateRootPath]
0x180139912  mov     userToken, rax
0x180139915  lea     packageId, [rbp+450h+szStateRootPath]
0x180139919  call    cs:__imp_GetStateRootFolderBase
0x18013991f  test    eax, eax
0x180139921  jz      loc_1801399D5
0x180139927  lea     rax, [rsp+550h+cchRemaining]
0x18013992c  mov     dword ptr [rsp+550h+dwFlags], 0; dwFlags
0x180139934  lea     r9, [rsp+550h+pszEnd]; ppszDestEnd
0x180139939  mov     [rsp+550h+format], rax; pcchRemaining
0x18013993e  lea     r8, [rbp+450h+szStateRootPath]; pszSrc
0x180139942  mov     [rsp+550h+pszEnd], 0
0x18013994b  mov     edx, 104h; cchDest
0x180139950  mov     [rsp+550h+cchRemaining], 0
0x180139959  lea     userToken, [rbp+450h+szUserHivePath]; pszDest
0x180139960  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180139965  mov     ebx, eax
0x180139967  test    eax, eax
0x180139969  js      short loc_1801399E7
0x18013996b  mov     packageId, [rsp+550h+cchRemaining]; cchDest
0x180139970  lea     rax, [rsp+550h+cchRemaining]
0x180139975  mov     userToken, [rsp+550h+pszEnd]; pszDest
0x18013997a  lea     r9, [rsp+550h+pszEnd]; ppszDestEnd
0x18013997f  mov     dword ptr [rsp+550h+dwFlags], 0; dwFlags
0x180139987  lea     r8, asc_1802AFED8; "\\"
0x18013998e  mov     [rsp+550h+format], rax; pcchRemaining
0x180139993  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180139998  mov     ebx, eax
0x18013999a  test    eax, eax
0x18013999c  js      short loc_1801399E7
0x18013999e  xor     edx, edx; length
0x1801399a0  mov     userToken, rsi; string
0x1801399a3  call    WindowsGetStringRawBuffer
0x1801399a8  mov     packageId, [rsp+550h+cchRemaining]; cchDest
0x1801399ad  lea     userToken, [rsp+550h+cchRemaining]
0x1801399b2  mov     dword ptr [rsp+550h+dwFlags], 0; dwFlags
0x1801399ba  lea     r9, [rsp+550h+pszEnd]; ppszDestEnd
0x1801399bf  mov     [rsp+550h+format], userToken; pcchRemaining
0x1801399c4  mov     r8, rax; pszSrc
0x1801399c7  mov     userToken, [rsp+550h+pszEnd]; pszDest
0x1801399cc  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1801399d1  mov     ebx, eax
0x1801399d3  jmp     short loc_1801399E7
0x1801399d5  call    cs:__imp_GetLastError
0x1801399db  mov     ebx, eax
0x1801399dd  test    eax, eax
0x1801399df  jle     short loc_1801399E7
0x1801399e1  movzx   ebx, ax
0x1801399e4  or      ebx, r12d
0x1801399e7  mov     userToken, rdi
0x1801399ea  call    cs:__imp_CloseState
0x1801399f0  jmp     short loc_180139A04
0x1801399f2  call    cs:__imp_GetLastError
0x1801399f8  mov     ebx, eax
0x1801399fa  test    eax, eax
0x1801399fc  jle     short loc_180139A04
0x1801399fe  movzx   ebx, ax
0x180139a01  or      ebx, r12d
0x180139a04  test    ebx, ebx
0x180139a06  js      loc_180139B76
0x180139a0c  lea     userToken, [rbp+450h+szUserHivePath]; path
0x180139a13  call    RemoveDirectoryTree
0x180139a18  mov     ebx, eax
0x180139a1a  test    eax, eax
0x180139a1c  jle     short loc_180139A24
0x180139a1e  movzx   ebx, ax
0x180139a21  or      ebx, r12d
0x180139a24  lea     eax, [rbx+7FF8FFFEh]
0x180139a2a  cmp     eax, 1
0x180139a2d  jbe     loc_180139B24
0x180139a33  test    ebx, ebx
0x180139a35  jns     loc_180139B76
0x180139a3b  mov     [rsp+550h+retryCount], 0
0x180139a43  mov     [rsp+550h+timer._dwTimeout], 7D0h
0x180139a4b  call    ?GetUnbiasedInterruptTimeInMilliseconds@@YA_KXZ; GetUnbiasedInterruptTimeInMilliseconds(void)
0x180139a50  mov     [rsp+550h+timer._startTime], rax
0x180139a55  xor     edi, edi
0x180139a57  mov     [rsp+550h+timer._isStarted], 1
0x180139a5c  lea     rax, [rbp+450h+szStateRootPath]
0x180139a60  mov     [rsp+550h+pszEnd], rax
0x180139a65  lea     userToken, [rsp+550h+pszEnd]; lambda
0x180139a6a  lea     rax, [rbp+450h+szUserHivePath]
0x180139a71  mov     [rsp+550h+var_508], rax
0x180139a76  call    RegistrationStoreData__PrivilegedAction__lambda_4ad815d377d0a4db042d95d3845689d5___
0x180139a7b  mov     ebx, eax
0x180139a7d  mov     esi, edi
0x180139a7f  cmp     eax, 80070020h
0x180139a84  jnz     short loc_180139AA7
0x180139a86  inc     edi
0x180139a88  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180139a8d  mov     [rsp+550h+retryCount], edi
0x180139a91  call    cs:__imp_Sleep
0x180139a97  lea     userToken, [rsp+550h+timer]; this
0x180139a9c  mov     esi, edi
0x180139a9e  call    ?GetRemainingTime@UnbiasedTimer@@QEBAKXZ; UnbiasedTimer::GetRemainingTime(void)
0x180139aa3  test    eax, eax
0x180139aa5  jnz     short loc_180139A5C
0x180139aa7  test    esi, esi
0x180139aa9  jz      short loc_180139AC5
0x180139aab  mov     eax, ebx
0x180139aad  lea     packageId, [rsp+550h+Succeeded]; Succeeded
0x180139ab2  shr     eax, 1Fh
0x180139ab5  lea     userToken, [rsp+550h+retryCount]; Retries
0x180139aba  xor     al, 1
0x180139abc  mov     [rsp+550h+Succeeded], al
0x180139ac0  call    ??$PrivateHiveSharingViolation@AEAI_N@ComTelemetry@@SAXAEAI$$QEA_N@Z; ComTelemetry::PrivateHiveSharingViolation<uint &,bool>(uint &,bool &&)
0x180139ac5  test    ebx, ebx
0x180139ac7  jns     short loc_180139B14
0x180139ac9  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180139acf  test    eax, eax
0x180139ad1  jnz     short loc_180139AEE
0x180139ad3  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180139ad9  jz      loc_180139B76
0x180139adf  xor     ecx, ecx; level
0x180139ae1  call    IsWppLevelEnabled
0x180139ae6  test    al, al
0x180139ae8  jz      loc_180139B76
0x180139aee  mov     dword ptr [rsp+550h+dwFlags], ebx
0x180139af2  lea     r8, aRegistrationst_9; "RegistrationStoreData::PrivateHive::Rem"...
0x180139af9  mov     r9d, 197h; line
0x180139aff  mov     [rsp+550h+format], r14; format
0x180139b04  lea     packageId, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x180139b0b  mov     ecx, ebx; hr
0x180139b0d  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x180139b12  jmp     short loc_180139B76
0x180139b14  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180139b1b  jz      short loc_180139B76
0x180139b1d  mov     ecx, 3
0x180139b22  jmp     short loc_180139AE1
0x180139b24  xor     ebx, ebx
0x180139b26  jmp     short loc_180139B76
0x180139b28  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180139b2e  mov     ebx, 80070490h
0x180139b33  test    eax, eax
0x180139b35  jnz     short loc_180139B4A
0x180139b37  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180139b3d  jz      short loc_180139B76
0x180139b3f  xor     ecx, ecx; level
0x180139b41  call    IsWppLevelEnabled
0x180139b46  test    al, al
0x180139b48  jz      short loc_180139B76
0x180139b4a  lea     r14, aHrHresult; "hr:%!HRESULT!"
0x180139b51  mov     dword ptr [rsp+550h+dwFlags], ebx; <args_0>
0x180139b55  xor     r9d, r9d; level
0x180139b58  mov     [rsp+550h+format], r14; format
0x180139b5d  mov     r8d, 10Eh; line
0x180139b63  lea     packageId, aRegistrationst_9; "RegistrationStoreData::PrivateHive::Rem"...
0x180139b6a  lea     userToken, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x180139b71  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180139b76  mov     eax, ebx
0x180139b78  mov     userToken, [rbp+450h+var_30]
0x180139b7f  xor     userToken, rsp; StackCookie
0x180139b82  call    __security_check_cookie
0x180139b87  mov     rbx, [rsp+550h+arg_10]
0x180139b8f  add     rsp, 530h
0x180139b96  pop     r14
0x180139b98  pop     r12
0x180139b9a  pop     rdi
0x180139b9b  pop     rsi
0x180139b9c  pop     rbp
0x180139b9d  retn
```
