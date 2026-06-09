# CryptDecodeObjectEx

- ea: `0x180008720`
- end: `0x1800091f5`
- name: `CryptDecodeObjectEx`
- size: `2773`
- prototype: `BOOL __stdcall(DWORD dwCertEncodingType, LPCSTR lpszStructType, const BYTE *pbEncoded, DWORD cbEncoded, DWORD dwFlags, PCRYPT_DECODE_PARA pDecodePara, void *pvStructInfo, DWORD *pcbStructInfo)`
- caller_count: `97`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003ab0`
- `0x180003e98`
- `0x180003fb0`
- `0x180005644`
- `0x180006110`
- `0x180006750`
- `0x180006980`
- `0x1800069cc`
- `0x180006a8c`
- `0x180006af4`
- `0x180006b98`
- `0x180007100`
- `0x1800071e0`
- `0x1800079d0`
- `0x180007bf0`
- `0x180007c30`
- `0x1800086a0`
- `0x1800169cc`
- `0x180017588`
- `0x18001d504`
- `0x18001e2fc`
- `0x18001e590`
- `0x18001e764`
- `0x18001e8f4`
- `0x18002a150`
- `0x18002db94`
- `0x18002f250`
- `0x18002f5d8`
- `0x18002f6f0`
- `0x180030170`
- `0x1800303e4`
- `0x180031c00`
- `0x180033068`
- `0x18004fdb0`
- `0x180050424`
- `0x18005f450`
- `0x180065adc`
- `0x180065cc4`
- `0x180065e34`
- `0x180065ef4`
- `0x18006cf20`
- `0x180070880`
- `0x180070f1c`
- `0x180076ea4`
- `0x18007f120`
- `0x18008162c`
- `0x18008986c`
- `0x1800899b8`
- `0x180089c28`
- `0x18008d9e8`

## callees

- `0x180008720`
- `0x180012d00`
- `0x1800258c4`
- `0x180026720`
- `0x180027ba8`
- `0x180027cb0`
- `0x180028834`
- `0x180029494`
- `0x180073ce0`
- `0x18009bea4`
- `0x1800bd1b8`
- `0x1800bf564`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000888e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000888e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008871`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000891c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800089d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008af8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800090ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000915f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800091d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008871`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000891c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800089d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008af8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800090ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000915f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800091d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000890b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800089b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008cdf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008f0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008fde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009038`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009176`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000890b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800089b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008cdf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008f0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008fde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009038`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009176`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000889f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008940`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008c67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008d43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008db2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008ee7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009015`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000906f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800091a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000889f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008940`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008c67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008d43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008db2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008ee7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009015`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000906f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800091a5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800091b7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800091b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ffc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009056`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009190`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ffc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009056`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009190`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180008c03`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180008c4e`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180008e53`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180008ead`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180008fa4`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180008c03`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180008c4e`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180008e53`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180008ead`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180008fa4`

## pseudocode

```c
BOOL __stdcall CryptDecodeObjectEx(
        DWORD dwCertEncodingType,
        LPCSTR lpszStructType,
        const BYTE *pbEncoded,
        DWORD cbEncoded,
        DWORD dwFlags,
        PCRYPT_DECODE_PARA pDecodePara,
        void *pvStructInfo,
        DWORD *pcbStructInfo)
{
  LPCSTR v8; // r13
  const CHAR *v10; // rsi
  LPCSTR *v11; // r15
  DWORD v12; // r14d
  LPCSTR v13; // rbx
  struct _DLL_ELEMENT *i; // rdi
  unsigned __int64 v15; // rax
  LPCSTR v16; // rbx
  const CHAR *v17; // rax
  bool v18; // zf
  FARPROC ProcAddress; // rbx
  int v20; // r14d
  DWORD v21; // ebx
  HMODULE v22; // rsi
  void *v23; // rdx
  void (*v24)(void *, unsigned __int8); // r8
  void *v25; // r9
  void **v26; // rcx
  struct _DLL_ELEMENT *v27; // rax
  __int64 v29; // rsi
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // eax
  const char *v33; // rdi
  const char *v34; // rsi
  struct _FUNC_SET *v35; // rbx
  struct _REG_OID_FUNC_ELEMENT *v36; // rcx
  unsigned __int64 v37; // rax
  DWORD LastError; // ebx
  __int64 v39; // rbx
  const CHAR *v40; // rax
  bool v41; // zf
  void *v42; // r15
  void *v43; // rsi
  LPCSTR v44; // r12
  __int64 v45; // rbx
  __int64 v46; // rcx
  __int64 v47; // rcx
  int v48; // eax
  DWORD v49; // ecx
  DWORD v50; // ebx
  __int64 v51; // rdx
  __int64 v52; // r8
  const CHAR *v53; // rax
  bool v54; // zf
  __int64 v55; // r13
  int v56; // eax
  void (__fastcall *EncodeFreeFunction)(void *); // rax
  __int64 (__fastcall *DecodeAllocFunction)(_QWORD); // rax
  unsigned int v59; // r8d
  DWORD v60; // ebx
  DWORD lpString2; // [rsp+20h] [rbp-88h]
  unsigned int cchCount2; // [rsp+28h] [rbp-80h]
  void *v63; // [rsp+58h] [rbp-50h] BYREF
  void *v64; // [rsp+60h] [rbp-48h] BYREF

  v8 = lpszStructType;
  v10 = lpszStructType;
  v11 = (LPCSTR *)hX509DecodeExFuncSet;
  v12 = (unsigned __int16)dwCertEncodingType;
  if ( !(_WORD)dwCertEncodingType )
    v12 = HIWORD(dwCertEncodingType);
  if ( (unsigned __int64)lpszStructType <= 0xFFFF
    || *lpszStructType != 35
    || (v33 = lpszStructType + 1, v10 = (const CHAR *)o_atol_0(lpszStructType + 1), (unsigned __int64)v10 <= 0xFFFF) )
  {
    if ( !*((_DWORD *)v11 + 12) )
    {
      EnterCriticalSection(&CriticalSection);
      if ( !*((_DWORD *)v11 + 12) )
      {
        CryptEnumOIDFunction(0xFFFFFFFF, v11[1], 0, 0, v11, (PFN_CRYPT_ENUM_OID_FUNC)EnumRegFuncCallback);
        *((_DWORD *)v11 + 12) = 1;
      }
      LeaveCriticalSection(&CriticalSection);
    }
    v13 = v11[7];
    if ( !v13 )
      goto LABEL_6;
    while ( 1 )
    {
      if ( !v13 )
      {
        v56 = 0;
        i = 0;
        ProcAddress = 0;
        goto LABEL_129;
      }
      if ( v12 == *(_DWORD *)v13 )
      {
        v53 = (const CHAR *)*((_QWORD *)v13 + 2);
        if ( (unsigned __int64)v10 > 0xFFFF )
        {
          if ( (unsigned __int64)v53 <= 0xFFFF )
            goto LABEL_112;
          v54 = CompareStringA(0x409u, 1u, v10, -1, v53, -1) == 2;
        }
        else
        {
          v54 = v10 == v53;
        }
        if ( v54 )
        {
          v55 = *((_QWORD *)v13 + 3);
          EnterCriticalSection(&CriticalSection);
          i = *(struct _DLL_ELEMENT **)(v55 + 8);
          ProcAddress = *(FARPROC *)(v55 + 24);
          if ( ProcAddress )
          {
            AddRefDll(*(struct _DLL_ELEMENT **)(v55 + 8));
            goto LABEL_127;
          }
          LeaveCriticalSection(&CriticalSection);
          if ( (unsigned int)LoadDll(i) )
          {
            ProcAddress = GetProcAddress(*((HMODULE *)i + 3), *(LPCSTR *)(v55 + 16));
            if ( ProcAddress )
            {
              EnterCriticalSection(&CriticalSection);
              *(_QWORD *)(v55 + 24) = ProcAddress;
LABEL_127:
              LeaveCriticalSection(&CriticalSection);
              v56 = 1;
LABEL_128:
              v8 = lpszStructType;
LABEL_129:
              v63 = i;
              if ( v56 )
                goto LABEL_21;
LABEL_6:
              if ( (unsigned __int64)v10 > 0xFFFF )
              {
                for ( i = (struct _DLL_ELEMENT *)v11[4]; i; i = (struct _DLL_ELEMENT *)*((_QWORD *)i + 1) )
                {
                  if ( v12 == *((_DWORD *)i + 1) && CompareStringA(0x409u, 1u, v10, -1, *((PCNZCH *)i + 2), -1) == 2 )
                  {
                    ProcAddress = (FARPROC)*((_QWORD *)i + 4);
                    v63 = i;
                    goto LABEL_21;
                  }
                }
              }
              else
              {
                for ( i = (struct _DLL_ELEMENT *)v11[2]; i; i = (struct _DLL_ELEMENT *)*((_QWORD *)i + 1) )
                {
                  if ( v12 == *((_DWORD *)i + 1) )
                  {
                    v15 = *((_QWORD *)i + 2);
                    if ( (unsigned __int64)v10 >= v15 && (unsigned __int64)v10 <= *((_QWORD *)i + 3) )
                    {
                      ProcAddress = *(FARPROC *)(*((_QWORD *)i + 5) + 8LL * (_QWORD)&v10[-v15]);
                      v63 = i;
                      goto LABEL_21;
                    }
                  }
                }
              }
              v16 = v11[8];
              if ( !v16 )
                goto LABEL_49;
              while ( 2 )
              {
                if ( !v16 )
                  goto LABEL_64;
                if ( v12 == *(_DWORD *)v16 )
                {
                  v17 = (const CHAR *)*((_QWORD *)v16 + 2);
                  if ( (unsigned __int64)v10 > 0xFFFF )
                  {
                    if ( (unsigned __int64)v17 > 0xFFFF )
                    {
                      v18 = CompareStringA(0x409u, 1u, v10, -1, v17, -1) == 2;
                      goto LABEL_18;
                    }
                  }
                  else
                  {
                    v18 = v10 == v17;
LABEL_18:
                    if ( v18 )
                    {
                      v29 = *((_QWORD *)v16 + 3);
                      EnterCriticalSection(&CriticalSection);
                      i = *(struct _DLL_ELEMENT **)(v29 + 8);
                      ProcAddress = *(FARPROC *)(v29 + 24);
                      if ( ProcAddress )
                      {
                        ++*((_DWORD *)i + 8);
                        if ( *((_DWORD *)i + 14) )
                        {
                          *((_DWORD *)i + 14) = 0;
                          v30 = *((_QWORD *)i + 8);
                          if ( v30 )
                            *(_QWORD *)(v30 + 72) = *((_QWORD *)i + 9);
                          v31 = *((_QWORD *)i + 9);
                          if ( v31 )
                          {
                            *(_QWORD *)(v31 + 64) = *((_QWORD *)i + 8);
                          }
                          else if ( i == qword_1801583A0 )
                          {
                            qword_1801583A0 = (struct _DLL_ELEMENT *)*((_QWORD *)i + 8);
                          }
                          *((_QWORD *)i + 8) = 0;
                          *((_QWORD *)i + 9) = 0;
                          if ( dword_1801583A8 )
                            --dword_1801583A8;
                        }
                        goto LABEL_47;
                      }
                      LeaveCriticalSection(&CriticalSection);
                      if ( (unsigned int)LoadDll(i) )
                      {
                        ProcAddress = GetProcAddress(*((HMODULE *)i + 3), *(LPCSTR *)(v29 + 16));
                        if ( ProcAddress )
                        {
                          EnterCriticalSection(&CriticalSection);
                          *(_QWORD *)(v29 + 24) = ProcAddress;
LABEL_47:
                          LeaveCriticalSection(&CriticalSection);
                          v32 = 1;
                          goto LABEL_48;
                        }
                        LastError = GetLastError();
                        ReleaseDll(i);
                        SetLastError(LastError);
                      }
LABEL_64:
                      v32 = 0;
                      i = 0;
                      ProcAddress = 0;
LABEL_48:
                      v63 = i;
                      if ( !v32 )
                      {
LABEL_49:
                        SetLastError(2u);
                        v33 = v8 + 1;
                        goto LABEL_50;
                      }
LABEL_21:
                      cchCount2 = (unsigned int)pDecodePara;
                      lpString2 = dwFlags;
                      v20 = ((__int64 (__fastcall *)(_QWORD, LPCSTR, const BYTE *, _QWORD))ProcAddress)(
                              dwCertEncodingType,
                              v8,
                              pbEncoded,
                              cbEncoded);
                      goto LABEL_22;
                    }
                  }
                }
                v16 = (LPCSTR)*((_QWORD *)v16 + 1);
                continue;
              }
            }
            v60 = GetLastError();
            ReleaseDll(i);
            SetLastError(v60);
          }
          v56 = 0;
          i = 0;
          ProcAddress = 0;
          goto LABEL_128;
        }
      }
LABEL_112:
      v13 = (LPCSTR)*((_QWORD *)v13 + 1);
    }
  }
  SetLastError(0x80070057);
LABEL_50:
  v64 = 0;
  v63 = 0;
  if ( (dwFlags & 0x8000) != 0 )
    *(_QWORD *)pvStructInfo = 0;
  v34 = lpszStructType;
  v35 = hX509DecodeFuncSet;
  if ( (unsigned __int64)lpszStructType > 0xFFFF && *lpszStructType == 35 )
  {
    v34 = (const char *)o_atol_0(v33);
    if ( (unsigned __int64)v34 > 0xFFFF )
    {
      v49 = -2147024809;
LABEL_101:
      SetLastError(v49);
      i = 0;
      *pcbStructInfo = 0;
      v20 = 0;
      goto LABEL_22;
    }
  }
  if ( !*((_DWORD *)v35 + 12) )
    LoadRegFunc((LPCSTR *)v35);
  v36 = (struct _REG_OID_FUNC_ELEMENT *)*((_QWORD *)v35 + 7);
  if ( v36 && GetRegOIDFunctionAddress(v36, v12, v34, &v64, &v63) )
  {
    v42 = v64;
    i = (struct _DLL_ELEMENT *)v63;
    goto LABEL_76;
  }
  if ( (unsigned __int64)v34 > 0xFFFF )
  {
    for ( i = (struct _DLL_ELEMENT *)*((_QWORD *)v35 + 4); i; i = (struct _DLL_ELEMENT *)*((_QWORD *)i + 1) )
    {
      if ( v12 == *((_DWORD *)i + 1) && CompareStringA(0x409u, 1u, v34, -1, *((PCNZCH *)i + 2), -1) == 2 )
      {
        v42 = (void *)*((_QWORD *)i + 4);
        v64 = v42;
        v63 = i;
        goto LABEL_76;
      }
    }
  }
  else
  {
    for ( i = (struct _DLL_ELEMENT *)*((_QWORD *)v35 + 2); i; i = (struct _DLL_ELEMENT *)*((_QWORD *)i + 1) )
    {
      if ( v12 == *((_DWORD *)i + 1) )
      {
        v37 = *((_QWORD *)i + 2);
        if ( (unsigned __int64)v34 >= v37 && (unsigned __int64)v34 <= *((_QWORD *)i + 3) )
        {
          v42 = *(void **)(*((_QWORD *)i + 5) + 8LL * (_QWORD)&v34[-v37]);
          v64 = v42;
          v63 = i;
          goto LABEL_76;
        }
      }
    }
  }
  v39 = *((_QWORD *)v35 + 8);
  if ( !v39 )
    goto LABEL_100;
  while ( 1 )
  {
    if ( !v39 )
      goto LABEL_103;
    if ( v12 == *(_DWORD *)v39 )
    {
      v40 = *(const CHAR **)(v39 + 16);
      if ( (unsigned __int64)v34 <= 0xFFFF )
      {
        v41 = v34 == v40;
        goto LABEL_70;
      }
      if ( (unsigned __int64)v40 > 0xFFFF )
        break;
    }
LABEL_71:
    v39 = *(_QWORD *)(v39 + 8);
  }
  v41 = CompareStringA(0x409u, 1u, v34, -1, v40, -1) == 2;
LABEL_70:
  if ( !v41 )
    goto LABEL_71;
  v45 = *(_QWORD *)(v39 + 24);
  EnterCriticalSection(&CriticalSection);
  i = *(struct _DLL_ELEMENT **)(v45 + 8);
  v42 = *(void **)(v45 + 24);
  if ( v42 )
  {
    ++*((_DWORD *)i + 8);
    if ( *((_DWORD *)i + 14) )
    {
      *((_DWORD *)i + 14) = 0;
      v46 = *((_QWORD *)i + 8);
      if ( v46 )
        *(_QWORD *)(v46 + 72) = *((_QWORD *)i + 9);
      v47 = *((_QWORD *)i + 9);
      if ( v47 )
      {
        *(_QWORD *)(v47 + 64) = *((_QWORD *)i + 8);
      }
      else if ( i == qword_1801583A0 )
      {
        qword_1801583A0 = (struct _DLL_ELEMENT *)*((_QWORD *)i + 8);
      }
      *((_QWORD *)i + 8) = 0;
      *((_QWORD *)i + 9) = 0;
      if ( dword_1801583A8 )
        --dword_1801583A8;
    }
    goto LABEL_98;
  }
  LeaveCriticalSection(&CriticalSection);
  if ( (unsigned int)LoadDll(i) )
  {
    v42 = GetProcAddress(*((HMODULE *)i + 3), *(LPCSTR *)(v45 + 16));
    if ( v42 )
    {
      EnterCriticalSection(&CriticalSection);
      *(_QWORD *)(v45 + 24) = v42;
LABEL_98:
      LeaveCriticalSection(&CriticalSection);
      v48 = 1;
      goto LABEL_99;
    }
    v50 = GetLastError();
    ReleaseDll(i);
    SetLastError(v50);
  }
LABEL_103:
  v48 = 0;
  i = 0;
  v42 = 0;
LABEL_99:
  v64 = v42;
  v63 = i;
  if ( !v48 )
  {
LABEL_100:
    v49 = 2;
    goto LABEL_101;
  }
LABEL_76:
  if ( (dwFlags & 0x8000) != 0 )
  {
    *pcbStructInfo = 0;
    cchCount2 = 0;
    lpString2 = dwFlags & 0xFFFF7FFF;
    v44 = lpszStructType;
    v20 = ((__int64 (__fastcall *)(_QWORD, LPCSTR, const BYTE *, _QWORD))v42)(
            dwCertEncodingType,
            lpszStructType,
            pbEncoded,
            cbEncoded);
    if ( v20 && *pcbStructInfo )
    {
      DecodeAllocFunction = (__int64 (__fastcall *)(_QWORD))PkiGetDecodeAllocFunction(pDecodePara);
      v43 = (void *)DecodeAllocFunction(v59);
      v64 = v43;
      if ( v43 )
        goto LABEL_78;
      SetLastError(0x8007000E);
      *pcbStructInfo = 0;
      v20 = 0;
    }
  }
  else
  {
    v43 = pvStructInfo;
    v64 = pvStructInfo;
    v44 = lpszStructType;
LABEL_78:
    cchCount2 = (unsigned int)v43;
    lpString2 = dwFlags & 0xFFFF7FFF;
    v20 = ((__int64 (__fastcall *)(_QWORD, LPCSTR, const BYTE *, _QWORD))v42)(
            dwCertEncodingType,
            v44,
            pbEncoded,
            cbEncoded);
    if ( (dwFlags & 0x8000) != 0 )
    {
      if ( v20 )
      {
        *(_QWORD *)pvStructInfo = v43;
      }
      else
      {
        EncodeFreeFunction = (void (__fastcall *)(void *))PkiGetEncodeFreeFunction(pDecodePara);
        EncodeFreeFunction(v43);
      }
    }
  }
LABEL_22:
  if ( i && *(_DWORD *)i == 3 )
  {
    v21 = GetLastError();
    v22 = 0;
    EnterCriticalSection(&CriticalSection);
    v26 = (void **)*((unsigned int *)i + 8);
    if ( (unsigned int)v26 > 1 )
    {
      *((_DWORD *)i + 8) = (_DWORD)v26 - 1;
    }
    else
    {
      if ( !dword_1801583AC )
      {
        LeaveCriticalSection(&CriticalSection);
        v22 = (HMODULE)DuplicateLibrary(qword_1801583C0, v51, v52);
        EnterCriticalSection(&CriticalSection);
      }
      v18 = (*((_DWORD *)i + 8))-- == 1;
      if ( v18 && *((_DWORD *)i + 9) && !*((_DWORD *)i + 14) )
      {
        if ( dword_1801583AC )
          goto LABEL_31;
        if ( (unsigned int)ILS_RegisterWaitForSingleObject(v26, v23, v24, v25, lpString2, cchCount2) )
        {
          hLibModule = v22;
          v22 = 0;
          dword_1801583AC = 1;
LABEL_31:
          *((_DWORD *)i + 14) = 2;
          v27 = qword_1801583A0;
          if ( qword_1801583A0 )
          {
            *((_QWORD *)qword_1801583A0 + 9) = i;
            *((_QWORD *)i + 8) = v27;
          }
          qword_1801583A0 = i;
          ++dword_1801583A8;
        }
        else
        {
          qword_1801583B0 = 0;
        }
      }
    }
    LeaveCriticalSection(&CriticalSection);
    if ( v22 )
      FreeLibrary(v22);
    SetLastError(v21);
  }
  return v20;
}

```

## disassembly

```asm
0x180008720  mov     [rsp+arg_18], r9d
0x180008725  mov     [rsp+arg_10], r8
0x18000872a  mov     [rsp+lpString1], rdx
0x18000872f  mov     [rsp+arg_0], ecx
0x180008733  push    rbx
0x180008734  push    rsi
0x180008735  push    rdi
0x180008736  push    r12
0x180008738  push    r13
0x18000873a  push    r14
0x18000873c  push    r15
0x18000873e  sub     rsp, 70h
0x180008742  mov     r13, rdx
0x180008745  mov     r12d, ecx
0x180008748  mov     rsi, rdx
0x18000874b  mov     r15, cs:?hX509DecodeExFuncSet@@3PEAXEA; void * hX509DecodeExFuncSet
0x180008752  movzx   r14d, cx
0x180008756  mov     eax, ecx
0x180008758  shr     eax, 10h
0x18000875b  test    r14d, r14d
0x18000875e  cmovz   r14d, eax
0x180008762  cmp     rdx, 0FFFFh
0x180008769  ja      loc_180008ACE
0x18000876f  cmp     dword ptr [r15+30h], 0
0x180008774  jz      loc_180008D3C
0x18000877a  mov     rbx, [r15+38h]
0x18000877e  test    rbx, rbx
0x180008781  jnz     loc_180008DC0
0x180008787  cmp     rsi, 0FFFFh
0x18000878e  ja      loc_180008BCB
0x180008794  mov     rdi, [r15+10h]
0x180008798  test    rdi, rdi
0x18000879b  jz      short loc_1800087B8
0x18000879d  cmp     r14d, [rdi+4]
0x1800087a1  jnz     short loc_1800087B2
0x1800087a3  mov     rax, [rdi+10h]
0x1800087a7  cmp     rsi, rax
0x1800087aa  jb      short loc_1800087B2
0x1800087ac  cmp     rsi, [rdi+18h]
0x1800087b0  jbe     short loc_1800087F3
0x1800087b2  mov     rdi, [rdi+8]
0x1800087b6  jmp     short loc_180008798
0x1800087b8  mov     rbx, [r15+40h]
0x1800087bc  test    rbx, rbx
0x1800087bf  jz      loc_1800089D0
0x1800087c5  test    rbx, rbx
0x1800087c8  jz      loc_180008A85
0x1800087ce  cmp     r14d, [rbx]
0x1800087d1  jnz     short loc_1800087ED
0x1800087d3  mov     rax, [rbx+10h]
0x1800087d7  cmp     rsi, 0FFFFh
0x1800087de  ja      loc_180008C22
0x1800087e4  cmp     rsi, rax
0x1800087e7  jz      loc_180008935
0x1800087ed  mov     rbx, [rbx+8]
0x1800087f1  jmp     short loc_1800087C5
0x1800087f3  sub     rsi, rax
0x1800087f6  mov     rax, [rdi+28h]
0x1800087fa  mov     rbx, [rax+rsi*8]
0x1800087fe  mov     [rsp+0A8h+var_50], rdi
0x180008803  mov     rax, [rsp+0A8h+pcbStructInfo]
0x18000880b  mov     [rsp+0A8h+var_70], rax
0x180008810  mov     rax, [rsp+0A8h+pvStructInfo]
0x180008818  mov     [rsp+0A8h+var_78], rax
0x18000881d  mov     rax, [rsp+0A8h+pDecodePara]
0x180008825  mov     qword ptr [rsp+0A8h+cchCount2], rax
0x18000882a  mov     eax, [rsp+0A8h+dwFlags]
0x180008831  mov     dword ptr [rsp+0A8h+lpString2], eax
0x180008835  mov     r9d, [rsp+0A8h+arg_18]
0x18000883d  mov     r8, [rsp+0A8h+arg_10]
0x180008845  mov     rdx, r13
0x180008848  mov     ecx, r12d
0x18000884b  mov     rax, rbx
0x18000884e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008853  mov     r14d, eax
0x180008856  mov     [rsp+0A8h+var_58], eax
0x18000885a  jmp     short loc_18000887C
0x18000885c  xor     r14d, r14d
0x18000885f  mov     [rsp+0A8h+var_58], r14d
0x180008864  mov     rcx, [rsp+0A8h+pcbStructInfo]
0x18000886c  mov     [rcx], r14d
0x18000886f  mov     ecx, eax; dwErrCode
0x180008871  call    cs:__imp_SetLastError
0x180008877  mov     rdi, [rsp+0A8h+var_50]
0x18000887c  test    rdi, rdi
0x18000887f  jz      loc_180008922
0x180008885  cmp     dword ptr [rdi], 3
0x180008888  jnz     loc_180008922
0x18000888e  call    cs:__imp_GetLastError
0x180008894  mov     ebx, eax
0x180008896  xor     esi, esi
0x180008898  lea     rcx, CriticalSection; lpCriticalSection
0x18000889f  call    cs:__imp_EnterCriticalSection
0x1800088a5  mov     ecx, [rdi+20h]; void **
0x1800088a8  cmp     ecx, 1
0x1800088ab  ja      loc_180008E64
0x1800088b1  cmp     cs:dword_1801583AC, esi
0x1800088b7  jz      loc_180008D8F
0x1800088bd  add     dword ptr [rdi+20h], 0FFFFFFFFh
0x1800088c1  jnz     short loc_180008904
0x1800088c3  cmp     dword ptr [rdi+24h], 0
0x1800088c7  jz      short loc_180008904
0x1800088c9  cmp     dword ptr [rdi+38h], 0
0x1800088cd  jnz     short loc_180008904
0x1800088cf  cmp     cs:dword_1801583AC, 0
0x1800088d6  jz      loc_180008FB2
0x1800088dc  mov     dword ptr [rdi+38h], 2
0x1800088e3  mov     rax, cs:qword_1801583A0
0x1800088ea  test    rax, rax
0x1800088ed  jz      short loc_1800088F7
0x1800088ef  mov     [rax+48h], rdi
0x1800088f3  mov     [rdi+40h], rax
0x1800088f7  mov     cs:qword_1801583A0, rdi
0x1800088fe  inc     cs:dword_1801583A8
0x180008904  lea     rcx, CriticalSection; lpCriticalSection
0x18000890b  call    cs:__imp_LeaveCriticalSection
0x180008911  test    rsi, rsi
0x180008914  jnz     loc_1800091B4
0x18000891a  mov     ecx, ebx; dwErrCode
0x18000891c  call    cs:__imp_SetLastError
0x180008922  mov     eax, r14d
0x180008925  add     rsp, 70h
0x180008929  pop     r15
0x18000892b  pop     r14
0x18000892d  pop     r13
0x18000892f  pop     r12
0x180008931  pop     rdi
0x180008932  pop     rsi
0x180008933  pop     rbx
0x180008934  retn
0x180008935  mov     rsi, [rbx+18h]
0x180008939  lea     rcx, CriticalSection; lpCriticalSection
0x180008940  call    cs:__imp_EnterCriticalSection
0x180008946  mov     rdi, [rsi+8]
0x18000894a  mov     rbx, [rsi+18h]
0x18000894e  test    rbx, rbx
0x180008951  jz      loc_180008FD7
0x180008957  inc     dword ptr [rdi+20h]
0x18000895a  cmp     dword ptr [rdi+38h], 0
0x18000895e  jz      short loc_1800089B1
0x180008960  xor     edx, edx
0x180008962  mov     [rdi+38h], edx
0x180008965  mov     rcx, [rdi+40h]
0x180008969  test    rcx, rcx
0x18000896c  jz      short loc_180008976
0x18000896e  mov     rax, [rdi+48h]
0x180008972  mov     [rcx+48h], rax
0x180008976  mov     rcx, [rdi+48h]
0x18000897a  test    rcx, rcx
0x18000897d  jnz     loc_180008F6B
0x180008983  cmp     rdi, cs:qword_1801583A0
0x18000898a  jnz     short loc_180008997
0x18000898c  mov     rax, [rdi+40h]
0x180008990  mov     cs:qword_1801583A0, rax
0x180008997  mov     [rdi+40h], rdx
0x18000899b  mov     [rdi+48h], rdx
0x18000899f  mov     eax, cs:dword_1801583A8
0x1800089a5  test    eax, eax
0x1800089a7  jz      short loc_1800089B1
0x1800089a9  dec     eax
0x1800089ab  mov     cs:dword_1801583A8, eax
0x1800089b1  lea     rcx, CriticalSection; lpCriticalSection
0x1800089b8  call    cs:__imp_LeaveCriticalSection
0x1800089be  mov     eax, 1
0x1800089c3  mov     [rsp+0A8h+var_50], rdi
0x1800089c8  test    eax, eax
0x1800089ca  jnz     loc_180008803
0x1800089d0  mov     ecx, 2; dwErrCode
0x1800089d5  call    cs:__imp_SetLastError
0x1800089db  lea     rdi, [r13+1]
0x1800089df  xor     eax, eax
0x1800089e1  mov     [rsp+0A8h+var_48], rax
0x1800089e6  mov     [rsp+0A8h+var_50], rax
0x1800089eb  mov     r13d, [rsp+0A8h+dwFlags]
0x1800089f3  mov     r12d, r13d
0x1800089f6  and     r12d, 8000h
0x1800089fd  jnz     loc_180008EBB
0x180008a03  mov     rax, [rsp+0A8h+lpString1]
0x180008a0b  mov     rsi, rax
0x180008a0e  mov     rbx, cs:?hX509DecodeFuncSet@@3PEAXEA; void * hX509DecodeFuncSet
0x180008a15  cmp     rax, 0FFFFh
0x180008a1b  ja      loc_180008DEE
0x180008a21  cmp     dword ptr [rbx+30h], 0
0x180008a25  jz      loc_180008ECF
0x180008a2b  mov     rcx, [rbx+38h]; struct _REG_OID_FUNC_ELEMENT *
0x180008a2f  test    rcx, rcx
0x180008a32  jnz     loc_180008F3A
0x180008a38  cmp     rsi, 0FFFFh
0x180008a3f  ja      loc_180008E19
0x180008a45  mov     rdi, [rbx+10h]
0x180008a49  test    rdi, rdi
0x180008a4c  jz      short loc_180008A90
0x180008a4e  cmp     r14d, [rdi+4]
0x180008a52  jnz     short loc_180008A67
0x180008a54  mov     rax, [rdi+10h]
0x180008a58  cmp     rsi, rax
0x180008a5b  jb      short loc_180008A67
0x180008a5d  cmp     rsi, [rdi+18h]
0x180008a61  jbe     loc_180008B03
0x180008a67  mov     rdi, [rdi+8]
0x180008a6b  jmp     short loc_180008A49
0x180008a6d  call    cs:__imp_GetLastError
0x180008a73  mov     ebx, eax
0x180008a75  mov     rcx, rdi; struct _DLL_ELEMENT *
0x180008a78  call    ?ReleaseDll@@YAXPEAU_DLL_ELEMENT@@@Z; ReleaseDll(_DLL_ELEMENT *)
0x180008a7d  mov     ecx, ebx; dwErrCode
0x180008a7f  call    cs:__imp_SetLastError
0x180008a85  xor     eax, eax
0x180008a87  xor     edi, edi
0x180008a89  xor     ebx, ebx
0x180008a8b  jmp     loc_1800089C3
0x180008a90  mov     rbx, [rbx+40h]
0x180008a94  test    rbx, rbx
0x180008a97  jz      loc_180008CFC
0x180008a9d  nop     dword ptr [rax]
0x180008aa0  test    rbx, rbx
0x180008aa3  jz      loc_180008D33
0x180008aa9  cmp     r14d, [rbx]
0x180008aac  jnz     short loc_180008AC8
0x180008aae  mov     rax, [rbx+10h]
0x180008ab2  cmp     rsi, 0FFFFh
0x180008ab9  ja      loc_180008E81
0x180008abf  cmp     rsi, rax
0x180008ac2  jz      loc_180008C5C
0x180008ac8  mov     rbx, [rbx+8]
0x180008acc  jmp     short loc_180008AA0
0x180008ace  cmp     byte ptr [rdx], 23h ; '#'
0x180008ad1  jnz     loc_18000876F
0x180008ad7  lea     rdi, [rdx+1]
0x180008adb  mov     rcx, rdi; String
0x180008ade  call    _o_atol_0
0x180008ae3  movsxd  rsi, eax
0x180008ae6  cmp     rsi, 0FFFFh
0x180008aed  jbe     loc_18000876F
0x180008af3  mov     ecx, 80070057h; dwErrCode
0x180008af8  call    cs:__imp_SetLastError
0x180008afe  jmp     loc_1800089DF
0x180008b03  sub     rsi, rax
0x180008b06  mov     rax, [rdi+28h]
0x180008b0a  mov     r15, [rax+rsi*8]
0x180008b0e  mov     [rsp+0A8h+var_48], r15
0x180008b13  mov     [rsp+0A8h+var_50], rdi
0x180008b18  mov     [rsp+0A8h+var_54], r12d
0x180008b1d  mov     rbx, [rsp+0A8h+pcbStructInfo]
0x180008b25  test    r12d, r12d
0x180008b28  jnz     loc_180009098
0x180008b2e  mov     rsi, [rsp+0A8h+pvStructInfo]
0x180008b36  mov     [rsp+0A8h+var_48], rsi
0x180008b3b  mov     r12, [rsp+0A8h+lpString1]
0x180008b43  btr     r13d, 0Fh
0x180008b48  mov     [rsp+0A8h+var_78], rbx
0x180008b4d  mov     qword ptr [rsp+0A8h+cchCount2], rsi
0x180008b52  mov     dword ptr [rsp+0A8h+lpString2], r13d
0x180008b57  mov     r9d, [rsp+0A8h+arg_18]
0x180008b5f  mov     r8, [rsp+0A8h+arg_10]
0x180008b67  mov     rdx, r12
0x180008b6a  mov     ecx, [rsp+0A8h+arg_0]
0x180008b71  mov     rax, r15
0x180008b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b79  mov     r14d, eax
0x180008b7c  mov     [rsp+0A8h+var_58], eax
0x180008b80  jmp     short loc_180008BA7
0x180008b82  xor     r14d, r14d
0x180008b85  mov     [rsp+0A8h+var_58], r14d
0x180008b8a  mov     rcx, [rsp+0A8h+pcbStructInfo]
0x180008b92  mov     [rcx], r14d
0x180008b95  mov     ecx, eax; dwErrCode
0x180008b97  call    cs:__imp_SetLastError
0x180008b9d  mov     rdi, [rsp+0A8h+var_50]
0x180008ba2  mov     rsi, [rsp+0A8h+var_48]
0x180008ba7  cmp     [rsp+0A8h+var_54], 0
0x180008bac  jz      loc_18000887C
0x180008bb2  test    r14d, r14d
0x180008bb5  jz      loc_18000907E
0x180008bbb  mov     rax, [rsp+0A8h+pvStructInfo]
0x180008bc3  mov     [rax], rsi
0x180008bc6  jmp     loc_18000887C
0x180008bcb  mov     rdi, [r15+20h]
0x180008bcf  nop
0x180008bd0  test    rdi, rdi
0x180008bd3  jz      loc_1800087B8
0x180008bd9  cmp     r14d, [rdi+4]
0x180008bdd  jnz     short loc_180008C0E
0x180008bdf  mov     [rsp+0A8h+cchCount2], 0FFFFFFFFh; cchCount2
0x180008be7  mov     rax, [rdi+10h]
0x180008beb  mov     [rsp+0A8h+lpString2], rax; lpString2
0x180008bf0  mov     r9d, 0FFFFFFFFh; cchCount1
0x180008bf6  mov     r8, rsi; lpString1
0x180008bf9  mov     edx, 1; dwCmpFlags
0x180008bfe  mov     ecx, 409h; Locale
0x180008c03  call    cs:__imp_CompareStringA
0x180008c09  cmp     eax, 2
0x180008c0c  jz      short loc_180008C14
0x180008c0e  mov     rdi, [rdi+8]
0x180008c12  jmp     short loc_180008BD0
0x180008c14  mov     rbx, [rdi+20h]
0x180008c18  mov     [rsp+0A8h+var_50], rdi
0x180008c1d  jmp     loc_180008803
0x180008c22  cmp     rax, 0FFFFh
0x180008c28  jbe     loc_1800087ED
  ... truncated ...
```
