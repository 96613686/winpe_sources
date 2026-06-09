# ScHelperEncryptCredentialsEX

- ea: `0x1800d78e0`
- end: `0x1800d827e`
- name: `ScHelperEncryptCredentialsEX`
- size: `2462`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, unsigned int, __int64, __int64, __int64, size_t, __int64, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bbb14`

## callees

- `0x180002ba4`
- `0x180004760`
- `0x180007e80`
- `0x180032964`
- `0x1800341e4`
- `0x180034328`
- `0x180034f04`
- `0x1800690cc`
- `0x18006fe20`
- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x1800d62a4`
- `0x1800d6508`
- `0x1800d6d24`
- `0x1800d6ec8`
- `0x1800d78e0`
- `0x1800dfed0`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7fcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d8196`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d8196`
- `ncrypt!NCryptOpenKey` at `0x1800d7c7f`
- `ncrypt!NCryptOpenKey` at `0x1800d7c7f`
- `ncrypt!NCryptFreeObject` at `0x1800d81d7`
- `ncrypt!NCryptFreeObject` at `0x1800d81d7`
- `ncrypt!NCryptGetProperty` at `0x1800d7a9e`
- `ncrypt!NCryptGetProperty` at `0x1800d7a9e`
- `CRYPTSP!CryptEncrypt` at `0x1800d7fc1`
- `CRYPTSP!CryptEncrypt` at `0x1800d8107`
- `CRYPTSP!CryptEncrypt` at `0x1800d7fc1`
- `CRYPTSP!CryptEncrypt` at `0x1800d8107`
- `CRYPTSP!CryptDestroyKey` at `0x1800d81b3`
- `CRYPTSP!CryptDestroyKey` at `0x1800d81c5`
- `CRYPTSP!CryptDestroyKey` at `0x1800d81b3`
- `CRYPTSP!CryptDestroyKey` at `0x1800d81c5`
- `cryptngc!NgcEncryptWithAsymmetricKey` at `0x1800d7d9b`
- `cryptngc!NgcEncryptWithAsymmetricKey` at `0x1800d7d9b`

## pseudocode

```c
__int64 __fastcall ScHelperEncryptCredentialsEX(
        NCRYPT_HANDLE a1,
        DWORD a2,
        NCRYPT_PROV_HANDLE a3,
        __int64 a4,
        struct _CRYPTOAPI_BLOB *a5,
        unsigned __int8 *a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        unsigned __int8 *a10,
        size_t a11,
        __int64 a12,
        unsigned int *a13)
{
  void *v13; // r15
  int v14; // esi
  unsigned __int8 *v15; // r13
  int IsNcryptRsaKey; // esi
  struct Kerb3961::EncryptionAlgorithm *v17; // r12
  NCRYPT_HANDLE v18; // rcx
  KerberosCryptoPolicy *v19; // rcx
  size_t v20; // r15
  unsigned int v21; // ecx
  unsigned int v22; // edx
  __int64 v23; // r10
  unsigned int v24; // ecx
  unsigned int v25; // r12d
  unsigned __int8 *v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rsi
  int v30; // eax
  struct _CRYPTOAPI_BLOB *v31; // rdi
  __int64 v32; // rbx
  __int64 cbData; // rdi
  void *v34; // rdx
  char *v35; // rbx
  unsigned __int8 *v36; // r12
  NCRYPT_PROV_HANDLE v37; // rbx
  unsigned int v38; // eax
  int v39; // eax
  int v40; // eax
  unsigned int v41; // eax
  void *v42; // rdx
  size_t v43; // r8
  __int64 v44; // rbx
  __int64 v45; // rax
  size_t v46; // r8
  char *v47; // rdi
  char *v48; // rbx
  __int64 v49; // rcx
  unsigned __int8 *v50; // r12
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  unsigned int v54; // ecx
  unsigned int v55; // eax
  BYTE *v56; // rdi
  unsigned __int64 v57; // rbx
  unsigned __int64 v58; // rcx
  __int64 v59; // rcx
  unsigned __int64 v60; // rcx
  void *v61; // rsp
  void *v62; // rsp
  BYTE *v63; // rax
  HLOCAL v64; // rdx
  __int64 v65; // rdx
  BOOL v66; // esi
  __int64 v67; // r8
  __int64 v68; // r9
  unsigned int *v69; // rbx
  unsigned __int64 v70; // rbx
  unsigned __int64 v71; // rcx
  __int64 v72; // rcx
  unsigned __int64 v73; // rcx
  void *v74; // rsp
  void *v75; // rsp
  BYTE *v76; // rax
  HLOCAL v77; // rdx
  unsigned __int8 *v78; // rdx
  size_t v79; // r8
  _BYTE v81[32]; // [rsp+0h] [rbp-60h] BYREF
  DWORD *pcbResult; // [rsp+20h] [rbp-40h]
  DWORD dwBufLen[2]; // [rsp+30h] [rbp-30h]
  unsigned int v84; // [rsp+60h] [rbp+0h] BYREF
  void *v85; // [rsp+68h] [rbp+8h] BYREF
  size_t v86; // [rsp+70h] [rbp+10h] BYREF
  DWORD v87; // [rsp+78h] [rbp+18h] BYREF
  DWORD pdwDataLen; // [rsp+7Ch] [rbp+1Ch] BYREF
  int v89; // [rsp+80h] [rbp+20h] BYREF
  unsigned int v90; // [rsp+84h] [rbp+24h] BYREF
  size_t Size; // [rsp+88h] [rbp+28h] BYREF
  DWORD dwKeySpec; // [rsp+90h] [rbp+30h]
  __int64 v93; // [rsp+98h] [rbp+38h]
  unsigned __int8 *v94; // [rsp+A0h] [rbp+40h]
  unsigned __int8 *v95; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int *v96; // [rsp+B0h] [rbp+50h]
  HLOCAL hMem; // [rsp+B8h] [rbp+58h] BYREF
  HCRYPTKEY hKey; // [rsp+C0h] [rbp+60h] BYREF
  __int64 v99; // [rsp+C8h] [rbp+68h] BYREF
  void *Src; // [rsp+D0h] [rbp+70h]
  struct _CRYPTOAPI_BLOB *v101; // [rsp+D8h] [rbp+78h]
  NCRYPT_HANDLE hObject; // [rsp+E0h] [rbp+80h]
  unsigned __int8 *v103; // [rsp+E8h] [rbp+88h]
  HCRYPTKEY v104; // [rsp+F0h] [rbp+90h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+F8h] [rbp+98h] BYREF
  void *v106; // [rsp+100h] [rbp+A0h] BYREF
  void *v107; // [rsp+108h] [rbp+A8h] BYREF
  NCRYPT_PROV_HANDLE hProvider; // [rsp+110h] [rbp+B0h]
  __int64 v109; // [rsp+118h] [rbp+B8h]
  unsigned __int8 *v110; // [rsp+120h] [rbp+C0h]
  __int64 *v111; // [rsp+128h] [rbp+C8h] BYREF
  BYTE pbOutput[528]; // [rsp+130h] [rbp+D0h] BYREF

  v13 = 0;
  v101 = a5;
  hObject = a1;
  v93 = a8;
  hProvider = a3;
  dwKeySpec = a2;
  v94 = a6;
  v103 = a10;
  v110 = (unsigned __int8 *)a9;
  v96 = a13;
  v104 = 0;
  hKey = 0;
  hMem = 0;
  v86 = 0x20800000000LL;
  v87 = 0;
  pdwDataLen = 0;
  v99 = 0;
  v84 = 0;
  memset_0(pbOutput, 0, 0x20Au);
  v14 = 1;
  v15 = 0;
  v89 = 1;
  phKey = 0;
  v107 = 0;
  v95 = 0;
  v90 = 0;
  v106 = 0;
  Size = 0;
  v85 = 0;
  KerberosCryptoPolicy::Create(&v111);
  if ( !v111 )
  {
    IsNcryptRsaKey = -1073741670;
    goto LABEL_95;
  }
  v109 = KerberosCryptoPolicy::SelectEncryptionAlgorithm(v111, 13);
  v17 = (struct Kerb3961::EncryptionAlgorithm *)v109;
  if ( !v109 )
  {
    IsNcryptRsaKey = -1073741059;
    goto LABEL_95;
  }
  v18 = hObject;
  if ( !hObject )
    goto LABEL_6;
  if ( ((dwKeySpec + 1) & 0xFFFFFFFE) == 0 )
  {
    IsNcryptRsaKey = ScHelperIsNcryptRsaKey(1, (void *)hObject, &v89);
    if ( IsNcryptRsaKey < 0 )
      goto LABEL_95;
    v14 = v89;
    v18 = hObject;
  }
  if ( v14 )
  {
    v26 = v94;
    Src = 0;
    if ( v94 && a7 )
    {
      v84 = 0;
      IsNcryptRsaKey = ScHelperGetNGCEncryptedAESKeySize(v94, a7, &v84);
      if ( IsNcryptRsaKey < 0 )
        goto LABEL_95;
      v20 = (unsigned int)a11;
      v14 = v89;
      v25 = a11 + v84 + 56;
      v26 = v94;
    }
    else
    {
      v20 = (unsigned int)a11;
      v25 = a11 + 88;
    }
    v23 = v93;
    goto LABEL_28;
  }
  if ( !hProvider )
  {
LABEL_6:
    IsNcryptRsaKey = -1073741023;
    goto LABEL_95;
  }
  IsNcryptRsaKey = NCryptGetProperty(v18, L"SmartCardAssociatedECDHKey", pbOutput, HIDWORD(v86), (DWORD *)&v86 + 1, 0);
  if ( IsNcryptRsaKey >= 0 )
  {
    v20 = (unsigned int)a11;
    if ( (unsigned int)a11 > 0xFFFF || !KerberosCryptoPolicy::GetEncryptedSize(v19, v17, a11, &v84) )
    {
      IsNcryptRsaKey = -1073741637;
      goto LABEL_94;
    }
    v21 = v84 + 84;
    if ( v84 + 84 < v84
      || (v22 = v21 + v101->cbData, v22 < v21)
      || (v23 = v93, v24 = v22 + *(_DWORD *)(v93 + 16), v24 < v22)
      || (v25 = v24 + HIDWORD(v86), v24 + HIDWORD(v86) < v24) )
    {
      IsNcryptRsaKey = -1073741675;
      goto LABEL_94;
    }
    v14 = v89;
    v26 = v94;
    Src = pbOutput;
LABEL_28:
    v84 = v25;
    if ( !a12 || *a13 < v25 )
    {
      *a13 = v25;
      IsNcryptRsaKey = -1073741789;
      goto LABEL_94;
    }
    if ( !v14 )
    {
      *(_DWORD *)a12 = 0;
      v27 = a12 + 8;
      *(_DWORD *)(a12 + 4) = *(_DWORD *)(v23 + 16);
      memcpy_0((void *)(a12 + 8), *(const void **)(v23 + 8), *(unsigned int *)(v23 + 16));
      v28 = v109;
      v29 = *(unsigned int *)(v93 + 16);
      *(_OWORD *)(v29 + v27) = *(_OWORD *)a9;
      *(_OWORD *)(v29 + v27 + 16) = *(_OWORD *)(a9 + 16);
      *(_OWORD *)(v29 + v27 + 32) = *(_OWORD *)(a9 + 32);
      *(_OWORD *)(v29 + v27 + 48) = *(_OWORD *)(a9 + 48);
      v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 216LL))(v28);
      v31 = v101;
      *(_DWORD *)(v29 + v27 + 64) = v30;
      *(_DWORD *)(v29 + v27 + 68) = v31->cbData;
      v32 = v29 + a12 + 8;
      memcpy_0((void *)(v32 + 72), v31->pbData, v31->cbData);
      cbData = v31->cbData;
      v34 = Src;
      *(_DWORD *)(cbData + v32 + 72) = HIDWORD(v86);
      v35 = (char *)(cbData + v32 + 76);
      memcpy_0(v35, v34, HIDWORD(v86));
      v36 = (unsigned __int8 *)&v35[HIDWORD(v86)];
      v37 = hProvider;
      v84 = v84 - cbData - v29 - HIDWORD(v86) - 84;
      IsNcryptRsaKey = NCryptOpenKey(hProvider, &phKey, (LPCWSTR)Src, 0, 0x40u);
      if ( IsNcryptRsaKey >= 0 )
      {
        v38 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v109 + 216LL))(v109);
        v39 = KerbEncryptCreds(
                v37,
                phKey,
                v101,
                v38,
                (unsigned int)pcbResult,
                v110,
                dwBufLen[0],
                v110 + 32,
                v20,
                v103,
                &v84,
                v36);
        v13 = v85;
        IsNcryptRsaKey = v39;
        if ( v39 >= 0 )
          *v96 = v84 + (_DWORD)v36 - a12;
        goto LABEL_95;
      }
LABEL_94:
      v13 = v85;
      goto LABEL_95;
    }
    if ( v26 && a7 )
    {
      IsNcryptRsaKey = ScHelperCreateCredKeysAES(&v107, &v95, &v90);
      if ( IsNcryptRsaKey < 0 )
      {
        v15 = v95;
        goto LABEL_94;
      }
      v40 = ScHelperEncryptAES(&v107, (unsigned int)v20, v103, (char *)&Size + 4, &v85);
      v15 = v95;
      IsNcryptRsaKey = v40;
      if ( v40 < 0 )
        goto LABEL_94;
      IsNcryptRsaKey = (unsigned __int16)NgcEncryptWithAsymmetricKey(v94, a7, v95, v90, &v106, &Size);
      if ( IsNcryptRsaKey )
        IsNcryptRsaKey |= 0xC0070000;
      if ( IsNcryptRsaKey < 0 )
        goto LABEL_94;
      *(_QWORD *)a12 = 0;
      *(_DWORD *)(a12 + 8) = 1;
      *(_DWORD *)(a12 + 12) = 2;
      v41 = Size;
      v42 = v106;
      v43 = (unsigned int)Size;
      *(_DWORD *)(a12 + 16) = Size;
      v44 = v41;
      memcpy_0((void *)(a12 + 20), v42, v43);
      v45 = HIDWORD(Size);
      v13 = v85;
      v46 = HIDWORD(Size);
      *(_DWORD *)(a12 + 20 + v44) = HIDWORD(Size);
      v47 = (char *)(v44 + 4 + a12 + 20);
      v48 = &v47[v45];
      memcpy_0(v47, v13, v46);
      if ( v48 != (char *)(a12 + v25) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v49);
      *v96 = (_DWORD)v48 - a12;
      goto LABEL_91;
    }
    IsNcryptRsaKey = ScHelperCreateCredKeys(
                       (void *)hObject,
                       dwKeySpec,
                       v23,
                       (UCHAR *)a9,
                       0,
                       &v104,
                       &hKey,
                       (HCRYPTPROV *)&v99);
    if ( IsNcryptRsaKey < 0 )
      goto LABEL_94;
    v50 = v103;
    IsNcryptRsaKey = ScHelperCreateCredHMAC(v99, v104, v103, (unsigned int)v20, &hMem, &v86);
    if ( IsNcryptRsaKey < 0 )
    {
LABEL_90:
      v13 = v85;
LABEL_91:
      if ( hMem )
        LocalFree(hMem);
      goto LABEL_95;
    }
    v54 = v86 + v20;
    if ( (int)v86 + (int)v20 < (unsigned int)v86 || (v55 = v54 + 4, v54 + 4 < v54) )
    {
      IsNcryptRsaKey = -1073741675;
      v87 = -1;
      goto LABEL_90;
    }
    v56 = 0;
    v87 = v54 + 4;
    v57 = v55;
    if ( v54 == -4 )
      goto LABEL_113;
    if ( v55 > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_113;
    v58 = v55 + g_ulAdditionalProbeSize + 8;
    if ( v58 < v55 || !(unsigned int)VerifyStackAvailable(v58, v51, v52, v53) )
      goto LABEL_113;
    v59 = v57 + 23;
    if ( v57 + 23 <= v57 + 8 )
      v59 = 0xFFFFFFFFFFFFFF0LL;
    v60 = v59 & 0xFFFFFFFFFFFFFFF0uLL;
    v61 = alloca(v60);
    v62 = alloca(v60);
    v56 = (BYTE *)&v84;
    if ( v81 == (_BYTE *)-96LL || (v84 = 1801679955, (v56 = (BYTE *)&v85) == 0) )
    {
LABEL_113:
      if ( v57 + 8 >= v57 )
      {
        v63 = (BYTE *)((__int64 (*)(void))g_pfnAllocate)();
        v56 = v63;
        if ( v63 )
        {
          *(_DWORD *)v63 = 1885431112;
          v56 = v63 + 8;
        }
      }
    }
    if ( !v56 )
    {
LABEL_61:
      IsNcryptRsaKey = -1073741670;
      goto LABEL_90;
    }
    v64 = hMem;
    *(_DWORD *)v56 = v86;
    memcpy_0(v56 + 4, v64, (unsigned int)v86);
    memcpy_0(&v56[(unsigned int)v86 + 4], v50, v20);
    pdwDataLen = v87;
    v66 = CryptEncrypt(hKey, 0, 1, 0, v56, &pdwDataLen, v87);
    if ( !v66 && GetLastError() != 234 )
      goto LABEL_64;
    v69 = v96;
    if ( *v96 && *v96 >= (unsigned __int64)pdwDataLen + 64 )
    {
      if ( !v66 )
      {
        if ( *((_DWORD *)v56 - 2) == 1885431112 )
          ((void (*)(void))g_pfnFree)();
        v70 = v87;
        v56 = 0;
        if ( !v87 )
          goto LABEL_114;
        if ( v87 > (unsigned __int64)g_ulMaxStackAllocSize )
          goto LABEL_114;
        v71 = v87 + g_ulAdditionalProbeSize + 8;
        if ( v71 < v87 || !(unsigned int)VerifyStackAvailable(v71, v65, v67, v68) )
          goto LABEL_114;
        v72 = v70 + 23;
        if ( v70 + 23 <= v70 + 8 )
          v72 = 0xFFFFFFFFFFFFFF0LL;
        v73 = v72 & 0xFFFFFFFFFFFFFFF0uLL;
        v74 = alloca(v73);
        v75 = alloca(v73);
        v56 = (BYTE *)&v84;
        if ( v81 == (_BYTE *)-96LL || (v84 = 1801679955, (v56 = (BYTE *)&v85) == 0) )
        {
LABEL_114:
          if ( v70 + 8 >= v70 )
          {
            v76 = (BYTE *)((__int64 (*)(void))g_pfnAllocate)();
            v56 = v76;
            if ( v76 )
            {
              *(_DWORD *)v76 = 1885431112;
              v56 = v76 + 8;
            }
          }
        }
        if ( !v56 )
          goto LABEL_61;
        v77 = hMem;
        *(_DWORD *)v56 = v86;
        memcpy_0(v56 + 4, v77, (unsigned int)v86);
        memcpy_0(&v56[(unsigned int)v86 + 4], v50, v20);
        if ( !CryptEncrypt(hKey, 0, 1, 0, v56, &v87, pdwDataLen) )
        {
LABEL_64:
          IsNcryptRsaKey = -1073741023;
          goto LABEL_87;
        }
        v69 = v96;
      }
      v78 = v110;
      v79 = v87;
      *(_OWORD *)a12 = *(_OWORD *)v110;
      *(_OWORD *)(a12 + 16) = *((_OWORD *)v78 + 1);
      *(_OWORD *)(a12 + 32) = *((_OWORD *)v78 + 2);
      *(_OWORD *)(a12 + 48) = *((_OWORD *)v78 + 3);
      memcpy_0((void *)(a12 + 64), v56, v79);
      IsNcryptRsaKey = 0;
    }
    else
    {
      IsNcryptRsaKey = -1073741789;
    }
    *v69 = pdwDataLen + 64;
LABEL_87:
    if ( *((_DWORD *)v56 - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    goto LABEL_90;
  }
LABEL_95:
  if ( hKey )
    CryptDestroyKey(hKey);
  if ( v104 )
    CryptDestroyKey(v104);
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( v15 && *((_DWORD *)v15 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v106 && *((_DWORD *)v106 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v13 && *((_DWORD *)v13 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v111);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v107);
  return (unsigned int)IsNcryptRsaKey;
}

```

## disassembly

```asm
0x1800d78e0  push    rbp
0x1800d78e2  push    rsi
0x1800d78e3  push    rdi
0x1800d78e4  push    r12
0x1800d78e6  push    r13
0x1800d78e8  push    r14
0x1800d78ea  push    r15
0x1800d78ec  sub     rsp, 350h
0x1800d78f3  lea     rbp, [rsp+60h]
0x1800d78f8  mov     [rbp+320h+arg_18], rbx
0x1800d78ff  mov     rax, cs:__security_cookie
0x1800d7906  xor     rax, rbp
0x1800d7909  mov     [rbp+320h+var_40], rax
0x1800d7910  mov     rax, [rbp+320h+arg_20]
0x1800d7917  xor     r15d, r15d
0x1800d791a  mov     rdi, [rbp+320h+arg_40]
0x1800d7921  mov     rbx, [rbp+320h+arg_60]
0x1800d7928  mov     r14, [rbp+320h+arg_58]
0x1800d792f  mov     [rbp+320h+var_2A8], rax
0x1800d7933  mov     rax, [rbp+320h+arg_38]
0x1800d793a  mov     [rbp+320h+hObject], rcx
0x1800d7941  mov     rcx, [rbp+320h+arg_28]
0x1800d7948  mov     [rbp+320h+var_2E8], rax
0x1800d794c  mov     rax, [rbp+320h+arg_48]
0x1800d7953  mov     [rbp+320h+hProvider], r8
0x1800d795a  mov     r8d, 20Ah; Size
0x1800d7960  mov     [rbp+320h+dwKeySpec], edx
0x1800d7963  xor     edx, edx; Val
0x1800d7965  mov     [rbp+320h+var_2E0], rcx
0x1800d7969  lea     rcx, [rbp+320h+pbOutput]; void *
0x1800d7970  mov     [rbp+320h+var_298], rax
0x1800d7977  mov     [rbp+320h+var_260], rdi
0x1800d797e  mov     [rbp+320h+var_2D0], rbx
0x1800d7982  mov     [rbp+320h+var_290], r15
0x1800d7989  mov     [rbp+320h+hKey], r15
0x1800d798d  mov     [rbp+320h+hMem], r15
0x1800d7991  mov     dword ptr [rbp+320h+var_310], r15d
0x1800d7995  mov     [rbp+320h+var_308], r15d
0x1800d7999  mov     [rbp+320h+pdwDataLen], r15d
0x1800d799d  mov     [rbp+320h+var_2B8], r15
0x1800d79a1  mov     [rbp+320h+var_320], r15d
0x1800d79a5  call    memset_0
0x1800d79aa  lea     esi, [r15+1]
0x1800d79ae  mov     dword ptr [rbp+320h+var_310+4], 208h
0x1800d79b5  mov     r13d, r15d
0x1800d79b8  mov     [rbp+320h+var_300], esi
0x1800d79bb  lea     rcx, [rbp+320h+var_258]
0x1800d79c2  mov     dword ptr [rbp+320h+Size+4], r13d
0x1800d79c6  mov     [rbp+320h+phKey], r15
0x1800d79cd  mov     [rbp+320h+var_278], r15
0x1800d79d4  mov     [rbp+320h+var_2D8], r15
0x1800d79d8  mov     [rbp+320h+var_2FC], r15d
0x1800d79dc  mov     [rbp+320h+var_280], r15
0x1800d79e3  mov     dword ptr [rbp+320h+Size], r15d
0x1800d79e7  mov     [rbp+320h+var_318], r15
0x1800d79eb  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x1800d79f0  mov     rcx, [rbp+320h+var_258]
0x1800d79f7  test    rcx, rcx
0x1800d79fa  jnz     short loc_1800D7A06
0x1800d79fc  mov     esi, 0C000009Ah
0x1800d7a01  jmp     loc_1800D81AA
0x1800d7a06  mov     edx, 0Dh
0x1800d7a0b  call    ?SelectEncryptionAlgorithm@KerberosCryptoPolicy@@QEAAPEAUEncryptionAlgorithm@Kerb3961@@W4KeyUsage@3@W4KdcPrincipalKeyState@@@Z; KerberosCryptoPolicy::SelectEncryptionAlgorithm(Kerb3961::KeyUsage,KdcPrincipalKeyState)
0x1800d7a10  mov     [rbp+320h+var_268], rax
0x1800d7a17  mov     r12, rax
0x1800d7a1a  test    rax, rax
0x1800d7a1d  jnz     short loc_1800D7A29
0x1800d7a1f  mov     esi, 0C00002FDh
0x1800d7a24  jmp     loc_1800D81AA
0x1800d7a29  mov     rcx, [rbp+320h+hObject]
0x1800d7a30  test    rcx, rcx
0x1800d7a33  jnz     short loc_1800D7A3F
0x1800d7a35  mov     esi, 0C0000321h
0x1800d7a3a  jmp     loc_1800D81AA
0x1800d7a3f  mov     eax, [rbp+320h+dwKeySpec]
0x1800d7a42  inc     eax
0x1800d7a44  test    eax, 0FFFFFFFEh
0x1800d7a49  jnz     short loc_1800D7A6D
0x1800d7a4b  mov     rdx, rcx; void *
0x1800d7a4e  lea     r8, [rbp+320h+var_300]; int *
0x1800d7a52  mov     ecx, esi; int
0x1800d7a54  call    ?ScHelperIsNcryptRsaKey@@YAJHPEAXPEAH@Z; ScHelperIsNcryptRsaKey(int,void *,int *)
0x1800d7a59  mov     esi, eax
0x1800d7a5b  test    eax, eax
0x1800d7a5d  js      loc_1800D81AA
0x1800d7a63  mov     esi, [rbp+320h+var_300]
0x1800d7a66  mov     rcx, [rbp+320h+hObject]; hObject
0x1800d7a6d  test    esi, esi
0x1800d7a6f  jnz     loc_1800D7B2A
0x1800d7a75  cmp     [rbp+320h+hProvider], r13
0x1800d7a7c  jz      short loc_1800D7A35
0x1800d7a7e  mov     r9d, dword ptr [rbp+320h+var_310+4]; cbOutput
0x1800d7a82  lea     rax, [rbp+320h+var_310+4]
0x1800d7a86  mov     [rsp+380h+dwFlags], r13d; dwFlags
0x1800d7a8b  lea     r8, [rbp+320h+pbOutput]; pbOutput
0x1800d7a92  lea     rdx, aSmartcardassoc; "SmartCardAssociatedECDHKey"
0x1800d7a99  mov     [rsp+380h+pcbResult], rax; pcbResult
0x1800d7a9e  call    cs:__imp_NCryptGetProperty
0x1800d7aa4  mov     esi, eax
0x1800d7aa6  test    eax, eax
0x1800d7aa8  js      loc_1800D81AA
0x1800d7aae  mov     r15d, dword ptr [rbp+320h+arg_50]
0x1800d7ab5  cmp     r15d, 0FFFFh
0x1800d7abc  jbe     short loc_1800D7AC8
0x1800d7abe  mov     esi, 0C00000BBh
0x1800d7ac3  jmp     loc_1800D81A6
0x1800d7ac8  lea     r9, [rbp+320h+var_320]; unsigned int *
0x1800d7acc  mov     r8d, r15d; unsigned int
0x1800d7acf  mov     rdx, r12; struct Kerb3961::EncryptionAlgorithm *
0x1800d7ad2  call    ?GetEncryptedSize@KerberosCryptoPolicy@@QEAA_NPEAUEncryptionAlgorithm@Kerb3961@@KPEAK@Z; KerberosCryptoPolicy::GetEncryptedSize(Kerb3961::EncryptionAlgorithm *,ulong,ulong *)
0x1800d7ad7  test    al, al
0x1800d7ad9  jz      short loc_1800D7ABE
0x1800d7adb  mov     eax, [rbp+320h+var_320]
0x1800d7ade  lea     ecx, [rax+54h]
0x1800d7ae1  cmp     ecx, eax
0x1800d7ae3  jb      short loc_1800D7B20
0x1800d7ae5  mov     r8, [rbp+320h+var_2A8]
0x1800d7ae9  mov     edx, [r8]
0x1800d7aec  add     edx, ecx
0x1800d7aee  cmp     edx, ecx
0x1800d7af0  jb      short loc_1800D7B20
0x1800d7af2  mov     r10, [rbp+320h+var_2E8]
0x1800d7af6  mov     ecx, [r10+10h]
0x1800d7afa  add     ecx, edx
0x1800d7afc  cmp     ecx, edx
0x1800d7afe  jb      short loc_1800D7B20
0x1800d7b00  mov     r12d, dword ptr [rbp+320h+var_310+4]
0x1800d7b04  add     r12d, ecx
0x1800d7b07  cmp     r12d, ecx
0x1800d7b0a  jb      short loc_1800D7B20
0x1800d7b0c  mov     esi, [rbp+320h+var_300]
0x1800d7b0f  lea     rdx, [rbp+320h+pbOutput]
0x1800d7b16  mov     rcx, [rbp+320h+var_2E0]
0x1800d7b1a  mov     [rbp+320h+Src], rdx
0x1800d7b1e  jmp     short loc_1800D7B8A
0x1800d7b20  mov     esi, 0C0000095h
0x1800d7b25  jmp     loc_1800D81A6
0x1800d7b2a  mov     rcx, [rbp+320h+var_2E0]; unsigned __int8 *
0x1800d7b2e  xor     r12d, r12d
0x1800d7b31  mov     [rbp+320h+Src], r12
0x1800d7b35  test    rcx, rcx
0x1800d7b38  jz      short loc_1800D7B7B
0x1800d7b3a  cmp     [rbp+320h+arg_30], r12d
0x1800d7b41  jz      short loc_1800D7B7B
0x1800d7b43  mov     edx, [rbp+320h+arg_30]; unsigned int
0x1800d7b49  lea     r8, [rbp+320h+var_320]; unsigned int *
0x1800d7b4d  mov     [rbp+320h+var_320], r12d
0x1800d7b51  call    ?ScHelperGetNGCEncryptedAESKeySize@@YAJPEAEKPEAK@Z; ScHelperGetNGCEncryptedAESKeySize(uchar *,ulong,ulong *)
0x1800d7b56  mov     esi, eax
0x1800d7b58  test    eax, eax
0x1800d7b5a  js      loc_1800D81AA
0x1800d7b60  mov     r12d, [rbp+320h+var_320]
0x1800d7b64  mov     r15d, dword ptr [rbp+320h+arg_50]
0x1800d7b6b  add     r12d, 38h ; '8'
0x1800d7b6f  mov     esi, [rbp+320h+var_300]
0x1800d7b72  add     r12d, r15d
0x1800d7b75  mov     rcx, [rbp+320h+var_2E0]
0x1800d7b79  jmp     short loc_1800D7B86
0x1800d7b7b  mov     r15d, dword ptr [rbp+320h+arg_50]
0x1800d7b82  lea     r12d, [r15+58h]
0x1800d7b86  mov     r10, [rbp+320h+var_2E8]
0x1800d7b8a  mov     eax, r12d
0x1800d7b8d  mov     [rbp+320h+var_320], eax
0x1800d7b90  test    r14, r14
0x1800d7b93  jz      loc_1800D819E
0x1800d7b99  cmp     [rbx], eax
0x1800d7b9b  jb      loc_1800D819E
0x1800d7ba1  test    esi, esi
0x1800d7ba3  jnz     loc_1800D7D10
0x1800d7ba9  mov     [r14], r13d
0x1800d7bac  lea     rbx, [r14+8]
0x1800d7bb0  mov     eax, [r10+10h]
0x1800d7bb4  mov     rcx, rbx; void *
0x1800d7bb7  mov     [r14+4], eax
0x1800d7bbb  mov     r8d, [r10+10h]; Size
0x1800d7bbf  mov     rdx, [r10+8]; Src
0x1800d7bc3  call    memcpy_0
0x1800d7bc8  movaps  xmm0, xmmword ptr [rdi]
0x1800d7bcb  mov     rax, [rbp+320h+var_2E8]
0x1800d7bcf  mov     rcx, [rbp+320h+var_268]
0x1800d7bd6  mov     esi, [rax+10h]
0x1800d7bd9  movups  xmmword ptr [rsi+rbx], xmm0
0x1800d7bdd  movaps  xmm1, xmmword ptr [rdi+10h]
0x1800d7be1  movups  xmmword ptr [rsi+rbx+10h], xmm1
0x1800d7be6  movaps  xmm0, xmmword ptr [rdi+20h]
0x1800d7bea  movups  xmmword ptr [rsi+rbx+20h], xmm0
0x1800d7bef  movaps  xmm1, xmmword ptr [rdi+30h]
0x1800d7bf3  movups  xmmword ptr [rsi+rbx+30h], xmm1
0x1800d7bf8  mov     rax, [rcx]
0x1800d7bfb  mov     rax, [rax+0D8h]
0x1800d7c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7c07  mov     rdi, [rbp+320h+var_2A8]
0x1800d7c0b  mov     [rsi+rbx+40h], eax
0x1800d7c0f  mov     eax, [rdi]
0x1800d7c11  mov     [rsi+rbx+44h], eax
0x1800d7c15  add     rbx, rsi
0x1800d7c18  mov     r8d, [rdi]; Size
0x1800d7c1b  mov     rdx, [rdi+8]; Src
0x1800d7c1f  lea     rcx, [rbx+48h]; void *
0x1800d7c23  call    memcpy_0
0x1800d7c28  mov     edi, [rdi]
0x1800d7c2a  mov     eax, dword ptr [rbp+320h+var_310+4]
0x1800d7c2d  mov     rdx, [rbp+320h+Src]; Src
0x1800d7c31  mov     [rdi+rbx+48h], eax
0x1800d7c35  add     rbx, 4Ch ; 'L'
0x1800d7c39  mov     r8d, dword ptr [rbp+320h+var_310+4]; Size
0x1800d7c3d  add     rbx, rdi
0x1800d7c40  mov     rcx, rbx; void *
0x1800d7c43  call    memcpy_0
0x1800d7c48  mov     eax, [rbp+320h+var_320]
0x1800d7c4b  lea     rdx, [rbp+320h+phKey]; phKey
0x1800d7c52  mov     r12d, dword ptr [rbp+320h+var_310+4]
0x1800d7c56  sub     eax, edi
0x1800d7c58  mov     r8, [rbp+320h+Src]; pszKeyName
0x1800d7c5c  sub     eax, esi
0x1800d7c5e  sub     eax, dword ptr [rbp+320h+var_310+4]
0x1800d7c61  add     r12, rbx
0x1800d7c64  mov     rbx, [rbp+320h+hProvider]
0x1800d7c6b  sub     eax, 54h ; 'T'
0x1800d7c6e  xor     r9d, r9d; dwLegacyKeySpec
0x1800d7c71  mov     [rbp+320h+var_320], eax
0x1800d7c74  mov     rcx, rbx; hProvider
0x1800d7c77  mov     dword ptr [rsp+380h+pcbResult], 40h ; '@'; unsigned int
0x1800d7c7f  call    cs:__imp_NCryptOpenKey
0x1800d7c85  mov     esi, eax
0x1800d7c87  test    eax, eax
0x1800d7c89  js      loc_1800D81A6
0x1800d7c8f  mov     rcx, [rbp+320h+var_268]
0x1800d7c96  mov     rax, [rcx]
0x1800d7c99  mov     rax, [rax+0D8h]
0x1800d7ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7ca5  mov     rdx, [rbp+320h+var_260]
0x1800d7cac  lea     r8, [rbp+320h+var_320]
0x1800d7cb0  mov     [rsp+380h+var_328], r12; unsigned __int8 *
0x1800d7cb5  mov     r9d, eax; unsigned int
0x1800d7cb8  mov     [rsp+380h+var_330], r8; unsigned int *
0x1800d7cbd  mov     r8, [rbp+320h+var_298]
0x1800d7cc4  mov     [rsp+380h+var_338], r8; unsigned __int8 *
0x1800d7cc9  lea     rcx, [rdx+20h]
0x1800d7ccd  mov     r8, [rbp+320h+var_2A8]; struct _CRYPTOAPI_BLOB *
0x1800d7cd1  mov     [rsp+380h+var_340], r15d; unsigned int
0x1800d7cd6  mov     [rsp+380h+var_348], rcx; unsigned __int8 *
0x1800d7cdb  mov     rcx, rbx; unsigned __int64
0x1800d7cde  mov     qword ptr [rsp+380h+dwFlags], rdx; unsigned __int8 *
0x1800d7ce3  mov     rdx, [rbp+320h+phKey]; unsigned __int64
0x1800d7cea  call    ?KerbEncryptCreds@@YAJ_K0PEAU_CRYPTOAPI_BLOB@@KKPEAEK2K2PEAK2@Z; KerbEncryptCreds(unsigned __int64,unsigned __int64,_CRYPTOAPI_BLOB *,ulong,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong *,uchar *)
0x1800d7cef  mov     r15, [rbp+320h+var_318]
0x1800d7cf3  mov     esi, eax
0x1800d7cf5  test    eax, eax
0x1800d7cf7  js      loc_1800D81AA
0x1800d7cfd  mov     rax, [rbp+320h+var_2D0]
0x1800d7d01  sub     r12d, r14d
0x1800d7d04  add     r12d, [rbp+320h+var_320]
0x1800d7d08  mov     [rax], r12d
0x1800d7d0b  jmp     loc_1800D81AA
0x1800d7d10  test    rcx, rcx
0x1800d7d13  jz      loc_1800D7E38
0x1800d7d19  cmp     [rbp+320h+arg_30], r13d
0x1800d7d20  jz      loc_1800D7E38
0x1800d7d26  lea     r8, [rbp+320h+var_2FC]; unsigned int *
0x1800d7d2a  lea     rdx, [rbp+320h+var_2D8]; unsigned __int8 **
0x1800d7d2e  lea     rcx, [rbp+320h+var_278]; void **
0x1800d7d35  call    ?ScHelperCreateCredKeysAES@@YAJPEAPEAXPEAPEAEPEAK@Z; ScHelperCreateCredKeysAES(void * *,uchar * *,ulong *)
0x1800d7d3a  mov     esi, eax
0x1800d7d3c  test    eax, eax
0x1800d7d3e  js      loc_1800D7E2F
0x1800d7d44  mov     r8, [rbp+320h+var_298]
0x1800d7d4b  lea     rax, [rbp+320h+var_318]
0x1800d7d4f  lea     r9, [rbp+320h+Size+4]
0x1800d7d53  mov     [rsp+380h+pcbResult], rax
0x1800d7d58  mov     edx, r15d
0x1800d7d5b  lea     rcx, [rbp+320h+var_278]
0x1800d7d62  call    ?ScHelperEncryptAES@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@KQEAEPEAKPEAPEAE@Z; ScHelperEncryptAES(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,ulong,uchar * const,ulong *,uchar * *)
0x1800d7d67  mov     r13, [rbp+320h+var_2D8]
0x1800d7d6b  mov     esi, eax
0x1800d7d6d  test    eax, eax
0x1800d7d6f  js      loc_1800D81A6
0x1800d7d75  mov     r9d, [rbp+320h+var_2FC]
0x1800d7d79  lea     rax, [rbp+320h+Size]
0x1800d7d7d  mov     edx, [rbp+320h+arg_30]
0x1800d7d83  mov     r8, r13
0x1800d7d86  mov     rcx, [rbp+320h+var_2E0]
0x1800d7d8a  mov     qword ptr [rsp+380h+dwFlags], rax
0x1800d7d8f  lea     rax, [rbp+320h+var_280]
0x1800d7d96  mov     [rsp+380h+pcbResult], rax
0x1800d7d9b  call    cs:__imp_NgcEncryptWithAsymmetricKey
0x1800d7da1  movzx   esi, ax
0x1800d7da4  mov     eax, esi
0x1800d7da6  or      eax, 0C0070000h
0x1800d7dab  test    esi, esi
0x1800d7dad  cmovnz  esi, eax
0x1800d7db0  test    esi, esi
0x1800d7db2  js      loc_1800D81A6
0x1800d7db8  mov     qword ptr [r14], 0
0x1800d7dbf  lea     rdi, [r14+14h]
0x1800d7dc3  mov     dword ptr [r14+8], 1
0x1800d7dcb  mov     rcx, rdi; void *
0x1800d7dce  mov     dword ptr [r14+0Ch], 2
0x1800d7dd6  mov     eax, dword ptr [rbp+320h+Size]
0x1800d7dd9  mov     rdx, [rbp+320h+var_280]; Src
  ... truncated ...
```
