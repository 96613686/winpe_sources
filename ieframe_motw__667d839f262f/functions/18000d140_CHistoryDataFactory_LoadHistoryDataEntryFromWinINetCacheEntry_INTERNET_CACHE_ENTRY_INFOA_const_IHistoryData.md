# CHistoryDataFactory::LoadHistoryDataEntryFromWinINetCacheEntry(_INTERNET_CACHE_ENTRY_INFOA const *,IHistoryData * *)

- ea: `0x18000d140`
- end: `0x18000da61`
- name: `?LoadHistoryDataEntryFromWinINetCacheEntry@CHistoryDataFactory@@UEAAJPEBU_INTERNET_CACHE_ENTRY_INFOA@@PEAPEAUIHistoryData@@@Z`
- size: `2337`
- prototype: `__int64 __fastcall(CHistoryDataFactory *__hidden this, const struct _INTERNET_CACHE_ENTRY_INFOA *, struct IHistoryData **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a0f8`
- `0x18000c530`
- `0x18000c5f0`
- `0x18000d140`
- `0x1800b83c8`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000d945`
- `msvcrt!_wcsnicmp` at `0x18000d945`
- `KERNEL32!MultiByteToWideChar` at `0x18000d2a9`
- `KERNEL32!MultiByteToWideChar` at `0x18000d2a9`
- `KERNEL32!lstrlenW` at `0x18000d991`
- `KERNEL32!lstrlenW` at `0x18000d991`
- `KERNEL32!InitOnceExecuteOnce` at `0x18000d755`
- `KERNEL32!InitOnceExecuteOnce` at `0x18000d755`
- `KERNEL32!GetProcessHeap` at `0x18000d260`
- `KERNEL32!GetProcessHeap` at `0x18000d2e3`
- `KERNEL32!GetProcessHeap` at `0x18000d307`
- `KERNEL32!GetProcessHeap` at `0x18000d895`
- `KERNEL32!GetProcessHeap` at `0x18000d260`
- `KERNEL32!GetProcessHeap` at `0x18000d2e3`
- `KERNEL32!GetProcessHeap` at `0x18000d307`
- `KERNEL32!GetProcessHeap` at `0x18000d895`
- `KERNEL32!HeapAlloc` at `0x18000d278`
- `KERNEL32!HeapAlloc` at `0x18000d319`
- `KERNEL32!HeapAlloc` at `0x18000d278`
- `KERNEL32!HeapAlloc` at `0x18000d319`
- `KERNEL32!LeaveCriticalSection` at `0x18000d1d1`
- `KERNEL32!LeaveCriticalSection` at `0x18000d1d1`
- `KERNEL32!EnterCriticalSection` at `0x18000d1a3`
- `KERNEL32!EnterCriticalSection` at `0x18000d1a3`
- `KERNEL32!HeapFree` at `0x18000d2f1`
- `KERNEL32!HeapFree` at `0x18000d8a3`
- `KERNEL32!HeapFree` at `0x18000d2f1`
- `KERNEL32!HeapFree` at `0x18000d8a3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x18000d443`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x18000d443`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18000d719`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18000d719`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000d469`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000d886`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000d88f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000d469`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000d886`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000d88f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18000d382`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18000d382`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000d3b0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000d3c8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000d95c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000d3b0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000d3c8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000d95c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x18000d5d4`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x18000d5d4`
- `Secur32!GetUserNameExW` at `0x18000d97a`
- `Secur32!GetUserNameExW` at `0x18000d97a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000d39a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000d615`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000d39a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000d615`

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
  v6 = &NameBuffer;
  v7 = 257;
  if ( !NameBuffer )
  {
    nSize[0] = 257;
    if ( GetUserNameExW((EXTENDED_NAME_FORMAT)65538, &NameBuffer, nSize) )
    {
      v67 = 0;
      v51 = 257;
      lstrlenW(&NameBuffer);
      SHUnicodeToAnsiInetCP(0xFDE9u, &NameBuffer, 2084);
      v52 = &v67;
      v53 = &NameBuffer;
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
          if ( dword_1805C31B0[2 * v25] == 13 )
          {
            if ( word_1805C31B4[4 * v25] != 19 )
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
          if ( dword_1805C31B0[2 * v32] == 6 )
          {
            LOBYTE(v34) = LOWORD(pvar[0]) != (unsigned __int16)word_1805C31B4[4 * v32];
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
            if ( dword_1805C31B0[2 * v35] == 9 )
            {
              LOBYTE(v36) = v31 != word_1805C31B4[4 * v35];
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
0x18000d140  mov     [rsp-8+arg_0], rbx
0x18000d145  push    rbp
0x18000d146  push    rsi
0x18000d147  push    rdi
0x18000d148  push    r12
0x18000d14a  push    r13
0x18000d14c  push    r14
0x18000d14e  push    r15
0x18000d150  lea     rbp, [rsp-1A30h]
0x18000d158  mov     eax, 1B30h
0x18000d15d  call    _alloca_probe
0x18000d162  sub     rsp, rax
0x18000d165  mov     rax, cs:__security_cookie
0x18000d16c  xor     rax, rsp
0x18000d16f  mov     [rbp+1A60h+var_40], rax
0x18000d176  xor     r15d, r15d
0x18000d179  mov     [rsp+1B60h+ppv], r8
0x18000d17e  lea     rcx, ?g_userNameInfo@@3VCUserNameInfo@@A; lpCriticalSection
0x18000d185  mov     [r8], r15
0x18000d188  mov     [rsp+1B60h+psz], r15
0x18000d18d  mov     ebx, r15d
0x18000d190  mov     [rbp+1A60h+pwszDst], r15w
0x18000d198  mov     r14, r8
0x18000d19b  mov     [rbp+1A60h+var_1AD0], r15w
0x18000d1a0  mov     r13, rdx
0x18000d1a3  call    cs:__imp_EnterCriticalSection
0x18000d1a9  cmp     cs:NameBuffer, r15w
0x18000d1b1  lea     rsi, NameBuffer
0x18000d1b8  mov     edi, 101h
0x18000d1bd  lea     r12, __ImageBase
0x18000d1c4  jz      loc_18000D969
0x18000d1ca  lea     rcx, ?g_userNameInfo@@3VCUserNameInfo@@A; lpCriticalSection
0x18000d1d1  call    cs:__imp_LeaveCriticalSection
0x18000d1d7  test    ebx, ebx
0x18000d1d9  js      loc_18000D45F
0x18000d1df  mov     eax, 7FFFFFFEh
0x18000d1e4  lea     rdx, [rbp+1A60h+var_1AD0]
0x18000d1e8  test    rax, rax
0x18000d1eb  jz      short loc_18000D209
0x18000d1ed  movzx   ecx, word ptr [rsi]
0x18000d1f0  test    cx, cx
0x18000d1f3  jz      short loc_18000D209
0x18000d1f5  mov     [rdx], cx
0x18000d1f8  add     rsi, 2
0x18000d1fc  add     rdx, 2
0x18000d200  dec     rax
0x18000d203  sub     rdi, 1
0x18000d207  jnz     short loc_18000D1E8
0x18000d209  mov     rax, rdi
0x18000d20c  lea     rcx, [rdx-2]
0x18000d210  neg     rax
0x18000d213  sbb     ebx, ebx
0x18000d215  not     ebx
0x18000d217  and     ebx, 8007007Ah
0x18000d21d  test    rdi, rdi
0x18000d220  cmovnz  rcx, rdx
0x18000d224  mov     [rcx], r15w
0x18000d228  jz      loc_18000D45F
0x18000d22e  lea     rax, [rbp+1A60h+var_1AD0]
0x18000d232  mov     edx, 10Dh; unsigned __int64
0x18000d237  lea     r9, aVisited_0; "Visited: "
0x18000d23e  mov     [rsp+1B60h+lpWideCharStr], rax
0x18000d243  lea     r8, aSS_6; "%s%s@"
0x18000d24a  lea     rcx, [rbp+1A60h+pwszDst]; unsigned __int16 *
0x18000d251  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d256  mov     ebx, eax
0x18000d258  test    eax, eax
0x18000d25a  js      loc_18000D45F
0x18000d260  call    cs:__imp_GetProcessHeap
0x18000d266  mov     r12d, 8
0x18000d26c  mov     r8d, 1048h; dwBytes
0x18000d272  mov     rcx, rax; hHeap
0x18000d275  mov     edx, r12d; dwFlags
0x18000d278  call    cs:__imp_HeapAlloc
0x18000d27e  mov     rdi, rax
0x18000d281  test    rax, rax
0x18000d284  jz      loc_18000D49B
0x18000d28a  mov     r8, [r13+8]; lpMultiByteStr
0x18000d28e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000d292  mov     r9d, esi; cbMultiByte
0x18000d295  mov     [rsp+1B60h+cchWideChar], 824h; cchWideChar
0x18000d29d  xor     edx, edx; dwFlags
0x18000d29f  mov     [rsp+1B60h+lpWideCharStr], rax; lpWideCharStr
0x18000d2a4  mov     ecx, 0FDE9h; CodePage
0x18000d2a9  call    cs:__imp_MultiByteToWideChar
0x18000d2af  mov     ebx, 80004005h
0x18000d2b4  test    eax, eax
0x18000d2b6  jle     short loc_18000D2E1
0x18000d2b8  lea     rcx, [rbp+1A60h+pwszDst]
0x18000d2bf  mov     rax, rsi
0x18000d2c2  inc     rax
0x18000d2c5  cmp     [rcx+rax*2], r15w
0x18000d2ca  jnz     short loc_18000D2C2
0x18000d2cc  mov     rcx, rsi
0x18000d2cf  inc     rcx
0x18000d2d2  cmp     [rdi+rcx*2], r15w
0x18000d2d7  jnz     short loc_18000D2CF
0x18000d2d9  cmp     ecx, eax
0x18000d2db  ja      loc_18000D936
0x18000d2e1  mov     esi, ebx
0x18000d2e3  call    cs:__imp_GetProcessHeap
0x18000d2e9  mov     r8, rdi; lpMem
0x18000d2ec  xor     edx, edx; dwFlags
0x18000d2ee  mov     rcx, rax; hHeap
0x18000d2f1  call    cs:__imp_HeapFree
0x18000d2f7  test    esi, esi
0x18000d2f9  js      loc_18000D8BD
0x18000d2ff  mov     rsi, [rsp+1B60h+psz]
0x18000d304  mov     [r14], r15
0x18000d307  call    cs:__imp_GetProcessHeap
0x18000d30d  mov     r8d, 50h ; 'P'; dwBytes
0x18000d313  mov     edx, r12d; dwFlags
0x18000d316  mov     rcx, rax; hHeap
0x18000d319  call    cs:__imp_HeapAlloc
0x18000d31f  mov     rdi, rax
0x18000d322  test    rax, rax
0x18000d325  jz      loc_18000D857
0x18000d32b  lea     rax, ??_7CHistoryData@@6B@; const CHistoryData::`vftable'
0x18000d332  mov     dword ptr [rdi+8], 1
0x18000d339  mov     [rdi], rax
0x18000d33c  lea     r12, [rdi+30h]
0x18000d340  mov     rax, cs:c_li0
0x18000d347  lea     r14, [rdi+38h]
0x18000d34b  mov     [r12], r15
0x18000d34f  lea     rdx, [rbp+1A60h+pwszDst]; pwszDst
0x18000d356  mov     [r14], r15
0x18000d359  mov     r8d, 824h; cwchBuf
0x18000d35f  mov     [rdi+0Ch], rax
0x18000d363  lea     r15, [rdi+40h]
0x18000d367  mov     [rdi+14h], rax
0x18000d36b  mov     [rdi+1Ch], rax
0x18000d36f  mov     [rdi+24h], rax
0x18000d373  mov     qword ptr [r15], 0
0x18000d37a  mov     byte ptr [rdi+48h], 1
0x18000d37e  mov     rcx, [r13+8]; pszSrc
0x18000d382  call    cs:__imp_SHAnsiToUnicode
0x18000d388  test    eax, eax
0x18000d38a  jle     loc_18000D44B
0x18000d390  mov     rdx, r12; ppv
0x18000d393  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18000d39a  call    cs:__imp_PSCreateMemoryPropertyStore
0x18000d3a0  mov     ebx, eax
0x18000d3a2  test    eax, eax
0x18000d3a4  js      loc_18000D9FA
0x18000d3aa  mov     rdx, r15; ppwsz
0x18000d3ad  mov     rcx, rsi; psz
0x18000d3b0  call    cs:__imp_SHStrDupW
0x18000d3b6  xor     esi, esi
0x18000d3b8  mov     ebx, eax
0x18000d3ba  test    eax, eax
0x18000d3bc  js      short loc_18000D426
0x18000d3be  mov     rdx, r14; ppwsz
0x18000d3c1  lea     rcx, [rbp+1A60h+pwszDst]; psz
0x18000d3c8  call    cs:__imp_SHStrDupW
0x18000d3ce  mov     ebx, eax
0x18000d3d0  test    eax, eax
0x18000d3d2  js      short loc_18000D426
0x18000d3d4  xorps   xmm0, xmm0
0x18000d3d7  lea     ecx, [rsi+13h]
0x18000d3da  movups  xmmword ptr [rsp+1B60h+pvar], xmm0
0x18000d3df  xor     eax, eax
0x18000d3e1  mov     word ptr [rsp+1B60h+pvar], cx
0x18000d3e6  mov     dword ptr [rsp+1B60h+pvar+8], esi
0x18000d3ea  lea     rdx, __ImageBase
0x18000d3f1  mov     [rsp+1B60h+var_1B08], rax
0x18000d3f6  cmp     rax, 24h ; '$'
0x18000d3fa  jnb     loc_18000D4A1
0x18000d400  cmp     ds:rva dword_1805C31B0[rdx+rax*8], 0Dh
0x18000d408  jz      short loc_18000D40F
0x18000d40a  inc     rax
0x18000d40d  jmp     short loc_18000D3F6
0x18000d40f  cmp     cx, ds:rva word_1805C31B4[rdx+rax*8]
0x18000d417  jz      loc_18000D4A1
0x18000d41d  mov     ebx, 8007065Dh
0x18000d422  mov     byte ptr [rdi+48h], 1
0x18000d426  test    ebx, ebx
0x18000d428  js      short loc_18000D44B
0x18000d42a  mov     r9, [rsp+1B60h+ppv]; ppv
0x18000d42f  lea     r8, _GUID_94aeefba_1ea6_41d9_b4c7_a37a98d3da6f; riid
0x18000d436  lea     rdx, ?qit@?1??QueryInterface@CHistoryData@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x18000d43d  mov     rcx, rdi; that
0x18000d440  mov     [r9], rsi
0x18000d443  call    cs:__imp_QISearch
0x18000d449  mov     ebx, eax
0x18000d44b  or      eax, 0FFFFFFFFh
0x18000d44e  lock xadd [rdi+8], eax
0x18000d453  cmp     eax, 1
0x18000d456  jz      loc_18000D864
0x18000d45c  xor     r15d, r15d
0x18000d45f  mov     rcx, [rsp+1B60h+psz]; pv
0x18000d464  mov     [rsp+1B60h+psz], r15
0x18000d469  call    cs:__imp_CoTaskMemFree
0x18000d46f  mov     eax, ebx
0x18000d471  mov     rcx, [rbp+1A60h+var_40]
0x18000d478  xor     rcx, rsp; StackCookie
0x18000d47b  call    __security_check_cookie
0x18000d480  mov     rbx, [rsp+1B60h+arg_0]
0x18000d488  add     rsp, 1B30h
0x18000d48f  pop     r15
0x18000d491  pop     r14
0x18000d493  pop     r13
0x18000d495  pop     r12
0x18000d497  pop     rdi
0x18000d498  pop     rsi
0x18000d499  pop     rbp
0x18000d49a  retn
0x18000d49b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000d4a1  movups  xmm0, xmmword ptr cs:FMTID_InternetSite.Data1
0x18000d4a8  mov     rcx, [r12]
0x18000d4ac  lea     r8, [rsp+1B60h+pvar]
0x18000d4b1  mov     [rbp+1A60h+var_1AD8], 0Dh
0x18000d4b8  lea     rdx, [rsp+1B60h+var_1AE8]
0x18000d4bd  movdqu  [rsp+1B60h+var_1AE8], xmm0
0x18000d4c3  mov     rax, [rcx]
0x18000d4c6  mov     rax, [rax+30h]
0x18000d4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4cf  xor     r8d, r8d
0x18000d4d2  mov     byte ptr [rdi+48h], 1
0x18000d4d6  mov     ebx, eax
0x18000d4d8  test    eax, eax
0x18000d4da  js      loc_18000D426
0x18000d4e0  movzx   edx, word ptr [rsp+1B60h+pvar]
0x18000d4e5  mov     esi, 8007065Dh
0x18000d4ea  test    dx, dx
0x18000d4ed  jz      loc_18000D8C4
0x18000d4f3  mov     eax, r8d
0x18000d4f6  lea     r9, __ImageBase
0x18000d4fd  mov     ecx, r8d
0x18000d500  cmp     rax, 24h ; '$'
0x18000d504  jnb     short loc_18000D524
0x18000d506  cmp     ds:rva dword_1805C31B0[r9+rax*8], 6
0x18000d50f  jz      short loc_18000D516
0x18000d511  inc     rax
0x18000d514  jmp     short loc_18000D4FD
0x18000d516  cmp     dx, ds:rva word_1805C31B4[r9+rax*8]
0x18000d51f  setnz   cl
0x18000d522  inc     ecx
0x18000d524  cmp     ecx, 2
0x18000d527  mov     ebx, r8d
0x18000d52a  cmovz   ebx, esi
0x18000d52d  jnz     loc_18000D8C4
0x18000d533  mov     byte ptr [rdi+48h], 1
0x18000d537  test    ebx, ebx
0x18000d539  js      loc_18000D9FA
0x18000d53f  test    dx, dx
0x18000d542  jz      loc_18000D901
0x18000d548  mov     rcx, r8
0x18000d54b  lea     r9, __ImageBase
0x18000d552  mov     eax, r8d
0x18000d555  cmp     rcx, 24h ; '$'
0x18000d559  jnb     short loc_18000D579
0x18000d55b  cmp     ds:rva dword_1805C31B0[r9+rcx*8], 9
0x18000d564  jz      short loc_18000D56B
0x18000d566  inc     rcx
0x18000d569  jmp     short loc_18000D552
0x18000d56b  cmp     dx, ds:rva word_1805C31B4[r9+rcx*8]
0x18000d574  setnz   al
0x18000d577  inc     eax
0x18000d579  cmp     eax, 2
0x18000d57c  mov     ebx, r8d
0x18000d57f  cmovz   ebx, esi
0x18000d582  jnz     loc_18000D901
0x18000d588  xor     esi, esi
0x18000d58a  mov     byte ptr [rdi+48h], 1
0x18000d58e  test    ebx, ebx
0x18000d590  js      loc_18000D44B
0x18000d596  mov     ebx, esi
0x18000d598  cmp     [r13+58h], esi
0x18000d59c  jbe     loc_18000D82A
0x18000d5a2  mov     rcx, [r12]
0x18000d5a6  lea     r8, [rsp+1B60h+var_1AF8]
0x18000d5ab  mov     [rsp+1B60h+var_1AF8], rsi
0x18000d5b0  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18000d5b7  mov     rax, [rcx]
0x18000d5ba  mov     rax, [rax]
0x18000d5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5c2  mov     ebx, eax
0x18000d5c4  test    eax, eax
0x18000d5c6  js      loc_18000D814
0x18000d5cc  mov     edx, [r13+58h]; cbInit
0x18000d5d0  mov     rcx, [r13+50h]; pInit
0x18000d5d4  call    cs:__imp_SHCreateMemStream
0x18000d5da  mov     r15, rax
0x18000d5dd  test    rax, rax
0x18000d5e0  jz      loc_18000D85D
0x18000d5e6  mov     rcx, [rsp+1B60h+var_1AF8]
0x18000d5eb  mov     rdx, r15
0x18000d5ee  mov     rax, [rcx]
0x18000d5f1  mov     rax, [rax+28h]
0x18000d5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5fa  mov     ebx, eax
0x18000d5fc  test    eax, eax
0x18000d5fe  js      loc_18000DA0D
0x18000d604  lea     rdx, [rsp+1B60h+var_1B28]; ppv
0x18000d609  mov     [rsp+1B60h+var_1B28], rsi
0x18000d60e  lea     rcx, _GUID_00000109_0000_0000_c000_000000000046; riid
0x18000d615  call    cs:__imp_PSCreateMemoryPropertyStore
0x18000d61b  mov     ebx, eax
0x18000d61d  test    eax, eax
0x18000d61f  js      loc_18000D7EB
  ... truncated ...
```
