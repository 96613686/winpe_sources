# CHistoryDataFactory::s_LoadHistoryDataFromPrefixInfo(CWinINetPrefixInfo const *,ushort * *,IHistoryData * *)

- ea: `0x180027c90`
- end: `0x18002848a`
- name: `?s_LoadHistoryDataFromPrefixInfo@CHistoryDataFactory@@CAJPEBVCWinINetPrefixInfo@@PEAPEAGPEAPEAUIHistoryData@@@Z`
- size: `2042`
- prototype: `static int(const struct CWinINetPrefixInfo *, unsigned __int16 **, struct IHistoryData **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18043f000`
- `0x18043f170`

## callees

- `0x180027c90`
- `0x1800b83c8`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180027faf`
- `msvcrt!memcpy_s` at `0x180027faf`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800281b7`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800281b7`
- `KERNEL32!GetProcessHeap` at `0x180027cdf`
- `KERNEL32!GetProcessHeap` at `0x180027fd3`
- `KERNEL32!GetProcessHeap` at `0x1800283a1`
- `KERNEL32!GetProcessHeap` at `0x180027cdf`
- `KERNEL32!GetProcessHeap` at `0x180027fd3`
- `KERNEL32!GetProcessHeap` at `0x1800283a1`
- `KERNEL32!HeapAlloc` at `0x180027cf3`
- `KERNEL32!HeapAlloc` at `0x180027cf3`
- `KERNEL32!HeapFree` at `0x180027fe1`
- `KERNEL32!HeapFree` at `0x1800283af`
- `KERNEL32!HeapFree` at `0x180027fe1`
- `KERNEL32!HeapFree` at `0x1800283af`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x1800282c1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x1800282c1`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18002817e`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18002817e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180027f28`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180027f28`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180027fbc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002828e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180028391`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002839b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180027fbc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002828e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180028391`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002839b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180027d6d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180027d84`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180028318`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180027d6d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180027d84`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180028318`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x18002804b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x18002804b`
- `WININET!GetUrlCacheEntryBinaryBlob` at `0x180027f0d`
- `WININET!GetUrlCacheEntryBinaryBlob` at `0x180027f0d`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180027d56`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180028089`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180027d56`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180028089`

## pseudocode

```c
__int64 __fastcall CHistoryDataFactory::s_LoadHistoryDataFromPrefixInfo(
        const WCHAR **a1,
        unsigned __int16 **a2,
        struct IHistoryData **a3)
{
  LPWSTR *v3; // r14
  const struct CWinINetPrefixInfo *v4; // r15
  const WCHAR *v5; // rsi
  const WCHAR *v6; // rbx
  HANDLE ProcessHeap; // rax
  char *v8; // r13
  _QWORD *v9; // r12
  int k; // edi
  unsigned __int64 v11; // rax
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  int v13; // eax
  __int16 v14; // r8
  unsigned __int64 i; // rax
  int v16; // edx
  unsigned __int64 j; // rax
  int v18; // ecx
  char *v19; // rbx
  signed int UrlCacheEntryBinaryBlob; // eax
  SIZE_T v21; // rsi
  char *v22; // rax
  char *v23; // rdi
  BYTE *v24; // rsi
  HANDLE v25; // rax
  unsigned int v26; // esi
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // rcx
  IStream *v28; // rax
  IStream *v29; // r12
  __int64 *v30; // r14
  __int64 v31; // r15
  __int64 v32; // rax
  __int64 v33; // rax
  int (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // rcx
  const WCHAR *v35; // rcx
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // rcx
  HANDLE v38; // rax
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall ***v40)(_QWORD, GUID *, __int64 *); // rcx
  int v41; // eax
  DWORD pcbBlob; // [rsp+40h] [rbp-89h] BYREF
  __int64 v43; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int16 **v44; // [rsp+50h] [rbp-79h]
  const struct CWinINetPrefixInfo *v45; // [rsp+58h] [rbp-71h]
  DWORD dwType; // [rsp+60h] [rbp-69h] BYREF
  BYTE *ppbBlob; // [rsp+68h] [rbp-61h] BYREF
  void *ppv; // [rsp+70h] [rbp-59h] BYREF
  void *v49; // [rsp+78h] [rbp-51h] BYREF
  PROPVARIANT pvar[2]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v51; // [rsp+90h] [rbp-39h]
  FILETIME pftModifiedTime; // [rsp+98h] [rbp-31h] BYREF
  __int64 *v53; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-21h] BYREF
  FILETIME pftExpireTime; // [rsp+B0h] [rbp-19h] BYREF
  FILETIME pftAccessTime; // [rsp+B8h] [rbp-11h] BYREF
  struct IHistoryData **v57; // [rsp+C0h] [rbp-9h]
  GUID v58; // [rsp+C8h] [rbp-1h] BYREF
  int v59; // [rsp+D8h] [rbp+Fh]

  v57 = a3;
  v44 = a2;
  v3 = a2;
  v45 = (const struct CWinINetPrefixInfo *)a1;
  v4 = (const struct CWinINetPrefixInfo *)a1;
  if ( a2 )
    *a2 = 0;
  *a3 = 0;
  v5 = a1[2];
  v6 = *a1;
  v49 = 0;
  ProcessHeap = GetProcessHeap();
  v8 = (char *)HeapAlloc(ProcessHeap, 8u, 0x50u);
  if ( !v8 )
    std::_Xbad_alloc();
  *(_QWORD *)v8 = &CHistoryData::`vftable';
  v9 = v8 + 48;
  *(_QWORD *)(v8 + 12) = c_li0;
  *(_QWORD *)(v8 + 20) = c_li0;
  *(_QWORD *)(v8 + 28) = c_li0;
  *(_QWORD *)(v8 + 36) = c_li0;
  *((_DWORD *)v8 + 2) = 1;
  *((_QWORD *)v8 + 6) = 0;
  *((_QWORD *)v8 + 7) = 0;
  *((_QWORD *)v8 + 8) = 0;
  v8[72] = 1;
  k = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)v8 + 6);
  if ( k < 0 )
    goto LABEL_74;
  k = SHStrDupW(v6, (LPWSTR *)v8 + 8);
  if ( k < 0 )
    goto LABEL_74;
  k = SHStrDupW(v5, (LPWSTR *)v8 + 7);
  if ( k < 0 )
    goto LABEL_74;
  v11 = 0;
  v51 = 0;
  *(_OWORD *)pvar = 0;
  LODWORD(pvar[1]) = 0;
  LOWORD(pvar[0]) = 19;
  while ( v11 < 0x24 )
  {
    if ( dword_1805C31B0[2 * v11] == 13 )
    {
      if ( LOWORD(dword_1805C31B0[2 * v11 + 1]) != 19 )
      {
        k = -2147023267;
        v8[72] = 1;
        goto LABEL_74;
      }
      break;
    }
    ++v11;
  }
  v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v9;
  v59 = 13;
  v58 = FMTID_InternetSite;
  v13 = (*v12)[6](v12, &v58, (__int64 *)pvar);
  v8[72] = 1;
  k = v13;
  if ( v13 < 0 )
    goto LABEL_74;
  v14 = (__int16)pvar[0];
  if ( !LOWORD(pvar[0]) )
    goto LABEL_103;
  for ( i = 0; ; ++i )
  {
    v16 = 0;
    if ( i >= 0x24 )
      break;
    if ( dword_1805C31B0[2 * i] == 6 )
    {
      LOBYTE(v16) = LOWORD(pvar[0]) != LOWORD(dword_1805C31B0[2 * i + 1]);
      ++v16;
      break;
    }
  }
  if ( v16 == 2 )
  {
    k = -2147023267;
  }
  else
  {
LABEL_103:
    v40 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v9;
    v59 = 6;
    v58 = FMTID_InternetSite;
    v41 = (*v40)[6](v40, &v58, (__int64 *)pvar);
    v14 = (__int16)pvar[0];
    k = v41;
  }
  v8[72] = 1;
  if ( k >= 0 )
  {
    if ( !v14 )
      goto LABEL_93;
    for ( j = 0; ; ++j )
    {
      v18 = 0;
      if ( j >= 0x24 )
        break;
      if ( dword_1805C31B0[2 * j] == 9 )
      {
        LOBYTE(v18) = v14 != LOWORD(dword_1805C31B0[2 * j + 1]);
        ++v18;
        break;
      }
    }
    if ( v18 == 2 )
    {
      k = -2147023267;
    }
    else
    {
LABEL_93:
      v39 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v9;
      v59 = 9;
      v58 = FMTID_InternetSite;
      k = (*v39)[6](v39, &v58, (__int64 *)pvar);
    }
    v8[72] = 1;
    if ( k >= 0 )
    {
      ppbBlob = 0;
      pcbBlob = 0;
      dwType = 0;
      pftExpireTime = 0;
      pftAccessTime = 0;
      v19 = 0;
      pftModifiedTime = 0;
      UrlCacheEntryBinaryBlob = GetUrlCacheEntryBinaryBlob(
                                  v5,
                                  &dwType,
                                  &pftExpireTime,
                                  &pftAccessTime,
                                  &pftModifiedTime,
                                  &ppbBlob,
                                  &pcbBlob);
      k = UrlCacheEntryBinaryBlob;
      if ( UrlCacheEntryBinaryBlob )
      {
        if ( UrlCacheEntryBinaryBlob > 0 )
          k = (unsigned __int16)UrlCacheEntryBinaryBlob | 0x80070000;
      }
      else
      {
        v21 = pcbBlob + 112;
        v22 = (char *)CoTaskMemAlloc(v21);
        v23 = v22;
        if ( v22 )
        {
          *(_OWORD *)(v22 + 4) = 0;
          *(_OWORD *)(v22 + 20) = 0;
          *(_OWORD *)(v22 + 36) = 0;
          *(_OWORD *)(v22 + 52) = 0;
          *(_OWORD *)(v22 + 68) = 0;
          *(_OWORD *)(v22 + 84) = 0;
          *((_OWORD *)v22 + 6) = 0;
          *(_DWORD *)v22 = 112;
          *((_DWORD *)v22 + 6) = dwType;
          *(FILETIME *)(v22 + 44) = pftModifiedTime;
          *(FILETIME *)(v22 + 52) = pftExpireTime;
          *(FILETIME *)(v22 + 60) = pftAccessTime;
          *(FILETIME *)(v22 + 68) = pftModifiedTime;
          if ( ppbBlob && pcbBlob )
          {
            *((_QWORD *)v22 + 10) = v22 + 112;
            *((_DWORD *)v22 + 22) = pcbBlob;
            memcpy_s(v22 + 112, v21 - 112, ppbBlob, pcbBlob);
          }
          v19 = v23;
          k = 0;
        }
        else
        {
          k = -2147024882;
        }
        CoTaskMemFree(0);
      }
      v24 = ppbBlob;
      ppbBlob = 0;
      if ( v24 )
      {
        v25 = GetProcessHeap();
        HeapFree(v25, 0, v24);
      }
      if ( k >= 0 )
      {
        v26 = 0;
        *(_QWORD *)(v8 + 12) = *(_QWORD *)(v19 + 60);
        k = 0;
        *(_QWORD *)(v8 + 20) = *(_QWORD *)(v19 + 44);
        *(_QWORD *)(v8 + 28) = *(_QWORD *)(v19 + 52);
        *(_QWORD *)(v8 + 36) = *(_QWORD *)(v19 + 68);
        if ( *((_DWORD *)v19 + 22) )
        {
          v27 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v9;
          v54 = 0;
          k = (**v27)(v27, &GUID_00000109_0000_0000_c000_000000000046, &v54);
          if ( k >= 0 )
          {
            v28 = SHCreateMemStream(*((const BYTE **)v19 + 10), *((_DWORD *)v19 + 22));
            v29 = v28;
            if ( v28 )
            {
              k = (*(__int64 (__fastcall **)(__int64, IStream *))(*(_QWORD *)v54 + 40LL))(v54, v28);
              if ( k < 0 )
              {
                if ( k == -2147024883 )
                  k = 0;
              }
              else
              {
                ppv = 0;
                k = PSCreateMemoryPropertyStore(&GUID_00000109_0000_0000_c000_000000000046, &ppv);
                if ( k >= 0 && (*(int (__fastcall **)(void *, IStream *))(*(_QWORD *)ppv + 40LL))(ppv, v29) >= 0 )
                {
                  v53 = 0;
                  k = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 **))ppv)(
                        ppv,
                        &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                        &v53);
                  if ( k >= 0 )
                  {
                    v30 = v53;
                    v31 = *((_QWORD *)v8 + 6);
                    LODWORD(v43) = 0;
                    for ( k = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*v53 + 24))(v53, &v43); k >= 0; ++v26 )
                    {
                      if ( v26 >= (unsigned int)v43 )
                        break;
                      v59 = 0;
                      v32 = *v30;
                      v58 = 0;
                      k = (*(__int64 (__fastcall **)(__int64 *, _QWORD, GUID *))(v32 + 32))(v30, v26, &v58);
                      if ( k >= 0 )
                      {
                        v51 = 0;
                        v33 = *v30;
                        *(_OWORD *)pvar = 0;
                        k = (*(__int64 (__fastcall **)(__int64 *, GUID *, PROPVARIANT *))(v33 + 40))(v30, &v58, pvar);
                        if ( k >= 0 )
                        {
                          k = (*(__int64 (__fastcall **)(__int64, GUID *, PROPVARIANT *))(*(_QWORD *)v31 + 48LL))(
                                v31,
                                &v58,
                                pvar);
                          PropVariantClear(pvar);
                        }
                      }
                    }
                    if ( k >= 0 && *((_DWORD *)v19 + 6) == 2097153 )
                    {
                      InitOnceExecuteOnce(&InitOnce, InitOnceVersionInfo, 0, 0);
                      if ( VersionInformation.dwPlatformId == 2
                        && (VersionInformation.dwMajorVersion > 6
                         || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion > 1) )
                      {
                        v34 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)v8 + 6);
                        v43 = 0;
                        if ( (**v34)(v34, &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &v43) >= 0
                          && (*(int (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, 2) >= 0 )
                        {
                          v8[72] = 0;
                        }
                        if ( v43 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                      }
                    }
                    v3 = v44;
                    v4 = v45;
                  }
                  if ( v53 )
                    (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
                }
                if ( ppv )
                  (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
              }
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)v29 + 16LL))(v29);
            }
            else
            {
              k = -2147024882;
            }
            v9 = v8 + 48;
          }
          if ( v54 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        }
      }
      CoTaskMemFree(v19);
LABEL_74:
      if ( k >= 0 )
      {
        v49 = 0;
        k = QISearch(v8, &`CHistoryData::QueryInterface'::`2'::qit, &GUID_94aeefba_1ea6_41d9_b4c7_a37a98d3da6f, &v49);
      }
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) == 1 )
  {
    v37 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v9;
    *(_QWORD *)v8 = &CHistoryData::`vftable';
    if ( v37 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v37)[2])(v37);
    CoTaskMemFree(*((LPVOID *)v8 + 7));
    CoTaskMemFree(*((LPVOID *)v8 + 8));
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v8);
  }
  if ( k < 0 )
    goto LABEL_83;
  v35 = (const WCHAR *)*((_QWORD *)v4 + 1);
  if ( !v35 )
    goto LABEL_92;
  if ( *v35 == 35 )
  {
    if ( ++v35 )
      goto LABEL_81;
LABEL_92:
    *v57 = (struct IHistoryData *)v49;
    return (unsigned int)k;
  }
  if ( !*v35 )
    goto LABEL_92;
LABEL_81:
  if ( !v3 )
    goto LABEL_92;
  k = SHStrDupW(v35, v3);
  if ( k >= 0 )
    goto LABEL_92;
LABEL_83:
  if ( v49 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v49 + 16LL))(v49);
  return (unsigned int)k;
}

```

## disassembly

```asm
0x180027c90  push    rbp
0x180027c92  push    rbx
0x180027c93  push    rsi
0x180027c94  push    rdi
0x180027c95  push    r13
0x180027c97  push    r14
0x180027c99  push    r15
0x180027c9b  lea     rbp, [rsp-27h]
0x180027ca0  sub     rsp, 0F0h
0x180027ca7  mov     rax, cs:__security_cookie
0x180027cae  xor     rax, rsp
0x180027cb1  mov     [rbp+57h+var_40], rax
0x180027cb5  xor     edi, edi
0x180027cb7  mov     [rbp+57h+var_60], r8
0x180027cbb  mov     [rbp+57h+var_D0], rdx
0x180027cbf  mov     r14, rdx
0x180027cc2  mov     [rbp+57h+var_C8], rcx
0x180027cc6  mov     r15, rcx
0x180027cc9  test    rdx, rdx
0x180027ccc  jz      short loc_180027CD1
0x180027cce  mov     [rdx], rdi
0x180027cd1  mov     [r8], rdi
0x180027cd4  mov     rsi, [rcx+10h]
0x180027cd8  mov     rbx, [rcx]
0x180027cdb  mov     [rbp+57h+var_A8], rdi
0x180027cdf  call    cs:__imp_GetProcessHeap
0x180027ce5  mov     edx, 8; dwFlags
0x180027cea  mov     r8d, 50h ; 'P'; dwBytes
0x180027cf0  mov     rcx, rax; hHeap
0x180027cf3  call    cs:__imp_HeapAlloc
0x180027cf9  mov     r13, rax
0x180027cfc  test    rax, rax
0x180027cff  jz      loc_180028367
0x180027d05  lea     rax, ??_7CHistoryData@@6B@; const CHistoryData::`vftable'
0x180027d0c  mov     [rsp+120h+arg_18], r12
0x180027d14  mov     [r13+0], rax
0x180027d18  lea     r12, [r13+30h]
0x180027d1c  mov     rax, cs:c_li0
0x180027d23  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180027d2a  mov     rdx, r12; ppv
0x180027d2d  mov     [r13+0Ch], rax
0x180027d31  mov     [r13+14h], rax
0x180027d35  mov     [r13+1Ch], rax
0x180027d39  mov     [r13+24h], rax
0x180027d3d  mov     dword ptr [r13+8], 1
0x180027d45  mov     [r12], rdi
0x180027d49  mov     [r13+38h], rdi
0x180027d4d  mov     [r13+40h], rdi
0x180027d51  mov     byte ptr [r13+48h], 1
0x180027d56  call    cs:__imp_PSCreateMemoryPropertyStore
0x180027d5c  mov     edi, eax
0x180027d5e  test    eax, eax
0x180027d60  js      loc_1800282A0
0x180027d66  lea     rdx, [r13+40h]; ppwsz
0x180027d6a  mov     rcx, rbx; psz
0x180027d6d  call    cs:__imp_SHStrDupW
0x180027d73  mov     edi, eax
0x180027d75  test    eax, eax
0x180027d77  js      loc_1800282A0
0x180027d7d  lea     rdx, [r13+38h]; ppwsz
0x180027d81  mov     rcx, rsi; psz
0x180027d84  call    cs:__imp_SHStrDupW
0x180027d8a  mov     edi, eax
0x180027d8c  test    eax, eax
0x180027d8e  js      loc_1800282A0
0x180027d94  xor     eax, eax
0x180027d96  lea     rbx, dword_1805C31B0
0x180027d9d  xorps   xmm0, xmm0
0x180027da0  mov     [rbp+57h+var_90], rax
0x180027da4  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180027da8  mov     edx, 13h
0x180027dad  mov     dword ptr [rbp+57h+pvar+8], eax
0x180027db0  mov     word ptr [rbp+57h+pvar], dx
0x180027db4  cmp     rax, 24h ; '$'
0x180027db8  jnb     short loc_180027DD8
0x180027dba  lea     rcx, ds:0[rax*8]
0x180027dc2  cmp     dword ptr [rcx+rbx], 0Dh
0x180027dc6  jz      short loc_180027DCD
0x180027dc8  inc     rax
0x180027dcb  jmp     short loc_180027DB4
0x180027dcd  cmp     dx, [rcx+rbx+4]
0x180027dd2  jnz     loc_180028296
0x180027dd8  movups  xmm0, xmmword ptr cs:FMTID_InternetSite.Data1
0x180027ddf  mov     rcx, [r12]
0x180027de3  lea     r8, [rbp+57h+pvar]
0x180027de7  mov     [rbp+57h+var_48], 0Dh
0x180027dee  lea     rdx, [rbp+57h+var_58]
0x180027df2  movups  [rbp+57h+var_58], xmm0
0x180027df6  mov     rax, [rcx]
0x180027df9  mov     rax, [rax+30h]
0x180027dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e02  mov     byte ptr [r13+48h], 1
0x180027e07  mov     edi, eax
0x180027e09  test    eax, eax
0x180027e0b  js      loc_1800282A0
0x180027e11  movzx   r8d, word ptr [rbp+57h+pvar]
0x180027e16  test    r8w, r8w
0x180027e1a  jz      loc_18002844C
0x180027e20  xor     r10d, r10d
0x180027e23  mov     eax, r10d
0x180027e26  mov     edx, r10d
0x180027e29  cmp     rax, 24h ; '$'
0x180027e2d  jnb     short loc_180027E4D
0x180027e2f  lea     rcx, ds:0[rax*8]
0x180027e37  cmp     dword ptr [rcx+rbx], 6
0x180027e3b  jz      short loc_180027E42
0x180027e3d  inc     rax
0x180027e40  jmp     short loc_180027E26
0x180027e42  cmp     r8w, [rcx+rbx+4]
0x180027e48  setnz   dl
0x180027e4b  inc     edx
0x180027e4d  cmp     edx, 2
0x180027e50  mov     edi, r10d
0x180027e53  mov     ebx, 8007065Dh
0x180027e58  cmovz   edi, ebx
0x180027e5b  jnz     loc_180028451
0x180027e61  mov     byte ptr [r13+48h], 1
0x180027e66  test    edi, edi
0x180027e68  js      loc_1800282C9
0x180027e6e  test    r8w, r8w
0x180027e72  jz      loc_1800283D4
0x180027e78  mov     rax, r10
0x180027e7b  lea     r9, dword_1805C31B0
0x180027e82  mov     ecx, r10d
0x180027e85  cmp     rax, 24h ; '$'
0x180027e89  jnb     short loc_180027EAA
0x180027e8b  lea     rdx, ds:0[rax*8]
0x180027e93  cmp     dword ptr [rdx+r9], 9
0x180027e98  jz      short loc_180027E9F
0x180027e9a  inc     rax
0x180027e9d  jmp     short loc_180027E82
0x180027e9f  cmp     r8w, [rdx+r9+4]
0x180027ea5  setnz   cl
0x180027ea8  inc     ecx
0x180027eaa  cmp     ecx, 2
0x180027ead  mov     edi, r10d
0x180027eb0  cmovz   edi, ebx
0x180027eb3  jnz     loc_1800283D4
0x180027eb9  mov     byte ptr [r13+48h], 1
0x180027ebe  test    edi, edi
0x180027ec0  js      loc_1800282C9
0x180027ec6  lea     rax, [rsp+120h+var_E0]
0x180027ecb  mov     [rbp+57h+var_B8], r10
0x180027ecf  mov     [rsp+120h+pcbBlob], rax; pcbBlob
0x180027ed4  lea     r9, [rbp+57h+pftAccessTime]; pftAccessTime
0x180027ed8  lea     rax, [rbp+57h+var_B8]
0x180027edc  mov     [rsp+120h+var_E0], r10d
0x180027ee1  mov     [rsp+120h+ppbBlob], rax; ppbBlob
0x180027ee6  lea     r8, [rbp+57h+pftExpireTime]; pftExpireTime
0x180027eea  lea     rax, [rbp+57h+var_88]
0x180027eee  mov     [rbp+57h+dwType], r10d
0x180027ef2  lea     rdx, [rbp+57h+dwType]; dwType
0x180027ef6  mov     [rsp+120h+pftModifiedTime], rax; pftModifiedTime
0x180027efb  mov     rcx, rsi; pwszUrlName
0x180027efe  mov     qword ptr [rbp+57h+pftExpireTime.dwLowDateTime], r10
0x180027f02  mov     qword ptr [rbp+57h+pftAccessTime.dwLowDateTime], r10
0x180027f06  mov     rbx, r10
0x180027f09  mov     qword ptr [rbp+57h+var_88.dwLowDateTime], r10
0x180027f0d  call    cs:__imp_GetUrlCacheEntryBinaryBlob
0x180027f13  mov     edi, eax
0x180027f15  test    eax, eax
0x180027f17  jnz     loc_180028408
0x180027f1d  mov     eax, [rsp+120h+var_E0]
0x180027f21  add     eax, 70h ; 'p'
0x180027f24  mov     ecx, eax; cb
0x180027f26  mov     esi, eax
0x180027f28  call    cs:__imp_CoTaskMemAlloc
0x180027f2e  mov     rdi, rax
0x180027f31  test    rax, rax
0x180027f34  jz      loc_18002841C
0x180027f3a  xorps   xmm0, xmm0
0x180027f3d  movups  xmmword ptr [rax+4], xmm0
0x180027f41  movups  xmmword ptr [rax+14h], xmm0
0x180027f45  movups  xmmword ptr [rax+24h], xmm0
0x180027f49  movups  xmmword ptr [rax+34h], xmm0
0x180027f4d  movups  xmmword ptr [rax+44h], xmm0
0x180027f51  movups  xmmword ptr [rax+54h], xmm0
0x180027f55  movups  xmmword ptr [rax+60h], xmm0
0x180027f59  mov     dword ptr [rax], 70h ; 'p'
0x180027f5f  mov     eax, [rbp+57h+dwType]
0x180027f62  mov     [rdi+18h], eax
0x180027f65  mov     rax, qword ptr [rbp+57h+var_88.dwLowDateTime]
0x180027f69  mov     [rdi+2Ch], rax
0x180027f6d  mov     rax, qword ptr [rbp+57h+pftExpireTime.dwLowDateTime]
0x180027f71  mov     [rdi+34h], rax
0x180027f75  mov     rax, qword ptr [rbp+57h+pftAccessTime.dwLowDateTime]
0x180027f79  mov     [rdi+3Ch], rax
0x180027f7d  mov     rax, qword ptr [rbp+57h+var_88.dwLowDateTime]
0x180027f81  mov     [rdi+44h], rax
0x180027f85  cmp     [rbp+57h+var_B8], 0
0x180027f8a  jz      short loc_180027FB5
0x180027f8c  cmp     [rsp+120h+var_E0], 0
0x180027f91  jbe     short loc_180027FB5
0x180027f93  lea     rcx, [rdi+70h]; Destination
0x180027f97  mov     [rdi+50h], rcx
0x180027f9b  lea     rdx, [rsi-70h]; DestinationSize
0x180027f9f  mov     eax, [rsp+120h+var_E0]
0x180027fa3  mov     [rdi+58h], eax
0x180027fa6  mov     r9d, [rsp+120h+var_E0]; SourceSize
0x180027fab  mov     r8, [rbp+57h+var_B8]; Source
0x180027faf  call    cs:__imp_memcpy_s
0x180027fb5  mov     rbx, rdi
0x180027fb8  xor     edi, edi
0x180027fba  xor     ecx, ecx; pv
0x180027fbc  call    cs:__imp_CoTaskMemFree
0x180027fc2  mov     rsi, [rbp+57h+var_B8]
0x180027fc6  mov     [rbp+57h+var_B8], 0
0x180027fce  test    rsi, rsi
0x180027fd1  jz      short loc_180027FE7
0x180027fd3  call    cs:__imp_GetProcessHeap
0x180027fd9  mov     r8, rsi; lpMem
0x180027fdc  xor     edx, edx; dwFlags
0x180027fde  mov     rcx, rax; hHeap
0x180027fe1  call    cs:__imp_HeapFree
0x180027fe7  test    edi, edi
0x180027fe9  js      loc_18002828B
0x180027fef  mov     rax, [rbx+3Ch]
0x180027ff3  xor     esi, esi
0x180027ff5  mov     [r13+0Ch], rax
0x180027ff9  mov     edi, esi
0x180027ffb  mov     rax, [rbx+2Ch]
0x180027fff  mov     [r13+14h], rax
0x180028003  mov     rax, [rbx+34h]
0x180028007  mov     [r13+1Ch], rax
0x18002800b  mov     rax, [rbx+44h]
0x18002800f  mov     [r13+24h], rax
0x180028013  cmp     [rbx+58h], esi
0x180028016  jbe     loc_18002828B
0x18002801c  mov     rcx, [r12]
0x180028020  lea     r8, [rbp+57h+var_78]
0x180028024  mov     [rbp+57h+var_78], rsi
0x180028028  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18002802f  mov     rax, [rcx]
0x180028032  mov     rax, [rax]
0x180028035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002803a  mov     edi, eax
0x18002803c  test    eax, eax
0x18002803e  js      loc_180028276
0x180028044  mov     edx, [rbx+58h]; cbInit
0x180028047  mov     rcx, [rbx+50h]; pInit
0x18002804b  call    cs:__imp_SHCreateMemStream
0x180028051  mov     r12, rax
0x180028054  test    rax, rax
0x180028057  jz      loc_18002835D
0x18002805d  mov     rcx, [rbp+57h+var_78]
0x180028061  mov     rdx, r12
0x180028064  mov     rax, [rcx]
0x180028067  mov     rax, [rax+28h]
0x18002806b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028070  mov     edi, eax
0x180028072  test    eax, eax
0x180028074  js      loc_18002843E
0x18002807a  lea     rdx, [rbp+57h+ppv]; ppv
0x18002807e  mov     [rbp+57h+ppv], rsi
0x180028082  lea     rcx, _GUID_00000109_0000_0000_c000_000000000046; riid
0x180028089  call    cs:__imp_PSCreateMemoryPropertyStore
0x18002808f  mov     edi, eax
0x180028091  test    eax, eax
0x180028093  js      loc_18002824D
0x180028099  mov     rcx, [rbp+57h+ppv]
0x18002809d  mov     rdx, r12
0x1800280a0  mov     rax, [rcx]
0x1800280a3  mov     rax, [rax+28h]
0x1800280a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280ac  test    eax, eax
0x1800280ae  js      loc_18002824D
0x1800280b4  mov     rcx, [rbp+57h+ppv]
0x1800280b8  lea     r8, [rbp+57h+var_80]
0x1800280bc  mov     [rbp+57h+var_80], rsi
0x1800280c0  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800280c7  mov     rax, [rcx]
0x1800280ca  mov     rax, [rax]
0x1800280cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280d2  mov     edi, eax
0x1800280d4  test    eax, eax
0x1800280d6  js      loc_180028238
0x1800280dc  mov     r14, [rbp+57h+var_80]
0x1800280e0  lea     rdx, [rsp+120h+var_D8]
0x1800280e5  mov     r15, [r13+30h]
0x1800280e9  mov     rcx, r14
0x1800280ec  mov     dword ptr [rsp+120h+var_D8], esi
0x1800280f0  mov     rax, [r14]
0x1800280f3  mov     rax, [rax+18h]
0x1800280f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280fc  mov     edi, eax
0x1800280fe  test    eax, eax
0x180028100  js      loc_18002818E
0x180028106  cmp     esi, dword ptr [rsp+120h+var_D8]
0x18002810a  jnb     loc_18002818E
0x180028110  xor     eax, eax
0x180028112  lea     r8, [rbp+57h+var_58]
0x180028116  mov     [rbp+57h+var_48], eax
0x180028119  xorps   xmm0, xmm0
0x18002811c  mov     rax, [r14]
0x18002811f  mov     edx, esi
0x180028121  mov     rcx, r14
0x180028124  movups  [rbp+57h+var_58], xmm0
0x180028128  mov     rax, [rax+20h]
0x18002812c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028131  mov     edi, eax
  ... truncated ...
```
