# CflApi::ClearTempUserAccount(void)

- ea: `0x18001c500`
- end: `0x18001cb3b`
- name: `?ClearTempUserAccount@CflApi@@YAJXZ`
- size: `1595`
- prototype: `__int64 __fastcall(CflApi *__hidden this)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800101c0`
- `0x180020a54`

## callees

- `0x1800067a4`
- `0x1800067c4`
- `0x1800071b4`
- `0x180010700`
- `0x18001332c`
- `0x18001492c`
- `0x18001a2f8`
- `0x18001ba30`
- `0x18001bcfc`
- `0x18001c500`
- `0x18001e684`
- `0x18001f46c`
- `0x18001f4d8`
- `0x18001f66c`
- `0x18001f8e4`
- `0x18002222c`
- `0x18002225c`
- `0x18002237c`
- `0x180027c6c`
- `0x18002dfe4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c8a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c963`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c991`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c8a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c963`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c991`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001c5af`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001ca8f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001c5af`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001ca8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c58c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c58c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cacf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cb2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cacf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cb2e`
- `samcli!NetUserGetInfo` at `0x18001c820`
- `samcli!NetUserGetInfo` at `0x18001c820`
- `samcli!NetUserEnum` at `0x18001c7a9`
- `samcli!NetUserEnum` at `0x18001c7a9`
- `samcli!NetUserDel` at `0x18001c9b0`
- `samcli!NetUserDel` at `0x18001c9b0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001c528`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001c528`
- `USERENV!DeleteProfileW` at `0x18001c66c`
- `USERENV!DeleteProfileW` at `0x18001ca00`
- `USERENV!DeleteProfileW` at `0x18001c66c`
- `USERENV!DeleteProfileW` at `0x18001ca00`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001c874`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001c874`
- `netutils!NetApiBufferFree` at `0x18001c8b0`
- `netutils!NetApiBufferFree` at `0x18001c973`
- `netutils!NetApiBufferFree` at `0x18001c9a1`
- `netutils!NetApiBufferFree` at `0x18001ca6c`
- `netutils!NetApiBufferFree` at `0x18001cb1e`
- `netutils!NetApiBufferFree` at `0x18001c8b0`
- `netutils!NetApiBufferFree` at `0x18001c973`
- `netutils!NetApiBufferFree` at `0x18001c9a1`
- `netutils!NetApiBufferFree` at `0x18001ca6c`
- `netutils!NetApiBufferFree` at `0x18001cb1e`

## string_xrefs

- `0x18001ca84`: `CflTempAccountCreated`
- `0x18001c550`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c72e`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c84b`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c884`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c8f5`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c938`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c9df`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001ca2b`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001cab4`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001cb03`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CflApi::ClearTempUserAccount(CflApi *this)
{
  int v1; // eax
  bool v2; // dl
  unsigned int v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  int v6; // eax
  bool v7; // dl
  int CanProcessCleanupTempUserAccountProfile; // eax
  bool v9; // r15
  int TempUserAccountSidsForDeferredProfileCleanup; // eax
  LPCWSTR v11; // rdi
  LPCWSTR v12; // rbx
  LPCWSTR i; // rsi
  const WCHAR *v14; // rcx
  unsigned int v15; // r8d
  const char *v16; // r9
  wchar_t *v17; // r14
  wchar_t *v18; // rbx
  const wchar_t *v19; // rdx
  size_t v20; // r8
  const wchar_t *v21; // rcx
  int v22; // eax
  DWORD v23; // eax
  DWORD v24; // r14d
  LPBYTE v25; // rsi
  DWORD v26; // r12d
  const wchar_t *v27; // rcx
  LPCWSTR v28; // rdi
  WCHAR *v29; // rbx
  const char *v30; // r9
  int LastError; // edi
  __int64 v32; // rax
  unsigned __int64 v33; // rdi
  int v34; // eax
  unsigned __int64 v35; // rdx
  WCHAR *v36; // rdi
  int v37; // eax
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // eax
  int v41; // eax
  bool v42; // dl
  int phkResult; // [rsp+20h] [rbp-59h]
  unsigned int phkResulta; // [rsp+20h] [rbp-59h]
  int phkResultb; // [rsp+20h] [rbp-59h]
  const char *entriesread; // [rsp+28h] [rbp-51h]
  LPWSTR StringSid; // [rsp+40h] [rbp-39h] BYREF
  LPBYTE v49; // [rsp+48h] [rbp-31h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-29h] BYREF
  LPBYTE bufptr; // [rsp+58h] [rbp-21h] BYREF
  wchar_t *S1[2]; // [rsp+60h] [rbp-19h] BYREF
  wchar_t *v53; // [rsp+70h] [rbp-9h]
  LPCWSTR v54; // [rsp+78h] [rbp-1h] BYREF
  WCHAR *v55; // [rsp+80h] [rbp+7h]
  LPCWSTR lpSidString[2]; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v57; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  char v59; // [rsp+E0h] [rbp+67h] BYREF
  DWORD v60; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD resume_handle; // [rsp+F0h] [rbp+77h] BYREF
  DWORD totalentries; // [rsp+F8h] [rbp+7Fh] BYREF

  v1 = RegDeleteKeyW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ExperienceManagerData");
  v2 = (v1 & 0xFFFFFFFD) != 0;
  if ( v1 > 0 )
    v1 = (unsigned __int16)v1 | 0x80070000;
  if ( v2 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)v1,
      phkResult);
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE", 0, 2u, &hKey);
  if ( v3 )
  {
    wil::details::in1diag3::_Log_Win32(retaddr, v4, v5, (const char *)v3, phkResulta);
  }
  else
  {
    v6 = RegDeleteValueW(hKey, L"DefaultAccountAction");
    v7 = (v6 & 0xFFFFFFFD) != 0;
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    if ( v7 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)(unsigned int)v6,
        phkResulta);
  }
  v59 = 0;
  CanProcessCleanupTempUserAccountProfile = CflApi::CanProcessCleanupTempUserAccountProfile(&v59);
  if ( CanProcessCleanupTempUserAccountProfile < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x113,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)CanProcessCleanupTempUserAccountProfile,
      phkResulta);
  if ( !v59 )
  {
    v9 = 0;
    goto LABEL_43;
  }
  v9 = 1;
  *(_OWORD *)lpSidString = 0;
  v57 = 0;
  TempUserAccountSidsForDeferredProfileCleanup = CflApi::GetTempUserAccountSidsForDeferredProfileCleanup(lpSidString);
  if ( TempUserAccountSidsForDeferredProfileCleanup < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)TempUserAccountSidsForDeferredProfileCleanup,
      phkResulta);
  *(_OWORD *)S1 = 0;
  v53 = 0;
  v11 = lpSidString[0];
  v12 = lpSidString[0];
  for ( i = lpSidString[1]; v12 != i; v12 += 16 )
  {
    if ( *((_QWORD *)v12 + 3) <= 7u )
      v14 = v12;
    else
      v14 = *(const WCHAR **)v12;
    if ( !DeleteProfileW(v14, 0, 0) )
    {
      wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x11F, v15, v16);
      if ( S1[1] == v53 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(S1, S1[1], v12);
      }
      else
      {
        std::wstring::wstring(S1[1], v12);
        S1[1] += 16;
      }
    }
  }
  v17 = S1[1];
  v18 = S1[0];
  if ( (char *)S1[1] - (char *)S1[0] != (char *)i - (char *)v11 )
    goto LABEL_38;
  if ( S1[0] != S1[1] )
  {
    while ( 1 )
    {
      v19 = *((_QWORD *)v11 + 3) <= 7u ? v11 : *(const wchar_t **)v11;
      v20 = *((_QWORD *)v18 + 2);
      v21 = *((_QWORD *)v18 + 3) <= 7u ? v18 : *(const wchar_t **)v18;
      if ( v20 != *((_QWORD *)v11 + 2) || v20 && wmemcmp(v21, v19, v20) )
        break;
      v18 += 16;
      if ( v18 == v17 )
        goto LABEL_41;
      v11 += 16;
    }
LABEL_38:
    v22 = CflApi::ReplaceTempUserAccountSidsForDeferredProfileCleanup(S1);
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x127,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)(unsigned int)v22,
        phkResulta);
    v9 = S1[0] == S1[1];
  }
LABEL_41:
  std::vector<std::wstring>::_Tidy(S1);
  std::vector<std::wstring>::_Tidy(lpSidString);
LABEL_43:
  resume_handle = 0;
  while ( 1 )
  {
    v60 = 0;
    totalentries = 0;
    bufptr = 0;
    v23 = NetUserEnum(0, 2u, 2u, &bufptr, 0xFFFFFFFF, &v60, &totalentries, &resume_handle);
    v24 = v23;
    if ( v23 )
    {
      if ( v23 != 234 )
        break;
    }
    v25 = bufptr;
    if ( bufptr )
    {
      v26 = 0;
      if ( v60 )
      {
        while ( 1 )
        {
          if ( !v25 )
          {
LABEL_89:
            v25 = bufptr;
            break;
          }
          v27 = (const wchar_t *)*((_QWORD *)v25 + 10);
          if ( v27 && !wcscmp_0(v27, L"{2D0CB8B4-2469-4C46-A0FC-F09CAF1FF0CD}") )
          {
            v28 = *(LPCWSTR *)v25;
            v29 = 0;
            v55 = 0;
            v49 = 0;
            if ( NetUserGetInfo(0, v28, 0x17u, &v49) )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x38C,
                (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
                (const char *)0x80004005LL,
                (int)"user name: %ls, status: %d",
                (const char *)v28);
            }
            else
            {
              StringSid = 0;
              if ( !ConvertSidToStringSidW(*((PSID *)v49 + 4), &StringSid) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x390,
                              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
                              v30);
                if ( StringSid )
                  LocalFree(StringSid);
                if ( v49 )
                  NetApiBufferFree(v49);
                if ( LastError < 0 )
                  goto LABEL_88;
LABEL_78:
                v24 = NetUserDel(0, *(LPCWSTR *)v25);
                if ( v24 )
                {
                  wil::details::in1diag3::Log_HrMsg(
                    retaddr,
                    (void *)0x155,
                    (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
                    (const char *)0x80004005LL,
                    (int)"user name: %ls, status: %d",
                    *(const char **)v25);
                  goto LABEL_86;
                }
                if ( v59 )
                {
                  if ( DeleteProfileW(v29, 0, 0) )
                  {
LABEL_86:
                    if ( v29 )
                      CflFreeBuffer(v29);
                    goto LABEL_88;
                  }
                  wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x15E, v38, v39);
                }
                v40 = CflApi::AddTempUserAccountSidForDeferredProfileCleanup(v29);
                if ( v40 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x163,
                    (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
                    (const char *)(unsigned int)v40,
                    phkResultb);
                v9 = 0;
                goto LABEL_86;
              }
              v32 = -1;
              do
                ++v32;
              while ( StringSid[v32] );
              v33 = v32 + 1;
              v54 = 0;
              v34 = CflApiNew::AllocBuffer_unsigned_short_(v32 + 1, &v54);
              if ( v34 >= 0 )
              {
                v35 = v33;
                v36 = (WCHAR *)v54;
                v37 = StringCchCopyW((unsigned __int16 *)v54, v35, StringSid);
                if ( v37 >= 0 )
                {
                  v29 = v36;
                  v55 = v36;
                  if ( StringSid )
                    LocalFree(StringSid);
                  if ( v49 )
                    NetApiBufferFree(v49);
                  goto LABEL_78;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x396,
                  (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
                  (const char *)(unsigned int)v37,
                  phkResultb);
                if ( v36 )
                  CflFreeBuffer(v36);
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x395,
                  (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
                  (const char *)(unsigned int)v34,
                  phkResultb);
                if ( v54 )
                  CflFreeBuffer((HLOCAL)v54);
              }
              if ( StringSid )
                LocalFree(StringSid);
            }
            if ( v49 )
              NetApiBufferFree(v49);
          }
LABEL_88:
          ++v26;
          v25 += 152;
          if ( v26 >= v60 )
            goto LABEL_89;
        }
      }
    }
    if ( v25 )
      NetApiBufferFree(v25);
    if ( v24 != 234 )
    {
      if ( v9 )
      {
        v41 = RegDeleteValueW(hKey, L"CflTempAccountCreated");
        v42 = (v41 & 0xFFFFFFFD) != 0;
        if ( v41 > 0 )
          v41 = (unsigned __int16)v41 | 0x80070000;
        if ( v42 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x172,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
            (const char *)(unsigned int)v41,
            phkResultb);
      }
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    }
  }
  LODWORD(entriesread) = v23;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x143,
    (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
    (const char *)0x80004005LL,
    (int)"status: %d",
    entriesread);
  if ( bufptr )
    NetApiBufferFree(bufptr);
  if ( hKey )
    RegCloseKey(hKey);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18001c500  push    rbp
0x18001c502  push    rbx
0x18001c503  push    rsi
0x18001c504  push    rdi
0x18001c505  push    r12
0x18001c507  push    r14
0x18001c509  push    r15
0x18001c50b  lea     rbp, [rsp-27h]
0x18001c510  sub     rsp, 0A0h
0x18001c517  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001c51e  mov     rbx, 0FFFFFFFF80000002h
0x18001c525  mov     rcx, rbx; hKey
0x18001c528  call    cs:__imp_RegDeleteKeyW
0x18001c52e  mov     r15d, 0FFFFFFFDh
0x18001c534  test    r15d, eax
0x18001c537  setnz   dl
0x18001c53a  xor     edi, edi
0x18001c53c  mov     r14d, 80070000h
0x18001c542  test    eax, eax
0x18001c544  jle     short loc_18001C54C
0x18001c546  movzx   eax, ax
0x18001c549  or      eax, r14d
0x18001c54c  mov     rcx, [rbp+5Fh]; this
0x18001c550  lea     rsi, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001c557  test    dl, dl
0x18001c559  jz      short loc_18001C56C
0x18001c55b  mov     r9d, eax; char *
0x18001c55e  mov     r8, rsi; unsigned int
0x18001c561  mov     edx, 0FDh; void *
0x18001c566  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c56b  nop
0x18001c56c  mov     [rbp+57h+hKey], rdi
0x18001c570  lea     rax, [rbp+57h+hKey]
0x18001c574  mov     [rsp+0D0h+phkResult], rax; int
0x18001c579  mov     r9d, 2; samDesired
0x18001c57f  xor     r8d, r8d; ulOptions
0x18001c582  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001c589  mov     rcx, rbx; hKey
0x18001c58c  call    cs:__imp_RegOpenKeyExW
0x18001c592  mov     rcx, [rbp+5Fh]; this
0x18001c596  test    eax, eax
0x18001c598  jz      short loc_18001C5A4
0x18001c59a  mov     r9d, eax; char *
0x18001c59d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18001c5a2  jmp     short loc_18001C5DD
0x18001c5a4  lea     rdx, aDefaultaccount; "DefaultAccountAction"
0x18001c5ab  mov     rcx, [rbp+57h+hKey]; hKey
0x18001c5af  call    cs:__imp_RegDeleteValueW
0x18001c5b5  test    r15d, eax
0x18001c5b8  setnz   dl
0x18001c5bb  test    eax, eax
0x18001c5bd  jle     short loc_18001C5C5
0x18001c5bf  movzx   eax, ax
0x18001c5c2  or      eax, r14d
0x18001c5c5  mov     rcx, [rbp+5Fh]; this
0x18001c5c9  test    dl, dl
0x18001c5cb  jz      short loc_18001C5DD
0x18001c5cd  mov     r9d, eax; char *
0x18001c5d0  mov     r8, rsi; unsigned int
0x18001c5d3  mov     edx, 10Ch; void *
0x18001c5d8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c5dd  mov     [rbp+57h+arg_0], dil
0x18001c5e1  lea     rcx, [rbp+57h+arg_0]
0x18001c5e5  call    CflApi__CanProcessCleanupTempUserAccountProfile
0x18001c5ea  mov     rcx, [rbp+5Fh]; this
0x18001c5ee  test    eax, eax
0x18001c5f0  jns     short loc_18001C602
0x18001c5f2  mov     r9d, eax; char *
0x18001c5f5  mov     r8, rsi; unsigned int
0x18001c5f8  mov     edx, 113h; void *
0x18001c5fd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c602  cmp     [rbp+57h+arg_0], dil
0x18001c606  jz      loc_18001C768
0x18001c60c  mov     r15b, 1
0x18001c60f  xorps   xmm0, xmm0
0x18001c612  movdqu  xmmword ptr [rbp+57h+lpSidString], xmm0
0x18001c617  mov     [rbp+57h+var_38], rdi
0x18001c61b  lea     rcx, [rbp+57h+lpSidString]
0x18001c61f  call    CflApi__GetTempUserAccountSidsForDeferredProfileCleanup
0x18001c624  mov     rcx, [rbp+5Fh]; this
0x18001c628  test    eax, eax
0x18001c62a  jns     short loc_18001C63C
0x18001c62c  mov     r9d, eax; char *
0x18001c62f  mov     r8, rsi; unsigned int
0x18001c632  mov     edx, 117h; void *
0x18001c637  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c63c  xorps   xmm0, xmm0
0x18001c63f  movdqu  xmmword ptr [rbp+57h+S1], xmm0
0x18001c644  mov     [rbp+57h+var_60], rdi
0x18001c648  mov     rdi, [rbp+57h+lpSidString]
0x18001c64c  mov     rbx, rdi
0x18001c64f  mov     rsi, [rbp+57h+lpSidString+8]
0x18001c653  cmp     rdi, rsi
0x18001c656  jz      short loc_18001C6B8
0x18001c658  cmp     qword ptr [rbx+18h], 7
0x18001c65d  jbe     short loc_18001C664
0x18001c65f  mov     rcx, [rbx]
0x18001c662  jmp     short loc_18001C667
0x18001c664  mov     rcx, rbx; lpSidString
0x18001c667  xor     r8d, r8d; lpComputerName
0x18001c66a  xor     edx, edx; lpProfilePath
0x18001c66c  call    cs:__imp_DeleteProfileW
0x18001c672  test    eax, eax
0x18001c674  jnz     short loc_18001C6AF
0x18001c676  mov     rcx, [rbp+5Fh]; this
0x18001c67a  mov     edx, 11Fh; void *
0x18001c67f  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18001c684  mov     rax, [rbp+57h+S1+8]
0x18001c688  cmp     rax, [rbp+57h+var_60]
0x18001c68c  jz      short loc_18001C6A0
0x18001c68e  mov     rdx, rbx
0x18001c691  mov     rcx, rax
0x18001c694  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001c699  add     [rbp+57h+S1+8], 20h ; ' '
0x18001c69e  jmp     short loc_18001C6AF
0x18001c6a0  mov     r8, rbx
0x18001c6a3  mov     rdx, rax
0x18001c6a6  lea     rcx, [rbp+57h+S1]
0x18001c6aa  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18001c6af  add     rbx, 20h ; ' '
0x18001c6b3  cmp     rbx, rsi
0x18001c6b6  jnz     short loc_18001C658
0x18001c6b8  mov     r14, [rbp+57h+S1+8]
0x18001c6bc  mov     rax, r14
0x18001c6bf  mov     rbx, [rbp+57h+S1]
0x18001c6c3  sub     rax, rbx
0x18001c6c6  sub     rsi, rdi
0x18001c6c9  cmp     rax, rsi
0x18001c6cc  jnz     short loc_18001C718
0x18001c6ce  cmp     rbx, r14
0x18001c6d1  jz      short loc_18001C751
0x18001c6d3  cmp     qword ptr [rdi+18h], 7
0x18001c6d8  jbe     short loc_18001C6DF
0x18001c6da  mov     rdx, [rdi]
0x18001c6dd  jmp     short loc_18001C6E2
0x18001c6df  mov     rdx, rdi; S2
0x18001c6e2  mov     r8, [rbx+10h]; N
0x18001c6e6  cmp     qword ptr [rbx+18h], 7
0x18001c6eb  jbe     short loc_18001C6F2
0x18001c6ed  mov     rcx, [rbx]
0x18001c6f0  jmp     short loc_18001C6F5
0x18001c6f2  mov     rcx, rbx; S1
0x18001c6f5  cmp     r8, [rdi+10h]
0x18001c6f9  jnz     short loc_18001C718
0x18001c6fb  test    r8, r8
0x18001c6fe  jz      short loc_18001C709
0x18001c700  call    wmemcmp
0x18001c705  test    eax, eax
0x18001c707  jnz     short loc_18001C718
0x18001c709  add     rbx, 20h ; ' '
0x18001c70d  cmp     rbx, r14
0x18001c710  jz      short loc_18001C751
0x18001c712  add     rdi, 20h ; ' '
0x18001c716  jmp     short loc_18001C6D3
0x18001c718  lea     rcx, [rbp+57h+S1]
0x18001c71c  call    CflApi__ReplaceTempUserAccountSidsForDeferredProfileCleanup
0x18001c721  mov     rcx, [rbp+5Fh]; this
0x18001c725  xor     edi, edi
0x18001c727  test    eax, eax
0x18001c729  jns     short loc_18001C73F
0x18001c72b  mov     r9d, eax; char *
0x18001c72e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001c735  mov     edx, 127h; void *
0x18001c73a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c73f  movzx   r15d, r15b
0x18001c743  mov     rax, [rbp+57h+S1+8]
0x18001c747  cmp     [rbp+57h+S1], rax
0x18001c74b  cmovnz  r15d, edi
0x18001c74f  jmp     short loc_18001C753
0x18001c751  xor     edi, edi
0x18001c753  lea     rcx, [rbp+57h+S1]
0x18001c757  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001c75c  nop
0x18001c75d  lea     rcx, [rbp+57h+lpSidString]
0x18001c761  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001c766  jmp     short loc_18001C76B
0x18001c768  mov     r15b, dil
0x18001c76b  mov     [rbp+57h+arg_10], edi
0x18001c76e  mov     [rbp+57h+arg_8], edi
0x18001c771  mov     [rbp+57h+arg_18], edi
0x18001c774  mov     [rbp+57h+bufptr], rdi
0x18001c778  lea     rax, [rbp+57h+arg_10]
0x18001c77c  mov     [rsp+0D0h+resume_handle], rax; resume_handle
0x18001c781  lea     rax, [rbp+57h+arg_18]
0x18001c785  mov     [rsp+0D0h+totalentries], rax; totalentries
0x18001c78a  lea     rax, [rbp+57h+arg_8]
0x18001c78e  mov     [rsp+0D0h+entriesread], rax; entriesread
0x18001c793  mov     dword ptr [rsp+0D0h+phkResult], 0FFFFFFFFh; int
0x18001c79b  lea     r9, [rbp+57h+bufptr]; bufptr
0x18001c79f  mov     edx, 2; level
0x18001c7a4  xor     ecx, ecx; servername
0x18001c7a6  mov     r8d, edx; filter
0x18001c7a9  call    cs:__imp_NetUserEnum
0x18001c7af  mov     r14d, eax
0x18001c7b2  test    eax, eax
0x18001c7b4  jz      short loc_18001C7C1
0x18001c7b6  cmp     eax, 0EAh
0x18001c7bb  jnz     loc_18001CAE9
0x18001c7c1  mov     rsi, [rbp+57h+bufptr]
0x18001c7c5  test    rsi, rsi
0x18001c7c8  jz      loc_18001CA64
0x18001c7ce  mov     r12d, edi
0x18001c7d1  cmp     [rbp+57h+arg_8], edi
0x18001c7d4  jbe     loc_18001CA64
0x18001c7da  test    rsi, rsi
0x18001c7dd  jz      loc_18001CA60
0x18001c7e3  mov     rcx, [rsi+50h]; String1
0x18001c7e7  test    rcx, rcx
0x18001c7ea  jz      loc_18001CA4C
0x18001c7f0  lea     rdx, a2d0cb8b424694c; "{2D0CB8B4-2469-4C46-A0FC-F09CAF1FF0CD}"
0x18001c7f7  call    wcscmp_0
0x18001c7fc  test    eax, eax
0x18001c7fe  jnz     loc_18001CA4C
0x18001c804  mov     rdi, [rsi]
0x18001c807  xor     eax, eax
0x18001c809  mov     ebx, eax
0x18001c80b  mov     [rbp+57h+var_50], rax
0x18001c80f  mov     [rbp+57h+var_88], rax
0x18001c813  lea     r9, [rbp+57h+var_88]; bufptr
0x18001c817  lea     r8d, [rax+17h]; level
0x18001c81b  mov     rdx, rdi; username
0x18001c81e  xor     ecx, ecx; servername
0x18001c820  call    cs:__imp_NetUserGetInfo
0x18001c826  xor     edx, edx
0x18001c828  test    eax, eax
0x18001c82a  jz      short loc_18001C864
0x18001c82c  mov     rcx, [rbp+5Fh]; this
0x18001c830  mov     dword ptr [rsp+0D0h+totalentries], eax
0x18001c834  mov     [rsp+0D0h+entriesread], rdi; char *
0x18001c839  lea     rax, aUserNameLsStat; "user name: %ls, status: %d"
0x18001c840  mov     [rsp+0D0h+phkResult], rax; int
0x18001c845  mov     r9d, 80004005h; char *
0x18001c84b  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001c852  mov     edx, 38Ch; void *
0x18001c857  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001c85c  nop
0x18001c85d  xor     edi, edi
0x18001c85f  jmp     loc_18001C96A
0x18001c864  mov     rcx, [rbp+57h+var_88]
0x18001c868  mov     [rbp+57h+StringSid], rdx
0x18001c86c  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18001c870  mov     rcx, [rcx+20h]; Sid
0x18001c874  call    cs:__imp_ConvertSidToStringSidW
0x18001c87a  xor     edx, edx
0x18001c87c  test    eax, eax
0x18001c87e  jnz     short loc_18001C8C5
0x18001c880  mov     rcx, [rbp+5Fh]; this
0x18001c884  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001c88b  mov     edx, 390h; void *
0x18001c890  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c895  mov     edi, eax
0x18001c897  mov     rcx, [rbp+57h+StringSid]; hMem
0x18001c89b  test    rcx, rcx
0x18001c89e  jz      short loc_18001C8A7
0x18001c8a0  call    cs:__imp_LocalFree
0x18001c8a6  nop
0x18001c8a7  mov     rcx, [rbp+57h+var_88]; Buffer
0x18001c8ab  test    rcx, rcx
0x18001c8ae  jz      short loc_18001C8B6
0x18001c8b0  call    cs:__imp_NetApiBufferFree
0x18001c8b6  test    edi, edi
0x18001c8b8  jns     loc_18001C9A9
0x18001c8be  xor     edi, edi
0x18001c8c0  jmp     loc_18001C97A
0x18001c8c5  mov     rcx, [rbp+57h+StringSid]
0x18001c8c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c8cd  inc     rax
0x18001c8d0  cmp     [rcx+rax*2], dx
0x18001c8d4  jnz     short loc_18001C8CD
0x18001c8d6  lea     rdi, [rax+1]
0x18001c8da  mov     [rbp+57h+var_58], rdx
0x18001c8de  lea     rdx, [rbp+57h+var_58]
0x18001c8e2  mov     rcx, rdi
0x18001c8e5  call    CflApiNew__AllocBuffer_unsigned_short_
0x18001c8ea  test    eax, eax
0x18001c8ec  jns     short loc_18001C91A
0x18001c8ee  mov     rcx, [rbp+5Fh]; this
0x18001c8f2  mov     r9d, eax; char *
0x18001c8f5  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001c8fc  mov     edx, 395h; void *
0x18001c901  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c906  nop
0x18001c907  mov     rcx, [rbp+57h+var_58]; hMem
0x18001c90b  xor     edi, edi
0x18001c90d  test    rcx, rcx
0x18001c910  jz      short loc_18001C918
0x18001c912  call    CflFreeBuffer
0x18001c917  nop
0x18001c918  jmp     short loc_18001C95A
0x18001c91a  mov     r8, [rbp+57h+StringSid]; unsigned __int16 *
0x18001c91e  mov     rdx, rdi; unsigned __int64
0x18001c921  mov     rdi, [rbp+57h+var_58]
0x18001c925  mov     rcx, rdi; unsigned __int16 *
0x18001c928  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c92d  test    eax, eax
0x18001c92f  jns     short loc_18001C97F
0x18001c931  mov     rcx, [rbp+5Fh]; this
0x18001c935  mov     r9d, eax; char *
0x18001c938  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001c93f  mov     edx, 396h; void *
  ... truncated ...
```
