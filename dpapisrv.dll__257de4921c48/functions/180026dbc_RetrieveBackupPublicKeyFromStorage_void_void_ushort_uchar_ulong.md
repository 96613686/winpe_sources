# RetrieveBackupPublicKeyFromStorage(void *,void *,ushort *,uchar * *,ulong *)

- ea: `0x180026dbc`
- end: `0x1800278bc`
- name: `?RetrieveBackupPublicKeyFromStorage@@YAKPEAX0PEAGPEAPEAEPEAK@Z`
- size: `2816`
- prototype: `__int64 __fastcall(HANDLE Token, PSID Sid, unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024f38`

## callees

- `0x180001184`
- `0x1800060e0`
- `0x180007f10`
- `0x1800123e8`
- `0x18001467c`
- `0x18001d810`
- `0x180023d84`
- `0x180026dbc`
- `0x180029adc`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800271f9`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800271f9`
- `api-ms-win-crt-private-l1-1-0!_o__difftime64` at `0x180027324`
- `api-ms-win-crt-private-l1-1-0!_o__difftime64` at `0x180027324`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002788b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002788b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002729a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800272dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002729a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800272dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027260`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027260`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800272fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800272fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002763a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002763a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180026f3e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180026f3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002735d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027562`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027729`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002735d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027562`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027729`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002787a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002787a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002709f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180027460`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180027621`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002709f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180027460`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180027621`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180027020`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180027020`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800273f6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180027839`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002784d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800273f6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180027839`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002784d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180026fd1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180026fd1`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180026f04`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180026f04`

## string_xrefs

- `0x180026e8d`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180026fac`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180027051`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x1800270d0`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180027149`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x1800271a3`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x1800271da`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x18002721b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x1800273c8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x18002741e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180027491`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x1800274ef`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x18002753e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x1800275c4`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x1800275f2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180027652`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x1800276b9`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180027705`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180027786`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x1800277ac`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x18002728e`: `MaxDomainBackupKeyCacheAge`
- `0x1800272d0`: `MaxDomainBackupKeyCacheAge`

## pseudocode

```c
__int64 __fastcall RetrieveBackupPublicKeyFromStorage(
        HANDLE Token,
        PSID Sid,
        unsigned __int16 *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  int v9; // eax
  DWORD v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  DWORD LastError; // eax
  unsigned int *v14; // r14
  unsigned int *v15; // rsi
  DWORD v16; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  HANDLE FileMappingW; // r15
  HANDLE v20; // r12
  HANDLE v21; // r15
  DWORD FileSize; // eax
  unsigned __int64 v23; // rbx
  unsigned int *v24; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // r10
  DWORD v28; // eax
  __time64_t v29; // r12
  double v30; // xmm0_8
  unsigned __int8 *v31; // rcx
  unsigned int *v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  DWORD v35; // eax
  unsigned __int8 *v36; // rcx
  unsigned int *v37; // rax
  __int64 v38; // r8
  __int64 v39; // r9
  DWORD v40; // eax
  unsigned __int8 *v41; // rcx
  __int64 v42; // r9
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-2D0h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-2CCh] BYREF
  DWORD cbData; // [rsp+50h] [rbp-2C8h] BYREF
  DWORD Type; // [rsp+54h] [rbp-2C4h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-2C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+60h] [rbp-2B8h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-2B4h] BYREF
  unsigned int *v52; // [rsp+68h] [rbp-2B0h]
  unsigned int *v53; // [rsp+70h] [rbp-2A8h]
  HANDLE hFile; // [rsp+78h] [rbp-2A0h] BYREF
  unsigned int *v55; // [rsp+80h] [rbp-298h]
  HANDLE v56; // [rsp+88h] [rbp-290h]
  unsigned __int16 v57[3]; // [rsp+90h] [rbp-288h] BYREF
  WCHAR ReferencedDomainName[21]; // [rsp+96h] [rbp-282h] BYREF
  WCHAR Name[264]; // [rsp+C0h] [rbp-258h] BYREF

  v56 = Token;
  v55 = a5;
  cchName = 257;
  cchReferencedDomainName = 19;
  hFile = 0;
  peUse = 0;
  *(_DWORD *)Data = 259200;
  phkResult = 0;
  Type = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl'::`2'::impl) )
  {
    if ( !a4 || !a5 )
    {
      v11 = 884;
      v10 = 87;
      goto LABEL_6;
    }
    v9 = StringCchCopyW(v57, 0x13u, L"BK-");
    if ( v9 )
    {
      v10 = (unsigned __int16)v9;
      v11 = 901;
LABEL_6:
      v12 = v10;
LABEL_7:
      DebugTraceError(v12, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", v11);
      return v10;
    }
  }
  else if ( (unsigned int)StringCchCopyW(v57, 0x13u, L"BK-") )
  {
    v11 = 918;
    v10 = 122;
    goto LABEL_6;
  }
  cchReferencedDomainName -= 3;
  if ( !LookupAccountSidLocalW(Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    LastError = GetLastError();
    v11 = 933;
LABEL_13:
    v10 = LastError;
    v12 = LastError;
    goto LABEL_7;
  }
  cchReferencedDomainName += 3;
  if ( Token && !SetThreadToken(0, Token) )
  {
    LastError = GetLastError();
    v11 = 950;
    goto LABEL_13;
  }
  v14 = 0;
  v52 = 0;
  v15 = 0;
  v53 = 0;
  v16 = OpenFileInStorageArea(0, 0x80000000, a3, v57, &hFile);
  v10 = v16;
  if ( v16 )
  {
    v17 = 970;
    v18 = v16;
LABEL_19:
    DebugTraceError(v18, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", v17);
    FileMappingW = 0;
    v20 = Token;
    goto LABEL_85;
  }
  v21 = hFile;
  FileSize = GetFileSize(hFile, 0);
  v23 = FileSize;
  if ( FileSize == -1 && GetLastError() )
  {
    v18 = 13;
    v10 = 13;
    v17 = 986;
    goto LABEL_19;
  }
  FileMappingW = CreateFileMappingW(v21, 0, 2u, 0, 0, 0);
  if ( FileMappingW )
  {
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl'::`2'::impl) )
    {
      v24 = (unsigned int *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      v14 = v24;
      v52 = v24;
      if ( !v24 )
      {
        v10 = GetLastError();
        DebugTraceError(v10, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1017);
        v20 = Token;
        goto LABEL_85;
      }
      if ( *v24 == 2 )
      {
        v25 = v24[1];
        if ( (unsigned int)v25 > 0xFFFF
          || (v26 = v24[2], (unsigned int)v26 > 0xFFFF)
          || (v27 = v24[3], (unsigned int)v27 > 0xFFFF) )
        {
          v10 = 13;
          DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1029);
          v20 = Token;
          goto LABEL_85;
        }
        if ( v23 < v25 + v27 + v26 + 16 )
        {
          v10 = 13;
          DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1039);
          v20 = Token;
          goto LABEL_85;
        }
        v20 = Token;
        v28 = LogonCredVerifySignature(
                Token,
                (UCHAR *)v24 + v27 + 16,
                (int)v26 + (int)v25,
                0,
                (struct _CRED_SIGNATURE *)(v24 + 4),
                v24[3]);
        v10 = v28;
        if ( v28 )
        {
          DebugTraceError(v28, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1054);
          goto LABEL_85;
        }
        if ( v14[2] != 8 )
        {
          v10 = 13;
          DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1062);
          goto LABEL_85;
        }
        v29 = _time64(0);
        if ( v29 == -1 )
        {
          v10 = 31;
          DebugTraceError(31, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1070);
          v20 = Token;
          goto LABEL_85;
        }
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Cryptography\\Protect", 0, 1u, &phkResult)
          && !RegQueryValueExW(phkResult, L"MaxDomainBackupKeyCacheAge", 0, &Type, 0, 0)
          && Type == 4 )
        {
          cbData = 4;
          if ( RegQueryValueExW(phkResult, L"MaxDomainBackupKeyCacheAge", 0, 0, Data, &cbData) )
            *(_DWORD *)Data = 259200;
        }
        if ( phkResult )
          RegCloseKey(phkResult);
        if ( *(_DWORD *)Data )
        {
          v30 = _o__difftime64(v29, *(_QWORD *)((char *)v14 + v14[3] + v14[1] + 16));
          if ( v30 == 0.0 || v30 > (double)*(int *)Data )
            v10 = 1901;
        }
        v31 = (unsigned __int8 *)LocalAlloc(0, v14[1]);
        *a4 = v31;
        if ( !v31 )
        {
          v10 = 14;
          v20 = Token;
          goto LABEL_85;
        }
        memcpy_0(v31, (char *)v14 + v14[3] + 16, v14[1]);
        *v55 = v14[1];
      }
      else
      {
        if ( *v24 != 1 )
        {
          v10 = 13;
          DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1189);
          v20 = Token;
          goto LABEL_85;
        }
        if ( !UnmapViewOfFile(v24) )
        {
          v10 = GetLastError();
          DebugTraceError(v10, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1123);
          v20 = Token;
          goto LABEL_85;
        }
        v14 = 0;
        v52 = 0;
        v32 = (unsigned int *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
        v15 = v32;
        v53 = v32;
        if ( !v32 )
        {
          v10 = GetLastError();
          DebugTraceError(v10, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1132);
          v20 = Token;
          goto LABEL_85;
        }
        v33 = v32[1];
        if ( (unsigned int)v33 > 0xFFFF || (v34 = v32[2], (unsigned int)v34 > 0xFFFF) )
        {
          v10 = 13;
          DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1140);
          v20 = Token;
          goto LABEL_85;
        }
        if ( v23 < v33 + v34 + 12 )
        {
          v10 = 13;
          DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1149);
          v20 = Token;
          goto LABEL_85;
        }
        v35 = LogonCredVerifySignature(
                Token,
                (UCHAR *)v32 + (unsigned int)v34 + 12,
                v33,
                0,
                (struct _CRED_SIGNATURE *)(v32 + 3),
                v34);
        v10 = v35;
        if ( v35 )
        {
          DebugTraceError(v35, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1166);
          v20 = Token;
          goto LABEL_85;
        }
        v36 = (unsigned __int8 *)LocalAlloc(0, v15[1]);
        *a4 = v36;
        if ( !v36 )
        {
          v10 = 14;
          v20 = Token;
          goto LABEL_85;
        }
        memcpy_0(v36, (char *)v15 + v15[2] + 12, v15[1]);
        *a5 = v15[1];
        v10 = 1901;
      }
    }
    else
    {
      v37 = (unsigned int *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      v15 = v37;
      v53 = v37;
      if ( !v37 )
      {
        v10 = GetLastError();
        DebugTraceError(v10, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1201);
        v20 = Token;
        goto LABEL_85;
      }
      if ( *v37 != 1 || (v38 = v37[1], (unsigned int)v38 > 0xFFFF) || (v39 = v37[2], (unsigned int)v39 > 0xFFFF) )
      {
        v10 = 13;
        DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1210);
        v20 = Token;
        goto LABEL_85;
      }
      if ( v23 < v38 + v39 + 12 )
      {
        v10 = 13;
        DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1219);
        v20 = Token;
        goto LABEL_85;
      }
      v40 = LogonCredVerifySignature(
              0,
              (UCHAR *)v37 + (unsigned int)v39 + 12,
              v38,
              0,
              (struct _CRED_SIGNATURE *)(v37 + 3),
              v39);
      v10 = v40;
      if ( v40 )
      {
        DebugTraceError(v40, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1236);
        v20 = Token;
        goto LABEL_85;
      }
      v41 = (unsigned __int8 *)LocalAlloc(0, v15[1]);
      *a4 = v41;
      if ( !v41 )
      {
        v10 = -1073741772;
        v20 = Token;
        goto LABEL_85;
      }
      memcpy_0(v41, (char *)v15 + v15[2] + 12, v15[1]);
      *a5 = v15[1];
    }
    v20 = Token;
    goto LABEL_85;
  }
  v10 = GetLastError();
  DebugTraceError(v10, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1005);
  v20 = Token;
LABEL_85:
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x200000000000LL) )
    {
      cbData = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (int)&dword_18004C260,
        (int)&dword_180044A04,
        0,
        v42,
        (__int64)&cbData);
    }
    if ( v14 )
      UnmapViewOfFile(v14);
  }
  if ( v15 )
    UnmapViewOfFile(v15);
  if ( FileMappingW )
    CloseHandle(FileMappingW);
  if ( hFile )
    CloseHandle(hFile);
  if ( v20 )
    RevertToSelf();
  return v10;
}

```

## disassembly

```asm
0x180026dbc  push    rbx
0x180026dbe  push    rsi
0x180026dbf  push    r12
0x180026dc1  push    r13
0x180026dc3  push    r14
0x180026dc5  push    r15
0x180026dc7  sub     rsp, 2E8h
0x180026dce  mov     rax, cs:__security_cookie
0x180026dd5  xor     rax, rsp
0x180026dd8  mov     [rsp+318h+var_48], rax
0x180026de0  mov     r13, r9
0x180026de3  mov     r15, r8
0x180026de6  mov     rbx, rdx
0x180026de9  mov     rsi, rcx
0x180026dec  mov     [rsp+318h+ExistingTokenHandle], rcx
0x180026df1  mov     [rsp+318h+var_290], rcx
0x180026df9  mov     r12, [rsp+318h+arg_20]
0x180026e01  mov     [rsp+318h+var_298], r12
0x180026e09  mov     [rsp+318h+cchName], 101h
0x180026e11  mov     r14d, 13h
0x180026e17  mov     [rsp+318h+var_2D0], r14d
0x180026e1c  mov     [rsp+318h+hFile], 0
0x180026e25  mov     [rsp+318h+var_2B8], 0
0x180026e2d  mov     dword ptr [rsp+318h+Data], 3F480h
0x180026e35  mov     [rsp+318h+phkResult], 0
0x180026e3e  mov     [rsp+318h+Type], 0
0x180026e46  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation> `wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl(void)'::`2'::impl
0x180026e4d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled(void)
0x180026e52  test    al, al
0x180026e54  jz      short loc_180026EAB
0x180026e56  test    r13, r13
0x180026e59  jz      short loc_180026E9E
0x180026e5b  test    r12, r12
0x180026e5e  jz      short loc_180026E9E
0x180026e60  lea     r8, aBk; "BK-"
0x180026e67  mov     edx, r14d; unsigned __int64
0x180026e6a  lea     rcx, [rsp+318h+var_288]; unsigned __int16 *
0x180026e72  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026e77  test    eax, eax
0x180026e79  jz      short loc_180026ED3
0x180026e7b  movzx   ebx, ax
0x180026e7e  mov     r9d, 385h
0x180026e84  mov     ecx, ebx
0x180026e86  lea     rdx, aDwlasterror; "dwLastError"
0x180026e8d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180026e94  call    DebugTraceError
0x180026e99  jmp     loc_180027897
0x180026e9e  mov     r9d, 374h
0x180026ea4  mov     ebx, 57h ; 'W'
0x180026ea9  jmp     short loc_180026E84
0x180026eab  lea     r8, aBk; "BK-"
0x180026eb2  mov     rdx, r14; unsigned __int64
0x180026eb5  lea     rcx, [rsp+318h+var_288]; unsigned __int16 *
0x180026ebd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026ec2  test    eax, eax
0x180026ec4  jz      short loc_180026ED3
0x180026ec6  mov     r9d, 396h
0x180026ecc  mov     ebx, 7Ah ; 'z'
0x180026ed1  jmp     short loc_180026E84
0x180026ed3  add     [rsp+318h+var_2D0], 0FFFFFFFDh
0x180026ed8  lea     rax, [rsp+318h+var_2B8]
0x180026edd  mov     [rsp+318h+peUse], rax; peUse
0x180026ee2  lea     rax, [rsp+318h+var_2D0]
0x180026ee7  mov     [rsp+318h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180026eec  lea     r9, [rsp+318h+ReferencedDomainName]; ReferencedDomainName
0x180026ef4  lea     r8, [rsp+318h+cchName]; cchName
0x180026ef9  lea     rdx, [rsp+318h+Name]; Name
0x180026f01  mov     rcx, rbx; Sid
0x180026f04  call    cs:__imp_LookupAccountSidLocalW
0x180026f0b  nop     dword ptr [rax+rax+00h]
0x180026f10  test    eax, eax
0x180026f12  jnz     short loc_180026F2F
0x180026f14  call    cs:__imp_GetLastError
0x180026f1b  nop     dword ptr [rax+rax+00h]
0x180026f20  mov     r9d, 3A5h
0x180026f26  mov     ebx, eax
0x180026f28  mov     ecx, eax
0x180026f2a  jmp     loc_180026E86
0x180026f2f  add     [rsp+318h+var_2D0], 3
0x180026f34  test    rsi, rsi
0x180026f37  jz      short loc_180026F62
0x180026f39  mov     rdx, rsi; Token
0x180026f3c  xor     ecx, ecx; Thread
0x180026f3e  call    cs:__imp_SetThreadToken
0x180026f45  nop     dword ptr [rax+rax+00h]
0x180026f4a  test    eax, eax
0x180026f4c  jnz     short loc_180026F62
0x180026f4e  call    cs:__imp_GetLastError
0x180026f55  nop     dword ptr [rax+rax+00h]
0x180026f5a  mov     r9d, 3B6h
0x180026f60  jmp     short loc_180026F26
0x180026f62  xor     ecx, ecx; void *
0x180026f64  mov     [rsp+318h+hFileMappingObject], rcx
0x180026f69  xor     r14d, r14d
0x180026f6c  mov     [rsp+318h+var_2B0], r14
0x180026f71  xor     esi, esi
0x180026f73  mov     [rsp+318h+var_2A8], rsi
0x180026f78  lea     rax, [rsp+318h+hFile]
0x180026f7d  mov     [rsp+318h+cchReferencedDomainName], rax; void **
0x180026f82  lea     r9, [rsp+318h+var_288]; unsigned __int16 *
0x180026f8a  mov     r8, r15; unsigned __int16 *
0x180026f8d  mov     edx, 80000000h; unsigned int
0x180026f92  call    ?OpenFileInStorageArea@@YAKPEAXKPEBG1PEAPEAX@Z; OpenFileInStorageArea(void *,ulong,ushort const *,ushort const *,void * *)
0x180026f97  mov     ebx, eax
0x180026f99  test    eax, eax
0x180026f9b  jz      short loc_180026FC7
0x180026f9d  mov     r9d, 3CAh
0x180026fa3  mov     ecx, eax
0x180026fa5  lea     rdx, aDwlasterror; "dwLastError"
0x180026fac  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180026fb3  call    DebugTraceError
0x180026fb8  mov     r15, [rsp+318h+hFileMappingObject]
0x180026fbd  mov     r12, [rsp+318h+ExistingTokenHandle]
0x180026fc2  jmp     loc_1800277D8
0x180026fc7  xor     edx, edx; lpFileSizeHigh
0x180026fc9  mov     r15, [rsp+318h+hFile]
0x180026fce  mov     rcx, r15; hFile
0x180026fd1  call    cs:__imp_GetFileSize
0x180026fd8  nop     dword ptr [rax+rax+00h]
0x180026fdd  mov     ebx, eax
0x180026fdf  cmp     eax, 0FFFFFFFFh
0x180026fe2  jnz     short loc_180027003
0x180026fe4  call    cs:__imp_GetLastError
0x180026feb  nop     dword ptr [rax+rax+00h]
0x180026ff0  test    eax, eax
0x180026ff2  jz      short loc_180027003
0x180026ff4  mov     ecx, 0Dh
0x180026ff9  mov     ebx, ecx
0x180026ffb  mov     r9d, 3DAh
0x180027001  jmp     short loc_180026FA5
0x180027003  mov     [rsp+318h+peUse], 0; lpName
0x18002700c  mov     dword ptr [rsp+318h+cchReferencedDomainName], 0; dwMaximumSizeLow
0x180027014  xor     r9d, r9d; dwMaximumSizeHigh
0x180027017  xor     edx, edx; lpFileMappingAttributes
0x180027019  lea     r8d, [r9+2]; flProtect
0x18002701d  mov     rcx, r15; hFile
0x180027020  call    cs:__imp_CreateFileMappingW
0x180027027  nop     dword ptr [rax+rax+00h]
0x18002702c  mov     r15, rax
0x18002702f  mov     [rsp+318h+hFileMappingObject], rax
0x180027034  test    rax, rax
0x180027037  jnz     short loc_180027070
0x180027039  call    cs:__imp_GetLastError
0x180027040  nop     dword ptr [rax+rax+00h]
0x180027045  mov     ebx, eax
0x180027047  mov     [rsp+318h+var_2E8], eax
0x18002704b  mov     r9d, 3EDh
0x180027051  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180027058  lea     rdx, aDwlasterror; "dwLastError"
0x18002705f  mov     ecx, eax
0x180027061  call    DebugTraceError
0x180027066  mov     r12, [rsp+318h+ExistingTokenHandle]
0x18002706b  jmp     loc_1800277D8
0x180027070  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation> `wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl(void)'::`2'::impl
0x180027077  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled(void)
0x18002707c  mov     [rsp+318h+cchReferencedDomainName], 0; dwNumberOfBytesToMap
0x180027085  xor     r9d, r9d; dwFileOffsetLow
0x180027088  xor     r8d, r8d; dwFileOffsetHigh
0x18002708b  test    al, al
0x18002708d  jz      loc_180027614
0x180027093  lea     r15d, [r9+4]
0x180027097  mov     edx, r15d; dwDesiredAccess
0x18002709a  mov     rcx, [rsp+318h+hFileMappingObject]; hFileMappingObject
0x18002709f  call    cs:__imp_MapViewOfFile
0x1800270a6  nop     dword ptr [rax+rax+00h]
0x1800270ab  mov     r14, rax
0x1800270ae  mov     [rsp+318h+var_2B0], rax
0x1800270b3  test    rax, rax
0x1800270b6  jnz     short loc_1800270F4
0x1800270b8  call    cs:__imp_GetLastError
0x1800270bf  nop     dword ptr [rax+rax+00h]
0x1800270c4  mov     ebx, eax
0x1800270c6  mov     [rsp+318h+var_2E8], eax
0x1800270ca  mov     r9d, 3F9h
0x1800270d0  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800270d7  lea     rdx, aDwlasterror; "dwLastError"
0x1800270de  mov     ecx, eax
0x1800270e0  call    DebugTraceError
0x1800270e5  mov     r15, [rsp+318h+hFileMappingObject]
0x1800270ea  mov     r12, [rsp+318h+ExistingTokenHandle]
0x1800270ef  jmp     loc_1800277D8
0x1800270f4  cmp     dword ptr [rax], 2
0x1800270f7  jnz     loc_1800273EA
0x1800270fd  mov     r8d, [rax+4]
0x180027101  mov     eax, 0FFFFh
0x180027106  cmp     r8d, eax
0x180027109  ja      loc_1800273B7
0x18002710f  mov     r9d, [r14+8]
0x180027113  cmp     r9d, eax
0x180027116  ja      loc_1800273B7
0x18002711c  mov     r10d, [r14+0Ch]
0x180027120  cmp     r10d, eax
0x180027123  ja      loc_1800273B7
0x180027129  lea     rdx, [r9+10h]
0x18002712d  add     rdx, r10
0x180027130  add     rdx, r8
0x180027133  cmp     rbx, rdx
0x180027136  jnb     short loc_18002716B
0x180027138  mov     ecx, 0Dh
0x18002713d  mov     ebx, ecx
0x18002713f  mov     [rsp+318h+var_2E8], ecx
0x180027143  mov     r9d, 40Fh
0x180027149  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180027150  lea     rdx, aDwlasterror; "dwLastError"
0x180027157  call    DebugTraceError
0x18002715c  mov     r15, [rsp+318h+hFileMappingObject]
0x180027161  mov     r12, [rsp+318h+ExistingTokenHandle]
0x180027166  jmp     loc_1800277D8
0x18002716b  lea     rax, [r14+10h]
0x18002716f  add     r8d, r9d
0x180027172  lea     rdx, [r10+10h]
0x180027176  add     rdx, r14
0x180027179  mov     dword ptr [rsp+318h+peUse], r10d; int
0x18002717e  mov     [rsp+318h+cchReferencedDomainName], rax; struct _CRED_SIGNATURE *
0x180027183  xor     r9d, r9d
0x180027186  mov     r12, [rsp+318h+ExistingTokenHandle]
0x18002718b  mov     rcx, r12; ExistingTokenHandle
0x18002718e  call    LogonCredVerifySignature
0x180027193  mov     ebx, eax
0x180027195  mov     [rsp+318h+var_2E8], eax
0x180027199  test    eax, eax
0x18002719b  jz      short loc_1800271C2
0x18002719d  mov     r9d, 41Eh
0x1800271a3  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800271aa  lea     rdx, aDwlasterror; "dwLastError"
0x1800271b1  mov     ecx, eax
0x1800271b3  call    DebugTraceError
0x1800271b8  mov     r15, [rsp+318h+hFileMappingObject]
0x1800271bd  jmp     loc_1800277D8
0x1800271c2  cmp     dword ptr [r14+8], 8
0x1800271c7  jz      short loc_1800271F7
0x1800271c9  mov     ecx, 0Dh
0x1800271ce  mov     ebx, ecx
0x1800271d0  mov     [rsp+318h+var_2E8], ecx
0x1800271d4  mov     r9d, 426h
0x1800271da  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800271e1  lea     rdx, aDwlasterror; "dwLastError"
0x1800271e8  call    DebugTraceError
0x1800271ed  mov     r15, [rsp+318h+hFileMappingObject]
0x1800271f2  jmp     loc_1800277D8
0x1800271f7  xor     ecx, ecx; Time
0x1800271f9  call    cs:__imp__time64
0x180027200  nop     dword ptr [rax+rax+00h]
0x180027205  mov     r12, rax
0x180027208  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002720c  jnz     short loc_18002723F
0x18002720e  lea     ebx, [rax+20h]
0x180027211  mov     [rsp+318h+var_2E8], ebx
0x180027215  mov     r9d, 42Eh
0x18002721b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180027222  lea     rdx, aDwlasterror; "dwLastError"
0x180027229  mov     ecx, ebx
0x18002722b  call    DebugTraceError
0x180027230  mov     r15, [rsp+318h+hFileMappingObject]
0x180027235  mov     r12, [rsp+318h+ExistingTokenHandle]
0x18002723a  jmp     loc_1800277D8
0x18002723f  lea     rax, [rsp+318h+phkResult]
0x180027244  mov     [rsp+318h+cchReferencedDomainName], rax; phkResult
0x180027249  mov     r9d, 1; samDesired
0x18002724f  xor     r8d, r8d; ulOptions
0x180027252  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Cryptography\\Prot"...
0x180027259  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027260  call    cs:__imp_RegOpenKeyExW
0x180027267  nop     dword ptr [rax+rax+00h]
0x18002726c  test    eax, eax
0x18002726e  jnz     loc_1800272F4
0x180027274  mov     [rsp+318h+peUse], 0; lpcbData
0x18002727d  mov     [rsp+318h+cchReferencedDomainName], 0; lpData
0x180027286  lea     r9, [rsp+318h+Type]; lpType
0x18002728b  xor     r8d, r8d; lpReserved
0x18002728e  lea     rdx, aMaxdomainbacku; "MaxDomainBackupKeyCacheAge"
0x180027295  mov     rcx, [rsp+318h+phkResult]; hKey
0x18002729a  call    cs:__imp_RegQueryValueExW
0x1800272a1  nop     dword ptr [rax+rax+00h]
0x1800272a6  test    eax, eax
0x1800272a8  jnz     short loc_1800272F4
0x1800272aa  cmp     [rsp+318h+Type], r15d
0x1800272af  jnz     short loc_1800272F4
0x1800272b1  mov     [rsp+318h+cbData], r15d
0x1800272b6  lea     rax, [rsp+318h+cbData]
0x1800272bb  mov     [rsp+318h+peUse], rax; lpcbData
0x1800272c0  lea     rax, [rsp+318h+Data]
0x1800272c5  mov     [rsp+318h+cchReferencedDomainName], rax; lpData
0x1800272ca  xor     r9d, r9d; lpType
0x1800272cd  xor     r8d, r8d; lpReserved
0x1800272d0  lea     rdx, aMaxdomainbacku; "MaxDomainBackupKeyCacheAge"
0x1800272d7  mov     rcx, [rsp+318h+phkResult]; hKey
0x1800272dc  call    cs:__imp_RegQueryValueExW
0x1800272e3  nop     dword ptr [rax+rax+00h]
0x1800272e8  test    eax, eax
0x1800272ea  jz      short loc_1800272F4
0x1800272ec  mov     dword ptr [rsp+318h+Data], 3F480h
0x1800272f4  mov     rcx, [rsp+318h+phkResult]; hKey
0x1800272f9  test    rcx, rcx
0x1800272fc  jz      short loc_18002730A
0x1800272fe  call    cs:__imp_RegCloseKey
0x180027305  nop     dword ptr [rax+rax+00h]
0x18002730a  cmp     dword ptr [rsp+318h+Data], 0
0x18002730f  jz      short loc_180027357
0x180027311  mov     edx, [r14+0Ch]
  ... truncated ...
```
