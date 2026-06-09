# CertGetPublicKeyLength

- ea: `0x180026d50`
- end: `0x180027451`
- name: `CertGetPublicKeyLength`
- size: `1793`
- prototype: `DWORD __stdcall(DWORD dwCertEncodingType, PCERT_PUBLIC_KEY_INFO pPublicKey)`
- caller_count: `5`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a3c0`
- `0x18000ac20`
- `0x180060108`
- `0x180086f54`
- `0x1800870c8`

## callees

- `0x180006980`
- `0x180009da0`
- `0x180012d00`
- `0x18002561c`
- `0x1800258c4`
- `0x180026d50`
- `0x180027460`
- `0x180027ba8`
- `0x180027cb0`
- `0x1800286e0`
- `0x180028d60`
- `0x180029494`
- `0x180030e60`
- `0x1800b1e60`
- `0x1800b7278`
- `0x1800bf564`
- `0x1800ca464`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002700c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800272de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002740b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002742c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116bb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002700c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800272de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002740b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002742c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116bb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026f1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002701e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027073`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800270c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002713a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027161`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027190`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800271be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002741d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180116c39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026f1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002701e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027073`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800270c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002713a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027161`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027190`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800271be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002741d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180116c39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026f07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027115`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002737c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800273c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026f07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027115`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002737c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800273c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026ee1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800270ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800273b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800273fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026ee1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800270ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800273b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800273fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002706b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002706b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002739a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800273e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002739a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800273e7`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800271fd`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18002723f`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18002727c`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800272b6`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800271fd`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18002723f`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18002727c`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800272b6`
- `CRYPTSP!CryptDestroyKey` at `0x1800270b8`
- `CRYPTSP!CryptDestroyKey` at `0x1800270b8`
- `CRYPTSP!CryptGetKeyParam` at `0x1800270a1`
- `CRYPTSP!CryptGetKeyParam` at `0x180116b9b`
- `CRYPTSP!CryptGetKeyParam` at `0x1800270a1`
- `CRYPTSP!CryptGetKeyParam` at `0x180116b9b`
- `CRYPTSP!CryptExportKey` at `0x180116bdb`
- `CRYPTSP!CryptExportKey` at `0x180116c15`
- `CRYPTSP!CryptExportKey` at `0x180116bdb`
- `CRYPTSP!CryptExportKey` at `0x180116c15`
- `CRYPTSP!CryptImportKey` at `0x180027049`
- `CRYPTSP!CryptImportKey` at `0x180027049`

## pseudocode

```c
DWORD __stdcall CertGetPublicKeyLength(DWORD dwCertEncodingType, PCERT_PUBLIC_KEY_INFO pPublicKey)
{
  LPSTR pszObjId; // rdx
  int v5; // r15d
  PCCRYPT_OID_INFO OIDInfo; // rax
  unsigned int dwValue; // ecx
  LPSTR v8; // rbx
  struct _FUNC_SET *v9; // rsi
  DWORD v10; // r12d
  struct _REG_OID_FUNC_ELEMENT *v11; // rcx
  void *i; // rdi
  void *ProcAddress; // rbx
  __int64 v14; // rdi
  const CHAR *v15; // rax
  bool v16; // zf
  __int64 v17; // rsi
  int v18; // eax
  LPSTR v19; // rbx
  struct _FUNC_SET *v20; // rsi
  struct _REG_OID_FUNC_ELEMENT *v21; // rcx
  void *j; // rdi
  __int64 v23; // rdi
  const CHAR *v24; // rax
  bool v25; // zf
  void *v26; // rbx
  int v27; // esi
  DWORD v28; // ebx
  BYTE *v29; // rdi
  DWORD v30; // ebx
  DWORD v31; // edi
  __int64 v33; // rsi
  int v34; // eax
  DWORD LastError; // ebx
  DWORD v36; // ebx
  PCCRYPT_OID_INFO v37; // rax
  int v38; // eax
  __int64 v39; // rbx
  HCRYPTKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  BYTE *pbData; // [rsp+48h] [rbp-28h] BYREF
  void *v42; // [rsp+50h] [rbp-20h] BYREF
  void *v43; // [rsp+58h] [rbp-18h] BYREF
  HCRYPTPROV hProv; // [rsp+60h] [rbp-10h]
  DWORD v45; // [rsp+B8h] [rbp+48h] BYREF
  DWORD dwDataLen; // [rsp+C0h] [rbp+50h] BYREF
  DWORD pdwDataLen; // [rsp+C8h] [rbp+58h] BYREF

  pszObjId = pPublicKey->Algorithm.pszObjId;
  v45 = 0;
  hKey = 0;
  v5 = 1;
  pdwDataLen = 0;
  OIDInfo = CryptFindOIDInfo(1u, pszObjId, 0x40000003u);
  if ( OIDInfo )
  {
    dwValue = OIDInfo->dwValue;
    if ( dwValue >= 0xFFFFFFFD )
      return I_CryptCNGGetPublicKeyLength(dwCertEncodingType, pPublicKey);
    if ( dwValue - 43521 <= 1 )
      return GetDHPublicKeyLength(dwCertEncodingType, pPublicKey);
    if ( dwValue == 8704 )
      return GetDSSPublicKeyLength(dwCertEncodingType, pPublicKey);
  }
  hProv = I_CryptGetDefaultCryptProv();
  if ( !hProv )
    goto LABEL_110;
  v8 = pPublicKey->Algorithm.pszObjId;
  v9 = pvArg;
  v42 = 0;
  v43 = 0;
  pbData = 0;
  dwDataLen = 0;
  v10 = (unsigned __int16)dwCertEncodingType;
  if ( !(_WORD)dwCertEncodingType )
    v10 = HIWORD(dwCertEncodingType);
  if ( (unsigned __int64)v8 > 0xFFFF && *v8 == 35 )
  {
    v8 = (LPSTR)o_atol_0(v8 + 1);
    if ( (unsigned __int64)v8 > 0xFFFF )
    {
      SetLastError(0x80070057);
      goto LABEL_33;
    }
  }
  if ( !*((_DWORD *)v9 + 12) )
    LoadRegFunc((LPCSTR *)v9);
  v11 = (struct _REG_OID_FUNC_ELEMENT *)*((_QWORD *)v9 + 7);
  if ( v11 && GetRegOIDFunctionAddress(v11, v10, v8, &v42, &v43) )
  {
    ProcAddress = v42;
    i = v43;
    goto LABEL_19;
  }
  if ( (unsigned __int64)v8 <= 0xFFFF )
  {
    for ( i = (void *)*((_QWORD *)v9 + 2); ; i = (void *)*((_QWORD *)i + 1) )
    {
      if ( !i )
        goto LABEL_20;
      if ( v10 == *((_DWORD *)i + 1)
        && (unsigned __int64)v8 >= *((_QWORD *)i + 2)
        && (unsigned __int64)v8 <= *((_QWORD *)i + 3) )
      {
        break;
      }
    }
    ProcAddress = *(void **)(*((_QWORD *)i + 5) + 8LL * (_QWORD)&v8[-*((_QWORD *)i + 2)]);
LABEL_19:
    v5 = ((__int64 (__fastcall *)(HCRYPTPROV, _QWORD, PCERT_PUBLIC_KEY_INFO, _QWORD, _DWORD, _QWORD, HCRYPTKEY *))ProcAddress)(
           hProv,
           dwCertEncodingType,
           pPublicKey,
           0,
           0,
           0,
           &hKey);
    CryptFreeOIDFunctionAddress(i, 0);
    goto LABEL_57;
  }
  for ( i = (void *)*((_QWORD *)v9 + 4); i; i = (void *)*((_QWORD *)i + 1) )
  {
    if ( v10 == *((_DWORD *)i + 1) && CompareStringA(0x409u, 1u, v8, -1, *((PCNZCH *)i + 2), -1) == 2 )
    {
      ProcAddress = (void *)*((_QWORD *)i + 4);
      goto LABEL_19;
    }
  }
LABEL_20:
  v14 = *((_QWORD *)v9 + 8);
  if ( !v14 )
    goto LABEL_32;
  while ( 1 )
  {
    if ( !v14 )
      goto LABEL_70;
    if ( v10 == *(_DWORD *)v14 )
    {
      v15 = *(const CHAR **)(v14 + 16);
      if ( (unsigned __int64)v8 <= 0xFFFF )
      {
        v16 = v8 == v15;
        goto LABEL_25;
      }
      if ( (unsigned __int64)v15 > 0xFFFF )
        break;
    }
LABEL_26:
    v14 = *(_QWORD *)(v14 + 8);
  }
  v16 = CompareStringA(0x409u, 1u, v8, -1, v15, -1) == 2;
LABEL_25:
  if ( !v16 )
    goto LABEL_26;
  v17 = *(_QWORD *)(v14 + 24);
  EnterCriticalSection(&CriticalSection);
  ProcAddress = *(void **)(v17 + 24);
  i = *(void **)(v17 + 8);
  if ( ProcAddress )
  {
    AddRefDll(*(struct _DLL_ELEMENT **)(v17 + 8));
LABEL_30:
    LeaveCriticalSection(&CriticalSection);
    v18 = 1;
    goto LABEL_31;
  }
  LeaveCriticalSection(&CriticalSection);
  if ( (unsigned int)LoadDll((struct _DLL_ELEMENT *)i) )
  {
    ProcAddress = GetProcAddress(*((HMODULE *)i + 3), *(LPCSTR *)(v17 + 16));
    if ( ProcAddress )
    {
      EnterCriticalSection(&CriticalSection);
      *(_QWORD *)(v17 + 24) = ProcAddress;
      goto LABEL_30;
    }
    LastError = GetLastError();
    ReleaseDll((struct _DLL_ELEMENT *)i);
    SetLastError(LastError);
  }
LABEL_70:
  v18 = 0;
  i = 0;
  ProcAddress = 0;
LABEL_31:
  if ( v18 )
    goto LABEL_19;
LABEL_32:
  SetLastError(2u);
LABEL_33:
  v19 = pPublicKey->Algorithm.pszObjId;
  v20 = qword_180158340;
  v43 = 0;
  v42 = 0;
  if ( (unsigned __int64)v19 > 0xFFFF && *v19 == 35 )
  {
    v19 = (LPSTR)o_atol_0(v19 + 1);
    if ( (unsigned __int64)v19 > 0xFFFF )
    {
      SetLastError(0x80070057);
      goto LABEL_113;
    }
  }
  if ( !*((_DWORD *)v20 + 12) )
    LoadRegFunc((LPCSTR *)v20);
  v21 = (struct _REG_OID_FUNC_ELEMENT *)*((_QWORD *)v20 + 7);
  if ( v21 && GetRegOIDFunctionAddress(v21, v10, v19, &v43, &v42) )
  {
    v26 = v43;
    j = v42;
    goto LABEL_52;
  }
  if ( (unsigned __int64)v19 <= 0xFFFF )
  {
    for ( j = (void *)*((_QWORD *)v20 + 2); ; j = (void *)*((_QWORD *)j + 1) )
    {
      if ( !j )
        goto LABEL_44;
      if ( v10 == *((_DWORD *)j + 1)
        && (unsigned __int64)v19 >= *((_QWORD *)j + 2)
        && (unsigned __int64)v19 <= *((_QWORD *)j + 3) )
      {
        break;
      }
    }
    v26 = *(void **)(*((_QWORD *)j + 5) + 8LL * (_QWORD)&v19[-*((_QWORD *)j + 2)]);
LABEL_52:
    v27 = ((__int64 (__fastcall *)(_QWORD, PCERT_PUBLIC_KEY_INFO, __int64, _QWORD, BYTE **, DWORD *))v26)(
            dwCertEncodingType,
            pPublicKey,
            0x8000,
            0,
            &pbData,
            &dwDataLen);
    if ( j && *(_DWORD *)j == 3 )
    {
      v28 = GetLastError();
      ReleaseDll((struct _DLL_ELEMENT *)j);
      SetLastError(v28);
    }
    goto LABEL_55;
  }
  for ( j = (void *)*((_QWORD *)v20 + 4); j; j = (void *)*((_QWORD *)j + 1) )
  {
    if ( v10 == *((_DWORD *)j + 1) && CompareStringA(0x409u, 1u, v19, -1, *((PCNZCH *)j + 2), -1) == 2 )
    {
      v26 = (void *)*((_QWORD *)j + 4);
      goto LABEL_52;
    }
  }
LABEL_44:
  v23 = *((_QWORD *)v20 + 8);
  if ( !v23 )
    goto LABEL_72;
  while ( 2 )
  {
    if ( !v23 )
      goto LABEL_71;
    if ( v10 != *(_DWORD *)v23 )
      goto LABEL_50;
    v24 = *(const CHAR **)(v23 + 16);
    if ( (unsigned __int64)v19 <= 0xFFFF )
    {
      v25 = v19 == v24;
      goto LABEL_49;
    }
    if ( (unsigned __int64)v24 <= 0xFFFF )
      goto LABEL_50;
    v25 = CompareStringA(0x409u, 1u, v19, -1, v24, -1) == 2;
LABEL_49:
    if ( !v25 )
    {
LABEL_50:
      v23 = *(_QWORD *)(v23 + 8);
      continue;
    }
    break;
  }
  v33 = *(_QWORD *)(v23 + 24);
  EnterCriticalSection(&CriticalSection);
  v26 = *(void **)(v33 + 24);
  j = *(void **)(v33 + 8);
  if ( v26 )
  {
    AddRefDll(*(struct _DLL_ELEMENT **)(v33 + 8));
LABEL_66:
    LeaveCriticalSection(&CriticalSection);
    v34 = 1;
    goto LABEL_67;
  }
  LeaveCriticalSection(&CriticalSection);
  if ( (unsigned int)LoadDll((struct _DLL_ELEMENT *)j) )
  {
    v26 = GetProcAddress(*((HMODULE *)j + 3), *(LPCSTR *)(v33 + 16));
    if ( v26 )
    {
      EnterCriticalSection(&CriticalSection);
      *(_QWORD *)(v33 + 24) = v26;
      goto LABEL_66;
    }
    v36 = GetLastError();
    ReleaseDll((struct _DLL_ELEMENT *)j);
    SetLastError(v36);
  }
LABEL_71:
  v26 = 0;
  j = 0;
  v34 = 0;
LABEL_67:
  if ( v34 )
    goto LABEL_52;
LABEL_72:
  SetLastError(2u);
LABEL_113:
  v37 = CryptFindOIDInfo(1u, pPublicKey->Algorithm.pszObjId, 0x40000003u);
  if ( v37 && v37->dwValue == 8704 )
    v38 = ConvertDSSPublicKeyInfo(
            dwCertEncodingType,
            (_DWORD)pPublicKey,
            0x8000,
            0,
            (__int64)&pbData,
            (__int64)&dwDataLen);
  else
    v38 = ConvertRSAPublicKeyInfo(
            dwCertEncodingType,
            (_DWORD)pPublicKey,
            0x8000,
            0,
            (__int64)&pbData,
            (__int64)&dwDataLen);
  v27 = v38;
LABEL_55:
  if ( !v27 || !CryptImportKey(hProv, pbData, dwDataLen, 0, 0, &hKey) )
  {
    hKey = 0;
    v5 = 0;
  }
LABEL_57:
  v29 = pbData;
  if ( pbData )
  {
    v30 = GetLastError();
    LocalFree(v29);
    SetLastError(v30);
  }
  if ( !v5 )
  {
    if ( GetLastError() != -2146881276 )
      goto LABEL_110;
    return I_CryptCNGGetPublicKeyLength(dwCertEncodingType, pPublicKey);
  }
  pdwDataLen = 4;
  v31 = 0;
  if ( !CryptGetKeyParam(hKey, 9u, (BYTE *)&v45, &pdwDataLen, 0) )
  {
    pdwDataLen = 4;
    if ( !CryptGetKeyParam(hKey, 8u, (BYTE *)&v45, &pdwDataLen, 0) )
    {
      dwDataLen = 0;
      v45 = 0;
      v31 = GetLastError();
      dwDataLen = 0;
      if ( CryptExportKey(hKey, 0, 6u, 0, 0, &dwDataLen) )
      {
        if ( dwDataLen >= 0x10 )
        {
          v39 = PkiNonzeroAlloc(dwDataLen);
          if ( v39 )
          {
            if ( CryptExportKey(hKey, 0, 6u, 0, (BYTE *)v39, &dwDataLen) )
              v45 = *(_DWORD *)(v39 + 12);
            PkiDefaultCryptFree((HLOCAL)v39);
          }
        }
      }
      if ( !v45 )
      {
        SetLastError(v31);
LABEL_110:
        v45 = 0;
        v31 = GetLastError();
      }
    }
  }
  if ( hKey )
    CryptDestroyKey(hKey);
  SetLastError(v31);
  return v45;
}

```

## disassembly

```asm
0x180026d50  mov     [rsp-38h+arg_0], rbx
0x180026d55  push    rbp
0x180026d56  push    rsi
0x180026d57  push    rdi
0x180026d58  push    r12
0x180026d5a  push    r13
0x180026d5c  push    r14
0x180026d5e  push    r15
0x180026d60  mov     rbp, rsp
0x180026d63  sub     rsp, 70h
0x180026d67  xor     r12d, r12d
0x180026d6a  mov     r14, rdx
0x180026d6d  mov     rdx, [rdx]; pvKey
0x180026d70  mov     r13d, ecx
0x180026d73  mov     r8d, 40000003h; dwGroupId
0x180026d79  mov     [rbp+arg_8], r12d
0x180026d7d  mov     [rbp+hKey], r12
0x180026d81  lea     r15d, [r12+1]
0x180026d86  mov     [rbp+pdwDataLen], r12d
0x180026d8a  mov     ecx, r15d; dwKeyType
0x180026d8d  call    CryptFindOIDInfo
0x180026d92  test    rax, rax
0x180026d95  jz      loc_180027449
0x180026d9b  mov     ecx, [rax+1Ch]
0x180026d9e  cmp     ecx, 0FFFFFFFDh
0x180026da1  jnb     loc_1800272EF
0x180026da7  lea     eax, [rcx-0AA01h]
0x180026dad  cmp     eax, r15d
0x180026db0  jbe     loc_180027439
0x180026db6  cmp     ecx, 2200h
0x180026dbc  jz      loc_180027359
0x180026dc2  call    I_CryptGetDefaultCryptProv
0x180026dc7  mov     [rbp+hProv], rax
0x180026dcb  test    rax, rax
0x180026dce  jz      loc_180027428
0x180026dd4  mov     rbx, [r14]
0x180026dd7  mov     ecx, r13d
0x180026dda  mov     rsi, cs:pvArg
0x180026de1  mov     edi, 0FFFFh
0x180026de6  shr     ecx, 10h
0x180026de9  mov     [rbp+var_20], r12
0x180026ded  mov     [rbp+var_18], r12
0x180026df1  mov     [rbp+pbData], r12
0x180026df5  mov     [rbp+dwDataLen], r12d
0x180026df9  movzx   r12d, r13w
0x180026dfd  test    r12d, r12d
0x180026e00  cmovz   r12d, ecx
0x180026e04  cmp     rbx, rdi
0x180026e07  ja      loc_18002716D
0x180026e0d  cmp     dword ptr [rsi+30h], 0
0x180026e11  jz      loc_1800272C4
0x180026e17  mov     rcx, [rsi+38h]; struct _REG_OID_FUNC_ELEMENT *
0x180026e1b  test    rcx, rcx
0x180026e1e  jnz     loc_1800272FF
0x180026e24  cmp     rbx, rdi
0x180026e27  ja      loc_1800271CC
0x180026e2d  mov     rdi, [rsi+10h]
0x180026e31  test    rdi, rdi
0x180026e34  jz      short loc_180026E99
0x180026e36  cmp     r12d, [rdi+4]
0x180026e3a  jnz     loc_180026ECD
0x180026e40  cmp     rbx, [rdi+10h]
0x180026e44  jb      loc_180026ECD
0x180026e4a  cmp     rbx, [rdi+18h]
0x180026e4e  ja      short loc_180026ECD
0x180026e50  sub     rbx, [rdi+10h]
0x180026e54  mov     rax, [rdi+28h]
0x180026e58  mov     rbx, [rax+rbx*8]
0x180026e5c  mov     rcx, [rbp+hProv]
0x180026e60  lea     rax, [rbp+hKey]
0x180026e64  mov     [rsp+70h+var_40], rax
0x180026e69  xor     r12d, r12d
0x180026e6c  mov     [rsp+70h+phKey], r12
0x180026e71  mov     rax, rbx
0x180026e74  xor     r9d, r9d
0x180026e77  mov     [rsp+70h+dwFlags], r12d
0x180026e7c  mov     r8, r14
0x180026e7f  mov     edx, r13d
0x180026e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e87  xor     edx, edx; dwFlags
0x180026e89  mov     rcx, rdi; hFuncAddr
0x180026e8c  mov     r15d, eax
0x180026e8f  call    CryptFreeOIDFunctionAddress
0x180026e94  jmp     loc_180027057
0x180026e99  mov     rdi, [rsi+40h]
0x180026e9d  test    rdi, rdi
0x180026ea0  jz      short loc_180026F18
0x180026ea2  mov     esi, 0FFFFh
0x180026ea7  test    rdi, rdi
0x180026eaa  jz      loc_180027140
0x180026eb0  cmp     r12d, [rdi]
0x180026eb3  jnz     short loc_180026EC7
0x180026eb5  mov     rax, [rdi+10h]
0x180026eb9  cmp     rbx, rsi
0x180026ebc  ja      loc_180027259
0x180026ec2  cmp     rbx, rax
0x180026ec5  jz      short loc_180026ED6
0x180026ec7  mov     rdi, [rdi+8]
0x180026ecb  jmp     short loc_180026EA7
0x180026ecd  mov     rdi, [rdi+8]
0x180026ed1  jmp     loc_180026E31
0x180026ed6  mov     rsi, [rdi+18h]
0x180026eda  lea     rcx, CriticalSection; lpCriticalSection
0x180026ee1  call    cs:__imp_EnterCriticalSection
0x180026ee7  mov     rbx, [rsi+18h]
0x180026eeb  mov     rdi, [rsi+8]
0x180026eef  test    rbx, rbx
0x180026ef2  jz      loc_180027375
0x180026ef8  mov     rcx, rdi; struct _DLL_ELEMENT *
0x180026efb  call    ?AddRefDll@@YAXPEAU_DLL_ELEMENT@@@Z; AddRefDll(_DLL_ELEMENT *)
0x180026f00  lea     rcx, CriticalSection; lpCriticalSection
0x180026f07  call    cs:__imp_LeaveCriticalSection
0x180026f0d  mov     eax, r15d
0x180026f10  test    eax, eax
0x180026f12  jnz     loc_180026E5C
0x180026f18  mov     ecx, 2; dwErrCode
0x180026f1d  call    cs:__imp_SetLastError
0x180026f23  mov     edi, 0FFFFh
0x180026f28  mov     rbx, [r14]
0x180026f2b  mov     rsi, cs:qword_180158340
0x180026f32  mov     [rbp+var_18], 0
0x180026f3a  mov     [rbp+var_20], 0
0x180026f42  cmp     rbx, rdi
0x180026f45  ja      loc_18002719B
0x180026f4b  cmp     dword ptr [rsi+30h], 0
0x180026f4f  jz      loc_1800272D1
0x180026f55  mov     rcx, [rsi+38h]; struct _REG_OID_FUNC_ELEMENT *
0x180026f59  test    rcx, rcx
0x180026f5c  jnz     loc_18002732C
0x180026f62  cmp     rbx, rdi
0x180026f65  ja      loc_18002720E
0x180026f6b  mov     rdi, [rsi+10h]
0x180026f6f  test    rdi, rdi
0x180026f72  jz      short loc_180026F8C
0x180026f74  cmp     r12d, [rdi+4]
0x180026f78  jnz     short loc_180026F86
0x180026f7a  cmp     rbx, [rdi+10h]
0x180026f7e  jb      short loc_180026F86
0x180026f80  cmp     rbx, [rdi+18h]
0x180026f84  jbe     short loc_180026FC8
0x180026f86  mov     rdi, [rdi+8]
0x180026f8a  jmp     short loc_180026F6F
0x180026f8c  mov     rdi, [rsi+40h]
0x180026f90  test    rdi, rdi
0x180026f93  jz      loc_180027159
0x180026f99  mov     esi, 0FFFFh
0x180026f9e  test    rdi, rdi
0x180026fa1  jz      loc_18002714B
0x180026fa7  cmp     r12d, [rdi]
0x180026faa  jnz     short loc_180026FC2
0x180026fac  mov     rax, [rdi+10h]
0x180026fb0  cmp     rbx, rsi
0x180026fb3  ja      loc_180027293
0x180026fb9  cmp     rbx, rax
0x180026fbc  jz      loc_1800270E1
0x180026fc2  mov     rdi, [rdi+8]
0x180026fc6  jmp     short loc_180026F9E
0x180026fc8  sub     rbx, [rdi+10h]
0x180026fcc  mov     rax, [rdi+28h]
0x180026fd0  mov     rbx, [rax+rbx*8]
0x180026fd4  xor     r12d, r12d
0x180026fd7  lea     rax, [rbp+dwDataLen]
0x180026fdb  xor     r9d, r9d
0x180026fde  mov     [rsp+70h+phKey], rax
0x180026fe3  mov     r8d, 8000h
0x180026fe9  lea     rax, [rbp+pbData]
0x180026fed  mov     rdx, r14
0x180026ff0  mov     qword ptr [rsp+70h+dwFlags], rax
0x180026ff5  mov     ecx, r13d
0x180026ff8  mov     rax, rbx
0x180026ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027000  mov     esi, eax
0x180027002  test    rdi, rdi
0x180027005  jz      short loc_180027024
0x180027007  cmp     dword ptr [rdi], 3
0x18002700a  jnz     short loc_180027024
0x18002700c  call    cs:__imp_GetLastError
0x180027012  mov     rcx, rdi; struct _DLL_ELEMENT *
0x180027015  mov     ebx, eax
0x180027017  call    ?ReleaseDll@@YAXPEAU_DLL_ELEMENT@@@Z; ReleaseDll(_DLL_ELEMENT *)
0x18002701c  mov     ecx, ebx; dwErrCode
0x18002701e  call    cs:__imp_SetLastError
0x180027024  test    esi, esi
0x180027026  jz      loc_180027369
0x18002702c  mov     r8d, [rbp+dwDataLen]; dwDataLen
0x180027030  lea     rax, [rbp+hKey]
0x180027034  mov     rdx, [rbp+pbData]; pbData
0x180027038  xor     r9d, r9d; hPubKey
0x18002703b  mov     rcx, [rbp+hProv]; hProv
0x18002703f  mov     [rsp+70h+phKey], rax; phKey
0x180027044  mov     [rsp+70h+dwFlags], r12d; dwFlags
0x180027049  call    cs:__imp_CryptImportKey
0x18002704f  test    eax, eax
0x180027051  jz      loc_180027369
0x180027057  mov     rdi, [rbp+pbData]
0x18002705b  test    rdi, rdi
0x18002705e  jz      short loc_180027079
0x180027060  call    cs:__imp_GetLastError
0x180027066  mov     rcx, rdi; hMem
0x180027069  mov     ebx, eax
0x18002706b  call    cs:__imp_LocalFree
0x180027071  mov     ecx, ebx; dwErrCode
0x180027073  call    cs:__imp_SetLastError
0x180027079  test    r15d, r15d
0x18002707c  jz      loc_1800272DE
0x180027082  mov     rcx, [rbp+hKey]; hKey
0x180027086  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18002708a  mov     ebx, 4
0x18002708f  mov     [rsp+70h+dwFlags], r12d; dwFlags
0x180027094  lea     r8, [rbp+arg_8]; pbData
0x180027098  mov     [rbp+pdwDataLen], ebx
0x18002709b  mov     edi, r12d
0x18002709e  lea     edx, [rbx+5]; dwParam
0x1800270a1  call    cs:__imp_CryptGetKeyParam
0x1800270a7  test    eax, eax
0x1800270a9  jz      loc_180116B82
0x1800270af  mov     rcx, [rbp+hKey]; hKey
0x1800270b3  test    rcx, rcx
0x1800270b6  jz      short loc_1800270BE
0x1800270b8  call    cs:__imp_CryptDestroyKey
0x1800270be  mov     ecx, edi; dwErrCode
0x1800270c0  call    cs:__imp_SetLastError
0x1800270c6  mov     eax, [rbp+arg_8]
0x1800270c9  mov     rbx, [rsp+70h+arg_0]
0x1800270d1  add     rsp, 70h
0x1800270d5  pop     r15
0x1800270d7  pop     r14
0x1800270d9  pop     r13
0x1800270db  pop     r12
0x1800270dd  pop     rdi
0x1800270de  pop     rsi
0x1800270df  pop     rbp
0x1800270e0  retn
0x1800270e1  mov     rsi, [rdi+18h]
0x1800270e5  lea     rcx, CriticalSection; lpCriticalSection
0x1800270ec  call    cs:__imp_EnterCriticalSection
0x1800270f2  mov     rbx, [rsi+18h]
0x1800270f6  xor     r12d, r12d
0x1800270f9  mov     rdi, [rsi+8]
0x1800270fd  test    rbx, rbx
0x180027100  jz      loc_1800273C2
0x180027106  mov     rcx, rdi; struct _DLL_ELEMENT *
0x180027109  call    ?AddRefDll@@YAXPEAU_DLL_ELEMENT@@@Z; AddRefDll(_DLL_ELEMENT *)
0x18002710e  lea     rcx, CriticalSection; lpCriticalSection
0x180027115  call    cs:__imp_LeaveCriticalSection
0x18002711b  mov     eax, r15d
0x18002711e  test    eax, eax
0x180027120  jnz     loc_180026FD7
0x180027126  jmp     short loc_18002715C
0x180027128  call    cs:__imp_GetLastError
0x18002712e  mov     rcx, rdi; struct _DLL_ELEMENT *
0x180027131  mov     ebx, eax
0x180027133  call    ?ReleaseDll@@YAXPEAU_DLL_ELEMENT@@@Z; ReleaseDll(_DLL_ELEMENT *)
0x180027138  mov     ecx, ebx; dwErrCode
0x18002713a  call    cs:__imp_SetLastError
0x180027140  xor     eax, eax
0x180027142  xor     edi, edi
0x180027144  xor     ebx, ebx
0x180027146  jmp     loc_180026F10
0x18002714b  xor     r12d, r12d
0x18002714e  mov     rbx, r12
0x180027151  mov     rdi, r12
0x180027154  mov     eax, r12d
0x180027157  jmp     short loc_18002711E
0x180027159  xor     r12d, r12d
0x18002715c  mov     ecx, 2; dwErrCode
0x180027161  call    cs:__imp_SetLastError
0x180027167  nop
0x180027168  jmp     loc_180116B0E
0x18002716d  cmp     byte ptr [rbx], 23h ; '#'
0x180027170  jnz     loc_180026E0D
0x180027176  lea     rcx, [rbx+1]; String
0x18002717a  call    _o_atol_0
0x18002717f  movsxd  rbx, eax
0x180027182  cmp     rbx, rdi
0x180027185  jbe     loc_180026E0D
0x18002718b  mov     ecx, 80070057h; dwErrCode
0x180027190  call    cs:__imp_SetLastError
0x180027196  jmp     loc_180026F28
0x18002719b  cmp     byte ptr [rbx], 23h ; '#'
0x18002719e  jnz     loc_180026F4B
0x1800271a4  lea     rcx, [rbx+1]; String
0x1800271a8  call    _o_atol_0
0x1800271ad  movsxd  rbx, eax
0x1800271b0  cmp     rbx, rdi
0x1800271b3  jbe     loc_180026F4B
0x1800271b9  mov     ecx, 80070057h; dwErrCode
0x1800271be  call    cs:__imp_SetLastError
0x1800271c4  xor     r12d, r12d
0x1800271c7  jmp     loc_180116B0E
0x1800271cc  mov     rdi, [rsi+20h]
0x1800271d0  test    rdi, rdi
0x1800271d3  jz      loc_180026E99
0x1800271d9  cmp     r12d, [rdi+4]
0x1800271dd  jnz     short loc_180027208
0x1800271df  mov     rax, [rdi+10h]
0x1800271e3  or      ecx, 0FFFFFFFFh
0x1800271e6  mov     dword ptr [rsp+70h+phKey], ecx; cchCount2
0x1800271ea  mov     r9d, ecx; cchCount1
0x1800271ed  mov     ecx, 409h; Locale
  ... truncated ...
```
