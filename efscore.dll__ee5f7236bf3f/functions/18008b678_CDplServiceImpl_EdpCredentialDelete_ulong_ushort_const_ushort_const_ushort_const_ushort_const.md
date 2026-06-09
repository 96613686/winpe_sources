# CDplServiceImpl::EdpCredentialDelete(ulong,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18008b678`
- end: `0x18008c1f9`
- name: `?EdpCredentialDelete@CDplServiceImpl@@AEAAJKPEBG000@Z`
- size: `2945`
- prototype: `int(CDplServiceImpl *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180081634`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800861ec`
- `0x180087d4c`
- `0x180087d84`
- `0x180088cf8`
- `0x18008b678`
- `0x18008d024`
- `0x18008fb78`
- `0x1800954e4`
- `0x1800991bc`
- `0x180099274`
- `0x1800ac870`
- `0x1800ad2d0`
- `0x1800af128`
- `0x1800b5a5c`
- `0x1800bb988`
- `0x1800d5af8`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b8e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b8e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008b8db`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008b8db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008c185`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008c193`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008c1a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008c185`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008c193`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008c1a1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008b9eb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008b9eb`
- `ntdll!RtlPublishWnfStateData` at `0x18008c0a6`
- `ntdll!RtlPublishWnfStateData` at `0x18008c0a6`
- `ntdll!RtlNtStatusToDosError` at `0x18008c0b4`
- `ntdll!RtlNtStatusToDosError` at `0x18008c0b4`

## string_xrefs

- `0x18008b81f`: `Can't delete consumer credentials`
- `0x18008bad4`: `Revoking matching uses user SID`
- `0x18008be47`: `No credentials found to delete`
- `0x18008bf29`: `No credentials found to delete`
- `0x18008bf46`: `Found credentials to delete`
- `0x18008c063`: `Publishing revocation WNF event about deleted credentials`

## pseudocode

```c
__int64 __fastcall CDplServiceImpl::EdpCredentialDelete(
        CDplServiceImpl *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        const unsigned __int16 *lpString1,
        unsigned __int16 *a6)
{
  bool v9; // di
  unsigned __int64 v10; // r13
  PSID v11; // rsi
  PSID *v12; // r12
  int v13; // ecx
  int v14; // edx
  int User; // ebx
  int v16; // esi
  BOOL v17; // ecx
  __int64 *v18; // rdx
  int v19; // r8d
  int v20; // eax
  signed int LastError; // eax
  int v22; // ecx
  int v23; // eax
  PSID v24; // r15
  unsigned __int16 *v25; // rbx
  const unsigned __int16 *v26; // rsi
  unsigned __int16 *v27; // r15
  int v28; // ecx
  int v29; // ecx
  int v30; // eax
  __int64 v31; // rcx
  int v32; // ecx
  int v33; // ecx
  __int64 v34; // rcx
  unsigned __int64 v35; // rax
  int v36; // eax
  int v37; // ecx
  NTSTATUS v38; // eax
  NTSTATUS v39; // edi
  int v40; // eax
  struct CDplAccount **v41; // rcx
  struct CDplAccount *v42; // rax
  char bIgnoreCase; // [rsp+28h] [rbp-79h]
  char bIgnoreCasea; // [rsp+28h] [rbp-79h]
  PSID pSid2; // [rsp+68h] [rbp-39h] BYREF
  PSID pSid1; // [rsp+70h] [rbp-31h] BYREF
  unsigned __int64 v48; // [rsp+78h] [rbp-29h] BYREF
  struct CDplAccount **v49; // [rsp+80h] [rbp-21h] BYREF
  int v50; // [rsp+88h] [rbp-19h] BYREF
  int v51; // [rsp+8Ch] [rbp-15h]
  LPCWCH lpString2; // [rsp+90h] [rbp-11h] BYREF
  unsigned __int16 *v53; // [rsp+98h] [rbp-9h] BYREF
  unsigned __int16 *v54; // [rsp+A0h] [rbp-1h] BYREF
  struct CDplUser *v55; // [rsp+A8h] [rbp+7h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp+Fh] BYREF
  int v58; // [rsp+100h] [rbp+5Fh] BYREF
  unsigned __int16 *v59; // [rsp+110h] [rbp+6Fh]

  v59 = a4;
  v50 = 1;
  lpString2 = 0;
  v54 = 0;
  v53 = 0;
  v49 = 0;
  v48 = 0;
  pSid1 = 0;
  v9 = 0;
  pSid2 = 0;
  v10 = 0;
  hMem = 0;
  v11 = 0;
  v55 = 0;
  v12 = 0;
  v58 = 0;
  v51 = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 37, 76);
  if ( a2 > 0xF )
  {
    bIgnoreCase = 84;
    goto LABEL_72;
  }
  if ( !a3 || (a2 & 1) == 0 )
  {
    bIgnoreCase = 96;
LABEL_72:
    User = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 37, bIgnoreCase);
    goto LABEL_74;
  }
  v13 = a6 != 0 ? -1 : -9;
  v14 = a2 & v13 & (a4 != 0 ? -1 : -3);
  if ( !v14 )
  {
    User = 1;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 37, 122);
LABEL_74:
    v24 = pSid2;
    goto LABEL_75;
  }
  if ( (v14 & 1) == 0 )
  {
    User = -2147418113;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 37, 132);
    goto LABEL_74;
  }
  v16 = v14 & 4;
  v9 = v16 != 0;
  if ( (v14 & 8) == 0 )
  {
    v27 = 0;
    if ( (v14 & 4) != 0 )
    {
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)L"Revoking matching uses AppCallerID",
        0,
        37,
        242);
      v26 = lpString1;
    }
    else
    {
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)L"Revoking will match all AppCallerIDs",
        0,
        37,
        248);
      v26 = (const unsigned __int16 *)-1LL;
    }
    v25 = a3;
    goto LABEL_38;
  }
  fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 148);
  User = CDplServiceImpl::EdpCredentialIdParse(this, a6, (unsigned __int16 **)&lpString2, &v54, &v53, &v58);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              User,
              37,
              148) < 0 )
  {
LABEL_14:
    v11 = pSid1;
    goto LABEL_74;
  }
  if ( v58 )
  {
    fnEfsLogTrace1String1Dword(
      g_hPublisher,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)L"Can't delete consumer credentials",
      0,
      37,
      157);
    bIgnoreCasea = -98;
LABEL_12:
    User = 1;
    v18 = EFS_TRACE_STATUS;
    v19 = 1;
LABEL_13:
    fnEfsLogTrace1(g_hPublisher, (_DWORD)v18, v19, 37, bIgnoreCasea);
    goto LABEL_14;
  }
  if ( v16 )
  {
    v17 = lpString1 != 0;
    if ( v17 != (lpString2 != 0) )
    {
      bIgnoreCasea = -79;
LABEL_18:
      User = -2147024809;
      v19 = -2147024809;
      goto LABEL_19;
    }
    if ( lpString1 && lpString2 )
    {
      v20 = CompareStringOrdinal(lpString1, -1, lpString2, -1, 1);
      if ( !v20 )
      {
        LastError = GetLastError();
        User = LastError;
        if ( LastError > 0 )
          User = (unsigned __int16)LastError | 0x80070000;
        bIgnoreCasea = -59;
        v19 = User;
        goto LABEL_19;
      }
      if ( v20 != 2 )
      {
        bIgnoreCasea = -54;
        goto LABEL_18;
      }
    }
  }
  fnEfsLogTrace1Strings(v17, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 216);
  User = CDplServiceImpl::CheckConvertStringSidToSid(a3, &pSid1);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              User,
              37,
              216) < 0 )
    goto LABEL_14;
  fnEfsLogTrace1Strings(v22, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 218);
  User = CDplServiceImpl::CheckConvertStringSidToSid(v53, &pSid2);
  v23 = fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
          (unsigned int)&sourceString,
          User,
          37,
          218);
  v24 = pSid2;
  v11 = pSid1;
  if ( v23 >= 0 )
  {
    if ( !EqualSid(pSid1, pSid2) )
    {
      User = -2147024809;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 37, 222);
      goto LABEL_75;
    }
    fnEfsLogTrace1String1Dword(
      g_hPublisher,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)L"Revoking matching uses credential ID",
      0,
      37,
      234);
    v25 = v53;
    v26 = lpString2;
    v27 = v54;
    if ( !v53 )
    {
LABEL_39:
      v51 = CDplServiceImpl::SvcLock(this);
      fnEfsLogTrace1Strings(v29, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 11);
      User = CDplServiceImpl::FindUser(this, a3, 0, &v55);
      v30 = fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              User,
              37,
              11);
      v12 = (PSID *)v55;
      if ( v30 < 0 )
        goto LABEL_14;
      if ( !v55 )
      {
        if ( User != 1 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v31);
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)L"User is not known",
          0,
          37,
          20);
        bIgnoreCasea = 21;
        goto LABEL_12;
      }
      fnEfsLogTrace1Strings(v31, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 29);
      User = EdpCredSvcShouldCheckCaller(&v50);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  User,
                  37,
                  29) < 0 )
        goto LABEL_14;
      if ( v50 )
      {
        fnEfsLogTrace1Strings(v32, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 33);
        User = CDplUser::CheckCaller(v12);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    User,
                    37,
                    33) < 0 )
          goto LABEL_14;
      }
      fnEfsLogTrace1Strings(v32, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 40);
      User = CDplUser::LoadDplAccountsAndPolicies((CDplUser *)v12, v27);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  User,
                  37,
                  40) < 0 )
        goto LABEL_14;
      fnEfsLogTrace1Strings(v33, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 56);
      User = CDplUser::EnumRefEnterpriseCredentials((CDplUser *)v12, v59, v26, v27, 0xFFFFFFFF, 0, 0, &v49, 0, 0, &v48);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  User,
                  37,
                  56) < 0 )
        goto LABEL_14;
      if ( User == 1 )
      {
        if ( v48 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v34);
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)L"No credentials found to delete",
          0,
          37,
          65);
        goto LABEL_14;
      }
      if ( User )
        MicrosoftTelemetryAssertTriggeredNoArgs(v34);
      if ( v48 )
      {
        if ( v49 )
        {
          CDplServiceImpl::PublishCredentialsUpdatingNotification(this);
          if ( v48 )
          {
            do
            {
              v35 = v10++;
              v36 = CDplUser::DeleteDplAccount(v12, v49[v35], 1);
              if ( v36 < 0 && User >= 0 )
              {
                User = v36;
                fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, v36, 37, 103);
              }
            }
            while ( v10 < v48 );
          }
          if ( User < 0 || v10 )
          {
            fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
              (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
              (unsigned int)L"Found credentials to delete",
              v10,
              37,
              115);
          }
          else
          {
            fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 37, 110);
            fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
              (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
              (unsigned int)L"No credentials found to delete",
              0,
              37,
              111);
          }
          fnEfsLogTrace1Strings(v37, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 118);
          User = CDplUser::Save((CDplUser *)v12);
          fnEfsLogTrace1String1Dword(
            g_hPublisher,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
            (unsigned int)&sourceString,
            User,
            37,
            118);
          goto LABEL_14;
        }
        bIgnoreCasea = 76;
      }
      else
      {
        bIgnoreCasea = 75;
      }
      User = -2147418113;
      v19 = -2147418113;
LABEL_19:
      v18 = EFS_TRACE_ERROR;
      goto LABEL_13;
    }
LABEL_38:
    fnEfsLogTrace1String1Dword(
      g_hPublisher,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)L"Revoking matching uses user SID",
      0,
      37,
      4);
    fnEfsLogTrace1Strings(v28, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 6);
    User = CDplServiceImpl::CheckConvertStringSidToSid(v25, &hMem);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                User,
                37,
                6) < 0 )
      goto LABEL_14;
    goto LABEL_39;
  }
LABEL_75:
  ReleaseIf<CDplUser>(v12);
  CDplServiceImpl::SvcUnlockIf(this, v51);
  if ( v10 )
  {
    if ( !v9 )
    {
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)L"Publishing revocation WNF event about deleted credentials",
        v10,
        37,
        135);
      v38 = RtlPublishWnfStateData(WNF_EDP_IDENTITY_REVOKED, 0, 0, 0, 0);
      v39 = v38;
      if ( v38 < 0 )
      {
        v40 = RtlNtStatusToDosError(v38);
        if ( !v40 || v40 == 317 )
        {
          v40 = v39 | 0x10000000;
        }
        else if ( v40 > 0 )
        {
          v40 = (unsigned __int16)v40 | 0x80070000;
        }
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v40, 37, 146);
      }
    }
  }
  if ( lpString2 )
    DplibMemFree((void *)lpString2);
  lpString2 = 0;
  if ( v54 )
    DplibMemFree(v54);
  v54 = 0;
  if ( v53 )
    DplibMemFree(v53);
  v41 = v49;
  v53 = 0;
  if ( v49 )
  {
    while ( v48 )
    {
      v42 = (struct CDplAccount *)ReleaseIf<CDplAccount>(v41[--v48]);
      v49[v48] = v42;
      v41 = v49;
    }
    v48 = -1;
    if ( v41 )
      DplibMemFree(v41);
    v49 = 0;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v11 )
    LocalFree(v11);
  if ( v24 )
    LocalFree(v24);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    User,
    37,
    184);
  return (unsigned int)User;
}

```

## disassembly

```asm
0x18008b678  mov     rax, rsp
0x18008b67b  mov     [rax+18h], rbx
0x18008b67f  mov     [rax+20h], r9
0x18008b683  mov     [rax+8], rcx
0x18008b687  push    rbp
0x18008b688  push    rsi
0x18008b689  push    rdi
0x18008b68a  push    r12
0x18008b68c  push    r13
0x18008b68e  push    r14
0x18008b690  push    r15
0x18008b692  lea     rbp, [rax-4Fh]
0x18008b696  sub     rsp, 0B0h
0x18008b69d  xor     eax, eax
0x18008b69f  mov     [rbp+47h+var_60], 1
0x18008b6a6  mov     r15, r9
0x18008b6a9  mov     [rbp+47h+lpString2], rax
0x18008b6ad  mov     r14, r8
0x18008b6b0  mov     [rbp+47h+var_48], rax
0x18008b6b4  mov     ebx, edx
0x18008b6b6  mov     [rbp+47h+var_50], rax
0x18008b6ba  lea     r9d, [rax+25h]
0x18008b6be  mov     [rbp+47h+var_68], rax
0x18008b6c2  lea     r8, sourceString
0x18008b6c9  mov     [rbp+47h+var_70], rax
0x18008b6cd  lea     rdx, EFS_TRACE_ENTER_EVENT
0x18008b6d4  mov     [rbp+47h+pSid1], rax
0x18008b6d8  mov     dil, al
0x18008b6db  mov     [rbp+47h+pSid2], rax
0x18008b6df  mov     r13d, eax
0x18008b6e2  mov     [rbp+47h+hMem], rax
0x18008b6e6  mov     esi, eax
0x18008b6e8  mov     [rbp+47h+var_40], rax
0x18008b6ec  mov     r12d, eax
0x18008b6ef  mov     [rbp+47h+arg_8], eax
0x18008b6f2  mov     [rbp+47h+var_5C], eax
0x18008b6f5  mov     [rsp+0E0h+bIgnoreCase], 114Ch
0x18008b6fd  call    fnEfsLogTrace1Strings
0x18008b702  lea     r10, EFS_TRACE_MSG_DWORD_EVENT
0x18008b709  lea     r11, EFS_TRACE_ERROR
0x18008b710  cmp     ebx, 0Fh
0x18008b713  jbe     short loc_18008B722
0x18008b715  mov     [rsp+0E0h+bIgnoreCase], 1154h
0x18008b71d  jmp     loc_18008C00F
0x18008b722  test    r14, r14
0x18008b725  jz      loc_18008C007
0x18008b72b  test    bl, 1
0x18008b72e  jz      loc_18008C007
0x18008b734  mov     rax, r15
0x18008b737  neg     rax
0x18008b73a  mov     rax, [rbp+47h+arg_28]
0x18008b73e  sbb     edx, edx
0x18008b740  and     edx, 2
0x18008b743  add     edx, 0FFFFFFFDh
0x18008b746  neg     rax
0x18008b749  sbb     ecx, ecx
0x18008b74b  and     ecx, 8
0x18008b74e  add     ecx, 0FFFFFFF7h
0x18008b751  and     edx, ecx
0x18008b753  and     edx, ebx
0x18008b755  jnz     short loc_18008B771
0x18008b757  lea     ebx, [rdx+1]
0x18008b75a  mov     [rsp+0E0h+bIgnoreCase], 117Ah
0x18008b762  mov     r8d, ebx
0x18008b765  lea     rdx, EFS_TRACE_STATUS
0x18008b76c  jmp     loc_18008C01D
0x18008b771  test    dl, 1
0x18008b774  jz      loc_18008BFF2
0x18008b77a  mov     esi, edx
0x18008b77c  and     esi, 4
0x18008b77f  setnz   dil
0x18008b783  test    dl, 8
0x18008b786  jz      loc_18008BA6A
0x18008b78c  mov     r15d, 1194h
0x18008b792  lea     r8, sourceString
0x18008b799  mov     r9d, 25h ; '%'
0x18008b79f  mov     [rsp+0E0h+bIgnoreCase], r15d
0x18008b7a4  lea     rdx, EFS_TRACE_START_EVENT
0x18008b7ab  call    fnEfsLogTrace1Strings
0x18008b7b0  mov     rdx, [rbp+47h+arg_28]; unsigned __int16 *
0x18008b7b4  lea     rax, [rbp+47h+arg_8]
0x18008b7b8  mov     rcx, [rbp+47h+arg_0]; this
0x18008b7bc  lea     r9, [rbp+47h+var_48]; unsigned __int16 **
0x18008b7c0  mov     [rsp+0E0h+var_B8], rax; int *
0x18008b7c5  lea     r8, [rbp+47h+lpString2]; unsigned __int16 **
0x18008b7c9  lea     rax, [rbp+47h+var_50]
0x18008b7cd  mov     qword ptr [rsp+0E0h+bIgnoreCase], rax; unsigned __int16 **
0x18008b7d2  call    ?EdpCredentialIdParse@CDplServiceImpl@@AEAAJPEBGPEAPEAG11PEAH@Z; CDplServiceImpl::EdpCredentialIdParse(ushort const *,ushort * *,ushort * *,ushort * *,int *)
0x18008b7d7  mov     rcx, cs:g_hPublisher
0x18008b7de  lea     r9, sourceString
0x18008b7e5  mov     [rsp+0E0h+var_B0], r15d
0x18008b7ea  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18008b7f1  mov     r15d, 25h ; '%'
0x18008b7f7  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18008b7fe  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x18008b803  mov     ebx, eax
0x18008b805  mov     [rsp+0E0h+bIgnoreCase], eax
0x18008b809  call    fnEfsLogTrace1String1Dword
0x18008b80e  test    eax, eax
0x18008b810  js      short loc_18008B871
0x18008b812  cmp     [rbp+47h+arg_8], r12d
0x18008b816  jz      short loc_18008B87A
0x18008b818  mov     rcx, cs:g_hPublisher
0x18008b81f  lea     r9, aCanTDeleteCons; "Can't delete consumer credentials"
0x18008b826  mov     [rsp+0E0h+var_B0], 119Dh
0x18008b82e  lea     r8, EFS_TRACE_MSG_DWORD_EVENT
0x18008b835  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x18008b83a  lea     rdx, EFS_TRACE_MSG_DWORD_EVENT
0x18008b841  mov     [rsp+0E0h+bIgnoreCase], r12d
0x18008b846  call    fnEfsLogTrace1String1Dword
0x18008b84b  mov     r9d, r15d
0x18008b84e  mov     [rsp+0E0h+bIgnoreCase], 119Eh
0x18008b856  mov     ebx, 1
0x18008b85b  lea     rdx, EFS_TRACE_STATUS
0x18008b862  mov     r8d, ebx
0x18008b865  mov     rcx, cs:g_hPublisher
0x18008b86c  call    fnEfsLogTrace1
0x18008b871  mov     rsi, [rbp+47h+pSid1]
0x18008b875  jmp     loc_18008C02F
0x18008b87a  test    esi, esi
0x18008b87c  jz      loc_18008B916
0x18008b882  mov     r10, [rbp+47h+lpString1]
0x18008b886  xor     ecx, ecx
0x18008b888  mov     r8, [rbp+47h+lpString2]; lpString2
0x18008b88c  test    r10, r10
0x18008b88f  setnz   cl
0x18008b892  xor     eax, eax
0x18008b894  test    r8, r8
0x18008b897  setnz   al
0x18008b89a  cmp     ecx, eax
0x18008b89c  jz      short loc_18008B8BD
0x18008b89e  mov     [rsp+0E0h+bIgnoreCase], 11B1h
0x18008b8a6  mov     ebx, 80070057h
0x18008b8ab  mov     r8d, 80070057h
0x18008b8b1  mov     r9d, r15d
0x18008b8b4  lea     rdx, EFS_TRACE_ERROR
0x18008b8bb  jmp     short loc_18008B865
0x18008b8bd  test    r10, r10
0x18008b8c0  jz      short loc_18008B916
0x18008b8c2  test    r8, r8
0x18008b8c5  jz      short loc_18008B916
0x18008b8c7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008b8cb  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x18008b8d3  mov     r9d, esi; cchCount2
0x18008b8d6  mov     edx, esi; cchCount1
0x18008b8d8  mov     rcx, r10; lpString1
0x18008b8db  call    cs:__imp_CompareStringOrdinal
0x18008b8e1  test    eax, eax
0x18008b8e3  jnz     short loc_18008B907
0x18008b8e5  call    cs:__imp_GetLastError
0x18008b8eb  mov     ebx, eax
0x18008b8ed  test    eax, eax
0x18008b8ef  jle     short loc_18008B8FA
0x18008b8f1  movzx   ebx, ax
0x18008b8f4  or      ebx, 80070000h
0x18008b8fa  mov     [rsp+0E0h+bIgnoreCase], 11C5h
0x18008b902  mov     r8d, ebx
0x18008b905  jmp     short loc_18008B8B1
0x18008b907  cmp     eax, 2
0x18008b90a  jz      short loc_18008B916
0x18008b90c  mov     [rsp+0E0h+bIgnoreCase], 11CAh
0x18008b914  jmp     short loc_18008B8A6
0x18008b916  mov     esi, 11D8h
0x18008b91b  lea     r8, sourceString
0x18008b922  mov     r9d, r15d
0x18008b925  mov     [rsp+0E0h+bIgnoreCase], esi
0x18008b929  lea     rdx, EFS_TRACE_START_EVENT
0x18008b930  call    fnEfsLogTrace1Strings
0x18008b935  lea     rdx, [rbp+47h+pSid1]; void **
0x18008b939  mov     rcx, r14; unsigned __int16 *
0x18008b93c  call    ?CheckConvertStringSidToSid@CDplServiceImpl@@CAJPEBGPEAPEAX@Z; CDplServiceImpl::CheckConvertStringSidToSid(ushort const *,void * *)
0x18008b941  mov     rcx, cs:g_hPublisher
0x18008b948  lea     r9, sourceString
0x18008b94f  mov     [rsp+0E0h+var_B0], esi
0x18008b953  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18008b95a  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x18008b95f  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18008b966  mov     [rsp+0E0h+bIgnoreCase], eax
0x18008b96a  mov     ebx, eax
0x18008b96c  call    fnEfsLogTrace1String1Dword
0x18008b971  test    eax, eax
0x18008b973  js      loc_18008B871
0x18008b979  mov     esi, 11DAh
0x18008b97e  lea     r8, sourceString
0x18008b985  mov     r9d, r15d
0x18008b988  mov     [rsp+0E0h+bIgnoreCase], esi
0x18008b98c  lea     rdx, EFS_TRACE_START_EVENT
0x18008b993  call    fnEfsLogTrace1Strings
0x18008b998  mov     rcx, [rbp+47h+var_50]; unsigned __int16 *
0x18008b99c  lea     rdx, [rbp+47h+pSid2]; void **
0x18008b9a0  call    ?CheckConvertStringSidToSid@CDplServiceImpl@@CAJPEBGPEAPEAX@Z; CDplServiceImpl::CheckConvertStringSidToSid(ushort const *,void * *)
0x18008b9a5  mov     rcx, cs:g_hPublisher
0x18008b9ac  lea     r9, sourceString
0x18008b9b3  mov     [rsp+0E0h+var_B0], esi
0x18008b9b7  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18008b9be  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x18008b9c3  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18008b9ca  mov     [rsp+0E0h+bIgnoreCase], eax
0x18008b9ce  mov     ebx, eax
0x18008b9d0  call    fnEfsLogTrace1String1Dword
0x18008b9d5  mov     r15, [rbp+47h+pSid2]
0x18008b9d9  mov     rsi, [rbp+47h+pSid1]
0x18008b9dd  test    eax, eax
0x18008b9df  js      loc_18008C033
0x18008b9e5  mov     rdx, r15; pSid2
0x18008b9e8  mov     rcx, rsi; pSid1
0x18008b9eb  call    cs:__imp_EqualSid
0x18008b9f1  mov     rcx, cs:g_hPublisher
0x18008b9f8  test    eax, eax
0x18008b9fa  jnz     short loc_18008BA24
0x18008b9fc  lea     r9d, [rax+25h]
0x18008ba00  mov     [rsp+0E0h+bIgnoreCase], 11DEh
0x18008ba08  mov     r8d, 80070057h
0x18008ba0e  lea     rdx, EFS_TRACE_ERROR
0x18008ba15  mov     ebx, 80070057h
0x18008ba1a  call    fnEfsLogTrace1
0x18008ba1f  jmp     loc_18008C033
0x18008ba24  mov     [rsp+0E0h+var_B0], 11EAh
0x18008ba2c  lea     r9, aRevokingMatchi_0; "Revoking matching uses credential ID"
0x18008ba33  mov     dword ptr [rsp+0E0h+var_B8], 25h ; '%'
0x18008ba3b  lea     r8, EFS_TRACE_MSG_DWORD_EVENT
0x18008ba42  lea     rdx, EFS_TRACE_MSG_DWORD_EVENT
0x18008ba49  mov     [rsp+0E0h+bIgnoreCase], r12d
0x18008ba4e  call    fnEfsLogTrace1String1Dword
0x18008ba53  mov     rbx, [rbp+47h+var_50]
0x18008ba57  mov     rsi, [rbp+47h+lpString2]
0x18008ba5b  mov     r15, [rbp+47h+var_48]
0x18008ba5f  test    rbx, rbx
0x18008ba62  jz      loc_18008BB6F
0x18008ba68  jmp     short loc_18008BACD
0x18008ba6a  mov     rcx, cs:g_hPublisher
0x18008ba71  xor     r15d, r15d
0x18008ba74  mov     r8, r10
0x18008ba77  mov     rdx, r10
0x18008ba7a  test    esi, esi
0x18008ba7c  jz      short loc_18008BAA5
0x18008ba7e  mov     [rsp+0E0h+var_B0], 11F2h
0x18008ba86  lea     r9, aRevokingMatchi; "Revoking matching uses AppCallerID"
0x18008ba8d  mov     dword ptr [rsp+0E0h+var_B8], 25h ; '%'
0x18008ba95  mov     [rsp+0E0h+bIgnoreCase], r12d
0x18008ba9a  call    fnEfsLogTrace1String1Dword
0x18008ba9f  mov     rsi, [rbp+47h+lpString1]
0x18008baa3  jmp     short loc_18008BACA
0x18008baa5  mov     [rsp+0E0h+var_B0], 11F8h
0x18008baad  lea     r9, aRevokingWillMa; "Revoking will match all AppCallerIDs"
0x18008bab4  mov     dword ptr [rsp+0E0h+var_B8], 25h ; '%'
0x18008babc  mov     [rsp+0E0h+bIgnoreCase], r12d
0x18008bac1  call    fnEfsLogTrace1String1Dword
0x18008bac6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008baca  mov     rbx, r14
0x18008bacd  mov     rcx, cs:g_hPublisher
0x18008bad4  lea     r9, aRevokingMatchi_1; "Revoking matching uses user SID"
0x18008badb  mov     [rsp+0E0h+var_B0], 1204h
0x18008bae3  lea     r8, EFS_TRACE_MSG_DWORD_EVENT
0x18008baea  mov     dword ptr [rsp+0E0h+var_B8], 25h ; '%'
0x18008baf2  lea     rdx, EFS_TRACE_MSG_DWORD_EVENT
0x18008baf9  mov     [rsp+0E0h+bIgnoreCase], r12d
0x18008bafe  call    fnEfsLogTrace1String1Dword
0x18008bb03  mov     r9d, 25h ; '%'
0x18008bb09  mov     [rsp+0E0h+bIgnoreCase], 1206h
0x18008bb11  lea     r8, sourceString
0x18008bb18  lea     rdx, EFS_TRACE_START_EVENT
0x18008bb1f  call    fnEfsLogTrace1Strings
0x18008bb24  lea     rdx, [rbp+47h+hMem]; void **
0x18008bb28  mov     rcx, rbx; unsigned __int16 *
0x18008bb2b  call    ?CheckConvertStringSidToSid@CDplServiceImpl@@CAJPEBGPEAPEAX@Z; CDplServiceImpl::CheckConvertStringSidToSid(ushort const *,void * *)
0x18008bb30  mov     rcx, cs:g_hPublisher
0x18008bb37  lea     r9, sourceString
0x18008bb3e  mov     [rsp+0E0h+var_B0], 1206h
0x18008bb46  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18008bb4d  mov     dword ptr [rsp+0E0h+var_B8], 25h ; '%'
0x18008bb55  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18008bb5c  mov     [rsp+0E0h+bIgnoreCase], eax
0x18008bb60  mov     ebx, eax
0x18008bb62  call    fnEfsLogTrace1String1Dword
0x18008bb67  test    eax, eax
0x18008bb69  js      loc_18008B871
0x18008bb6f  mov     rcx, [rbp+47h+arg_0]; this
0x18008bb73  call    ?SvcLock@CDplServiceImpl@@AEAAHXZ; CDplServiceImpl::SvcLock(void)
0x18008bb78  mov     r12d, 120Bh
0x18008bb7e  mov     [rbp+47h+var_5C], eax
0x18008bb81  mov     r9d, 25h ; '%'
0x18008bb87  mov     [rsp+0E0h+bIgnoreCase], r12d
0x18008bb8c  lea     r8, sourceString
0x18008bb93  lea     rdx, EFS_TRACE_START_EVENT
0x18008bb9a  call    fnEfsLogTrace1Strings
0x18008bb9f  mov     rcx, [rbp+47h+arg_0]; this
0x18008bba3  lea     r9, [rbp+47h+var_40]; struct CDplUser **
0x18008bba7  xor     r8d, r8d; int
0x18008bbaa  mov     rdx, r14; unsigned __int16 *
0x18008bbad  call    ?FindUser@CDplServiceImpl@@AEAAJPEBGHPEAPEAVCDplUser@@@Z; CDplServiceImpl::FindUser(ushort const *,int,CDplUser * *)
0x18008bbb2  mov     rcx, cs:g_hPublisher
0x18008bbb9  lea     r9, sourceString
0x18008bbc0  mov     [rsp+0E0h+var_B0], r12d
0x18008bbc5  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18008bbcc  mov     dword ptr [rsp+0E0h+var_B8], 25h ; '%'
0x18008bbd4  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18008bbdb  mov     [rsp+0E0h+bIgnoreCase], eax
0x18008bbdf  mov     ebx, eax
0x18008bbe1  call    fnEfsLogTrace1String1Dword
  ... truncated ...
```
