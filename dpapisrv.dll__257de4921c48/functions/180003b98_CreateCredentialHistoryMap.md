# CreateCredentialHistoryMap

- ea: `0x180003b98`
- end: `0x1800045b9`
- name: `CreateCredentialHistoryMap`
- size: `2593`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180003510`
- `0x180004e60`
- `0x1800285dc`

## callees

- `0x180003080`
- `0x1800032b4`
- `0x180003b98`
- `0x1800045c0`
- `0x180004640`
- `0x180004780`
- `0x1800048e4`
- `0x180007f10`
- `0x180008a44`
- `0x18001c340`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001eb8c`
- `0x180028f0c`
- `0x1800296c8`
- `0x180029ed4`
- `0x18003c62c`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800044ea`
- `RPCRT4!UuidCreate` at `0x1800044ea`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003c6b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003c6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000419c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000420f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000424e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000419c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000420f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000424e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004354`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800040c2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800040c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800040a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800040a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004544`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004544`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003c34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003c7d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003ffc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800043e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003c34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003c7d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003ffc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800043e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000423d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000459e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000423d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000459e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180003fc7`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180003fc7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180004030`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180004030`

## string_xrefs

- `0x180004145`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x1800041d5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180004221`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180004283`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x1800042a6`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x18000431d`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180004375`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
__int64 __fastcall CreateCredentialHistoryMap(
        __int64 a1,
        unsigned __int16 *a2,
        __int64 *a3,
        void *a4,
        int a5,
        _QWORD *a6,
        _QWORD *a7)
{
  _QWORD *v7; // rax
  unsigned __int16 *v9; // rbx
  char *v11; // rax
  char *v12; // r12
  DWORD LengthSid; // edi
  HLOCAL v14; // rax
  __int64 v15; // rax
  __int64 v16; // r11
  unsigned __int16 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r8
  unsigned __int16 *v20; // rdx
  unsigned int v21; // r10d
  __int64 v22; // rbx
  __int64 v23; // rdx
  unsigned __int16 *v24; // rax
  __int64 v25; // r8
  const wchar_t *v26; // r10
  __int64 v27; // rcx
  unsigned __int16 *v28; // rax
  __int64 v29; // rdx
  unsigned __int16 *v30; // rcx
  __int64 v31; // rax
  _WORD *v32; // r8
  unsigned __int16 *v33; // rdx
  __int64 v34; // rcx
  _WORD *v35; // rdx
  __int64 v36; // r8
  _WORD *v37; // rax
  unsigned int v38; // edx
  __int64 v39; // r10
  const wchar_t *v40; // rcx
  char *v41; // rax
  __int64 v42; // r9
  char *v43; // rcx
  DWORD v44; // ebx
  void *v46; // r13
  _DWORD *v47; // rsi
  const WCHAR *v48; // rdi
  struct _SECURITY_ATTRIBUTES *v49; // r9
  void *FileWithRetries; // r15
  DWORD FileSize; // eax
  int v52; // edx
  SIZE_T v53; // rbx
  int v54; // r14d
  HLOCAL v55; // rax
  _QWORD *v56; // rax
  HANDLE CurrentThread; // rax
  __int64 v58; // rax
  DWORD LastError; // eax
  __int64 v60; // r9
  __int64 v61; // rcx
  __int64 v62; // r9
  unsigned int CurrentCredential; // eax
  __int64 v64; // r9
  __int64 v65; // rax
  __int64 *v66; // rdi
  __int64 v67; // rcx
  __int64 v68; // rax
  const wchar_t *v69; // r9
  char v70; // [rsp+30h] [rbp-D0h]
  DWORD NumberOfBytesRead[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD FileSizeHigh; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v73; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v74; // [rsp+58h] [rbp-A8h]
  __int64 *v75; // [rsp+60h] [rbp-A0h]
  _QWORD *v76; // [rsp+68h] [rbp-98h]
  unsigned __int16 v77[264]; // [rsp+70h] [rbp-90h] BYREF

  v7 = a7;
  v76 = a6;
  v9 = a2;
  v74 = a7;
  FileSizeHigh = 0;
  v73 = 0;
  v75 = a3;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids, a2);
    v7 = v74;
  }
  if ( a6 && v7 )
  {
    *a6 = 0;
    *v7 = 0;
    v11 = (char *)LocalAlloc(0x40u, 0x228u);
    v12 = v11;
    if ( !v11 )
      return 8;
    if ( !a4 )
    {
      if ( a1 )
      {
        if ( !(unsigned int)GetTokenUserSid(a1, v11) )
        {
          LastError = GetLastError();
          v60 = 1572;
          goto LABEL_98;
        }
        if ( !(unsigned int)GetTokenAuthenticationId(a1, &v73) )
        {
          LastError = GetLastError();
          v60 = 1579;
          goto LABEL_98;
        }
      }
      else
      {
        *(_QWORD *)NumberOfBytesRead = 0;
        CurrentThread = GetCurrentThread();
        if ( !OpenThreadToken(CurrentThread, 8u, 1, (PHANDLE)NumberOfBytesRead) )
        {
          v44 = 1008;
          v60 = 1590;
LABEL_100:
          v61 = v44;
          goto LABEL_101;
        }
        if ( !(unsigned int)GetTokenUserSid(*(_QWORD *)NumberOfBytesRead, v12) )
        {
          v44 = GetLastError();
          DebugTraceError(v44, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", 1597);
          CloseHandle(*(HANDLE *)NumberOfBytesRead);
          goto LABEL_57;
        }
        if ( !(unsigned int)GetTokenAuthenticationId(0, &v73) )
        {
          LastError = GetLastError();
          v60 = 1605;
          goto LABEL_98;
        }
        CloseHandle(*(HANDLE *)NumberOfBytesRead);
      }
LABEL_9:
      if ( !v9 )
        goto LABEL_13;
      v15 = -1;
      do
        ++v15;
      while ( v9[v15] );
      if ( (int)v15 + 27 <= 260 )
      {
LABEL_13:
        v16 = 2147483646;
        v17 = v77;
        v18 = 2147483646;
        v19 = 261;
        do
        {
          if ( !v18 )
            break;
          if ( !*v9 )
            break;
          *v17++ = *v9++;
          --v18;
          --v19;
        }
        while ( v19 );
        v20 = v17 - 1;
        v21 = v19 == 0 ? 0x8007007A : 0;
        if ( v19 )
          v20 = v17;
        *v20 = 0;
        if ( v19 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v77[v22] );
          v23 = 261;
          v24 = v77;
          do
          {
            if ( !*v24 )
              break;
            ++v24;
            --v23;
          }
          while ( v23 );
          v21 = v23 == 0 ? 0x80070057 : 0;
          v25 = (261 - v23) & -(__int64)(v23 != 0);
          if ( v23 )
          {
            v26 = L"\\Microsoft\\Protect\\";
            v27 = 2147483646;
            v28 = &v77[v25];
            v29 = 261 - v25;
            if ( v25 != 261 )
            {
              do
              {
                if ( !v27 )
                  break;
                if ( !*v26 )
                  break;
                *v28++ = *v26++;
                --v27;
                --v29;
              }
              while ( v29 );
            }
            v30 = v28 - 1;
            if ( v29 )
              v30 = v28;
            v21 = v29 == 0 ? 0x8007007A : 0;
            *v30 = 0;
          }
          if ( v21 )
          {
            v62 = 1669;
          }
          else
          {
            v31 = 2147483646;
            v32 = v12 + 8;
            v33 = v77;
            v34 = 261;
            do
            {
              if ( !v31 )
                break;
              if ( !*v33 )
                break;
              *v32++ = *v33++;
              --v31;
              --v34;
            }
            while ( v34 );
            v35 = v32 - 1;
            v21 = v34 == 0 ? 0x8007007A : 0;
            if ( v34 )
              v35 = v32;
            *v35 = 0;
            if ( v34 )
            {
              v36 = 261;
              v37 = v12 + 8;
              do
              {
                if ( !*v37 )
                  break;
                ++v37;
                --v36;
              }
              while ( v36 );
              v38 = v36 == 0 ? 0x80070057 : 0;
              v39 = (261 - v36) & -(__int64)(v36 != 0);
              if ( v36 )
              {
                v40 = L"CREDHIST";
                v41 = &v12[2 * v39 + 8];
                v42 = 261 - v39;
                if ( 261 != v39 )
                {
                  do
                  {
                    if ( !v16 )
                      break;
                    if ( !*v40 )
                      break;
                    *(_WORD *)v41 = *v40++;
                    v41 += 2;
                    --v16;
                    --v42;
                  }
                  while ( v42 );
                }
                v43 = v41 - 2;
                if ( v42 )
                  v43 = v41;
                v38 = v42 == 0 ? 0x8007007A : 0;
                *(_WORD *)v43 = 0;
              }
              if ( v38 )
              {
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  WPP_SF_sDsd(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    v38,
                    (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
                    (unsigned int)"dwError",
                    v38,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
                    155);
                }
                goto LABEL_56;
              }
              v46 = *(void **)v12;
              v47 = 0;
              v48 = &v77[(int)v22 + 1];
              AcquireExclusiveLockForUser(*(void **)v12);
              while ( 1 )
              {
                FileWithRetries = (void *)CreateFileWithRetries((LPCWSTR)v12 + 4, 0xC0000000, 0, v49, 4u, 0x10000006u);
                if ( FileWithRetries != (void *)-1LL )
                  break;
                CurrentCredential = GetLastError();
                v44 = CurrentCredential;
                if ( CurrentCredential != 3 || a5 )
                {
                  v64 = 1742;
                  goto LABEL_117;
                }
                if ( (int)DPAPICreateNestedDirectories(v77, v48) < 0 )
                  goto LABEL_61;
              }
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
              {
                WPP_SF_S(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  26,
                  WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids,
                  v12 + 8);
              }
              FileSize = GetFileSize(FileWithRetries, &FileSizeHigh);
              v53 = FileSize;
              if ( FileSize == -1 && GetLastError() || FileSizeHigh )
              {
                v44 = 87;
                v58 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  v70 = -30;
                  goto LABEL_90;
                }
LABEL_61:
                if ( v46 )
                  ReleaseExclusiveLockForUser(v46);
                if ( v47 )
                  LocalFree(v47);
                if ( FileWithRetries )
                {
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
                  {
                    v69 = L"NULL";
                    if ( v12 )
                      v69 = (const wchar_t *)(v12 + 8);
                    WPP_SF_S(
                      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                      30,
                      WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids,
                      v69);
                  }
                  CloseHandle(FileWithRetries);
                }
                if ( !v12 )
                  return v44;
                goto LABEL_57;
              }
              v54 = 24;
              if ( (unsigned int)v53 >= 0x18 )
              {
                v55 = LocalAlloc(0, v53);
                *((_QWORD *)v12 + 67) = v55;
                if ( v55 )
                {
                  NumberOfBytesRead[0] = 0;
                  if ( ReadFile(FileWithRetries, v55, v53, NumberOfBytesRead, 0) )
                  {
                    v54 = v53;
LABEL_79:
                    v56 = v76;
                    v44 = 0;
                    *((_DWORD *)v12 + 136) = v54;
                    *v56 = v12;
                    v12 = 0;
                    *v74 = FileWithRetries;
                    FileWithRetries = 0;
                    v47 = 0;
                    goto LABEL_61;
                  }
                  v44 = GetLastError();
                  v58 = WPP_GLOBAL_Control;
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                  {
                    v70 = 68;
LABEL_90:
                    WPP_SF_sDsd(
                      *(_QWORD *)(v58 + 16),
                      v52,
                      (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
                      (unsigned int)"dwError",
                      v44,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
                      v70);
                    goto LABEL_61;
                  }
                }
                else
                {
                  v44 = 8;
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                  {
                    WPP_SF_sDsd(
                      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                      8,
                      (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
                      (unsigned int)"dwError",
                      8,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
                      54);
                  }
                }
                goto LABEL_61;
              }
              if ( a5 )
              {
                CurrentCredential = 3;
                v64 = 1778;
                v44 = 3;
LABEL_117:
                DebugTraceError(
                  CurrentCredential,
                  "dwError",
                  "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
                  v64);
                goto LABEL_61;
              }
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
              {
                WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 27, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids);
              }
              v47 = LocalAlloc(0, 0x18u);
              if ( !v47 )
              {
                CurrentCredential = 14;
                v64 = 1787;
                v44 = 14;
                goto LABEL_117;
              }
              if ( !v75 )
                goto LABEL_138;
              v65 = *v75;
              if ( !*v75 )
                v65 = v75[1];
              if ( v65 )
              {
                v66 = (__int64 *)(v47 + 1);
                *(_OWORD *)(v47 + 1) = *(_OWORD *)v75;
              }
              else
              {
LABEL_138:
                v66 = (__int64 *)(v47 + 1);
                CurrentCredential = GetCurrentCredential(v75, &v73, v47 + 1);
                v44 = CurrentCredential;
                if ( CurrentCredential )
                {
                  v64 = 1806;
                  goto LABEL_117;
                }
                v68 = *v66;
                if ( !*v66 )
                  v68 = *(_QWORD *)(v47 + 3);
                if ( !v68 )
                {
                  UuidCreate((UUID *)(v47 + 1));
                  v67 = WPP_GLOBAL_Control;
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                  {
LABEL_136:
                    v47[5] = 0;
                    *v47 = 1;
                    CurrentCredential = WriteNewCredentialHistoryRecord(FileWithRetries, 0, 0, (__int64)v47);
                    v44 = CurrentCredential;
                    if ( !CurrentCredential )
                    {
                      *((_QWORD *)v12 + 67) = v47;
                      goto LABEL_79;
                    }
                    v64 = 1830;
                    goto LABEL_117;
                  }
                  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
                  {
LABEL_133:
                    if ( (_UNKNOWN *)v67 != &WPP_GLOBAL_Control && (*(_BYTE *)(v67 + 28) & 4) != 0 )
                      WPP_SF__guid_(*(_QWORD *)(v67 + 16), 29, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids, v66);
                    goto LABEL_136;
                  }
                  WPP_SF__guid_(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    28,
                    WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids,
                    v47 + 1);
                }
              }
              v67 = WPP_GLOBAL_Control;
              goto LABEL_133;
            }
            v62 = 1681;
          }
        }
        else
        {
          v62 = 1654;
        }
        DebugTraceError(v21, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v62);
LABEL_56:
        v44 = 87;
LABEL_57:
        DestroyCredentialHistoryMap(v12);
        return v44;
      }
      v44 = 87;
      v60 = 1644;
      goto LABEL_100;
    }
    if ( a5 )
    {
      LengthSid = GetLengthSid(a4);
      v14 = LocalAlloc(0, LengthSid);
      *(_QWORD *)v12 = v14;
      if ( v14 )
      {
        memcpy_0(v14, a4, LengthSid);
        goto LABEL_9;
      }
      LastError = 14;
      v60 = 1630;
LABEL_98:
      v44 = LastError;
      v61 = LastError;
LABEL_101:
      DebugTraceError(v61, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v60);
      goto LABEL_57;
    }
  }
  return 87;
}

```

## disassembly

```asm
0x180003b98  mov     [rsp-8+arg_10], rbx
0x180003b9d  push    rbp
0x180003b9e  push    rsi
0x180003b9f  push    rdi
0x180003ba0  push    r12
0x180003ba2  push    r13
0x180003ba4  push    r14
0x180003ba6  push    r15
0x180003ba8  lea     rbp, [rsp-190h]
0x180003bb0  sub     rsp, 290h
0x180003bb7  mov     rax, cs:__security_cookie
0x180003bbe  xor     rax, rsp
0x180003bc1  mov     [rbp+1C0h+var_40], rax
0x180003bc8  mov     r14, [rbp+1C0h+arg_28]
0x180003bcf  xor     r15d, r15d
0x180003bd2  mov     rax, [rbp+1C0h+arg_30]
0x180003bd9  mov     rsi, r9
0x180003bdc  mov     [rsp+2C0h+var_258], r14
0x180003be1  mov     rbx, rdx
0x180003be4  mov     [rsp+2C0h+var_268], rax
0x180003be9  mov     rdi, rcx
0x180003bec  mov     [rsp+2C0h+FileSizeHigh], r15d
0x180003bf1  mov     [rsp+2C0h+var_270], r15
0x180003bf6  mov     [rsp+2C0h+var_260], r8
0x180003bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c02  lea     rdx, WPP_GLOBAL_Control
0x180003c09  cmp     rcx, rdx
0x180003c0c  jnz     loc_18000406E
0x180003c12  test    r14, r14
0x180003c15  jz      loc_1800045AF
0x180003c1b  test    rax, rax
0x180003c1e  jz      loc_1800045AF
0x180003c24  mov     [r14], r15
0x180003c27  mov     edx, 228h; uBytes
0x180003c2c  mov     ecx, 40h ; '@'; uFlags
0x180003c31  mov     [rax], r15
0x180003c34  call    cs:__imp_LocalAlloc
0x180003c3b  nop     dword ptr [rax+rax+00h]
0x180003c40  mov     r12, rax
0x180003c43  test    rax, rax
0x180003c46  jz      loc_180004183
0x180003c4c  mov     r13d, 1
0x180003c52  test    rsi, rsi
0x180003c55  jz      loc_18000409A
0x180003c5b  cmp     [rbp+1C0h+arg_20], r15d
0x180003c62  jz      loc_1800045AF
0x180003c68  mov     rcx, rsi; pSid
0x180003c6b  call    cs:__imp_GetLengthSid
0x180003c72  nop     dword ptr [rax+rax+00h]
0x180003c77  mov     edx, eax; uBytes
0x180003c79  xor     ecx, ecx; uFlags
0x180003c7b  mov     edi, eax
0x180003c7d  call    cs:__imp_LocalAlloc
0x180003c84  nop     dword ptr [rax+rax+00h]
0x180003c89  mov     [r12], rax
0x180003c8d  test    rax, rax
0x180003c90  jz      loc_1800041B0
0x180003c96  mov     r8d, edi; Size
0x180003c99  mov     rdx, rsi; Src
0x180003c9c  mov     rcx, rax; void *
0x180003c9f  call    memcpy_0
0x180003ca4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003ca8  test    rbx, rbx
0x180003cab  jz      short loc_180003CC8
0x180003cad  mov     rax, rsi
0x180003cb0  inc     rax
0x180003cb3  cmp     [rbx+rax*2], r15w
0x180003cb8  jnz     short loc_180003CB0
0x180003cba  add     eax, 1Bh
0x180003cbd  cmp     eax, 104h
0x180003cc2  jg      loc_180004265
0x180003cc8  mov     r11d, 7FFFFFFEh
0x180003cce  lea     rcx, [rsp+2C0h+var_250]
0x180003cd3  mov     r9d, 105h
0x180003cd9  mov     eax, r11d
0x180003cdc  mov     r8d, r9d
0x180003cdf  mov     edi, 2
0x180003ce4  test    rax, rax
0x180003ce7  jz      short loc_180003D02
0x180003ce9  movzx   edx, word ptr [rbx]
0x180003cec  test    dx, dx
0x180003cef  jz      short loc_180003D02
0x180003cf1  mov     [rcx], dx
0x180003cf4  add     rbx, rdi
0x180003cf7  add     rcx, rdi
0x180003cfa  sub     rax, r13
0x180003cfd  sub     r8, r13
0x180003d00  jnz     short loc_180003CE4
0x180003d02  mov     rax, r8
0x180003d05  lea     rdx, [rcx-2]
0x180003d09  neg     rax
0x180003d0c  mov     r14d, 8007007Ah
0x180003d12  sbb     r10d, r10d
0x180003d15  not     r10d
0x180003d18  and     r10d, r14d
0x180003d1b  test    r8, r8
0x180003d1e  cmovnz  rdx, rcx
0x180003d22  mov     [rdx], r15w
0x180003d26  jz      loc_180004275
0x180003d2c  lea     rax, [rsp+2C0h+var_250]
0x180003d31  mov     rbx, rsi
0x180003d34  inc     rbx
0x180003d37  cmp     [rax+rbx*2], r15w
0x180003d3c  jnz     short loc_180003D34
0x180003d3e  mov     rdx, r9
0x180003d41  lea     rax, [rsp+2C0h+var_250]
0x180003d46  cmp     [rax], r15w
0x180003d4a  jz      short loc_180003D54
0x180003d4c  add     rax, rdi
0x180003d4f  sub     rdx, r13
0x180003d52  jnz     short loc_180003D46
0x180003d54  mov     rax, rdx
0x180003d57  mov     esi, 80070057h
0x180003d5c  neg     rax
0x180003d5f  mov     rcx, r9
0x180003d62  mov     rax, rdx
0x180003d65  sbb     r10d, r10d
0x180003d68  sub     rcx, rdx
0x180003d6b  not     r10d
0x180003d6e  and     r10d, esi
0x180003d71  neg     rax
0x180003d74  sbb     r8, r8
0x180003d77  and     r8, rcx
0x180003d7a  test    rdx, rdx
0x180003d7d  jz      short loc_180003DD6
0x180003d7f  mov     rdx, r9
0x180003d82  lea     rax, [rsp+2C0h+var_250]
0x180003d87  lea     r10, aMicrosoftProte; "\\Microsoft\\Protect\\"
0x180003d8e  mov     rcx, r11
0x180003d91  lea     rax, [rax+r8*2]
0x180003d95  sub     rdx, r8
0x180003d98  jz      short loc_180003DBB
0x180003d9a  test    rcx, rcx
0x180003d9d  jz      short loc_180003DBB
0x180003d9f  movzx   r8d, word ptr [r10]
0x180003da3  test    r8w, r8w
0x180003da7  jz      short loc_180003DBB
0x180003da9  mov     [rax], r8w
0x180003dad  add     r10, rdi
0x180003db0  add     rax, rdi
0x180003db3  sub     rcx, r13
0x180003db6  sub     rdx, r13
0x180003db9  jnz     short loc_180003D9A
0x180003dbb  test    rdx, rdx
0x180003dbe  lea     rcx, [rax-2]
0x180003dc2  cmovnz  rcx, rax
0x180003dc6  neg     rdx
0x180003dc9  sbb     r10d, r10d
0x180003dcc  not     r10d
0x180003dcf  and     r10d, r14d
0x180003dd2  mov     [rcx], r15w
0x180003dd6  test    r10d, r10d
0x180003dd9  jnz     loc_18000429E
0x180003ddf  lea     r14, [r12+8]
0x180003de4  mov     rax, r11
0x180003de7  mov     r8, r14
0x180003dea  lea     rdx, [rsp+2C0h+var_250]
0x180003def  mov     rcx, r9
0x180003df2  test    rax, rax
0x180003df5  jz      short loc_180003E13
0x180003df7  movzx   r10d, word ptr [rdx]
0x180003dfb  test    r10w, r10w
0x180003dff  jz      short loc_180003E13
0x180003e01  mov     [r8], r10w
0x180003e05  add     rdx, rdi
0x180003e08  add     r8, rdi
0x180003e0b  sub     rax, r13
0x180003e0e  sub     rcx, r13
0x180003e11  jnz     short loc_180003DF2
0x180003e13  mov     rax, rcx
0x180003e16  lea     rdx, [r8-2]
0x180003e1a  neg     rax
0x180003e1d  sbb     r10d, r10d
0x180003e20  not     r10d
0x180003e23  and     r10d, 8007007Ah
0x180003e2a  test    rcx, rcx
0x180003e2d  cmovnz  rdx, r8
0x180003e31  mov     [rdx], r15w
0x180003e35  jz      loc_18000427D
0x180003e3b  mov     r8, r9
0x180003e3e  mov     rax, r14
0x180003e41  cmp     [rax], r15w
0x180003e45  jz      short loc_180003E4F
0x180003e47  add     rax, rdi
0x180003e4a  sub     r8, r13
0x180003e4d  jnz     short loc_180003E41
0x180003e4f  mov     rax, r8
0x180003e52  mov     rcx, r9
0x180003e55  neg     rax
0x180003e58  mov     rax, r8
0x180003e5b  sbb     edx, edx
0x180003e5d  sub     rcx, r8
0x180003e60  not     edx
0x180003e62  and     edx, esi
0x180003e64  neg     rax
0x180003e67  sbb     r10, r10
0x180003e6a  and     r10, rcx
0x180003e6d  test    r8, r8
0x180003e70  jz      short loc_180003EBC
0x180003e72  lea     rcx, aCredhist; "CREDHIST"
0x180003e79  lea     rax, [r14+r10*2]
0x180003e7d  sub     r9, r10
0x180003e80  jz      short loc_180003EA0
0x180003e82  test    r11, r11
0x180003e85  jz      short loc_180003EA0
0x180003e87  movzx   edx, word ptr [rcx]
0x180003e8a  test    dx, dx
0x180003e8d  jz      short loc_180003EA0
0x180003e8f  mov     [rax], dx
0x180003e92  add     rcx, rdi
0x180003e95  add     rax, rdi
0x180003e98  sub     r11, r13
0x180003e9b  sub     r9, r13
0x180003e9e  jnz     short loc_180003E82
0x180003ea0  test    r9, r9
0x180003ea3  lea     rcx, [rax-2]
0x180003ea7  cmovnz  rcx, rax
0x180003eab  neg     r9
0x180003eae  sbb     edx, edx
0x180003eb0  not     edx
0x180003eb2  and     edx, 8007007Ah
0x180003eb8  mov     [rcx], r15w
0x180003ebc  test    edx, edx
0x180003ebe  jz      loc_180003F5A
0x180003ec4  mov     rax, cs:WPP_GLOBAL_Control
0x180003ecb  lea     rbx, WPP_GLOBAL_Control
0x180003ed2  cmp     rax, rbx
0x180003ed5  jz      short loc_180003EE1
0x180003ed7  test    [rax+1Ch], r13b
0x180003edb  jnz     loc_1800042A6
0x180003ee1  mov     ebx, 57h ; 'W'
0x180003ee6  mov     rcx, r12; hMem
0x180003ee9  call    DestroyCredentialHistoryMap
0x180003eee  jmp     short loc_180003F2D
0x180003ef0  mov     edx, 8
0x180003ef5  mov     ebx, edx
0x180003ef7  mov     rax, cs:WPP_GLOBAL_Control
0x180003efe  cmp     rax, rdi
0x180003f01  jz      short loc_180003F0D
0x180003f03  test    byte ptr [rax+1Ch], 1
0x180003f07  jnz     loc_18000436D
0x180003f0d  test    r13, r13
0x180003f10  jnz     loc_180004534
0x180003f16  test    rsi, rsi
0x180003f19  jnz     loc_180004541
0x180003f1f  test    r15, r15
0x180003f22  jnz     loc_180004555
0x180003f28  test    r12, r12
0x180003f2b  jnz     short loc_180003EE6
0x180003f2d  mov     eax, ebx
0x180003f2f  mov     rcx, [rbp+1C0h+var_40]
0x180003f36  xor     rcx, rsp; StackCookie
0x180003f39  call    __security_check_cookie
0x180003f3e  mov     rbx, [rsp+2C0h+arg_10]
0x180003f46  add     rsp, 290h
0x180003f4d  pop     r15
0x180003f4f  pop     r14
0x180003f51  pop     r13
0x180003f53  pop     r12
0x180003f55  pop     rdi
0x180003f56  pop     rsi
0x180003f57  pop     rbp
0x180003f58  retn
0x180003f5a  mov     r13, [r12]
0x180003f5e  lea     rdi, [rsp+2C0h+var_24E]
0x180003f63  movsxd  rax, ebx
0x180003f66  mov     rcx, r13; void *
0x180003f69  mov     rsi, r15
0x180003f6c  lea     rdi, [rdi+rax*2]
0x180003f70  call    ?AcquireExclusiveLockForUser@@YAXPEAX@Z; AcquireExclusiveLockForUser(void *)
0x180003f75  mov     [rsp+2C0h+var_298], 10000006h; unsigned int
0x180003f7d  xor     r8d, r8d; dwShareMode
0x180003f80  mov     edx, 0C0000000h; dwDesiredAccess
0x180003f85  mov     dword ptr [rsp+2C0h+lpOverlapped], 4; DWORD
0x180003f8d  mov     rcx, r14; lpFileName
0x180003f90  call    ?CreateFileWithRetries@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; CreateFileWithRetries(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x180003f95  mov     r15, rax
0x180003f98  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003f9c  jz      loc_1800042DA
0x180003fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fa9  lea     rdi, WPP_GLOBAL_Control
0x180003fb0  cmp     rcx, rdi
0x180003fb3  jz      short loc_180003FBF
0x180003fb5  test    byte ptr [rcx+1Ch], 4
0x180003fb9  jnz     loc_180004337
0x180003fbf  lea     rdx, [rsp+2C0h+FileSizeHigh]; lpFileSizeHigh
0x180003fc4  mov     rcx, r15; hFile
0x180003fc7  call    cs:__imp_GetFileSize
0x180003fce  nop     dword ptr [rax+rax+00h]
0x180003fd3  mov     ebx, eax
0x180003fd5  cmp     eax, 0FFFFFFFFh
0x180003fd8  jz      loc_180004354
0x180003fde  cmp     [rsp+2C0h+FileSizeHigh], esi
0x180003fe2  jnz     loc_18000415A
0x180003fe8  mov     r14d, 18h
0x180003fee  cmp     ebx, r14d
0x180003ff1  jb      loc_1800043A1
0x180003ff7  mov     rdx, rbx; uBytes
0x180003ffa  xor     ecx, ecx; uFlags
0x180003ffc  call    cs:__imp_LocalAlloc
  ... truncated ...
```
