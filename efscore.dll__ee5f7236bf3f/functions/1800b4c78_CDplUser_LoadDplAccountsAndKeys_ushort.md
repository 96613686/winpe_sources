# CDplUser::LoadDplAccountsAndKeys(ushort *)

- ea: `0x1800b4c78`
- end: `0x1800b5a55`
- name: `?LoadDplAccountsAndKeys@CDplUser@@AEAAJPEAG@Z`
- size: `3549`
- prototype: `__int64 __fastcall(CDplUser *__hidden this, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800ab1d8`
- `0x1800b5a5c`
- `0x1800b9364`

## callees

- `0x180001a7c`
- `0x180001c34`
- `0x18000505d`
- `0x1800124d8`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800841d0`
- `0x180087d4c`
- `0x1800a2178`
- `0x1800aa5a4`
- `0x1800aada4`
- `0x1800ac870`
- `0x1800b3e5c`
- `0x1800b4c78`
- `0x1800bd7a8`
- `0x1800bd810`
- `0x1800d5af8`
- `0x1800d6064`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b52a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b52a0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b5233`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b5293`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b5233`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b5293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5914`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5914`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b50e2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b50e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b4e66`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b4e66`
- `RPCRT4!UuidFromStringW` at `0x1800b554e`
- `RPCRT4!UuidFromStringW` at `0x1800b554e`

## pseudocode

```c
__int64 __fastcall CDplUser::LoadDplAccountsAndKeys(const unsigned __int16 **this, unsigned __int16 *a2)
{
  int v2; // r14d
  UUID *v3; // rbx
  LPWSTR v5; // r13
  BYTE *v6; // rdi
  CDplAccount *v7; // rsi
  struct _GUID_ENTRY *v8; // r12
  int v9; // ecx
  int v10; // ecx
  LSTATUS v11; // eax
  DWORD v12; // edx
  bool v13; // cf
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // eax
  DWORD i; // ecx
  LSTATUS v19; // eax
  signed int v20; // ebx
  unsigned int v21; // edi
  __int64 v22; // rcx
  struct _GUID_ENTRY **v23; // rax
  unsigned __int16 *v24; // rbx
  unsigned __int16 *v25; // rdi
  __int64 *v26; // rax
  unsigned __int16 *v27; // rsi
  __int64 v28; // rcx
  int v29; // eax
  signed int LastError; // eax
  __int64 *v31; // rdx
  int v32; // eax
  signed int v33; // eax
  int v34; // eax
  unsigned __int16 *v35; // rdi
  int v36; // eax
  int v37; // ecx
  RPC_STATUS v38; // eax
  CDplUser **v39; // rcx
  UUID *v40; // rdx
  __int64 *v41; // rdi
  __int64 *v42; // rbx
  _QWORD *v43; // rax
  __int64 v44; // rdx
  _QWORD *v45; // rcx
  _QWORD *v46; // rcx
  __int64 ***v47; // rax
  _QWORD *v48; // rcx
  __int64 ***v49; // rax
  unsigned __int16 *v50; // rax
  unsigned __int16 **v51; // rdx
  unsigned __int16 *v52; // rax
  unsigned __int16 *v53; // rax
  unsigned __int16 *j; // r9
  unsigned int v55; // ecx
  __int64 v56; // r8
  int v57; // ecx
  unsigned int v58; // eax
  __int64 k; // rbx
  unsigned int v60; // r8d
  int v61; // r9d
  __int64 *v62; // rcx
  __int64 v63; // rax
  LPDWORD lpcSubKeys; // [rsp+20h] [rbp-A9h]
  LPDWORD lpcbMaxSubKeyLen; // [rsp+28h] [rbp-A1h]
  LPDWORD lpcbMaxClassLen; // [rsp+30h] [rbp-99h]
  __int64 *v68; // [rsp+60h] [rbp-69h] BYREF
  __int64 **v69; // [rsp+68h] [rbp-61h]
  LPBYTE lpData; // [rsp+70h] [rbp-59h] BYREF
  DWORD cchValueName; // [rsp+78h] [rbp-51h] BYREF
  DWORD cbMaxValueLen; // [rsp+7Ch] [rbp-4Dh] BYREF
  DWORD Type; // [rsp+80h] [rbp-49h] BYREF
  DWORD cbData; // [rsp+84h] [rbp-45h] BYREF
  int v75; // [rsp+88h] [rbp-41h] BYREF
  UUID *v76; // [rsp+90h] [rbp-39h] BYREF
  LPWSTR lpValueName; // [rsp+98h] [rbp-31h] BYREF
  unsigned __int16 *v78; // [rsp+A0h] [rbp-29h] BYREF
  CDplAccount *v79; // [rsp+A8h] [rbp-21h] BYREF
  unsigned int v80; // [rsp+B0h] [rbp-19h] BYREF
  int v81; // [rsp+B4h] [rbp-15h] BYREF
  DWORD v82; // [rsp+B8h] [rbp-11h]
  HKEY hKey; // [rsp+C0h] [rbp-9h] BYREF
  unsigned __int8 *v84; // [rsp+C8h] [rbp-1h] BYREF
  int v85; // [rsp+D0h] [rbp+7h]
  _QWORD v86[9]; // [rsp+D8h] [rbp+Fh]
  unsigned int v87; // [rsp+130h] [rbp+67h] BYREF
  LPCWCH lpString1; // [rsp+138h] [rbp+6Fh]
  DWORD cbMaxValueNameLen; // [rsp+140h] [rbp+77h] BYREF
  int v90; // [rsp+148h] [rbp+7Fh] BYREF

  lpString1 = a2;
  v2 = 0;
  Type = 0;
  v3 = 0;
  hKey = 0;
  lpValueName = 0;
  cchValueName = 0;
  cbMaxValueNameLen = 0;
  v87 = 0;
  v5 = 0;
  lpData = 0;
  v6 = 0;
  cbData = 0;
  cbMaxValueLen = 0;
  v7 = 0;
  v75 = 0;
  v8 = 0;
  v76 = 0;
  v86[0] = 0;
  v84 = 0;
  v80 = 0;
  v81 = 0;
  v78 = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 40, 205);
  v69 = &v68;
  v68 = (__int64 *)&v68;
  v85 = CDplUser::UserSvcLock((CDplUser *)this);
  if ( *((_DWORD *)this + 58) )
  {
    v8 = CDplUser::HasAccountDecryptionFailed((CDplUser *)this, (unsigned __int16 *)lpString1);
    if ( !v8 )
      goto LABEL_134;
  }
  fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 229);
  v2 = CDplUser::CheckCaller((PSID *)this);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v2,
              40,
              229) < 0 )
    goto LABEL_134;
  fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 233);
  v2 = EdpCredSvcOpenUserCredStore(this[13], 0x20019u, &hKey);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v2,
              40,
              233) < 0 )
    goto LABEL_134;
  v11 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v11 )
  {
    if ( v11 > 0 )
      v2 = (unsigned __int16)v11 | 0x80070000;
    else
      v2 = v11;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v2, 40, 254);
    goto LABEL_134;
  }
  if ( !cbMaxValueNameLen || !cbMaxValueLen )
  {
    *((_DWORD *)this + 58) = 1;
    goto LABEL_134;
  }
  fnEfsLogTrace1Strings(0, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 12);
  v12 = -1;
  LODWORD(lpcbMaxClassLen) = 4108;
  LODWORD(lpcbMaxSubKeyLen) = 40;
  v13 = cbMaxValueNameLen + 1 < cbMaxValueNameLen;
  if ( cbMaxValueNameLen + 1 >= cbMaxValueNameLen )
    v12 = cbMaxValueNameLen + 1;
  cbMaxValueNameLen = v12;
  v2 = v13 ? 0x80070216 : 0;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v2,
              (char)lpcbMaxSubKeyLen,
              (char)lpcbMaxClassLen) < 0 )
    goto LABEL_134;
  if ( cbMaxValueNameLen > 0x3FFF )
    cbMaxValueNameLen = 0x3FFF;
  fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 21);
  v2 = ULongLongToULong(2LL * cbMaxValueNameLen, &v87);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v2,
              40,
              21) < 0 )
    goto LABEL_134;
  fnEfsLogTrace1Strings(v15, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 30);
  v2 = DplibpMemAllocEx(v87, 0, 0, &lpValueName);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v2,
              40,
              30) < 0 )
  {
    v5 = lpValueName;
    goto LABEL_134;
  }
  fnEfsLogTrace1Strings(v16, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 39);
  v2 = DplibpMemAllocEx(cbMaxValueLen, 0, 0, &lpData);
  v17 = fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
          (unsigned int)&sourceString,
          v2,
          40,
          39);
  v5 = lpValueName;
  v6 = lpData;
  if ( v17 >= 0 )
  {
    v90 = 0;
    for ( i = 0; ; i = v82 + 1 )
    {
      cchValueName = cbMaxValueNameLen;
      cbData = cbMaxValueLen;
      v82 = i;
      Type = 0;
      v19 = RegEnumValueW(hKey, i, v5, &cchValueName, 0, &Type, v6, &cbData);
      v87 = v19;
      if ( v19 )
      {
        if ( v19 > 0 )
          v20 = (unsigned __int16)v19 | 0x80070000;
        else
          v20 = v19;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, v20, 40, 62);
        v21 = v87;
        if ( v87 == 259 )
        {
          ReleaseIf<CDplAccount>(v7);
          if ( v8 && v68 != (__int64 *)&v68 )
          {
            v22 = *(_QWORD *)v8;
            if ( *(struct _GUID_ENTRY **)(*(_QWORD *)v8 + 8LL) != v8
              || (v23 = (struct _GUID_ENTRY **)*((_QWORD *)v8 + 1), *v23 != v8) )
            {
LABEL_149:
              __fastfail(3u);
            }
            *v23 = (struct _GUID_ENTRY *)v22;
            *(_QWORD *)(v22 + 8) = v23;
            DplibMemFree(v8);
          }
          v24 = (unsigned __int16 *)(this + 25);
          while ( 1 )
          {
            v25 = (unsigned __int16 *)v68;
            if ( v68 == (__int64 *)&v68 )
              break;
            if ( (__int64 **)v68[1] != &v68 )
              goto LABEL_149;
            v26 = (__int64 *)*v68;
            if ( *(__int64 **)(*v68 + 8) != v68 )
              goto LABEL_149;
            v68 = (__int64 *)*v68;
            v26[1] = (__int64)&v68;
            v24 = (unsigned __int16 *)(this + 25);
            *((_QWORD *)v25 + 1) = v25;
            *(_QWORD *)v25 = v25;
            v27 = (unsigned __int16 *)this[25];
            while ( 1 )
            {
              if ( v27 == v24 )
                goto LABEL_114;
              if ( !memcmp_0(v27 - 32, v25 - 32, 0x10u) )
                break;
              v27 = *(unsigned __int16 **)v27;
              v79 = 0;
            }
            if ( v27 == (unsigned __int16 *)88 )
            {
LABEL_114:
              v53 = (unsigned __int16 *)this[26];
              if ( *(unsigned __int16 **)v53 != v24 )
                goto LABEL_149;
              *(_QWORD *)v25 = v24;
              *((_QWORD *)v25 + 1) = v53;
              *(_QWORD *)v53 = v25;
              this[26] = v25;
            }
            else
            {
              if ( *((_DWORD *)v25 + 12) )
              {
                if ( *((int *)this + 72) <= 0 )
                  MicrosoftTelemetryAssertTriggeredNoArgs(v28);
                _InterlockedDecrement((volatile signed __int32 *)this + 72);
              }
              if ( !*((_QWORD *)v25 - 3) && !*((_DWORD *)v27 + 14) )
              {
                if ( *((int *)this + 73) <= 0 )
                  MicrosoftTelemetryAssertTriggeredNoArgs(v28);
                _InterlockedDecrement((volatile signed __int32 *)this + 73);
              }
              if ( *((_QWORD *)v27 + 5) < *((_QWORD *)v25 + 5) )
              {
                v50 = *(unsigned __int16 **)v27;
                if ( *(unsigned __int16 **)(*(_QWORD *)v27 + 8LL) != v27 )
                  goto LABEL_149;
                v51 = (unsigned __int16 **)*((_QWORD *)v27 + 1);
                if ( *v51 != v27 )
                  goto LABEL_149;
                *v51 = v50;
                *((_QWORD *)v50 + 1) = v51;
                *((_QWORD *)v27 + 1) = v27;
                *(_QWORD *)v27 = v27;
                ReleaseIf<CDplAccount>(v27 - 44);
                v52 = (unsigned __int16 *)this[26];
                if ( *(unsigned __int16 **)v52 != v24 )
                  goto LABEL_149;
                *(_QWORD *)v25 = v24;
                *((_QWORD *)v25 + 1) = v52;
                *(_QWORD *)v52 = v25;
                this[26] = v25;
              }
              else
              {
                ReleaseIf<CDplAccount>(v25 - 44);
              }
            }
          }
          for ( j = *(unsigned __int16 **)v24; j != v24; j = *(unsigned __int16 **)j )
          {
            if ( *((_DWORD *)j + 29) )
            {
              v55 = 0;
              while ( *((_DWORD *)j + 30) != *((_DWORD *)&gc_ConsumerAccountLevelList + v55) )
              {
                if ( ++v55 >= 2 )
                {
                  v55 = -1;
                  break;
                }
              }
              v56 = v55;
              v57 = -1;
              v58 = *((_DWORD *)v86 + v56);
              if ( v58 + 1 >= v58 )
                v57 = v58 + 1;
              *((_DWORD *)v86 + v56) = v57;
            }
          }
          v7 = 0;
          for ( k = 0; k != 2; ++k )
          {
            if ( *((_DWORD *)v86 + k) > 1u
              && (unsigned int)dword_180114250 > 5
              && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
            {
              v90 = *((_DWORD *)&gc_ConsumerAccountLevelList + k);
              v79 = (CDplAccount *)0x1000000;
              v87 = v60;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_180114250,
                (unsigned int)byte_180103661,
                v60,
                v61,
                (__int64)&v90,
                (__int64)&v87,
                (__int64)&v79);
            }
          }
          v5 = lpValueName;
          *((_DWORD *)this + 58) = 1;
LABEL_133:
          v3 = v76;
          v6 = lpData;
          goto LABEL_134;
        }
        goto LABEL_84;
      }
      if ( Type == 3 && cchValueName > 0xB )
        break;
LABEL_86:
      ;
    }
    v29 = CompareStringOrdinal(L"EdpAccount_", 11, v5, 11, 0);
    if ( !v29 )
    {
      LastError = GetLastError();
      v20 = LastError;
      if ( LastError > 0 )
        v20 = (unsigned __int16)LastError | 0x80070000;
      LODWORD(lpcSubKeys) = 4192;
      goto LABEL_45;
    }
    if ( v29 != 2 )
      goto LABEL_86;
    if ( v8 && cchValueName >= 0x2F )
    {
      v32 = CompareStringOrdinal(lpString1, 36, v5 + 11, 36, 1);
      if ( !v32 )
      {
        v33 = GetLastError();
        v20 = v33;
        if ( v33 > 0 )
          v20 = (unsigned __int16)v33 | 0x80070000;
        LODWORD(lpcSubKeys) = 4222;
LABEL_45:
        v31 = EFS_TRACE_STATUS;
LABEL_82:
        fnEfsLogTrace1(g_hPublisher, (_DWORD)v31, v20, 40, (char)lpcSubKeys);
LABEL_83:
        v21 = v87;
LABEL_84:
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v20, 40, 80);
        if ( v21 != 234 )
        {
          if ( v2 >= 0 )
          {
            v2 = v20;
            fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, v20, 40, 97);
          }
          goto LABEL_133;
        }
LABEL_85:
        v6 = lpData;
        goto LABEL_86;
      }
      if ( v32 != 2 )
        goto LABEL_86;
    }
    v79 = (CDplAccount *)ReleaseIf<CDplAccount>(v7);
    v34 = DplpCreateObject1<CDplAccount,CDplUser *>(&v79, this);
    v20 = v34;
    if ( v34 < 0 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v34, 40, 150);
      v7 = v79;
      goto LABEL_83;
    }
    if ( v78 )
      DplibMemFree(v78);
    v78 = 0;
    v7 = v79;
    v20 = CDplAccount::VerifyAndUnprotectSerialAccountBlob(v79, v6, cbData, v5, 0, &v75, &v84, &v80, &v81, &v78);
    if ( v20 >= 0 )
    {
      v20 = CDplAccount::Deserialize(v7, v84, v80, v78);
      if ( v81 )
      {
        *((_DWORD *)v7 + 40) = 1;
        *((_DWORD *)v7 + 42) = 1;
        *((_DWORD *)this + 71) = 1;
      }
    }
    if ( v20 == -2147024809 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 40, 195);
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)L"bIsDecryptionFailure = ",
        v75,
        40,
        196);
      v35 = 0;
      if ( cchValueName >= 0x2F )
      {
        v36 = v5[47];
        v35 = v5 + 11;
        v5[47] = 0;
        v90 = v36;
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (_DWORD)v5 + 22,
          0,
          40,
          208);
      }
      if ( v75 && !v8 && v35 && !CDplUser::HasAccountDecryptionFailed((CDplUser *)this, v35) )
      {
        fnEfsLogTrace1Strings(v37, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 221);
        v20 = DplibpMemAllocEx(32, 0, 0, &v76);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    v20,
                    40,
                    221) < 0 )
        {
          if ( (_WORD)v90 )
          {
            v5[47] = v90;
            v90 = 0;
          }
          goto LABEL_83;
        }
        fnEfsLogTrace1Strings(0, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 231);
        v38 = UuidFromStringW(v35, v76 + 1);
        LODWORD(lpcbMaxClassLen) = 4327;
        LODWORD(lpcbMaxSubKeyLen) = 40;
        v20 = 0;
        if ( v38 )
          v20 = v38 | 0x80010000;
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    v20,
                    (char)lpcbMaxSubKeyLen,
                    (char)lpcbMaxClassLen) < 0 )
        {
          if ( (_WORD)v90 )
          {
            v5[47] = v90;
            v90 = 0;
          }
          goto LABEL_83;
        }
        v39 = (CDplUser **)this[28];
        if ( *v39 != (CDplUser *)(this + 27) )
          goto LABEL_149;
        v40 = v76;
        v76 = 0;
        *(_QWORD *)&v40->Data1 = this + 27;
        *(_QWORD *)v40->Data4 = v39;
        *v39 = (CDplUser *)v40;
        this[28] = (const unsigned __int16 *)v40;
      }
      if ( (_WORD)v90 )
      {
        v5[47] = v90;
        v90 = 0;
      }
    }
    else
    {
      if ( v20 < 0 )
      {
        LODWORD(lpcSubKeys) = 4358;
        v31 = EFS_TRACE_ERROR;
        goto LABEL_82;
      }
      v41 = v68;
      if ( v68 == (__int64 *)&v68 )
        goto LABEL_96;
      do
      {
        v42 = v41 - 11;
        if ( !memcmp_0((char *)v7 + 24, v41 - 8, 0x10u) )
          break;
        v41 = (__int64 *)*v41;
        v42 = 0;
      }
      while ( v41 != (__int64 *)&v68 );
      v5 = lpValueName;
      if ( !v42 )
      {
LABEL_96:
        v48 = v69;
        if ( *v69 != (__int64 *)&v68 )
          goto LABEL_149;
        v49 = (__int64 ***)((char *)v7 + 88);
        v7 = 0;
        v49[1] = v69;
        *v49 = &v68;
        *v48 = v49;
        v69 = (__int64 **)v49;
      }
      else if ( (unsigned __int64)v42[16] < *((_QWORD *)v7 + 16) )
      {
        v43 = v42 + 11;
        v44 = v42[11];
        if ( *(__int64 **)(v44 + 8) != v42 + 11 )
          goto LABEL_149;
        v45 = (_QWORD *)v42[12];
        if ( (_QWORD *)*v45 != v43 )
          goto LABEL_149;
        *v45 = v44;
        *(_QWORD *)(v44 + 8) = v45;
        v42[12] = (__int64)v43;
        *v43 = v43;
        v46 = v69;
        if ( *v69 != (__int64 *)&v68 )
          goto LABEL_149;
        v47 = (__int64 ***)((char *)v7 + 88);
        v7 = (CDplAccount *)v42;
        v47[1] = v69;
        *v47 = &v68;
        *v46 = v47;
        v69 = (__int64 **)v47;
      }
    }
    goto LABEL_85;
  }
LABEL_134:
  CDplUser::UserSvcUnlock((CDplUser *)this, v85);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  ReleaseIf<CDplAccount>(v7);
  if ( v78 )
    DplibMemFree(v78);
  v78 = 0;
  if ( v84 )
    DplibMemFree(v84);
  v84 = 0;
  while ( 1 )
  {
    v62 = v68;
    if ( v68 == (__int64 *)&v68 )
      break;
    if ( (__int64 **)v68[1] != &v68 )
      goto LABEL_149;
    v63 = *v68;
    if ( *(__int64 **)(*v68 + 8) != v68 )
      goto LABEL_149;
    v68 = (__int64 *)*v68;
    *(_QWORD *)(v63 + 8) = &v68;
    v62[1] = (__int64)v62;
    *v62 = (__int64)v62;
    ReleaseIf<CDplAccount>(v62 - 11);
  }
  if ( v5 )
    DplibMemFree(v5);
  if ( v6 )
    DplibMemFree(v6);
  if ( v3 )
    DplibMemFree(v3);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v2,
    40,
    33);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800b4c78  mov     [rsp-8+lpString1], rdx
0x1800b4c7d  push    rbp
0x1800b4c7e  push    rbx
0x1800b4c7f  push    rsi
0x1800b4c80  push    rdi
0x1800b4c81  push    r12
0x1800b4c83  push    r13
0x1800b4c85  push    r14
0x1800b4c87  push    r15
0x1800b4c89  lea     rbp, [rsp-1Fh]
0x1800b4c8e  sub     rsp, 0E8h
0x1800b4c95  xor     r14d, r14d
0x1800b4c98  mov     dword ptr [rsp+120h+lpcSubKeys], 0FCDh
0x1800b4ca0  xorps   xmm0, xmm0
0x1800b4ca3  mov     [rbp+57h+Type], r14d
0x1800b4ca7  mov     ebx, r14d
0x1800b4caa  mov     [rbp+57h+hKey], r14
0x1800b4cae  lea     r8, sourceString
0x1800b4cb5  mov     [rbp+57h+lpValueName], r14
0x1800b4cb9  lea     r9d, [r14+28h]
0x1800b4cbd  mov     [rbp+57h+cchValueName], r14d
0x1800b4cc1  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800b4cc8  mov     [rbp+57h+cbMaxValueNameLen], r14d
0x1800b4ccc  mov     r15, rcx
0x1800b4ccf  mov     [rbp+57h+arg_0], r14d
0x1800b4cd3  movups  [rbp+57h+var_C0], xmm0
0x1800b4cd7  mov     r13d, r14d
0x1800b4cda  mov     [rbp+57h+lpData], r14
0x1800b4cde  mov     edi, r14d
0x1800b4ce1  mov     [rbp+57h+cbData], r14d
0x1800b4ce5  mov     [rbp+57h+cbMaxValueLen], r14d
0x1800b4ce9  mov     esi, r14d
0x1800b4cec  mov     [rbp+57h+var_98], r14d
0x1800b4cf0  mov     r12d, r14d
0x1800b4cf3  mov     [rbp+57h+var_90], rbx
0x1800b4cf7  mov     [rbp+57h+var_48], r14
0x1800b4cfb  mov     [rbp+57h+var_58], r14
0x1800b4cff  mov     [rbp+57h+var_70], r14d
0x1800b4d03  mov     [rbp+57h+var_6C], r14d
0x1800b4d07  mov     [rbp+57h+var_80], r14
0x1800b4d0b  call    fnEfsLogTrace1Strings
0x1800b4d10  lea     rax, [rbp+57h+var_C0]
0x1800b4d14  mov     rcx, r15; this
0x1800b4d17  mov     qword ptr [rbp+57h+var_C0+8], rax
0x1800b4d1b  lea     rax, [rbp+57h+var_C0]
0x1800b4d1f  mov     qword ptr [rbp+57h+var_C0], rax
0x1800b4d23  call    ?UserSvcLock@CDplUser@@AEAAHXZ; CDplUser::UserSvcLock(void)
0x1800b4d28  mov     [rbp+57h+var_50], eax
0x1800b4d2b  cmp     [r15+0E8h], r14d
0x1800b4d32  jz      short loc_1800B4D4C
0x1800b4d34  mov     rdx, [rbp+57h+lpString1]; unsigned __int16 *
0x1800b4d38  mov     rcx, r15; this
0x1800b4d3b  call    ?HasAccountDecryptionFailed@CDplUser@@AEAAPEAU_GUID_ENTRY@@PEAG@Z; CDplUser::HasAccountDecryptionFailed(ushort *)
0x1800b4d40  mov     r12, rax
0x1800b4d43  test    rax, rax
0x1800b4d46  jz      loc_1800B58FD
0x1800b4d4c  mov     r9d, 28h ; '('
0x1800b4d52  mov     dword ptr [rsp+120h+lpcSubKeys], 0FE5h
0x1800b4d5a  lea     r8, sourceString
0x1800b4d61  lea     rdx, EFS_TRACE_START_EVENT
0x1800b4d68  call    fnEfsLogTrace1Strings
0x1800b4d6d  mov     rcx, r15; this
0x1800b4d70  call    ?CheckCaller@CDplUser@@AEAAJXZ; CDplUser::CheckCaller(void)
0x1800b4d75  mov     rcx, cs:g_hPublisher
0x1800b4d7c  lea     r9, sourceString
0x1800b4d83  mov     dword ptr [rsp+120h+lpcbMaxClassLen], 0FE5h
0x1800b4d8b  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800b4d92  mov     dword ptr [rsp+120h+lpcbMaxSubKeyLen], 28h ; '('
0x1800b4d9a  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800b4da1  mov     dword ptr [rsp+120h+lpcSubKeys], eax
0x1800b4da5  mov     r14d, eax
0x1800b4da8  call    fnEfsLogTrace1String1Dword
0x1800b4dad  test    eax, eax
0x1800b4daf  js      loc_1800B58FD
0x1800b4db5  mov     r9d, 28h ; '('
0x1800b4dbb  mov     dword ptr [rsp+120h+lpcSubKeys], 0FE9h
0x1800b4dc3  lea     r8, sourceString
0x1800b4dca  lea     rdx, EFS_TRACE_START_EVENT
0x1800b4dd1  call    fnEfsLogTrace1Strings
0x1800b4dd6  mov     rcx, [r15+68h]; unsigned __int16 *
0x1800b4dda  lea     r8, [rbp+57h+hKey]; phkResult
0x1800b4dde  mov     edx, 20019h; samDesired
0x1800b4de3  call    ?EdpCredSvcOpenUserCredStore@@YAJPEBGKPEAPEAUHKEY__@@@Z; EdpCredSvcOpenUserCredStore(ushort const *,ulong,HKEY__ * *)
0x1800b4de8  mov     rcx, cs:g_hPublisher
0x1800b4def  lea     r9, sourceString
0x1800b4df6  mov     dword ptr [rsp+120h+lpcbMaxClassLen], 0FE9h
0x1800b4dfe  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800b4e05  mov     dword ptr [rsp+120h+lpcbMaxSubKeyLen], 28h ; '('
0x1800b4e0d  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800b4e14  mov     dword ptr [rsp+120h+lpcSubKeys], eax
0x1800b4e18  mov     r14d, eax
0x1800b4e1b  call    fnEfsLogTrace1String1Dword
0x1800b4e20  xor     ecx, ecx
0x1800b4e22  test    eax, eax
0x1800b4e24  js      loc_1800B58FD
0x1800b4e2a  mov     [rsp+120h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x1800b4e2f  lea     rax, [rbp+57h+cbMaxValueLen]
0x1800b4e33  mov     [rsp+120h+lpcbSecurityDescriptor], rcx; lpcbSecurityDescriptor
0x1800b4e38  xor     r9d, r9d; lpReserved
0x1800b4e3b  mov     [rsp+120h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800b4e40  xor     r8d, r8d; lpcchClass
0x1800b4e43  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x1800b4e47  xor     edx, edx; lpClass
0x1800b4e49  mov     [rsp+120h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800b4e4e  mov     [rsp+120h+lpcValues], rcx; lpcValues
0x1800b4e53  mov     [rsp+120h+lpcbMaxClassLen], rcx; lpcbMaxClassLen
0x1800b4e58  mov     [rsp+120h+lpcbMaxSubKeyLen], rcx; lpcbMaxSubKeyLen
0x1800b4e5d  mov     [rsp+120h+lpcSubKeys], rcx; lpcSubKeys
0x1800b4e62  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b4e66  call    cs:__imp_RegQueryInfoKeyW
0x1800b4e6c  xor     ecx, ecx
0x1800b4e6e  test    eax, eax
0x1800b4e70  jz      short loc_1800B4EAD
0x1800b4e72  jg      short loc_1800B4E79
0x1800b4e74  mov     r14d, eax
0x1800b4e77  jmp     short loc_1800B4E84
0x1800b4e79  movzx   r14d, ax
0x1800b4e7d  or      r14d, 80070000h
0x1800b4e84  mov     rcx, cs:g_hPublisher
0x1800b4e8b  lea     rdx, EFS_TRACE_ERROR
0x1800b4e92  mov     r9d, 28h ; '('
0x1800b4e98  mov     dword ptr [rsp+120h+lpcSubKeys], 0FFEh
0x1800b4ea0  mov     r8d, r14d
0x1800b4ea3  call    fnEfsLogTrace1
0x1800b4ea8  jmp     loc_1800B58FD
0x1800b4ead  cmp     [rbp+57h+cbMaxValueNameLen], ecx
0x1800b4eb0  jz      loc_1800B59CA
0x1800b4eb6  cmp     [rbp+57h+cbMaxValueLen], ecx
0x1800b4eb9  jz      loc_1800B59CA
0x1800b4ebf  mov     r9d, 28h ; '('
0x1800b4ec5  mov     dword ptr [rsp+120h+lpcSubKeys], 100Ch
0x1800b4ecd  lea     r8, sourceString
0x1800b4ed4  lea     rdx, EFS_TRACE_START_EVENT
0x1800b4edb  call    fnEfsLogTrace1Strings
0x1800b4ee0  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x1800b4ee3  lea     r9, sourceString
0x1800b4eea  or      edx, 0FFFFFFFFh
0x1800b4eed  mov     dword ptr [rsp+120h+lpcbMaxClassLen], 100Ch
0x1800b4ef5  mov     dword ptr [rsp+120h+lpcbMaxSubKeyLen], 28h ; '('
0x1800b4efd  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800b4f04  lea     eax, [rcx+1]
0x1800b4f07  cmp     eax, ecx
0x1800b4f09  mov     rcx, cs:g_hPublisher
0x1800b4f10  cmovnb  edx, eax
0x1800b4f13  sbb     r14d, r14d
0x1800b4f16  mov     [rbp+57h+cbMaxValueNameLen], edx
0x1800b4f19  and     r14d, 80070216h
0x1800b4f20  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800b4f27  mov     dword ptr [rsp+120h+lpcSubKeys], r14d
0x1800b4f2c  call    fnEfsLogTrace1String1Dword
0x1800b4f31  test    eax, eax
0x1800b4f33  js      loc_1800B58FD
0x1800b4f39  mov     eax, 3FFFh
0x1800b4f3e  cmp     [rbp+57h+cbMaxValueNameLen], eax
0x1800b4f41  jbe     short loc_1800B4F46
0x1800b4f43  mov     [rbp+57h+cbMaxValueNameLen], eax
0x1800b4f46  mov     r9d, 28h ; '('
0x1800b4f4c  mov     dword ptr [rsp+120h+lpcSubKeys], 1015h
0x1800b4f54  lea     r8, sourceString
0x1800b4f5b  lea     rdx, EFS_TRACE_START_EVENT
0x1800b4f62  call    fnEfsLogTrace1Strings
0x1800b4f67  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x1800b4f6a  lea     rdx, [rbp+57h+arg_0]; unsigned int *
0x1800b4f6e  add     rcx, rcx; unsigned __int64
0x1800b4f71  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800b4f76  mov     rcx, cs:g_hPublisher
0x1800b4f7d  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800b4f84  mov     dword ptr [rsp+120h+lpcbMaxClassLen], 1015h
0x1800b4f8c  lea     r9, sourceString
0x1800b4f93  mov     dword ptr [rsp+120h+lpcbMaxSubKeyLen], 28h ; '('
0x1800b4f9b  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800b4fa2  mov     dword ptr [rsp+120h+lpcSubKeys], eax
0x1800b4fa6  mov     r14d, eax
0x1800b4fa9  call    fnEfsLogTrace1String1Dword
0x1800b4fae  test    eax, eax
0x1800b4fb0  js      loc_1800B58FD
0x1800b4fb6  mov     r13d, 101Eh
0x1800b4fbc  lea     r8, sourceString
0x1800b4fc3  mov     r9d, 28h ; '('
0x1800b4fc9  mov     dword ptr [rsp+120h+lpcSubKeys], r13d
0x1800b4fce  lea     rdx, EFS_TRACE_START_EVENT
0x1800b4fd5  call    fnEfsLogTrace1Strings
0x1800b4fda  mov     ecx, [rbp+57h+arg_0]
0x1800b4fdd  lea     r9, [rbp+57h+lpValueName]
0x1800b4fe1  xor     r8d, r8d
0x1800b4fe4  xor     edx, edx
0x1800b4fe6  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800b4feb  mov     rcx, cs:g_hPublisher
0x1800b4ff2  lea     r9, sourceString
0x1800b4ff9  mov     dword ptr [rsp+120h+lpcbMaxClassLen], r13d
0x1800b4ffe  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800b5005  mov     r13d, 28h ; '('
0x1800b500b  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800b5012  mov     dword ptr [rsp+120h+lpcbMaxSubKeyLen], r13d
0x1800b5017  mov     r14d, eax
0x1800b501a  mov     dword ptr [rsp+120h+lpcSubKeys], eax
0x1800b501e  call    fnEfsLogTrace1String1Dword
0x1800b5023  test    eax, eax
0x1800b5025  js      loc_1800B59C1
0x1800b502b  mov     edi, 1027h
0x1800b5030  lea     r8, sourceString
0x1800b5037  mov     r9d, r13d
0x1800b503a  mov     dword ptr [rsp+120h+lpcSubKeys], edi
0x1800b503e  lea     rdx, EFS_TRACE_START_EVENT
0x1800b5045  call    fnEfsLogTrace1Strings
0x1800b504a  mov     ecx, [rbp+57h+cbMaxValueLen]
0x1800b504d  lea     r9, [rbp+57h+lpData]
0x1800b5051  xor     r8d, r8d
0x1800b5054  xor     edx, edx
0x1800b5056  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800b505b  mov     rcx, cs:g_hPublisher
0x1800b5062  lea     r9, sourceString
0x1800b5069  mov     dword ptr [rsp+120h+lpcbMaxClassLen], edi
0x1800b506d  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800b5074  mov     dword ptr [rsp+120h+lpcbMaxSubKeyLen], r13d
0x1800b5079  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800b5080  mov     dword ptr [rsp+120h+lpcSubKeys], eax
0x1800b5084  mov     r14d, eax
0x1800b5087  call    fnEfsLogTrace1String1Dword
0x1800b508c  mov     r13, [rbp+57h+lpValueName]
0x1800b5090  xor     r8d, r8d
0x1800b5093  mov     rdi, [rbp+57h+lpData]
0x1800b5097  test    eax, eax
0x1800b5099  js      loc_1800B58FD
0x1800b509f  mov     [rbp+57h+arg_18], r8d
0x1800b50a3  mov     ecx, r8d
0x1800b50a6  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1800b50a9  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800b50ad  mov     [rbp+57h+cchValueName], eax
0x1800b50b0  mov     edx, ecx; dwIndex
0x1800b50b2  mov     eax, [rbp+57h+cbMaxValueLen]
0x1800b50b5  mov     [rbp+57h+cbData], eax
0x1800b50b8  lea     rax, [rbp+57h+cbData]
0x1800b50bc  mov     [rsp+120h+lpcValues], rax; lpcbData
0x1800b50c1  lea     rax, [rbp+57h+Type]
0x1800b50c5  mov     [rsp+120h+lpcbMaxClassLen], rdi; lpData
0x1800b50ca  mov     [rsp+120h+lpcbMaxSubKeyLen], rax; lpType
0x1800b50cf  mov     [rsp+120h+lpcSubKeys], r8; lpReserved
0x1800b50d4  mov     [rbp+57h+var_68], ecx
0x1800b50d7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b50db  mov     [rbp+57h+Type], r8d
0x1800b50df  mov     r8, r13; lpValueName
0x1800b50e2  call    cs:__imp_RegEnumValueW
0x1800b50e8  xor     r8d, r8d
0x1800b50eb  mov     [rbp+57h+arg_0], eax
0x1800b50ee  test    eax, eax
0x1800b50f0  jz      loc_1800B5207
0x1800b50f6  jg      short loc_1800B50FC
0x1800b50f8  mov     ebx, eax
0x1800b50fa  jmp     short loc_1800B5105
0x1800b50fc  movzx   ebx, ax
0x1800b50ff  or      ebx, 80070000h
0x1800b5105  mov     rcx, cs:g_hPublisher
0x1800b510c  lea     rdx, EFS_TRACE_STATUS
0x1800b5113  mov     r9d, 28h ; '('
0x1800b5119  mov     dword ptr [rsp+120h+lpcSubKeys], 103Eh
0x1800b5121  mov     r8d, ebx
0x1800b5124  call    fnEfsLogTrace1
0x1800b5129  mov     edi, [rbp+57h+arg_0]
0x1800b512c  cmp     edi, 103h
0x1800b5132  jnz     loc_1800B561C
0x1800b5138  mov     rcx, rsi
0x1800b513b  call    ??$ReleaseIf@VCDplAccount@@@@YAPEAVCDplAccount@@PEAV0@@Z; ReleaseIf<CDplAccount>(CDplAccount *)
0x1800b5140  xor     r10d, r10d
0x1800b5143  test    r12, r12
0x1800b5146  jz      short loc_1800B5180
0x1800b5148  lea     rax, [rbp+57h+var_C0]
0x1800b514c  cmp     qword ptr [rbp+57h+var_C0], rax
0x1800b5150  jz      short loc_1800B5180
0x1800b5152  mov     rcx, [r12]
0x1800b5156  cmp     [rcx+8], r12
0x1800b515a  jnz     loc_1800B59DA
0x1800b5160  mov     rax, [r12+8]
0x1800b5165  cmp     [rax], r12
0x1800b5168  jnz     loc_1800B59DA
0x1800b516e  mov     [rax], rcx
0x1800b5171  mov     [rcx+8], rax
0x1800b5175  mov     rcx, r12; void *
0x1800b5178  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800b517d  xor     r10d, r10d
0x1800b5180  lea     rbx, [r15+0C8h]
0x1800b5187  mov     rdi, qword ptr [rbp+57h+var_C0]
0x1800b518b  lea     rax, [rbp+57h+var_C0]
0x1800b518f  cmp     rdi, rax
0x1800b5192  jz      loc_1800B5813
0x1800b5198  lea     rax, [rbp+57h+var_C0]
0x1800b519c  cmp     [rdi+8], rax
0x1800b51a0  jnz     loc_1800B59DA
0x1800b51a6  mov     rax, [rdi]
0x1800b51a9  cmp     [rax+8], rdi
0x1800b51ad  jnz     loc_1800B59DA
0x1800b51b3  mov     qword ptr [rbp+57h+var_C0], rax
0x1800b51b7  lea     rcx, [rbp+57h+var_C0]
0x1800b51bb  mov     [rax+8], rcx
0x1800b51bf  lea     rbx, [r15+0C8h]
0x1800b51c6  mov     [rdi+8], rdi
0x1800b51ca  mov     [rdi], rdi
0x1800b51cd  mov     rsi, [rbx]
0x1800b51d0  cmp     rsi, rbx
0x1800b51d3  jz      loc_1800B57F3
  ... truncated ...
```
