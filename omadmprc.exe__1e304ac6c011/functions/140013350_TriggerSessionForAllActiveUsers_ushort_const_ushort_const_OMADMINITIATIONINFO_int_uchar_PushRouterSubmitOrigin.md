# TriggerSessionForAllActiveUsers(ushort const *,ushort const *,OMADMINITIATIONINFO *,int,uchar,PushRouterSubmitOrigin,long *)

- ea: `0x140013350`
- end: `0x140013ad6`
- name: `?TriggerSessionForAllActiveUsers@@YAJPEBG0PEAUOMADMINITIATIONINFO@@HEW4PushRouterSubmitOrigin@@PEAJ@Z`
- size: `1926`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, struct OMADMINITIATIONINFO *, int, unsigned __int8, enum PushRouterSubmitOrigin, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140011468`

## callees

- `0x140002aa0`
- `0x1400084e4`
- `0x140008504`
- `0x14000b708`
- `0x14000c4ac`
- `0x14000eee0`
- `0x14000f2b8`
- `0x14000fe64`
- `0x140012388`
- `0x1400124a8`
- `0x140013350`
- `0x140014620`
- `0x1400147f0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14001358b`
- `msvcrt!??3@YAXPEAX@Z` at `0x140013904`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400139dc`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001358b`
- `msvcrt!??3@YAXPEAX@Z` at `0x140013904`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400139dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001351d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400136a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400136fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400137d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001351d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400136a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400136fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400137d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400136c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001371d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013782`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400137f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400136c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001371d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013782`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400137f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001391f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013a4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001391f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013a4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400136b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001370f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013742`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013774`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400137e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013824`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013843`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400138d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400138ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400139b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400139c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013a11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400136b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001370f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013742`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013774`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400137e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013824`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013843`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400138d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400138ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400139b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400139c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013a11`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140013509`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140013561`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140013509`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140013561`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400135de`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400135de`
- `omadmapi!__imp_?OmaDmGetNextSessionIDToUse@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAK@Z` at `0x140013643`
- `omadmapi!__imp_?OmaDmGetNextSessionIDToUse@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAK@Z` at `0x140013643`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x140013a66`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x140013a8a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x140013aa9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x140013a66`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x140013a8a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x140013aa9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1400134bd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1400134bd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x140013427`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x140013427`

## string_xrefs

- `0x140013575`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1400135b0`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x14001395c`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall TriggerSessionForAllActiveUsers(
        const WCHAR *a1,
        unsigned __int16 *a2,
        struct OMADMINITIATIONINFO *a3,
        unsigned int a4,
        char a5,
        int a6,
        _DWORD *TokenInformationLength)
{
  unsigned int v7; // r12d
  struct OMADMINITIATIONINFO *v8; // r13
  PSID *v9; // rsi
  int v10; // r15d
  unsigned int LastError; // edi
  __int64 v12; // rdx
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  unsigned int v15; // edi
  unsigned int v16; // ecx
  HLOCAL v17; // rbx
  int v18; // eax
  PSID *v19; // r14
  __int64 v20; // rdi
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  OLECHAR *v24; // r9
  int ChildInitiationInfo; // eax
  LPWSTR *v26; // rax
  unsigned __int64 v27; // r8
  LPWSTR *v28; // rsi
  LPWSTR v29; // r13
  LPWSTR v30; // r12
  DWORD v31; // edi
  LPWSTR *hlocal_string_nothrow; // rax
  unsigned __int64 v33; // r8
  LPWSTR *v34; // r12
  _DWORD **v35; // r13
  DWORD v36; // edi
  WCHAR *v37; // r13
  LPWSTR v38; // r12
  DWORD v39; // edi
  HLOCAL *v40; // rdi
  void **v41; // r12
  _DWORD *v42; // rax
  void *v43; // r13
  DWORD v44; // ebx
  int v45; // ecx
  __int64 v46; // rdx
  COmaDmPrcLogger *Logger; // rax
  unsigned int v48; // edi
  __int64 v49; // rdx
  PSID *v50; // rcx
  int ReturnLength; // [rsp+28h] [rbp-B1h]
  int ReturnLengtha; // [rsp+28h] [rbp-B1h]
  int ReturnLengthb; // [rsp+28h] [rbp-B1h]
  __int64 v55; // [rsp+48h] [rbp-91h] BYREF
  __int64 v56; // [rsp+50h] [rbp-89h] BYREF
  unsigned int v57; // [rsp+58h] [rbp-81h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-79h] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp-71h] BYREF
  unsigned int v60; // [rsp+70h] [rbp-69h] BYREF
  unsigned int v61; // [rsp+74h] [rbp-65h]
  HLOCAL v62; // [rsp+78h] [rbp-61h] BYREF
  HLOCAL v63; // [rsp+80h] [rbp-59h] BYREF
  PSID *v64; // [rsp+88h] [rbp-51h]
  _DWORD *v65; // [rsp+90h] [rbp-49h]
  HLOCAL hMem; // [rsp+98h] [rbp-41h] BYREF
  HLOCAL v67; // [rsp+A0h] [rbp-39h] BYREF
  _QWORD v68[4]; // [rsp+A8h] [rbp-31h] BYREF
  char v69; // [rsp+C8h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+47h]
  LPCWSTR lpSubKey; // [rsp+128h] [rbp+4Fh] BYREF
  unsigned __int16 *v72; // [rsp+130h] [rbp+57h] BYREF
  struct OMADMINITIATIONINFO *v73; // [rsp+138h] [rbp+5Fh]
  unsigned int v74; // [rsp+140h] [rbp+67h]

  v74 = a4;
  v73 = a3;
  v72 = a2;
  lpSubKey = a1;
  v7 = a4;
  v8 = a3;
  v9 = 0;
  v10 = 0;
  v61 = 0;
  v55 = 0;
  *TokenInformationLength = 0;
  v68[0] = &v55;
  v68[1] = &v72;
  v68[2] = &lpSubKey;
  v68[3] = (char *)&v55 + 4;
  v69 = 1;
  if ( (unsigned int)ShouldDisableOnRoaming(a1) )
  {
    LastError = -2102657020;
    v12 = 1382;
LABEL_5:
    LODWORD(v55) = LastError;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
      (const char *)LastError,
      ReturnLength);
    goto LABEL_88;
  }
  if ( (unsigned int)ShouldDisableAsDeletePending(lpSubKey) )
  {
    LastError = -2102657018;
    v12 = 1388;
    goto LABEL_5;
  }
  if ( a5 )
  {
    LastError = -2147418113;
    v12 = 1394;
    goto LABEL_5;
  }
  v56 = 0;
  v13 = UMgrEnumerateSessionUsers((char *)&v55 + 4, &v56);
  LastError = v13;
  LODWORD(v55) = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x577,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
      (const char *)(unsigned int)v13,
      ReturnLength);
    goto LABEL_86;
  }
  if ( !HIDWORD(v55) || !v56 )
  {
    if ( v56 )
      UMgrFreeSessionUsers(v56);
    wil::details::lambda_call__lambda_887815b2c35ab7a699d0f5890dd297cb___::_lambda_call__lambda_887815b2c35ab7a699d0f5890dd297cb___(v68);
    return 1;
  }
  v57 = 1;
  GetTestSettingDword(lpSubKey, v14, &v57);
  v15 = 0;
  v61 = 0;
  v16 = HIDWORD(v55);
  if ( !(HIDWORD(v55) * v57) )
  {
LABEL_89:
    if ( v56 )
      UMgrFreeSessionUsers(v56);
    wil::details::lambda_call__lambda_887815b2c35ab7a699d0f5890dd297cb___::_lambda_call__lambda_887815b2c35ab7a699d0f5890dd297cb___(v68);
    return 0;
  }
  v17 = v63;
  while ( 1 )
  {
    TokenHandle = 0;
    v18 = UMgrQueryUserToken(*(_QWORD *)(v56 + 16LL * (v15 % v16)), &TokenHandle);
    LastError = v18;
    LODWORD(v55) = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x588,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
        (const char *)(unsigned int)v18,
        ReturnLength);
      goto LABEL_84;
    }
    v19 = 0;
    v64 = 0;
    v20 = -6;
    if ( TokenHandle )
      v20 = (__int64)TokenHandle;
    LODWORD(TokenInformationLength) = 0;
    if ( GetTokenInformation((HANDLE)v20, TokenUser, 0, 0, (PDWORD)&TokenInformationLength) || GetLastError() != 122 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x117,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                    v21);
    }
    else
    {
      v9 = (PSID *)operator new((unsigned int)TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v9 )
      {
        LastError = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x119,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
          (const char *)0x8007000ELL,
          ReturnLengtha);
        LODWORD(v55) = -2147024882;
LABEL_69:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x58B,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
          (const char *)LastError,
          ReturnLengtha);
        goto LABEL_84;
      }
      if ( GetTokenInformation(
             (HANDLE)v20,
             TokenUser,
             v9,
             (DWORD)TokenInformationLength,
             (PDWORD)&TokenInformationLength) )
      {
        v19 = v9;
        v64 = v9;
        LODWORD(v55) = 0;
        goto LABEL_25;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x11A,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                    v22);
      operator delete(v9);
      v9 = 0;
    }
    LODWORD(v55) = LastError;
    if ( (LastError & 0x80000000) != 0 )
      goto LABEL_69;
LABEL_25:
    StringSid = 0;
    if ( !ConvertSidToStringSidW(*v19, &StringSid) )
      break;
    v62 = 0;
    v24 = StringSid;
    if ( v57 != 1 )
      v24 = 0;
    ChildInitiationInfo = CreateChildInitiationInfo(v72, v8, v7, v24, (unsigned __int16 **)&v62);
    LastError = ChildInitiationInfo;
    LODWORD(v55) = ChildInitiationInfo;
    if ( ChildInitiationInfo < 0 )
    {
      v49 = 1431;
LABEL_71:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v49,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
        (const char *)(unsigned int)ChildInitiationInfo,
        ReturnLengthb);
      if ( v62 )
        LocalFree(v62);
      if ( StringSid )
        LocalFree(StringSid);
      if ( v19 )
      {
        v50 = v19;
LABEL_77:
        operator delete(v50);
        goto LABEL_84;
      }
      goto LABEL_84;
    }
    v60 = 0;
    ChildInitiationInfo = OmaDmGetNextSessionIDToUse(lpSubKey, 1, &v60);
    LastError = ChildInitiationInfo;
    LODWORD(v55) = ChildInitiationInfo;
    if ( ChildInitiationInfo < 0 )
    {
      v49 = 1434;
      goto LABEL_71;
    }
    v26 = (LPWSTR *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v28 = v26;
    if ( v26 )
    {
      v26[4] = 0;
      v26[5] = 0;
      *v26 = 0;
      v26[1] = 0;
      v26[2] = 0;
      v26[3] = 0;
    }
    else
    {
      v28 = 0;
    }
    v29 = StringSid;
    StringSid = 0;
    v30 = *v28;
    if ( *v28 )
    {
      v31 = GetLastError();
      LocalFree(v30);
      SetLastError(v31);
    }
    *v28 = v29;
    hlocal_string_nothrow = (LPWSTR *)wil::make_hlocal_string_nothrow((wil *)&hMem, lpSubKey, v27);
    v34 = hlocal_string_nothrow;
    v35 = (_DWORD **)(v28 + 1);
    if ( v28 + 1 != hlocal_string_nothrow )
    {
      v65 = *hlocal_string_nothrow;
      TokenInformationLength = *v35;
      if ( TokenInformationLength )
      {
        v36 = GetLastError();
        LocalFree(TokenInformationLength);
        SetLastError(v36);
      }
      *v35 = v65;
      *v34 = 0;
    }
    if ( hMem )
      LocalFree(hMem);
    v37 = (WCHAR *)v62;
    v62 = 0;
    v38 = v28[2];
    if ( v38 )
    {
      v39 = GetLastError();
      LocalFree(v38);
      SetLastError(v39);
    }
    v28[2] = v37;
    if ( v72 )
    {
      v40 = (HLOCAL *)wil::make_hlocal_string_nothrow((wil *)&v67, v72, v33);
      v10 |= 1u;
    }
    else
    {
      v17 = 0;
      v63 = 0;
      v40 = &v63;
      v10 |= 2u;
    }
    v41 = (void **)(v28 + 3);
    if ( v28 + 3 != (LPWSTR *)v40 )
    {
      v42 = *v40;
      TokenInformationLength = *v40;
      v43 = *v41;
      if ( *v41 )
      {
        v44 = GetLastError();
        LocalFree(v43);
        SetLastError(v44);
        v42 = TokenInformationLength;
      }
      *v41 = v42;
      *v40 = 0;
      v17 = v63;
    }
    if ( (v10 & 2) != 0 )
    {
      v10 &= ~2u;
      if ( v17 )
        LocalFree(v17);
    }
    if ( (v10 & 1) != 0 )
    {
      v10 &= ~1u;
      if ( v67 )
        LocalFree(v67);
    }
    v45 = a6;
    *((_DWORD *)v28 + 9) = a6;
    *((_BYTE *)v28 + 32) = a5;
    v28[5] = (LPWSTR)v60;
    v46 = 3;
    if ( v45 != 42 )
      v46 = 2;
    LODWORD(v55) = ThreadpoolManager::QueueThreadpoolWork(qword_140024308, v46, v33, v28);
    Logger = COmaDmPrcLogger::GetLogger();
    v9 = 0;
    v48 = v61;
    COmaDmPrcLogger::LogOmaDmPrcTriggerWvdActiveUserSessionInfo(
      Logger,
      StringSid,
      lpSubKey,
      (const unsigned __int16 *)v62,
      v72,
      v60,
      v61,
      _InterlockedCompareExchange(&ThreadpoolManager::m_numberOfWorkQueued, 0, 0));
    if ( v62 )
      LocalFree(v62);
    if ( StringSid )
      LocalFree(StringSid);
    if ( v19 )
      operator delete(v19);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    v15 = v48 + 1;
    v61 = v15;
    v16 = HIDWORD(v55);
    if ( v15 >= HIDWORD(v55) * v57 )
      goto LABEL_89;
    v7 = v74;
    v8 = v73;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x58E,
                (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
                v23);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v9 )
  {
    v50 = v9;
    goto LABEL_77;
  }
LABEL_84:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
LABEL_86:
  if ( v56 )
    UMgrFreeSessionUsers(v56);
LABEL_88:
  wil::details::lambda_call__lambda_887815b2c35ab7a699d0f5890dd297cb___::_lambda_call__lambda_887815b2c35ab7a699d0f5890dd297cb___(v68);
  return LastError;
}

```

## disassembly

```asm
0x140013350  mov     rax, rsp
0x140013353  mov     [rax+20h], r9d
0x140013357  mov     [rax+18h], r8
0x14001335b  mov     [rax+10h], rdx
0x14001335f  mov     [rax+8], rcx
0x140013363  push    rbp
0x140013364  push    rbx
0x140013365  push    rsi
0x140013366  push    rdi
0x140013367  push    r12
0x140013369  push    r13
0x14001336b  push    r14
0x14001336d  push    r15
0x14001336f  lea     rbp, [rax-47h]
0x140013373  sub     rsp, 0D8h
0x14001337a  mov     r12d, r9d
0x14001337d  mov     r13, r8
0x140013380  xor     esi, esi
0x140013382  mov     r15d, esi
0x140013385  mov     [rbp+3Fh+var_A4], esi
0x140013388  mov     dword ptr [rsp+110h+var_D0], esi
0x14001338c  mov     dword ptr [rsp+110h+var_D0+4], esi
0x140013390  mov     rax, [rbp+3Fh+TokenInformationLength]
0x140013394  mov     [rax], esi
0x140013396  lea     rax, [rsp+110h+var_D0]
0x14001339b  mov     [rbp+3Fh+var_70], rax
0x14001339f  lea     rax, [rbp+3Fh+arg_8]
0x1400133a3  mov     [rbp+3Fh+var_68], rax
0x1400133a7  lea     rax, [rbp+3Fh+lpSubKey]
0x1400133ab  mov     [rbp+3Fh+var_60], rax
0x1400133af  lea     rax, [rsp+110h+var_D0+4]
0x1400133b4  mov     [rbp+3Fh+var_58], rax
0x1400133b8  lea     ebx, [rsi+1]
0x1400133bb  mov     [rbp+3Fh+var_50], bl
0x1400133be  call    ?ShouldDisableOnRoaming@@YAHPEBGW4tagDMACCOUNTLOOKUPTYPE@@@Z; ShouldDisableOnRoaming(ushort const *,tagDMACCOUNTLOOKUPTYPE)
0x1400133c3  test    eax, eax
0x1400133c5  jz      short loc_1400133D3
0x1400133c7  mov     edi, 82AC0004h
0x1400133cc  mov     edx, 566h
0x1400133d1  jmp     short loc_1400133EA
0x1400133d3  mov     rcx, [rbp+3Fh+lpSubKey]
0x1400133d7  call    ?ShouldDisableAsDeletePending@@YAHPEBGW4tagDMACCOUNTLOOKUPTYPE@@@Z; ShouldDisableAsDeletePending(ushort const *,tagDMACCOUNTLOOKUPTYPE)
0x1400133dc  test    eax, eax
0x1400133de  jz      short loc_140013406
0x1400133e0  mov     edi, 82AC0006h
0x1400133e5  mov     edx, 56Ch; void *
0x1400133ea  mov     dword ptr [rsp+110h+var_D0], edi
0x1400133ee  mov     rcx, [rbp+47h]; this
0x1400133f2  mov     r9d, edi; char *
0x1400133f5  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x1400133fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013401  jmp     loc_140013A73
0x140013406  cmp     [rbp+3Fh+arg_20], sil
0x14001340a  jz      short loc_140013418
0x14001340c  mov     edi, 8000FFFFh
0x140013411  mov     edx, 572h
0x140013416  jmp     short loc_1400133EA
0x140013418  mov     [rsp+110h+var_C8], rsi
0x14001341d  lea     rdx, [rsp+110h+var_C8]
0x140013422  lea     rcx, [rsp+110h+var_D0+4]
0x140013427  call    cs:__imp_UMgrEnumerateSessionUsers
0x14001342e  nop     dword ptr [rax+rax+00h]
0x140013433  mov     edi, eax
0x140013435  mov     dword ptr [rsp+110h+var_D0], eax
0x140013439  test    eax, eax
0x14001343b  jns     short loc_14001345A
0x14001343d  mov     rcx, [rbp+47h]; this
0x140013441  mov     r9d, eax; char *
0x140013444  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x14001344b  mov     edx, 577h; void *
0x140013450  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013455  jmp     loc_140013A5C
0x14001345a  mov     rcx, [rsp+110h+var_C8]
0x14001345f  cmp     dword ptr [rsp+110h+var_D0+4], esi
0x140013463  jz      loc_140013AA4
0x140013469  test    rcx, rcx
0x14001346c  jz      loc_140013AA4
0x140013472  mov     [rsp+110h+var_C0], ebx
0x140013476  lea     r8, [rsp+110h+var_C0]; unsigned int *
0x14001347b  mov     rcx, [rbp+3Fh+lpSubKey]; lpSubKey
0x14001347f  call    ?GetTestSettingDword@@YAJPEBG0PEAK@Z; GetTestSettingDword(ushort const *,ushort const *,ulong *)
0x140013484  mov     edi, esi
0x140013486  mov     [rbp+3Fh+var_A4], esi
0x140013489  mov     eax, [rsp+110h+var_C0]
0x14001348d  mov     ecx, dword ptr [rsp+110h+var_D0+4]
0x140013491  imul    eax, ecx
0x140013494  test    eax, eax
0x140013496  jz      loc_140013A80
0x14001349c  mov     rbx, [rbp+3Fh+var_98]
0x1400134a0  xor     edx, edx
0x1400134a2  mov     eax, edi
0x1400134a4  div     ecx
0x1400134a6  mov     r8d, edx
0x1400134a9  mov     [rbp+3Fh+TokenHandle], rsi
0x1400134ad  add     r8, r8
0x1400134b0  lea     rdx, [rbp+3Fh+TokenHandle]
0x1400134b4  mov     rcx, [rsp+110h+var_C8]
0x1400134b9  mov     rcx, [rcx+r8*8]
0x1400134bd  call    cs:__imp_UMgrQueryUserToken
0x1400134c4  nop     dword ptr [rax+rax+00h]
0x1400134c9  mov     edi, eax
0x1400134cb  mov     dword ptr [rsp+110h+var_D0], eax
0x1400134cf  test    eax, eax
0x1400134d1  js      loc_140013A28
0x1400134d7  mov     rax, [rbp+3Fh+TokenHandle]
0x1400134db  mov     r14, rsi
0x1400134de  mov     [rbp+3Fh+var_90], rsi
0x1400134e2  mov     rdi, 0FFFFFFFFFFFFFFFAh
0x1400134e9  test    rax, rax
0x1400134ec  cmovnz  rdi, rax
0x1400134f0  mov     dword ptr [rbp+3Fh+TokenInformationLength], esi
0x1400134f3  lea     rax, [rbp+3Fh+TokenInformationLength]
0x1400134f7  mov     [rsp+110h+ReturnLength], rax; int
0x1400134fc  xor     r9d, r9d; TokenInformationLength
0x1400134ff  xor     r8d, r8d; TokenInformation
0x140013502  lea     edx, [r9+1]; TokenInformationClass
0x140013506  mov     rcx, rdi; TokenHandle
0x140013509  call    cs:__imp_GetTokenInformation
0x140013510  nop     dword ptr [rax+rax+00h]
0x140013515  test    eax, eax
0x140013517  jnz     loc_1400135AC
0x14001351d  call    cs:__imp_GetLastError
0x140013524  nop     dword ptr [rax+rax+00h]
0x140013529  cmp     eax, 7Ah ; 'z'
0x14001352c  jnz     short loc_1400135AC
0x14001352e  mov     ecx, dword ptr [rbp+3Fh+TokenInformationLength]; unsigned __int64
0x140013531  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140013538  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001353d  mov     rsi, rax
0x140013540  test    rax, rax
0x140013543  jz      loc_140013950
0x140013549  lea     rax, [rbp+3Fh+TokenInformationLength]
0x14001354d  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x140013552  mov     r9d, dword ptr [rbp+3Fh+TokenInformationLength]; TokenInformationLength
0x140013556  mov     r8, rsi; TokenInformation
0x140013559  mov     edx, 1; TokenInformationClass
0x14001355e  mov     rcx, rdi; TokenHandle
0x140013561  call    cs:__imp_GetTokenInformation
0x140013568  nop     dword ptr [rax+rax+00h]
0x14001356d  test    eax, eax
0x14001356f  jnz     short loc_14001359B
0x140013571  mov     rcx, [rbp+47h]; this
0x140013575  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14001357c  mov     edx, 11Ah; void *
0x140013581  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140013586  mov     edi, eax
0x140013588  mov     rcx, rsi
0x14001358b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140013592  nop     dword ptr [rax+rax+00h]
0x140013597  xor     esi, esi
0x140013599  jmp     short loc_1400135C3
0x14001359b  mov     r14, rsi
0x14001359e  mov     [rbp+3Fh+var_90], rsi
0x1400135a2  mov     dword ptr [rsp+110h+var_D0], 0
0x1400135aa  jmp     short loc_1400135CF
0x1400135ac  mov     rcx, [rbp+47h]; this
0x1400135b0  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400135b7  mov     edx, 117h; void *
0x1400135bc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400135c1  mov     edi, eax
0x1400135c3  mov     dword ptr [rsp+110h+var_D0], edi
0x1400135c7  test    edi, edi
0x1400135c9  js      loc_140013971
0x1400135cf  mov     [rbp+3Fh+StringSid], 0
0x1400135d7  lea     rdx, [rbp+3Fh+StringSid]; StringSid
0x1400135db  mov     rcx, [r14]; Sid
0x1400135de  call    cs:__imp_ConvertSidToStringSidW
0x1400135e5  nop     dword ptr [rax+rax+00h]
0x1400135ea  test    eax, eax
0x1400135ec  jz      loc_1400139F1
0x1400135f2  mov     [rbp+3Fh+var_A0], 0
0x1400135fa  mov     r9, [rbp+3Fh+StringSid]
0x1400135fe  xor     eax, eax
0x140013600  cmp     [rsp+110h+var_C0], 1
0x140013605  cmovnz  r9, rax; unsigned __int16 *
0x140013609  lea     rax, [rbp+3Fh+var_A0]
0x14001360d  mov     [rsp+110h+ReturnLength], rax; int
0x140013612  mov     r8d, r12d; int
0x140013615  mov     rdx, r13; struct OMADMINITIATIONINFO *
0x140013618  mov     rcx, [rbp+3Fh+arg_8]; unsigned __int16 *
0x14001361c  call    ?CreateChildInitiationInfo@@YAJPEBGPEAUOMADMINITIATIONINFO@@H0PEAPEAG@Z; CreateChildInitiationInfo(ushort const *,OMADMINITIATIONINFO *,int,ushort const *,ushort * *)
0x140013621  mov     edi, eax
0x140013623  mov     dword ptr [rsp+110h+var_D0], eax
0x140013627  xor     r12d, r12d
0x14001362a  test    eax, eax
0x14001362c  js      loc_1400139EA
0x140013632  mov     [rbp+3Fh+var_A8], r12d
0x140013636  lea     r8, [rbp+3Fh+var_A8]
0x14001363a  lea     edx, [r12+1]
0x14001363f  mov     rcx, [rbp+3Fh+lpSubKey]
0x140013643  call    cs:__imp_?OmaDmGetNextSessionIDToUse@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAK@Z; OmaDmGetNextSessionIDToUse(ushort const *,tagDMACCOUNTLOOKUPTYPE,ulong *)
0x14001364a  nop     dword ptr [rax+rax+00h]
0x14001364f  mov     edi, eax
0x140013651  mov     dword ptr [rsp+110h+var_D0], eax
0x140013655  test    eax, eax
0x140013657  js      loc_14001398F
0x14001365d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140013664  lea     ecx, [r12+30h]; unsigned __int64
0x140013669  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001366e  mov     rsi, rax
0x140013671  test    rax, rax
0x140013674  jz      short loc_14001368F
0x140013676  mov     [rax+20h], r12
0x14001367a  mov     [rax+28h], r12
0x14001367e  mov     [rax], r12
0x140013681  mov     [rax+8], r12
0x140013685  mov     [rax+10h], r12
0x140013689  mov     [rax+18h], r12
0x14001368d  jmp     short loc_140013692
0x14001368f  mov     rsi, r12
0x140013692  mov     r13, [rbp+3Fh+StringSid]
0x140013696  mov     [rbp+3Fh+StringSid], r12
0x14001369a  mov     r12, [rsi]
0x14001369d  test    r12, r12
0x1400136a0  jz      short loc_1400136CD
0x1400136a2  call    cs:__imp_GetLastError
0x1400136a9  nop     dword ptr [rax+rax+00h]
0x1400136ae  mov     edi, eax
0x1400136b0  mov     rcx, r12; hMem
0x1400136b3  call    cs:__imp_LocalFree
0x1400136ba  nop     dword ptr [rax+rax+00h]
0x1400136bf  mov     ecx, edi; dwErrCode
0x1400136c1  call    cs:__imp_SetLastError
0x1400136c8  nop     dword ptr [rax+rax+00h]
0x1400136cd  mov     [rsi], r13
0x1400136d0  mov     rdx, [rbp+3Fh+lpSubKey]; unsigned __int16 *
0x1400136d4  lea     rcx, [rbp+3Fh+hMem]; this
0x1400136d8  call    ?make_hlocal_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_hlocal_string_nothrow(ushort const *,unsigned __int64)
0x1400136dd  mov     r12, rax
0x1400136e0  lea     r13, [rsi+8]
0x1400136e4  cmp     r13, rax
0x1400136e7  jz      short loc_140013739
0x1400136e9  mov     rax, [rax]
0x1400136ec  mov     [rbp+3Fh+var_88], rax
0x1400136f0  mov     rax, [r13+0]
0x1400136f4  mov     [rbp+3Fh+TokenInformationLength], rax
0x1400136f8  test    rax, rax
0x1400136fb  jz      short loc_140013729
0x1400136fd  call    cs:__imp_GetLastError
0x140013704  nop     dword ptr [rax+rax+00h]
0x140013709  mov     edi, eax
0x14001370b  mov     rcx, [rbp+3Fh+TokenInformationLength]; hMem
0x14001370f  call    cs:__imp_LocalFree
0x140013716  nop     dword ptr [rax+rax+00h]
0x14001371b  mov     ecx, edi; dwErrCode
0x14001371d  call    cs:__imp_SetLastError
0x140013724  nop     dword ptr [rax+rax+00h]
0x140013729  mov     rax, [rbp+3Fh+var_88]
0x14001372d  mov     [r13+0], rax
0x140013731  mov     qword ptr [r12], 0
0x140013739  mov     rcx, [rbp+3Fh+hMem]; hMem
0x14001373d  test    rcx, rcx
0x140013740  jz      short loc_14001374E
0x140013742  call    cs:__imp_LocalFree
0x140013749  nop     dword ptr [rax+rax+00h]
0x14001374e  mov     r13, [rbp+3Fh+var_A0]
0x140013752  mov     [rbp+3Fh+var_A0], 0
0x14001375a  mov     r12, [rsi+10h]
0x14001375e  test    r12, r12
0x140013761  jz      short loc_14001378E
0x140013763  call    cs:__imp_GetLastError
0x14001376a  nop     dword ptr [rax+rax+00h]
0x14001376f  mov     edi, eax
0x140013771  mov     rcx, r12; hMem
0x140013774  call    cs:__imp_LocalFree
0x14001377b  nop     dword ptr [rax+rax+00h]
0x140013780  mov     ecx, edi; dwErrCode
0x140013782  call    cs:__imp_SetLastError
0x140013789  nop     dword ptr [rax+rax+00h]
0x14001378e  mov     [rsi+10h], r13
0x140013792  mov     rdx, [rbp+3Fh+arg_8]; unsigned __int16 *
0x140013796  test    rdx, rdx
0x140013799  jz      short loc_1400137AD
0x14001379b  lea     rcx, [rbp+3Fh+var_78]; this
0x14001379f  call    ?make_hlocal_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_hlocal_string_nothrow(ushort const *,unsigned __int64)
0x1400137a4  mov     rdi, rax
0x1400137a7  or      r15d, 1
0x1400137ab  jmp     short loc_1400137BB
0x1400137ad  xor     ebx, ebx
0x1400137af  mov     [rbp+3Fh+var_98], rbx
0x1400137b3  lea     rdi, [rbp+3Fh+var_98]
0x1400137b7  or      r15d, 2
0x1400137bb  lea     r12, [rsi+18h]
0x1400137bf  cmp     r12, rdi
0x1400137c2  jz      short loc_140013812
0x1400137c4  mov     rax, [rdi]
0x1400137c7  mov     [rbp+3Fh+TokenInformationLength], rax
0x1400137cb  mov     r13, [r12]
0x1400137cf  test    r13, r13
0x1400137d2  jz      short loc_140013803
0x1400137d4  call    cs:__imp_GetLastError
0x1400137db  nop     dword ptr [rax+rax+00h]
0x1400137e0  mov     ebx, eax
0x1400137e2  mov     rcx, r13; hMem
0x1400137e5  call    cs:__imp_LocalFree
0x1400137ec  nop     dword ptr [rax+rax+00h]
0x1400137f1  mov     ecx, ebx; dwErrCode
0x1400137f3  call    cs:__imp_SetLastError
0x1400137fa  nop     dword ptr [rax+rax+00h]
0x1400137ff  mov     rax, [rbp+3Fh+TokenInformationLength]
  ... truncated ...
```
