# VerifyAttestationToken

- ea: `0x100475a58`
- end: `0x100476483`
- name: `VerifyAttestationToken`
- size: `2603`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x100473cc0`

## callees

- `0x10040128c`
- `0x100430674`
- `0x1004306f0`
- `0x100431464`
- `0x1004700b4`
- `0x100474a74`
- `0x100475a58`
- `0x100476654`
- `0x100477f34`
- `0x100477fb8`
- `0x100478034`
- `0x100483c50`
- `0x100546cf5`
- `0x100546d0d`
- `0x100546d25`
- `0x1005480f8`
- `0x100548170`
- `0x100548210`

## import_xrefs

- `KERNEL32!Sleep` at `0x100475f2d`
- `KERNEL32!Sleep` at `0x100475f2d`
- `KERNEL32!LocalFree` at `0x100475e98`
- `KERNEL32!LocalFree` at `0x100475efc`
- `KERNEL32!LocalFree` at `0x100475e98`
- `KERNEL32!LocalFree` at `0x100475efc`
- `CRYPT32!CryptDecodeObjectEx` at `0x100475e51`
- `CRYPT32!CryptDecodeObjectEx` at `0x100475e51`
- `CRYPT32!CertFreeCertificateContext` at `0x100475ef1`
- `CRYPT32!CertFreeCertificateContext` at `0x100475ef1`
- `CRYPT32!CertCreateCertificateContext` at `0x100475dab`
- `CRYPT32!CertCreateCertificateContext` at `0x100475dab`
- `VCRUNTIME140!wcschr` at `0x100475c0d`
- `VCRUNTIME140!wcschr` at `0x100475c0d`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x100475bed`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x100475bed`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100476002`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100476047`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004762ee`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100476325`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100476385`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004763fe`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10047644f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100476002`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100476047`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004762ee`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100476325`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100476385`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004763fe`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10047644f`
- `api-ms-win-crt-convert-l1-1-0!atoll` at `0x1004760ba`
- `api-ms-win-crt-convert-l1-1-0!atoll` at `0x1004760c6`
- `api-ms-win-crt-convert-l1-1-0!atoll` at `0x1004760ba`
- `api-ms-win-crt-convert-l1-1-0!atoll` at `0x1004760c6`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1004760d1`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1004760d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall VerifyAttestationToken(
        __int64 a1,
        const wchar_t *a2,
        _BYTE *a3,
        unsigned int a4,
        void *Buf2,
        unsigned int Size,
        int a7,
        void *a8)
{
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdi
  char *v14; // rax
  char *v15; // r14
  __int64 v16; // r12
  char *v18; // rax
  char *v19; // r13
  const void *v20; // rax
  unsigned int v21; // edi
  wchar_t *v22; // rax
  __int64 v23; // rax
  unsigned int AASsigningKeys; // eax
  char *v25; // r14
  _BYTE *v26; // rsi
  _BYTE *v27; // rax
  char *v28; // rdx
  unsigned __int64 v29; // rcx
  __int64 v30; // r8
  _BYTE *v31; // rdx
  _BYTE *v32; // rcx
  char i; // al
  __int64 v34; // rax
  int v35; // eax
  PCCERT_CONTEXT CertificateContext; // rax
  const CERT_CONTEXT *v37; // r15
  BYTE *v38; // rcx
  NTSTATUS v39; // ebx
  _BYTE *v40; // rcx
  _BYTE *v41; // rcx
  BYTE *v42; // rdx
  const char *v43; // rbx
  __int64 v44; // rax
  const char *v45; // r14
  __int64 v46; // rbx
  __int64 v47; // r14
  __time64_t v48; // rax
  _BYTE *v49; // rax
  void **v50; // rcx
  __int64 v51; // rax
  char *v52; // rbx
  __int64 v53; // rax
  BYTE *v54; // rbx
  BYTE *v55; // rcx
  char *v56; // rcx
  BYTE *v57; // rcx
  void *v58; // rdx
  void *v59; // rdx
  PUCHAR v60; // rdx
  BCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *pbCertEncoded[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v63; // [rsp+58h] [rbp-A8h]
  __int64 v64; // [rsp+60h] [rbp-A0h]
  DWORD cbInput; // [rsp+6Ch] [rbp-94h] BYREF
  int v66; // [rsp+70h] [rbp-90h]
  PUCHAR pbInput; // [rsp+78h] [rbp-88h] BYREF
  void *v68[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v69; // [rsp+90h] [rbp-70h]
  void *v70[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v71; // [rsp+A8h] [rbp-58h]
  void *v72[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v73; // [rsp+C0h] [rbp-40h]
  void *v74[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v75; // [rsp+D8h] [rbp-28h]
  char v76[8]; // [rsp+E0h] [rbp-20h] BYREF
  char *v77; // [rsp+E8h] [rbp-18h]
  PUCHAR pbSignature; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v79; // [rsp+F8h] [rbp-8h]
  __int64 v80; // [rsp+100h] [rbp+0h]
  _BYTE *v81; // [rsp+108h] [rbp+8h]
  const WCHAR *pPaddingInfo; // [rsp+110h] [rbp+10h] BYREF
  __int64 v83; // [rsp+118h] [rbp+18h]
  char *v84; // [rsp+120h] [rbp+20h]
  __int64 v85; // [rsp+128h] [rbp+28h]
  _WORD v86[8]; // [rsp+130h] [rbp+30h] BYREF
  __m128i si128; // [rsp+140h] [rbp+40h]
  void *Buf1[2]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE *v89; // [rsp+160h] [rbp+60h]
  unsigned __int64 v90; // [rsp+168h] [rbp+68h]
  UCHAR pbHash[32]; // [rsp+170h] [rbp+70h] BYREF

  v85 = -2;
  v83 = a1;
  v11 = 0x500002600LL;
  while ( *a3 <= 0x22u && _bittest64(&v11, (char)*a3) )
  {
    ++a3;
    --a4;
  }
  while ( 1 )
  {
    v12 = a4 - 1;
    if ( a3[v12] > 0x22u || !_bittest64(&v11, (char)a3[v12]) )
      break;
    --a4;
  }
  v13 = a4;
  v14 = (char *)memchr_0(a3, 46, a4);
  v15 = v14;
  v84 = v14;
  v16 = 0;
  if ( !v14 )
    return 100;
  v77 = v14 + 1;
  v18 = (char *)memchr_0(v14 + 1, 46, (size_t)&a3[v13 - (_QWORD)v14 - 1]);
  v19 = v18;
  if ( !v18 )
    return 101;
  pbSignature = 0;
  v79 = 0;
  v80 = 0;
  sqlencrypt::utils::VectorBase64URLdecode(&pbSignature, v18 + 1, &a3[v13 - (_QWORD)v18 - 1]);
  v74[0] = 0;
  v74[1] = 0;
  v75 = 0;
  sqlencrypt::utils::VectorBase64URLdecode(v74, a3, v15 - a3);
  v20 = (const void *)jsonstr(v74[0], "\"alg\"", &phKey);
  if ( !v20 || !phKey || memcmp_0(v20, "RS256", (_BYTE *)phKey - (_BYTE *)v20) )
  {
    v21 = 102;
    goto LABEL_127;
  }
  hasha256(a3, (_DWORD)v19 - (_DWORD)a3, pbHash);
  jsonstr(v74[0], "\"kid\"", v76);
  if ( wcsncmp(a2, L"https://", 8u) )
  {
    v21 = 103;
    goto LABEL_127;
  }
  v21 = 104;
  v22 = wcschr(a2 + 8, 0x2Fu);
  if ( v22 )
  {
    v23 = v22 - a2;
  }
  else
  {
    v23 = -1;
    do
      ++v23;
    while ( a2[v23] );
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v86[0] = 0;
  std::basic_string<char16_t>::assign(v86, a2, (unsigned int)v23);
  v89 = 0;
  v90 = 15;
  LOBYTE(Buf1[0]) = 0;
  std::string::_Construct<char16_t const *>(Buf1);
  v66 = 0;
  *(_OWORD *)v72 = 0;
  v73 = 0;
  v63 = 0;
  v64 = 0;
  std::basic_string<char16_t>::_Construct_lv_contents(pbCertEncoded, v86);
  AASsigningKeys = GetAASsigningKeys(a1, v72, pbCertEncoded, 0);
  if ( AASsigningKeys )
  {
LABEL_60:
    v21 = AASsigningKeys;
    v26 = v72[0];
    goto LABEL_61;
  }
  v25 = v77;
LABEL_23:
  ++v21;
  v26 = v72[0];
  while ( 1 )
  {
    while ( 1 )
    {
      v27 = (_BYTE *)jsonkey(v26, v16, "\"x5c\"");
      if ( !v27 )
      {
        v35 = 0;
        v32 = v81;
        goto LABEL_39;
      }
      v28 = v27 + 1;
      if ( *v27 == 91 )
      {
        while ( 1 )
        {
          v29 = *v28;
          if ( (unsigned __int8)v29 > 0x20u )
            break;
          v30 = 0x100002600LL;
          if ( !_bittest64(&v30, v29) )
            break;
          ++v28;
        }
        v31 = v28 + 1;
        if ( (_BYTE)v29 == 34 )
          break;
      }
    }
    v32 = v31;
    v81 = v31;
    v25 = v31;
    for ( i = *v31; i && i != 34; i = *v25 )
    {
      if ( i != 92 || (v34 = 2, v25[1] != 34) )
        v34 = 1;
      v25 += v34;
    }
    v16 = v25 - v26;
    v35 = 1;
LABEL_39:
    if ( !v35 )
    {
      v16 = 0;
      if ( v66 )
        goto LABEL_61;
      v66 = 1;
      Sleep(0xBB8u);
      if ( v26 )
      {
        v40 = v26;
        if ( (unsigned __int64)(v73 - (_QWORD)v26) >= 0x1000 )
        {
          if ( ((unsigned __int8)v26 & 0x1F) != 0
            || (v26 = (_BYTE *)*((_QWORD *)v26 - 1), v26 >= v40)
            || (unsigned __int64)(v40 - v26 - 8) > 0x1F )
          {
LABEL_66:
            _invalid_parameter_noinfo_noreturn();
          }
        }
        operator delete(v26);
      }
      *(_OWORD *)v72 = 0;
      v73 = 0;
      v63 = 0;
      v64 = 0;
      std::basic_string<char16_t>::_Construct_lv_contents(pbCertEncoded, v86);
      AASsigningKeys = GetAASsigningKeys(v83, v72, pbCertEncoded, 1);
      if ( AASsigningKeys )
        goto LABEL_60;
      goto LABEL_23;
    }
    *(_OWORD *)pbCertEncoded = 0;
    v63 = 0;
    sqlencrypt::utils::VectorBase64URLdecode(pbCertEncoded, v32, v25 - v32);
    CertificateContext = CertCreateCertificateContext(
                           1u,
                           pbCertEncoded[0],
                           LODWORD(pbCertEncoded[1]) - LODWORD(pbCertEncoded[0]));
    v37 = CertificateContext;
    if ( CertificateContext )
    {
      phKey = 0;
      pbInput = 0;
      cbInput = 0;
      if ( CryptDecodeObjectEx(
             1u,
             (LPCSTR)0x48,
             CertificateContext->pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData,
             CertificateContext->pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData,
             0x8000u,
             0,
             &pbInput,
             &cbInput) )
      {
        break;
      }
    }
LABEL_41:
    v38 = pbCertEncoded[0];
    if ( pbCertEncoded[0] )
    {
      if ( v63 - (unsigned __int64)pbCertEncoded[0] >= 0x1000 )
      {
        if ( ((__int64)pbCertEncoded[0] & 0x1F) != 0 )
          goto LABEL_72;
        v38 = (BYTE *)*((_QWORD *)pbCertEncoded[0] - 1);
        if ( v38 >= pbCertEncoded[0] || (unsigned __int64)(pbCertEncoded[0] - v38 - 8) > 0x1F )
          goto LABEL_72;
      }
      operator delete(v38);
    }
  }
  if ( BCryptImportKeyPair_0(phAlgorithm, 0, L"RSAPUBLICBLOB", &phKey, pbInput, cbInput, 0) )
  {
    LocalFree(pbInput);
    goto LABEL_41;
  }
  pPaddingInfo = L"SHA256";
  v39 = BCryptVerifySignature_0(phKey, &pPaddingInfo, pbHash, 0x20u, pbSignature, v79 - (_DWORD)pbSignature, 2u);
  BCryptDestroyKey_0(phKey);
  CertFreeCertificateContext(v37);
  LocalFree(pbInput);
  if ( v39 )
    goto LABEL_41;
  v42 = pbCertEncoded[0];
  if ( pbCertEncoded[0] )
  {
    if ( v63 - (unsigned __int64)pbCertEncoded[0] >= 0x1000 )
    {
      if ( ((__int64)pbCertEncoded[0] & 0x1F) != 0
        || (v42 = (BYTE *)*((_QWORD *)pbCertEncoded[0] - 1), v42 >= pbCertEncoded[0])
        || (unsigned __int64)(pbCertEncoded[0] - v42 - 8) > 0x1F )
      {
LABEL_72:
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v42);
  }
  v70[0] = 0;
  v70[1] = 0;
  v71 = 0;
  sqlencrypt::utils::VectorBase64URLdecode(v70, v77, v19 - v84 + 1);
  ++v21;
  v43 = (const char *)jsonkey(v70[0], 0, "\"nbf\"");
  v44 = jsonkey(v70[0], 0, "\"exp\"");
  v45 = (const char *)v44;
  if ( !v43 )
    goto LABEL_117;
  if ( !v44 )
    goto LABEL_117;
  ++v21;
  v46 = atoll(v43);
  v47 = atoll(v45);
  v48 = _time64(0);
  if ( v47 < v46 )
    goto LABEL_117;
  if ( v48 < v46 - 300 )
    goto LABEL_117;
  if ( v48 > v47 + 300 )
    goto LABEL_117;
  ++v21;
  phKey = 0;
  v49 = (_BYTE *)jsonstr(v70[0], "\"iss\"", &phKey);
  if ( !phKey )
    goto LABEL_117;
  if ( !v49 )
    goto LABEL_117;
  ++v21;
  if ( (_BYTE *)((_BYTE *)phKey - v49) != v89 )
    goto LABEL_117;
  v50 = Buf1;
  if ( v90 >= 0x10 )
    v50 = (void **)Buf1[0];
  if ( memcmp_0(v50, v49, (_BYTE *)phKey - v49) )
    goto LABEL_117;
  ++v21;
  phKey = 0;
  v51 = jsonstr(v70[0], "\"aas-ehd\"", &phKey);
  if ( !v51 || !phKey )
    goto LABEL_117;
  v68[0] = 0;
  v68[1] = 0;
  v69 = 0;
  sqlencrypt::utils::VectorBase64URLdecode(v68, v51, (char *)phKey - v51);
  v52 = (char *)v68[0];
  if ( (void *)((char *)v68[1] - (char *)v68[0]) != (void *)Size || memcmp_0(v68[0], Buf2, Size) )
    goto LABEL_102;
  if ( a7 )
    goto LABEL_101;
  ++v21;
  phKey = 0;
  v53 = jsonstr(v70[0], "\"rp_data\"", &phKey);
  if ( !v53 || !phKey )
    goto LABEL_115;
  ++v21;
  pbCertEncoded[0] = 0;
  pbCertEncoded[1] = 0;
  v63 = 0;
  sqlencrypt::utils::VectorBase64URLdecode(pbCertEncoded, v53, (char *)phKey - v53);
  v54 = pbCertEncoded[0];
  if ( (BYTE *)(pbCertEncoded[1] - pbCertEncoded[0]) != (BYTE *)256 || memcmp_0(pbCertEncoded[0], a8, 0x100u) )
  {
    if ( v54 )
    {
      v57 = v54;
      if ( (unsigned __int64)(v63 - (_QWORD)v54) >= 0x1000 )
      {
        if ( ((unsigned __int8)v54 & 0x1F) != 0 )
          goto LABEL_113;
        v54 = (BYTE *)*((_QWORD *)v54 - 1);
        if ( v54 >= v57 || (unsigned __int64)(v57 - v54 - 8) > 0x1F )
          goto LABEL_113;
      }
      operator delete(v54);
    }
LABEL_115:
    v52 = (char *)v68[0];
    goto LABEL_102;
  }
  if ( !v54 )
    goto LABEL_100;
  v55 = v54;
  if ( (unsigned __int64)(v63 - (_QWORD)v54) >= 0x1000 )
  {
    if ( ((unsigned __int8)v54 & 0x1F) != 0
      || (v54 = (BYTE *)*((_QWORD *)v54 - 1), v54 >= v55)
      || (unsigned __int64)(v55 - v54 - 8) > 0x1F )
    {
LABEL_113:
      _invalid_parameter_noinfo_noreturn();
    }
  }
  operator delete(v54);
LABEL_100:
  v52 = (char *)v68[0];
LABEL_101:
  v21 = 0;
LABEL_102:
  if ( v52 )
  {
    v56 = v52;
    if ( (unsigned __int64)(v69 - (_QWORD)v52) >= 0x1000 )
    {
      if ( ((unsigned __int8)v52 & 0x1F) != 0
        || (v52 = (char *)*((_QWORD *)v52 - 1), v52 >= v56)
        || (unsigned __int64)(v56 - v52 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v52);
    *(_OWORD *)v68 = 0;
    v69 = 0;
  }
LABEL_117:
  v58 = v70[0];
  if ( v70[0] )
  {
    if ( v71 - (unsigned __int64)v70[0] >= 0x1000 )
    {
      if ( ((__int64)v70[0] & 0x1F) != 0
        || (v58 = (void *)*((_QWORD *)v70[0] - 1), v58 >= v70[0])
        || (unsigned __int64)((char *)v70[0] - (char *)v58 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v58);
    *(_OWORD *)v70 = 0;
    v71 = 0;
  }
LABEL_61:
  if ( v26 )
  {
    v41 = v26;
    if ( (unsigned __int64)(v73 - (_QWORD)v26) >= 0x1000 )
    {
      if ( ((unsigned __int8)v26 & 0x1F) != 0 )
        goto LABEL_66;
      v26 = (_BYTE *)*((_QWORD *)v26 - 1);
      if ( v26 >= v41 || (unsigned __int64)(v41 - v26 - 8) > 0x1F )
        goto LABEL_66;
    }
    operator delete(v26);
  }
  std::string::_Tidy_deallocate(Buf1);
  std::basic_string<char16_t>::_Tidy_deallocate(v86);
LABEL_127:
  v59 = v74[0];
  if ( v74[0] )
  {
    if ( v75 - (unsigned __int64)v74[0] >= 0x1000 )
    {
      if ( ((__int64)v74[0] & 0x1F) != 0
        || (v59 = (void *)*((_QWORD *)v74[0] - 1), v59 >= v74[0])
        || (unsigned __int64)((char *)v74[0] - (char *)v59 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v59);
    *(_OWORD *)v74 = 0;
    v75 = 0;
  }
  v60 = pbSignature;
  if ( pbSignature )
  {
    if ( (unsigned __int64)(v80 - (_QWORD)pbSignature) >= 0x1000 )
    {
      if ( ((unsigned __int8)pbSignature & 0x1F) != 0
        || (v60 = (PUCHAR)*((_QWORD *)pbSignature - 1), v60 >= pbSignature)
        || (unsigned __int64)(pbSignature - v60 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v60);
  }
  return v21;
}

```

## disassembly

```asm
0x100475a58  push    rbp
0x100475a5a  push    rbx
0x100475a5b  push    rsi
0x100475a5c  push    rdi
0x100475a5d  push    r12
0x100475a5f  push    r13
0x100475a61  push    r14
0x100475a63  push    r15
0x100475a65  lea     rbp, [rsp-0A8h]
0x100475a6d  sub     rsp, 1A8h
0x100475a74  mov     [rbp+0E0h+var_B8], 0FFFFFFFFFFFFFFFEh
0x100475a7c  mov     rax, cs:__security_cookie
0x100475a83  xor     rax, rsp
0x100475a86  mov     [rbp+0E0h+var_50], rax
0x100475a8d  mov     rbx, r8
0x100475a90  mov     rsi, rdx
0x100475a93  mov     r15, rcx
0x100475a96  mov     [rbp+0E0h+var_C8], rcx
0x100475a9a  mov     rdx, 500002600h
0x100475aa4  cmp     byte ptr [rbx], 22h ; '"'
0x100475aa7  ja      short loc_100475ABB
0x100475aa9  movsx   rax, byte ptr [rbx]
0x100475aad  bt      rdx, rax
0x100475ab1  jnb     short loc_100475ABB
0x100475ab3  inc     rbx
0x100475ab6  dec     r9d
0x100475ab9  jmp     short loc_100475AA4
0x100475abb  lea     ecx, [r9-1]
0x100475abf  cmp     byte ptr [rcx+rbx], 22h ; '"'
0x100475ac3  ja      short loc_100475AD5
0x100475ac5  movsx   rax, byte ptr [rcx+rbx]
0x100475aca  bt      rdx, rax
0x100475ace  jnb     short loc_100475AD5
0x100475ad0  mov     r9d, ecx
0x100475ad3  jmp     short loc_100475ABB
0x100475ad5  mov     edi, r9d
0x100475ad8  mov     r8d, r9d; MaxCount
0x100475adb  mov     r13d, 2Eh ; '.'
0x100475ae1  mov     edx, r13d; Val
0x100475ae4  mov     rcx, rbx; Buf
0x100475ae7  call    memchr_0
0x100475aec  mov     r14, rax
0x100475aef  mov     [rbp+0E0h+var_C0], rax
0x100475af3  xor     r12d, r12d
0x100475af6  test    rax, rax
0x100475af9  jnz     short loc_100475B04
0x100475afb  lea     eax, [r13+36h]
0x100475aff  jmp     loc_100476460
0x100475b04  lea     rcx, [rax+1]; Buf
0x100475b08  mov     [rbp+0E0h+var_F8], rcx
0x100475b0c  mov     r8, rdi
0x100475b0f  sub     r8, r14
0x100475b12  dec     r8
0x100475b15  add     r8, rbx; MaxCount
0x100475b18  mov     edx, r13d; Val
0x100475b1b  call    memchr_0
0x100475b20  mov     r13, rax
0x100475b23  test    rax, rax
0x100475b26  jnz     short loc_100475B31
0x100475b28  lea     eax, [r13+65h]
0x100475b2c  jmp     loc_100476460
0x100475b31  mov     [rbp+0E0h+pbSignature], r12
0x100475b35  mov     [rbp+0E0h+var_E8], r12
0x100475b39  mov     [rbp+0E0h+var_E0], r12
0x100475b3d  sub     rdi, r13
0x100475b40  lea     r8, [rdi-1]
0x100475b44  add     r8, rbx
0x100475b47  lea     rdx, [rax+1]
0x100475b4b  lea     rcx, [rbp+0E0h+pbSignature]
0x100475b4f  call    ?VectorBase64URLdecode@utils@sqlencrypt@@YA_KAEAV?$vector@DV?$allocator@D@std@@@std@@PEAD_K@Z; sqlencrypt::utils::VectorBase64URLdecode(std::vector<char> &,char *,unsigned __int64)
0x100475b54  mov     [rbp+0E0h+var_118], r12
0x100475b58  mov     [rbp+0E0h+var_118+8], r12
0x100475b5c  mov     [rbp+0E0h+var_108], r12
0x100475b60  mov     r8, r14
0x100475b63  sub     r8, rbx
0x100475b66  mov     rdx, rbx
0x100475b69  lea     rcx, [rbp+0E0h+var_118]
0x100475b6d  call    ?VectorBase64URLdecode@utils@sqlencrypt@@YA_KAEAV?$vector@DV?$allocator@D@std@@@std@@PEAD_K@Z; sqlencrypt::utils::VectorBase64URLdecode(std::vector<char> &,char *,unsigned __int64)
0x100475b72  lea     r8, [rsp+1E0h+phKey]
0x100475b77  lea     rdx, aAlg; "\"alg\""
0x100475b7e  mov     rcx, [rbp+0E0h+var_118]
0x100475b82  call    jsonstr
0x100475b87  test    rax, rax
0x100475b8a  jz      loc_1004763C3
0x100475b90  mov     r8, [rsp+1E0h+phKey]
0x100475b95  test    r8, r8
0x100475b98  jz      loc_1004763C3
0x100475b9e  sub     r8, rax; Size
0x100475ba1  lea     rdx, aRs256; "RS256"
0x100475ba8  mov     rcx, rax; Buf1
0x100475bab  call    memcmp_0
0x100475bb0  test    eax, eax
0x100475bb2  jnz     loc_1004763C3
0x100475bb8  mov     edx, r13d
0x100475bbb  sub     edx, ebx; cbInput
0x100475bbd  lea     r8, [rbp+0E0h+pbHash]; pbOutput
0x100475bc1  mov     rcx, rbx; pbInput
0x100475bc4  call    hasha256
0x100475bc9  lea     r8, [rbp+0E0h+var_100]
0x100475bcd  lea     rdx, aKid; "\"kid\""
0x100475bd4  mov     rcx, [rbp+0E0h+var_118]
0x100475bd8  call    jsonstr
0x100475bdd  mov     r8d, 8; MaxCount
0x100475be3  lea     rdx, aHttps; "https://"
0x100475bea  mov     rcx, rsi; String1
0x100475bed  call    cs:__imp_wcsncmp
0x100475bf3  test    eax, eax
0x100475bf5  jz      short loc_100475C01
0x100475bf7  mov     edi, 67h ; 'g'
0x100475bfc  jmp     loc_1004763C8
0x100475c01  mov     edi, 68h ; 'h'
0x100475c06  lea     edx, [rdi-39h]; Ch
0x100475c09  lea     rcx, [rsi+10h]; Str
0x100475c0d  call    cs:__imp_wcschr
0x100475c13  test    rax, rax
0x100475c16  jz      short loc_100475C20
0x100475c18  sub     rax, rsi
0x100475c1b  sar     rax, 1
0x100475c1e  jmp     short loc_100475C2E
0x100475c20  or      rax, 0FFFFFFFFFFFFFFFFh
0x100475c24  inc     rax
0x100475c27  cmp     [rsi+rax*2], r12w
0x100475c2c  jnz     short loc_100475C24
0x100475c2e  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100475c36  movdqu  [rbp+0E0h+var_A0], xmm0
0x100475c3b  mov     [rbp+0E0h+var_B0], r12w
0x100475c40  mov     r8d, eax
0x100475c43  mov     rdx, rsi
0x100475c46  lea     rcx, [rbp+0E0h+var_B0]
0x100475c4a  call    ?assign@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::assign(char16_t const * const,unsigned __int64)
0x100475c4f  nop
0x100475c50  lea     rcx, [rbp+0E0h+var_B0]
0x100475c54  cmp     qword ptr [rbp+0E0h+var_A0+8], 8
0x100475c59  cmovnb  rcx, qword ptr [rbp+0E0h+var_B0]
0x100475c5e  mov     rax, qword ptr [rbp+0E0h+var_A0]
0x100475c62  lea     r8, [rcx+rax*2]
0x100475c66  lea     rdx, [rbp+0E0h+var_B0]
0x100475c6a  cmovnb  rdx, qword ptr [rbp+0E0h+var_B0]
0x100475c6f  mov     [rbp+0E0h+var_80], r12
0x100475c73  mov     [rbp+0E0h+var_78], 0Fh
0x100475c7b  mov     byte ptr [rbp+0E0h+Buf1], r12b
0x100475c7f  mov     r9b, [rsp+1E0h+var_178]
0x100475c84  lea     rcx, [rbp+0E0h+Buf1]; Src
0x100475c88  call    ??$_Construct@PEB_S@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEB_S0Uforward_iterator_tag@1@@Z; std::string::_Construct<char16_t const *>(char16_t const * const,char16_t const * const,std::forward_iterator_tag)
0x100475c8d  nop
0x100475c8e  mov     [rsp+1E0h+var_170], r12d
0x100475c93  xorps   xmm0, xmm0
0x100475c96  movdqu  xmmword ptr [rbp+0E0h+var_130], xmm0
0x100475c9b  mov     [rbp+0E0h+var_120], r12
0x100475c9f  mov     [rsp+1E0h+var_188], r12
0x100475ca4  mov     [rsp+1E0h+var_180], r12
0x100475ca9  lea     rdx, [rbp+0E0h+var_B0]
0x100475cad  lea     rcx, [rsp+1E0h+pbCertEncoded]
0x100475cb2  call    ?_Construct_lv_contents@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAXAEBV12@@Z; std::basic_string<char16_t>::_Construct_lv_contents(std::basic_string<char16_t> const &)
0x100475cb7  xor     r9d, r9d
0x100475cba  lea     r8, [rsp+1E0h+pbCertEncoded]
0x100475cbf  lea     rdx, [rbp+0E0h+var_130]
0x100475cc3  mov     rcx, r15
0x100475cc6  call    GetAASsigningKeys
0x100475ccb  test    eax, eax
0x100475ccd  jnz     loc_100475FBE
0x100475cd3  mov     r14, [rbp+0E0h+var_F8]
0x100475cd7  inc     edi
0x100475cd9  mov     rsi, [rbp+0E0h+var_130]
0x100475cdd  xor     ebx, ebx
0x100475cdf  lea     r8, aX5c; "\"x5c\""
0x100475ce6  mov     rdx, r12
0x100475ce9  mov     rcx, rsi
0x100475cec  call    jsonkey
0x100475cf1  test    rax, rax
0x100475cf4  mov     rdx, rax
0x100475cf7  jz      short loc_100475D6A
0x100475cf9  mov     cl, [rax]
0x100475cfb  inc     rdx
0x100475cfe  cmp     cl, 5Bh ; '['
0x100475d01  jnz     short loc_100475CDF
0x100475d03  movsx   rcx, byte ptr [rdx]
0x100475d07  cmp     cl, 20h ; ' '
0x100475d0a  ja      short loc_100475D21
0x100475d0c  mov     r8, 100002600h
0x100475d16  bt      r8, rcx
0x100475d1a  jnb     short loc_100475D21
0x100475d1c  inc     rdx
0x100475d1f  jmp     short loc_100475D03
0x100475d21  inc     rdx
0x100475d24  mov     r8b, 22h ; '"'
0x100475d27  cmp     cl, r8b
0x100475d2a  jnz     short loc_100475CDF
0x100475d2c  mov     rcx, rdx
0x100475d2f  mov     [rbp+0E0h+var_D8], rdx
0x100475d33  mov     r14, rdx
0x100475d36  mov     al, [rdx]
0x100475d38  jmp     short loc_100475D59
0x100475d3a  cmp     al, r8b
0x100475d3d  jz      short loc_100475D5D
0x100475d3f  cmp     al, 5Ch ; '\'
0x100475d41  jnz     short loc_100475D4E
0x100475d43  cmp     [r14+1], r8b
0x100475d47  mov     eax, 2
0x100475d4c  jz      short loc_100475D53
0x100475d4e  mov     eax, 1
0x100475d53  add     r14, rax
0x100475d56  mov     al, [r14]
0x100475d59  test    al, al
0x100475d5b  jnz     short loc_100475D3A
0x100475d5d  mov     r12, r14
0x100475d60  sub     r12, rsi
0x100475d63  mov     eax, 1
0x100475d68  jmp     short loc_100475D70
0x100475d6a  mov     eax, ebx
0x100475d6c  mov     rcx, [rbp+0E0h+var_D8]
0x100475d70  test    eax, eax
0x100475d72  jz      loc_100475F12
0x100475d78  xorps   xmm0, xmm0
0x100475d7b  movdqu  xmmword ptr [rsp+1E0h+pbCertEncoded], xmm0
0x100475d81  mov     [rsp+1E0h+var_188], rbx
0x100475d86  mov     r8, r14
0x100475d89  sub     r8, rcx
0x100475d8c  mov     rdx, rcx
0x100475d8f  lea     rcx, [rsp+1E0h+pbCertEncoded]
0x100475d94  call    ?VectorBase64URLdecode@utils@sqlencrypt@@YA_KAEAV?$vector@DV?$allocator@D@std@@@std@@PEAD_K@Z; sqlencrypt::utils::VectorBase64URLdecode(std::vector<char> &,char *,unsigned __int64)
0x100475d99  mov     r8, [rsp+1E0h+pbCertEncoded+8]
0x100475d9e  mov     rdx, [rsp+1E0h+pbCertEncoded]; pbCertEncoded
0x100475da3  sub     r8, rdx; cbCertEncoded
0x100475da6  mov     ecx, 1; dwCertEncodingType
0x100475dab  call    cs:__imp_CertCreateCertificateContext
0x100475db1  mov     r15, rax
0x100475db4  test    rax, rax
0x100475db7  jnz     short loc_100475E0B
0x100475db9  mov     rcx, [rsp+1E0h+pbCertEncoded]
0x100475dbe  test    rcx, rcx
0x100475dc1  jz      loc_100475CDF
0x100475dc7  mov     rax, [rsp+1E0h+var_188]
0x100475dcc  sub     rax, rcx
0x100475dcf  cmp     rax, 1000h
0x100475dd5  mov     rdx, rcx
0x100475dd8  jb      short loc_100475E01
0x100475dda  test    dl, 1Fh
0x100475ddd  jnz     loc_100476047
0x100475de3  mov     rcx, [rcx-8]; void *
0x100475de7  cmp     rcx, rdx
0x100475dea  jnb     loc_100476047
0x100475df0  sub     rdx, rcx
0x100475df3  sub     rdx, 8
0x100475df7  cmp     rdx, 1Fh
0x100475dfb  ja      loc_100476047
0x100475e01  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100475e06  jmp     loc_100475CDF
0x100475e0b  mov     [rsp+1E0h+phKey], rbx
0x100475e10  mov     [rsp+1E0h+pbInput], rbx
0x100475e15  mov     [rsp+1E0h+cbInput], ebx
0x100475e19  mov     r8, [rax+18h]
0x100475e1d  lea     rax, [rsp+1E0h+cbInput]
0x100475e22  mov     [rsp+1E0h+pcbStructInfo], rax; pcbStructInfo
0x100475e27  lea     rax, [rsp+1E0h+pbInput]
0x100475e2c  mov     [rsp+1E0h+pvStructInfo], rax; pvStructInfo
0x100475e31  mov     [rsp+1E0h+pDecodePara], rbx; pDecodePara
0x100475e36  mov     [rsp+1E0h+dwFlags], 8000h; dwFlags
0x100475e3e  mov     r9d, [r8+78h]; cbEncoded
0x100475e42  mov     r8, [r8+80h]; pbEncoded
0x100475e49  mov     edx, 48h ; 'H'; lpszStructType
0x100475e4e  lea     ecx, [rdx-47h]; dwCertEncodingType
0x100475e51  call    cs:__imp_CryptDecodeObjectEx
0x100475e57  test    eax, eax
0x100475e59  jz      loc_100475DB9
0x100475e5f  mov     dword ptr [rsp+1E0h+pvStructInfo], ebx; dwFlags
0x100475e63  mov     eax, [rsp+1E0h+cbInput]
0x100475e67  mov     dword ptr [rsp+1E0h+pDecodePara], eax; cbInput
0x100475e6b  mov     rax, [rsp+1E0h+pbInput]
0x100475e70  mov     qword ptr [rsp+1E0h+dwFlags], rax; pbInput
0x100475e75  lea     r9, [rsp+1E0h+phKey]; phKey
0x100475e7a  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x100475e81  xor     edx, edx; hImportKey
0x100475e83  mov     rcx, cs:phAlgorithm; hAlgorithm
0x100475e8a  call    BCryptImportKeyPair_0
0x100475e8f  test    eax, eax
0x100475e91  jz      short loc_100475EA3
0x100475e93  mov     rcx, [rsp+1E0h+pbInput]; hMem
0x100475e98  call    cs:__imp_LocalFree
0x100475e9e  jmp     loc_100475DB9
0x100475ea3  lea     rax, aSha256; "SHA256"
0x100475eaa  mov     [rbp+0E0h+pPaddingInfo], rax
0x100475eae  mov     rcx, [rbp+0E0h+var_E8]
0x100475eb2  mov     rax, [rbp+0E0h+pbSignature]
0x100475eb6  sub     rcx, rax
0x100475eb9  mov     dword ptr [rsp+1E0h+pvStructInfo], 2; dwFlags
0x100475ec1  mov     dword ptr [rsp+1E0h+pDecodePara], ecx; cbSignature
0x100475ec5  mov     qword ptr [rsp+1E0h+dwFlags], rax; pbSignature
0x100475eca  mov     r9d, 20h ; ' '; cbHash
0x100475ed0  lea     r8, [rbp+0E0h+pbHash]; pbHash
0x100475ed4  lea     rdx, [rbp+0E0h+pPaddingInfo]; pPaddingInfo
0x100475ed8  mov     rcx, [rsp+1E0h+phKey]; hKey
0x100475edd  call    BCryptVerifySignature_0
0x100475ee2  mov     ebx, eax
0x100475ee4  mov     rcx, [rsp+1E0h+phKey]; hKey
0x100475ee9  call    BCryptDestroyKey_0
0x100475eee  mov     rcx, r15; pCertContext
0x100475ef1  call    cs:__imp_CertFreeCertificateContext
0x100475ef7  mov     rcx, [rsp+1E0h+pbInput]; hMem
0x100475efc  call    cs:__imp_LocalFree
  ... truncated ...
```
