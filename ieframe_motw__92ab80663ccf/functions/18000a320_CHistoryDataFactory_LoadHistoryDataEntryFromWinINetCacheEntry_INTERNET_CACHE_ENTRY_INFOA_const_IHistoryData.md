# CHistoryDataFactory::LoadHistoryDataEntryFromWinINetCacheEntry(_INTERNET_CACHE_ENTRY_INFOA const *,IHistoryData * *)

- ea: `0x18000a320`
- end: `0x18000ace8`
- name: `?LoadHistoryDataEntryFromWinINetCacheEntry@CHistoryDataFactory@@UEAAJPEBU_INTERNET_CACHE_ENTRY_INFOA@@PEAPEAUIHistoryData@@@Z`
- size: `2504`
- prototype: `__int64 __fastcall(CHistoryDataFactory *__hidden this, const struct _INTERNET_CACHE_ENTRY_INFOA *, struct IHistoryData **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009610`
- `0x1800096dc`
- `0x18000a320`
- `0x18000bc38`
- `0x1800bf0d8`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000abb0`
- `msvcrt!_wcsnicmp` at `0x18000abb0`
- `KERNEL32!MultiByteToWideChar` at `0x18000a4a1`
- `KERNEL32!MultiByteToWideChar` at `0x18000a4a1`
- `KERNEL32!lstrlenW` at `0x18000ac12`
- `KERNEL32!lstrlenW` at `0x18000ac12`
- `KERNEL32!InitOnceExecuteOnce` at `0x18000a9a2`
- `KERNEL32!InitOnceExecuteOnce` at `0x18000a9a2`
- `KERNEL32!GetProcessHeap` at `0x18000a44c`
- `KERNEL32!GetProcessHeap` at `0x18000a4e1`
- `KERNEL32!GetProcessHeap` at `0x18000a511`
- `KERNEL32!GetProcessHeap` at `0x18000aaf4`
- `KERNEL32!GetProcessHeap` at `0x18000a44c`
- `KERNEL32!GetProcessHeap` at `0x18000a4e1`
- `KERNEL32!GetProcessHeap` at `0x18000a511`
- `KERNEL32!GetProcessHeap` at `0x18000aaf4`
- `KERNEL32!HeapAlloc` at `0x18000a46a`
- `KERNEL32!HeapAlloc` at `0x18000a529`
- `KERNEL32!HeapAlloc` at `0x18000a46a`
- `KERNEL32!HeapAlloc` at `0x18000a529`
- `KERNEL32!LeaveCriticalSection` at `0x18000a3b7`
- `KERNEL32!LeaveCriticalSection` at `0x18000a3b7`
- `KERNEL32!EnterCriticalSection` at `0x18000a383`
- `KERNEL32!EnterCriticalSection` at `0x18000a383`
- `KERNEL32!HeapFree` at `0x18000a4f5`
- `KERNEL32!HeapFree` at `0x18000ab08`
- `KERNEL32!HeapFree` at `0x18000a4f5`
- `KERNEL32!HeapFree` at `0x18000ab08`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x18000a671`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x18000a671`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18000a960`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18000a960`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000a69d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000aad9`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000aae8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000a69d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000aad9`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000aae8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18000a598`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18000a598`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000a5d2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000a5f0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000abcd`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000a5d2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000a5f0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000abcd`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x18000a80f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x18000a80f`
- `Secur32!GetUserNameExW` at `0x18000abf1`
- `Secur32!GetUserNameExW` at `0x18000abf1`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000a5b6`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000a856`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000a5b6`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000a856`

## pseudocode

```c
__int64 __fastcall CHistoryDataFactory::LoadHistoryDataEntryFromWinINetCacheEntry(
        CHistoryDataFactory *this,
        const struct _INTERNET_CACHE_ENTRY_INFOA *a2,
        struct IHistoryData **a3)
{
  HRESULT Error; // ebx
  void **v4; // r14
  WCHAR *v6; // rsi
  __int64 v7; // rdi
  __int64 v8; // rax
  _WORD *v9; // rdx
  _WORD *v10; // rcx
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  wchar_t *v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rcx
  HRESULT v16; // esi
  HANDLE v17; // rax
  const WCHAR *v18; // rsi
  HANDLE v19; // rax
  char *v20; // rax
  _QWORD *v21; // rdi
  _QWORD *v22; // r12
  LPVOID *v23; // r14
  LPVOID *v24; // r15
  unsigned __int64 v25; // rax
  void **v26; // r9
  WCHAR *v27; // rcx
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64 *, wchar_t *); // rcx
  int v30; // eax
  __int16 v31; // dx
  unsigned __int64 v32; // rax
  wchar_t *v33; // r9
  int v34; // ecx
  unsigned __int64 v35; // rcx
  int v36; // eax
  ULONG v37; // esi
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64 *, wchar_t *); // rcx
  IStream *v39; // rax
  IStream *v40; // r15
  __int64 *v41; // r14
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64 *, wchar_t *); // r12
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 (__fastcall ***v45)(_QWORD, GUID *, __int64 *, wchar_t *); // rcx
  HANDLE v46; // rax
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64 *, wchar_t *); // rcx
  HRESULT v48; // eax
  __int64 (__fastcall ***v49)(_QWORD, GUID *, __int64 *, wchar_t *); // rcx
  __int64 v50; // rsi
  int v51; // r14d
  char *v52; // r8
  WCHAR *v53; // rdx
  wchar_t v54; // ax
  ULONG nSize[2]; // [rsp+30h] [rbp-D0h] BYREF
  void *v56; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR psz; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v59; // [rsp+58h] [rbp-A8h]
  __int64 *v60; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v61; // [rsp+68h] [rbp-98h] BYREF
  void **ppv; // [rsp+70h] [rbp-90h]
  GUID v63; // [rsp+78h] [rbp-88h] BYREF
  int v64; // [rsp+88h] [rbp-78h]
  _WORD v65[264]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t pwszDst[2088]; // [rsp+2A0h] [rbp+1A0h] BYREF
  char v67; // [rsp+12F0h] [rbp+11F0h] BYREF

  ppv = (void **)a3;
  *a3 = 0;
  psz = 0;
  Error = 0;
  pwszDst[0] = 0;
  v4 = (void **)a3;
  v65[0] = 0;
  EnterCriticalSection(&g_userNameInfo);
  v6 = &SrcStr;
  v7 = 257;
  if ( !SrcStr )
  {
    nSize[0] = 257;
    if ( GetUserNameExW((EXTENDED_NAME_FORMAT)65538, &SrcStr, nSize) )
    {
      v67 = 0;
      v51 = 257;
      lstrlenW(&SrcStr);
      SHUnicodeToAnsiInetCP(0xFDE9u, &SrcStr, 2084);
      v52 = &v67;
      v53 = &SrcStr;
      if ( v67 )
      {
        do
        {
          if ( v51 <= 3 )
            break;
          v54 = *v52;
          if ( v54 > 0x7Fu )
          {
            v51 -= 3;
            *v53 = 37;
            v53[1] = a0123456789abcd_0[((unsigned __int64)v54 >> 4) & 0xF];
            v53 += 2;
            v54 = a0123456789abcd_0[v54 & 0xF];
          }
          else
          {
            --v51;
          }
          ++v52;
          *v53++ = v54;
        }
        while ( *v52 );
      }
      v4 = ppv;
      *v53 = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
  }
  LeaveCriticalSection(&g_userNameInfo);
  if ( Error >= 0 )
  {
    v8 = 2147483646;
    v9 = v65;
    do
    {
      if ( !v8 )
        break;
      if ( !*v6 )
        break;
      *v9++ = *v6++;
      --v8;
      --v7;
    }
    while ( v7 );
    v10 = v9 - 1;
    Error = v7 == 0 ? 0x8007007A : 0;
    if ( v7 )
      v10 = v9;
    *v10 = 0;
    if ( v7 )
    {
      Error = StringCchPrintfW(pwszDst, 0x10Du, L"%s%s@", L"Visited: ", v65);
      if ( Error >= 0 )
      {
        ProcessHeap = GetProcessHeap();
        lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0x1048u);
        v13 = lpWideCharStr;
        if ( !lpWideCharStr )
          std::_Xbad_alloc();
        Error = -2147467259;
        if ( MultiByteToWideChar(0xFDE9u, 0, a2->lpszSourceUrlName, -1, lpWideCharStr, 2084) <= 0 )
          goto LABEL_18;
        v14 = -1;
        do
          ++v14;
        while ( pwszDst[v14] );
        v15 = -1;
        do
          ++v15;
        while ( v13[v15] );
        if ( (unsigned int)v15 <= (unsigned int)v14
          || (v50 = (unsigned int)v14, _wcsnicmp(pwszDst, v13, (unsigned int)v14)) )
        {
LABEL_18:
          v16 = -2147467259;
        }
        else
        {
          v16 = SHStrDupW(&v13[v50], (LPWSTR *)&psz);
        }
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v13);
        if ( v16 < 0 )
        {
          Error = v16;
          goto LABEL_34;
        }
        v18 = psz;
        *v4 = 0;
        v19 = GetProcessHeap();
        v20 = (char *)HeapAlloc(v19, 8u, 0x50u);
        v21 = v20;
        if ( !v20 )
          std::_Xbad_alloc();
        *((_DWORD *)v20 + 2) = 1;
        *(_QWORD *)v20 = &CHistoryData::`vftable';
        v22 = v20 + 48;
        v23 = (LPVOID *)(v20 + 56);
        *((_QWORD *)v20 + 6) = 0;
        *((_QWORD *)v20 + 7) = 0;
        *(_QWORD *)(v20 + 12) = c_li0;
        v24 = (LPVOID *)(v20 + 64);
        *(_QWORD *)(v20 + 20) = c_li0;
        *(_QWORD *)(v20 + 28) = c_li0;
        *(_QWORD *)(v20 + 36) = c_li0;
        *((_QWORD *)v20 + 8) = 0;
        v20[72] = 1;
        if ( SHAnsiToUnicode(a2->lpszSourceUrlName, pwszDst, 2084) <= 0 )
          goto LABEL_33;
        Error = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)v21 + 6);
        if ( Error < 0 )
          goto LABEL_31;
        Error = SHStrDupW(v18, (LPWSTR *)v21 + 8);
        if ( Error < 0 )
          goto LABEL_31;
        Error = SHStrDupW(pwszDst, (LPWSTR *)v21 + 7);
        if ( Error < 0 )
          goto LABEL_31;
        *(_OWORD *)pvar = 0;
        v25 = 0;
        LOWORD(pvar[0]) = 19;
        LODWORD(pvar[1]) = 0;
        v59 = 0;
        while ( v25 < 0x24 )
        {
          if ( dword_1806073F0[2 * v25] == 13 )
          {
            if ( word_1806073F4[4 * v25] != 19 )
            {
              Error = -2147023267;
              *((_BYTE *)v21 + 72) = 1;
              goto LABEL_31;
            }
            break;
          }
          ++v25;
        }
        v29 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *, wchar_t *))*v22;
        v64 = 13;
        v63 = FMTID_InternetSite;
        v30 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *, wchar_t *), GUID *, PROPVARIANT *))(*v29)[6])(
                v29,
                &v63,
                pvar);
        *((_BYTE *)v21 + 72) = 1;
        Error = v30;
        if ( v30 < 0 )
          goto LABEL_31;
        v31 = (__int16)pvar[0];
        if ( !LOWORD(pvar[0]) )
          goto LABEL_96;
        v32 = 0;
        v33 = &_ImageBase;
        while ( 1 )
        {
          v34 = 0;
          if ( v32 >= 0x24 )
            break;
          if ( dword_1806073F0[2 * v32] == 6 )
          {
            LOBYTE(v34) = LOWORD(pvar[0]) != (unsigned __int16)word_1806073F4[4 * v32];
            ++v34;
            break;
          }
          ++v32;
        }
        if ( v34 == 2 )
        {
          Error = -2147023267;
        }
        else
        {
LABEL_96:
          v47 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *, wchar_t *))*v22;
          v64 = 6;
          v63 = FMTID_InternetSite;
          v48 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *, wchar_t *), GUID *, PROPVARIANT *))(*v47)[6])(
                  v47,
                  &v63,
                  pvar);
          v31 = (__int16)pvar[0];
          Error = v48;
        }
        *((_BYTE *)v21 + 72) = 1;
        if ( Error < 0 )
        {
LABEL_31:
          if ( Error < 0 )
            goto LABEL_33;
        }
        else
        {
          if ( !v31 )
            goto LABEL_97;
          v35 = 0;
          v33 = &_ImageBase;
          while ( 1 )
          {
            v36 = 0;
            if ( v35 >= 0x24 )
              break;
            if ( dword_1806073F0[2 * v35] == 9 )
            {
              LOBYTE(v36) = v31 != word_1806073F4[4 * v35];
              ++v36;
              break;
            }
            ++v35;
          }
          if ( v36 == 2 )
          {
            Error = -2147023267;
          }
          else
          {
LABEL_97:
            v49 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *, wchar_t *))*v22;
            v64 = 9;
            v63 = FMTID_InternetSite;
            Error = (*v49)[6](v49, &v63, (__int64 *)pvar, v33);
          }
          v37 = 0;
          *((_BYTE *)v21 + 72) = 1;
          if ( Error < 0 )
            goto LABEL_33;
          Error = 0;
          if ( a2->dwHeaderInfoSize )
          {
            v38 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *, wchar_t *))*v22;
            v61 = 0;
            Error = (**v38)(v38, &GUID_00000109_0000_0000_c000_000000000046, &v61, v33);
            if ( Error >= 0 )
            {
              v39 = SHCreateMemStream((const BYTE *)a2->lpHeaderInfo, a2->dwHeaderInfoSize);
              v40 = v39;
              if ( v39 )
              {
                Error = (*(__int64 (__fastcall **)(__int64, IStream *))(*(_QWORD *)v61 + 40LL))(v61, v39);
                if ( Error < 0 )
                {
                  if ( Error == -2147024883 )
                    Error = 0;
                }
                else
                {
                  v56 = 0;
                  Error = PSCreateMemoryPropertyStore(&GUID_00000109_0000_0000_c000_000000000046, &v56);
                  if ( Error >= 0 && (*(int (__fastcall **)(void *, IStream *))(*(_QWORD *)v56 + 40LL))(v56, v40) >= 0 )
                  {
                    v60 = 0;
                    Error = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 **))v56)(
                              v56,
                              &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                              &v60);
                    if ( Error >= 0 )
                    {
                      v41 = v60;
                      v42 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *, wchar_t *))*v22;
                      nSize[0] = 0;
                      for ( Error = (*(__int64 (__fastcall **)(__int64 *, ULONG *))(*v60 + 24))(v60, nSize);
                            Error >= 0;
                            ++v37 )
                      {
                        if ( v37 >= nSize[0] )
                          break;
                        v64 = 0;
                        v43 = *v41;
                        v63 = 0;
                        Error = (*(__int64 (__fastcall **)(__int64 *, _QWORD, GUID *))(v43 + 32))(v41, v37, &v63);
                        if ( Error >= 0 )
                        {
                          v59 = 0;
                          v44 = *v41;
                          *(_OWORD *)pvar = 0;
                          Error = (*(__int64 (__fastcall **)(__int64 *, GUID *, PROPVARIANT *))(v44 + 40))(
                                    v41,
                                    &v63,
                                    pvar);
                          if ( Error >= 0 )
                          {
                            Error = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *, wchar_t *), GUID *, PROPVARIANT *))(*v42)[6])(
                                      v42,
                                      &v63,
                                      pvar);
                            PropVariantClear(pvar);
                          }
                        }
                      }
                      if ( Error >= 0
                        && a2->CacheEntryType == 2097153
                        && (InitOnceExecuteOnce(&InitOnce, InitOnceVersionInfo, 0, 0),
                            VersionInformation.dwPlatformId == 2)
                        && (VersionInformation.dwMajorVersion > 6
                         || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion > 1) )
                      {
                        *(_QWORD *)nSize = 0;
                        v22 = v21 + 6;
                        if ( (**(int (__fastcall ***)(_QWORD, GUID *, ULONG *))v21[6])(
                               v21[6],
                               &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917,
                               nSize) >= 0
                          && (*(int (__fastcall **)(_QWORD, __int64))(**(_QWORD **)nSize + 24LL))(*(_QWORD *)nSize, 2) >= 0 )
                        {
                          *((_BYTE *)v21 + 72) = 0;
                        }
                        if ( *(_QWORD *)nSize )
                          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)nSize + 16LL))(*(_QWORD *)nSize);
                      }
                      else
                      {
                        v22 = v21 + 6;
                      }
                      v23 = (LPVOID *)(v21 + 7);
                    }
                    if ( v60 )
                      (*(void (__fastcall **)(__int64 *))(*v60 + 16))(v60);
                  }
                  if ( v56 )
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v56 + 16LL))(v56);
                }
                (*(void (__fastcall **)(IStream *))(*(_QWORD *)v40 + 16LL))(v40);
              }
              else
              {
                Error = -2147024882;
              }
              v24 = (LPVOID *)(v21 + 8);
            }
            if ( v61 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
          }
          if ( Error < 0 )
            goto LABEL_33;
          *(FILETIME *)((char *)v21 + 12) = a2->LastAccessTime;
          *(FILETIME *)((char *)v21 + 20) = a2->LastModifiedTime;
          *(FILETIME *)((char *)v21 + 28) = a2->ExpireTime;
          *(FILETIME *)((char *)v21 + 36) = a2->LastSyncTime;
        }
        v26 = ppv;
        *ppv = 0;
        Error = QISearch(
                  v21,
                  &`CHistoryData::QueryInterface'::`2'::qit,
                  &GUID_94aeefba_1ea6_41d9_b4c7_a37a98d3da6f,
                  v26);
LABEL_33:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v21 + 2, 0xFFFFFFFF) == 1 )
        {
          v45 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *, wchar_t *))*v22;
          *v21 = &CHistoryData::`vftable';
          if ( v45 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *, wchar_t *)))(*v45)[2])(v45);
          CoTaskMemFree(*v23);
          CoTaskMemFree(*v24);
          v46 = GetProcessHeap();
          HeapFree(v46, 0, v21);
        }
      }
    }
  }
LABEL_34:
  v27 = (WCHAR *)psz;
  psz = 0;
  CoTaskMemFree(v27);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000a320  mov     [rsp-8+arg_0], rbx
0x18000a325  push    rbp
0x18000a326  push    rsi
0x18000a327  push    rdi
0x18000a328  push    r12
0x18000a32a  push    r13
0x18000a32c  push    r14
0x18000a32e  push    r15
0x18000a330  lea     rbp, [rsp-1A30h]
0x18000a338  mov     eax, 1B30h
0x18000a33d  call    _alloca_probe
0x18000a342  sub     rsp, rax
0x18000a345  mov     rax, cs:__security_cookie
0x18000a34c  xor     rax, rsp
0x18000a34f  mov     [rbp+1A60h+var_40], rax
0x18000a356  xor     r15d, r15d
0x18000a359  mov     [rsp+1B60h+ppv], r8
0x18000a35e  lea     rcx, ?g_userNameInfo@@3VCUserNameInfo@@A; lpCriticalSection
0x18000a365  mov     [r8], r15
0x18000a368  mov     [rsp+1B60h+psz], r15
0x18000a36d  mov     ebx, r15d
0x18000a370  mov     [rbp+1A60h+pwszDst], r15w
0x18000a378  mov     r14, r8
0x18000a37b  mov     [rbp+1A60h+var_1AD0], r15w
0x18000a380  mov     r13, rdx
0x18000a383  call    cs:__imp_EnterCriticalSection
0x18000a38a  nop     dword ptr [rax+rax+00h]
0x18000a38f  cmp     cs:SrcStr, r15w
0x18000a397  lea     rsi, SrcStr
0x18000a39e  mov     edi, 101h
0x18000a3a3  lea     r12, __ImageBase
0x18000a3aa  jz      loc_18000ABE0
0x18000a3b0  lea     rcx, ?g_userNameInfo@@3VCUserNameInfo@@A; lpCriticalSection
0x18000a3b7  call    cs:__imp_LeaveCriticalSection
0x18000a3be  nop     dword ptr [rax+rax+00h]
0x18000a3c3  test    ebx, ebx
0x18000a3c5  js      loc_18000A693
0x18000a3cb  mov     eax, 7FFFFFFEh
0x18000a3d0  lea     rdx, [rbp+1A60h+var_1AD0]
0x18000a3d4  test    rax, rax
0x18000a3d7  jz      short loc_18000A3F5
0x18000a3d9  movzx   ecx, word ptr [rsi]
0x18000a3dc  test    cx, cx
0x18000a3df  jz      short loc_18000A3F5
0x18000a3e1  mov     [rdx], cx
0x18000a3e4  add     rsi, 2
0x18000a3e8  add     rdx, 2
0x18000a3ec  dec     rax
0x18000a3ef  sub     rdi, 1
0x18000a3f3  jnz     short loc_18000A3D4
0x18000a3f5  mov     rax, rdi
0x18000a3f8  lea     rcx, [rdx-2]
0x18000a3fc  neg     rax
0x18000a3ff  sbb     ebx, ebx
0x18000a401  not     ebx
0x18000a403  and     ebx, 8007007Ah
0x18000a409  test    rdi, rdi
0x18000a40c  cmovnz  rcx, rdx
0x18000a410  mov     [rcx], r15w
0x18000a414  jz      loc_18000A693
0x18000a41a  lea     rax, [rbp+1A60h+var_1AD0]
0x18000a41e  mov     edx, 10Dh; unsigned __int64
0x18000a423  lea     r9, aVisited_0; "Visited: "
0x18000a42a  mov     [rsp+1B60h+lpWideCharStr], rax
0x18000a42f  lea     r8, aSS_6; "%s%s@"
0x18000a436  lea     rcx, [rbp+1A60h+pwszDst]; unsigned __int16 *
0x18000a43d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a442  mov     ebx, eax
0x18000a444  test    eax, eax
0x18000a446  js      loc_18000A693
0x18000a44c  call    cs:__imp_GetProcessHeap
0x18000a453  nop     dword ptr [rax+rax+00h]
0x18000a458  mov     r12d, 8
0x18000a45e  mov     r8d, 1048h; dwBytes
0x18000a464  mov     rcx, rax; hHeap
0x18000a467  mov     edx, r12d; dwFlags
0x18000a46a  call    cs:__imp_HeapAlloc
0x18000a471  nop     dword ptr [rax+rax+00h]
0x18000a476  mov     rdi, rax
0x18000a479  test    rax, rax
0x18000a47c  jz      loc_18000A6D6
0x18000a482  mov     r8, [r13+8]; lpMultiByteStr
0x18000a486  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a48a  mov     r9d, esi; cbMultiByte
0x18000a48d  mov     [rsp+1B60h+cchWideChar], 824h; cchWideChar
0x18000a495  xor     edx, edx; dwFlags
0x18000a497  mov     [rsp+1B60h+lpWideCharStr], rax; lpWideCharStr
0x18000a49c  mov     ecx, 0FDE9h; CodePage
0x18000a4a1  call    cs:__imp_MultiByteToWideChar
0x18000a4a8  nop     dword ptr [rax+rax+00h]
0x18000a4ad  mov     ebx, 80004005h
0x18000a4b2  test    eax, eax
0x18000a4b4  jle     short loc_18000A4DF
0x18000a4b6  lea     rcx, [rbp+1A60h+pwszDst]
0x18000a4bd  mov     rax, rsi
0x18000a4c0  inc     rax
0x18000a4c3  cmp     [rcx+rax*2], r15w
0x18000a4c8  jnz     short loc_18000A4C0
0x18000a4ca  mov     rcx, rsi
0x18000a4cd  inc     rcx
0x18000a4d0  cmp     [rdi+rcx*2], r15w
0x18000a4d5  jnz     short loc_18000A4CD
0x18000a4d7  cmp     ecx, eax
0x18000a4d9  ja      loc_18000ABA1
0x18000a4df  mov     esi, ebx
0x18000a4e1  call    cs:__imp_GetProcessHeap
0x18000a4e8  nop     dword ptr [rax+rax+00h]
0x18000a4ed  mov     r8, rdi; lpMem
0x18000a4f0  xor     edx, edx; dwFlags
0x18000a4f2  mov     rcx, rax; hHeap
0x18000a4f5  call    cs:__imp_HeapFree
0x18000a4fc  nop     dword ptr [rax+rax+00h]
0x18000a501  test    esi, esi
0x18000a503  js      loc_18000AB28
0x18000a509  mov     rsi, [rsp+1B60h+psz]
0x18000a50e  mov     [r14], r15
0x18000a511  call    cs:__imp_GetProcessHeap
0x18000a518  nop     dword ptr [rax+rax+00h]
0x18000a51d  mov     r8d, 50h ; 'P'; dwBytes
0x18000a523  mov     edx, r12d; dwFlags
0x18000a526  mov     rcx, rax; hHeap
0x18000a529  call    cs:__imp_HeapAlloc
0x18000a530  nop     dword ptr [rax+rax+00h]
0x18000a535  mov     rdi, rax
0x18000a538  test    rax, rax
0x18000a53b  jz      loc_18000AAAA
0x18000a541  lea     rax, ??_7CHistoryData@@6B@; const CHistoryData::`vftable'
0x18000a548  mov     dword ptr [rdi+8], 1
0x18000a54f  mov     [rdi], rax
0x18000a552  lea     r12, [rdi+30h]
0x18000a556  mov     rax, cs:c_li0
0x18000a55d  lea     r14, [rdi+38h]
0x18000a561  mov     [r12], r15
0x18000a565  lea     rdx, [rbp+1A60h+pwszDst]; pwszDst
0x18000a56c  mov     [r14], r15
0x18000a56f  mov     r8d, 824h; cwchBuf
0x18000a575  mov     [rdi+0Ch], rax
0x18000a579  lea     r15, [rdi+40h]
0x18000a57d  mov     [rdi+14h], rax
0x18000a581  mov     [rdi+1Ch], rax
0x18000a585  mov     [rdi+24h], rax
0x18000a589  mov     qword ptr [r15], 0
0x18000a590  mov     byte ptr [rdi+48h], 1
0x18000a594  mov     rcx, [r13+8]; pszSrc
0x18000a598  call    cs:__imp_SHAnsiToUnicode
0x18000a59f  nop     dword ptr [rax+rax+00h]
0x18000a5a4  test    eax, eax
0x18000a5a6  jle     loc_18000A67F
0x18000a5ac  mov     rdx, r12; ppv
0x18000a5af  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18000a5b6  call    cs:__imp_PSCreateMemoryPropertyStore
0x18000a5bd  nop     dword ptr [rax+rax+00h]
0x18000a5c2  mov     ebx, eax
0x18000a5c4  test    eax, eax
0x18000a5c6  js      loc_18000AC81
0x18000a5cc  mov     rdx, r15; ppwsz
0x18000a5cf  mov     rcx, rsi; psz
0x18000a5d2  call    cs:__imp_SHStrDupW
0x18000a5d9  nop     dword ptr [rax+rax+00h]
0x18000a5de  xor     esi, esi
0x18000a5e0  mov     ebx, eax
0x18000a5e2  test    eax, eax
0x18000a5e4  js      short loc_18000A654
0x18000a5e6  mov     rdx, r14; ppwsz
0x18000a5e9  lea     rcx, [rbp+1A60h+pwszDst]; psz
0x18000a5f0  call    cs:__imp_SHStrDupW
0x18000a5f7  nop     dword ptr [rax+rax+00h]
0x18000a5fc  mov     ebx, eax
0x18000a5fe  test    eax, eax
0x18000a600  js      short loc_18000A654
0x18000a602  xorps   xmm0, xmm0
0x18000a605  lea     ecx, [rsi+13h]
0x18000a608  movups  xmmword ptr [rsp+1B60h+pvar], xmm0
0x18000a60d  xor     eax, eax
0x18000a60f  mov     word ptr [rsp+1B60h+pvar], cx
0x18000a614  mov     dword ptr [rsp+1B60h+pvar+8], esi
0x18000a618  lea     rdx, __ImageBase
0x18000a61f  mov     [rsp+1B60h+var_1B08], rax
0x18000a624  cmp     rax, 24h ; '$'
0x18000a628  jnb     loc_18000A6DC
0x18000a62e  cmp     ds:rva dword_1806073F0[rdx+rax*8], 0Dh
0x18000a636  jz      short loc_18000A63D
0x18000a638  inc     rax
0x18000a63b  jmp     short loc_18000A624
0x18000a63d  cmp     cx, ds:rva word_1806073F4[rdx+rax*8]
0x18000a645  jz      loc_18000A6DC
0x18000a64b  mov     ebx, 8007065Dh
0x18000a650  mov     byte ptr [rdi+48h], 1
0x18000a654  test    ebx, ebx
0x18000a656  js      short loc_18000A67F
0x18000a658  mov     r9, [rsp+1B60h+ppv]; ppv
0x18000a65d  lea     r8, _GUID_94aeefba_1ea6_41d9_b4c7_a37a98d3da6f; riid
0x18000a664  lea     rdx, ?qit@?1??QueryInterface@CHistoryData@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x18000a66b  mov     rcx, rdi; that
0x18000a66e  mov     [r9], rsi
0x18000a671  call    cs:__imp_QISearch
0x18000a678  nop     dword ptr [rax+rax+00h]
0x18000a67d  mov     ebx, eax
0x18000a67f  or      eax, 0FFFFFFFFh
0x18000a682  lock xadd [rdi+8], eax
0x18000a687  cmp     eax, 1
0x18000a68a  jz      loc_18000AAB7
0x18000a690  xor     r15d, r15d
0x18000a693  mov     rcx, [rsp+1B60h+psz]; pv
0x18000a698  mov     [rsp+1B60h+psz], r15
0x18000a69d  call    cs:__imp_CoTaskMemFree
0x18000a6a4  nop     dword ptr [rax+rax+00h]
0x18000a6a9  mov     eax, ebx
0x18000a6ab  mov     rcx, [rbp+1A60h+var_40]
0x18000a6b2  xor     rcx, rsp; StackCookie
0x18000a6b5  call    __security_check_cookie
0x18000a6ba  mov     rbx, [rsp+1B60h+arg_0]
0x18000a6c2  add     rsp, 1B30h
0x18000a6c9  pop     r15
0x18000a6cb  pop     r14
0x18000a6cd  pop     r13
0x18000a6cf  pop     r12
0x18000a6d1  pop     rdi
0x18000a6d2  pop     rsi
0x18000a6d3  pop     rbp
0x18000a6d4  retn
0x18000a6d6  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000a6dc  movups  xmm0, xmmword ptr cs:FMTID_InternetSite.Data1
0x18000a6e3  mov     rcx, [r12]
0x18000a6e7  lea     r8, [rsp+1B60h+pvar]
0x18000a6ec  mov     [rbp+1A60h+var_1AD8], 0Dh
0x18000a6f3  lea     rdx, [rsp+1B60h+var_1AE8]
0x18000a6f8  movdqu  [rsp+1B60h+var_1AE8], xmm0
0x18000a6fe  mov     rax, [rcx]
0x18000a701  mov     rax, [rax+30h]
0x18000a705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a70a  xor     r8d, r8d
0x18000a70d  mov     byte ptr [rdi+48h], 1
0x18000a711  mov     ebx, eax
0x18000a713  test    eax, eax
0x18000a715  js      loc_18000A654
0x18000a71b  movzx   edx, word ptr [rsp+1B60h+pvar]
0x18000a720  mov     esi, 8007065Dh
0x18000a725  test    dx, dx
0x18000a728  jz      loc_18000AB2F
0x18000a72e  mov     eax, r8d
0x18000a731  lea     r9, __ImageBase
0x18000a738  mov     ecx, r8d
0x18000a73b  cmp     rax, 24h ; '$'
0x18000a73f  jnb     short loc_18000A75F
0x18000a741  cmp     ds:rva dword_1806073F0[r9+rax*8], 6
0x18000a74a  jz      short loc_18000A751
0x18000a74c  inc     rax
0x18000a74f  jmp     short loc_18000A738
0x18000a751  cmp     dx, ds:rva word_1806073F4[r9+rax*8]
0x18000a75a  setnz   cl
0x18000a75d  inc     ecx
0x18000a75f  cmp     ecx, 2
0x18000a762  mov     ebx, r8d
0x18000a765  cmovz   ebx, esi
0x18000a768  jnz     loc_18000AB2F
0x18000a76e  mov     byte ptr [rdi+48h], 1
0x18000a772  test    ebx, ebx
0x18000a774  js      loc_18000AC81
0x18000a77a  test    dx, dx
0x18000a77d  jz      loc_18000AB6C
0x18000a783  mov     rcx, r8
0x18000a786  lea     r9, __ImageBase
0x18000a78d  mov     eax, r8d
0x18000a790  cmp     rcx, 24h ; '$'
0x18000a794  jnb     short loc_18000A7B4
0x18000a796  cmp     ds:rva dword_1806073F0[r9+rcx*8], 9
0x18000a79f  jz      short loc_18000A7A6
0x18000a7a1  inc     rcx
0x18000a7a4  jmp     short loc_18000A78D
0x18000a7a6  cmp     dx, ds:rva word_1806073F4[r9+rcx*8]
0x18000a7af  setnz   al
0x18000a7b2  inc     eax
0x18000a7b4  cmp     eax, 2
0x18000a7b7  mov     ebx, r8d
0x18000a7ba  cmovz   ebx, esi
0x18000a7bd  jnz     loc_18000AB6C
0x18000a7c3  xor     esi, esi
0x18000a7c5  mov     byte ptr [rdi+48h], 1
0x18000a7c9  test    ebx, ebx
0x18000a7cb  js      loc_18000A67F
0x18000a7d1  mov     ebx, esi
0x18000a7d3  cmp     [r13+58h], esi
0x18000a7d7  jbe     loc_18000AA7D
0x18000a7dd  mov     rcx, [r12]
0x18000a7e1  lea     r8, [rsp+1B60h+var_1AF8]
0x18000a7e6  mov     [rsp+1B60h+var_1AF8], rsi
0x18000a7eb  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18000a7f2  mov     rax, [rcx]
0x18000a7f5  mov     rax, [rax]
0x18000a7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7fd  mov     ebx, eax
0x18000a7ff  test    eax, eax
0x18000a801  js      loc_18000AA67
0x18000a807  mov     edx, [r13+58h]; cbInit
0x18000a80b  mov     rcx, [r13+50h]; pInit
0x18000a80f  call    cs:__imp_SHCreateMemStream
0x18000a816  nop     dword ptr [rax+rax+00h]
0x18000a81b  mov     r15, rax
0x18000a81e  test    rax, rax
  ... truncated ...
```
