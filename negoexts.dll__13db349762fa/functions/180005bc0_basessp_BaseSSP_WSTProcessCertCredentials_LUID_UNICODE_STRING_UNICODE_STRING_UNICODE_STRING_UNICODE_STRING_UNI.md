# basessp::BaseSSP::WSTProcessCertCredentials(_LUID *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_SEC_WINNT_AUTH_PACKED_CREDENTIALS * *,ulong *)

- ea: `0x180005bc0`
- end: `0x18000637e`
- name: `?WSTProcessCertCredentials@BaseSSP@basessp@@AEAAJPEAU_LUID@@PEAU_UNICODE_STRING@@1111PEAPEAU_SEC_WINNT_AUTH_PACKED_CREDENTIALS@@PEAK@Z`
- size: `1982`
- prototype: `__int64 __usercall@<rax>(basessp::BaseSSP *__hidden this@<rcx>, struct _LUID *@<rdx>, struct _UNICODE_STRING *@<r8>, struct _UNICODE_STRING *@<r9>, struct _UNICODE_STRING *, PUNICODE_STRING DestinationString, struct _UNICODE_STRING *, struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004404`

## callees

- `0x180005960`
- `0x180005998`
- `0x180005bc0`
- `0x180006390`
- `0x180006650`
- `0x18000ba90`
- `0x18000ebcc`
- `0x18000ec28`
- `0x18001d71c`
- `0x18001db40`
- `0x18001dc88`
- `0x18001e2b4`
- `0x18001ece2`
- `0x18001ecee`
- `0x18001ed20`
- `0x18001edb0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005f66`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006078`
- `ntdll!NtClose` at `0x180006322`
- `ntdll!NtClose` at `0x180006322`
- `ntdll!RtlInitUnicodeString` at `0x180005c7b`
- `ntdll!RtlInitUnicodeString` at `0x180005c86`
- `ntdll!RtlInitUnicodeString` at `0x180005c7b`
- `ntdll!RtlInitUnicodeString` at `0x180005c86`
- `CRYPT32!CertCloseStore` at `0x180006317`
- `CRYPT32!CertCloseStore` at `0x180006317`
- `CRYPT32!CertOpenStore` at `0x180005fc5`
- `CRYPT32!CertOpenStore` at `0x180005fc5`
- `CRYPT32!CertFindCertificateInStore` at `0x18000604b`
- `CRYPT32!CertFindCertificateInStore` at `0x18000604b`
- `CRYPT32!CertFreeCertificateContext` at `0x180006303`
- `CRYPT32!CertFreeCertificateContext` at `0x180006303`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800060d9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800060ed`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800060d9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800060ed`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18000634f`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18000634f`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x180005cd3`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x180005cd3`

## pseudocode

```c
__int64 __fastcall basessp::BaseSSP::WSTProcessCertCredentials(
        basessp::BaseSSP *this,
        struct _LUID *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5,
        PUNICODE_STRING DestinationString,
        struct _UNICODE_STRING *a7,
        struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **a8,
        unsigned int *a9)
{
  _BYTE *v9; // r12
  WCHAR *p_Size; // rsi
  unsigned __int64 v13; // rdi
  WCHAR *p_MarshaledCredential; // rdi
  int v15; // r14d
  void (*v16)(void); // rax
  void (*v17)(void); // rax
  void (*v18)(void); // rax
  unsigned __int8 *v19; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  _BYTE *v23; // rdx
  __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  void *v26; // rsp
  void *v27; // rsp
  WCHAR *v28; // rax
  HCERTSTORE v29; // r15
  const CERT_CONTEXT *v30; // rdi
  const CERT_CONTEXT *CertificateInStore; // rax
  DWORD LastError; // eax
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r9
  unsigned __int8 v36; // r9
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rcx
  void *(*v40)(unsigned __int64); // rdx
  basessp *v41; // rcx
  struct _UNICODE_STRING v42; // xmm1
  __int64 v43; // [rsp+0h] [rbp-50h] BYREF
  void *pvPara; // [rsp+20h] [rbp-30h]
  PCCERT_CONTEXT pPrevCertContext; // [rsp+28h] [rbp-28h]
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **v46; // [rsp+30h] [rbp-20h]
  size_t Size; // [rsp+50h] [rbp+0h] BYREF
  _CRED_MARSHAL_TYPE CredType; // [rsp+58h] [rbp+8h] BYREF
  void *v49; // [rsp+60h] [rbp+10h] BYREF
  HANDLE Token; // [rsp+68h] [rbp+18h] BYREF
  unsigned __int8 *Src; // [rsp+70h] [rbp+20h] BYREF
  PVOID Credential; // [rsp+78h] [rbp+28h] BYREF
  struct _UNICODE_STRING v53; // [rsp+80h] [rbp+30h] BYREF
  struct _UNICODE_STRING v54; // [rsp+90h] [rbp+40h] BYREF
  struct _LUID *v55; // [rsp+A0h] [rbp+50h]
  struct _UNICODE_STRING *v56; // [rsp+A8h] [rbp+58h]
  struct _UNICODE_STRING *v57; // [rsp+B0h] [rbp+60h]
  struct _UNICODE_STRING *v58; // [rsp+B8h] [rbp+68h]
  struct _UNICODE_STRING *v59; // [rsp+C0h] [rbp+70h]
  __int128 pvFindPara; // [rsp+C8h] [rbp+78h] BYREF
  struct _UNICODE_STRING v61; // [rsp+D8h] [rbp+88h] BYREF
  unsigned int v62; // [rsp+F0h] [rbp+A0h] BYREF
  struct _UNICODE_STRING v63; // [rsp+F8h] [rbp+A8h] BYREF
  struct _UNICODE_STRING v64; // [rsp+108h] [rbp+B8h] BYREF
  struct _UNICODE_STRING v65; // [rsp+118h] [rbp+C8h] BYREF
  struct _UNICODE_STRING v66; // [rsp+128h] [rbp+D8h] BYREF
  WCHAR MarshaledCredential; // [rsp+150h] [rbp+100h] BYREF

  v9 = 0;
  v55 = a2;
  v57 = a5;
  v58 = DestinationString;
  v59 = a7;
  CredType = 0;
  pvFindPara = 0;
  Size = 0;
  v56 = a4;
  memset_0(&v62, 0, 0x48u);
  Credential = 0;
  Token = 0;
  Src = 0;
  v49 = 0;
  v53 = 0;
  v54 = 0;
  v61 = 0;
  RtlInitUnicodeString(DestinationString, 0);
  RtlInitUnicodeString(a7, 0);
  *a8 = 0;
  p_Size = 0;
  *a9 = 0;
  v13 = a3->Length + 2LL;
  if ( v13 >= 0x402 )
  {
    if ( v13 > g_ulMaxStackAllocSize || v13 + g_ulAdditionalProbeSize + 8 < v13 || !(unsigned int)VerifyStackAvailable() )
      goto LABEL_104;
    v24 = v13 + 23;
    if ( v13 + 23 <= v13 + 8 )
      v24 = 0xFFFFFFFFFFFFFF0LL;
    v25 = v24 & 0xFFFFFFFFFFFFFFF0uLL;
    v26 = alloca(v25);
    v27 = alloca(v25);
    p_Size = (WCHAR *)&Size;
    if ( &v43 == (__int64 *)-80LL || (LODWORD(Size) = 1801679955, (p_Size = (WCHAR *)&CredType) == 0) )
    {
LABEL_104:
      if ( v13 + 8 >= v13 )
      {
        v28 = (WCHAR *)((__int64 (*)(void))g_pfnAllocate)();
        p_Size = v28;
        if ( v28 )
        {
          *(_DWORD *)v28 = 1885431112;
          p_Size = v28 + 4;
        }
      }
    }
    if ( !p_Size )
    {
      v15 = -1073741801;
      goto LABEL_4;
    }
    p_MarshaledCredential = p_Size;
  }
  else
  {
    p_MarshaledCredential = &MarshaledCredential;
  }
  v15 = -1073741275;
  memcpy_0(p_MarshaledCredential, a3->Buffer, a3->Length);
  if ( CredUnmarshalCredentialW(p_MarshaledCredential, &CredType, &Credential) && CredType == CertCredential )
  {
    if ( v55 )
    {
      v15 = (*(__int64 (__fastcall **)(struct _LUID *, HANDLE *))(*((_QWORD *)this + 30) + 368LL))(v55, &Token);
      if ( v15 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            &WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids,
            (unsigned int)v15);
        goto LABEL_4;
      }
      if ( !SetThreadToken(0, Token) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids);
        v15 = -1073741555;
        goto LABEL_4;
      }
    }
    v29 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x10000u, L"MY");
    if ( !v29 )
    {
      v30 = 0;
      v15 = -2146893042;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids);
      goto LABEL_68;
    }
    *((_QWORD *)&pvFindPara + 1) = (char *)Credential + 4;
    LODWORD(pvFindPara) = 20;
    CertificateInStore = CertFindCertificateInStore(v29, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
    v30 = CertificateInStore;
    if ( CertificateInStore )
    {
      v15 = basessp::BaseSSP::WSTGetCspDataForCert(
              this,
              CertificateInStore,
              (struct basessp::_WST_CSPDATA_DETAIL *)&v62);
      if ( v15 >= 0 )
      {
        RevertToSelf();
        v15 = basessp::BaseSSP::WSTBuildSCLogonInfo(
                this,
                v63.Buffer,
                v64.Buffer,
                v65.Buffer,
                v66.Buffer,
                v62,
                &Src,
                (unsigned int *)&Size);
        if ( v15 >= 0 )
        {
          v15 = basessp::BaseSSP::WSTDuplicateStringEx(this, &v61, v56, v36);
          if ( v15 >= 0 )
          {
            v15 = basessp::BaseSSP::WSTParseHintsFromDomainName(this, &v61, &v53, &v54);
            if ( v15 >= 0 )
            {
              LODWORD(pPrevCertContext) = Size;
              v15 = basessp::BaseSSP::WSTCreateCertLogonBuffer(
                      this,
                      v57,
                      &v54,
                      &v53,
                      Src,
                      (size_t)pPrevCertContext,
                      (unsigned int)v46,
                      &v49,
                      (unsigned int *)&Size + 1);
              if ( v15 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    21,
                    &WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids,
                    (unsigned int)v15);
                v9 = v49;
                goto LABEL_93;
              }
              v39 = *((_QWORD *)this + 30);
              v9 = v49;
              v40 = *(void *(**)(unsigned __int64))(v39 + 392);
              v41 = *(basessp **)(v39 + 384);
              LODWORD(pvPara) = HIDWORD(Size);
              v15 = basessp::WSTConvertLegacySCardBufferToEx2PackedCreds(
                      v41,
                      v40,
                      (void (*)(void *))Token,
                      v49,
                      pvPara,
                      (unsigned int)a8,
                      v46);
              if ( v15 >= 0 )
              {
                v15 = 0;
                v42 = v54;
                *v58 = v53;
                v53 = 0;
                *v59 = v42;
                v54 = 0;
                goto LABEL_93;
              }
              v37 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_93;
              v38 = 22;
            }
            else
            {
              v37 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_93;
              v38 = 20;
            }
          }
          else
          {
            v37 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_93;
            v38 = 19;
          }
        }
        else
        {
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_93;
          v38 = 18;
        }
        WPP_SF_d(v37[2], v38, &WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids, (unsigned int)v15);
LABEL_93:
        CertFreeCertificateContext(v30);
        goto LABEL_94;
      }
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_68:
        RevertToSelf();
        if ( !v30 )
        {
LABEL_94:
          if ( v29 )
            CertCloseStore(v29, 0);
          goto LABEL_4;
        }
        goto LABEL_93;
      }
      v34 = 17;
      v35 = (unsigned int)v15;
    }
    else
    {
      v15 = -2146893042;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_68;
      LastError = GetLastError();
      v33 = WPP_GLOBAL_Control;
      v34 = 16;
      v35 = LastError;
    }
    WPP_SF_d(v33[2], v34, &WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids, v35);
    goto LABEL_68;
  }
LABEL_4:
  if ( Token )
    NtClose(Token);
  if ( p_Size && *((_DWORD *)p_Size - 2) == 1885431112 )
    ((void (__fastcall *)(WCHAR *))g_pfnFree)(p_Size - 4);
  if ( Credential )
    CredFree(Credential);
  basessp::BaseSSP::WSTFreeString(this, &v63);
  basessp::BaseSSP::WSTFreeString(this, &v65);
  basessp::BaseSSP::WSTFreeString(this, &v66);
  basessp::BaseSSP::WSTFreeString(this, &v64);
  if ( v53.Buffer )
  {
    if ( *((_DWORD *)this + 52) == 1 )
      v16 = *(void (**)(void))(*((_QWORD *)this + 30) + 392LL);
    else
      v16 = *(void (**)(void))(*((_QWORD *)this + 31) + 8LL);
    v16();
  }
  if ( v54.Buffer )
  {
    if ( *((_DWORD *)this + 52) == 1 )
      v17 = *(void (**)(void))(*((_QWORD *)this + 30) + 392LL);
    else
      v17 = *(void (**)(void))(*((_QWORD *)this + 31) + 8LL);
    v17();
  }
  if ( v61.Buffer )
  {
    if ( *((_DWORD *)this + 52) == 1 )
      v18 = *(void (**)(void))(*((_QWORD *)this + 30) + 392LL);
    else
      v18 = *(void (**)(void))(*((_QWORD *)this + 31) + 8LL);
    v18();
  }
  v19 = Src;
  if ( Src )
  {
    v21 = (unsigned int)Size;
    if ( (_DWORD)Size )
    {
      do
      {
        *v19++ = 0;
        --v21;
      }
      while ( v21 );
    }
    basessp::BaseSSP::WSTFree(this, Src);
  }
  if ( v9 )
  {
    v22 = HIDWORD(Size);
    v23 = v9;
    if ( HIDWORD(Size) )
    {
      do
      {
        *v23++ = 0;
        --v22;
      }
      while ( v22 );
    }
    basessp::BaseSSP::WSTFree(this, v9);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180005bc0  push    rbp
0x180005bc2  push    rbx
0x180005bc3  push    rsi
0x180005bc4  push    rdi
0x180005bc5  push    r12
0x180005bc7  push    r13
0x180005bc9  push    r14
0x180005bcb  push    r15
0x180005bcd  sub     rsp, 578h
0x180005bd4  lea     rbp, [rsp+50h]
0x180005bd9  mov     rax, cs:__security_cookie
0x180005be0  xor     rax, rbp
0x180005be3  mov     [rbp+560h+var_50], rax
0x180005bea  mov     rax, [rbp+560h+arg_20]
0x180005bf1  xor     r12d, r12d
0x180005bf4  mov     rsi, [rbp+560h+DestinationString]
0x180005bfb  mov     r15, r8
0x180005bfe  mov     r14, [rbp+560h+arg_30]
0x180005c05  mov     rbx, rcx
0x180005c08  mov     r13, [rbp+560h+arg_38]
0x180005c0f  lea     rcx, [rbp+560h+var_4C0]; void *
0x180005c16  mov     rdi, [rbp+560h+arg_40]
0x180005c1d  xorps   xmm0, xmm0
0x180005c20  mov     [rbp+560h+var_510], rdx
0x180005c24  mov     r8d, 48h ; 'H'; Size
0x180005c2a  xor     edx, edx; Val
0x180005c2c  mov     [rbp+560h+var_500], rax
0x180005c30  mov     [rbp+560h+var_4F8], rsi
0x180005c34  mov     [rbp+560h+var_4F0], r14
0x180005c38  mov     [rbp+560h+CredType], r12d
0x180005c3c  movups  [rbp+560h+pvFindPara], xmm0
0x180005c40  mov     dword ptr [rbp+560h+Size], r12d
0x180005c44  mov     dword ptr [rbp+560h+Size+4], r12d
0x180005c48  mov     [rbp+560h+var_508], r9
0x180005c4c  call    memset_0
0x180005c51  xorps   xmm0, xmm0
0x180005c54  mov     [rbp+560h+Credential], r12
0x180005c58  xorps   xmm1, xmm1
0x180005c5b  mov     [rbp+560h+Token], r12
0x180005c5f  xor     edx, edx; SourceString
0x180005c61  mov     [rbp+560h+Src], r12
0x180005c65  mov     rcx, rsi; DestinationString
0x180005c68  mov     [rbp+560h+var_550], r12
0x180005c6c  movups  xmmword ptr [rbp+560h+var_530.Length], xmm0
0x180005c70  movups  xmmword ptr [rbp+560h+var_520.Length], xmm1
0x180005c74  movups  xmmword ptr [rbp+560h+var_4D8.Length], xmm0
0x180005c7b  call    cs:__imp_RtlInitUnicodeString
0x180005c81  xor     edx, edx; SourceString
0x180005c83  mov     rcx, r14; DestinationString
0x180005c86  call    cs:__imp_RtlInitUnicodeString
0x180005c8c  xor     ecx, ecx
0x180005c8e  mov     [r13+0], rcx
0x180005c92  mov     esi, ecx
0x180005c94  mov     [rdi], ecx
0x180005c96  movzx   edi, word ptr [r15]
0x180005c9a  add     rdi, 2
0x180005c9e  cmp     rdi, 402h
0x180005ca5  jnb     loc_180005E4D
0x180005cab  lea     rdi, [rbp+560h+MarshaledCredential]
0x180005cb2  movzx   r8d, word ptr [r15]; Size
0x180005cb6  mov     rcx, rdi; void *
0x180005cb9  mov     rdx, [r15+8]; Src
0x180005cbd  mov     r14d, 0C0000225h
0x180005cc3  call    memcpy_0
0x180005cc8  lea     r8, [rbp+560h+Credential]; Credential
0x180005ccc  mov     rcx, rdi; MarshaledCredential
0x180005ccf  lea     rdx, [rbp+560h+CredType]; CredType
0x180005cd3  call    cs:__imp_CredUnmarshalCredentialW
0x180005cd9  test    eax, eax
0x180005cdb  jnz     loc_180005EED
0x180005ce1  mov     rcx, [rbp+560h+Token]; Handle
0x180005ce5  test    rcx, rcx
0x180005ce8  jnz     loc_180006322
0x180005cee  test    rsi, rsi
0x180005cf1  jnz     loc_18000632D
0x180005cf7  mov     rcx, [rbp+560h+Credential]; Buffer
0x180005cfb  test    rcx, rcx
0x180005cfe  jnz     loc_18000634F
0x180005d04  lea     rdx, [rbp+560h+var_4B8]; struct _UNICODE_STRING *
0x180005d0b  mov     rcx, rbx; this
0x180005d0e  call    ?WSTFreeString@BaseSSP@basessp@@QEAAXPEAU_UNICODE_STRING@@@Z; basessp::BaseSSP::WSTFreeString(_UNICODE_STRING *)
0x180005d13  lea     rdx, [rbp+560h+var_498]; struct _UNICODE_STRING *
0x180005d1a  mov     rcx, rbx; this
0x180005d1d  call    ?WSTFreeString@BaseSSP@basessp@@QEAAXPEAU_UNICODE_STRING@@@Z; basessp::BaseSSP::WSTFreeString(_UNICODE_STRING *)
0x180005d22  lea     rdx, [rbp+560h+var_488]; struct _UNICODE_STRING *
0x180005d29  mov     rcx, rbx; this
0x180005d2c  call    ?WSTFreeString@BaseSSP@basessp@@QEAAXPEAU_UNICODE_STRING@@@Z; basessp::BaseSSP::WSTFreeString(_UNICODE_STRING *)
0x180005d31  lea     rdx, [rbp+560h+var_4A8]; struct _UNICODE_STRING *
0x180005d38  mov     rcx, rbx; this
0x180005d3b  call    ?WSTFreeString@BaseSSP@basessp@@QEAAXPEAU_UNICODE_STRING@@@Z; basessp::BaseSSP::WSTFreeString(_UNICODE_STRING *)
0x180005d40  mov     rcx, [rbp+560h+var_530.Buffer]
0x180005d44  test    rcx, rcx
0x180005d47  jz      short loc_180005D69
0x180005d49  cmp     dword ptr [rbx+0D0h], 1
0x180005d50  jnz     loc_180005DEA
0x180005d56  mov     rax, [rbx+0F0h]
0x180005d5d  mov     rax, [rax+188h]
0x180005d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d69  mov     rcx, [rbp+560h+var_520.Buffer]
0x180005d6d  test    rcx, rcx
0x180005d70  jz      short loc_180005D8E
0x180005d72  cmp     dword ptr [rbx+0D0h], 1
0x180005d79  jnz     short loc_180005DFA
0x180005d7b  mov     rax, [rbx+0F0h]
0x180005d82  mov     rax, [rax+188h]
0x180005d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d8e  mov     rcx, [rbp+560h+var_4D8.Buffer]
0x180005d95  test    rcx, rcx
0x180005d98  jz      short loc_180005DB6
0x180005d9a  cmp     dword ptr [rbx+0D0h], 1
0x180005da1  jnz     short loc_180005E07
0x180005da3  mov     rax, [rbx+0F0h]
0x180005daa  mov     rax, [rax+188h]
0x180005db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005db6  mov     rax, [rbp+560h+Src]
0x180005dba  test    rax, rax
0x180005dbd  jnz     short loc_180005E14
0x180005dbf  test    r12, r12
0x180005dc2  jnz     short loc_180005E2E
0x180005dc4  mov     eax, r14d
0x180005dc7  mov     rcx, [rbp+560h+var_50]
0x180005dce  xor     rcx, rbp; StackCookie
0x180005dd1  call    __security_check_cookie
0x180005dd6  lea     rsp, [rbp+528h]
0x180005ddd  pop     r15
0x180005ddf  pop     r14
0x180005de1  pop     r13
0x180005de3  pop     r12
0x180005de5  pop     rdi
0x180005de6  pop     rsi
0x180005de7  pop     rbx
0x180005de8  pop     rbp
0x180005de9  retn
0x180005dea  mov     rax, [rbx+0F8h]
0x180005df1  mov     rax, [rax+8]
0x180005df5  jmp     loc_180005D64
0x180005dfa  mov     rax, [rbx+0F8h]
0x180005e01  mov     rax, [rax+8]
0x180005e05  jmp     short loc_180005D89
0x180005e07  mov     rax, [rbx+0F8h]
0x180005e0e  mov     rax, [rax+8]
0x180005e12  jmp     short loc_180005DB1
0x180005e14  mov     ecx, dword ptr [rbp+560h+Size]
0x180005e17  test    rcx, rcx
0x180005e1a  jnz     loc_18000635A
0x180005e20  mov     rdx, [rbp+560h+Src]; void *
0x180005e24  mov     rcx, rbx; this
0x180005e27  call    ?WSTFree@BaseSSP@basessp@@QEAAXPEAX@Z; basessp::BaseSSP::WSTFree(void *)
0x180005e2c  jmp     short loc_180005DBF
0x180005e2e  mov     eax, dword ptr [rbp+560h+Size+4]
0x180005e31  mov     rdx, r12
0x180005e34  test    rax, rax
0x180005e37  jnz     loc_18000636C
0x180005e3d  mov     rdx, r12; void *
0x180005e40  mov     rcx, rbx; this
0x180005e43  call    ?WSTFree@BaseSSP@basessp@@QEAAXPEAX@Z; basessp::BaseSSP::WSTFree(void *)
0x180005e48  jmp     loc_180005DC4
0x180005e4d  cmp     rdi, cs:g_ulMaxStackAllocSize
0x180005e54  ja      short loc_180005EAE
0x180005e56  mov     rcx, cs:g_ulAdditionalProbeSize
0x180005e5d  add     rcx, 8
0x180005e61  add     rcx, rdi
0x180005e64  cmp     rcx, rdi
0x180005e67  jb      short loc_180005EAE
0x180005e69  call    VerifyStackAvailable
0x180005e6e  test    eax, eax
0x180005e70  jz      short loc_180005EAE
0x180005e72  lea     rax, [rdi+8]
0x180005e76  lea     rcx, [rax+0Fh]
0x180005e7a  cmp     rcx, rax
0x180005e7d  ja      short loc_180005E89
0x180005e7f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180005e89  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180005e8d  mov     rax, rcx
0x180005e90  call    _alloca_probe
0x180005e95  sub     rsp, rcx
0x180005e98  lea     rsi, [rsp+5B0h+Size]
0x180005e9d  test    rsi, rsi
0x180005ea0  jz      short loc_180005EAE
0x180005ea2  mov     dword ptr [rsi], 6B637453h
0x180005ea8  add     rsi, 8
0x180005eac  jnz     short loc_180005ED5
0x180005eae  lea     rcx, [rdi+8]
0x180005eb2  cmp     rcx, rdi
0x180005eb5  jb      short loc_180005ED5
0x180005eb7  mov     rax, cs:g_pfnAllocate
0x180005ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec3  mov     rsi, rax
0x180005ec6  test    rax, rax
0x180005ec9  jz      short loc_180005ED5
0x180005ecb  mov     dword ptr [rax], 70616548h
0x180005ed1  add     rsi, 8
0x180005ed5  test    rsi, rsi
0x180005ed8  jnz     short loc_180005EE5
0x180005eda  mov     r14d, 0C0000017h
0x180005ee0  jmp     loc_180005CE1
0x180005ee5  mov     rdi, rsi
0x180005ee8  jmp     loc_180005CB2
0x180005eed  cmp     [rbp+560h+CredType], 1
0x180005ef1  jnz     loc_180005CE1
0x180005ef7  mov     rcx, [rbp+560h+var_510]
0x180005efb  test    rcx, rcx
0x180005efe  jz      loc_180005FA9
0x180005f04  mov     rax, [rbx+0F0h]
0x180005f0b  lea     rdx, [rbp+560h+Token]
0x180005f0f  mov     rax, [rax+170h]
0x180005f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f1b  mov     r14d, eax
0x180005f1e  test    eax, eax
0x180005f20  jns     short loc_180005F60
0x180005f22  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f29  lea     rax, WPP_GLOBAL_Control
0x180005f30  cmp     rcx, rax
0x180005f33  jz      loc_180005CE1
0x180005f39  test    byte ptr [rcx+1Ch], 1
0x180005f3d  jz      loc_180005CE1
0x180005f43  mov     rcx, [rcx+10h]
0x180005f47  lea     r8, WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids
0x180005f4e  mov     edx, 0Dh
0x180005f53  mov     r9d, r14d
0x180005f56  call    WPP_SF_d
0x180005f5b  jmp     loc_180005CE1
0x180005f60  mov     rdx, [rbp+560h+Token]; Token
0x180005f64  xor     ecx, ecx; Thread
0x180005f66  call    cs:__imp_SetThreadToken
0x180005f6c  test    eax, eax
0x180005f6e  jnz     short loc_180005FA9
0x180005f70  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f77  lea     rax, WPP_GLOBAL_Control
0x180005f7e  cmp     rcx, rax
0x180005f81  jz      short loc_180005F9E
0x180005f83  test    byte ptr [rcx+1Ch], 1
0x180005f87  jz      short loc_180005F9E
0x180005f89  mov     rcx, [rcx+10h]
0x180005f8d  lea     r8, WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids
0x180005f94  mov     edx, 0Eh
0x180005f99  call    WPP_SF_
0x180005f9e  mov     r14d, 0C000010Dh
0x180005fa4  jmp     loc_180005CE1
0x180005fa9  lea     rax, aMy; "MY"
0x180005fb0  mov     r9d, 10000h; dwFlags
0x180005fb6  xor     r8d, r8d; hCryptProv
0x180005fb9  mov     [rsp+5B0h+pvPara], rax; pvPara
0x180005fbe  xor     edx, edx; dwEncodingType
0x180005fc0  mov     ecx, 0Ah; lpszStoreProvider
0x180005fc5  call    cs:__imp_CertOpenStore
0x180005fcb  mov     r15, rax
0x180005fce  test    rax, rax
0x180005fd1  jnz     short loc_180006016
0x180005fd3  xor     edi, edi
0x180005fd5  mov     r14d, 8009030Eh
0x180005fdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fe2  lea     rax, WPP_GLOBAL_Control
0x180005fe9  cmp     rcx, rax
0x180005fec  jz      loc_1800060D9
0x180005ff2  test    byte ptr [rcx+1Ch], 1
0x180005ff6  jz      loc_1800060D9
0x180005ffc  mov     rcx, [rcx+10h]
0x180006000  lea     r8, WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids
0x180006007  mov     edx, 0Fh
0x18000600c  call    WPP_SF_
0x180006011  jmp     loc_1800060D9
0x180006016  mov     rax, [rbp+560h+Credential]
0x18000601a  mov     r9d, 10000h; dwFindType
0x180006020  add     rax, 4
0x180006024  mov     [rsp+5B0h+pPrevCertContext], r12; pPrevCertContext
0x180006029  mov     qword ptr [rbp+560h+pvFindPara+8], rax
0x180006030  xor     r8d, r8d; dwFindFlags
0x180006033  lea     rax, [rbp+560h+pvFindPara]
0x180006037  mov     dword ptr [rbp+560h+pvFindPara], 14h
0x18000603e  mov     edx, 10001h; dwCertEncodingType
0x180006043  mov     [rsp+5B0h+pvPara], rax; pvFindPara
0x180006048  mov     rcx, r15; hCertStore
0x18000604b  call    cs:__imp_CertFindCertificateInStore
0x180006051  mov     rdi, rax
0x180006054  test    rax, rax
0x180006057  jnz     short loc_18000608F
0x180006059  mov     r14d, 8009030Eh
0x18000605f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006066  lea     rax, WPP_GLOBAL_Control
0x18000606d  cmp     rcx, rax
0x180006070  jz      short loc_1800060D9
0x180006072  test    byte ptr [rcx+1Ch], 1
0x180006076  jz      short loc_1800060D9
0x180006078  call    cs:__imp_GetLastError
0x18000607e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006085  mov     edx, 10h
0x18000608a  mov     r9d, eax
0x18000608d  jmp     short loc_1800060C9
0x18000608f  lea     r8, [rbp+560h+var_4C0]; struct basessp::_WST_CSPDATA_DETAIL *
0x180006096  mov     rdx, rax; pCert
0x180006099  mov     rcx, rbx; this
0x18000609c  call    ?WSTGetCspDataForCert@BaseSSP@basessp@@AEAAJPEBU_CERT_CONTEXT@@PEAU_WST_CSPDATA_DETAIL@2@@Z; basessp::BaseSSP::WSTGetCspDataForCert(_CERT_CONTEXT const *,basessp::_WST_CSPDATA_DETAIL *)
0x1800060a1  mov     r14d, eax
0x1800060a4  test    eax, eax
0x1800060a6  jns     short loc_1800060ED
0x1800060a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060af  lea     rax, WPP_GLOBAL_Control
0x1800060b6  cmp     rcx, rax
0x1800060b9  jz      short loc_1800060D9
  ... truncated ...
```
