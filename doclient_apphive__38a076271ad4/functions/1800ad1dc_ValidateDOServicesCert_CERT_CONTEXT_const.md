# ValidateDOServicesCert(_CERT_CONTEXT const *)

- ea: `0x1800ad1dc`
- end: `0x1800ad656`
- name: `?ValidateDOServicesCert@@YAJPEBU_CERT_CONTEXT@@@Z`
- size: `1146`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `4`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bca50`
- `0x1800bcb40`
- `0x1800e6150`
- `0x1800e6280`

## callees

- `0x1800095a0`
- `0x1800a1ea4`
- `0x1800a1f08`
- `0x1800a9440`
- `0x1800ad1dc`
- `0x1800ae230`
- `0x1800ae90c`
- `0x1800aead0`
- `0x1800f8110`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad2ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad3ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad4af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad2ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad3ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad4af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ad2c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ad2c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad3ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad46d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad3ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad46d`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800ad513`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800ad513`
- `CRYPT32!CryptEncodeObjectEx` at `0x1800ad3a0`
- `CRYPT32!CryptEncodeObjectEx` at `0x1800ad3a0`
- `CRYPT32!CertGetCertificateChain` at `0x1800ad267`
- `CRYPT32!CertGetCertificateChain` at `0x1800ad267`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x1800ad4a1`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x1800ad4a1`
- `CRYPT32!CertFreeCertificateChain` at `0x1800ad2b8`
- `CRYPT32!CertFreeCertificateChain` at `0x1800ad621`
- `CRYPT32!CertFreeCertificateChain` at `0x1800ad2b8`
- `CRYPT32!CertFreeCertificateChain` at `0x1800ad621`
- `bcrypt!BCryptDestroyHash` at `0x1800ad43f`
- `bcrypt!BCryptDestroyHash` at `0x1800ad43f`

## string_xrefs

- `0x1800ad545`: `ValidateDOServicesCert`
- `0x1800ad573`: `ValidateDOServicesCert`
- `0x1800ad5fa`: `ValidateDOServicesCert`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ValidateDOServicesCert(PCCERT_CONTEXT pCertContext)
{
  PCCERT_CONTEXT v1; // r13
  signed int v2; // esi
  signed int LastError; // eax
  PCCERT_CHAIN_CONTEXT v4; // r12
  const CERT_CHAIN_CONTEXT *v5; // r15
  DWORD v6; // ebx
  PCERT_SIMPLE_CHAIN v7; // rcx
  struct _CERT_PUBLIC_KEY_INFO *v8; // rbx
  struct _CERT_PUBLIC_KEY_INFO *v9; // rbx
  signed int v10; // eax
  void *v11; // rdx
  wil *v12; // rcx
  HLOCAL v13; // rcx
  signed int v14; // eax
  unsigned __int64 v15; // r15
  __int64 *v16; // r14
  __int64 v17; // rbx
  bool v18; // al
  PCCERT_CHAIN_CONTEXT *v19; // rax
  DWORD pcbComputedHash; // [rsp+58h] [rbp-B0h] BYREF
  PCCERT_CHAIN_CONTEXT pvEncoded[2]; // [rsp+60h] [rbp-A8h] BYREF
  __m128i si128; // [rsp+70h] [rbp-98h]
  DWORD pcbEncoded; // [rsp+80h] [rbp-88h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-80h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+90h] [rbp-78h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+98h] [rbp-70h] BYREF
  BYTE pbComputedHash[16]; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v30; // [rsp+C8h] [rbp-40h]

  v1 = pCertContext;
  memset(&pChainPara, 0, sizeof(pChainPara));
  pChainPara.cbSize = 32;
  pChainContext = 0;
  pvEncoded[0] = (PCCERT_CHAIN_CONTEXT)&pChainContext;
  pvEncoded[1] = 0;
  si128.m128i_i8[0] = 1;
  if ( CertGetCertificateChain(0, pCertContext, 0, pCertContext->hCertStore, &pChainPara, 0, 0, &pvEncoded[1]) )
  {
    v2 = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v2 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v2 = LastError;
    }
    else
    {
      v2 = -2147467259;
    }
  }
  if ( si128.m128i_i8[0] )
  {
    v4 = pvEncoded[1];
    v5 = *(const CERT_CHAIN_CONTEXT **)pvEncoded[0];
    if ( *(_QWORD *)pvEncoded[0] )
    {
      v6 = GetLastError();
      CertFreeCertificateChain(v5);
      SetLastError(v6);
    }
    *(_QWORD *)pvEncoded[0] = v4;
  }
  if ( v2 < 0 )
    goto LABEL_48;
  v2 = -2146762751;
  if ( !pChainContext->cChain )
    goto LABEL_48;
  v7 = *pChainContext->rgpChain;
  v2 = -2146762749;
  if ( v7->cElement <= 1 )
  {
    LogMessage(
      2u,
      "ValidateDOServicesCert",
      0x3E6u,
      "Unexpected number of items in certificate chain: %u",
      v7->cElement);
LABEL_48:
    LogResult(5u, "ValidateDOServicesCert", 0x3EDu, v2, "Validation of server certificate failed");
    if ( g_loggingProvider )
      v18 = *(_DWORD *)g_loggingProvider > 5u;
    else
      v18 = 0;
    if ( v18 )
    {
      *(_OWORD *)pvEncoded = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(pvEncoded[0]) = 0;
      if ( (int)EncodeData(v1->pbCertEncoded, v1->cbCertEncoded) >= 0 )
      {
        v19 = pvEncoded;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v19 = (PCCERT_CHAIN_CONTEXT *)pvEncoded[0];
        LogMessage(5u, "ValidateDOServicesCert", 0x3F6u, "Encoded certificate info: %s\n", (const char *)v19);
      }
      std::string::~string(pvEncoded);
    }
    goto LABEL_57;
  }
  v8 = *(struct _CERT_PUBLIC_KEY_INFO **)(*(_QWORD *)(*((_QWORD *)v7->rgpElement + 1) + 8LL) + 24LL);
  *(_OWORD *)pbComputedHash = 0;
  v30 = 0;
  pcbComputedHash = 32;
  v9 = v8 + 2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNGRefactor>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CNGRefactor>::GetImpl'::`2'::impl) )
  {
    pcbEncoded = 0;
    hMem = 0;
    pvEncoded[0] = (PCCERT_CHAIN_CONTEXT)&hMem;
    pvEncoded[1] = 0;
    si128.m128i_i8[0] = 1;
    if ( CryptEncodeObjectEx(1u, (LPCSTR)8, v9, 0x8000u, 0, &pvEncoded[1], &pcbEncoded) )
    {
      v2 = 0;
    }
    else
    {
      v10 = GetLastError();
      if ( v10 )
      {
        v2 = (unsigned __int16)v10 | 0x80070000;
        if ( v10 <= 0 )
          v2 = v10;
      }
      else
      {
        v2 = -2147467259;
      }
    }
    if ( si128.m128i_i8[0] )
    {
      v11 = *(void **)pvEncoded[0];
      *(_QWORD *)pvEncoded[0] = pvEncoded[1];
      if ( v11 )
        LocalFree(v11);
    }
    if ( v2 >= 0 )
    {
      try
      {
        *(_OWORD *)pvEncoded = 0;
        CHash::CHash((BCRYPT_HASH_HANDLE *)pvEncoded);
        CHash::Hash((CHash *)pvEncoded, hMem, pcbEncoded, pbComputedHash, pcbComputedHash);
        v12 = (wil *)pvEncoded[0];
        if ( pvEncoded[0] )
          BCryptDestroyHash((BCRYPT_HASH_HANDLE)pvEncoded[0]);
      }
      catch ( ... )
      {
        v2 = wil::ResultFromCaughtException(v12);
        v1 = pCertContext;
      }
    }
    v13 = hMem;
    hMem = 0;
    if ( v13 )
      LocalFree(v13);
  }
  else if ( CryptHashPublicKeyInfo(0, 0x800Cu, 0, 1u, v9, pbComputedHash, &pcbComputedHash) )
  {
    v2 = 0;
  }
  else
  {
    v14 = GetLastError();
    if ( v14 )
    {
      v2 = (unsigned __int16)v14 | 0x80070000;
      if ( v14 <= 0 )
        v2 = v14;
    }
    else
    {
      v2 = -2147467259;
    }
  }
  if ( v2 < 0 )
    goto LABEL_48;
  v2 = -2146762748;
  v15 = 0;
  v16 = qword_18017E1D0;
  if ( !(unsigned int)o__stricmp_0(v9->Algorithm.pszObjId, "1.2.840.10045.2.1") )
    v16 = qword_18017E190;
  while ( 1 )
  {
    v17 = pcbComputedHash;
    if ( RtlCompareMemory(v16, pbComputedHash, pcbComputedHash) == v17 )
      break;
    ++v15;
    v16 += 4;
    if ( v15 >= 2 )
      goto LABEL_48;
  }
  v2 = 0;
LABEL_57:
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800ad1dc  mov     r11, rsp
0x1800ad1df  mov     [r11+10h], rbx
0x1800ad1e3  mov     [r11+18h], rsi
0x1800ad1e7  push    rdi
0x1800ad1e8  push    r12
0x1800ad1ea  push    r13
0x1800ad1ec  push    r14
0x1800ad1ee  push    r15
0x1800ad1f0  sub     rsp, 0E0h
0x1800ad1f7  mov     rax, cs:__security_cookie
0x1800ad1fe  xor     rax, rsp
0x1800ad201  mov     [rsp+108h+var_30], rax
0x1800ad209  mov     r13, rcx
0x1800ad20c  mov     [rsp+108h+var_B8], rcx
0x1800ad211  xorps   xmm0, xmm0
0x1800ad214  movups  xmmword ptr [r11-70h], xmm0
0x1800ad219  movups  xmmword ptr [r11-60h], xmm0
0x1800ad21e  mov     dword ptr [r11-70h], 20h ; ' '
0x1800ad226  xor     edi, edi
0x1800ad228  mov     [r11-78h], rdi
0x1800ad22c  lea     rax, [r11-78h]
0x1800ad230  mov     [rsp+108h+pvEncoded], rax
0x1800ad235  mov     [rsp+108h+pvEncoded+8], rdi
0x1800ad23a  mov     byte ptr [rsp+108h+var_98], 1
0x1800ad23f  lea     rax, [rsp+108h+pvEncoded+8]
0x1800ad244  mov     [rsp+108h+ppChainContext], rax; ppChainContext
0x1800ad249  mov     [rsp+108h+pvReserved], rdi; pvReserved
0x1800ad24e  mov     [rsp+108h+dwFlags], edi; dwFlags
0x1800ad252  lea     rax, [r11-70h]
0x1800ad256  mov     [rsp+108h+pChainPara], rax; pChainPara
0x1800ad25b  mov     r9, [rcx+20h]; hAdditionalStore
0x1800ad25f  xor     r8d, r8d; pTime
0x1800ad262  mov     rdx, rcx; pCertContext
0x1800ad265  xor     ecx, ecx; hChainEngine
0x1800ad267  call    cs:__imp_CertGetCertificateChain
0x1800ad26d  test    eax, eax
0x1800ad26f  jz      short loc_1800AD275
0x1800ad271  mov     esi, edi
0x1800ad273  jmp     short loc_1800AD294
0x1800ad275  call    cs:__imp_GetLastError
0x1800ad27b  test    eax, eax
0x1800ad27d  jz      short loc_1800AD28F
0x1800ad27f  movzx   esi, ax
0x1800ad282  or      esi, 80070000h
0x1800ad288  test    eax, eax
0x1800ad28a  cmovle  esi, eax
0x1800ad28d  jmp     short loc_1800AD294
0x1800ad28f  mov     esi, 80004005h
0x1800ad294  cmp     byte ptr [rsp+108h+var_98], dil
0x1800ad299  jz      short loc_1800AD2C9
0x1800ad29b  mov     r12, [rsp+108h+pvEncoded+8]
0x1800ad2a0  mov     r14, [rsp+108h+pvEncoded]
0x1800ad2a5  mov     r15, [r14]
0x1800ad2a8  test    r15, r15
0x1800ad2ab  jz      short loc_1800AD2C6
0x1800ad2ad  call    cs:__imp_GetLastError
0x1800ad2b3  mov     ebx, eax
0x1800ad2b5  mov     rcx, r15; pChainContext
0x1800ad2b8  call    cs:__imp_CertFreeCertificateChain
0x1800ad2be  mov     ecx, ebx; dwErrCode
0x1800ad2c0  call    cs:__imp_SetLastError
0x1800ad2c6  mov     [r14], r12
0x1800ad2c9  test    esi, esi
0x1800ad2cb  js      loc_1800AD55E
0x1800ad2d1  mov     rcx, [rsp+108h+pChainContext]
0x1800ad2d9  mov     esi, 800B0001h
0x1800ad2de  cmp     [rcx+0Ch], edi
0x1800ad2e1  cmova   esi, edi
0x1800ad2e4  jbe     loc_1800AD556
0x1800ad2ea  mov     rax, [rcx+10h]
0x1800ad2ee  mov     rcx, [rax]
0x1800ad2f1  mov     eax, [rcx+0Ch]
0x1800ad2f4  mov     esi, 800B0003h
0x1800ad2f9  cmp     eax, 1
0x1800ad2fc  cmova   esi, edi
0x1800ad2ff  jbe     loc_1800AD534
0x1800ad305  mov     rax, [rcx+10h]
0x1800ad309  mov     rcx, [rax+8]
0x1800ad30d  mov     rax, [rcx+8]
0x1800ad311  mov     rbx, [rax+18h]
0x1800ad315  xorps   xmm0, xmm0
0x1800ad318  movups  xmmword ptr [rsp+108h+pbComputedHash], xmm0
0x1800ad320  movups  [rsp+108h+var_40], xmm0
0x1800ad328  mov     [rsp+108h+pcbComputedHash], 20h ; ' '
0x1800ad330  add     rbx, 60h ; '`'
0x1800ad334  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CNGRefactor@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CNGRefactor@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNGRefactor> `wil::Feature<__WilFeatureTraits_Feature_CNGRefactor>::GetImpl(void)'::`2'::impl
0x1800ad33b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CNGRefactor@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNGRefactor>::__private_IsEnabled(void)
0x1800ad340  test    al, al
0x1800ad342  jz      loc_1800AD475
0x1800ad348  mov     [rsp+108h+var_C0], rbx
0x1800ad34d  mov     [rsp+108h+pcbEncoded], edi
0x1800ad354  mov     [rsp+108h+hMem], rdi
0x1800ad35c  lea     rax, [rsp+108h+hMem]
0x1800ad364  mov     [rsp+108h+pvEncoded], rax
0x1800ad369  mov     [rsp+108h+pvEncoded+8], rdi
0x1800ad36e  mov     byte ptr [rsp+108h+var_98], 1
0x1800ad373  lea     rax, [rsp+108h+pcbEncoded]
0x1800ad37b  mov     [rsp+108h+pvReserved], rax; pcbEncoded
0x1800ad380  lea     rax, [rsp+108h+pvEncoded+8]
0x1800ad385  mov     qword ptr [rsp+108h+dwFlags], rax; pvEncoded
0x1800ad38a  mov     [rsp+108h+pChainPara], rdi; pEncodePara
0x1800ad38f  mov     r9d, 8000h; dwFlags
0x1800ad395  mov     r8, rbx; pvStructInfo
0x1800ad398  mov     edx, 8; lpszStructType
0x1800ad39d  lea     ecx, [rdx-7]; dwCertEncodingType
0x1800ad3a0  call    cs:__imp_CryptEncodeObjectEx
0x1800ad3a6  test    eax, eax
0x1800ad3a8  jz      short loc_1800AD3AE
0x1800ad3aa  mov     esi, edi
0x1800ad3ac  jmp     short loc_1800AD3CD
0x1800ad3ae  call    cs:__imp_GetLastError
0x1800ad3b4  test    eax, eax
0x1800ad3b6  jz      short loc_1800AD3C8
0x1800ad3b8  movzx   esi, ax
0x1800ad3bb  or      esi, 80070000h
0x1800ad3c1  test    eax, eax
0x1800ad3c3  cmovle  esi, eax
0x1800ad3c6  jmp     short loc_1800AD3CD
0x1800ad3c8  mov     esi, 80004005h
0x1800ad3cd  cmp     byte ptr [rsp+108h+var_98], dil
0x1800ad3d2  jz      short loc_1800AD3F2
0x1800ad3d4  mov     rcx, [rsp+108h+pvEncoded]
0x1800ad3d9  mov     rdx, [rcx]
0x1800ad3dc  mov     rax, [rsp+108h+pvEncoded+8]
0x1800ad3e1  mov     [rcx], rax
0x1800ad3e4  test    rdx, rdx
0x1800ad3e7  jz      short loc_1800AD3F2
0x1800ad3e9  mov     rcx, rdx; hMem
0x1800ad3ec  call    cs:__imp_LocalFree
0x1800ad3f2  test    esi, esi
0x1800ad3f4  js      short loc_1800AD458
0x1800ad3f6  xorps   xmm0, xmm0
0x1800ad3f9  movups  xmmword ptr [rsp+108h+pvEncoded], xmm0
0x1800ad3fe  lea     rcx, [rsp+108h+pvEncoded]; phHash
0x1800ad403  call    ??0CHash@@QEAA@XZ; CHash::CHash(void)
0x1800ad408  nop
0x1800ad409  mov     eax, [rsp+108h+pcbComputedHash]
0x1800ad40d  mov     r8d, [rsp+108h+pcbEncoded]; unsigned __int64
0x1800ad415  mov     [rsp+108h+pChainPara], rax; unsigned __int64
0x1800ad41a  lea     r9, [rsp+108h+pbComputedHash]; unsigned __int8 *
0x1800ad422  mov     rdx, [rsp+108h+hMem]; void *
0x1800ad42a  lea     rcx, [rsp+108h+pvEncoded]; this
0x1800ad42f  call    ?Hash@CHash@@QEAAXPEBX_KPEAE1@Z; CHash::Hash(void const *,unsigned __int64,uchar *,unsigned __int64)
0x1800ad434  nop
0x1800ad435  mov     rcx, [rsp+108h+pvEncoded]; hHash
0x1800ad43a  test    rcx, rcx
0x1800ad43d  jz      short loc_1800AD446
0x1800ad43f  call    cs:__imp_BCryptDestroyHash
0x1800ad445  nop
0x1800ad446  jmp     short loc_1800AD458
0x1800ad448  xor     edi, edi
0x1800ad44a  mov     esi, [rsp+108h+var_C8]
0x1800ad44e  mov     rbx, [rsp+108h+var_C0]
0x1800ad453  mov     r13, [rsp+108h+var_B8]
0x1800ad458  mov     rcx, [rsp+108h+hMem]; hMem
0x1800ad460  mov     [rsp+108h+hMem], rdi
0x1800ad468  test    rcx, rcx
0x1800ad46b  jz      short loc_1800AD4CE
0x1800ad46d  call    cs:__imp_LocalFree
0x1800ad473  jmp     short loc_1800AD4CE
0x1800ad475  lea     rax, [rsp+108h+pcbComputedHash]
0x1800ad47a  mov     [rsp+108h+pvReserved], rax; pcbComputedHash
0x1800ad47f  lea     rax, [rsp+108h+pbComputedHash]
0x1800ad487  mov     qword ptr [rsp+108h+dwFlags], rax; pbComputedHash
0x1800ad48c  mov     [rsp+108h+pChainPara], rbx; pInfo
0x1800ad491  mov     r9d, 1; dwCertEncodingType
0x1800ad497  xor     r8d, r8d; dwFlags
0x1800ad49a  mov     edx, 800Ch; Algid
0x1800ad49f  xor     ecx, ecx; hCryptProv
0x1800ad4a1  call    cs:__imp_CryptHashPublicKeyInfo
0x1800ad4a7  test    eax, eax
0x1800ad4a9  jz      short loc_1800AD4AF
0x1800ad4ab  mov     esi, edi
0x1800ad4ad  jmp     short loc_1800AD4CE
0x1800ad4af  call    cs:__imp_GetLastError
0x1800ad4b5  test    eax, eax
0x1800ad4b7  jz      short loc_1800AD4C9
0x1800ad4b9  movzx   esi, ax
0x1800ad4bc  or      esi, 80070000h
0x1800ad4c2  test    eax, eax
0x1800ad4c4  cmovle  esi, eax
0x1800ad4c7  jmp     short loc_1800AD4CE
0x1800ad4c9  mov     esi, 80004005h
0x1800ad4ce  test    esi, esi
0x1800ad4d0  js      loc_1800AD55E
0x1800ad4d6  mov     esi, 800B0004h
0x1800ad4db  mov     r15, rdi
0x1800ad4de  lea     rdx, a128401004521; "1.2.840.10045.2.1"
0x1800ad4e5  mov     rcx, [rbx]
0x1800ad4e8  call    _o__stricmp_0
0x1800ad4ed  lea     rcx, qword_18017E190
0x1800ad4f4  lea     r14, qword_18017E1D0
0x1800ad4fb  test    eax, eax
0x1800ad4fd  cmovz   r14, rcx
0x1800ad501  mov     ebx, [rsp+108h+pcbComputedHash]
0x1800ad505  mov     r8d, ebx; Length
0x1800ad508  lea     rdx, [rsp+108h+pbComputedHash]; Source2
0x1800ad510  mov     rcx, r14; Source1
0x1800ad513  call    cs:__imp_RtlCompareMemory
0x1800ad519  cmp     rax, rbx
0x1800ad51c  jz      short loc_1800AD52D
0x1800ad51e  inc     r15
0x1800ad521  add     r14, 20h ; ' '
0x1800ad525  cmp     r15, 2
0x1800ad529  jb      short loc_1800AD501
0x1800ad52b  jmp     short loc_1800AD55E
0x1800ad52d  mov     esi, edi
0x1800ad52f  jmp     loc_1800AD614
0x1800ad534  mov     dword ptr [rsp+108h+pChainPara], eax
0x1800ad538  lea     r9, aUnexpectedNumb; "Unexpected number of items in certifica"...
0x1800ad53f  mov     r8d, 3E6h; unsigned int
0x1800ad545  lea     rdx, aValidatedoserv; "ValidateDOServicesCert"
0x1800ad54c  mov     ecx, 2; unsigned __int8
0x1800ad551  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800ad556  test    esi, esi
0x1800ad558  jns     loc_1800AD614
0x1800ad55e  lea     rax, aValidationOfSe; "Validation of server certificate failed"
0x1800ad565  mov     [rsp+108h+pChainPara], rax; char *
0x1800ad56a  mov     r9d, esi; int
0x1800ad56d  mov     r8d, 3EDh; unsigned int
0x1800ad573  lea     rdx, aValidatedoserv; "ValidateDOServicesCert"
0x1800ad57a  mov     ebx, 5
0x1800ad57f  mov     ecx, ebx; unsigned __int8
0x1800ad581  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x1800ad586  mov     rax, cs:?g_loggingProvider@@3PEBU_tlgProvider_t@@EB; _tlgProvider_t const * const g_loggingProvider
0x1800ad58d  test    rax, rax
0x1800ad590  jz      short loc_1800AD599
0x1800ad592  cmp     [rax], ebx
0x1800ad594  setnbe  al
0x1800ad597  jmp     short loc_1800AD59C
0x1800ad599  mov     al, dil
0x1800ad59c  test    al, al
0x1800ad59e  jz      short loc_1800AD614
0x1800ad5a0  xorps   xmm0, xmm0
0x1800ad5a3  movups  xmmword ptr [rsp+108h+pvEncoded], xmm0
0x1800ad5a8  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800ad5b0  movdqu  [rsp+108h+var_98], xmm1
0x1800ad5b6  mov     byte ptr [rsp+108h+pvEncoded], dil
0x1800ad5bb  mov     r9d, 1
0x1800ad5c1  lea     r8, [rsp+108h+pvEncoded]
0x1800ad5c6  mov     edx, [r13+10h]; cbBinary
0x1800ad5ca  mov     rcx, [r13+8]; pbBinary
0x1800ad5ce  call    _EncodeData
0x1800ad5d3  test    eax, eax
0x1800ad5d5  js      short loc_1800AD609
0x1800ad5d7  lea     rax, [rsp+108h+pvEncoded]
0x1800ad5dc  cmp     qword ptr [rsp+108h+var_98+8], 0Fh
0x1800ad5e2  cmova   rax, [rsp+108h+pvEncoded]
0x1800ad5e8  mov     [rsp+108h+pChainPara], rax
0x1800ad5ed  lea     r9, aEncodedCertifi; "Encoded certificate info: %s\n"
0x1800ad5f4  mov     r8d, 3F6h; unsigned int
0x1800ad5fa  lea     rdx, aValidatedoserv; "ValidateDOServicesCert"
0x1800ad601  mov     ecx, ebx; unsigned __int8
0x1800ad603  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800ad608  nop
0x1800ad609  lea     rcx, [rsp+108h+pvEncoded]; void *
0x1800ad60e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ad613  nop
0x1800ad614  mov     rcx, [rsp+108h+pChainContext]; pChainContext
0x1800ad61c  test    rcx, rcx
0x1800ad61f  jz      short loc_1800AD627
0x1800ad621  call    cs:__imp_CertFreeCertificateChain
0x1800ad627  mov     eax, esi
0x1800ad629  mov     rcx, [rsp+108h+var_30]
0x1800ad631  xor     rcx, rsp; StackCookie
0x1800ad634  call    __security_check_cookie
0x1800ad639  lea     r11, [rsp+108h+var_28]
0x1800ad641  mov     rbx, [r11+38h]
0x1800ad645  mov     rsi, [r11+40h]
0x1800ad649  mov     rsp, r11
0x1800ad64c  pop     r15
0x1800ad64e  pop     r14
0x1800ad650  pop     r13
0x1800ad652  pop     r12
0x1800ad654  pop     rdi
0x1800ad655  retn
```
