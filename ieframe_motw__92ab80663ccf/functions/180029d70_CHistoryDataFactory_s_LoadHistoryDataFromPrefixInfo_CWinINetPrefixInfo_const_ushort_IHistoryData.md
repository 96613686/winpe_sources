# CHistoryDataFactory::s_LoadHistoryDataFromPrefixInfo(CWinINetPrefixInfo const *,ushort * *,IHistoryData * *)

- ea: `0x180029d70`
- end: `0x18002a5ef`
- name: `?s_LoadHistoryDataFromPrefixInfo@CHistoryDataFactory@@CAJPEBVCWinINetPrefixInfo@@PEAPEAGPEAPEAUIHistoryData@@@Z`
- size: `2175`
- prototype: `static int(const struct CWinINetPrefixInfo *, unsigned __int16 **, struct IHistoryData **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180479a50`
- `0x180479bc0`

## callees

- `0x180029d70`
- `0x1800bf0d8`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002a0b9`
- `msvcrt!memcpy_s` at `0x18002a0b9`
- `KERNEL32!InitOnceExecuteOnce` at `0x18002a2eb`
- `KERNEL32!InitOnceExecuteOnce` at `0x18002a2eb`
- `KERNEL32!GetProcessHeap` at `0x180029dbf`
- `KERNEL32!GetProcessHeap` at `0x18002a0e9`
- `KERNEL32!GetProcessHeap` at `0x18002a4fa`
- `KERNEL32!GetProcessHeap` at `0x180029dbf`
- `KERNEL32!GetProcessHeap` at `0x18002a0e9`
- `KERNEL32!GetProcessHeap` at `0x18002a4fa`
- `KERNEL32!HeapAlloc` at `0x180029dd9`
- `KERNEL32!HeapAlloc` at `0x180029dd9`
- `KERNEL32!HeapFree` at `0x18002a0fd`
- `KERNEL32!HeapFree` at `0x18002a50e`
- `KERNEL32!HeapFree` at `0x18002a0fd`
- `KERNEL32!HeapFree` at `0x18002a50e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x18002a401`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x18002a401`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18002a2ac`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18002a2ac`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18002a02c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18002a02c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002a0cc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002a3c8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002a4de`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002a4ee`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002a0cc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002a3c8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002a4de`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002a4ee`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180029e5f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180029e7c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18002a45e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180029e5f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180029e7c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18002a45e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x18002a16d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x18002a16d`
- `WININET!GetUrlCacheEntryBinaryBlob` at `0x18002a00b`
- `WININET!GetUrlCacheEntryBinaryBlob` at `0x18002a00b`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180029e42`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002a1b1`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180029e42`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002a1b1`

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
    if ( dword_1806073F0[2 * v11] == 13 )
    {
      if ( LOWORD(dword_1806073F0[2 * v11 + 1]) != 19 )
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
    if ( dword_1806073F0[2 * i] == 6 )
    {
      LOBYTE(v16) = LOWORD(pvar[0]) != LOWORD(dword_1806073F0[2 * i + 1]);
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
      if ( dword_1806073F0[2 * j] == 9 )
      {
        LOBYTE(v18) = v14 != LOWORD(dword_1806073F0[2 * j + 1]);
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
0x180029d70  push    rbp
0x180029d72  push    rbx
0x180029d73  push    rsi
0x180029d74  push    rdi
0x180029d75  push    r13
0x180029d77  push    r14
0x180029d79  push    r15
0x180029d7b  lea     rbp, [rsp-27h]
0x180029d80  sub     rsp, 0F0h
0x180029d87  mov     rax, cs:__security_cookie
0x180029d8e  xor     rax, rsp
0x180029d91  mov     [rbp+57h+var_40], rax
0x180029d95  xor     edi, edi
0x180029d97  mov     [rbp+57h+var_60], r8
0x180029d9b  mov     [rbp+57h+var_D0], rdx
0x180029d9f  mov     r14, rdx
0x180029da2  mov     [rbp+57h+var_C8], rcx
0x180029da6  mov     r15, rcx
0x180029da9  test    rdx, rdx
0x180029dac  jz      short loc_180029DB1
0x180029dae  mov     [rdx], rdi
0x180029db1  mov     [r8], rdi
0x180029db4  mov     rsi, [rcx+10h]
0x180029db8  mov     rbx, [rcx]
0x180029dbb  mov     [rbp+57h+var_A8], rdi
0x180029dbf  call    cs:__imp_GetProcessHeap
0x180029dc6  nop     dword ptr [rax+rax+00h]
0x180029dcb  mov     edx, 8; dwFlags
0x180029dd0  mov     r8d, 50h ; 'P'; dwBytes
0x180029dd6  mov     rcx, rax; hHeap
0x180029dd9  call    cs:__imp_HeapAlloc
0x180029de0  nop     dword ptr [rax+rax+00h]
0x180029de5  mov     r13, rax
0x180029de8  test    rax, rax
0x180029deb  jz      loc_18002A4B4
0x180029df1  lea     rax, ??_7CHistoryData@@6B@; const CHistoryData::`vftable'
0x180029df8  mov     [rsp+120h+arg_18], r12
0x180029e00  mov     [r13+0], rax
0x180029e04  lea     r12, [r13+30h]
0x180029e08  mov     rax, cs:c_li0
0x180029e0f  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180029e16  mov     rdx, r12; ppv
0x180029e19  mov     [r13+0Ch], rax
0x180029e1d  mov     [r13+14h], rax
0x180029e21  mov     [r13+1Ch], rax
0x180029e25  mov     [r13+24h], rax
0x180029e29  mov     dword ptr [r13+8], 1
0x180029e31  mov     [r12], rdi
0x180029e35  mov     [r13+38h], rdi
0x180029e39  mov     [r13+40h], rdi
0x180029e3d  mov     byte ptr [r13+48h], 1
0x180029e42  call    cs:__imp_PSCreateMemoryPropertyStore
0x180029e49  nop     dword ptr [rax+rax+00h]
0x180029e4e  mov     edi, eax
0x180029e50  test    eax, eax
0x180029e52  js      loc_18002A3E0
0x180029e58  lea     rdx, [r13+40h]; ppwsz
0x180029e5c  mov     rcx, rbx; psz
0x180029e5f  call    cs:__imp_SHStrDupW
0x180029e66  nop     dword ptr [rax+rax+00h]
0x180029e6b  mov     edi, eax
0x180029e6d  test    eax, eax
0x180029e6f  js      loc_18002A3E0
0x180029e75  lea     rdx, [r13+38h]; ppwsz
0x180029e79  mov     rcx, rsi; psz
0x180029e7c  call    cs:__imp_SHStrDupW
0x180029e83  nop     dword ptr [rax+rax+00h]
0x180029e88  mov     edi, eax
0x180029e8a  test    eax, eax
0x180029e8c  js      loc_18002A3E0
0x180029e92  xor     eax, eax
0x180029e94  lea     rbx, dword_1806073F0
0x180029e9b  xorps   xmm0, xmm0
0x180029e9e  mov     [rbp+57h+var_90], rax
0x180029ea2  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180029ea6  mov     edx, 13h
0x180029eab  mov     dword ptr [rbp+57h+pvar+8], eax
0x180029eae  mov     word ptr [rbp+57h+pvar], dx
0x180029eb2  cmp     rax, 24h ; '$'
0x180029eb6  jnb     short loc_180029ED6
0x180029eb8  lea     rcx, ds:0[rax*8]
0x180029ec0  cmp     dword ptr [rcx+rbx], 0Dh
0x180029ec4  jz      short loc_180029ECB
0x180029ec6  inc     rax
0x180029ec9  jmp     short loc_180029EB2
0x180029ecb  cmp     dx, [rcx+rbx+4]
0x180029ed0  jnz     loc_18002A3D6
0x180029ed6  movups  xmm0, xmmword ptr cs:FMTID_InternetSite.Data1
0x180029edd  mov     rcx, [r12]
0x180029ee1  lea     r8, [rbp+57h+pvar]
0x180029ee5  mov     [rbp+57h+var_48], 0Dh
0x180029eec  lea     rdx, [rbp+57h+var_58]
0x180029ef0  movups  [rbp+57h+var_58], xmm0
0x180029ef4  mov     rax, [rcx]
0x180029ef7  mov     rax, [rax+30h]
0x180029efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f00  mov     byte ptr [r13+48h], 1
0x180029f05  mov     edi, eax
0x180029f07  test    eax, eax
0x180029f09  js      loc_18002A3E0
0x180029f0f  movzx   r8d, word ptr [rbp+57h+pvar]
0x180029f14  test    r8w, r8w
0x180029f18  jz      loc_18002A5B1
0x180029f1e  xor     r10d, r10d
0x180029f21  mov     eax, r10d
0x180029f24  mov     edx, r10d
0x180029f27  cmp     rax, 24h ; '$'
0x180029f2b  jnb     short loc_180029F4B
0x180029f2d  lea     rcx, ds:0[rax*8]
0x180029f35  cmp     dword ptr [rcx+rbx], 6
0x180029f39  jz      short loc_180029F40
0x180029f3b  inc     rax
0x180029f3e  jmp     short loc_180029F24
0x180029f40  cmp     r8w, [rcx+rbx+4]
0x180029f46  setnz   dl
0x180029f49  inc     edx
0x180029f4b  cmp     edx, 2
0x180029f4e  mov     edi, r10d
0x180029f51  mov     ebx, 8007065Dh
0x180029f56  cmovz   edi, ebx
0x180029f59  jnz     loc_18002A5B6
0x180029f5f  mov     byte ptr [r13+48h], 1
0x180029f64  test    edi, edi
0x180029f66  js      loc_18002A40F
0x180029f6c  test    r8w, r8w
0x180029f70  jz      loc_18002A539
0x180029f76  mov     rax, r10
0x180029f79  lea     r9, dword_1806073F0
0x180029f80  mov     ecx, r10d
0x180029f83  cmp     rax, 24h ; '$'
0x180029f87  jnb     short loc_180029FA8
0x180029f89  lea     rdx, ds:0[rax*8]
0x180029f91  cmp     dword ptr [rdx+r9], 9
0x180029f96  jz      short loc_180029F9D
0x180029f98  inc     rax
0x180029f9b  jmp     short loc_180029F80
0x180029f9d  cmp     r8w, [rdx+r9+4]
0x180029fa3  setnz   cl
0x180029fa6  inc     ecx
0x180029fa8  cmp     ecx, 2
0x180029fab  mov     edi, r10d
0x180029fae  cmovz   edi, ebx
0x180029fb1  jnz     loc_18002A539
0x180029fb7  mov     byte ptr [r13+48h], 1
0x180029fbc  test    edi, edi
0x180029fbe  js      loc_18002A40F
0x180029fc4  lea     rax, [rsp+120h+var_E0]
0x180029fc9  mov     [rbp+57h+var_B8], r10
0x180029fcd  mov     [rsp+120h+pcbBlob], rax; pcbBlob
0x180029fd2  lea     r9, [rbp+57h+pftAccessTime]; pftAccessTime
0x180029fd6  lea     rax, [rbp+57h+var_B8]
0x180029fda  mov     [rsp+120h+var_E0], r10d
0x180029fdf  mov     [rsp+120h+ppbBlob], rax; ppbBlob
0x180029fe4  lea     r8, [rbp+57h+pftExpireTime]; pftExpireTime
0x180029fe8  lea     rax, [rbp+57h+var_88]
0x180029fec  mov     [rbp+57h+dwType], r10d
0x180029ff0  lea     rdx, [rbp+57h+dwType]; dwType
0x180029ff4  mov     [rsp+120h+pftModifiedTime], rax; pftModifiedTime
0x180029ff9  mov     rcx, rsi; pwszUrlName
0x180029ffc  mov     qword ptr [rbp+57h+pftExpireTime.dwLowDateTime], r10
0x18002a000  mov     qword ptr [rbp+57h+pftAccessTime.dwLowDateTime], r10
0x18002a004  mov     rbx, r10
0x18002a007  mov     qword ptr [rbp+57h+var_88.dwLowDateTime], r10
0x18002a00b  call    cs:__imp_GetUrlCacheEntryBinaryBlob
0x18002a012  nop     dword ptr [rax+rax+00h]
0x18002a017  mov     edi, eax
0x18002a019  test    eax, eax
0x18002a01b  jnz     loc_18002A56D
0x18002a021  mov     eax, [rsp+120h+var_E0]
0x18002a025  add     eax, 70h ; 'p'
0x18002a028  mov     ecx, eax; cb
0x18002a02a  mov     esi, eax
0x18002a02c  call    cs:__imp_CoTaskMemAlloc
0x18002a033  nop     dword ptr [rax+rax+00h]
0x18002a038  mov     rdi, rax
0x18002a03b  test    rax, rax
0x18002a03e  jz      loc_18002A581
0x18002a044  xorps   xmm0, xmm0
0x18002a047  movups  xmmword ptr [rax+4], xmm0
0x18002a04b  movups  xmmword ptr [rax+14h], xmm0
0x18002a04f  movups  xmmword ptr [rax+24h], xmm0
0x18002a053  movups  xmmword ptr [rax+34h], xmm0
0x18002a057  movups  xmmword ptr [rax+44h], xmm0
0x18002a05b  movups  xmmword ptr [rax+54h], xmm0
0x18002a05f  movups  xmmword ptr [rax+60h], xmm0
0x18002a063  mov     dword ptr [rax], 70h ; 'p'
0x18002a069  mov     eax, [rbp+57h+dwType]
0x18002a06c  mov     [rdi+18h], eax
0x18002a06f  mov     rax, qword ptr [rbp+57h+var_88.dwLowDateTime]
0x18002a073  mov     [rdi+2Ch], rax
0x18002a077  mov     rax, qword ptr [rbp+57h+pftExpireTime.dwLowDateTime]
0x18002a07b  mov     [rdi+34h], rax
0x18002a07f  mov     rax, qword ptr [rbp+57h+pftAccessTime.dwLowDateTime]
0x18002a083  mov     [rdi+3Ch], rax
0x18002a087  mov     rax, qword ptr [rbp+57h+var_88.dwLowDateTime]
0x18002a08b  mov     [rdi+44h], rax
0x18002a08f  cmp     [rbp+57h+var_B8], 0
0x18002a094  jz      short loc_18002A0C5
0x18002a096  cmp     [rsp+120h+var_E0], 0
0x18002a09b  jbe     short loc_18002A0C5
0x18002a09d  lea     rcx, [rdi+70h]; Destination
0x18002a0a1  mov     [rdi+50h], rcx
0x18002a0a5  lea     rdx, [rsi-70h]; DestinationSize
0x18002a0a9  mov     eax, [rsp+120h+var_E0]
0x18002a0ad  mov     [rdi+58h], eax
0x18002a0b0  mov     r9d, [rsp+120h+var_E0]; SourceSize
0x18002a0b5  mov     r8, [rbp+57h+var_B8]; Source
0x18002a0b9  call    cs:__imp_memcpy_s
0x18002a0c0  nop     dword ptr [rax+rax+00h]
0x18002a0c5  mov     rbx, rdi
0x18002a0c8  xor     edi, edi
0x18002a0ca  xor     ecx, ecx; pv
0x18002a0cc  call    cs:__imp_CoTaskMemFree
0x18002a0d3  nop     dword ptr [rax+rax+00h]
0x18002a0d8  mov     rsi, [rbp+57h+var_B8]
0x18002a0dc  mov     [rbp+57h+var_B8], 0
0x18002a0e4  test    rsi, rsi
0x18002a0e7  jz      short loc_18002A109
0x18002a0e9  call    cs:__imp_GetProcessHeap
0x18002a0f0  nop     dword ptr [rax+rax+00h]
0x18002a0f5  mov     r8, rsi; lpMem
0x18002a0f8  xor     edx, edx; dwFlags
0x18002a0fa  mov     rcx, rax; hHeap
0x18002a0fd  call    cs:__imp_HeapFree
0x18002a104  nop     dword ptr [rax+rax+00h]
0x18002a109  test    edi, edi
0x18002a10b  js      loc_18002A3C5
0x18002a111  mov     rax, [rbx+3Ch]
0x18002a115  xor     esi, esi
0x18002a117  mov     [r13+0Ch], rax
0x18002a11b  mov     edi, esi
0x18002a11d  mov     rax, [rbx+2Ch]
0x18002a121  mov     [r13+14h], rax
0x18002a125  mov     rax, [rbx+34h]
0x18002a129  mov     [r13+1Ch], rax
0x18002a12d  mov     rax, [rbx+44h]
0x18002a131  mov     [r13+24h], rax
0x18002a135  cmp     [rbx+58h], esi
0x18002a138  jbe     loc_18002A3C5
0x18002a13e  mov     rcx, [r12]
0x18002a142  lea     r8, [rbp+57h+var_78]
0x18002a146  mov     [rbp+57h+var_78], rsi
0x18002a14a  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18002a151  mov     rax, [rcx]
0x18002a154  mov     rax, [rax]
0x18002a157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a15c  mov     edi, eax
0x18002a15e  test    eax, eax
0x18002a160  js      loc_18002A3B0
0x18002a166  mov     edx, [rbx+58h]; cbInit
0x18002a169  mov     rcx, [rbx+50h]; pInit
0x18002a16d  call    cs:__imp_SHCreateMemStream
0x18002a174  nop     dword ptr [rax+rax+00h]
0x18002a179  mov     r12, rax
0x18002a17c  test    rax, rax
0x18002a17f  jz      loc_18002A4AA
0x18002a185  mov     rcx, [rbp+57h+var_78]
0x18002a189  mov     rdx, r12
0x18002a18c  mov     rax, [rcx]
0x18002a18f  mov     rax, [rax+28h]
0x18002a193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a198  mov     edi, eax
0x18002a19a  test    eax, eax
0x18002a19c  js      loc_18002A5A3
0x18002a1a2  lea     rdx, [rbp+57h+ppv]; ppv
0x18002a1a6  mov     [rbp+57h+ppv], rsi
0x18002a1aa  lea     rcx, _GUID_00000109_0000_0000_c000_000000000046; riid
0x18002a1b1  call    cs:__imp_PSCreateMemoryPropertyStore
0x18002a1b8  nop     dword ptr [rax+rax+00h]
0x18002a1bd  mov     edi, eax
0x18002a1bf  test    eax, eax
0x18002a1c1  js      loc_18002A387
0x18002a1c7  mov     rcx, [rbp+57h+ppv]
0x18002a1cb  mov     rdx, r12
0x18002a1ce  mov     rax, [rcx]
0x18002a1d1  mov     rax, [rax+28h]
0x18002a1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1da  test    eax, eax
0x18002a1dc  js      loc_18002A387
0x18002a1e2  mov     rcx, [rbp+57h+ppv]
0x18002a1e6  lea     r8, [rbp+57h+var_80]
0x18002a1ea  mov     [rbp+57h+var_80], rsi
0x18002a1ee  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18002a1f5  mov     rax, [rcx]
0x18002a1f8  mov     rax, [rax]
0x18002a1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a200  mov     edi, eax
0x18002a202  test    eax, eax
0x18002a204  js      loc_18002A372
0x18002a20a  mov     r14, [rbp+57h+var_80]
0x18002a20e  lea     rdx, [rsp+120h+var_D8]
0x18002a213  mov     r15, [r13+30h]
0x18002a217  mov     rcx, r14
0x18002a21a  mov     dword ptr [rsp+120h+var_D8], esi
0x18002a21e  mov     rax, [r14]
0x18002a221  mov     rax, [rax+18h]
0x18002a225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a22a  mov     edi, eax
0x18002a22c  test    eax, eax
0x18002a22e  js      loc_18002A2C2
  ... truncated ...
```
