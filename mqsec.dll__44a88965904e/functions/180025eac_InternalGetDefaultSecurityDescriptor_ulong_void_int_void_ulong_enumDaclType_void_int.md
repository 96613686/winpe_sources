# InternalGetDefaultSecurityDescriptor(ulong,void * *,int,void *,ulong,enumDaclType,void *,int)

- ea: `0x180025eac`
- end: `0x180026fd2`
- name: `?InternalGetDefaultSecurityDescriptor@@YAJKPEAPEAXHPEAXKW4enumDaclType@@1H@Z`
- size: `4390`
- prototype: `__int64 __fastcall(unsigned int, void **, __int64, __int64, int, unsigned int, PSID, int)`
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180027720`
- `0x180027800`
- `0x1800278e0`

## callees

- `0x180004074`
- `0x1800041cc`
- `0x1800049ac`
- `0x18000c39c`
- `0x18001722c`
- `0x180017430`
- `0x18001f3e0`
- `0x180020680`
- `0x180025698`
- `0x180025cd0`
- `0x180025eac`
- `0x180026fd8`
- `0x1800271b8`
- `0x180027438`
- `0x180027ba0`
- `0x180028104`
- `0x1800281a8`
- `0x1800288c0`

## import_xrefs

- `msvcrt!free` at `0x1800261af`
- `msvcrt!free` at `0x180026266`
- `msvcrt!free` at `0x180026275`
- `msvcrt!free` at `0x180026317`
- `msvcrt!free` at `0x180026321`
- `msvcrt!free` at `0x1800263d3`
- `msvcrt!free` at `0x1800263dd`
- `msvcrt!free` at `0x18002652a`
- `msvcrt!free` at `0x180026534`
- `msvcrt!free` at `0x180026753`
- `msvcrt!free` at `0x18002675d`
- `msvcrt!free` at `0x180026767`
- `msvcrt!free` at `0x1800267ec`
- `msvcrt!free` at `0x1800267f6`
- `msvcrt!free` at `0x1800268f8`
- `msvcrt!free` at `0x180026902`
- `msvcrt!free` at `0x18002690c`
- `msvcrt!free` at `0x180026a50`
- `msvcrt!free` at `0x180026a5a`
- `msvcrt!free` at `0x180026a64`
- `msvcrt!free` at `0x180026ba2`
- `msvcrt!free` at `0x180026bac`
- `msvcrt!free` at `0x180026bb6`
- `msvcrt!free` at `0x180026cee`
- `msvcrt!free` at `0x180026cf8`
- `msvcrt!free` at `0x180026d02`
- `msvcrt!free` at `0x180026e2e`
- `msvcrt!free` at `0x180026e38`
- `msvcrt!free` at `0x180026e42`
- `msvcrt!free` at `0x180026eed`
- `msvcrt!free` at `0x180026ef7`
- `msvcrt!free` at `0x180026f01`
- `msvcrt!free` at `0x180026f95`
- `msvcrt!free` at `0x180026f9f`
- `msvcrt!free` at `0x1800261af`
- `msvcrt!free` at `0x180026266`
- `msvcrt!free` at `0x180026275`
- `msvcrt!free` at `0x180026317`
- `msvcrt!free` at `0x180026321`
- `msvcrt!free` at `0x1800263d3`
- `msvcrt!free` at `0x1800263dd`
- `msvcrt!free` at `0x18002652a`
- `msvcrt!free` at `0x180026534`
- `msvcrt!free` at `0x180026753`
- `msvcrt!free` at `0x18002675d`
- `msvcrt!free` at `0x180026767`
- `msvcrt!free` at `0x1800267ec`
- `msvcrt!free` at `0x1800267f6`
- `msvcrt!free` at `0x1800268f8`
- `msvcrt!free` at `0x180026902`
- `msvcrt!free` at `0x18002690c`
- `msvcrt!free` at `0x180026a50`
- `msvcrt!free` at `0x180026a5a`
- `msvcrt!free` at `0x180026a64`
- `msvcrt!free` at `0x180026ba2`
- `msvcrt!free` at `0x180026bac`
- `msvcrt!free` at `0x180026bb6`
- `msvcrt!free` at `0x180026cee`
- `msvcrt!free` at `0x180026cf8`
- `msvcrt!free` at `0x180026d02`
- `msvcrt!free` at `0x180026e2e`
- `msvcrt!free` at `0x180026e38`
- `msvcrt!free` at `0x180026e42`
- `msvcrt!free` at `0x180026eed`
- `msvcrt!free` at `0x180026ef7`
- `msvcrt!free` at `0x180026f01`
- `msvcrt!free` at `0x180026f95`
- `msvcrt!free` at `0x180026f9f`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18002645f`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18002645f`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1800263ba`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1800263ba`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180025f50`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180025f50`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180026d56`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180026d56`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002681a`
- `ADVAPI32!AddAccessAllowedAce` at `0x180026978`
- `ADVAPI32!AddAccessAllowedAce` at `0x180026aca`
- `ADVAPI32!AddAccessAllowedAce` at `0x180026c16`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002681a`
- `ADVAPI32!AddAccessAllowedAce` at `0x180026978`
- `ADVAPI32!AddAccessAllowedAce` at `0x180026aca`
- `ADVAPI32!AddAccessAllowedAce` at `0x180026c16`
- `ADVAPI32!InitializeAcl` at `0x18002667b`
- `ADVAPI32!InitializeAcl` at `0x18002667b`
- `ADVAPI32!GetLengthSid` at `0x180026609`
- `ADVAPI32!GetLengthSid` at `0x180026621`
- `ADVAPI32!GetLengthSid` at `0x180026637`
- `ADVAPI32!GetLengthSid` at `0x180026654`
- `ADVAPI32!GetLengthSid` at `0x180026609`
- `ADVAPI32!GetLengthSid` at `0x180026621`
- `ADVAPI32!GetLengthSid` at `0x180026637`
- `ADVAPI32!GetLengthSid` at `0x180026654`
- `ADVAPI32!IsValidSid` at `0x180026391`
- `ADVAPI32!IsValidSid` at `0x180026439`
- `ADVAPI32!IsValidSid` at `0x180026391`
- `ADVAPI32!IsValidSid` at `0x180026439`
- `KERNEL32!GetLastError` at `0x18002646d`
- `KERNEL32!GetLastError` at `0x180026689`
- `KERNEL32!GetLastError` at `0x180026828`
- `KERNEL32!GetLastError` at `0x180026986`
- `KERNEL32!GetLastError` at `0x180026ad8`
- `KERNEL32!GetLastError` at `0x180026c24`
- `KERNEL32!GetLastError` at `0x180026d64`
- `KERNEL32!GetLastError` at `0x18002646d`
- `KERNEL32!GetLastError` at `0x180026689`
- `KERNEL32!GetLastError` at `0x180026828`
- `KERNEL32!GetLastError` at `0x180026986`
- `KERNEL32!GetLastError` at `0x180026ad8`
- `KERNEL32!GetLastError` at `0x180026c24`
- `KERNEL32!GetLastError` at `0x180026d64`

## pseudocode

```c
__int64 __fastcall InternalGetDefaultSecurityDescriptor(
        unsigned int a1,
        void **a2,
        __int64 a3,
        void *a4,
        int a5,
        unsigned int a6,
        PSID a7,
        int a8)
{
  int v9; // edi
  unsigned int v10; // r8d
  char *v11; // r13
  signed int AccessToken; // ebx
  unsigned int v14; // eax
  unsigned int v15; // eax
  void *v16; // r12
  PSID v17; // rcx
  struct _ACL *v18; // rbx
  PSID v19; // rcx
  unsigned int v20; // eax
  DWORD *AccessRights; // rax
  DWORD v22; // ebx
  DWORD v23; // esi
  int LastError; // esi
  unsigned int v25; // eax
  unsigned int v26; // eax
  char v27; // si
  unsigned int v28; // eax
  char v29; // si
  unsigned int v30; // eax
  char v31; // si
  unsigned int v32; // eax
  char v33; // si
  unsigned int v34; // eax
  unsigned int v35; // eax
  signed int SelfRelative; // esi
  unsigned int v37; // eax
  unsigned int v38; // eax
  signed int v39; // eax
  signed int v40; // eax
  DWORD dwAclRevision; // [rsp+60h] [rbp-E8h] BYREF
  DWORD v42; // [rsp+68h] [rbp-E0h] BYREF
  DWORD v43; // [rsp+70h] [rbp-D8h] BYREF
  PSID pSid; // [rsp+78h] [rbp-D0h] BYREF
  BOOL bOwnerDefaulted; // [rsp+80h] [rbp-C8h] BYREF
  BOOL bGroupDefaulted; // [rsp+84h] [rbp-C4h] BYREF
  DWORD AccessMask; // [rsp+88h] [rbp-C0h] BYREF
  PSID pGroup; // [rsp+90h] [rbp-B8h] BYREF
  HANDLE TokenHandle; // [rsp+98h] [rbp-B0h] BYREF
  int v50; // [rsp+A0h] [rbp-A8h] BYREF
  DWORD v51; // [rsp+A4h] [rbp-A4h]
  void *Block; // [rsp+A8h] [rbp-A0h] BYREF
  char *v53; // [rsp+B0h] [rbp-98h] BYREF
  PSID v54; // [rsp+B8h] [rbp-90h]
  struct _ACL *v55; // [rsp+C0h] [rbp-88h]
  _OWORD pSecurityDescriptor[2]; // [rsp+C8h] [rbp-80h] BYREF
  __int64 v57; // [rsp+E8h] [rbp-60h]
  const bad_win32_error *v58; // [rsp+F0h] [rbp-58h] BYREF
  const bad_win32_error *v59; // [rsp+F8h] [rbp-50h] BYREF
  _BYTE v60[32]; // [rsp+100h] [rbp-48h] BYREF

  v9 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    WPP_SF_ddDd(*((_QWORD *)WPP_GLOBAL_Control + 32), &WPP_GLOBAL_Control, a3, a1, a3, a5, a6);
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v57 = 0;
  v11 = 0;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    return LogGleAssertReturnHr(0x1F5u);
  pSid = 0;
  pGroup = 0;
  v50 = 0;
  bOwnerDefaulted = 0;
  bGroupDefaulted = 0;
  if ( a4 )
  {
    AccessToken = InternalCopyInfoFromArgumentDescriptor(
                    a4,
                    a6,
                    pSecurityDescriptor,
                    &pSid,
                    &pGroup,
                    &v50,
                    &bOwnerDefaulted,
                    &bGroupDefaulted);
    if ( AccessToken < 0 )
    {
      LOWORD(dwAclRevision) = 502;
      v42 = AccessToken;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v14 = mqwcslen(L"acssctrl/secdscrp");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v14 + 1),
          L"acssctrl/secdscrp",
          2,
          &dwAclRevision,
          4,
          &v42,
          0,
          0);
      }
      return (unsigned int)AccessToken;
    }
  }
  TokenHandle = 0;
  AccessToken = GetAccessToken(&TokenHandle, v9, v10, 0);
  if ( AccessToken )
  {
    LOWORD(dwAclRevision) = 503;
    v42 = AccessToken;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v15 = mqwcslen(L"acssctrl/secdscrp");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        2,
        2LL * (v15 + 1),
        L"acssctrl/secdscrp",
        2,
        &dwAclRevision,
        4,
        &v42,
        0,
        0);
    }
    if ( AccessToken > 0 )
      AccessToken = (unsigned __int16)AccessToken | 0x80070000;
    goto LABEL_148;
  }
  v16 = 0;
  Block = 0;
  v17 = pSid;
  if ( !pSid )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      InternalGetUserTokenBytes(TokenHandle, (char **)&Block);
      v16 = Block;
      v17 = *(PSID *)Block;
      pSid = *(PSID *)Block;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      {
        WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 32));
        v17 = pSid;
      }
      bOwnerDefaulted = 1;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &bad_win32_error `RTTI Type Descriptor', &v58) )
      {
        v39 = (*(__int64 (__fastcall **)(const bad_win32_error *))(*(_QWORD *)v58 + 16LL))(v58);
        if ( v39 > 0 )
          v39 = (unsigned __int16)v39 | 0x80070000;
        dwAclRevision = v39;
        if ( v39 < 0 )
          LogMsgHR(v39, (wchar_t *)L"acssctrl/secdscrp", 0x1F8u);
        __eh34_try_continuation(0, &bad_win32_error `RTTI Type Descriptor', &loc_1800261A7);
        free(Block);
LABEL_21:
        AccessToken = dwAclRevision;
LABEL_148:
        CHandle::~CHandle((CHandle *)&TokenHandle);
        return (unsigned int)AccessToken;
      }
    }
  }
  v42 = a5 & 2;
  v53 = 0;
  if ( !pGroup && (a5 & 2) == 0 )
  {
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      InternalGetGroupTokenBytes(TokenHandle, &v53);
      v11 = v53;
      pGroup = *(PSID *)v53;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 32));
      bGroupDefaulted = 1;
      v17 = pSid;
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &bad_win32_error `RTTI Type Descriptor', &v59) )
      {
        v40 = (*(__int64 (__fastcall **)(const bad_win32_error *))(*(_QWORD *)v59 + 16LL))(v59);
        if ( v40 > 0 )
          v40 = (unsigned __int16)v40 | 0x80070000;
        dwAclRevision = v40;
        if ( v40 < 0 )
          LogMsgHR(v40, (wchar_t *)L"acssctrl/secdscrp", 0x1F9u);
        __eh34_try_continuation(2, &bad_win32_error `RTTI Type Descriptor', &loc_18002625E);
        free(v53);
        free(Block);
        goto LABEL_21;
      }
    }
  }
  dwAclRevision = 0;
  AccessToken = MQSec_GetUserType(v17, (int *)&dwAclRevision, 0, 0);
  if ( AccessToken < 0 )
  {
    LOWORD(dwAclRevision) = 70;
    v42 = AccessToken;
    if ( g_pMSMQErrorLoggingTrace )
      goto LABEL_79;
    goto LABEL_147;
  }
  v18 = 0;
  if ( !dwAclRevision || a8 )
    goto LABEL_37;
  v19 = g_pAnonymSid;
  pSid = g_pAnonymSid;
  bOwnerDefaulted = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 18, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids);
LABEL_37:
    v19 = pSid;
  }
  if ( !v19 || !IsValidSid(v19) )
  {
    LOWORD(dwAclRevision) = 506;
    AccessToken = -1072824287;
    v43 = -1072824287;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v38 = mqwcslen(L"acssctrl/secdscrp");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v38 + 1),
        L"acssctrl/secdscrp",
        2,
        &dwAclRevision,
        4,
        &v43,
        0,
        0);
    }
    goto LABEL_147;
  }
  if ( (a5 & 1) == 0 )
  {
    if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pSid, bOwnerDefaulted) )
    {
      AccessToken = LogGleAssertReturnHr(0x1FBu);
      free(v11);
      free(v16);
      goto LABEL_148;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 32));
  }
  if ( !v42 )
  {
    if ( !pGroup || !IsValidSid(pGroup) )
    {
      LOWORD(dwAclRevision) = 508;
      AccessToken = -1072824287;
      v42 = -1072824287;
      if ( g_pMSMQErrorLoggingTrace )
      {
LABEL_79:
        v26 = mqwcslen(L"acssctrl/secdscrp");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v26 + 1),
          L"acssctrl/secdscrp",
          2,
          &dwAclRevision,
          4,
          &v42,
          0,
          0);
      }
LABEL_147:
      free(v11);
      free(v16);
      goto LABEL_148;
    }
    if ( !SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, bGroupDefaulted) )
    {
      AccessToken = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          20,
          &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids,
          (unsigned int)AccessToken);
      if ( AccessToken )
      {
        LOWORD(dwAclRevision) = 509;
        v42 = AccessToken;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v20 = mqwcslen(L"acssctrl/secdscrp");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            2,
            2LL * (v20 + 1),
            L"acssctrl/secdscrp",
            2,
            &dwAclRevision,
            4,
            &v42,
            0,
            0);
        }
        if ( AccessToken > 0 )
          AccessToken = (unsigned __int16)AccessToken | 0x80070000;
      }
      goto LABEL_147;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 32));
  }
  v55 = 0;
  if ( !v50 && (a5 & 4) == 0 )
  {
    AccessRights = (DWORD *)InternalGetAccessRights(v60, a1, a6, pSid, a7, dwAclRevision);
    dwAclRevision = *AccessRights;
    AccessMask = AccessRights[1];
    v42 = AccessRights[2];
    v22 = AccessRights[3];
    v43 = v22;
    v51 = AccessRights[4];
    v54 = pSid;
    v23 = GetLengthSid(g_pWorldSid) + 16;
    if ( v42 )
      v23 += GetLengthSid(v54) + 8;
    if ( v22 )
      v23 += GetLengthSid(g_pAnonymSid) + 8;
    if ( v51 )
      v23 += GetLengthSid(a7) + 8;
    v18 = (struct _ACL *)MmAllocate(v23);
    v55 = v18;
    if ( !InitializeAcl(v18, v23, dwAclRevision) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          22,
          &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids,
          (unsigned int)LastError);
      if ( LastError )
      {
        LOWORD(dwAclRevision) = 515;
        v42 = LastError;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v25 = mqwcslen(L"acssctrl/secdscrp");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            2,
            2LL * (v25 + 1),
            L"acssctrl/secdscrp",
            2,
            &dwAclRevision,
            4,
            &v42,
            0,
            0);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
LABEL_140:
      free(v18);
      free(v11);
      free(v16);
      AccessToken = LastError;
      goto LABEL_148;
    }
    v27 = AccessMask;
    if ( !AddAccessAllowedAce(v18, dwAclRevision, AccessMask, g_pWorldSid) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          23,
          &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids,
          (unsigned int)LastError);
      if ( LastError )
      {
        LOWORD(dwAclRevision) = 516;
        AccessMask = LastError;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v28 = mqwcslen(L"acssctrl/secdscrp");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            2,
            2LL * (v28 + 1),
            L"acssctrl/secdscrp",
            2,
            &dwAclRevision,
            4,
            &AccessMask,
            0,
            0);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      goto LABEL_140;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      WPP_SF__sid_D(*((_QWORD *)WPP_GLOBAL_Control + 32), v27);
    v29 = v43;
    if ( v43 )
    {
      v54 = g_pAnonymSid;
      if ( !AddAccessAllowedAce(v18, dwAclRevision, v43, g_pAnonymSid) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            25,
            &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids,
            (unsigned int)LastError);
        if ( LastError )
        {
          LOWORD(dwAclRevision) = 517;
          v43 = LastError;
          if ( g_pMSMQErrorLoggingTrace )
          {
            v30 = mqwcslen(L"acssctrl/secdscrp");
            CMSMQTrace::MSMQTraceEvent(
              g_pMSMQErrorLoggingTrace,
              1,
              2,
              2LL * (v30 + 1),
              L"acssctrl/secdscrp",
              2,
              &dwAclRevision,
              4,
              &v43,
              0,
              0);
          }
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
        }
        goto LABEL_140;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF__sid_D(*((_QWORD *)WPP_GLOBAL_Control + 32), v29);
    }
    v31 = v51;
    if ( v51 )
    {
      if ( !AddAccessAllowedAce(v18, dwAclRevision, v51, a7) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            27,
            &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids,
            (unsigned int)LastError);
        if ( LastError )
        {
          LOWORD(dwAclRevision) = 518;
          v43 = LastError;
          if ( g_pMSMQErrorLoggingTrace )
          {
            v32 = mqwcslen(L"acssctrl/secdscrp");
            CMSMQTrace::MSMQTraceEvent(
              g_pMSMQErrorLoggingTrace,
              1,
              2,
              2LL * (v32 + 1),
              L"acssctrl/secdscrp",
              2,
              &dwAclRevision,
              4,
              &v43,
              0,
              0);
          }
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
        }
        goto LABEL_140;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF__sid_D(*((_QWORD *)WPP_GLOBAL_Control + 32), v31);
    }
    v33 = v42;
    if ( v42 )
    {
      if ( !AddAccessAllowedAce(v18, dwAclRevision, v42, pSid) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            29,
            &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids,
            (unsigned int)LastError);
        if ( LastError )
        {
          LOWORD(dwAclRevision) = 519;
          v43 = LastError;
          if ( g_pMSMQErrorLoggingTrace )
          {
            v34 = mqwcslen(L"acssctrl/secdscrp");
            CMSMQTrace::MSMQTraceEvent(
              g_pMSMQErrorLoggingTrace,
              1,
              2,
              2LL * (v34 + 1),
              L"acssctrl/secdscrp",
              2,
              &dwAclRevision,
              4,
              &v43,
              0,
              0);
          }
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
        }
        goto LABEL_140;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF__sid_D(*((_QWORD *)WPP_GLOBAL_Control + 32), v33);
    }
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v18, 0) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          31,
          &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids,
          (unsigned int)LastError);
      if ( LastError )
      {
        LOWORD(dwAclRevision) = 520;
        v43 = LastError;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v35 = mqwcslen(L"acssctrl/secdscrp");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            2,
            2LL * (v35 + 1),
            L"acssctrl/secdscrp",
            2,
            &dwAclRevision,
            4,
            &v43,
            0,
            0);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      goto LABEL_140;
    }
  }
  SelfRelative = MQSec_MakeSelfRelative(pSecurityDescriptor, a2, &v43);
  if ( SelfRelative < 0 )
  {
    LOWORD(dwAclRevision) = 80;
    v43 = SelfRelative;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v37 = mqwcslen(L"acssctrl/secdscrp");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v37 + 1),
        L"acssctrl/secdscrp",
        2,
        &dwAclRevision,
        4,
        &v43,
        0,
        0);
    }
  }
  free(v18);
  free(v11);
  free(v16);
  CHandle::~CHandle((CHandle *)&TokenHandle);
  return (unsigned int)SelfRelative;
}

```

## disassembly

```asm
0x180025eac  mov     rax, rsp
0x180025eaf  mov     [rax+18h], rbx
0x180025eb3  mov     [rax+20h], rsi
0x180025eb7  mov     [rax+10h], rdx
0x180025ebb  mov     [rax+8], ecx
0x180025ebe  push    rdi
0x180025ebf  push    r12
0x180025ec1  push    r13
0x180025ec3  push    r14
0x180025ec5  push    r15
0x180025ec7  sub     rsp, 120h
0x180025ece  mov     rbx, r9
0x180025ed1  mov     edi, r8d
0x180025ed4  mov     eax, ecx
0x180025ed6  lea     rdx, WPP_GLOBAL_Control
0x180025edd  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ee4  mov     r14d, 4
0x180025eea  mov     r15d, [rsp+148h+arg_28]
0x180025ef2  mov     esi, [rsp+148h+arg_20]
0x180025ef9  cmp     rcx, rdx
0x180025efc  jz      short loc_180025F24
0x180025efe  test    [rcx+10Ch], r14b
0x180025f05  jz      short loc_180025F24
0x180025f07  mov     dword ptr [rsp+148h+var_118], r15d
0x180025f0c  mov     dword ptr [rsp+148h+var_120], esi
0x180025f10  mov     dword ptr [rsp+148h+var_128], r8d
0x180025f15  mov     r9d, eax
0x180025f18  mov     rcx, [rcx+100h]
0x180025f1f  call    WPP_SF_ddDd
0x180025f24  xorps   xmm0, xmm0
0x180025f27  xor     eax, eax
0x180025f29  movups  [rsp+148h+pSecurityDescriptor], xmm0
0x180025f31  movups  [rsp+148h+var_70], xmm0
0x180025f39  mov     [rsp+148h+var_60], rax
0x180025f41  lea     r12d, [rax+1]
0x180025f45  mov     edx, r12d; dwRevision
0x180025f48  lea     rcx, [rsp+148h+pSecurityDescriptor]; pSecurityDescriptor
0x180025f50  call    cs:__imp_InitializeSecurityDescriptor
0x180025f56  xor     r13d, r13d
0x180025f59  test    eax, eax
0x180025f5b  jnz     short loc_180025F6C
0x180025f5d  mov     ecx, 1F5h; unsigned __int16
0x180025f62  call    ?LogGleAssertReturnHr@@YAJG@Z; LogGleAssertReturnHr(ushort)
0x180025f67  jmp     loc_180026FB5
0x180025f6c  mov     [rsp+148h+pSid], r13
0x180025f71  mov     [rsp+148h+pGroup], r13
0x180025f79  mov     [rsp+148h+var_A8], r13d
0x180025f81  mov     [rsp+148h+bOwnerDefaulted], r13d
0x180025f89  mov     [rsp+148h+bGroupDefaulted], r13d
0x180025f91  test    rbx, rbx
0x180025f94  jz      loc_180026067
0x180025f9a  lea     rax, [rsp+148h+bGroupDefaulted]
0x180025fa2  mov     [rsp+148h+var_110], rax
0x180025fa7  lea     rax, [rsp+148h+bOwnerDefaulted]
0x180025faf  mov     [rsp+148h+var_118], rax
0x180025fb4  lea     rax, [rsp+148h+var_A8]
0x180025fbc  mov     [rsp+148h+var_120], rax
0x180025fc1  lea     rax, [rsp+148h+pGroup]
0x180025fc9  mov     qword ptr [rsp+148h+var_128], rax
0x180025fce  lea     r9, [rsp+148h+pSid]
0x180025fd3  lea     r8, [rsp+148h+pSecurityDescriptor]
0x180025fdb  mov     edx, r15d
0x180025fde  mov     rcx, rbx
0x180025fe1  call    ?InternalCopyInfoFromArgumentDescriptor@@YAJPEAXW4enumDaclType@@0PEAPEAX2PEAH33@Z; InternalCopyInfoFromArgumentDescriptor(void *,enumDaclType,void *,void * *,void * *,int *,int *,int *)
0x180025fe6  mov     ebx, eax
0x180025fe8  test    eax, eax
0x180025fea  jns     short loc_180026067
0x180025fec  mov     eax, 1F6h
0x180025ff1  mov     word ptr [rsp+148h+dwAclRevision], ax
0x180025ff6  mov     [rsp+148h+var_E0], ebx
0x180025ffa  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r13; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180026001  jz      loc_180026FB3
0x180026007  lea     rdi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x18002600e  mov     rcx, rdi; wchar_t *
0x180026011  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180026016  lea     r9d, [r12+rax]
0x18002601a  add     r9, r9
0x18002601d  mov     [rsp+148h+var_F8], r13
0x180026022  mov     [rsp+148h+var_100], r13
0x180026027  lea     rax, [rsp+148h+var_E0]
0x18002602c  mov     [rsp+148h+var_108], rax
0x180026031  mov     [rsp+148h+var_110], r14
0x180026036  lea     rax, [rsp+148h+dwAclRevision]
0x18002603b  mov     [rsp+148h+var_118], rax
0x180026040  mov     r15d, 2
0x180026046  mov     [rsp+148h+var_120], r15
0x18002604b  mov     qword ptr [rsp+148h+var_128], rdi
0x180026050  mov     r8d, r12d
0x180026053  mov     edx, r12d
0x180026056  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18002605d  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180026062  jmp     loc_180026FB3
0x180026067  mov     [rsp+148h+TokenHandle], r13
0x18002606f  xor     r9d, r9d; int
0x180026072  mov     edx, edi; int
0x180026074  lea     rcx, [rsp+148h+TokenHandle]; TokenHandle
0x18002607c  call    ?GetAccessToken@@YAKPEAPEAXHKH@Z; GetAccessToken(void * *,int,ulong,int)
0x180026081  mov     ebx, eax
0x180026083  test    eax, eax
0x180026085  jz      loc_180026113
0x18002608b  mov     eax, 1F7h
0x180026090  mov     word ptr [rsp+148h+dwAclRevision], ax
0x180026095  mov     [rsp+148h+var_E0], ebx
0x180026099  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r13; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800260a0  jz      short loc_1800260FD
0x1800260a2  lea     rdi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x1800260a9  mov     rcx, rdi; wchar_t *
0x1800260ac  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800260b1  lea     r9d, [r12+rax]
0x1800260b5  add     r9, r9
0x1800260b8  mov     [rsp+148h+var_F8], r13
0x1800260bd  mov     [rsp+148h+var_100], r13
0x1800260c2  lea     rax, [rsp+148h+var_E0]
0x1800260c7  mov     [rsp+148h+var_108], rax
0x1800260cc  mov     [rsp+148h+var_110], r14
0x1800260d1  lea     rax, [rsp+148h+dwAclRevision]
0x1800260d6  mov     [rsp+148h+var_118], rax
0x1800260db  mov     r15d, 2
0x1800260e1  mov     [rsp+148h+var_120], r15
0x1800260e6  mov     qword ptr [rsp+148h+var_128], rdi
0x1800260eb  mov     r8d, r15d
0x1800260ee  mov     edx, r12d
0x1800260f1  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800260f8  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x1800260fd  test    ebx, ebx
0x1800260ff  jle     loc_180026FA6
0x180026105  movzx   ebx, bx
0x180026108  or      ebx, 80070000h
0x18002610e  jmp     loc_180026FA6
0x180026113  mov     r12, r13
0x180026116  mov     [rsp+148h+Block], r13
0x18002611e  mov     rcx, [rsp+148h+pSid]; pSid2
0x180026123  test    rcx, rcx
0x180026126  jnz     loc_1800261BF
0x18002612c  lea     rdx, [rsp+148h+Block]; char **
0x180026134  mov     rcx, [rsp+148h+TokenHandle]; TokenHandle
0x18002613c  call    ?InternalGetUserTokenBytes@@YAXPEAXPEAPEAD@Z; InternalGetUserTokenBytes(void *,char * *)
0x180026141  mov     r12, [rsp+148h+Block]
0x180026149  mov     rcx, [r12]
0x18002614d  mov     [rsp+148h+pSid], rcx
0x180026152  mov     rax, cs:WPP_GLOBAL_Control
0x180026159  lea     rbx, WPP_GLOBAL_Control
0x180026160  cmp     rax, rbx
0x180026163  jz      short loc_180026193
0x180026165  test    [rax+10Ch], r14b
0x18002616c  jz      short loc_180026193
0x18002616e  mov     edx, 10h
0x180026173  mov     r9, rcx
0x180026176  lea     rdi, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x18002617d  mov     r8, rdi
0x180026180  mov     rcx, [rax+100h]; LoggerHandle
0x180026187  call    WPP_SF__sid_
0x18002618c  mov     rcx, [rsp+148h+pSid]
0x180026191  jmp     short loc_18002619A
0x180026193  lea     rdi, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x18002619a  mov     [rsp+148h+bOwnerDefaulted], 1
0x1800261a5  jmp     short loc_1800261CD
0x1800261a7  mov     rcx, [rsp+148h+Block]; Block
0x1800261af  call    cs:__imp_free
0x1800261b5  nop
0x1800261b6  mov     ebx, [rsp+148h+dwAclRevision]
0x1800261ba  jmp     loc_180026FA6
0x1800261bf  lea     rdi, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x1800261c6  lea     rbx, WPP_GLOBAL_Control
0x1800261cd  mov     eax, esi
0x1800261cf  mov     r15d, 2
0x1800261d5  and     eax, r15d
0x1800261d8  mov     [rsp+148h+var_E0], eax
0x1800261dc  mov     [rsp+148h+var_98], r13
0x1800261e4  cmp     [rsp+148h+pGroup], 0
0x1800261ed  jnz     loc_180026281
0x1800261f3  test    eax, eax
0x1800261f5  jnz     loc_180026281
0x1800261fb  lea     rdx, [rsp+148h+var_98]; char **
0x180026203  mov     rcx, [rsp+148h+TokenHandle]; TokenHandle
0x18002620b  call    ?InternalGetGroupTokenBytes@@YAXPEAXPEAPEAD@Z; InternalGetGroupTokenBytes(void *,char * *)
0x180026210  mov     r13, [rsp+148h+var_98]
0x180026218  mov     r9, [r13+0]
0x18002621c  mov     [rsp+148h+pGroup], r9
0x180026224  mov     rcx, cs:WPP_GLOBAL_Control
0x18002622b  cmp     rcx, rbx
0x18002622e  jz      short loc_18002624C
0x180026230  test    [rcx+10Ch], r14b
0x180026237  jz      short loc_18002624C
0x180026239  lea     edx, [r15+0Fh]
0x18002623d  mov     r8, rdi
0x180026240  mov     rcx, [rcx+100h]; LoggerHandle
0x180026247  call    WPP_SF__sid_
0x18002624c  mov     [rsp+148h+bGroupDefaulted], 1
0x180026257  mov     rcx, [rsp+148h+pSid]
0x18002625c  jmp     short loc_180026281
0x18002625e  mov     rcx, [rsp+148h+var_98]; Block
0x180026266  call    cs:__imp_free
0x18002626c  nop
0x18002626d  mov     rcx, [rsp+148h+Block]; Block
0x180026275  call    cs:__imp_free
0x18002627b  nop
0x18002627c  jmp     loc_1800261B6
0x180026281  mov     [rsp+148h+dwAclRevision], 0
0x180026289  xor     r9d, r9d; int *
0x18002628c  xor     r8d, r8d; int *
0x18002628f  lea     rdx, [rsp+148h+dwAclRevision]; int *
0x180026294  call    ?MQSec_GetUserType@@YAJPEAXPEAH11@Z; MQSec_GetUserType(void *,int *,int *,int *)
0x180026299  mov     ebx, eax
0x18002629b  test    eax, eax
0x18002629d  jns     loc_18002632D
0x1800262a3  mov     eax, 46h ; 'F'
0x1800262a8  mov     word ptr [rsp+148h+dwAclRevision], ax
0x1800262ad  mov     [rsp+148h+var_E0], ebx
0x1800262b1  xor     esi, esi
0x1800262b3  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rsi; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800262ba  jz      short loc_180026314
0x1800262bc  lea     rdi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x1800262c3  mov     rcx, rdi; wchar_t *
0x1800262c6  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800262cb  lea     ecx, [rsi+1]
0x1800262ce  lea     r9d, [rcx+rax]
0x1800262d2  add     r9, r9
0x1800262d5  mov     [rsp+148h+var_F8], rsi
0x1800262da  mov     [rsp+148h+var_100], rsi
0x1800262df  lea     rax, [rsp+148h+var_E0]
0x1800262e4  mov     [rsp+148h+var_108], rax
0x1800262e9  mov     [rsp+148h+var_110], r14
0x1800262ee  lea     rax, [rsp+148h+dwAclRevision]
0x1800262f3  mov     [rsp+148h+var_118], rax
0x1800262f8  mov     [rsp+148h+var_120], r15
0x1800262fd  mov     qword ptr [rsp+148h+var_128], rdi
0x180026302  mov     r8d, ecx
0x180026305  mov     edx, ecx
0x180026307  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18002630e  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180026313  nop
0x180026314  mov     rcx, r13; Block
0x180026317  call    cs:__imp_free
0x18002631d  nop
0x18002631e  mov     rcx, r12; Block
0x180026321  call    cs:__imp_free
0x180026327  nop
0x180026328  jmp     loc_180026FA6
0x18002632d  xor     ebx, ebx
0x18002632f  cmp     [rsp+148h+dwAclRevision], ebx
0x180026333  jz      short loc_180026383
0x180026335  cmp     [rsp+148h+arg_38], ebx
0x18002633c  jnz     short loc_180026383
0x18002633e  mov     rcx, cs:?g_pAnonymSid@@3PEAXEA; void * g_pAnonymSid
0x180026345  mov     [rsp+148h+pSid], rcx
0x18002634a  mov     [rsp+148h+bOwnerDefaulted], 1
0x180026355  mov     rax, cs:WPP_GLOBAL_Control
0x18002635c  lea     rdx, WPP_GLOBAL_Control
0x180026363  cmp     rax, rdx
0x180026366  jz      short loc_180026388
0x180026368  test    [rax+10Ch], r14b
0x18002636f  jz      short loc_180026388
0x180026371  lea     edx, [rbx+12h]
0x180026374  mov     r8, rdi
0x180026377  mov     rcx, [rax+100h]
0x18002637e  call    WPP_SF_
0x180026383  mov     rcx, [rsp+148h+pSid]; pSid
0x180026388  test    rcx, rcx
0x18002638b  jz      loc_180026F1C
0x180026391  call    cs:__imp_IsValidSid
0x180026397  test    eax, eax
0x180026399  jz      loc_180026F1C
0x18002639f  test    sil, 1
0x1800263a3  jnz     short loc_18002641E
0x1800263a5  mov     r8d, [rsp+148h+bOwnerDefaulted]; bOwnerDefaulted
0x1800263ad  mov     rdx, [rsp+148h+pSid]; pOwner
0x1800263b2  lea     rcx, [rsp+148h+pSecurityDescriptor]; pSecurityDescriptor
0x1800263ba  call    cs:__imp_SetSecurityDescriptorOwner
0x1800263c0  test    eax, eax
0x1800263c2  jnz     short loc_1800263E9
0x1800263c4  mov     ecx, 1FBh; unsigned __int16
0x1800263c9  call    ?LogGleAssertReturnHr@@YAJG@Z; LogGleAssertReturnHr(ushort)
0x1800263ce  mov     ebx, eax
0x1800263d0  mov     rcx, r13; Block
0x1800263d3  call    cs:__imp_free
0x1800263d9  nop
0x1800263da  mov     rcx, r12; Block
0x1800263dd  call    cs:__imp_free
0x1800263e3  nop
0x1800263e4  jmp     loc_180026FA6
0x1800263e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263f0  lea     rax, WPP_GLOBAL_Control
0x1800263f7  cmp     rcx, rax
0x1800263fa  jz      short loc_18002641E
0x1800263fc  test    [rcx+10Ch], r14b
0x180026403  jz      short loc_18002641E
0x180026405  mov     edx, 13h
0x18002640a  mov     r9, [rsp+148h+pSid]
0x18002640f  mov     r8, rdi
0x180026412  mov     rcx, [rcx+100h]; LoggerHandle
0x180026419  call    WPP_SF__sid_
0x18002641e  cmp     [rsp+148h+var_E0], ebx
0x180026422  jnz     loc_180026578
0x180026428  mov     rcx, [rsp+148h+pGroup]; pSid
0x180026430  test    rcx, rcx
0x180026433  jz      loc_180026773
0x180026439  call    cs:__imp_IsValidSid
0x18002643f  test    eax, eax
0x180026441  jz      loc_180026773
  ... truncated ...
```
