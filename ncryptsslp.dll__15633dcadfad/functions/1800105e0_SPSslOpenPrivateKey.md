# SPSslOpenPrivateKey

- ea: `0x1800105e0`
- end: `0x180010f57`
- name: `SPSslOpenPrivateKey`
- size: `2423`
- prototype: `__int64 __fastcall(__int64, __int64 *, const CERT_CONTEXT *, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180003ef0`
- `0x1800068e0`
- `0x180007940`
- `0x180009160`
- `0x18000b594`
- `0x18000b654`
- `0x1800105e0`
- `0x180010f60`
- `0x180011110`
- `0x1800185e0`
- `0x180018ac0`
- `0x180024924`
- `0x180024ef0`
- `0x180026010`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x180010a04`
- `ncrypt!NCryptOpenKey` at `0x180010a04`
- `ncrypt!NCryptGetProperty` at `0x180010aa7`
- `ncrypt!NCryptGetProperty` at `0x180010ada`
- `ncrypt!NCryptGetProperty` at `0x180010bb2`
- `ncrypt!NCryptGetProperty` at `0x180010c0e`
- `ncrypt!NCryptGetProperty` at `0x180010cfc`
- `ncrypt!NCryptGetProperty` at `0x180010aa7`
- `ncrypt!NCryptGetProperty` at `0x180010ada`
- `ncrypt!NCryptGetProperty` at `0x180010bb2`
- `ncrypt!NCryptGetProperty` at `0x180010c0e`
- `ncrypt!NCryptGetProperty` at `0x180010cfc`
- `ncrypt!NCryptFreeObject` at `0x180010eea`
- `ncrypt!NCryptFreeObject` at `0x180010efe`
- `ncrypt!NCryptFreeObject` at `0x180010f15`
- `ncrypt!NCryptFreeObject` at `0x180010eea`
- `ncrypt!NCryptFreeObject` at `0x180010efe`
- `ncrypt!NCryptFreeObject` at `0x180010f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a63`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800106d3`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800107dd`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180010a59`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800106d3`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800107dd`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180010a59`
- `CRYPTSP!CryptGetDefaultProviderW` at `0x180010887`
- `CRYPTSP!CryptGetDefaultProviderW` at `0x1800109a8`
- `CRYPTSP!CryptGetDefaultProviderW` at `0x180010887`
- `CRYPTSP!CryptGetDefaultProviderW` at `0x1800109a8`

## string_xrefs

- `0x180010654`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800107a1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001082b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180010981`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180010c22`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180010d2d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslOpenPrivateKey(__int64 a1, __int64 *a2, const CERT_CONTEXT *a3, int a4)
{
  LPCWSTR *p_phKey; // r14
  __int64 v5; // rsi
  BYTE *p_pcbResult; // r15
  int v8; // r9d
  SECURITY_STATUS v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rax
  BYTE *v13; // rdi
  WCHAR *v14; // r13
  int v15; // edx
  int v16; // r8d
  unsigned __int64 v17; // rbx
  __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  _DWORD *v22; // rax
  DWORD v23; // eax
  int v24; // edx
  int v25; // r8d
  _QWORD *v26; // rcx
  WCHAR *v27; // rcx
  __int64 v28; // rax
  DWORD v29; // eax
  unsigned __int64 v30; // rbx
  __int64 v31; // rcx
  unsigned __int64 v32; // rcx
  void *v33; // rsp
  void *v34; // rsp
  WCHAR *v35; // rax
  __int64 v36; // r9
  __int64 v37; // rcx
  DWORD v38; // eax
  int NCryptProviderHandle; // eax
  DWORD LastError; // eax
  SECURITY_STATUS Property; // eax
  unsigned __int64 v42; // rbx
  __int64 v43; // rcx
  unsigned __int64 v44; // rcx
  void *v45; // rsp
  void *v46; // rsp
  BYTE *v47; // rax
  unsigned __int64 v48; // rbx
  __int64 v49; // rcx
  unsigned __int64 v50; // rcx
  void *v51; // rsp
  void *v52; // rsp
  BYTE *v53; // rax
  int v54; // edx
  int v55; // r8d
  NCRYPT_HANDLE v56; // rcx
  _BYTE v58[32]; // [rsp+0h] [rbp-40h] BYREF
  int v59; // [rsp+30h] [rbp-10h]
  DWORD pcbResult; // [rsp+40h] [rbp+0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp+4h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp+8h] BYREF
  DWORD pcbProvName; // [rsp+50h] [rbp+10h] BYREF
  DWORD v64; // [rsp+54h] [rbp+14h] BYREF
  BYTE pbOutput[8]; // [rsp+58h] [rbp+18h] BYREF
  int v66; // [rsp+60h] [rbp+20h]
  __int64 *v67; // [rsp+70h] [rbp+30h]

  p_phKey = 0;
  v66 = a4;
  phKey = 0;
  v5 = 0;
  pcbData = 0;
  p_pcbResult = 0;
  v64 = 0;
  pcbResult = 0;
  pcbProvName = 0;
  *(_QWORD *)pbOutput = 0;
  v67 = a2;
  if ( !SslpValidateProvHandle() )
  {
    v9 = -2146893786;
    v10 = 4292;
    v11 = 2148073510LL;
LABEL_3:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v10);
    goto LABEL_133;
  }
  if ( (v8 & 0xFFFFFFBF) != 0 )
  {
    v9 = -2146893815;
    v10 = 4299;
    v11 = 2148073481LL;
    goto LABEL_3;
  }
  v12 = SafeAllocaAllocateFromHeap(32);
  v5 = v12;
  if ( !v12 )
  {
    v10 = 4313;
LABEL_8:
    v9 = -2146893810;
    v11 = 2148073486LL;
    goto LABEL_3;
  }
  *(_QWORD *)(v12 + 8) = 0;
  *(_QWORD *)(v12 + 16) = 0;
  *(_QWORD *)(v12 + 24) = 0;
  *(_DWORD *)v12 = 32;
  v13 = 0;
  *(_DWORD *)(v12 + 4) = 1936944180;
  v14 = 0;
  pcbData = 0;
  if ( !CertGetCertificateContextProperty(a3, 2u, 0, &pcbData) )
  {
    v64 = 8;
    if ( CertGetCertificateContextProperty(a3, 0x63u, &phKey, &v64) )
    {
      Property = NCryptGetProperty(phKey, L"Provider Handle", pbOutput, 8u, &pcbResult, 0);
      v9 = Property;
      if ( Property >= 0 )
      {
        Property = NCryptGetProperty(*(NCRYPT_HANDLE *)pbOutput, L"Name", 0, 0, &pcbResult, 0);
        v9 = Property;
        if ( Property >= 0 )
        {
          v42 = pcbResult;
          if ( !pcbResult
            || pcbResult > (unsigned __int64)g_ulMaxStackAllocSize
            || (unsigned __int64)pcbResult + g_ulAdditionalProbeSize + 8 < pcbResult
            || !(unsigned int)VerifyStackAvailable() )
          {
            goto LABEL_147;
          }
          v43 = v42 + 23;
          if ( v42 + 23 <= v42 + 8 )
            v43 = 0xFFFFFFFFFFFFFF0LL;
          v44 = v43 & 0xFFFFFFFFFFFFFFF0uLL;
          v45 = alloca(v44);
          v46 = alloca(v44);
          p_pcbResult = (BYTE *)&pcbResult;
          if ( v58 == (_BYTE *)-64LL || (pcbResult = 1801679955, (p_pcbResult = (BYTE *)&phKey) == 0) )
          {
LABEL_147:
            if ( v42 + 8 >= v42 )
            {
              v47 = (BYTE *)((__int64 (*)(void))g_pfnAllocate)();
              p_pcbResult = v47;
              if ( v47 )
              {
                *(_DWORD *)v47 = 1885431112;
                p_pcbResult = v47 + 8;
              }
            }
          }
          if ( !p_pcbResult )
          {
            v10 = 4474;
            goto LABEL_8;
          }
          Property = NCryptGetProperty(*(NCRYPT_HANDLE *)pbOutput, L"Name", p_pcbResult, pcbResult, &pcbResult, 0);
          v9 = Property;
          if ( Property >= 0 )
          {
            Property = SslGetNCryptProviderHandle(p_pcbResult, v5 + 16);
            v9 = Property;
            if ( Property >= 0 )
              goto LABEL_86;
            v10 = 4496;
          }
          else
          {
            v10 = 4488;
          }
        }
        else
        {
          v10 = 4465;
        }
      }
      else
      {
        v10 = 4451;
      }
    }
    else
    {
      LastError = GetLastError();
      Property = NormalizeNteStatus(LastError, 2148073485LL);
      v9 = Property;
      v10 = 4437;
    }
    v11 = (unsigned int)Property;
    goto LABEL_3;
  }
  v17 = pcbData;
  if ( !pcbData
    || pcbData > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)pcbData + g_ulAdditionalProbeSize + 8 < pcbData
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_148;
  }
  v18 = v17 + 23;
  if ( v17 + 23 <= v17 + 8 )
    v18 = 0xFFFFFFFFFFFFFF0LL;
  v19 = v18 & 0xFFFFFFFFFFFFFFF0uLL;
  v20 = alloca(v19);
  v21 = alloca(v19);
  p_phKey = (LPCWSTR *)&pcbResult;
  if ( v58 == (_BYTE *)-64LL || (pcbResult = 1801679955, (p_phKey = (LPCWSTR *)&phKey) == 0) )
  {
LABEL_148:
    if ( v17 + 8 >= v17 )
    {
      v22 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_phKey = (LPCWSTR *)v22;
      if ( v22 )
      {
        *v22 = 1885431112;
        p_phKey = (LPCWSTR *)(v22 + 2);
      }
    }
  }
  if ( !p_phKey )
  {
    v9 = -2146893810;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        v16,
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        243);
    goto LABEL_133;
  }
  if ( !CertGetCertificateContextProperty(a3, 2u, p_phKey, &pcbData) )
  {
    v23 = GetLastError();
    v9 = NormalizeNteStatus(v23, 2148073485LL);
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v59 = 4349;
LABEL_29:
      WPP_SF_sDsd(
        v26[2],
        v24,
        v25,
        (unsigned int)"Status",
        v9,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        v59);
      goto LABEL_125;
    }
    goto LABEL_125;
  }
  *((_DWORD *)p_phKey + 5) &= ~1u;
  v27 = (WCHAR *)p_phKey[1];
  if ( !v27 )
    goto LABEL_149;
  v28 = -1;
  do
    ++v28;
  while ( v27[v28] );
  if ( !v28 )
  {
LABEL_149:
    if ( !CryptGetDefaultProviderW(*((_DWORD *)p_phKey + 4), 0, 1u, 0, &pcbProvName) )
    {
      v29 = GetLastError();
      v9 = NormalizeNteStatus(v29, 2148073485LL);
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v59 = 4370;
        goto LABEL_29;
      }
LABEL_125:
      if ( *((_DWORD *)p_phKey - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      goto LABEL_127;
    }
    v30 = pcbProvName;
    if ( !pcbProvName
      || pcbProvName > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)pcbProvName + g_ulAdditionalProbeSize + 8 < pcbProvName
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_150;
    }
    v31 = v30 + 23;
    if ( v30 + 23 <= v30 + 8 )
      v31 = 0xFFFFFFFFFFFFFF0LL;
    v32 = v31 & 0xFFFFFFFFFFFFFFF0uLL;
    v33 = alloca(v32);
    v34 = alloca(v32);
    v14 = (WCHAR *)&pcbResult;
    if ( v58 == (_BYTE *)-64LL || (pcbResult = 1801679955, (v14 = (WCHAR *)&phKey) == 0) )
    {
LABEL_150:
      if ( v30 + 8 >= v30 )
      {
        v35 = (WCHAR *)((__int64 (*)(void))g_pfnAllocate)();
        v14 = v35;
        if ( v35 )
        {
          *(_DWORD *)v35 = 1885431112;
          v14 = v35 + 4;
        }
      }
    }
    if ( !v14 )
    {
      v9 = -2146893810;
      v36 = 4379;
      v37 = 2148073486LL;
LABEL_51:
      DebugTraceError(v37, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v36);
      goto LABEL_125;
    }
    if ( !CryptGetDefaultProviderW(*((_DWORD *)p_phKey + 4), 0, 1u, v14, &pcbProvName) )
    {
      v38 = GetLastError();
      NCryptProviderHandle = NormalizeNteStatus(v38, 2148073485LL);
      v9 = NCryptProviderHandle;
      v36 = 4391;
LABEL_54:
      v37 = (unsigned int)NCryptProviderHandle;
      goto LABEL_51;
    }
    v27 = v14;
  }
  NCryptProviderHandle = SslGetNCryptProviderHandle(v27, v5 + 16);
  v9 = NCryptProviderHandle;
  if ( NCryptProviderHandle < 0 )
  {
    v36 = 4410;
    goto LABEL_54;
  }
  v9 = NCryptOpenKey(*(_QWORD *)(v5 + 16), &phKey, *p_phKey, *((_DWORD *)p_phKey + 10), *((_DWORD *)p_phKey + 5) | v66);
  if ( v9 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v59 = 4423;
      goto LABEL_29;
    }
    goto LABEL_125;
  }
LABEL_86:
  v9 = NCryptGetProperty(phKey, L"Algorithm Name", 0, 0, &pcbResult, 0);
  if ( v9 < 0 )
  {
    DebugTraceError((unsigned int)v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 4515);
    goto LABEL_124;
  }
  v48 = pcbResult;
  if ( !pcbResult
    || pcbResult > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)pcbResult + g_ulAdditionalProbeSize + 8 < pcbResult
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_151;
  }
  v49 = v48 + 23;
  if ( v48 + 23 <= v48 + 8 )
    v49 = 0xFFFFFFFFFFFFFF0LL;
  v50 = v49 & 0xFFFFFFFFFFFFFFF0uLL;
  v51 = alloca(v50);
  v52 = alloca(v50);
  v13 = (BYTE *)&pcbResult;
  if ( v58 == (_BYTE *)-64LL || (pcbResult = 1801679955, (v13 = (BYTE *)&phKey) == 0) )
  {
LABEL_151:
    if ( v48 + 8 >= v48 )
    {
      v53 = (BYTE *)((__int64 (*)(void))g_pfnAllocate)();
      v13 = v53;
      if ( v53 )
      {
        *(_DWORD *)v53 = 1885431112;
        v13 = v53 + 8;
      }
    }
  }
  if ( !v13 )
  {
    v9 = -2146893810;
    goto LABEL_124;
  }
  v9 = NCryptGetProperty(phKey, L"Algorithm Name", v13, pcbResult, &pcbResult, 0);
  if ( v9 >= 0 )
  {
    if ( !wcscmp((const wchar_t *)v13, L"RSA") )
    {
      *(_DWORD *)(v5 + 8) = 196609;
    }
    else if ( !wcscmp((const wchar_t *)v13, L"DSA") )
    {
      *(_DWORD *)(v5 + 8) = 196611;
    }
    else if ( !wcscmp((const wchar_t *)v13, L"ECDSA_P256") || !wcscmp((const wchar_t *)v13, L"ECDH_P256") )
    {
      *(_DWORD *)(v5 + 8) = 196612;
    }
    else if ( !wcscmp((const wchar_t *)v13, L"ECDSA_P384") || !wcscmp((const wchar_t *)v13, L"ECDH_P384") )
    {
      *(_DWORD *)(v5 + 8) = 196613;
    }
    else if ( !wcscmp((const wchar_t *)v13, L"ECDSA_P521") || !wcscmp((const wchar_t *)v13, L"ECDH_P521") )
    {
      *(_DWORD *)(v5 + 8) = 196614;
    }
    else if ( !wcscmp((const wchar_t *)v13, L"ECDSA") || !wcscmp((const wchar_t *)v13, L"ECDH") )
    {
      *(_DWORD *)(v5 + 8) = 196619;
    }
    else if ( (unsigned int)I_GetSignatureDetailsFromAlgorithmName(v13, v5 + 8) )
    {
      v9 = -2146893783;
      goto LABEL_124;
    }
    v9 = 0;
    *(_QWORD *)(v5 + 24) = phKey;
    phKey = 0;
    *v67 = v5;
    v5 = 0;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v54,
      v55,
      (unsigned int)"Status",
      v9,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      185);
  }
LABEL_124:
  if ( p_phKey )
    goto LABEL_125;
LABEL_127:
  if ( v13 && *((_DWORD *)v13 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v14 && *((_DWORD *)v14 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_133:
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( v5 )
  {
    v56 = *(_QWORD *)(v5 + 24);
    if ( v56 )
      NCryptFreeObject(v56);
    MSCryptFree(v5);
  }
  if ( *(_QWORD *)pbOutput )
    NCryptFreeObject(*(NCRYPT_HANDLE *)pbOutput);
  if ( p_pcbResult && *((_DWORD *)p_pcbResult - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800105e0  push    rbp
0x1800105e2  push    rbx
0x1800105e3  push    rsi
0x1800105e4  push    rdi
0x1800105e5  push    r12
0x1800105e7  push    r13
0x1800105e9  push    r14
0x1800105eb  push    r15
0x1800105ed  sub     rsp, 88h
0x1800105f4  lea     rbp, [rsp+40h]
0x1800105f9  mov     rax, cs:__security_cookie
0x180010600  xor     rax, rbp
0x180010603  mov     [rbp+80h+var_48], rax
0x180010607  xor     r14d, r14d
0x18001060a  mov     [rbp+80h+var_60], r9d
0x18001060e  mov     [rbp+80h+phKey], r14
0x180010612  mov     esi, r14d
0x180010615  mov     [rbp+80h+pcbData], r14d
0x180010619  mov     r15d, r14d
0x18001061c  mov     [rbp+80h+var_6C], r14d
0x180010620  mov     r12, r8
0x180010623  mov     [rbp+80h+pcbResult], r14d
0x180010627  mov     [rbp+80h+var_70], r14d
0x18001062b  mov     qword ptr [rbp+80h+pbOutput], r14
0x18001062f  mov     [rbp+80h+var_50], rdx
0x180010633  call    SslpValidateProvHandle
0x180010638  test    rax, rax
0x18001063b  jnz     short loc_180010665
0x18001063d  mov     ebx, 80090026h
0x180010642  mov     r9d, 10C4h
0x180010648  mov     ecx, 80090026h
0x18001064d  lea     rdx, aStatus; "Status"
0x180010654  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001065b  call    DebugTraceError
0x180010660  jmp     loc_180010EE1
0x180010665  test    r9d, 0FFFFFFBFh
0x18001066c  jz      short loc_180010680
0x18001066e  mov     ebx, 80090009h
0x180010673  mov     r9d, 10CBh
0x180010679  mov     ecx, 80090009h
0x18001067e  jmp     short loc_18001064D
0x180010680  mov     ebx, 20h ; ' '
0x180010685  mov     ecx, ebx
0x180010687  call    SafeAllocaAllocateFromHeap
0x18001068c  mov     rsi, rax
0x18001068f  test    rax, rax
0x180010692  jnz     short loc_1800106A6
0x180010694  mov     r9d, 10D9h
0x18001069a  mov     ebx, 8009000Eh
0x18001069f  mov     ecx, 8009000Eh
0x1800106a4  jmp     short loc_18001064D
0x1800106a6  mov     [rax+8], r14
0x1800106aa  lea     r9, [rbp+80h+pcbData]; pcbData
0x1800106ae  mov     [rax+10h], r14
0x1800106b2  xor     r8d, r8d; pvData
0x1800106b5  mov     [rax+18h], r14
0x1800106b9  mov     rcx, r12; pCertContext
0x1800106bc  mov     [rax], ebx
0x1800106be  mov     rdi, r14
0x1800106c1  mov     dword ptr [rax+4], 73736C34h
0x1800106c8  mov     r13, r14
0x1800106cb  lea     edx, [r8+2]; dwPropId
0x1800106cf  mov     [rbp+80h+pcbData], r14d
0x1800106d3  call    cs:__imp_CertGetCertificateContextProperty
0x1800106d9  test    eax, eax
0x1800106db  jz      loc_180010A42
0x1800106e1  mov     ebx, [rbp+80h+pcbData]
0x1800106e4  test    rbx, rbx
0x1800106e7  jz      short loc_18001074B
0x1800106e9  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800106f0  ja      short loc_18001074B
0x1800106f2  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800106f9  add     rcx, 8
0x1800106fd  add     rcx, rbx
0x180010700  cmp     rcx, rbx
0x180010703  jb      short loc_18001074B
0x180010705  call    VerifyStackAvailable
0x18001070a  test    eax, eax
0x18001070c  jz      short loc_18001074B
0x18001070e  lea     rax, [rbx+8]
0x180010712  lea     rcx, [rax+0Fh]
0x180010716  cmp     rcx, rax
0x180010719  ja      short loc_180010725
0x18001071b  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180010725  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180010729  mov     rax, rcx
0x18001072c  call    _alloca_probe
0x180010731  sub     rsp, rcx
0x180010734  lea     r14, [rsp+0C0h+pcbResult]
0x180010739  test    r14, r14
0x18001073c  jz      short loc_18001074B
0x18001073e  mov     dword ptr [r14], 6B637453h
0x180010745  add     r14, 8
0x180010749  jnz     short loc_180010772
0x18001074b  lea     rcx, [rbx+8]
0x18001074f  cmp     rcx, rbx
0x180010752  jb      short loc_180010772
0x180010754  mov     rax, cs:g_pfnAllocate
0x18001075b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010760  mov     r14, rax
0x180010763  test    rax, rax
0x180010766  jz      short loc_180010772
0x180010768  mov     dword ptr [rax], 70616548h
0x18001076e  add     r14, 8
0x180010772  test    r14, r14
0x180010775  jnz     short loc_1800107CE
0x180010777  mov     ebx, 8009000Eh
0x18001077c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010783  lea     rax, WPP_GLOBAL_Control
0x18001078a  cmp     rcx, rax
0x18001078d  jz      loc_180010EE1
0x180010793  test    byte ptr [rcx+1Ch], 1
0x180010797  jz      loc_180010EE1
0x18001079d  mov     rcx, [rcx+10h]
0x1800107a1  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800107a8  mov     [rsp+0C0h+var_90], 10F3h
0x1800107b0  lea     r9, aStatus; "Status"
0x1800107b7  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x1800107bc  mov     dword ptr [rsp+0C0h+pcbProvName], 8009000Eh
0x1800107c4  call    WPP_SF_sDsd
0x1800107c9  jmp     loc_180010EE1
0x1800107ce  lea     r9, [rbp+80h+pcbData]; pcbData
0x1800107d2  mov     r8, r14; pvData
0x1800107d5  mov     edx, 2; dwPropId
0x1800107da  mov     rcx, r12; pCertContext
0x1800107dd  call    cs:__imp_CertGetCertificateContextProperty
0x1800107e3  xor     r12d, r12d
0x1800107e6  test    eax, eax
0x1800107e8  jnz     short loc_18001084C
0x1800107ea  call    cs:__imp_GetLastError
0x1800107f0  mov     ecx, eax
0x1800107f2  mov     edx, 8009000Dh
0x1800107f7  call    NormalizeNteStatus
0x1800107fc  mov     ebx, eax
0x1800107fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180010805  lea     rax, WPP_GLOBAL_Control
0x18001080c  cmp     rcx, rax
0x18001080f  jz      loc_180010E8F
0x180010815  test    byte ptr [rcx+1Ch], 1
0x180010819  jz      loc_180010E8F
0x18001081f  mov     [rsp+0C0h+var_90], 10FDh
0x180010827  mov     rcx, [rcx+10h]
0x18001082b  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010832  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x180010837  lea     r9, aStatus; "Status"
0x18001083e  mov     dword ptr [rsp+0C0h+pcbProvName], ebx
0x180010842  call    WPP_SF_sDsd
0x180010847  jmp     loc_180010E8F
0x18001084c  and     dword ptr [r14+14h], 0FFFFFFFEh
0x180010851  mov     rcx, [r14+8]
0x180010855  test    rcx, rcx
0x180010858  jz      short loc_180010871
0x18001085a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001085e  inc     rax
0x180010861  cmp     [rcx+rax*2], r12w
0x180010866  jnz     short loc_18001085E
0x180010868  test    rax, rax
0x18001086b  jnz     loc_1800109D3
0x180010871  mov     ecx, [r14+10h]; dwProvType
0x180010875  lea     rax, [rbp+80h+var_70]
0x180010879  xor     r9d, r9d; pszProvName
0x18001087c  mov     [rsp+0C0h+pcbProvName], rax; pcbProvName
0x180010881  xor     edx, edx; pdwReserved
0x180010883  lea     r8d, [r9+1]; dwFlags
0x180010887  call    cs:__imp_CryptGetDefaultProviderW
0x18001088d  test    eax, eax
0x18001088f  jnz     short loc_1800108D3
0x180010891  call    cs:__imp_GetLastError
0x180010897  mov     ecx, eax
0x180010899  mov     edx, 8009000Dh
0x18001089e  call    NormalizeNteStatus
0x1800108a3  mov     ebx, eax
0x1800108a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108ac  lea     rax, WPP_GLOBAL_Control
0x1800108b3  cmp     rcx, rax
0x1800108b6  jz      loc_180010E8F
0x1800108bc  test    byte ptr [rcx+1Ch], 1
0x1800108c0  jz      loc_180010E8F
0x1800108c6  mov     [rsp+0C0h+var_90], 1112h
0x1800108ce  jmp     loc_180010827
0x1800108d3  mov     ebx, [rbp+80h+var_70]
0x1800108d6  test    rbx, rbx
0x1800108d9  jz      short loc_18001093E
0x1800108db  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800108e2  ja      short loc_18001093E
0x1800108e4  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800108eb  add     rcx, 8
0x1800108ef  add     rcx, rbx
0x1800108f2  cmp     rcx, rbx
0x1800108f5  jb      short loc_18001093E
0x1800108f7  call    VerifyStackAvailable
0x1800108fc  test    eax, eax
0x1800108fe  jz      short loc_18001093E
0x180010900  lea     rax, [rbx+8]
0x180010904  lea     rcx, [rax+0Fh]
0x180010908  cmp     rcx, rax
0x18001090b  ja      short loc_180010917
0x18001090d  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180010917  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001091b  mov     rax, rcx
0x18001091e  call    _alloca_probe
0x180010923  sub     rsp, rcx
0x180010926  lea     r13, [rsp+0C0h+pcbResult]
0x18001092b  test    r13, r13
0x18001092e  jz      short loc_18001093E
0x180010930  mov     dword ptr [r13+0], 6B637453h
0x180010938  add     r13, 8
0x18001093c  jnz     short loc_180010965
0x18001093e  lea     rcx, [rbx+8]
0x180010942  cmp     rcx, rbx
0x180010945  jb      short loc_180010965
0x180010947  mov     rax, cs:g_pfnAllocate
0x18001094e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010953  mov     r13, rax
0x180010956  test    rax, rax
0x180010959  jz      short loc_180010965
0x18001095b  mov     dword ptr [rax], 70616548h
0x180010961  add     r13, 8
0x180010965  test    r13, r13
0x180010968  jnz     short loc_180010992
0x18001096a  mov     ebx, 8009000Eh
0x18001096f  mov     r9d, 111Bh
0x180010975  mov     ecx, 8009000Eh
0x18001097a  lea     rdx, aStatus; "Status"
0x180010981  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010988  call    DebugTraceError
0x18001098d  jmp     loc_180010E8F
0x180010992  mov     ecx, [r14+10h]; dwProvType
0x180010996  lea     rax, [rbp+80h+var_70]
0x18001099a  xor     edx, edx; pdwReserved
0x18001099c  mov     [rsp+0C0h+pcbProvName], rax; pcbProvName
0x1800109a1  mov     r9, r13; pszProvName
0x1800109a4  lea     r8d, [rdx+1]; dwFlags
0x1800109a8  call    cs:__imp_CryptGetDefaultProviderW
0x1800109ae  test    eax, eax
0x1800109b0  jnz     short loc_1800109D0
0x1800109b2  call    cs:__imp_GetLastError
0x1800109b8  mov     ecx, eax
0x1800109ba  mov     edx, 8009000Dh
0x1800109bf  call    NormalizeNteStatus
0x1800109c4  mov     ebx, eax
0x1800109c6  mov     r9d, 1127h
0x1800109cc  mov     ecx, eax
0x1800109ce  jmp     short loc_18001097A
0x1800109d0  mov     rcx, r13
0x1800109d3  lea     rdx, [rsi+10h]
0x1800109d7  call    SslGetNCryptProviderHandle
0x1800109dc  mov     ebx, eax
0x1800109de  test    eax, eax
0x1800109e0  jns     short loc_1800109EA
0x1800109e2  mov     r9d, 113Ah
0x1800109e8  jmp     short loc_1800109CC
0x1800109ea  mov     eax, [rbp+80h+var_60]
0x1800109ed  lea     rdx, [rbp+80h+phKey]; phKey
0x1800109f1  or      eax, [r14+14h]
0x1800109f5  mov     r9d, [r14+28h]; dwLegacyKeySpec
0x1800109f9  mov     r8, [r14]; pszKeyName
0x1800109fc  mov     rcx, [rsi+10h]; hProvider
0x180010a00  mov     dword ptr [rsp+0C0h+pcbProvName], eax; dwFlags
0x180010a04  call    cs:__imp_NCryptOpenKey
0x180010a0a  mov     ebx, eax
0x180010a0c  test    eax, eax
0x180010a0e  jns     loc_180010BE6
0x180010a14  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a1b  lea     rax, WPP_GLOBAL_Control
0x180010a22  cmp     rcx, rax
0x180010a25  jz      loc_180010E8F
0x180010a2b  test    byte ptr [rcx+1Ch], 1
0x180010a2f  jz      loc_180010E8F
0x180010a35  mov     [rsp+0C0h+var_90], 1147h
0x180010a3d  jmp     loc_180010827
0x180010a42  lea     r9, [rbp+80h+var_6C]; pcbData
0x180010a46  mov     [rbp+80h+var_6C], 8
0x180010a4d  lea     r8, [rbp+80h+phKey]; pvData
0x180010a51  mov     edx, 63h ; 'c'; dwPropId
0x180010a56  mov     rcx, r12; pCertContext
0x180010a59  call    cs:__imp_CertGetCertificateContextProperty
0x180010a5f  test    eax, eax
0x180010a61  jnz     short loc_180010A84
0x180010a63  call    cs:__imp_GetLastError
0x180010a69  mov     ecx, eax
0x180010a6b  mov     edx, 8009000Dh
0x180010a70  call    NormalizeNteStatus
0x180010a75  mov     ebx, eax
0x180010a77  mov     r9d, 1155h
0x180010a7d  mov     ecx, eax
0x180010a7f  jmp     loc_18001064D
0x180010a84  mov     rcx, [rbp+80h+phKey]; hObject
0x180010a88  lea     rax, [rbp+80h+pcbResult]
0x180010a8c  mov     [rsp+0C0h+dwFlags], r14d; dwFlags
0x180010a91  lea     r8, [rbp+80h+pbOutput]; pbOutput
0x180010a95  mov     r9d, 8; cbOutput
0x180010a9b  mov     [rsp+0C0h+pcbProvName], rax; pcbResult
0x180010aa0  lea     rdx, aProviderHandle; "Provider Handle"
0x180010aa7  call    cs:__imp_NCryptGetProperty
0x180010aad  mov     ebx, eax
0x180010aaf  test    eax, eax
0x180010ab1  jns     short loc_180010ABB
0x180010ab3  mov     r9d, 1163h
0x180010ab9  jmp     short loc_180010A7D
  ... truncated ...
```
