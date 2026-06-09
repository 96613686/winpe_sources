# CryptImportPublicKeyInfoEx

- ea: `0x1800275a0`
- end: `0x180027ba1`
- name: `CryptImportPublicKeyInfoEx`
- size: `1537`
- prototype: `BOOL __stdcall(HCRYPTPROV hCryptProv, DWORD dwCertEncodingType, PCERT_PUBLIC_KEY_INFO pInfo, ALG_ID aiKeyAlg, DWORD dwFlags, void *pvAuxInfo, HCRYPTKEY *phKey)`
- caller_count: `4`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180091c8c`
- `0x1800959d4`
- `0x180101980`
- `0x180101d20`

## callees

- `0x180006980`
- `0x180009da0`
- `0x180012d00`
- `0x1800258c4`
- `0x1800275a0`
- `0x180027ba8`
- `0x180027cb0`
- `0x1800286e0`
- `0x180029494`
- `0x1800b1e60`
- `0x1800bf564`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027912`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027728`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027827`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002788a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027901`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027924`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027955`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180116c46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027728`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027827`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002788a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027901`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027924`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027955`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180116c46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027712`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800278d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027b16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027b5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027712`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800278d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027b16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027b5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800276ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800278b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027b4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027b92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800276ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800278b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027b4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027b92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027882`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027882`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027b34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027b7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027b34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027b7d`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800279b9`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800279fb`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180027a38`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180027a72`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800279b9`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800279fb`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180027a38`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180027a72`
- `CRYPTSP!CryptImportKey` at `0x180027860`
- `CRYPTSP!CryptImportKey` at `0x180027860`

## pseudocode

```c
BOOL __stdcall CryptImportPublicKeyInfoEx(
        HCRYPTPROV hCryptProv,
        DWORD dwCertEncodingType,
        PCERT_PUBLIC_KEY_INFO pInfo,
        ALG_ID aiKeyAlg,
        DWORD dwFlags,
        void *pvAuxInfo,
        HCRYPTKEY *phKey)
{
  LPSTR pszObjId; // rbx
  struct _FUNC_SET *v8; // rsi
  DWORD v10; // r14d
  BOOL v12; // r15d
  struct _REG_OID_FUNC_ELEMENT *v13; // rcx
  void *i; // rdi
  FARPROC ProcAddress; // rbx
  int v16; // eax
  __int64 v17; // rdi
  const CHAR *v18; // rax
  bool v19; // zf
  __int64 v20; // rsi
  int v21; // eax
  LPSTR v22; // rbx
  struct _FUNC_SET *v23; // rsi
  struct _REG_OID_FUNC_ELEMENT *v24; // rcx
  void *j; // rdi
  __int64 v26; // rdi
  const CHAR *v27; // rax
  bool v28; // zf
  FARPROC v29; // rbx
  int v30; // eax
  int v31; // esi
  DWORD v32; // ebx
  HCRYPTKEY *v33; // rbx
  BYTE *v34; // rdi
  DWORD v35; // ebx
  __int64 v37; // rsi
  int v38; // eax
  DWORD v39; // ecx
  DWORD LastError; // ebx
  DWORD v41; // ebx
  PCCRYPT_OID_INFO OIDInfo; // rax
  int v43; // eax
  void *v44; // [rsp+40h] [rbp-18h] BYREF
  void *v45[2]; // [rsp+48h] [rbp-10h] BYREF
  DWORD dwDataLen; // [rsp+A8h] [rbp+50h] BYREF
  BYTE *pbData; // [rsp+B0h] [rbp+58h] BYREF
  ALG_ID v49; // [rsp+B8h] [rbp+60h]

  v49 = aiKeyAlg;
  pszObjId = pInfo->Algorithm.pszObjId;
  v8 = pvArg;
  v10 = (unsigned __int16)dwCertEncodingType;
  v44 = 0;
  v45[0] = 0;
  v12 = 1;
  if ( !(_WORD)dwCertEncodingType )
    v10 = HIWORD(dwCertEncodingType);
  pbData = 0;
  dwDataLen = 0;
  if ( (unsigned __int64)pszObjId > 0xFFFF && *pszObjId == 35 )
  {
    pszObjId = (LPSTR)o_atol_0(pszObjId + 1);
    if ( (unsigned __int64)pszObjId > 0xFFFF )
    {
      SetLastError(0x80070057);
      goto LABEL_29;
    }
  }
  if ( !*((_DWORD *)v8 + 12) )
    LoadRegFunc((LPCSTR *)v8);
  v13 = (struct _REG_OID_FUNC_ELEMENT *)*((_QWORD *)v8 + 7);
  if ( v13 && GetRegOIDFunctionAddress(v13, v10, pszObjId, &v44, v45) )
  {
    i = v45[0];
    v16 = ((__int64 (__fastcall *)(HCRYPTPROV, _QWORD, PCERT_PUBLIC_KEY_INFO, _QWORD, DWORD, void *, HCRYPTKEY *))v44)(
            hCryptProv,
            dwCertEncodingType,
            pInfo,
            v49,
            dwFlags,
            pvAuxInfo,
            phKey);
    goto LABEL_15;
  }
  if ( (unsigned __int64)pszObjId <= 0xFFFF )
  {
    for ( i = (void *)*((_QWORD *)v8 + 2); ; i = (void *)*((_QWORD *)i + 1) )
    {
      if ( !i )
        goto LABEL_16;
      if ( v10 == *((_DWORD *)i + 1)
        && (unsigned __int64)pszObjId >= *((_QWORD *)i + 2)
        && (unsigned __int64)pszObjId <= *((_QWORD *)i + 3) )
      {
        break;
      }
    }
    ProcAddress = *(FARPROC *)(*((_QWORD *)i + 5) + 8LL * (_QWORD)&pszObjId[-*((_QWORD *)i + 2)]);
    goto LABEL_14;
  }
  for ( i = (void *)*((_QWORD *)v8 + 4); i; i = (void *)*((_QWORD *)i + 1) )
  {
    if ( v10 == *((_DWORD *)i + 1) && CompareStringA(0x409u, 1u, pszObjId, -1, *((PCNZCH *)i + 2), -1) == 2 )
    {
      v16 = (*((__int64 (__fastcall **)(HCRYPTPROV, _QWORD, PCERT_PUBLIC_KEY_INFO, _QWORD, DWORD, void *, HCRYPTKEY *))i
             + 4))(
              hCryptProv,
              dwCertEncodingType,
              pInfo,
              v49,
              dwFlags,
              pvAuxInfo,
              phKey);
      goto LABEL_15;
    }
  }
LABEL_16:
  v17 = *((_QWORD *)v8 + 8);
  if ( !v17 )
    goto LABEL_28;
  while ( 1 )
  {
    if ( !v17 )
      goto LABEL_65;
    if ( v10 == *(_DWORD *)v17 )
    {
      v18 = *(const CHAR **)(v17 + 16);
      if ( (unsigned __int64)pszObjId <= 0xFFFF )
      {
        v19 = pszObjId == v18;
        goto LABEL_21;
      }
      if ( (unsigned __int64)v18 > 0xFFFF )
        break;
    }
LABEL_22:
    v17 = *(_QWORD *)(v17 + 8);
  }
  v19 = CompareStringA(0x409u, 1u, pszObjId, -1, v18, -1) == 2;
LABEL_21:
  if ( !v19 )
    goto LABEL_22;
  v20 = *(_QWORD *)(v17 + 24);
  EnterCriticalSection(&CriticalSection);
  ProcAddress = *(FARPROC *)(v20 + 24);
  i = *(void **)(v20 + 8);
  if ( ProcAddress )
  {
    AddRefDll(*(struct _DLL_ELEMENT **)(v20 + 8));
LABEL_26:
    LeaveCriticalSection(&CriticalSection);
    v21 = 1;
    goto LABEL_27;
  }
  LeaveCriticalSection(&CriticalSection);
  if ( (unsigned int)LoadDll((struct _DLL_ELEMENT *)i) )
  {
    ProcAddress = GetProcAddress(*((HMODULE *)i + 3), *(LPCSTR *)(v20 + 16));
    if ( ProcAddress )
    {
      EnterCriticalSection(&CriticalSection);
      *(_QWORD *)(v20 + 24) = ProcAddress;
      goto LABEL_26;
    }
    LastError = GetLastError();
    ReleaseDll((struct _DLL_ELEMENT *)i);
    SetLastError(LastError);
  }
LABEL_65:
  v21 = 0;
  i = 0;
  ProcAddress = 0;
LABEL_27:
  if ( v21 )
  {
LABEL_14:
    v16 = ((__int64 (__fastcall *)(HCRYPTPROV, _QWORD, PCERT_PUBLIC_KEY_INFO, _QWORD, DWORD, void *, HCRYPTKEY *))ProcAddress)(
            hCryptProv,
            dwCertEncodingType,
            pInfo,
            v49,
            dwFlags,
            pvAuxInfo,
            phKey);
LABEL_15:
    v12 = v16;
    CryptFreeOIDFunctionAddress(i, 0);
    goto LABEL_56;
  }
LABEL_28:
  SetLastError(2u);
LABEL_29:
  v22 = pInfo->Algorithm.pszObjId;
  v23 = qword_180158340;
  v45[0] = 0;
  v44 = 0;
  if ( (unsigned __int64)v22 > 0xFFFF && *v22 == 35 )
  {
    v22 = (LPSTR)o_atol_0(v22 + 1);
    if ( (unsigned __int64)v22 > 0xFFFF )
    {
      v39 = -2147024809;
      goto LABEL_101;
    }
  }
  if ( !*((_DWORD *)v23 + 12) )
    LoadRegFunc((LPCSTR *)v23);
  v24 = (struct _REG_OID_FUNC_ELEMENT *)*((_QWORD *)v23 + 7);
  if ( v24 && GetRegOIDFunctionAddress(v24, v10, v22, v45, &v44) )
  {
    j = v44;
    v30 = ((__int64 (__fastcall *)(_QWORD, PCERT_PUBLIC_KEY_INFO, __int64, _QWORD, BYTE **, DWORD *))v45[0])(
            dwCertEncodingType,
            pInfo,
            0x8000,
            0,
            &pbData,
            &dwDataLen);
    goto LABEL_49;
  }
  if ( (unsigned __int64)v22 <= 0xFFFF )
  {
    for ( j = (void *)*((_QWORD *)v23 + 2); ; j = (void *)*((_QWORD *)j + 1) )
    {
      if ( !j )
        goto LABEL_40;
      if ( v10 == *((_DWORD *)j + 1)
        && (unsigned __int64)v22 >= *((_QWORD *)j + 2)
        && (unsigned __int64)v22 <= *((_QWORD *)j + 3) )
      {
        break;
      }
    }
    v29 = *(FARPROC *)(*((_QWORD *)j + 5) + 8LL * (_QWORD)&v22[-*((_QWORD *)j + 2)]);
    goto LABEL_48;
  }
  for ( j = (void *)*((_QWORD *)v23 + 4); j; j = (void *)*((_QWORD *)j + 1) )
  {
    if ( v10 == *((_DWORD *)j + 1) && CompareStringA(0x409u, 1u, v22, -1, *((PCNZCH *)j + 2), -1) == 2 )
    {
      v30 = (*((__int64 (__fastcall **)(_QWORD, PCERT_PUBLIC_KEY_INFO, __int64, _QWORD, BYTE **, DWORD *))j + 4))(
              dwCertEncodingType,
              pInfo,
              0x8000,
              0,
              &pbData,
              &dwDataLen);
      goto LABEL_49;
    }
  }
LABEL_40:
  v26 = *((_QWORD *)v23 + 8);
  if ( !v26 )
    goto LABEL_63;
  while ( 2 )
  {
    if ( !v26 )
      goto LABEL_67;
    if ( v10 != *(_DWORD *)v26 )
      goto LABEL_46;
    v27 = *(const CHAR **)(v26 + 16);
    if ( (unsigned __int64)v22 <= 0xFFFF )
    {
      v28 = v22 == v27;
      goto LABEL_45;
    }
    if ( (unsigned __int64)v27 <= 0xFFFF )
      goto LABEL_46;
    v28 = CompareStringA(0x409u, 1u, v22, -1, v27, -1) == 2;
LABEL_45:
    if ( !v28 )
    {
LABEL_46:
      v26 = *(_QWORD *)(v26 + 8);
      continue;
    }
    break;
  }
  v37 = *(_QWORD *)(v26 + 24);
  EnterCriticalSection(&CriticalSection);
  v29 = *(FARPROC *)(v37 + 24);
  j = *(void **)(v37 + 8);
  if ( v29 )
  {
    AddRefDll(*(struct _DLL_ELEMENT **)(v37 + 8));
LABEL_61:
    LeaveCriticalSection(&CriticalSection);
    v38 = 1;
    goto LABEL_62;
  }
  LeaveCriticalSection(&CriticalSection);
  if ( (unsigned int)LoadDll((struct _DLL_ELEMENT *)j) )
  {
    v29 = GetProcAddress(*((HMODULE *)j + 3), *(LPCSTR *)(v37 + 16));
    if ( v29 )
    {
      EnterCriticalSection(&CriticalSection);
      *(_QWORD *)(v37 + 24) = v29;
      goto LABEL_61;
    }
    v41 = GetLastError();
    ReleaseDll((struct _DLL_ELEMENT *)j);
    SetLastError(v41);
  }
LABEL_67:
  v38 = 0;
  j = 0;
  v29 = 0;
LABEL_62:
  if ( v38 )
  {
LABEL_48:
    v30 = ((__int64 (__fastcall *)(_QWORD, PCERT_PUBLIC_KEY_INFO, __int64, _QWORD, BYTE **, DWORD *))v29)(
            dwCertEncodingType,
            pInfo,
            0x8000,
            0,
            &pbData,
            &dwDataLen);
LABEL_49:
    v31 = v30;
    if ( j && *(_DWORD *)j == 3 )
    {
      v32 = GetLastError();
      ReleaseDll((struct _DLL_ELEMENT *)j);
      SetLastError(v32);
    }
    goto LABEL_52;
  }
LABEL_63:
  v39 = 2;
LABEL_101:
  SetLastError(v39);
  OIDInfo = CryptFindOIDInfo(1u, pInfo->Algorithm.pszObjId, 0x40000003u);
  if ( OIDInfo && OIDInfo->dwValue == 8704 )
    v43 = ConvertDSSPublicKeyInfo(dwCertEncodingType, (_DWORD)pInfo, 0x8000, 0, (__int64)&pbData, (__int64)&dwDataLen);
  else
    v43 = ConvertRSAPublicKeyInfo(dwCertEncodingType, (_DWORD)pInfo, 0x8000, 0, (__int64)&pbData, (__int64)&dwDataLen);
  v31 = v43;
LABEL_52:
  v33 = phKey;
  if ( !v31 )
    goto LABEL_94;
  if ( v49 )
    *((_DWORD *)pbData + 1) = v49;
  if ( !CryptImportKey(hCryptProv, pbData, dwDataLen, 0, 0, v33) )
  {
LABEL_94:
    *v33 = 0;
    v12 = 0;
  }
LABEL_56:
  v34 = pbData;
  if ( pbData )
  {
    v35 = GetLastError();
    LocalFree(v34);
    SetLastError(v35);
  }
  return v12;
}

```

## disassembly

```asm
0x1800275a0  mov     [rsp-40h+arg_18], r9d
0x1800275a5  mov     [rsp-40h+hProv], rcx
0x1800275aa  push    rbp
0x1800275ab  push    rbx
0x1800275ac  push    rsi
0x1800275ad  push    rdi
0x1800275ae  push    r12
0x1800275b0  push    r13
0x1800275b2  push    r14
0x1800275b4  push    r15
0x1800275b6  mov     rbp, rsp
0x1800275b9  sub     rsp, 58h
0x1800275bd  mov     rbx, [r8]
0x1800275c0  mov     eax, edx
0x1800275c2  mov     rsi, cs:pvArg
0x1800275c9  mov     edi, 0FFFFh
0x1800275ce  shr     eax, 10h
0x1800275d1  mov     r12, r8
0x1800275d4  movzx   r14d, dx
0x1800275d8  mov     r13d, edx
0x1800275db  test    r14d, r14d
0x1800275de  mov     [rbp+var_18], 0
0x1800275e6  mov     [rbp+var_10], 0
0x1800275ee  mov     r15d, 1
0x1800275f4  cmovz   r14d, eax
0x1800275f8  mov     [rbp+pbData], 0
0x180027600  mov     [rbp+dwDataLen], 0
0x180027607  cmp     rbx, rdi
0x18002760a  ja      loc_180027932
0x180027610  cmp     dword ptr [rsi+30h], 0
0x180027614  jz      loc_180027A80
0x18002761a  mov     rcx, [rsi+38h]; struct _REG_OID_FUNC_ELEMENT *
0x18002761e  test    rcx, rcx
0x180027621  jnz     loc_180027AA6
0x180027627  cmp     rbx, rdi
0x18002762a  ja      loc_180027988
0x180027630  mov     rdi, [rsi+10h]
0x180027634  test    rdi, rdi
0x180027637  jz      short loc_1800276A4
0x180027639  cmp     r14d, [rdi+4]
0x18002763d  jnz     loc_1800276D8
0x180027643  cmp     rbx, [rdi+10h]
0x180027647  jb      loc_1800276D8
0x18002764d  cmp     rbx, [rdi+18h]
0x180027651  ja      loc_1800276D8
0x180027657  sub     rbx, [rdi+10h]
0x18002765b  mov     rax, [rdi+28h]
0x18002765f  mov     rbx, [rax+rbx*8]
0x180027663  mov     rax, [rbp+phKey]
0x180027667  mov     r8, r12
0x18002766a  mov     r9d, [rbp+arg_18]
0x18002766e  mov     edx, r13d
0x180027671  mov     rcx, [rbp+hProv]
0x180027675  mov     [rsp+58h+var_28], rax
0x18002767a  mov     rax, [rbp+pvAuxInfo]
0x18002767e  mov     [rsp+58h+var_30], rax
0x180027683  mov     eax, [rbp+dwFlags]
0x180027686  mov     [rsp+58h+var_38], eax
0x18002768a  mov     rax, rbx
0x18002768d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027692  xor     edx, edx; dwFlags
0x180027694  mov     rcx, rdi; hFuncAddr
0x180027697  mov     r15d, eax
0x18002769a  call    CryptFreeOIDFunctionAddress
0x18002769f  jmp     loc_18002786E
0x1800276a4  mov     rdi, [rsi+40h]
0x1800276a8  test    rdi, rdi
0x1800276ab  jz      short loc_180027723
0x1800276ad  mov     esi, 0FFFFh
0x1800276b2  test    rdi, rdi
0x1800276b5  jz      loc_180027907
0x1800276bb  cmp     r14d, [rdi]
0x1800276be  jnz     short loc_1800276D2
0x1800276c0  mov     rax, [rdi+10h]
0x1800276c4  cmp     rbx, rsi
0x1800276c7  ja      loc_180027A15
0x1800276cd  cmp     rbx, rax
0x1800276d0  jz      short loc_1800276E1
0x1800276d2  mov     rdi, [rdi+8]
0x1800276d6  jmp     short loc_1800276B2
0x1800276d8  mov     rdi, [rdi+8]
0x1800276dc  jmp     loc_180027634
0x1800276e1  mov     rsi, [rdi+18h]
0x1800276e5  lea     rcx, CriticalSection; lpCriticalSection
0x1800276ec  call    cs:__imp_EnterCriticalSection
0x1800276f2  mov     rbx, [rsi+18h]
0x1800276f6  mov     rdi, [rsi+8]
0x1800276fa  test    rbx, rbx
0x1800276fd  jz      loc_180027B0F
0x180027703  mov     rcx, rdi; struct _DLL_ELEMENT *
0x180027706  call    ?AddRefDll@@YAXPEAU_DLL_ELEMENT@@@Z; AddRefDll(_DLL_ELEMENT *)
0x18002770b  lea     rcx, CriticalSection; lpCriticalSection
0x180027712  call    cs:__imp_LeaveCriticalSection
0x180027718  mov     eax, r15d
0x18002771b  test    eax, eax
0x18002771d  jnz     loc_180027663
0x180027723  mov     ecx, 2; dwErrCode
0x180027728  call    cs:__imp_SetLastError
0x18002772e  mov     edi, 0FFFFh
0x180027733  mov     rbx, [r12]
0x180027737  mov     rsi, cs:qword_180158340
0x18002773e  mov     [rbp+var_10], 0
0x180027746  mov     [rbp+var_18], 0
0x18002774e  cmp     rbx, rdi
0x180027751  ja      loc_180027960
0x180027757  cmp     dword ptr [rsi+30h], 0
0x18002775b  jz      loc_180027A8D
0x180027761  mov     rcx, [rsi+38h]; struct _REG_OID_FUNC_ELEMENT *
0x180027765  test    rcx, rcx
0x180027768  jnz     loc_180027AD3
0x18002776e  cmp     rbx, rdi
0x180027771  ja      loc_1800279CA
0x180027777  mov     rdi, [rsi+10h]
0x18002777b  test    rdi, rdi
0x18002777e  jz      short loc_180027798
0x180027780  cmp     r14d, [rdi+4]
0x180027784  jnz     short loc_180027792
0x180027786  cmp     rbx, [rdi+10h]
0x18002778a  jb      short loc_180027792
0x18002778c  cmp     rbx, [rdi+18h]
0x180027790  jbe     short loc_1800277D4
0x180027792  mov     rdi, [rdi+8]
0x180027796  jmp     short loc_18002777B
0x180027798  mov     rdi, [rsi+40h]
0x18002779c  test    rdi, rdi
0x18002779f  jz      loc_1800278E5
0x1800277a5  mov     esi, 0FFFFh
0x1800277aa  test    rdi, rdi
0x1800277ad  jz      loc_18002792A
0x1800277b3  cmp     r14d, [rdi]
0x1800277b6  jnz     short loc_1800277CE
0x1800277b8  mov     rax, [rdi+10h]
0x1800277bc  cmp     rbx, rsi
0x1800277bf  ja      loc_180027A4F
0x1800277c5  cmp     rbx, rax
0x1800277c8  jz      loc_1800278A4
0x1800277ce  mov     rdi, [rdi+8]
0x1800277d2  jmp     short loc_1800277AA
0x1800277d4  sub     rbx, [rdi+10h]
0x1800277d8  mov     rax, [rdi+28h]
0x1800277dc  mov     rbx, [rax+rbx*8]
0x1800277e0  lea     rax, [rbp+dwDataLen]
0x1800277e4  xor     r9d, r9d
0x1800277e7  mov     [rsp+58h+var_30], rax
0x1800277ec  mov     r8d, 8000h
0x1800277f2  lea     rax, [rbp+pbData]
0x1800277f6  mov     rdx, r12
0x1800277f9  mov     qword ptr [rsp+58h+var_38], rax
0x1800277fe  mov     ecx, r13d
0x180027801  mov     rax, rbx
0x180027804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027809  mov     esi, eax
0x18002780b  test    rdi, rdi
0x18002780e  jz      short loc_18002782D
0x180027810  cmp     dword ptr [rdi], 3
0x180027813  jnz     short loc_18002782D
0x180027815  call    cs:__imp_GetLastError
0x18002781b  mov     rcx, rdi; struct _DLL_ELEMENT *
0x18002781e  mov     ebx, eax
0x180027820  call    ?ReleaseDll@@YAXPEAU_DLL_ELEMENT@@@Z; ReleaseDll(_DLL_ELEMENT *)
0x180027825  mov     ecx, ebx; dwErrCode
0x180027827  call    cs:__imp_SetLastError
0x18002782d  mov     rbx, [rbp+phKey]
0x180027831  test    esi, esi
0x180027833  jz      loc_180027B00
0x180027839  mov     ecx, [rbp+arg_18]
0x18002783c  test    ecx, ecx
0x18002783e  jnz     loc_180027A9A
0x180027844  mov     r8d, [rbp+dwDataLen]; dwDataLen
0x180027848  xor     r9d, r9d; hPubKey
0x18002784b  mov     rdx, [rbp+pbData]; pbData
0x18002784f  mov     rcx, [rbp+hProv]; hProv
0x180027853  mov     [rsp+58h+var_30], rbx; phKey
0x180027858  mov     [rsp+58h+var_38], 0; dwFlags
0x180027860  call    cs:__imp_CryptImportKey
0x180027866  test    eax, eax
0x180027868  jz      loc_180027B00
0x18002786e  mov     rdi, [rbp+pbData]
0x180027872  test    rdi, rdi
0x180027875  jz      short loc_180027890
0x180027877  call    cs:__imp_GetLastError
0x18002787d  mov     rcx, rdi; hMem
0x180027880  mov     ebx, eax
0x180027882  call    cs:__imp_LocalFree
0x180027888  mov     ecx, ebx; dwErrCode
0x18002788a  call    cs:__imp_SetLastError
0x180027890  mov     eax, r15d
0x180027893  add     rsp, 58h
0x180027897  pop     r15
0x180027899  pop     r14
0x18002789b  pop     r13
0x18002789d  pop     r12
0x18002789f  pop     rdi
0x1800278a0  pop     rsi
0x1800278a1  pop     rbx
0x1800278a2  pop     rbp
0x1800278a3  retn
0x1800278a4  mov     rsi, [rdi+18h]
0x1800278a8  lea     r14, CriticalSection
0x1800278af  mov     rcx, r14; lpCriticalSection
0x1800278b2  call    cs:__imp_EnterCriticalSection
0x1800278b8  mov     rbx, [rsi+18h]
0x1800278bc  mov     rdi, [rsi+8]
0x1800278c0  test    rbx, rbx
0x1800278c3  jz      loc_180027B5C
0x1800278c9  mov     rcx, rdi; struct _DLL_ELEMENT *
0x1800278cc  call    ?AddRefDll@@YAXPEAU_DLL_ELEMENT@@@Z; AddRefDll(_DLL_ELEMENT *)
0x1800278d1  mov     rcx, r14; lpCriticalSection
0x1800278d4  call    cs:__imp_LeaveCriticalSection
0x1800278da  mov     eax, r15d
0x1800278dd  test    eax, eax
0x1800278df  jnz     loc_1800277E0
0x1800278e5  mov     ecx, 2; dwErrCode
0x1800278ea  jmp     loc_180116C46
0x1800278ef  call    cs:__imp_GetLastError
0x1800278f5  mov     rcx, rdi; struct _DLL_ELEMENT *
0x1800278f8  mov     ebx, eax
0x1800278fa  call    ?ReleaseDll@@YAXPEAU_DLL_ELEMENT@@@Z; ReleaseDll(_DLL_ELEMENT *)
0x1800278ff  mov     ecx, ebx; dwErrCode
0x180027901  call    cs:__imp_SetLastError
0x180027907  xor     eax, eax
0x180027909  xor     edi, edi
0x18002790b  xor     ebx, ebx
0x18002790d  jmp     loc_18002771B
0x180027912  call    cs:__imp_GetLastError
0x180027918  mov     rcx, rdi; struct _DLL_ELEMENT *
0x18002791b  mov     ebx, eax
0x18002791d  call    ?ReleaseDll@@YAXPEAU_DLL_ELEMENT@@@Z; ReleaseDll(_DLL_ELEMENT *)
0x180027922  mov     ecx, ebx; dwErrCode
0x180027924  call    cs:__imp_SetLastError
0x18002792a  xor     eax, eax
0x18002792c  xor     edi, edi
0x18002792e  xor     ebx, ebx
0x180027930  jmp     short loc_1800278DD
0x180027932  cmp     byte ptr [rbx], 23h ; '#'
0x180027935  jnz     loc_180027610
0x18002793b  lea     rcx, [rbx+1]; String
0x18002793f  call    _o_atol_0
0x180027944  movsxd  rbx, eax
0x180027947  cmp     rbx, rdi
0x18002794a  jbe     loc_180027610
0x180027950  mov     ecx, 80070057h; dwErrCode
0x180027955  call    cs:__imp_SetLastError
0x18002795b  jmp     loc_180027733
0x180027960  cmp     byte ptr [rbx], 23h ; '#'
0x180027963  jnz     loc_180027757
0x180027969  lea     rcx, [rbx+1]; String
0x18002796d  call    _o_atol_0
0x180027972  movsxd  rbx, eax
0x180027975  cmp     rbx, rdi
0x180027978  jbe     loc_180027757
0x18002797e  mov     ecx, 80070057h
0x180027983  jmp     loc_180116C46
0x180027988  mov     rdi, [rsi+20h]
0x18002798c  test    rdi, rdi
0x18002798f  jz      loc_1800276A4
0x180027995  cmp     r14d, [rdi+4]
0x180027999  jnz     short loc_1800279C4
0x18002799b  mov     rax, [rdi+10h]
0x18002799f  or      ecx, 0FFFFFFFFh
0x1800279a2  mov     dword ptr [rsp+58h+var_30], ecx; cchCount2
0x1800279a6  mov     r9d, ecx; cchCount1
0x1800279a9  mov     ecx, 409h; Locale
0x1800279ae  mov     qword ptr [rsp+58h+var_38], rax; lpString2
0x1800279b3  mov     r8, rbx; lpString1
0x1800279b6  mov     edx, r15d; dwCmpFlags
0x1800279b9  call    cs:__imp_CompareStringA
0x1800279bf  cmp     eax, 2
0x1800279c2  jz      short loc_180027A0C
0x1800279c4  mov     rdi, [rdi+8]
0x1800279c8  jmp     short loc_18002798C
0x1800279ca  mov     rdi, [rsi+20h]
0x1800279ce  test    rdi, rdi
0x1800279d1  jz      loc_180027798
0x1800279d7  cmp     r14d, [rdi+4]
0x1800279db  jnz     short loc_180027A06
0x1800279dd  mov     rax, [rdi+10h]
0x1800279e1  or      ecx, 0FFFFFFFFh
0x1800279e4  mov     dword ptr [rsp+58h+var_30], ecx; cchCount2
0x1800279e8  mov     r9d, ecx; cchCount1
0x1800279eb  mov     ecx, 409h; Locale
0x1800279f0  mov     qword ptr [rsp+58h+var_38], rax; lpString2
0x1800279f5  mov     r8, rbx; lpString1
0x1800279f8  mov     edx, r15d; dwCmpFlags
0x1800279fb  call    cs:__imp_CompareStringA
0x180027a01  cmp     eax, 2
0x180027a04  jz      short loc_180027A46
0x180027a06  mov     rdi, [rdi+8]
0x180027a0a  jmp     short loc_1800279CE
0x180027a0c  mov     rbx, [rdi+20h]
0x180027a10  jmp     loc_180027663
0x180027a15  cmp     rax, rsi
0x180027a18  jbe     loc_1800276D2
0x180027a1e  or      ecx, 0FFFFFFFFh
0x180027a21  mov     r8, rbx; lpString1
0x180027a24  mov     dword ptr [rsp+58h+var_30], ecx; cchCount2
0x180027a28  mov     r9d, ecx; cchCount1
0x180027a2b  mov     ecx, 409h; Locale
0x180027a30  mov     qword ptr [rsp+58h+var_38], rax; lpString2
0x180027a35  mov     edx, r15d; dwCmpFlags
  ... truncated ...
```
