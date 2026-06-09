# EnumUrlCacheEntryCallback(_CRYPTNET_URL_CACHE_ENTRY const *,ulong,void *,void *)

- ea: `0x1800028f0`
- end: `0x180003391`
- name: `?EnumUrlCacheEntryCallback@@YAHPEBU_CRYPTNET_URL_CACHE_ENTRY@@KPEAX1@Z`
- size: `2721`
- prototype: `__int64 __fastcall(const struct _CRYPTNET_URL_CACHE_ENTRY *, __int64, UCHAR *, FILETIME *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1800028f0`
- `0x1800033a0`
- `0x1800033e0`
- `0x180003a44`
- `0x180004ac0`
- `0x1800068b0`
- `0x180009b20`
- `0x18000e2f0`
- `0x18000fb38`
- `0x18000fb7c`
- `0x18000fbc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000327e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000327e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800029c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800032a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003323`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003330`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003349`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800029c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800032a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003323`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003330`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002b22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002df3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002b22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002df3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002c59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002c59`
- `CRYPT32!I_CryptCreateLruEntry` at `0x180002ca9`
- `CRYPT32!I_CryptCreateLruEntry` at `0x180002e9e`
- `CRYPT32!I_CryptCreateLruEntry` at `0x1800032fe`
- `CRYPT32!I_CryptCreateLruEntry` at `0x180002ca9`
- `CRYPT32!I_CryptCreateLruEntry` at `0x180002e9e`
- `CRYPT32!I_CryptCreateLruEntry` at `0x1800032fe`
- `CRYPT32!I_CryptInsertLruEntry` at `0x180002cbd`
- `CRYPT32!I_CryptInsertLruEntry` at `0x180002eb2`
- `CRYPT32!I_CryptInsertLruEntry` at `0x18000330e`
- `CRYPT32!I_CryptInsertLruEntry` at `0x180002cbd`
- `CRYPT32!I_CryptInsertLruEntry` at `0x180002eb2`
- `CRYPT32!I_CryptInsertLruEntry` at `0x18000330e`
- `CRYPT32!I_CryptFindLruEntry` at `0x180002a14`
- `CRYPT32!I_CryptFindLruEntry` at `0x180002cde`
- `CRYPT32!I_CryptFindLruEntry` at `0x180002d3d`
- `CRYPT32!I_CryptFindLruEntry` at `0x180002a14`
- `CRYPT32!I_CryptFindLruEntry` at `0x180002cde`
- `CRYPT32!I_CryptFindLruEntry` at `0x180002d3d`
- `CRYPT32!I_CryptGetLruEntryData` at `0x180002a25`
- `CRYPT32!I_CryptGetLruEntryData` at `0x180002cf3`
- `CRYPT32!I_CryptGetLruEntryData` at `0x180002d52`
- `CRYPT32!I_CryptGetLruEntryData` at `0x180002a25`
- `CRYPT32!I_CryptGetLruEntryData` at `0x180002cf3`
- `CRYPT32!I_CryptGetLruEntryData` at `0x180002d52`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x180002a74`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x180002d09`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x180002d68`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x180002a74`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x180002d09`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x180002d68`
- `CRYPT32!I_CryptEnumMatchingLruEntries` at `0x180002f4c`
- `CRYPT32!I_CryptEnumMatchingLruEntries` at `0x180002f7b`
- `CRYPT32!I_CryptEnumMatchingLruEntries` at `0x180002f4c`
- `CRYPT32!I_CryptEnumMatchingLruEntries` at `0x180002f7b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002b10`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002de0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002b10`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002de0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002a40`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002a63`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002e0c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002e36`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002eca`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003082`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003126`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003209`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002a40`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002a63`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002e0c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002e36`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002eca`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003082`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003126`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003209`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003271`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003296`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003271`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003296`
- `bcrypt!BCryptCreateHash` at `0x180002960`
- `bcrypt!BCryptCreateHash` at `0x180002960`
- `bcrypt!BCryptHashData` at `0x180002988`
- `bcrypt!BCryptHashData` at `0x1800029b6`
- `bcrypt!BCryptHashData` at `0x180002988`
- `bcrypt!BCryptHashData` at `0x1800029b6`
- `bcrypt!BCryptDestroyHash` at `0x1800029dd`
- `bcrypt!BCryptDestroyHash` at `0x1800029dd`
- `bcrypt!BCryptFinishHash` at `0x180002f08`
- `bcrypt!BCryptFinishHash` at `0x180002f08`

## pseudocode

```c
__int64 __fastcall EnumUrlCacheEntryCallback(
        const struct _CRYPTNET_URL_CACHE_ENTRY *a1,
        __int64 a2,
        UCHAR *a3,
        FILETIME *a4)
{
  FILETIME v7; // r13
  int v8; // edi
  NTSTATUS v9; // eax
  unsigned int v10; // r15d
  __int64 v11; // r12
  UCHAR *v12; // rdx
  __int64 v13; // r8
  DWORD LastError; // ebx
  __int64 v15; // rcx
  __int64 LruEntry; // rax
  __int64 v17; // rdi
  __int64 LruEntryData; // rax
  __int64 v19; // r14
  _DWORD *v21; // rax
  const WCHAR *v22; // rbx
  __int64 j; // rdi
  HANDLE FileW; // rax
  unsigned int v25; // r8d
  int v26; // r13d
  __int64 v27; // rdx
  __int64 v28; // r10
  __m128i v29; // xmm2
  __m128i v30; // xmm1
  __m128i v31; // xmm0
  __int64 v32; // rax
  __m128i v33; // xmm1
  __m128i v34; // xmm1
  __int64 v35; // rdi
  __int64 v36; // rbx
  __int64 v37; // r8
  char *v38; // rax
  char *v39; // rbx
  FILETIME v40; // r12
  char *v41; // r9
  _OWORD *v42; // rax
  __int128 v43; // xmm1
  __int64 v44; // rcx
  __int64 k; // rax
  __int64 v46; // rbx
  __int64 v47; // rdi
  unsigned __int64 i; // rax
  unsigned __int64 v49; // rbx
  __int64 v50; // rsi
  const FILETIME *v51; // rbx
  unsigned int dwHighDateTime; // r12d
  const WCHAR *v53; // rdi
  HANDLE v54; // rax
  const FILETIME *v55; // rdi
  const FILETIME *v56; // rbx
  __int64 v57; // rax
  _QWORD *v58; // rbx
  __int128 v59; // xmm1
  __int64 v60; // rdx
  bool v61; // zf
  __int64 Job; // rax
  __int64 v63; // rbx
  FILETIME v64; // rcx
  __int64 v65; // rax
  unsigned __int64 v66; // rdx
  __int64 v67; // rax
  __int64 v68; // rsi
  _QWORD *v69; // rax
  FILETIME *v70; // rdi
  __int64 v71; // rcx
  __int64 v72; // r8
  __int64 *v73; // rax
  DWORD v74; // eax
  DWORD v75; // eax
  __int64 v76; // rax
  __int128 v77; // xmm1
  FILETIME v78; // rcx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-59h] BYREF
  __int128 v80; // [rsp+48h] [rbp-51h] BYREF
  FILETIME v81; // [rsp+58h] [rbp-41h]
  FILETIME FileTime1; // [rsp+60h] [rbp-39h] BYREF
  __int64 v83; // [rsp+68h] [rbp-31h]
  BCRYPT_HASH_HANDLE v84[3]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v85[2]; // [rsp+88h] [rbp-11h] BYREF
  UCHAR pbOutput[16]; // [rsp+98h] [rbp-1h] BYREF
  __int128 v87; // [rsp+A8h] [rbp+Fh]

  if ( !a4 || !a3 )
    return 0;
  v7 = *a4;
  v8 = 0;
  v81 = *a4;
  phHash = 0;
  v9 = BCryptCreateHash(hAlgSha256, &phHash, 0, 0, 0, 0, 0);
  v10 = 1;
  v11 = -1;
  if ( v9 )
    goto LABEL_9;
  v9 = BCryptHashData(phHash, a3 + 20, 8u, 0);
  if ( v9 )
    goto LABEL_9;
  v12 = a3 + 44;
  if ( a3 == (UCHAR *)-44LL )
  {
    LODWORD(v13) = 0;
  }
  else
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)&v12[2 * v13] );
  }
  v9 = BCryptHashData(phHash, v12, 2 * v13, 0);
  if ( v9 || (v9 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0)) != 0 )
  {
LABEL_9:
    SetLastError(v9);
    LastError = GetLastError();
  }
  else
  {
    LastError = 0;
    v8 = 1;
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( LastError )
    SetLastError(LastError);
  if ( !v8 )
    return 0;
  if ( !a1 )
  {
    v15 = *(_QWORD *)(*(_QWORD *)&v7 + 104LL);
    *((_QWORD *)&v80 + 1) = pbOutput;
    *(_QWORD *)&v80 = 32;
    LruEntry = I_CryptFindLruEntry(v15, &v80);
    v17 = LruEntry;
    if ( LruEntry )
    {
      LruEntryData = I_CryptGetLruEntryData(LruEntry);
      v19 = LruEntryData;
      if ( *(_DWORD *)(LruEntryData + 60) || *(_DWORD *)(LruEntryData + 64) )
      {
        if ( CompareFileTime((const FILETIME *)(LruEntryData + 60), a4 + 1) > 0 )
        {
          if ( (*(_DWORD *)(v19 + 56) = 1, !a4[5].dwLowDateTime) && !a4[5].dwHighDateTime
            || (v10 = 0, CompareFileTime((const FILETIME *)(v19 + 60), a4 + 5) < 0) )
          {
            v10 = 0;
            a4[5] = *(FILETIME *)(v19 + 60);
          }
        }
      }
      else
      {
        FileTime1 = (FILETIME)16LL;
        v83 = LruEntryData + 68;
        for ( i = I_CryptFindLruEntry(hPreFetchJobLruCache, &FileTime1); ; i = I_CryptEnumMatchingLruEntries(v49) )
        {
          v49 = i;
          if ( !i )
            break;
          v50 = I_CryptGetLruEntryData(i);
          if ( *(_QWORD *)(v50 + 48) == v7 )
          {
            I_CryptReleaseLruEntry(v49);
            *(_DWORD *)(v50 + 56) = 1;
            goto LABEL_53;
          }
        }
        while ( i < 0x10 )
        {
          if ( *(_BYTE *)(v19 + i + 68) )
            goto LABEL_21;
          ++i;
        }
LABEL_53:
        *(_DWORD *)(v19 + 56) = 1;
        v10 = 0;
      }
LABEL_21:
      I_CryptReleaseLruEntry(v17);
    }
    return v10;
  }
  v21 = (_DWORD *)*((_QWORD *)a1 + 7);
  if ( v21 && *v21 >= 0x28u && v21[1] && !v21[2] && (v21[6] || v21[7]) )
  {
    v22 = (const WCHAR *)*((_QWORD *)a1 + 5);
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      FileW = CreateFileW(v22, 0xC0000000, 0, 0, 3u, 0x80u, 0);
      if ( FileW != (HANDLE)-1LL )
        break;
      v74 = GetLastError();
      if ( v74 != 32 || (unsigned int)j >= 6 )
      {
        SetLastError(v74);
        v78 = v81;
        goto LABEL_144;
      }
      Sleep(*((_DWORD *)qword_18001B4D0 + j));
    }
    CloseHandle(FileW);
    v25 = *((_DWORD *)a1 + 4);
    v26 = 0;
    if ( v25 )
    {
      v27 = 0;
      if ( v25 < 8 )
        goto LABEL_147;
      v28 = *((_QWORD *)a1 + 3);
      v29 = 0;
      v30 = 0;
      do
      {
        v31 = _mm_loadu_si128((const __m128i *)(v28 + 4 * v27));
        v32 = (unsigned int)(v27 + 4);
        v27 = (unsigned int)(v27 + 8);
        v29 = _mm_add_epi32(v29, v31);
        v30 = _mm_add_epi32(v30, _mm_loadu_si128((const __m128i *)(v28 + 4 * v32)));
      }
      while ( (unsigned int)v27 < (v25 & 0xFFFFFFF8) );
      v33 = _mm_add_epi32(v30, v29);
      v34 = _mm_add_epi32(v33, _mm_srli_si128(v33, 8));
      v26 = _mm_cvtsi128_si32(_mm_add_epi32(v34, _mm_srli_si128(v34, 4)));
      if ( (unsigned int)v27 < v25 )
      {
LABEL_147:
        do
        {
          v26 += *(_DWORD *)(*((_QWORD *)a1 + 3) + 4 * v27);
          v27 = (unsigned int)(v27 + 1);
        }
        while ( (unsigned int)v27 < v25 );
      }
    }
    v35 = *((_QWORD *)a1 + 9);
    v36 = *((_QWORD *)a1 + 4);
    *(_QWORD *)&v80 = *((_QWORD *)a1 + 10);
    FileTime1 = (FILETIME)*((_QWORD *)a1 + 7);
    LODWORD(phHash) = v26;
    memset(v84, 0, sizeof(v84));
    CngRsa32Compat_MD5Init(v84);
    if ( v36 )
    {
      v37 = -1;
      do
        ++v37;
      while ( *(_WORD *)(v36 + 2 * v37) );
    }
    else
    {
      LODWORD(v37) = 0;
    }
    CngRsa32Compat_MD5Update(v84, v36, (unsigned int)(2 * v37));
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))CngRsa32Compat_MD5Update)(v84, FileTime1, 40);
    CngRsa32Compat_MD5Update(v84, &phHash, 4);
    if ( (_QWORD)v80 )
    {
      v72 = -1;
      do
        ++v72;
      while ( *(_WORD *)(v80 + 2 * v72) );
      CngRsa32Compat_MD5Update(v84, v80, (unsigned int)(2 * v72));
    }
    if ( v35 )
    {
      CngRsa32Compat_MD5Update(v84, v35 + 8, 8);
      CngRsa32Compat_MD5Update(v84, v35 + 16, 4);
      v60 = *(_QWORD *)(v35 + 24);
      if ( v60 )
      {
        do
          v61 = *(_WORD *)(v60 + 2 * v11++ + 2) == 0;
        while ( !v61 );
        CngRsa32Compat_MD5Update(v84, v60, (unsigned int)(2 * v11));
      }
    }
    CngRsa32Compat_MD5Final(v84);
    *(_OWORD *)v85 = *(_OWORD *)&v84[1];
    v80 = 0;
    v38 = (char *)LocalAlloc(0x40u, 0x58u);
    v39 = v38;
    if ( v38 )
    {
      v40 = v81;
      v41 = v38 + 16;
      v42 = v38 + 24;
      *v42 = *(_OWORD *)pbOutput;
      v43 = v87;
      *((_DWORD *)v39 + 14) = 1;
      v42[1] = v43;
      *(_OWORD *)(v39 + 68) = *(_OWORD *)v85;
      v44 = *(_QWORD *)(*(_QWORD *)&v40 + 104LL);
      *((_QWORD *)&v80 + 1) = v42;
      LODWORD(v80) = 32;
      if ( !(unsigned int)I_CryptCreateLruEntry(v44, &v80, v39, v41) )
        goto LABEL_139;
      I_CryptInsertLruEntry(*((_QWORD *)v39 + 2), 0);
      *((_QWORD *)&v80 + 1) = v85;
      *(_QWORD *)&v80 = 16;
      for ( k = I_CryptFindLruEntry(hPreFetchJobLruCache, &v80); ; k = I_CryptEnumMatchingLruEntries(v46) )
      {
        v46 = k;
        if ( !k )
          break;
        v47 = I_CryptGetLruEntryData(k);
        if ( *(_QWORD *)(v47 + 48) == v40 )
        {
          I_CryptReleaseLruEntry(v46);
          *(_DWORD *)(v47 + 56) = 1;
          return v10;
        }
      }
      Job = CreatePreFetchJob(
              *((void **)a1 + 4),
              *((struct _CRYPTNET_URL_CACHE_PRE_FETCH_INFO **)a1 + 7),
              *((_QWORD *)a1 + 9),
              (FILETIME *)a1 + 1,
              (__int64)v85,
              a4 + 1);
      v63 = Job;
      if ( Job )
      {
        v64 = v81;
        *(_DWORD *)(Job + 56) = 1;
        v65 = *(_QWORD *)(*(_QWORD *)&v64 + 40LL);
        if ( v65 )
        {
          *(_QWORD *)(v63 + 32) = v65;
          *(_QWORD *)(v65 + 40) = v63;
        }
        else
        {
          *(_QWORD *)(v63 + 32) = 0;
        }
        *(_QWORD *)(v63 + 40) = 0;
        *(_QWORD *)(*(_QWORD *)&v64 + 40LL) = v63;
        v61 = *(_DWORD *)(v63 + 208) == 0;
        *(FILETIME *)(v63 + 48) = v64;
        if ( v61 )
        {
          if ( !*(_DWORD *)(v63 + 176) )
            goto LABEL_107;
          if ( *(_DWORD *)(v63 + 140) == 3 )
          {
            if ( CompareFileTime((const FILETIME *)(v63 + 160), (const FILETIME *)(v63 + 152)) <= 0 )
              LODWORD(v66) = 0;
            else
              v66 = (*(_QWORD *)(v63 + 160) - *(_QWORD *)(v63 + 152)) / 0x989680uLL;
            if ( (unsigned int)v66 < dword_180020284 )
            {
              ++dword_1800203F0;
              *(_DWORD *)(v63 + 176) = 0;
            }
          }
          if ( !*(_DWORD *)(v63 + 176) )
          {
LABEL_107:
            *(_DWORD *)(v63 + 120) = 50;
            *(FILETIME *)(v63 + 232) = a4[1];
            UpdatePreFetchJob((struct _CUCS_PRE_FETCH_JOB_ENTRY *)v63);
            return v10;
          }
          if ( *(_DWORD *)(v63 + 140) == 3 )
            ++dword_1800203DC;
          else
            ++dword_1800203F4;
        }
        v61 = *(_DWORD *)(v63 + 176) == 0;
        *(_DWORD *)(v63 + 116) = 1;
        if ( v61 )
        {
          v71 = *(unsigned int *)(v63 + 212);
          *(_DWORD *)(v63 + 212) = v71 + 1;
          v67 = 8 * v71 + 192;
        }
        else
        {
          v67 = 184;
        }
        v68 = *(_QWORD *)(v63 + 48);
        v69 = (_QWORD *)(v63 + v67);
        if ( v69 )
          *(_QWORD *)(v63 + 16) = *v69;
        else
          *(_QWORD *)(v63 + 16) = 0;
        v70 = *(FILETIME **)(v68 + 48);
        if ( v70 )
        {
          while ( CompareFileTime((const FILETIME *)(v63 + 16), v70 + 2) >= 0 )
          {
            if ( !*(_QWORD *)v70 )
            {
              *(_QWORD *)(v63 + 8) = v70;
              *v70 = (FILETIME)v63;
              return v10;
            }
            v70 = (FILETIME *)*v70;
          }
          *(_QWORD *)v63 = v70;
          *(FILETIME *)(v63 + 8) = v70[1];
          v73 = (__int64 *)v70[1];
          if ( v73 )
            *v73 = v63;
          else
            *(_QWORD *)(v68 + 48) = v63;
          v70[1] = (FILETIME)v63;
        }
        else
        {
          *(_QWORD *)(v68 + 48) = v63;
        }
      }
      return v10;
    }
    SetLastError(0x8007000E);
    goto LABEL_139;
  }
  v51 = (const FILETIME *)*((_QWORD *)a1 + 8);
  dwHighDateTime = dword_180020274;
  if ( v51 )
  {
    if ( v51->dwLowDateTime < 0x10 )
    {
      v51 = 0;
    }
    else if ( v51->dwHighDateTime )
    {
      dwHighDateTime = v51->dwHighDateTime;
    }
  }
  if ( dwHighDateTime != -1 )
  {
    v53 = (const WCHAR *)*((_QWORD *)a1 + 5);
    FileTime1 = 0;
    for ( LODWORD(phHash) = 0; ; LODWORD(phHash) = (_DWORD)phHash + 1 )
    {
      v54 = CreateFileW(v53, 0xC0010000, 4u, 0, 3u, 0x80u, 0);
      if ( v54 != (HANDLE)-1LL )
      {
        CloseHandle(v54);
        v55 = (const FILETIME *)((char *)a1 + 8);
        if ( v51 )
        {
          v56 = v51 + 1;
          if ( CompareFileTime(v56, (const FILETIME *)a1 + 1) <= 0 )
          {
            if ( CompareFileTime((const FILETIME *)a1 + 1, a4 + 1) > 0 )
              v55 = v56;
          }
          else
          {
            v55 = v56;
          }
        }
        FileTime1 = (FILETIME)(*(_QWORD *)v55 + 10000000LL * dwHighDateTime);
        if ( CompareFileTime(&FileTime1, a4 + 1) <= 0 )
        {
          AddFlushCacheEntry(a1, (struct _CUCS_ENUM_URL_CACHE_ARG *)a4);
        }
        else
        {
          *(_OWORD *)v85 = 0;
          v57 = PkiZeroAlloc(0x58u);
          v58 = (_QWORD *)v57;
          if ( v57
            && (*(_OWORD *)(v57 + 24) = *(_OWORD *)pbOutput,
                v59 = v87,
                *(_DWORD *)(v57 + 56) = 1,
                *(_OWORD *)(v57 + 40) = v59,
                *(FILETIME *)(v57 + 60) = FileTime1,
                v85[1] = v57 + 24,
                LODWORD(v85[0]) = 32,
                (unsigned int)I_CryptCreateLruEntry(*(_QWORD *)(*(_QWORD *)&v81 + 104LL), v85, v57, v57 + 16)) )
          {
            I_CryptInsertLruEntry(v58[2], 0);
          }
          else
          {
            PkiFree(v58);
          }
          if ( !a4[5].dwLowDateTime && !a4[5].dwHighDateTime || CompareFileTime(&FileTime1, a4 + 5) < 0 )
            a4[5] = FileTime1;
        }
        return v10;
      }
      v75 = GetLastError();
      if ( v75 != 32 || (unsigned int)phHash >= 6 )
        break;
      Sleep(*((_DWORD *)qword_18001B4D0 + (unsigned int)phHash));
    }
    SetLastError(v75);
    *(_OWORD *)v85 = 0;
    v76 = PkiZeroAlloc(0x58u);
    v39 = (char *)v76;
    if ( v76 )
    {
      *(_OWORD *)(v76 + 24) = *(_OWORD *)pbOutput;
      v77 = v87;
      *(_DWORD *)(v76 + 56) = 1;
      *(_OWORD *)(v76 + 40) = v77;
      v85[1] = v76 + 24;
      LODWORD(v85[0]) = 32;
      if ( (unsigned int)I_CryptCreateLruEntry(*(_QWORD *)(*(_QWORD *)&v81 + 104LL), v85, v76, v76 + 16) )
      {
        I_CryptInsertLruEntry(*((_QWORD *)v39 + 2), 0);
        return v10;
      }
    }
LABEL_139:
    PkiFree(v39);
    return v10;
  }
  v78 = v7;
LABEL_144:
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))CreateAndAddCacheFile)(v78, pbOutput, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x1800028f0  mov     [rsp-8+arg_8], rbx
0x1800028f5  push    rbp
0x1800028f6  push    rsi
0x1800028f7  push    rdi
0x1800028f8  push    r12
0x1800028fa  push    r13
0x1800028fc  push    r14
0x1800028fe  push    r15
0x180002900  lea     rbp, [rsp-27h]
0x180002905  sub     rsp, 0C0h
0x18000290c  mov     rax, cs:__security_cookie
0x180002913  xor     rax, rsp
0x180002916  mov     [rbp+57h+var_38], rax
0x18000291a  mov     rsi, r9
0x18000291d  mov     rbx, r8
0x180002920  mov     r14, rcx
0x180002923  test    r9, r9
0x180002926  jz      loc_180002AA4
0x18000292c  test    rbx, rbx
0x18000292f  jz      loc_180002AA4
0x180002935  mov     r13, [r9]
0x180002938  lea     rdx, [rbp+57h+phHash]; phHash
0x18000293c  mov     rcx, cs:?hAlgSha256@@3PEAXEA; hAlgorithm
0x180002943  xor     edi, edi
0x180002945  mov     [rsp+0F0h+dwFlags], edi; dwFlags
0x180002949  xor     r9d, r9d; cbHashObject
0x18000294c  mov     [rsp+0F0h+cbSecret], edi; cbSecret
0x180002950  xor     r8d, r8d; pbHashObject
0x180002953  mov     [rsp+0F0h+pbSecret], rdi; pbSecret
0x180002958  mov     [rbp+57h+var_98], r13
0x18000295c  mov     [rbp+57h+phHash], rdi
0x180002960  call    cs:__imp_BCryptCreateHash
0x180002966  mov     r15d, 1
0x18000296c  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180002973  test    eax, eax
0x180002975  jnz     short loc_1800029C4
0x180002977  mov     rcx, [rbp+57h+phHash]; hHash
0x18000297b  lea     rdx, [rbx+14h]; pbInput
0x18000297f  xor     r9d, r9d; dwFlags
0x180002982  mov     r8d, 8; cbInput
0x180002988  call    cs:__imp_BCryptHashData
0x18000298e  test    eax, eax
0x180002990  jnz     short loc_1800029C4
0x180002992  lea     rdx, [rbx+2Ch]; pbInput
0x180002996  test    rdx, rdx
0x180002999  jz      loc_180003319
0x18000299f  mov     r8, r12
0x1800029a2  inc     r8
0x1800029a5  cmp     [rdx+r8*2], di
0x1800029aa  jnz     short loc_1800029A2
0x1800029ac  mov     rcx, [rbp+57h+phHash]; hHash
0x1800029b0  add     r8d, r8d; cbInput
0x1800029b3  xor     r9d, r9d; dwFlags
0x1800029b6  call    cs:__imp_BCryptHashData
0x1800029bc  test    eax, eax
0x1800029be  jz      loc_180002EF7
0x1800029c4  mov     ecx, eax; dwErrCode
0x1800029c6  call    cs:__imp_SetLastError
0x1800029cc  call    cs:__imp_GetLastError
0x1800029d2  mov     ebx, eax
0x1800029d4  mov     rcx, [rbp+57h+phHash]; hHash
0x1800029d8  test    rcx, rcx
0x1800029db  jz      short loc_1800029E3
0x1800029dd  call    cs:__imp_BCryptDestroyHash
0x1800029e3  test    ebx, ebx
0x1800029e5  jnz     loc_180003321
0x1800029eb  test    edi, edi
0x1800029ed  jz      loc_180002AA4
0x1800029f3  test    r14, r14
0x1800029f6  jnz     loc_180002AA8
0x1800029fc  mov     rcx, [r13+68h]
0x180002a00  lea     rax, [rbp+57h+pbOutput]
0x180002a04  lea     rdx, [rbp+57h+var_A8]
0x180002a08  mov     qword ptr [rbp+57h+var_A8+8], rax
0x180002a0c  mov     qword ptr [rbp+57h+var_A8], 20h ; ' '
0x180002a14  call    cs:__imp_I_CryptFindLruEntry
0x180002a1a  mov     rdi, rax
0x180002a1d  test    rax, rax
0x180002a20  jz      short loc_180002A7A
0x180002a22  mov     rcx, rax
0x180002a25  call    cs:__imp_I_CryptGetLruEntryData
0x180002a2b  mov     r14, rax
0x180002a2e  cmp     dword ptr [rax+3Ch], 0
0x180002a32  jz      loc_180002D18
0x180002a38  lea     rdx, [rsi+8]; lpFileTime2
0x180002a3c  lea     rcx, [rax+3Ch]; lpFileTime1
0x180002a40  call    cs:__imp_CompareFileTime
0x180002a46  test    eax, eax
0x180002a48  jle     short loc_180002A71
0x180002a4a  mov     [r14+38h], r15d
0x180002a4e  cmp     dword ptr [rsi+28h], 0
0x180002a52  jz      loc_180002EDD
0x180002a58  lea     rdx, [rsi+28h]; lpFileTime2
0x180002a5c  xor     r15d, r15d
0x180002a5f  lea     rcx, [r14+3Ch]; lpFileTime1
0x180002a63  call    cs:__imp_CompareFileTime
0x180002a69  test    eax, eax
0x180002a6b  js      loc_180002EE7
0x180002a71  mov     rcx, rdi
0x180002a74  call    cs:__imp_I_CryptReleaseLruEntry
0x180002a7a  mov     eax, r15d
0x180002a7d  mov     rcx, [rbp+57h+var_38]
0x180002a81  xor     rcx, rsp; StackCookie
0x180002a84  call    __security_check_cookie
0x180002a89  mov     rbx, [rsp+0F0h+arg_8]
0x180002a91  add     rsp, 0C0h
0x180002a98  pop     r15
0x180002a9a  pop     r14
0x180002a9c  pop     r13
0x180002a9e  pop     r12
0x180002aa0  pop     rdi
0x180002aa1  pop     rsi
0x180002aa2  pop     rbp
0x180002aa3  retn
0x180002aa4  xor     eax, eax
0x180002aa6  jmp     short loc_180002A7D
0x180002aa8  mov     rax, [r14+38h]
0x180002aac  test    rax, rax
0x180002aaf  jz      loc_180002D7E
0x180002ab5  cmp     dword ptr [rax], 28h ; '('
0x180002ab8  jb      loc_180002D7E
0x180002abe  cmp     dword ptr [rax+4], 0
0x180002ac2  jz      loc_180002D7E
0x180002ac8  cmp     dword ptr [rax+8], 0
0x180002acc  jnz     loc_180002D7E
0x180002ad2  cmp     dword ptr [rax+18h], 0
0x180002ad6  jz      loc_18000314C
0x180002adc  mov     rbx, [r14+28h]
0x180002ae0  lea     r13, qword_18001B4D0
0x180002ae7  xor     edi, edi
0x180002ae9  mov     qword ptr [rsp+0F0h+dwFlags], 0; hTemplateFile
0x180002af2  xor     r9d, r9d; lpSecurityAttributes
0x180002af5  mov     [rsp+0F0h+cbSecret], 80h; dwFlagsAndAttributes
0x180002afd  xor     r8d, r8d; dwShareMode
0x180002b00  mov     edx, 0C0000000h; dwDesiredAccess
0x180002b05  mov     dword ptr [rsp+0F0h+pbSecret], 3; dwCreationDisposition
0x180002b0d  mov     rcx, rbx; lpFileName
0x180002b10  call    cs:__imp_CreateFileW
0x180002b16  cmp     rax, r12
0x180002b19  jz      loc_180003254
0x180002b1f  mov     rcx, rax; hObject
0x180002b22  call    cs:__imp_CloseHandle
0x180002b28  mov     r8d, [r14+10h]
0x180002b2c  xor     r13d, r13d
0x180002b2f  test    r8d, r8d
0x180002b32  jz      short loc_180002BA3
0x180002b34  xor     edx, edx
0x180002b36  cmp     r8d, 8
0x180002b3a  jb      short loc_180002B94
0x180002b3c  mov     r10, [r14+18h]
0x180002b40  mov     r9d, r8d
0x180002b43  and     r9d, 0FFFFFFF8h
0x180002b47  xorps   xmm2, xmm2
0x180002b4a  xorps   xmm1, xmm1
0x180002b4d  movdqu  xmm0, xmmword ptr [r10+rdx*4]
0x180002b53  lea     eax, [rdx+4]
0x180002b56  add     edx, 8
0x180002b59  paddd   xmm2, xmm0
0x180002b5d  movdqu  xmm0, xmmword ptr [r10+rax*4]
0x180002b63  paddd   xmm1, xmm0
0x180002b67  cmp     edx, r9d
0x180002b6a  jb      short loc_180002B4D
0x180002b6c  paddd   xmm1, xmm2
0x180002b70  movdqa  xmm0, xmm1
0x180002b74  psrldq  xmm0, 8
0x180002b79  paddd   xmm1, xmm0
0x180002b7d  movdqa  xmm0, xmm1
0x180002b81  psrldq  xmm0, 4
0x180002b86  paddd   xmm1, xmm0
0x180002b8a  movd    r13d, xmm1
0x180002b8f  cmp     edx, r8d
0x180002b92  jnb     short loc_180002BA3
0x180002b94  mov     rcx, [r14+18h]
0x180002b98  add     r13d, [rcx+rdx*4]
0x180002b9c  inc     edx
0x180002b9e  cmp     edx, r8d
0x180002ba1  jb      short loc_180002B98
0x180002ba3  mov     rax, [r14+50h]
0x180002ba7  lea     rcx, [rbp+57h+var_80]; phHash
0x180002bab  mov     rdi, [r14+48h]
0x180002baf  xorps   xmm0, xmm0
0x180002bb2  mov     rbx, [r14+20h]
0x180002bb6  mov     qword ptr [rbp+57h+var_A8], rax
0x180002bba  mov     rax, [r14+38h]
0x180002bbe  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], rax
0x180002bc2  xor     eax, eax
0x180002bc4  mov     [rbp+57h+var_70], rax
0x180002bc8  mov     dword ptr [rbp+57h+phHash], r13d
0x180002bcc  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180002bd0  call    CngRsa32Compat_MD5Init
0x180002bd5  test    rbx, rbx
0x180002bd8  jz      loc_18000333C
0x180002bde  mov     r8, r12
0x180002be1  inc     r8
0x180002be4  cmp     word ptr [rbx+r8*2], 0
0x180002bea  jnz     short loc_180002BE1
0x180002bec  add     r8d, r8d
0x180002bef  lea     rcx, [rbp+57h+var_80]
0x180002bf3  mov     rdx, rbx
0x180002bf6  call    CngRsa32Compat_MD5Update
0x180002bfb  mov     rdx, qword ptr [rbp+57h+FileTime1.dwLowDateTime]
0x180002bff  lea     rcx, [rbp+57h+var_80]
0x180002c03  mov     r8d, 28h ; '('
0x180002c09  call    CngRsa32Compat_MD5Update
0x180002c0e  mov     r8d, 4
0x180002c14  lea     rdx, [rbp+57h+phHash]
0x180002c18  lea     rcx, [rbp+57h+var_80]
0x180002c1c  call    CngRsa32Compat_MD5Update
0x180002c21  mov     rax, qword ptr [rbp+57h+var_A8]
0x180002c25  test    rax, rax
0x180002c28  jnz     loc_1800031C3
0x180002c2e  test    rdi, rdi
0x180002c31  jnz     loc_180002F86
0x180002c37  lea     rcx, [rbp+57h+var_80]
0x180002c3b  call    CngRsa32Compat_MD5Final
0x180002c40  movups  xmm0, xmmword ptr [rbp+57h+var_80+8]
0x180002c44  mov     edx, 58h ; 'X'; uBytes
0x180002c49  mov     ecx, 40h ; '@'; uFlags
0x180002c4e  xorps   xmm1, xmm1
0x180002c51  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x180002c55  movups  [rbp+57h+var_A8], xmm1
0x180002c59  call    cs:__imp_LocalAlloc
0x180002c5f  mov     rbx, rax
0x180002c62  test    rax, rax
0x180002c65  jz      loc_180003344
0x180002c6b  movups  xmm0, xmmword ptr [rbp+57h+pbOutput]
0x180002c6f  mov     r12, [rbp+57h+var_98]
0x180002c73  lea     r9, [rbx+10h]
0x180002c77  add     rax, 18h
0x180002c7b  lea     rdx, [rbp+57h+var_A8]
0x180002c7f  mov     r8, rbx
0x180002c82  movups  xmmword ptr [rax], xmm0
0x180002c85  movups  xmm1, [rbp+57h+var_48]
0x180002c89  mov     [rbx+38h], r15d
0x180002c8d  movups  xmmword ptr [rax+10h], xmm1
0x180002c91  movups  xmm0, xmmword ptr [rbp+57h+var_68]
0x180002c95  movups  xmmword ptr [rbx+44h], xmm0
0x180002c99  mov     rcx, [r12+68h]
0x180002c9e  mov     qword ptr [rbp+57h+var_A8+8], rax
0x180002ca2  mov     dword ptr [rbp+57h+var_A8], 20h ; ' '
0x180002ca9  call    cs:__imp_I_CryptCreateLruEntry
0x180002caf  test    eax, eax
0x180002cb1  jz      loc_18000334F
0x180002cb7  mov     rcx, [rbx+10h]
0x180002cbb  xor     edx, edx
0x180002cbd  call    cs:__imp_I_CryptInsertLruEntry
0x180002cc3  mov     rcx, cs:?hPreFetchJobLruCache@@3PEAXEA; void * hPreFetchJobLruCache
0x180002cca  lea     rax, [rbp+57h+var_68]
0x180002cce  lea     rdx, [rbp+57h+var_A8]
0x180002cd2  mov     qword ptr [rbp+57h+var_A8+8], rax
0x180002cd6  mov     qword ptr [rbp+57h+var_A8], 10h
0x180002cde  call    cs:__imp_I_CryptFindLruEntry
0x180002ce4  mov     rbx, rax
0x180002ce7  test    rax, rax
0x180002cea  jz      loc_180002FE0
0x180002cf0  mov     rcx, rax
0x180002cf3  call    cs:__imp_I_CryptGetLruEntryData
0x180002cf9  mov     rdi, rax
0x180002cfc  mov     rcx, rbx
0x180002cff  cmp     [rax+30h], r12
0x180002d03  jnz     loc_180002F4C
0x180002d09  call    cs:__imp_I_CryptReleaseLruEntry
0x180002d0f  mov     [rdi+38h], r15d
0x180002d13  jmp     loc_180002A7A
0x180002d18  cmp     dword ptr [rax+40h], 0
0x180002d1c  jnz     loc_180002A38
0x180002d22  lea     rcx, [rax+44h]
0x180002d26  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], 10h
0x180002d2e  mov     [rbp+57h+var_88], rcx
0x180002d32  lea     rdx, [rbp+57h+FileTime1]
0x180002d36  mov     rcx, cs:?hPreFetchJobLruCache@@3PEAXEA; void * hPreFetchJobLruCache
0x180002d3d  call    cs:__imp_I_CryptFindLruEntry
0x180002d43  mov     rbx, rax
0x180002d46  test    rax, rax
0x180002d49  jz      loc_180002F60
0x180002d4f  mov     rcx, rax
0x180002d52  call    cs:__imp_I_CryptGetLruEntryData
0x180002d58  mov     rsi, rax
0x180002d5b  mov     rcx, rbx
0x180002d5e  cmp     [rax+30h], r13
0x180002d62  jnz     loc_180002F7B
0x180002d68  call    cs:__imp_I_CryptReleaseLruEntry
0x180002d6e  mov     [rsi+38h], r15d
0x180002d72  mov     [r14+38h], r15d
0x180002d76  xor     r15d, r15d
0x180002d79  jmp     loc_180002A71
0x180002d7e  mov     rbx, [r14+40h]
0x180002d82  mov     r12d, cs:dword_180020274
0x180002d89  test    rbx, rbx
0x180002d8c  jnz     loc_180002F30
0x180002d92  cmp     r12d, 0FFFFFFFFh
0x180002d96  jz      loc_180003377
0x180002d9c  mov     rdi, [r14+28h]
0x180002da0  lea     r13, qword_18001B4D0
0x180002da7  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], 0
0x180002daf  mov     dword ptr [rbp+57h+phHash], 0
0x180002db6  mov     qword ptr [rsp+0F0h+dwFlags], 0; hTemplateFile
0x180002dbf  xor     r9d, r9d; lpSecurityAttributes
0x180002dc2  mov     [rsp+0F0h+cbSecret], 80h; dwFlagsAndAttributes
0x180002dca  mov     edx, 0C0010000h; dwDesiredAccess
  ... truncated ...
```
