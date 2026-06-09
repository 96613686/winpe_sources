# CryptImportPublicKeyInfo

- ea: `0x1800288b0`
- end: `0x180028d4e`
- name: `CryptImportPublicKeyInfo`
- size: `1182`
- prototype: `BOOL __stdcall(HCRYPTPROV hCryptProv, DWORD dwCertEncodingType, PCERT_PUBLIC_KEY_INFO pInfo, HCRYPTKEY *phKey)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006980`
- `0x180009da0`
- `0x180012d00`
- `0x180027ba8`
- `0x1800286e0`
- `0x1800288b0`
- `0x180028d60`
- `0x180029494`
- `0x180029500`
- `0x1800b1e60`
- `0x1800bf564`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028af1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028af1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800289ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028b03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180116cc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800289ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028b03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180116cc2`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180028c09`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180028c4b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180028c88`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180028cc5`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180028c09`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180028c4b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180028c88`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180028cc5`
- `CRYPTSP!CryptImportKey` at `0x180028b31`
- `CRYPTSP!CryptImportKey` at `0x180028b31`

## pseudocode

```c
BOOL __stdcall CryptImportPublicKeyInfo(
        HCRYPTPROV hCryptProv,
        DWORD dwCertEncodingType,
        PCERT_PUBLIC_KEY_INFO pInfo,
        HCRYPTKEY *phKey)
{
  LPSTR pszObjId; // rdi
  struct _FUNC_SET *v5; // rsi
  DWORD v7; // r14d
  int v9; // r15d
  struct _REG_OID_FUNC_ELEMENT *v10; // rcx
  void *i; // rbx
  void *v12; // rax
  __int64 v13; // rbx
  const CHAR *v14; // rax
  bool v15; // zf
  DWORD v16; // ecx
  LPSTR v17; // rbx
  struct _FUNC_SET *v18; // rsi
  struct _REG_OID_FUNC_ELEMENT *v19; // rcx
  void *j; // rdi
  __int64 v21; // rdi
  const CHAR *v22; // rax
  bool v23; // zf
  int v24; // eax
  int v25; // esi
  DWORD LastError; // ebx
  HCRYPTKEY *v27; // rdi
  DWORD v29; // ecx
  PCCRYPT_OID_INFO OIDInfo; // rax
  int v31; // eax
  void *v32; // [rsp+40h] [rbp-18h] BYREF
  void *v33[2]; // [rsp+48h] [rbp-10h] BYREF
  DWORD dwDataLen; // [rsp+A8h] [rbp+50h] BYREF
  BYTE *pbData; // [rsp+B0h] [rbp+58h] BYREF
  HCRYPTKEY *v37; // [rsp+B8h] [rbp+60h]

  v37 = phKey;
  pszObjId = pInfo->Algorithm.pszObjId;
  v5 = pvArg;
  v7 = (unsigned __int16)dwCertEncodingType;
  v32 = 0;
  v33[0] = 0;
  v9 = 1;
  if ( !(_WORD)dwCertEncodingType )
    v7 = HIWORD(dwCertEncodingType);
  pbData = 0;
  dwDataLen = 0;
  if ( (unsigned __int64)pszObjId > 0xFFFF && *pszObjId == 35 )
  {
    pszObjId = (LPSTR)o_atol_0(pszObjId + 1);
    if ( (unsigned __int64)pszObjId > 0xFFFF )
    {
      v16 = -2147024809;
      goto LABEL_24;
    }
  }
  if ( !*((_DWORD *)v5 + 12) )
    LoadRegFunc((LPCSTR *)v5);
  v10 = (struct _REG_OID_FUNC_ELEMENT *)*((_QWORD *)v5 + 7);
  if ( v10 && GetRegOIDFunctionAddress(v10, v7, pszObjId, &v32, v33) )
    goto LABEL_76;
  if ( (unsigned __int64)pszObjId <= 0xFFFF )
  {
    for ( i = (void *)*((_QWORD *)v5 + 2); ; i = (void *)*((_QWORD *)i + 1) )
    {
      if ( !i )
        goto LABEL_15;
      if ( v7 == *((_DWORD *)i + 1)
        && (unsigned __int64)pszObjId >= *((_QWORD *)i + 2)
        && (unsigned __int64)pszObjId <= *((_QWORD *)i + 3) )
      {
        break;
      }
    }
    v12 = *(void **)(*((_QWORD *)i + 5) + 8LL * (_QWORD)&pszObjId[-*((_QWORD *)i + 2)]);
LABEL_14:
    v9 = ((__int64 (__fastcall *)(HCRYPTPROV, _QWORD, PCERT_PUBLIC_KEY_INFO, _QWORD, _DWORD, _QWORD, HCRYPTKEY *))v12)(
           hCryptProv,
           dwCertEncodingType,
           pInfo,
           0,
           0,
           0,
           v37);
    CryptFreeOIDFunctionAddress(i, 0);
    goto LABEL_49;
  }
  for ( i = (void *)*((_QWORD *)v5 + 4); i; i = (void *)*((_QWORD *)i + 1) )
  {
    if ( v7 == *((_DWORD *)i + 1) && CompareStringA(0x409u, 1u, pszObjId, -1, *((PCNZCH *)i + 2), -1) == 2 )
    {
      v12 = (void *)*((_QWORD *)i + 4);
      goto LABEL_14;
    }
  }
LABEL_15:
  v13 = *((_QWORD *)v5 + 8);
  if ( !v13 )
    goto LABEL_23;
  while ( 1 )
  {
    if ( !v13 )
      goto LABEL_23;
    if ( v7 == *(_DWORD *)v13 )
    {
      v14 = *(const CHAR **)(v13 + 16);
      if ( (unsigned __int64)pszObjId <= 0xFFFF )
      {
        v15 = pszObjId == v14;
        goto LABEL_20;
      }
      if ( (unsigned __int64)v14 > 0xFFFF )
        break;
    }
LABEL_21:
    v13 = *(_QWORD *)(v13 + 8);
  }
  v15 = CompareStringA(0x409u, 1u, pszObjId, -1, v14, -1) == 2;
LABEL_20:
  if ( !v15 )
    goto LABEL_21;
  if ( (unsigned int)GetDllProcAddr(*(struct _DLL_PROC_ELEMENT **)(v13 + 24), &v32, v33) )
  {
LABEL_76:
    v12 = v32;
    i = v33[0];
    goto LABEL_14;
  }
LABEL_23:
  v16 = 2;
LABEL_24:
  SetLastError(v16);
  v17 = pInfo->Algorithm.pszObjId;
  v18 = qword_180158340;
  v33[0] = 0;
  v32 = 0;
  if ( (unsigned __int64)v17 > 0xFFFF && *v17 == 35 )
  {
    v17 = (LPSTR)o_atol_0(v17 + 1);
    if ( (unsigned __int64)v17 > 0xFFFF )
    {
      v29 = -2147024809;
      goto LABEL_80;
    }
  }
  if ( !*((_DWORD *)v18 + 12) )
    LoadRegFunc((LPCSTR *)v18);
  v19 = (struct _REG_OID_FUNC_ELEMENT *)*((_QWORD *)v18 + 7);
  if ( v19 && GetRegOIDFunctionAddress(v19, v7, v17, v33, &v32) )
  {
LABEL_51:
    j = v32;
    v24 = ((__int64 (__fastcall *)(_QWORD, PCERT_PUBLIC_KEY_INFO, __int64, _QWORD, BYTE **, DWORD *))v33[0])(
            dwCertEncodingType,
            pInfo,
            0x8000,
            0,
            &pbData,
            &dwDataLen);
    goto LABEL_44;
  }
  if ( (unsigned __int64)v17 <= 0xFFFF )
  {
    for ( j = (void *)*((_QWORD *)v18 + 2); ; j = (void *)*((_QWORD *)j + 1) )
    {
      if ( !j )
        goto LABEL_35;
      if ( v7 == *((_DWORD *)j + 1)
        && (unsigned __int64)v17 >= *((_QWORD *)j + 2)
        && (unsigned __int64)v17 <= *((_QWORD *)j + 3) )
      {
        break;
      }
    }
    v24 = (*(__int64 (__fastcall **)(_QWORD, PCERT_PUBLIC_KEY_INFO, __int64, _QWORD, BYTE **, DWORD *))(*((_QWORD *)j + 5) + 8LL * (_QWORD)&v17[-*((_QWORD *)j + 2)]))(
            dwCertEncodingType,
            pInfo,
            0x8000,
            0,
            &pbData,
            &dwDataLen);
LABEL_44:
    v25 = v24;
    if ( j && *(_DWORD *)j == 3 )
    {
      LastError = GetLastError();
      ReleaseDll((struct _DLL_ELEMENT *)j);
      SetLastError(LastError);
    }
    goto LABEL_47;
  }
  for ( j = (void *)*((_QWORD *)v18 + 4); j; j = (void *)*((_QWORD *)j + 1) )
  {
    if ( v7 == *((_DWORD *)j + 1) && CompareStringA(0x409u, 1u, v17, -1, *((PCNZCH *)j + 2), -1) == 2 )
    {
      v24 = (*((__int64 (__fastcall **)(_QWORD, PCERT_PUBLIC_KEY_INFO, __int64, _QWORD, BYTE **, DWORD *))j + 4))(
              dwCertEncodingType,
              pInfo,
              0x8000,
              0,
              &pbData,
              &dwDataLen);
      goto LABEL_44;
    }
  }
LABEL_35:
  v21 = *((_QWORD *)v18 + 8);
  if ( v21 )
  {
    while ( v21 )
    {
      if ( v7 == *(_DWORD *)v21 )
      {
        v22 = *(const CHAR **)(v21 + 16);
        if ( (unsigned __int64)v17 > 0xFFFF )
        {
          if ( (unsigned __int64)v22 > 0xFFFF )
          {
            v23 = CompareStringA(0x409u, 1u, v17, -1, v22, -1) == 2;
            goto LABEL_40;
          }
        }
        else
        {
          v23 = v17 == v22;
LABEL_40:
          if ( v23 )
          {
            if ( !(unsigned int)GetDllProcAddr(*(struct _DLL_PROC_ELEMENT **)(v21 + 24), v33, &v32) )
              break;
            goto LABEL_51;
          }
        }
      }
      v21 = *(_QWORD *)(v21 + 8);
      continue;
    }
  }
  v29 = 2;
LABEL_80:
  SetLastError(v29);
  OIDInfo = CryptFindOIDInfo(1u, pInfo->Algorithm.pszObjId, 0x40000003u);
  if ( OIDInfo && OIDInfo->dwValue == 8704 )
    v31 = ConvertDSSPublicKeyInfo(dwCertEncodingType, (_DWORD)pInfo, 0x8000, 0, (__int64)&pbData, (__int64)&dwDataLen);
  else
    v31 = ConvertRSAPublicKeyInfo(dwCertEncodingType, (_DWORD)pInfo, 0x8000, 0, (__int64)&pbData, (__int64)&dwDataLen);
  v25 = v31;
LABEL_47:
  v27 = v37;
  if ( !v25 || !CryptImportKey(hCryptProv, pbData, dwDataLen, 0, 0, v37) )
  {
    *v27 = 0;
    v9 = 0;
  }
LABEL_49:
  PkiDefaultCryptFree(pbData);
  return v9;
}

```

## disassembly

```asm
0x1800288b0  mov     [rsp-40h+arg_18], r9
0x1800288b5  mov     [rsp-40h+hProv], rcx
0x1800288ba  push    rbp
0x1800288bb  push    rbx
0x1800288bc  push    rsi
0x1800288bd  push    rdi
0x1800288be  push    r12
0x1800288c0  push    r13
0x1800288c2  push    r14
0x1800288c4  push    r15
0x1800288c6  mov     rbp, rsp
0x1800288c9  sub     rsp, 58h
0x1800288cd  mov     rdi, [r8]
0x1800288d0  mov     eax, edx
0x1800288d2  mov     rsi, cs:pvArg
0x1800288d9  mov     ebx, 0FFFFh
0x1800288de  shr     eax, 10h
0x1800288e1  mov     r12, r8
0x1800288e4  movzx   r14d, dx
0x1800288e8  mov     r13d, edx
0x1800288eb  test    r14d, r14d
0x1800288ee  mov     [rbp+var_18], 0
0x1800288f6  mov     [rbp+var_10], 0
0x1800288fe  mov     r15d, 1
0x180028904  cmovz   r14d, eax
0x180028908  mov     [rbp+pbData], 0
0x180028910  mov     [rbp+dwDataLen], 0
0x180028917  cmp     rdi, rbx
0x18002891a  ja      loc_180028B88
0x180028920  cmp     dword ptr [rsi+30h], 0
0x180028924  jz      loc_180028CD3
0x18002892a  mov     rcx, [rsi+38h]; struct _REG_OID_FUNC_ELEMENT *
0x18002892e  test    rcx, rcx
0x180028931  jnz     loc_180028CED
0x180028937  cmp     rdi, rbx
0x18002893a  ja      loc_180028BD8
0x180028940  mov     rbx, [rsi+10h]
0x180028944  test    rbx, rbx
0x180028947  jz      short loc_1800289B1
0x180028949  cmp     r14d, [rbx+4]
0x18002894d  jnz     loc_180028AAA
0x180028953  cmp     rdi, [rbx+10h]
0x180028957  jb      loc_180028AAA
0x18002895d  cmp     rdi, [rbx+18h]
0x180028961  ja      loc_180028AAA
0x180028967  sub     rdi, [rbx+10h]
0x18002896b  mov     rax, [rbx+28h]
0x18002896f  mov     rax, [rax+rdi*8]
0x180028973  mov     rdi, [rbp+arg_18]
0x180028977  xor     r9d, r9d
0x18002897a  mov     rcx, [rbp+hProv]
0x18002897e  mov     r8, r12
0x180028981  mov     [rsp+58h+var_28], rdi
0x180028986  mov     edx, r13d
0x180028989  mov     [rsp+58h+phKey], 0
0x180028992  mov     [rsp+58h+dwFlags], 0
0x18002899a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002899f  xor     edx, edx; dwFlags
0x1800289a1  mov     rcx, rbx; hFuncAddr
0x1800289a4  mov     r15d, eax
0x1800289a7  call    CryptFreeOIDFunctionAddress
0x1800289ac  jmp     loc_180028B3F
0x1800289b1  mov     rbx, [rsi+40h]
0x1800289b5  test    rbx, rbx
0x1800289b8  jz      short loc_1800289FA
0x1800289ba  test    rbx, rbx
0x1800289bd  jz      short loc_1800289FA
0x1800289bf  cmp     r14d, [rbx]
0x1800289c2  jnz     short loc_1800289DB
0x1800289c4  mov     rax, [rbx+10h]
0x1800289c8  mov     ecx, 0FFFFh
0x1800289cd  cmp     rdi, rcx
0x1800289d0  ja      loc_180028C65
0x1800289d6  cmp     rdi, rax
0x1800289d9  jz      short loc_1800289E1
0x1800289db  mov     rbx, [rbx+8]
0x1800289df  jmp     short loc_1800289BA
0x1800289e1  mov     rcx, [rbx+18h]; struct _DLL_PROC_ELEMENT *
0x1800289e5  lea     r8, [rbp+var_10]; void **
0x1800289e9  lea     rdx, [rbp+var_18]; void **
0x1800289ed  call    ?GetDllProcAddr@@YAHPEAU_DLL_PROC_ELEMENT@@PEAPEAX1@Z; GetDllProcAddr(_DLL_PROC_ELEMENT *,void * *,void * *)
0x1800289f2  test    eax, eax
0x1800289f4  jnz     loc_180028D0D
0x1800289fa  mov     ecx, 2; dwErrCode
0x1800289ff  call    cs:__imp_SetLastError
0x180028a05  mov     rbx, [r12]
0x180028a09  mov     edi, 0FFFFh
0x180028a0e  mov     rsi, cs:qword_180158340
0x180028a15  mov     [rbp+var_10], 0
0x180028a1d  mov     [rbp+var_18], 0
0x180028a25  cmp     rbx, rdi
0x180028a28  ja      loc_180028BB0
0x180028a2e  cmp     dword ptr [rsi+30h], 0
0x180028a32  jz      loc_180028CE0
0x180028a38  mov     rcx, [rsi+38h]; struct _REG_OID_FUNC_ELEMENT *
0x180028a3c  test    rcx, rcx
0x180028a3f  jnz     loc_180028D1A
0x180028a45  cmp     rbx, rdi
0x180028a48  ja      loc_180028C1A
0x180028a4e  mov     rdi, [rsi+10h]
0x180028a52  test    rdi, rdi
0x180028a55  jz      short loc_180028A6F
0x180028a57  cmp     r14d, [rdi+4]
0x180028a5b  jnz     short loc_180028A69
0x180028a5d  cmp     rbx, [rdi+10h]
0x180028a61  jb      short loc_180028A69
0x180028a63  cmp     rbx, [rdi+18h]
0x180028a67  jbe     short loc_180028AB3
0x180028a69  mov     rdi, [rdi+8]
0x180028a6d  jmp     short loc_180028A52
0x180028a6f  mov     rdi, [rsi+40h]
0x180028a73  test    rdi, rdi
0x180028a76  jz      loc_180028B7E
0x180028a7c  test    rdi, rdi
0x180028a7f  jz      loc_180028B7E
0x180028a85  cmp     r14d, [rdi]
0x180028a88  jnz     short loc_180028AA4
0x180028a8a  mov     rax, [rdi+10h]
0x180028a8e  cmp     rbx, 0FFFFh
0x180028a95  ja      loc_180028C9F
0x180028a9b  cmp     rbx, rax
0x180028a9e  jz      loc_180028B5C
0x180028aa4  mov     rdi, [rdi+8]
0x180028aa8  jmp     short loc_180028A7C
0x180028aaa  mov     rbx, [rbx+8]
0x180028aae  jmp     loc_180028944
0x180028ab3  sub     rbx, [rdi+10h]
0x180028ab7  mov     rax, [rdi+28h]
0x180028abb  mov     rax, [rax+rbx*8]
0x180028abf  lea     rcx, [rbp+dwDataLen]
0x180028ac3  xor     r9d, r9d
0x180028ac6  mov     [rsp+58h+phKey], rcx
0x180028acb  mov     r8d, 8000h
0x180028ad1  lea     rcx, [rbp+pbData]
0x180028ad5  mov     rdx, r12
0x180028ad8  mov     qword ptr [rsp+58h+dwFlags], rcx
0x180028add  mov     ecx, r13d
0x180028ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ae5  mov     esi, eax
0x180028ae7  test    rdi, rdi
0x180028aea  jz      short loc_180028B09
0x180028aec  cmp     dword ptr [rdi], 3
0x180028aef  jnz     short loc_180028B09
0x180028af1  call    cs:__imp_GetLastError
0x180028af7  mov     rcx, rdi; struct _DLL_ELEMENT *
0x180028afa  mov     ebx, eax
0x180028afc  call    ?ReleaseDll@@YAXPEAU_DLL_ELEMENT@@@Z; ReleaseDll(_DLL_ELEMENT *)
0x180028b01  mov     ecx, ebx; dwErrCode
0x180028b03  call    cs:__imp_SetLastError
0x180028b09  mov     rdi, [rbp+arg_18]
0x180028b0d  test    esi, esi
0x180028b0f  jz      loc_180028D3F
0x180028b15  mov     r8d, [rbp+dwDataLen]; dwDataLen
0x180028b19  xor     r9d, r9d; hPubKey
0x180028b1c  mov     rdx, [rbp+pbData]; pbData
0x180028b20  mov     rcx, [rbp+hProv]; hProv
0x180028b24  mov     [rsp+58h+phKey], rdi; phKey
0x180028b29  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180028b31  call    cs:__imp_CryptImportKey
0x180028b37  test    eax, eax
0x180028b39  jz      loc_180028D3F
0x180028b3f  mov     rcx, [rbp+pbData]; hMem
0x180028b43  call    PkiDefaultCryptFree
0x180028b48  mov     eax, r15d
0x180028b4b  add     rsp, 58h
0x180028b4f  pop     r15
0x180028b51  pop     r14
0x180028b53  pop     r13
0x180028b55  pop     r12
0x180028b57  pop     rdi
0x180028b58  pop     rsi
0x180028b59  pop     rbx
0x180028b5a  pop     rbp
0x180028b5b  retn
0x180028b5c  mov     rcx, [rdi+18h]; struct _DLL_PROC_ELEMENT *
0x180028b60  lea     r8, [rbp+var_18]; void **
0x180028b64  lea     rdx, [rbp+var_10]; void **
0x180028b68  call    ?GetDllProcAddr@@YAHPEAU_DLL_PROC_ELEMENT@@PEAPEAX1@Z; GetDllProcAddr(_DLL_PROC_ELEMENT *,void * *,void * *)
0x180028b6d  test    eax, eax
0x180028b6f  jz      short loc_180028B7E
0x180028b71  mov     rax, [rbp+var_10]
0x180028b75  mov     rdi, [rbp+var_18]
0x180028b79  jmp     loc_180028ABF
0x180028b7e  mov     ecx, 2; dwErrCode
0x180028b83  jmp     loc_180116CC2
0x180028b88  cmp     byte ptr [rdi], 23h ; '#'
0x180028b8b  jnz     loc_180028920
0x180028b91  lea     rcx, [rdi+1]; String
0x180028b95  call    _o_atol_0
0x180028b9a  movsxd  rdi, eax
0x180028b9d  cmp     rdi, rbx
0x180028ba0  jbe     loc_180028920
0x180028ba6  mov     ecx, 80070057h
0x180028bab  jmp     loc_1800289FF
0x180028bb0  cmp     byte ptr [rbx], 23h ; '#'
0x180028bb3  jnz     loc_180028A2E
0x180028bb9  lea     rcx, [rbx+1]; String
0x180028bbd  call    _o_atol_0
0x180028bc2  movsxd  rbx, eax
0x180028bc5  cmp     rbx, rdi
0x180028bc8  jbe     loc_180028A2E
0x180028bce  mov     ecx, 80070057h
0x180028bd3  jmp     loc_180116CC2
0x180028bd8  mov     rbx, [rsi+20h]
0x180028bdc  test    rbx, rbx
0x180028bdf  jz      loc_1800289B1
0x180028be5  cmp     r14d, [rbx+4]
0x180028be9  jnz     short loc_180028C14
0x180028beb  mov     rax, [rbx+10h]
0x180028bef  or      ecx, 0FFFFFFFFh
0x180028bf2  mov     dword ptr [rsp+58h+phKey], ecx; cchCount2
0x180028bf6  mov     r9d, ecx; cchCount1
0x180028bf9  mov     ecx, 409h; Locale
0x180028bfe  mov     qword ptr [rsp+58h+dwFlags], rax; lpString2
0x180028c03  mov     r8, rdi; lpString1
0x180028c06  mov     edx, r15d; dwCmpFlags
0x180028c09  call    cs:__imp_CompareStringA
0x180028c0f  cmp     eax, 2
0x180028c12  jz      short loc_180028C5C
0x180028c14  mov     rbx, [rbx+8]
0x180028c18  jmp     short loc_180028BDC
0x180028c1a  mov     rdi, [rsi+20h]
0x180028c1e  test    rdi, rdi
0x180028c21  jz      loc_180028A6F
0x180028c27  cmp     r14d, [rdi+4]
0x180028c2b  jnz     short loc_180028C56
0x180028c2d  mov     rax, [rdi+10h]
0x180028c31  or      ecx, 0FFFFFFFFh
0x180028c34  mov     dword ptr [rsp+58h+phKey], ecx; cchCount2
0x180028c38  mov     r9d, ecx; cchCount1
0x180028c3b  mov     ecx, 409h; Locale
0x180028c40  mov     qword ptr [rsp+58h+dwFlags], rax; lpString2
0x180028c45  mov     r8, rbx; lpString1
0x180028c48  mov     edx, r15d; dwCmpFlags
0x180028c4b  call    cs:__imp_CompareStringA
0x180028c51  cmp     eax, 2
0x180028c54  jz      short loc_180028C96
0x180028c56  mov     rdi, [rdi+8]
0x180028c5a  jmp     short loc_180028C1E
0x180028c5c  mov     rax, [rbx+20h]
0x180028c60  jmp     loc_180028973
0x180028c65  cmp     rax, rcx
0x180028c68  jbe     loc_1800289DB
0x180028c6e  or      ecx, 0FFFFFFFFh
0x180028c71  mov     r8, rdi; lpString1
0x180028c74  mov     dword ptr [rsp+58h+phKey], ecx; cchCount2
0x180028c78  mov     r9d, ecx; cchCount1
0x180028c7b  mov     ecx, 409h; Locale
0x180028c80  mov     qword ptr [rsp+58h+dwFlags], rax; lpString2
0x180028c85  mov     edx, r15d; dwCmpFlags
0x180028c88  call    cs:__imp_CompareStringA
0x180028c8e  cmp     eax, 2
0x180028c91  jmp     loc_1800289D9
0x180028c96  mov     rax, [rdi+20h]
0x180028c9a  jmp     loc_180028ABF
0x180028c9f  cmp     rax, 0FFFFh
0x180028ca5  jbe     loc_180028AA4
0x180028cab  or      ecx, 0FFFFFFFFh
0x180028cae  mov     r8, rbx; lpString1
0x180028cb1  mov     dword ptr [rsp+58h+phKey], ecx; cchCount2
0x180028cb5  mov     r9d, ecx; cchCount1
0x180028cb8  mov     ecx, 409h; Locale
0x180028cbd  mov     qword ptr [rsp+58h+dwFlags], rax; lpString2
0x180028cc2  mov     edx, r15d; dwCmpFlags
0x180028cc5  call    cs:__imp_CompareStringA
0x180028ccb  cmp     eax, 2
0x180028cce  jmp     loc_180028A9E
0x180028cd3  mov     rcx, rsi; pvArg
0x180028cd6  call    ?LoadRegFunc@@YAXPEAU_FUNC_SET@@@Z; LoadRegFunc(_FUNC_SET *)
0x180028cdb  jmp     loc_18002892A
0x180028ce0  mov     rcx, rsi; pvArg
0x180028ce3  call    ?LoadRegFunc@@YAXPEAU_FUNC_SET@@@Z; LoadRegFunc(_FUNC_SET *)
0x180028ce8  jmp     loc_180028A38
0x180028ced  lea     rax, [rbp+var_10]
0x180028cf1  mov     r8, rdi; char *
0x180028cf4  lea     r9, [rbp+var_18]; void **
0x180028cf8  mov     qword ptr [rsp+58h+dwFlags], rax; void **
0x180028cfd  mov     edx, r14d; unsigned int
0x180028d00  call    ?GetRegOIDFunctionAddress@@YAHPEAU_REG_OID_FUNC_ELEMENT@@KPEBDPEAPEAX2@Z; GetRegOIDFunctionAddress(_REG_OID_FUNC_ELEMENT *,ulong,char const *,void * *,void * *)
0x180028d05  test    eax, eax
0x180028d07  jz      loc_180028937
0x180028d0d  mov     rax, [rbp+var_18]
0x180028d11  mov     rbx, [rbp+var_10]
0x180028d15  jmp     loc_180028973
0x180028d1a  lea     rax, [rbp+var_18]
0x180028d1e  mov     r8, rbx; char *
0x180028d21  lea     r9, [rbp+var_10]; void **
0x180028d25  mov     qword ptr [rsp+58h+dwFlags], rax; void **
0x180028d2a  mov     edx, r14d; unsigned int
0x180028d2d  call    ?GetRegOIDFunctionAddress@@YAHPEAU_REG_OID_FUNC_ELEMENT@@KPEBDPEAPEAX2@Z; GetRegOIDFunctionAddress(_REG_OID_FUNC_ELEMENT *,ulong,char const *,void * *,void * *)
0x180028d32  test    eax, eax
0x180028d34  jnz     loc_180028B71
0x180028d3a  jmp     loc_180028A45
0x180028d3f  mov     qword ptr [rdi], 0
0x180028d46  xor     r15d, r15d
0x180028d49  jmp     loc_180028B3F
0x180116cc2  call    cs:__imp_SetLastError
0x180116cc8  mov     rdx, [r12]; pvKey
0x180116ccc  mov     r8d, 40000003h; dwGroupId
0x180116cd2  mov     ecx, r15d; dwKeyType
  ... truncated ...
```
