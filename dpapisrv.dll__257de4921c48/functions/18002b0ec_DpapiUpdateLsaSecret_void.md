# DpapiUpdateLsaSecret(void *)

- ea: `0x18002b0ec`
- end: `0x18002bea7`
- name: `?DpapiUpdateLsaSecret@@YAKPEAX@Z`
- size: `3515`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180014c80`

## callees

- `0x1800063c0`
- `0x180006510`
- `0x180006c60`
- `0x180007f10`
- `0x1800097f0`
- `0x18000db40`
- `0x18000e470`
- `0x18000fce0`
- `0x180013f2c`
- `0x1800180cc`
- `0x18001ab70`
- `0x18001c340`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001e1b4`
- `0x180023d84`
- `0x18002b0ec`
- `0x18002dd6c`
- `0x18002e130`
- `0x180035b68`
- `0x180035bb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b3c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b3c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b301`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b301`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002b336`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002b336`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b315`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b364`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b47d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b315`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b364`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b47d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002baf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bbce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bc41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bdd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002baf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bbce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bc41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bdd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b41e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b459`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b41e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b459`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18002b1a4`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18002b1a4`
- `ntdll!RtlNtStatusToDosError` at `0x18002b268`
- `ntdll!RtlNtStatusToDosError` at `0x18002b290`
- `ntdll!RtlNtStatusToDosError` at `0x18002b268`
- `ntdll!RtlNtStatusToDosError` at `0x18002b290`
- `ntdll!NtPrivilegeCheck` at `0x18002b246`
- `ntdll!NtPrivilegeCheck` at `0x18002b246`
- `ntdll!NtOpenThreadToken` at `0x18002b210`
- `ntdll!NtOpenThreadToken` at `0x18002b210`
- `ntdll!NtClose` at `0x18002b27b`
- `ntdll!NtClose` at `0x18002b27b`

## string_xrefs

- `0x18002b403`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002b4e0`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002b55d`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall DpapiUpdateLsaSecret(_QWORD *a1)
{
  int v2; // r15d
  int v3; // esi
  int CurrentServiceSessionId; // r14d
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  HANDLE EventW; // rdi
  __int64 v9; // rcx
  DWORD LastError; // eax
  __int64 v11; // rdx
  unsigned int v12; // eax
  int v13; // r15d
  int v14; // r12d
  int v15; // r13d
  void *v16; // rcx
  unsigned int *v17; // r8
  unsigned int v18; // eax
  __int64 v19; // r9
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  int v25; // ebx
  BeforeKeyRotation *v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rdx
  unsigned __int16 *v29; // rbx
  unsigned __int16 *v30; // rbx
  unsigned __int16 *v31; // rbx
  unsigned int v32; // eax
  unsigned __int16 *v33; // rdi
  unsigned __int16 *v34; // rbx
  unsigned int v35; // eax
  unsigned __int16 *v36; // rdi
  unsigned __int8 Result[8]; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  int v40; // [rsp+50h] [rbp-B0h]
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID v42; // [rsp+60h] [rbp-A0h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v44[13]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v45; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned int v46[142]; // [rsp+C8h] [rbp-38h] BYREF
  _DWORD v47[13]; // [rsp+300h] [rbp+200h] BYREF
  unsigned int v48; // [rsp+334h] [rbp+234h] BYREF
  unsigned int v49[142]; // [rsp+338h] [rbp+238h] BYREF
  _DWORD v50[13]; // [rsp+570h] [rbp+470h] BYREF
  unsigned int v51; // [rsp+5A4h] [rbp+4A4h] BYREF
  unsigned int v52[142]; // [rsp+5A8h] [rbp+4A8h] BYREF
  _DWORD v53[13]; // [rsp+7E0h] [rbp+6E0h] BYREF
  unsigned int v54; // [rsp+814h] [rbp+714h] BYREF
  unsigned int v55[142]; // [rsp+818h] [rbp+718h] BYREF
  _DWORD v56[13]; // [rsp+A50h] [rbp+950h] BYREF
  unsigned int v57; // [rsp+A84h] [rbp+984h] BYREF
  unsigned int v58[142]; // [rsp+A88h] [rbp+988h] BYREF
  _DWORD v59[13]; // [rsp+CC0h] [rbp+BC0h] BYREF
  unsigned int v60; // [rsp+CF4h] [rbp+BF4h] BYREF
  unsigned int v61[142]; // [rsp+CF8h] [rbp+BF8h] BYREF

  memset_0(v44, 0, 0x270u);
  memset_0(v59, 0, 0x270u);
  memset_0(v47, 0, 0x270u);
  memset_0(v50, 0, 0x270u);
  memset_0(v53, 0, 0x270u);
  memset_0(v56, 0, 0x270u);
  v42 = 0;
  hMem = 0;
  v2 = 0;
  v40 = 0;
  v3 = 0;
  Result[0] = 0;
  CurrentServiceSessionId = RtlGetCurrentServiceSessionId();
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 134, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
  v5 = CPSImpersonateClient(a1);
  if ( v5 )
    goto LABEL_156;
  TokenHandle = 0;
  v6 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( v6 < 0 )
  {
    v5 = RtlNtStatusToDosError(v6);
  }
  else
  {
    RequiredPrivileges.PrivilegeCount = 1;
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.Privilege[0].Luid = (LUID)7LL;
    RequiredPrivileges.Privilege[0].Attributes = 0;
    v7 = NtPrivilegeCheck(TokenHandle, &RequiredPrivileges, Result);
    v5 = v7;
    if ( v7 < 0 )
    {
      v5 = RtlNtStatusToDosError(v7);
    }
    else if ( !Result[0] )
    {
      v5 = 1314;
    }
    NtClose(TokenHandle);
    TokenHandle = 0;
  }
  CPSRevertToSelf(a1);
  if ( v5 || !Result[0] )
  {
LABEL_156:
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 135, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    goto LABEL_149;
  }
  if ( !CurrentServiceSessionId )
    goto LABEL_40;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 136, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
  EventW = CreateEventW(0, 1, 0, L"LSA_DPAPI_CAN_RESET_CREDS");
  if ( !EventW && (GetLastError() != 183 || (EventW = OpenEventW(0x100000u, 0, L"LSA_DPAPI_CAN_RESET_CREDS")) == 0) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_44;
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_41;
    LastError = GetLastError();
    v11 = 137;
    goto LABEL_24;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 138, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
  v5 = WaitForSingleObject(EventW, 0x7530u);
  if ( v5 != 258 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 140, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    if ( CloseHandle(EventW) )
      goto LABEL_40;
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_44;
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
    {
LABEL_41:
      if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 8) != 0 )
        WPP_SF_(*(_QWORD *)(v9 + 16), 142, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
LABEL_44:
      v12 = CPSCreateServerContext((struct CRYPT_SERVER_CONTEXT *)v44, 0, 0, 0);
      v5 = v12;
      if ( v12 )
      {
        DebugTraceError(v12, "dwRet", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 8507);
LABEL_149:
        if ( CurrentServiceSessionId )
        {
          if ( v2 )
            CPSDeleteServerContext((struct CRYPT_SERVER_CONTEXT *)v53);
          if ( v3 )
            CPSDeleteServerContext((struct CRYPT_SERVER_CONTEXT *)v56);
        }
        return v5;
      }
      LODWORD(TokenHandle) = 1;
      v13 = 0;
      v14 = 0;
      v15 = 0;
      CPSOverrideToLocalSystem(v44, (int *)&TokenHandle, 0);
      GetDefaultAlgInfo(v16, &v45, v17, v46, 0);
      v18 = SynchronizeMasterKeys(v44, 0, 0, 0, 2u, 0, 0);
      v5 = v18;
      if ( v18 )
      {
        v19 = 8524;
LABEL_48:
        DebugTraceError(v18, "dwRet", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v19);
LABEL_142:
        CPSDeleteServerContext((struct CRYPT_SERVER_CONTEXT *)v44);
        if ( v13 )
          CPSDeleteServerContext((struct CRYPT_SERVER_CONTEXT *)v59);
        if ( v14 )
          CPSDeleteServerContext((struct CRYPT_SERVER_CONTEXT *)v47);
        if ( v15 )
          CPSDeleteServerContext((struct CRYPT_SERVER_CONTEXT *)v50);
        v2 = v40;
        goto LABEL_149;
      }
      v18 = CPSCreateServerContext((struct CRYPT_SERVER_CONTEXT *)v59, 0, 0, 0);
      v5 = v18;
      if ( v18 )
      {
        v19 = 8537;
        goto LABEL_48;
      }
      v13 = 1;
      GetDefaultAlgInfo(v20, &v60, 0, v61, 0);
      v18 = SynchronizeMasterKeys(v59, 0, 0, 0, 2u, 0, 0);
      v5 = v18;
      if ( v18 )
      {
        v19 = 8551;
        goto LABEL_48;
      }
      v18 = CPSCreateServerContext((struct CRYPT_SERVER_CONTEXT *)v47, 0, 0, 0);
      v5 = v18;
      if ( v18 )
      {
        v19 = 8564;
        goto LABEL_48;
      }
      v14 = 1;
      CPSSetWellKnownAccount(v47, 0x13u);
      GetDefaultAlgInfo(v21, &v48, 0, v49, 0);
      v18 = SynchronizeMasterKeys(v47, 0, 0, 0, 2u, 0, 0);
      v5 = v18;
      if ( v18 )
      {
        v19 = 8580;
        goto LABEL_48;
      }
      v18 = CPSCreateServerContext((struct CRYPT_SERVER_CONTEXT *)v50, 0, 0, 0);
      v5 = v18;
      if ( v18 )
      {
        v19 = 8593;
        goto LABEL_48;
      }
      v15 = 1;
      CPSSetWellKnownAccount(v50, 0x14u);
      GetDefaultAlgInfo(v22, &v51, 0, v52, 0);
      v18 = SynchronizeMasterKeys(v50, 0, 0, 0, 2u, 0, 0);
      v5 = v18;
      if ( v18 )
      {
        v19 = 8609;
        goto LABEL_48;
      }
      if ( CurrentServiceSessionId )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 143, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
        v18 = CPSCreateServerContext((struct CRYPT_SERVER_CONTEXT *)v53, 0, 0, 0);
        v5 = v18;
        if ( v18 )
        {
          v19 = 8627;
          goto LABEL_48;
        }
        v40 = 1;
        CPSSetWellKnownAccount(v53, 0x5Au);
        GetDefaultAlgInfo(v23, &v54, 0, v55, 0);
        v18 = SynchronizeMasterKeys(v53, 0, 0, 0, 2u, 0, 0);
        v5 = v18;
        if ( v18 )
        {
          v19 = 8640;
          goto LABEL_48;
        }
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 144, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
        v18 = CPSCreateServerContext((struct CRYPT_SERVER_CONTEXT *)v56, 0, 0, 0);
        v5 = v18;
        if ( v18 )
        {
          v19 = 8648;
          goto LABEL_48;
        }
        CPSSetWellKnownAccount(v56, 0x5Bu);
        GetDefaultAlgInfo(v24, &v57, 0, v58, 0);
        v18 = SynchronizeMasterKeys(v56, 0, 0, 0, 2u, 0, 0);
        v5 = v18;
        if ( v18 )
        {
          v3 = 1;
          v19 = 8661;
          goto LABEL_48;
        }
      }
      v25 = 1;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 145, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl'::`2'::impl) )
      {
        if ( !(unsigned int)UpdateSystemCredentials() )
        {
          v27 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            v25 = 0;
            if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              goto LABEL_90;
            v28 = 146;
LABEL_88:
            WPP_SF_(*(_QWORD *)(v27 + 16), v28, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
            goto LABEL_89;
          }
          goto LABEL_103;
        }
      }
      else if ( !(unsigned int)BeforeKeyRotation::UpdateSystemCredentials(v26) )
      {
        v27 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          v25 = 0;
          if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_90;
          v28 = 147;
          goto LABEL_88;
        }
LABEL_103:
        if ( !(unsigned int)CPSGetUserStorageArea(v44, 0, 1u, 0, (unsigned __int16 **)&hMem) )
        {
          v29 = (unsigned __int16 *)hMem;
          if ( !(unsigned int)CreateMasterKey(v44, (unsigned __int16 *)hMem, &v42, 0) )
            SetPreferredMasterKeyGuid(v44, v29, &v42);
          LocalFree(v29);
          hMem = 0;
        }
        if ( !(unsigned int)CPSGetUserStorageArea(v59, 0, 1u, 0, (unsigned __int16 **)&hMem) )
        {
          v30 = (unsigned __int16 *)hMem;
          if ( !(unsigned int)CreateMasterKey(v59, (unsigned __int16 *)hMem, &v42, 0) )
            SetPreferredMasterKeyGuid(v59, v30, &v42);
          LocalFree(v30);
          hMem = 0;
        }
        if ( !(unsigned int)CPSGetUserStorageArea(v47, 0, 1u, 0, (unsigned __int16 **)&hMem) )
        {
          v31 = (unsigned __int16 *)hMem;
          if ( !(unsigned int)CreateMasterKey(v47, (unsigned __int16 *)hMem, &v42, 0) )
            SetPreferredMasterKeyGuid(v47, v31, &v42);
          LocalFree(v31);
          hMem = 0;
        }
        v32 = CPSGetUserStorageArea(v50, 0, 1u, 0, (unsigned __int16 **)&hMem);
        v5 = v32;
        if ( v32 )
        {
          if ( v32 - 2 <= 1 )
            v5 = 0;
        }
        else
        {
          v33 = (unsigned __int16 *)hMem;
          v5 = CreateMasterKey(v50, (unsigned __int16 *)hMem, &v42, 0);
          if ( !v5 )
            SetPreferredMasterKeyGuid(v50, v33, &v42);
          LocalFree(v33);
          hMem = 0;
        }
        if ( CurrentServiceSessionId )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 151, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
          if ( !(unsigned int)CPSGetUserStorageArea(v53, 0, 1u, 0, (unsigned __int16 **)&hMem) )
          {
            v34 = (unsigned __int16 *)hMem;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
            {
              WPP_SF_S(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                152,
                WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
                hMem);
            }
            if ( !(unsigned int)CreateMasterKey(v53, v34, &v42, 0) )
              SetPreferredMasterKeyGuid(v53, v34, &v42);
            LocalFree(v34);
            hMem = 0;
          }
          v35 = CPSGetUserStorageArea(v56, 0, 1u, 0, (unsigned __int16 **)&hMem);
          v5 = v35;
          if ( v35 )
          {
            if ( v35 - 2 <= 1 )
              v5 = 0;
          }
          else
          {
            v36 = (unsigned __int16 *)hMem;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
            {
              WPP_SF_S(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                153,
                WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
                hMem);
            }
            v5 = CreateMasterKey(v56, v36, &v42, 0);
            if ( !v5 )
              SetPreferredMasterKeyGuid(v56, v36, &v42);
            LocalFree(v36);
          }
        }
        v3 = v40;
        goto LABEL_142;
      }
LABEL_89:
      v27 = WPP_GLOBAL_Control;
LABEL_90:
      if ( (_UNKNOWN *)v27 != &WPP_GLOBAL_Control && (*(_BYTE *)(v27 + 28) & 8) != 0 )
      {
        WPP_SF_(*(_QWORD *)(v27 + 16), 148, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
        v27 = WPP_GLOBAL_Control;
      }
      if ( v25 )
      {
        SynchronizeMasterKeys(v44, 0, 0, 0, 1u, 0, 0);
        SynchronizeMasterKeys(v59, 0, 0, 0, 1u, 0, 0);
        SynchronizeMasterKeys(v47, 0, 0, 0, 1u, 0, 0);
        SynchronizeMasterKeys(v50, 0, 0, 0, 1u, 0, 0);
        if ( CurrentServiceSessionId )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 149, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
          SynchronizeMasterKeys(v53, 0, 0, 0, 1u, 0, 0);
          SynchronizeMasterKeys(v56, 0, 0, 0, 1u, 0, 0);
        }
        v27 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v27 != &WPP_GLOBAL_Control && (*(_BYTE *)(v27 + 28) & 8) != 0 )
        WPP_SF_(*(_QWORD *)(v27 + 16), 150, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
      goto LABEL_103;
    }
    LastError = GetLastError();
    v11 = 141;
LABEL_24:
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v11, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, LastError);
LABEL_40:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_41;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 139, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
  DebugTraceError(258, "dwRet", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 8480);
  CloseHandle(EventW);
  return v5;
}

```

## disassembly

```asm
0x18002b0ec  push    rbp
0x18002b0ee  push    rbx
0x18002b0ef  push    rsi
0x18002b0f0  push    rdi
0x18002b0f1  push    r12
0x18002b0f3  push    r13
0x18002b0f5  push    r14
0x18002b0f7  push    r15
0x18002b0f9  lea     rbp, [rsp-0E48h]
0x18002b101  sub     rsp, 0F48h
0x18002b108  mov     rax, cs:__security_cookie
0x18002b10f  xor     rax, rsp
0x18002b112  mov     [rbp+0E80h+var_50], rax
0x18002b119  mov     rdi, rcx
0x18002b11c  mov     ebx, 270h
0x18002b121  mov     r8d, ebx; Size
0x18002b124  lea     rcx, [rbp+0E80h+var_EF0]; void *
0x18002b128  xor     edx, edx; Val
0x18002b12a  call    memset_0
0x18002b12f  mov     r8d, ebx; Size
0x18002b132  lea     rcx, [rbp+0E80h+var_2C0]; void *
0x18002b139  xor     edx, edx; Val
0x18002b13b  call    memset_0
0x18002b140  mov     r8d, ebx; Size
0x18002b143  lea     rcx, [rbp+0E80h+var_C80]; void *
0x18002b14a  xor     edx, edx; Val
0x18002b14c  call    memset_0
0x18002b151  mov     r8d, ebx; Size
0x18002b154  lea     rcx, [rbp+0E80h+var_A10]; void *
0x18002b15b  xor     edx, edx; Val
0x18002b15d  call    memset_0
0x18002b162  mov     r8d, ebx; Size
0x18002b165  lea     rcx, [rbp+0E80h+var_7A0]; void *
0x18002b16c  xor     edx, edx; Val
0x18002b16e  call    memset_0
0x18002b173  mov     r8d, ebx; Size
0x18002b176  lea     rcx, [rbp+0E80h+var_530]; void *
0x18002b17d  xor     edx, edx; Val
0x18002b17f  call    memset_0
0x18002b184  xor     r12d, r12d
0x18002b187  xorps   xmm0, xmm0
0x18002b18a  movups  xmmword ptr [rsp+0F80h+var_F20.Data1], xmm0
0x18002b18f  mov     [rsp+0F80h+hMem], r12
0x18002b194  mov     r15d, r12d
0x18002b197  mov     [rsp+0F80h+var_F30], r12d
0x18002b19c  mov     esi, r12d
0x18002b19f  mov     [rsp+0F80h+Result], r12b
0x18002b1a4  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18002b1ab  nop     dword ptr [rax+rax+00h]
0x18002b1b0  mov     r14d, eax
0x18002b1b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1ba  lea     rax, WPP_GLOBAL_Control
0x18002b1c1  cmp     rcx, rax
0x18002b1c4  jz      short loc_18002B1E1
0x18002b1c6  test    byte ptr [rcx+1Ch], 4
0x18002b1ca  jz      short loc_18002B1E1
0x18002b1cc  mov     rcx, [rcx+10h]
0x18002b1d0  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002b1d7  mov     edx, 86h
0x18002b1dc  call    WPP_SF_
0x18002b1e1  mov     rcx, rdi; void *
0x18002b1e4  call    ?CPSImpersonateClient@@YAKPEAX@Z; CPSImpersonateClient(void *)
0x18002b1e9  mov     ebx, eax
0x18002b1eb  mov     r13d, 1
0x18002b1f1  test    eax, eax
0x18002b1f3  jnz     loc_18002BE77
0x18002b1f9  lea     r9, [rsp+0F80h+TokenHandle]; TokenHandle
0x18002b1fe  mov     [rsp+0F80h+TokenHandle], r12
0x18002b203  mov     r8b, r13b; OpenAsSelf
0x18002b206  lea     edx, [rax+8]; DesiredAccess
0x18002b209  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002b210  call    cs:__imp_NtOpenThreadToken
0x18002b217  nop     dword ptr [rax+rax+00h]
0x18002b21c  test    eax, eax
0x18002b21e  js      short loc_18002B28E
0x18002b220  mov     rcx, [rsp+0F80h+TokenHandle]; ClientToken
0x18002b225  lea     r8, [rsp+0F80h+Result]; Result
0x18002b22a  lea     rdx, [rsp+0F80h+RequiredPrivileges]; RequiredPrivileges
0x18002b22f  mov     [rsp+0F80h+RequiredPrivileges.PrivilegeCount], r13d
0x18002b234  mov     [rsp+0F80h+RequiredPrivileges.Control], r13d
0x18002b239  mov     qword ptr [rsp+0F80h+RequiredPrivileges.Privilege.Luid.LowPart], 7
0x18002b242  mov     [rbp+0E80h+RequiredPrivileges.Privilege.Attributes], r12d
0x18002b246  call    cs:__imp_NtPrivilegeCheck
0x18002b24d  nop     dword ptr [rax+rax+00h]
0x18002b252  mov     ebx, eax
0x18002b254  test    eax, eax
0x18002b256  js      short loc_18002B266
0x18002b258  cmp     [rsp+0F80h+Result], r12b
0x18002b25d  jnz     short loc_18002B276
0x18002b25f  mov     ebx, 522h
0x18002b264  jmp     short loc_18002B276
0x18002b266  mov     ecx, eax; Status
0x18002b268  call    cs:__imp_RtlNtStatusToDosError
0x18002b26f  nop     dword ptr [rax+rax+00h]
0x18002b274  mov     ebx, eax
0x18002b276  mov     rcx, [rsp+0F80h+TokenHandle]; Handle
0x18002b27b  call    cs:__imp_NtClose
0x18002b282  nop     dword ptr [rax+rax+00h]
0x18002b287  mov     [rsp+0F80h+TokenHandle], r12
0x18002b28c  jmp     short loc_18002B29E
0x18002b28e  mov     ecx, eax; Status
0x18002b290  call    cs:__imp_RtlNtStatusToDosError
0x18002b297  nop     dword ptr [rax+rax+00h]
0x18002b29c  mov     ebx, eax
0x18002b29e  mov     rcx, rdi; void *
0x18002b2a1  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x18002b2a6  xor     edi, edi
0x18002b2a8  test    ebx, ebx
0x18002b2aa  jnz     loc_18002BE77
0x18002b2b0  cmp     [rsp+0F80h+Result], dil
0x18002b2b5  jz      loc_18002BE77
0x18002b2bb  test    r14d, r14d
0x18002b2be  jz      loc_18002B493
0x18002b2c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b2cb  lea     r12, WPP_GLOBAL_Control
0x18002b2d2  cmp     rcx, r12
0x18002b2d5  jz      short loc_18002B2F2
0x18002b2d7  test    byte ptr [rcx+1Ch], 8
0x18002b2db  jz      short loc_18002B2F2
0x18002b2dd  mov     rcx, [rcx+10h]
0x18002b2e1  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002b2e8  mov     edx, 88h
0x18002b2ed  call    WPP_SF_
0x18002b2f2  lea     r9, Name; "LSA_DPAPI_CAN_RESET_CREDS"
0x18002b2f9  xor     r8d, r8d; bInitialState
0x18002b2fc  mov     edx, r13d; bManualReset
0x18002b2ff  xor     ecx, ecx; lpEventAttributes
0x18002b301  call    cs:__imp_CreateEventW
0x18002b308  nop     dword ptr [rax+rax+00h]
0x18002b30d  mov     rdi, rax
0x18002b310  test    rax, rax
0x18002b313  jnz     short loc_18002B394
0x18002b315  call    cs:__imp_GetLastError
0x18002b31c  nop     dword ptr [rax+rax+00h]
0x18002b321  cmp     eax, 0B7h
0x18002b326  jnz     short loc_18002B34A
0x18002b328  lea     r8, Name; "LSA_DPAPI_CAN_RESET_CREDS"
0x18002b32f  xor     edx, edx; bInheritHandle
0x18002b331  mov     ecx, 100000h; dwDesiredAccess
0x18002b336  call    cs:__imp_OpenEventW
0x18002b33d  nop     dword ptr [rax+rax+00h]
0x18002b342  mov     rdi, rax
0x18002b345  test    rax, rax
0x18002b348  jnz     short loc_18002B394
0x18002b34a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b351  cmp     rcx, r12
0x18002b354  jz      loc_18002B4C1
0x18002b35a  test    [rcx+1Ch], r13b
0x18002b35e  jz      loc_18002B4A1
0x18002b364  call    cs:__imp_GetLastError
0x18002b36b  nop     dword ptr [rax+rax+00h]
0x18002b370  mov     edx, 89h
0x18002b375  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b37c  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002b383  mov     r9d, eax
0x18002b386  mov     rcx, [rcx+10h]
0x18002b38a  call    WPP_SF_d
0x18002b38f  jmp     loc_18002B49A
0x18002b394  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b39b  cmp     rcx, r12
0x18002b39e  jz      short loc_18002B3BB
0x18002b3a0  test    byte ptr [rcx+1Ch], 8
0x18002b3a4  jz      short loc_18002B3BB
0x18002b3a6  mov     rcx, [rcx+10h]
0x18002b3aa  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002b3b1  mov     edx, 8Ah
0x18002b3b6  call    WPP_SF_
0x18002b3bb  mov     edx, 7530h; dwMilliseconds
0x18002b3c0  mov     rcx, rdi; hHandle
0x18002b3c3  call    cs:__imp_WaitForSingleObject
0x18002b3ca  nop     dword ptr [rax+rax+00h]
0x18002b3cf  mov     ebx, eax
0x18002b3d1  cmp     eax, 102h
0x18002b3d6  jnz     short loc_18002B42F
0x18002b3d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3df  cmp     rcx, r12
0x18002b3e2  jz      short loc_18002B3FD
0x18002b3e4  test    [rcx+1Ch], r13b
0x18002b3e8  jz      short loc_18002B3FD
0x18002b3ea  mov     rcx, [rcx+10h]
0x18002b3ee  lea     edx, [rax-77h]
0x18002b3f1  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002b3f8  call    WPP_SF_
0x18002b3fd  mov     r9d, 2120h
0x18002b403  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002b40a  lea     rdx, aDwret; "dwRet"
0x18002b411  mov     ecx, 102h
0x18002b416  call    DebugTraceError
0x18002b41b  mov     rcx, rdi; hObject
0x18002b41e  call    cs:__imp_CloseHandle
0x18002b425  nop     dword ptr [rax+rax+00h]
0x18002b42a  jmp     loc_18002BE51
0x18002b42f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b436  cmp     rcx, r12
0x18002b439  jz      short loc_18002B456
0x18002b43b  test    byte ptr [rcx+1Ch], 8
0x18002b43f  jz      short loc_18002B456
0x18002b441  mov     rcx, [rcx+10h]
0x18002b445  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002b44c  mov     edx, 8Ch
0x18002b451  call    WPP_SF_
0x18002b456  mov     rcx, rdi; hObject
0x18002b459  call    cs:__imp_CloseHandle
0x18002b460  nop     dword ptr [rax+rax+00h]
0x18002b465  xor     edi, edi
0x18002b467  test    eax, eax
0x18002b469  jnz     short loc_18002B49A
0x18002b46b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b472  cmp     rcx, r12
0x18002b475  jz      short loc_18002B4C3
0x18002b477  test    [rcx+1Ch], r13b
0x18002b47b  jz      short loc_18002B4A1
0x18002b47d  call    cs:__imp_GetLastError
0x18002b484  nop     dword ptr [rax+rax+00h]
0x18002b489  mov     edx, 8Dh
0x18002b48e  jmp     loc_18002B375
0x18002b493  lea     r12, WPP_GLOBAL_Control
0x18002b49a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4a1  cmp     rcx, r12
0x18002b4a4  jz      short loc_18002B4C1
0x18002b4a6  test    byte ptr [rcx+1Ch], 8
0x18002b4aa  jz      short loc_18002B4C1
0x18002b4ac  mov     rcx, [rcx+10h]
0x18002b4b0  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002b4b7  mov     edx, 8Eh
0x18002b4bc  call    WPP_SF_
0x18002b4c1  xor     edi, edi
0x18002b4c3  xor     r9d, r9d; unsigned int *
0x18002b4c6  lea     rcx, [rbp+0E80h+var_EF0]; struct CRYPT_SERVER_CONTEXT *
0x18002b4ca  xor     r8d, r8d; unsigned __int16 **
0x18002b4cd  xor     edx, edx; void *
0x18002b4cf  call    ?CPSCreateServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@PEAXPEAPEBGPEAK@Z; CPSCreateServerContext(CRYPT_SERVER_CONTEXT *,void *,ushort const * *,ulong *)
0x18002b4d4  mov     ebx, eax
0x18002b4d6  test    eax, eax
0x18002b4d8  jz      short loc_18002B4FA
0x18002b4da  mov     r9d, 213Bh
0x18002b4e0  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002b4e7  lea     rdx, aDwret; "dwRet"
0x18002b4ee  mov     ecx, eax
0x18002b4f0  call    DebugTraceError
0x18002b4f5  jmp     loc_18002BE2B
0x18002b4fa  xor     r8d, r8d; int *
0x18002b4fd  mov     dword ptr [rsp+0F80h+TokenHandle], 1
0x18002b505  lea     rdx, [rsp+0F80h+TokenHandle]; int *
0x18002b50a  mov     r15d, edi
0x18002b50d  lea     rcx, [rbp+0E80h+var_EF0]; void *
0x18002b511  mov     r12d, edi
0x18002b514  mov     r13d, edi
0x18002b517  call    ?CPSOverrideToLocalSystem@@YAKPEAXPEAH1@Z; CPSOverrideToLocalSystem(void *,int *,int *)
0x18002b51c  lea     r9, [rbp+0E80h+var_EB8]; unsigned int *
0x18002b520  mov     [rsp+0F80h+var_F60], rdi; unsigned int *
0x18002b525  lea     rdx, [rbp+0E80h+var_EBC]; unsigned int *
0x18002b529  call    ?GetDefaultAlgInfo@@YAXPEAXPEAK111@Z; GetDefaultAlgInfo(void *,ulong *,ulong *,ulong *,ulong *)
0x18002b52e  mov     [rsp+0F80h+var_F50], rdi; unsigned int *
0x18002b533  lea     rcx, [rbp+0E80h+var_EF0]; void *
0x18002b537  mov     [rsp+0F80h+var_F58], rdi; unsigned int *
0x18002b53c  xor     r9d, r9d; struct DP_KEK *
0x18002b53f  xor     r8d, r8d; struct DP_KEK *
0x18002b542  mov     dword ptr [rsp+0F80h+var_F60], 2; unsigned int
0x18002b54a  xor     edx, edx; unsigned int
0x18002b54c  call    ?SynchronizeMasterKeys@@YAKPEAXKPEAUDP_KEK@@1KPEAK2@Z; SynchronizeMasterKeys(void *,ulong,DP_KEK *,DP_KEK *,ulong,ulong *,ulong *)
0x18002b551  mov     ebx, eax
0x18002b553  test    eax, eax
0x18002b555  jz      short loc_18002B577
0x18002b557  mov     r9d, 214Ch
0x18002b55d  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002b564  mov     ecx, eax
0x18002b566  lea     rdx, aDwret; "dwRet"
0x18002b56d  call    DebugTraceError
0x18002b572  jmp     loc_18002BDEA
0x18002b577  xor     r9d, r9d; unsigned int *
0x18002b57a  lea     rcx, [rbp+0E80h+var_2C0]; struct CRYPT_SERVER_CONTEXT *
0x18002b581  xor     r8d, r8d; unsigned __int16 **
0x18002b584  xor     edx, edx; void *
0x18002b586  call    ?CPSCreateServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@PEAXPEAPEBGPEAK@Z; CPSCreateServerContext(CRYPT_SERVER_CONTEXT *,void *,ushort const * *,ulong *)
0x18002b58b  mov     ebx, eax
0x18002b58d  test    eax, eax
0x18002b58f  jz      short loc_18002B599
0x18002b591  mov     r9d, 2159h
0x18002b597  jmp     short loc_18002B55D
0x18002b599  lea     r9, [rbp+0E80h+var_288]; unsigned int *
0x18002b5a0  mov     [rsp+0F80h+var_F60], rdi; unsigned int *
0x18002b5a5  xor     r8d, r8d; unsigned int *
0x18002b5a8  lea     rdx, [rbp+0E80h+var_28C]; unsigned int *
0x18002b5af  mov     r15d, 1
0x18002b5b5  call    ?GetDefaultAlgInfo@@YAXPEAXPEAK111@Z; GetDefaultAlgInfo(void *,ulong *,ulong *,ulong *,ulong *)
0x18002b5ba  mov     [rsp+0F80h+var_F50], rdi; unsigned int *
0x18002b5bf  lea     rcx, [rbp+0E80h+var_2C0]; void *
0x18002b5c6  mov     [rsp+0F80h+var_F58], rdi; unsigned int *
0x18002b5cb  xor     r9d, r9d; struct DP_KEK *
0x18002b5ce  xor     r8d, r8d; struct DP_KEK *
0x18002b5d1  mov     dword ptr [rsp+0F80h+var_F60], 2; unsigned int
0x18002b5d9  xor     edx, edx; unsigned int
0x18002b5db  call    ?SynchronizeMasterKeys@@YAKPEAXKPEAUDP_KEK@@1KPEAK2@Z; SynchronizeMasterKeys(void *,ulong,DP_KEK *,DP_KEK *,ulong,ulong *,ulong *)
0x18002b5e0  mov     ebx, eax
0x18002b5e2  test    eax, eax
0x18002b5e4  jz      short loc_18002B5F1
0x18002b5e6  mov     r9d, 2167h
0x18002b5ec  jmp     loc_18002B55D
0x18002b5f1  xor     r9d, r9d; unsigned int *
  ... truncated ...
```
