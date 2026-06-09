# LsapSetSystemAccessAccount(void *,ulong,int)

- ea: `0x18011b79c`
- end: `0x18011bf6b`
- name: `?LsapSetSystemAccessAccount@@YAJPEAXKH@Z`
- size: `1999`
- prototype: `__int64 __fastcall(struct _LSAP_DB_HANDLE *, unsigned int, int)`
- caller_count: `5`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180021940`
- `0x180111d00`
- `0x180118278`
- `0x18011c470`
- `0x1801206c0`

## callees

- `0x18000c300`
- `0x18000ddc0`
- `0x180010ba0`
- `0x180011278`
- `0x180053dec`
- `0x180073b20`
- `0x18007cb90`
- `0x18007fcb0`
- `0x18008d370`
- `0x180097c3c`
- `0x1800ada18`
- `0x1800b1ecc`
- `0x1800b9304`
- `0x1800bc040`
- `0x1801082a8`
- `0x18010bf74`
- `0x18011ac68`
- `0x18011ad84`
- `0x18011b79c`
- `0x18011d35c`

## import_xrefs

- `LSAADT!__imp_LsapQueryClientInfo` at `0x18011baad`
- `LSAADT!__imp_LsapQueryClientInfo` at `0x18011baad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18011ba53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18011ba53`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18011b933`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18011b933`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011b8b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011b8b2`
- `ntdll!RtlReleaseResource` at `0x18011bef1`
- `ntdll!RtlReleaseResource` at `0x18011bef1`
- `ntdll!RtlAcquireResourceShared` at `0x18011b94f`
- `ntdll!RtlAcquireResourceShared` at `0x18011b94f`
- `ntdll!RtlLeaveCriticalSection` at `0x18011b915`
- `ntdll!RtlLeaveCriticalSection` at `0x18011b915`
- `ntdll!RtlEnterCriticalSection` at `0x18011b8ef`
- `ntdll!RtlEnterCriticalSection` at `0x18011b8ef`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18011be97`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18011be97`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtGenerateLsaAuditSystemAccessChange` at `0x18011bd4b`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtGenerateLsaAuditSystemAccessChange` at `0x18011be0a`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtGenerateLsaAuditSystemAccessChange` at `0x18011bd4b`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtGenerateLsaAuditSystemAccessChange` at `0x18011be0a`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x18011bad2`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x18011bad2`

## string_xrefs

- `0x18011bb6f`: `SeServiceLogonRight`
- `0x18011bbd4`: `SeDenyServiceLogonRight`
- `0x18011bc9d`: `SeDenyServiceLogonRight`

## pseudocode

```c
__int64 __fastcall LsapSetSystemAccessAccount(struct _LSAP_DB_HANDLE *a1, unsigned int a2, int a3)
{
  bool v3; // di
  char v4; // r12
  char *v5; // r15
  _DWORD *v6; // r13
  void *v9; // rdx
  int v10; // esi
  HLOCAL v11; // rdi
  const unsigned __int16 *v12; // r9
  int v13; // eax
  struct _LSAP_DB_ACCOUNT *v14; // rcx
  NLRefcountableObjectWithLock *v15; // rbx
  unsigned int v16; // r14d
  struct _ACCT_TABLE_ENTRY *v17; // rax
  int v18; // eax
  int v19; // edx
  const WCHAR *v20; // rcx
  const WCHAR *v21; // r8
  __int64 v22; // rdi
  const WCHAR *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  struct _RTL_BALANCED_NODE *v29; // r12
  __int64 v30; // r14
  __int64 v31; // r14
  char *v32; // r13
  char v34; // [rsp+41h] [rbp-BFh] BYREF
  char v35; // [rsp+42h] [rbp-BEh]
  char v36; // [rsp+43h] [rbp-BDh]
  unsigned int v37; // [rsp+48h] [rbp-B8h] BYREF
  char *v38; // [rsp+50h] [rbp-B0h]
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD *v40; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h] BYREF
  struct _RTL_BALANCED_NODE *v42; // [rsp+70h] [rbp-90h] BYREF
  struct _LSAP_DB_ACCOUNT *v43; // [rsp+78h] [rbp-88h] BYREF
  struct _LSAP_DB_HANDLE *v44; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v45[10]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v46[16]; // [rsp+E0h] [rbp-20h] BYREF

  v3 = 0;
  v44 = a1;
  v4 = 0;
  v36 = 0;
  v5 = 0;
  v35 = 0;
  v6 = 0;
  v40 = 0;
  v34 = 0;
  v41 = 0;
  v42 = 0;
  hMem = 0;
  v37 = a2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 31, &WPP_dde5ba64ca46380d90069aada4d87825_Traceguids);
  v10 = LsapDbVerifyHandle((__int64)a1, 0, 3u, 0);
  if ( v10 >= 0 )
  {
    v5 = (char *)*((_QWORD *)a1 + 11);
    v38 = v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 12), 0x20u, &WPP_dde5ba64ca46380d90069aada4d87825_Traceguids, v5);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      LsapDsGetCallerInfo(WPP_GLOBAL_Control, (unsigned __int16 **)&hMem);
      v11 = hMem;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v12 = L"Unknown";
        if ( hMem )
          v12 = (const unsigned __int16 *)hMem;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 33, &WPP_dde5ba64ca46380d90069aada4d87825_Traceguids, v12);
      }
      LocalFree(v11);
      v3 = 0;
    }
    if ( v37 != (v37 & 0xFF7) )
    {
      v10 = -1073741811;
      goto LABEL_116;
    }
    if ( *((_BYTE *)a1 + 50) )
      goto LABEL_22;
    if ( !a3 )
    {
LABEL_21:
      v35 = 1;
LABEL_22:
      v10 = LsapDbReferenceObject(a1, 8u, 3u, 3u, 67108873);
      if ( v10 >= 0 )
      {
        v4 = 1;
        if ( dword_18019F50C == 4 )
        {
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::GetImpl'::`2'::impl) )
            v13 = LsapDbCacheQueryInformationAccount(a1, 1, &v40);
          else
            v13 = LsapDbCacheQueryInformationAccountOld(a1, 1, &v40);
          v6 = v40;
          v3 = v13 >= 0;
        }
        LODWORD(hMem) = LsapDbWriteAttributeObject(a1, &stru_18019E9F0, &v37, 4u);
        v10 = (int)hMem;
        if ( (int)hMem >= 0 )
        {
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::GetImpl'::`2'::impl) )
          {
            v15 = gpLsaAccountCache;
            if ( gpLsaAccountCache )
            {
              v16 = v37;
              NLRefcountableObjectWithLock::LockExclusive(gpLsaAccountCache);
              v17 = LsaAccountCache::TableLookup(v15, v5);
              if ( v17 )
                *((_DWORD *)v17 + 2) = v16;
              *((_DWORD *)v15 + 6) = 0;
              ReleaseSRWLockExclusive((PSRWLOCK)v15 + 2);
            }
          }
          else
          {
            v43 = 0;
            if ( dword_18019F50C == 4 && (int)LsapDbLookupAccount(v5, &v43) >= 0 )
            {
              v14 = v43;
              *((_DWORD *)v43 + 6) = v37;
            }
          }
          if ( (unsigned __int8)IsLsapAdtInitializeCrashOnAuditFailPresent(v14) )
          {
            v18 = LsapQueryClientInfo(&v42, &v41);
            if ( v18 >= 0 )
              v18 = LsapAdtAuditingEnabledByLogonId(141, &v41, 8, &v34);
            if ( v3 && v18 >= 0 && v34 )
            {
              memset_0(v45, 0, sizeof(v45));
              memset_0(v46, 0, 0x50u);
              v19 = v37;
              if ( v6 )
                v20 = (const WCHAR *)(v37 & ~*v6);
              else
                v20 = (const WCHAR *)v37;
              v21 = L"SeInteractiveLogonRight";
              v22 = (unsigned __int8)v20 & 1;
              v23 = L"SeInteractiveLogonRight";
              if ( ((unsigned __int8)v20 & 1) == 0 )
                v23 = (const WCHAR *)v45[0];
              v45[0] = v23;
              if ( ((unsigned __int8)v20 & 2) != 0 )
              {
                v45[v22] = L"SeNetworkLogonRight";
                v22 = (unsigned int)(v22 + 1);
              }
              if ( ((unsigned __int8)v20 & 4) != 0 )
              {
                v45[v22] = L"SeBatchLogonRight";
                v22 = (unsigned int)(v22 + 1);
              }
              if ( ((unsigned __int8)v20 & 0x10) != 0 )
              {
                v45[v22] = L"SeServiceLogonRight";
                v22 = (unsigned int)(v22 + 1);
              }
              if ( ((unsigned __int16)v20 & 0x400) != 0 )
              {
                v45[v22] = L"SeRemoteInteractiveLogonRight";
                v22 = (unsigned int)(v22 + 1);
              }
              if ( ((unsigned __int8)v20 & 0x40) != 0 )
              {
                v45[v22] = L"SeDenyInteractiveLogonRight";
                v22 = (unsigned int)(v22 + 1);
              }
              if ( (char)v20 < 0 )
              {
                v45[v22] = L"SeDenyNetworkLogonRight";
                v22 = (unsigned int)(v22 + 1);
              }
              if ( ((unsigned __int16)v20 & 0x100) != 0 )
              {
                v45[v22] = L"SeDenyBatchLogonRight";
                LODWORD(v22) = v22 + 1;
              }
              if ( ((unsigned __int16)v20 & 0x200) != 0 )
              {
                v24 = (int)v22;
                LODWORD(v22) = v22 + 1;
                v45[v24] = L"SeDenyServiceLogonRight";
              }
              if ( ((unsigned __int16)v20 & 0x800) != 0 )
              {
                v25 = (int)v22;
                LODWORD(v22) = v22 + 1;
                v45[v25] = L"SeDenyRemoteInteractiveLogonRight";
              }
              if ( v6 )
                v19 = *v6 & ~v19;
              v26 = v19 & 1;
              if ( (v19 & 1) == 0 )
                v21 = (const WCHAR *)v46[0];
              v46[0] = v21;
              if ( (v19 & 2) != 0 )
              {
                v46[v26] = L"SeNetworkLogonRight";
                v26 = (unsigned int)(v26 + 1);
              }
              if ( (v19 & 4) != 0 )
              {
                v46[v26] = L"SeBatchLogonRight";
                v26 = (unsigned int)(v26 + 1);
              }
              if ( (v19 & 0x10) != 0 )
              {
                v46[v26] = L"SeServiceLogonRight";
                v26 = (unsigned int)(v26 + 1);
              }
              if ( (v19 & 0x400) != 0 )
              {
                v20 = L"SeRemoteInteractiveLogonRight";
                v46[v26] = L"SeRemoteInteractiveLogonRight";
                v26 = (unsigned int)(v26 + 1);
              }
              if ( (v19 & 0x40) != 0 )
              {
                v20 = L"SeDenyInteractiveLogonRight";
                v46[v26] = L"SeDenyInteractiveLogonRight";
                v26 = (unsigned int)(v26 + 1);
              }
              if ( (v19 & 0x80u) != 0 )
              {
                v20 = L"SeDenyNetworkLogonRight";
                v46[v26] = L"SeDenyNetworkLogonRight";
                v26 = (unsigned int)(v26 + 1);
              }
              if ( (v19 & 0x100) != 0 )
              {
                v20 = L"SeDenyBatchLogonRight";
                v46[v26] = L"SeDenyBatchLogonRight";
                LODWORD(v26) = v26 + 1;
              }
              if ( (v19 & 0x200) != 0 )
              {
                v27 = (int)v26;
                v20 = L"SeDenyServiceLogonRight";
                LODWORD(v26) = v26 + 1;
                v46[v27] = L"SeDenyServiceLogonRight";
              }
              if ( (v19 & 0x800) != 0 )
              {
                v28 = (int)v26;
                LODWORD(v26) = v26 + 1;
                v46[v28] = L"SeDenyRemoteInteractiveLogonRight";
              }
              v29 = v42->Children[0];
              if ( (unsigned __int8)IsLsapAdtInitializeCrashOnAuditFailPresent(v20) )
              {
                if ( (_DWORD)v22 && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 34, &WPP_dde5ba64ca46380d90069aada4d87825_Traceguids);
                v30 = 0;
                if ( (int)v22 > 0 )
                {
                  do
                  {
                    if ( v34 )
                      LsapAdtGenerateLsaAuditSystemAccessChange(6, 4717, 141, 8, v29, v41, v5, v45[v30]);
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
                      WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 12),
                        35,
                        &WPP_dde5ba64ca46380d90069aada4d87825_Traceguids,
                        v45[v30]);
                    v30 = (unsigned int)(v30 + 1);
                  }
                  while ( (int)v30 < (int)v22 );
                  v10 = (int)hMem;
                  v6 = v40;
                }
                if ( (_DWORD)v26 && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 36, &WPP_dde5ba64ca46380d90069aada4d87825_Traceguids);
                v31 = 0;
                if ( (int)v26 > 0 )
                {
                  v32 = v38;
                  do
                  {
                    if ( v34 )
                      LsapAdtGenerateLsaAuditSystemAccessChange(6, 4718, 141, 8, v29, v41, v32, v46[v31]);
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
                      WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 12),
                        37,
                        &WPP_dde5ba64ca46380d90069aada4d87825_Traceguids,
                        v46[v31]);
                    v31 = (unsigned int)(v31 + 1);
                  }
                  while ( (int)v31 < (int)v26 );
                  v10 = (int)hMem;
                  v6 = v40;
                }
                if ( !(_DWORD)v22 && !(_DWORD)v26 && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 38, &WPP_dde5ba64ca46380d90069aada4d87825_Traceguids);
                v5 = v38;
              }
              else if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 39, &WPP_dde5ba64ca46380d90069aada4d87825_Traceguids);
              }
              v4 = 1;
            }
          }
        }
      }
      goto LABEL_116;
    }
    RtlEnterCriticalSection(&stru_18019F2D8);
    if ( (unsigned int)dword_18019F308 > 0x1F4 )
      v10 = -1073741527;
    RtlLeaveCriticalSection(&stru_18019F2D8);
    if ( v10 >= 0 )
    {
      WaitForSingleObject(hHandle, 0xFFFFFFFF);
      RtlAcquireResourceShared((PRTL_RESOURCE)&stru_18019F2D8, 1u);
      v36 = 1;
      goto LABEL_21;
    }
  }
LABEL_116:
  if ( v42 )
    LsapSubProv_FreeRoutine(v42, v9);
  if ( v6 )
    LsaFreeMemory(v6);
  if ( v4 )
    LsapDbDereferenceObject((unsigned int)&v44, 3, 3, 67108881, 7, v10);
  if ( v35 && v10 >= 0 )
    LsapSceNotify(7, 7, v5);
  if ( v36 )
    RtlReleaseResource((PRTL_RESOURCE)&stru_18019F2D8);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      40,
      &WPP_dde5ba64ca46380d90069aada4d87825_Traceguids,
      (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18011b79c  mov     [rsp-8+arg_10], rbx
0x18011b7a1  push    rbp
0x18011b7a2  push    rsi
0x18011b7a3  push    rdi
0x18011b7a4  push    r12
0x18011b7a6  push    r13
0x18011b7a8  push    r14
0x18011b7aa  push    r15
0x18011b7ac  lea     rbp, [rsp-30h]
0x18011b7b1  sub     rsp, 130h
0x18011b7b8  xor     edi, edi
0x18011b7ba  mov     [rbp+60h+var_E0], rcx
0x18011b7be  mov     r12b, dil
0x18011b7c1  mov     [rsp+160h+var_11D], dil
0x18011b7c6  mov     r15d, edi
0x18011b7c9  mov     [rsp+160h+var_11E], dil
0x18011b7ce  mov     r13d, edi
0x18011b7d1  mov     [rsp+160h+var_100], rdi
0x18011b7d6  mov     [rsp+160h+var_11F], dil
0x18011b7db  mov     r14d, r8d
0x18011b7de  mov     [rsp+160h+var_F8], rdi
0x18011b7e3  mov     rbx, rcx
0x18011b7e6  mov     [rsp+160h+var_F0], rdi
0x18011b7eb  mov     [rsp+160h+hMem], rdi
0x18011b7f0  mov     [rsp+160h+var_118], edx
0x18011b7f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b7fb  test    byte ptr [rcx+6Ch], 1
0x18011b7ff  jz      short loc_18011B814
0x18011b801  mov     rcx, [rcx+60h]
0x18011b805  lea     edx, [rdi+1Fh]
0x18011b808  lea     r8, WPP_dde5ba64ca46380d90069aada4d87825_Traceguids
0x18011b80f  call    WPP_SF_
0x18011b814  xor     r9d, r9d
0x18011b817  xor     edx, edx
0x18011b819  mov     rcx, rbx
0x18011b81c  lea     r8d, [r9+3]
0x18011b820  call    LsapDbVerifyHandle
0x18011b825  mov     esi, eax
0x18011b827  test    eax, eax
0x18011b829  js      loc_18011BE80
0x18011b82f  mov     r15, [rbx+58h]
0x18011b833  mov     [rsp+160h+var_110], r15
0x18011b838  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b83f  test    byte ptr [rcx+6Ch], 1
0x18011b843  jz      short loc_18011B85D
0x18011b845  mov     rcx, [rcx+60h]; LoggerHandle
0x18011b849  lea     r8, WPP_dde5ba64ca46380d90069aada4d87825_Traceguids
0x18011b850  mov     edx, 20h ; ' '
0x18011b855  mov     r9, r15
0x18011b858  call    WPP_SF__sid_
0x18011b85d  mov     rcx, cs:WPP_GLOBAL_Control; void *
0x18011b864  test    byte ptr [rcx+6Ch], 1
0x18011b868  jz      short loc_18011B8C0
0x18011b86a  cmp     byte ptr [rcx+69h], 4
0x18011b86e  jb      short loc_18011B8C0
0x18011b870  lea     rdx, [rsp+160h+hMem]; unsigned __int16 **
0x18011b875  call    ?LsapDsGetCallerInfo@@YAXPEAXPEAPEAG@Z; LsapDsGetCallerInfo(void *,ushort * *)
0x18011b87a  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b881  mov     rdi, [rsp+160h+hMem]
0x18011b886  test    byte ptr [rcx+6Ch], 1
0x18011b88a  jz      short loc_18011B8AF
0x18011b88c  mov     rcx, [rcx+60h]
0x18011b890  lea     r9, aUnknown; "Unknown"
0x18011b897  test    rdi, rdi
0x18011b89a  lea     r8, WPP_dde5ba64ca46380d90069aada4d87825_Traceguids
0x18011b8a1  mov     edx, 21h ; '!'
0x18011b8a6  cmovnz  r9, rdi
0x18011b8aa  call    WPP_SF_S
0x18011b8af  mov     rcx, rdi; hMem
0x18011b8b2  call    cs:__imp_LocalFree
0x18011b8b9  nop     dword ptr [rax+rax+00h]
0x18011b8be  xor     edi, edi
0x18011b8c0  mov     eax, [rsp+160h+var_118]
0x18011b8c4  and     eax, 0FF7h
0x18011b8c9  cmp     [rsp+160h+var_118], eax
0x18011b8cd  jz      short loc_18011B8D9
0x18011b8cf  mov     esi, 0C000000Dh
0x18011b8d4  jmp     loc_18011BE80
0x18011b8d9  cmp     [rbx+32h], dil
0x18011b8dd  jnz     loc_18011B96F
0x18011b8e3  test    r14d, r14d
0x18011b8e6  jz      short loc_18011B962
0x18011b8e8  lea     rcx, stru_18019F2D8; CriticalSection
0x18011b8ef  call    cs:__imp_RtlEnterCriticalSection
0x18011b8f6  nop     dword ptr [rax+rax+00h]
0x18011b8fb  mov     eax, cs:dword_18019F308
0x18011b901  mov     ecx, 0C0000129h
0x18011b906  cmp     eax, 1F4h
0x18011b90b  cmova   esi, ecx
0x18011b90e  lea     rcx, stru_18019F2D8; CriticalSection
0x18011b915  call    cs:__imp_RtlLeaveCriticalSection
0x18011b91c  nop     dword ptr [rax+rax+00h]
0x18011b921  test    esi, esi
0x18011b923  js      loc_18011BE80
0x18011b929  mov     rcx, cs:hHandle; hHandle
0x18011b930  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18011b933  call    cs:__imp_WaitForSingleObject
0x18011b93a  nop     dword ptr [rax+rax+00h]
0x18011b93f  mov     r14d, 1
0x18011b945  lea     rcx, stru_18019F2D8; Resource
0x18011b94c  mov     dl, r14b; Wait
0x18011b94f  call    cs:__imp_RtlAcquireResourceShared
0x18011b956  nop     dword ptr [rax+rax+00h]
0x18011b95b  mov     [rsp+160h+var_11D], r14b
0x18011b960  jmp     short loc_18011B968
0x18011b962  mov     r14d, 1
0x18011b968  mov     [rsp+160h+var_11E], r14b
0x18011b96d  jmp     short loc_18011B975
0x18011b96f  mov     r14d, 1
0x18011b975  mov     r8d, 3
0x18011b97b  mov     [rsp+160h+var_140], 4000009h; int
0x18011b983  mov     r9d, r8d
0x18011b986  mov     rcx, rbx; struct _LSAP_DB_HANDLE *
0x18011b989  lea     edx, [r8+5]; DesiredAccess
0x18011b98d  call    LsapDbReferenceObject
0x18011b992  mov     esi, eax
0x18011b994  test    eax, eax
0x18011b996  js      loc_18011BE80
0x18011b99c  cmp     cs:dword_18019F50C, 4
0x18011b9a3  mov     r12b, r14b
0x18011b9a6  mov     [rsp+160h+var_120], r14b
0x18011b9ab  jnz     short loc_18011B9E3
0x18011b9ad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::GetImpl(void)'::`2'::impl
0x18011b9b4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::__private_IsEnabled(void)
0x18011b9b9  lea     r8, [rsp+160h+var_100]
0x18011b9be  mov     edx, r14d
0x18011b9c1  mov     rcx, rbx
0x18011b9c4  test    al, al
0x18011b9c6  jz      short loc_18011B9CF
0x18011b9c8  call    ?LsapDbCacheQueryInformationAccount@@YAJPEAXW4_ACCOUNT_INFORMATION_CLASS@@PEAPEAT_LSAPR_ACCOUNT_INFO@@@Z; LsapDbCacheQueryInformationAccount(void *,_ACCOUNT_INFORMATION_CLASS,_LSAPR_ACCOUNT_INFO * *)
0x18011b9cd  jmp     short loc_18011B9D4
0x18011b9cf  call    ?LsapDbCacheQueryInformationAccountOld@@YAJPEAXW4_ACCOUNT_INFORMATION_CLASS@@PEAPEAT_LSAPR_ACCOUNT_INFO@@@Z; LsapDbCacheQueryInformationAccountOld(void *,_ACCOUNT_INFORMATION_CLASS,_LSAPR_ACCOUNT_INFO * *)
0x18011b9d4  mov     r13, [rsp+160h+var_100]
0x18011b9d9  test    eax, eax
0x18011b9db  movzx   edi, dil
0x18011b9df  cmovns  edi, r14d
0x18011b9e3  mov     r9d, 4; unsigned int
0x18011b9e9  lea     r8, [rsp+160h+var_118]; void *
0x18011b9ee  lea     rdx, stru_18019E9F0; struct _UNICODE_STRING *
0x18011b9f5  mov     rcx, rbx; void *
0x18011b9f8  call    ?LsapDbWriteAttributeObject@@YAJPEAXPEAU_UNICODE_STRING@@0K@Z; LsapDbWriteAttributeObject(void *,_UNICODE_STRING *,void *,ulong)
0x18011b9fd  mov     dword ptr [rsp+160h+hMem], eax
0x18011ba01  mov     esi, eax
0x18011ba03  test    eax, eax
0x18011ba05  js      loc_18011BE80
0x18011ba0b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::GetImpl(void)'::`2'::impl
0x18011ba12  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::__private_IsEnabled(void)
0x18011ba17  test    al, al
0x18011ba19  jz      short loc_18011BA67
0x18011ba1b  mov     rbx, cs:?gpLsaAccountCache@@3PEAVLsaAccountCache@@EA; LsaAccountCache * gpLsaAccountCache
0x18011ba22  test    rbx, rbx
0x18011ba25  jz      short loc_18011BA96
0x18011ba27  mov     r14d, [rsp+160h+var_118]
0x18011ba2c  mov     rcx, rbx; this
0x18011ba2f  call    ?LockExclusive@NLRefcountableObjectWithLock@@QEAAXXZ; NLRefcountableObjectWithLock::LockExclusive(void)
0x18011ba34  mov     rdx, r15; void *
0x18011ba37  mov     rcx, rbx; this
0x18011ba3a  call    ?TableLookup@LsaAccountCache@@AEAAPEAU_ACCT_TABLE_ENTRY@@PEAX@Z; LsaAccountCache::TableLookup(void *)
0x18011ba3f  test    rax, rax
0x18011ba42  jz      short loc_18011BA48
0x18011ba44  mov     [rax+8], r14d
0x18011ba48  lea     rcx, [rbx+10h]; SRWLock
0x18011ba4c  mov     dword ptr [rbx+18h], 0
0x18011ba53  call    cs:__imp_ReleaseSRWLockExclusive
0x18011ba5a  nop     dword ptr [rax+rax+00h]
0x18011ba5f  mov     r14d, 1
0x18011ba65  jmp     short loc_18011BA96
0x18011ba67  cmp     cs:dword_18019F50C, 4
0x18011ba6e  mov     [rsp+160h+var_E8], 0
0x18011ba77  jnz     short loc_18011BA96
0x18011ba79  lea     rdx, [rsp+160h+var_E8]; struct _LSAP_DB_ACCOUNT **
0x18011ba7e  mov     rcx, r15; Sid1
0x18011ba81  call    ?LsapDbLookupAccount@@YAJPEAXPEAPEAU_LSAP_DB_ACCOUNT@@@Z; LsapDbLookupAccount(void *,_LSAP_DB_ACCOUNT * *)
0x18011ba86  test    eax, eax
0x18011ba88  js      short loc_18011BA96
0x18011ba8a  mov     rcx, [rsp+160h+var_E8]
0x18011ba8f  mov     eax, [rsp+160h+var_118]
0x18011ba93  mov     [rcx+18h], eax
0x18011ba96  call    IsLsapAdtInitializeCrashOnAuditFailPresent
0x18011ba9b  test    al, al
0x18011ba9d  jz      loc_18011BE80
0x18011baa3  lea     rdx, [rsp+160h+var_F8]
0x18011baa8  lea     rcx, [rsp+160h+var_F0]
0x18011baad  call    cs:__imp_LsapQueryClientInfo
0x18011bab4  nop     dword ptr [rax+rax+00h]
0x18011bab9  test    eax, eax
0x18011babb  js      short loc_18011BADE
0x18011babd  lea     r9, [rsp+160h+var_11F]
0x18011bac2  mov     r8d, 8
0x18011bac8  lea     rdx, [rsp+160h+var_F8]
0x18011bacd  mov     ecx, 8Dh
0x18011bad2  call    cs:__imp_LsapAdtAuditingEnabledByLogonId
0x18011bad9  nop     dword ptr [rax+rax+00h]
0x18011bade  test    dil, dil
0x18011bae1  jz      loc_18011BE80
0x18011bae7  test    eax, eax
0x18011bae9  js      loc_18011BE80
0x18011baef  cmp     [rsp+160h+var_11F], 0
0x18011baf4  jz      loc_18011BE80
0x18011bafa  mov     ebx, 50h ; 'P'
0x18011baff  lea     rcx, [rbp+60h+var_D0]; void *
0x18011bb03  mov     r8d, ebx; Size
0x18011bb06  xor     edx, edx; Val
0x18011bb08  call    memset_0
0x18011bb0d  mov     r8d, ebx; Size
0x18011bb10  lea     rcx, [rbp+60h+var_80]; void *
0x18011bb14  xor     edx, edx; Val
0x18011bb16  call    memset_0
0x18011bb1b  mov     edx, [rsp+160h+var_118]
0x18011bb1f  test    r13, r13
0x18011bb22  jz      short loc_18011BB2E
0x18011bb24  mov     ecx, [r13+0]
0x18011bb28  not     ecx
0x18011bb2a  and     ecx, edx
0x18011bb2c  jmp     short loc_18011BB30
0x18011bb2e  mov     ecx, edx
0x18011bb30  mov     edi, ecx
0x18011bb32  lea     r8, aSeinteractivel; "SeInteractiveLogonRight"
0x18011bb39  and     edi, r14d
0x18011bb3c  lea     r10, aSenetworklogon; "SeNetworkLogonRight"
0x18011bb43  mov     rax, r8
0x18011bb46  cmovz   rax, [rbp+60h+var_D0]
0x18011bb4b  mov     [rbp+60h+var_D0], rax
0x18011bb4f  test    cl, 2
0x18011bb52  jz      short loc_18011BB5B
0x18011bb54  mov     [rbp+rdi*8+60h+var_D0], r10
0x18011bb59  inc     edi
0x18011bb5b  lea     r9, aSebatchlogonri; "SeBatchLogonRight"
0x18011bb62  test    cl, 4
0x18011bb65  jz      short loc_18011BB6F
0x18011bb67  mov     [rbp+rdi*8+60h+var_D0], r9
0x18011bb6c  add     edi, r14d
0x18011bb6f  lea     r11, aSeservicelogon; "SeServiceLogonRight"
0x18011bb76  test    cl, 10h
0x18011bb79  jz      short loc_18011BB83
0x18011bb7b  mov     [rbp+rdi*8+60h+var_D0], r11
0x18011bb80  add     edi, r14d
0x18011bb83  lea     rbx, aSeremoteintera; "SeRemoteInteractiveLogonRight"
0x18011bb8a  bt      ecx, 0Ah
0x18011bb8e  jnb     short loc_18011BB98
0x18011bb90  mov     [rbp+rdi*8+60h+var_D0], rbx
0x18011bb95  add     edi, r14d
0x18011bb98  lea     rbx, aSedenyinteract; "SeDenyInteractiveLogonRight"
0x18011bb9f  test    cl, 40h
0x18011bba2  jz      short loc_18011BBAC
0x18011bba4  mov     [rbp+rdi*8+60h+var_D0], rbx
0x18011bba9  add     edi, r14d
0x18011bbac  lea     rbx, aSedenynetworkl; "SeDenyNetworkLogonRight"
0x18011bbb3  test    cl, cl
0x18011bbb5  jns     short loc_18011BBBF
0x18011bbb7  mov     [rbp+rdi*8+60h+var_D0], rbx
0x18011bbbc  add     edi, r14d
0x18011bbbf  lea     rbx, aSedenybatchlog; "SeDenyBatchLogonRight"
0x18011bbc6  bt      ecx, 8
0x18011bbca  jnb     short loc_18011BBD4
0x18011bbcc  mov     [rbp+rdi*8+60h+var_D0], rbx
0x18011bbd1  add     edi, r14d
0x18011bbd4  lea     rbx, aSedenyservicel; "SeDenyServiceLogonRight"
0x18011bbdb  bt      ecx, 9
0x18011bbdf  jnb     short loc_18011BBEC
0x18011bbe1  movsxd  rax, edi
0x18011bbe4  add     edi, r14d
0x18011bbe7  mov     [rbp+rax*8+60h+var_D0], rbx
0x18011bbec  lea     r12, aSedenyremotein; "SeDenyRemoteInteractiveLogonRight"
0x18011bbf3  bt      ecx, 0Bh
0x18011bbf7  jnb     short loc_18011BC04
0x18011bbf9  movsxd  rax, edi
0x18011bbfc  add     edi, r14d
0x18011bbff  mov     [rbp+rax*8+60h+var_D0], r12
0x18011bc04  test    r13, r13
0x18011bc07  jz      short loc_18011BC0F
0x18011bc09  not     edx
0x18011bc0b  and     edx, [r13+0]
0x18011bc0f  mov     ebx, edx
0x18011bc11  and     ebx, r14d
0x18011bc14  cmovz   r8, [rbp+60h+var_80]
0x18011bc19  mov     [rbp+60h+var_80], r8
0x18011bc1d  test    dl, 2
0x18011bc20  jz      short loc_18011BC29
0x18011bc22  mov     [rbp+rbx*8+60h+var_80], r10
0x18011bc27  inc     ebx
0x18011bc29  test    dl, 4
0x18011bc2c  jz      short loc_18011BC36
0x18011bc2e  mov     [rbp+rbx*8+60h+var_80], r9
0x18011bc33  add     ebx, r14d
0x18011bc36  test    dl, 10h
0x18011bc39  jz      short loc_18011BC43
0x18011bc3b  mov     [rbp+rbx*8+60h+var_80], r11
0x18011bc40  add     ebx, r14d
0x18011bc43  bt      edx, 0Ah
0x18011bc47  jnb     short loc_18011BC58
0x18011bc49  lea     rcx, aSeremoteintera; "SeRemoteInteractiveLogonRight"
0x18011bc50  mov     [rbp+rbx*8+60h+var_80], rcx
0x18011bc55  add     ebx, r14d
0x18011bc58  test    dl, 40h
0x18011bc5b  jz      short loc_18011BC6C
0x18011bc5d  lea     rcx, aSedenyinteract; "SeDenyInteractiveLogonRight"
0x18011bc64  mov     [rbp+rbx*8+60h+var_80], rcx
0x18011bc69  add     ebx, r14d
0x18011bc6c  test    dl, dl
  ... truncated ...
```
