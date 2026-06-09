# IkeFindSspiCert

- ea: `0x18007d5e4`
- end: `0x18007daff`
- name: `IkeFindSspiCert`
- size: `1307`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config`

## callers

- `0x18008434c`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x1800061ec`
- `0x180008388`
- `0x1800144c0`
- `0x180020ae0`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x1800510ee`
- `0x18005bc40`
- `0x18007d490`
- `0x18007d5e4`
- `0x180080908`
- `0x180089f48`
- `0x18008a210`
- `0x18008b6e0`
- `0x18008d148`
- `0x180091058`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d6ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d6ad`
- `CRYPT32!CertFreeCertificateContext` at `0x18007da95`
- `CRYPT32!CertFreeCertificateContext` at `0x18007da95`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18007da70`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18007da70`
- `CRYPT32!CertOpenStore` at `0x18007d69f`
- `CRYPT32!CertOpenStore` at `0x18007d69f`
- `CRYPT32!CertFreeCertificateChain` at `0x18007daa5`
- `CRYPT32!CertFreeCertificateChain` at `0x18007daa5`
- `CRYPT32!CertCloseStore` at `0x18007dab5`
- `CRYPT32!CertCloseStore` at `0x18007dab5`

## string_xrefs

- `0x18007d6b6`: `CertOpenStore`

## pseudocode

```c
__int64 __fastcall IkeFindSspiCert(__int64 a1, unsigned int a2, __int64 a3)
{
  const CERT_CONTEXT *v6; // r12
  DWORD v7; // r9d
  HCERTSTORE v8; // rsi
  __int64 v9; // rcx
  __int64 LastError; // r8
  const char *v11; // rdx
  __int64 AuthConfig; // rdi
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v17; // rcx
  int TlsMmLuid; // eax
  __int64 v19; // rcx
  const WCHAR *v20; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdi
  __int64 v24; // rbx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  const WCHAR *v28; // rax
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // rdi
  __int64 v33; // rbx
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rcx
  const WCHAR *v37; // rax
  __int64 v38; // r8
  __int64 v39; // rbx
  __int64 v41; // [rsp+50h] [rbp-B0h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v43[2]; // [rsp+60h] [rbp-A0h] BYREF
  LPCVOID v44; // [rsp+68h] [rbp-98h]
  PCCERT_CHAIN_CONTEXT pChainContext[2]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v46[8]; // [rsp+80h] [rbp-80h] BYREF
  int v47; // [rsp+A0h] [rbp-60h] BYREF
  LPCVOID v48; // [rsp+A8h] [rbp-58h] BYREF
  const void *v49; // [rsp+B8h] [rbp-48h] BYREF
  int v50; // [rsp+C8h] [rbp-38h]
  _QWORD v51[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v52[32]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v53; // [rsp+100h] [rbp+0h]
  __int64 v54; // [rsp+108h] [rbp+8h]
  _BYTE v55[16]; // [rsp+110h] [rbp+10h] BYREF
  const char *v56; // [rsp+120h] [rbp+20h]
  __int64 v57; // [rsp+128h] [rbp+28h]

  v41 = 0;
  pChainContext[0] = 0;
  memset_0(v46, 0, 0x50u);
  v6 = 0;
  v43[1] = 0;
  pCertContext = 0;
  TraceLogHelper("IkeFindSspiCert", 1);
  if ( (unsigned int)IkeIsImpersonationActiveInitiator(a1, a2) && (unsigned int)IkeIsImpersonationUser(a1, a3) )
  {
    v7 = 98305;
    v46[3] = 1;
  }
  else
  {
    v7 = 163841;
  }
  v8 = CertOpenStore((LPCSTR)0xA, 1u, 0, v7, L"My");
  if ( !v8 )
  {
    LastError = GetLastError();
    v11 = "CertOpenStore";
LABEL_7:
    AuthConfig = WfpReportSysErrorAsWinError(v9, v11, LastError, 1);
    goto LABEL_35;
  }
  AuthConfig = IkeFindAuthConfig(a1, a2, *(unsigned int *)(a3 + 88), &v41);
  if ( !AuthConfig )
  {
    v14 = IkeSaToAuthInfo(a1, a2);
    v51[0] = v14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v13);
      TlsMmLuid = IkeGetTlsMmLuid(v17);
      WPP_SF_iS(v15, 70, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, TlsMmLuid, TlsPeerAddr);
      v14 = v51[0];
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v51[0] = IkeGetTlsMmLuid(v13);
      v53 = v51;
      v54 = 8;
      v20 = (const WCHAR *)IkeGetTlsPeerAddr(v19);
      tlgCreate1Sz_wchar_t((__int64)v55, v20);
      v57 = 36;
      v56 = "Looking up local cert chain for SSL";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_180154F5D,
        v21,
        v22,
        5,
        (__int64)v52);
    }
    v46[0] = *(_DWORD *)(v14 + 12);
    v46[2] = 1;
    v46[4] = 0;
    AuthConfig = IkeGetOptionalLocalCertHashFromAcquire(a1, a2, &v47);
    if ( !AuthConfig )
    {
      if ( !v47 )
      {
        AuthConfig = IkeChainSelect(
                       (_DWORD)v8,
                       0,
                       0,
                       0,
                       v41,
                       *(_DWORD *)(a3 + 88),
                       (__int64)v46,
                       a1 + 1040,
                       (__int64)pChainContext);
        if ( AuthConfig )
          goto LABEL_35;
        goto LABEL_33;
      }
      v43[0] = v47;
      v44 = v48;
      IkeCertFindByHash(v8, v43, &pCertContext);
      v6 = pCertContext;
      if ( !pCertContext )
      {
        LastError = 13806;
        v11 = "IkeFindSspiCert";
        goto LABEL_7;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v23 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v24 = IkeGetTlsPeerAddr(v9);
        v26 = IkeGetTlsMmLuid(v25);
        WPP_SF_iS(v23, 71, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v26, v24);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v51[0] = IkeGetTlsMmLuid(v9);
        v53 = v51;
        v54 = 8;
        v28 = (const WCHAR *)IkeGetTlsPeerAddr(v27);
        tlgCreate1Sz_wchar_t((__int64)v55, v28);
        v57 = 47;
        v56 = "Found cert using certificate hash from acquire";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)&byte_180154F1F,
          v29,
          v30,
          5,
          (__int64)v52);
      }
      IkeDumpCert(v6);
      AuthConfig = IkeChainSelect(
                     (_DWORD)v8,
                     (_DWORD)v6,
                     0,
                     0,
                     v41,
                     *(_DWORD *)(a3 + 88),
                     (__int64)v46,
                     a1 + 1040,
                     (__int64)pChainContext);
      if ( !AuthConfig )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v32 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v33 = IkeGetTlsPeerAddr(v31);
          v35 = IkeGetTlsMmLuid(v34);
          WPP_SF_iS(v32, 72, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v35, v33);
        }
        if ( (unsigned int)dword_180173278 > 4 )
        {
          v51[0] = IkeGetTlsMmLuid(v31);
          v53 = v51;
          v54 = 8;
          v37 = (const WCHAR *)IkeGetTlsPeerAddr(v36);
          tlgCreate1Sz_wchar_t((__int64)v55, v37);
          v57 = 53;
          v56 = "Found cert chain using certificate hash from acquire";
          tlgWriteTransfer_EtwEventWriteTransfer(
            (__int64)&dword_180173278,
            (unsigned __int8 *)byte_180154EE1,
            v38,
            (__int64)"Found cert chain using certificate hash from acquire",
            5,
            (__int64)v52);
        }
LABEL_33:
        AuthConfig = IkeCopyRootPolicyToSA(&v49, *(_QWORD *)(a3 + 104) + 64LL);
        if ( !AuthConfig )
        {
          v39 = *(_QWORD *)(a3 + 104);
          *(_QWORD *)(v39 + 56) = CertDuplicateCertificateContext((*(*pChainContext[0]->rgpChain)->rgpElement)->pCertContext);
          *(_DWORD *)(*(_QWORD *)(a3 + 104) + 84LL) = v50;
        }
      }
    }
  }
LABEL_35:
  WfpMemFree(&v48);
  if ( v6 )
    CertFreeCertificateContext(v6);
  if ( pChainContext[0] )
    CertFreeCertificateChain(pChainContext[0]);
  if ( v8 )
    CertCloseStore(v8, 0);
  TraceLogHelper("IkeFindSspiCert", 0);
  return IkeReturnError(AuthConfig, "IkeFindSspiCert");
}

```

## disassembly

```asm
0x18007d5e4  mov     [rsp-8+arg_18], rbx
0x18007d5e9  push    rbp
0x18007d5ea  push    rsi
0x18007d5eb  push    rdi
0x18007d5ec  push    r12
0x18007d5ee  push    r13
0x18007d5f0  push    r14
0x18007d5f2  push    r15
0x18007d5f4  lea     rbp, [rsp-40h]
0x18007d5f9  sub     rsp, 140h
0x18007d600  mov     rax, cs:__security_cookie
0x18007d607  xor     rax, rsp
0x18007d60a  mov     [rbp+70h+var_40], rax
0x18007d60e  mov     r13d, edx
0x18007d611  mov     [rsp+170h+var_120], 0
0x18007d61a  xor     edx, edx; Val
0x18007d61c  mov     [rsp+170h+pChainContext], 0
0x18007d625  mov     r14, r8
0x18007d628  mov     r15, rcx
0x18007d62b  lea     rcx, [rbp+70h+var_F0]; void *
0x18007d62f  lea     r8d, [rdx+50h]; Size
0x18007d633  call    memset_0
0x18007d638  xor     r12d, r12d
0x18007d63b  mov     [rsp+170h+var_10C], 0
0x18007d643  lea     rcx, aIkefindsspicer; "IkeFindSspiCert"
0x18007d64a  mov     [rsp+170h+pCertContext], r12
0x18007d64f  lea     ebx, [r12+1]
0x18007d654  mov     edx, ebx
0x18007d656  call    TraceLogHelper
0x18007d65b  mov     edx, r13d
0x18007d65e  mov     rcx, r15
0x18007d661  call    IkeIsImpersonationActiveInitiator
0x18007d666  test    eax, eax
0x18007d668  jz      short loc_18007D684
0x18007d66a  mov     rdx, r14
0x18007d66d  mov     rcx, r15
0x18007d670  call    IkeIsImpersonationUser
0x18007d675  test    eax, eax
0x18007d677  jz      short loc_18007D684
0x18007d679  mov     r9d, 18001h
0x18007d67f  mov     [rbp+70h+var_E4], ebx
0x18007d682  jmp     short loc_18007D68A
0x18007d684  mov     r9d, 28001h; dwFlags
0x18007d68a  xor     r8d, r8d; hCryptProv
0x18007d68d  lea     rax, aMy; "My"
0x18007d694  mov     edx, ebx; dwEncodingType
0x18007d696  mov     [rsp+170h+pvPara], rax; pvPara
0x18007d69b  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x18007d69f  call    cs:__imp_CertOpenStore
0x18007d6a5  mov     rsi, rax
0x18007d6a8  test    rax, rax
0x18007d6ab  jnz     short loc_18007D6CD
0x18007d6ad  call    cs:__imp_GetLastError
0x18007d6b3  mov     r8d, eax
0x18007d6b6  lea     rdx, aCertopenstore_0; "CertOpenStore"
0x18007d6bd  mov     r9d, ebx
0x18007d6c0  call    WfpReportSysErrorAsWinError
0x18007d6c5  mov     rdi, rax
0x18007d6c8  jmp     loc_18007DA84
0x18007d6cd  mov     r8d, [r14+58h]
0x18007d6d1  lea     r9, [rsp+170h+var_120]
0x18007d6d6  mov     edx, r13d
0x18007d6d9  mov     rcx, r15
0x18007d6dc  call    IkeFindAuthConfig
0x18007d6e1  mov     rdi, rax
0x18007d6e4  test    rax, rax
0x18007d6e7  jnz     loc_18007DA84
0x18007d6ed  mov     edx, r13d
0x18007d6f0  mov     rcx, r15
0x18007d6f3  call    IkeSaToAuthInfo
0x18007d6f8  mov     rbx, rax
0x18007d6fb  mov     [rbp+70h+var_A0], rax
0x18007d6ff  mov     rdi, cs:WPP_GLOBAL_Control
0x18007d706  lea     rax, WPP_GLOBAL_Control
0x18007d70d  cmp     rdi, rax
0x18007d710  jz      short loc_18007D74F
0x18007d712  cmp     byte ptr [rdi+19h], 4
0x18007d716  jb      short loc_18007D74F
0x18007d718  test    byte ptr [rdi+1Ch], 10h
0x18007d71c  jz      short loc_18007D74F
0x18007d71e  mov     rdi, [rdi+10h]
0x18007d722  call    IkeGetTlsPeerAddr
0x18007d727  mov     rbx, rax
0x18007d72a  call    IkeGetTlsMmLuid
0x18007d72f  mov     r9, rax
0x18007d732  mov     [rsp+170h+pvPara], rbx
0x18007d737  mov     edx, 46h ; 'F'
0x18007d73c  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x18007d743  mov     rcx, rdi
0x18007d746  call    WPP_SF_iS
0x18007d74b  mov     rbx, [rbp+70h+var_A0]
0x18007d74f  mov     eax, cs:dword_180173278
0x18007d755  cmp     eax, 4
0x18007d758  jbe     short loc_18007D7BB
0x18007d75a  call    IkeGetTlsMmLuid
0x18007d75f  mov     [rbp+70h+var_A0], rax
0x18007d763  lea     rax, [rbp+70h+var_A0]
0x18007d767  mov     [rbp+70h+var_70], rax
0x18007d76b  mov     [rbp+70h+var_68], 8
0x18007d773  call    IkeGetTlsPeerAddr
0x18007d778  mov     rdx, rax
0x18007d77b  lea     rcx, [rbp+70h+var_60]
0x18007d77f  call    _tlgCreate1Sz_wchar_t
0x18007d784  lea     rcx, aLookingUpLocal; "Looking up local cert chain for SSL"
0x18007d78b  mov     [rbp+70h+var_48], 24h ; '$'
0x18007d793  lea     rax, [rbp+70h+var_90]
0x18007d797  mov     [rbp+70h+var_50], rcx
0x18007d79b  mov     [rsp+170h+var_148], rax
0x18007d7a0  lea     rcx, dword_180173278
0x18007d7a7  lea     rdx, byte_180154F5D
0x18007d7ae  mov     dword ptr [rsp+170h+pvPara], 5
0x18007d7b6  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18007d7bb  mov     eax, [rbx+0Ch]
0x18007d7be  lea     r8, [rbp+70h+var_D0]
0x18007d7c2  mov     ebx, 1
0x18007d7c7  mov     [rbp+70h+var_F0], eax
0x18007d7ca  mov     edx, r13d
0x18007d7cd  mov     [rbp+70h+var_E8], ebx
0x18007d7d0  mov     rcx, r15
0x18007d7d3  mov     [rbp+70h+var_E0], r12d
0x18007d7d7  call    IkeGetOptionalLocalCertHashFromAcquire
0x18007d7dc  mov     rdi, rax
0x18007d7df  test    rax, rax
0x18007d7e2  jnz     loc_18007DA84
0x18007d7e8  mov     eax, [rbp+70h+var_D0]
0x18007d7eb  test    eax, eax
0x18007d7ed  jz      loc_18007D9F3
0x18007d7f3  mov     [rsp+170h+var_110], eax
0x18007d7f7  lea     r8, [rsp+170h+pCertContext]
0x18007d7fc  mov     rax, [rbp+70h+var_C8]
0x18007d800  lea     rdx, [rsp+170h+var_110]
0x18007d805  mov     rcx, rsi
0x18007d808  mov     [rsp+170h+var_108], rax
0x18007d80d  call    IkeCertFindByHash
0x18007d812  mov     r12, [rsp+170h+pCertContext]
0x18007d817  test    r12, r12
0x18007d81a  jnz     short loc_18007D82E
0x18007d81c  mov     r8d, 35EEh
0x18007d822  lea     rdx, aIkefindsspicer; "IkeFindSspiCert"
0x18007d829  jmp     loc_18007D6BD
0x18007d82e  mov     rdi, cs:WPP_GLOBAL_Control
0x18007d835  lea     r13, WPP_GLOBAL_Control
0x18007d83c  cmp     rdi, r13
0x18007d83f  jz      short loc_18007D87A
0x18007d841  cmp     byte ptr [rdi+19h], 4
0x18007d845  jb      short loc_18007D87A
0x18007d847  test    byte ptr [rdi+1Ch], 10h
0x18007d84b  jz      short loc_18007D87A
0x18007d84d  mov     rdi, [rdi+10h]
0x18007d851  call    IkeGetTlsPeerAddr
0x18007d856  mov     rbx, rax
0x18007d859  call    IkeGetTlsMmLuid
0x18007d85e  mov     r9, rax
0x18007d861  mov     [rsp+170h+pvPara], rbx
0x18007d866  mov     edx, 47h ; 'G'
0x18007d86b  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x18007d872  mov     rcx, rdi
0x18007d875  call    WPP_SF_iS
0x18007d87a  mov     eax, cs:dword_180173278
0x18007d880  cmp     eax, 4
0x18007d883  jbe     short loc_18007D8E6
0x18007d885  call    IkeGetTlsMmLuid
0x18007d88a  mov     [rbp+70h+var_A0], rax
0x18007d88e  lea     rax, [rbp+70h+var_A0]
0x18007d892  mov     [rbp+70h+var_70], rax
0x18007d896  mov     [rbp+70h+var_68], 8
0x18007d89e  call    IkeGetTlsPeerAddr
0x18007d8a3  mov     rdx, rax
0x18007d8a6  lea     rcx, [rbp+70h+var_60]
0x18007d8aa  call    _tlgCreate1Sz_wchar_t
0x18007d8af  lea     rcx, aFoundCertUsing; "Found cert using certificate hash from "...
0x18007d8b6  mov     [rbp+70h+var_48], 2Fh ; '/'
0x18007d8be  lea     rax, [rbp+70h+var_90]
0x18007d8c2  mov     [rbp+70h+var_50], rcx
0x18007d8c6  mov     [rsp+170h+var_148], rax
0x18007d8cb  lea     rcx, dword_180173278
0x18007d8d2  lea     rdx, byte_180154F1F
0x18007d8d9  mov     dword ptr [rsp+170h+pvPara], 5
0x18007d8e1  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18007d8e6  mov     rcx, r12; pCertContext
0x18007d8e9  call    IkeDumpCert
0x18007d8ee  lea     rcx, [rsp+170h+pChainContext]
0x18007d8f3  xor     r9d, r9d
0x18007d8f6  mov     [rsp+170h+var_130], rcx
0x18007d8fb  lea     rax, [r15+410h]
0x18007d902  mov     [rsp+170h+var_138], rax
0x18007d907  xor     r8d, r8d
0x18007d90a  lea     rax, [rbp+70h+var_F0]
0x18007d90e  mov     rdx, r12
0x18007d911  mov     [rsp+170h+var_140], rax
0x18007d916  mov     rcx, rsi
0x18007d919  mov     eax, [r14+58h]
0x18007d91d  mov     dword ptr [rsp+170h+var_148], eax
0x18007d921  mov     rax, [rsp+170h+var_120]
0x18007d926  mov     [rsp+170h+pvPara], rax
0x18007d92b  call    IkeChainSelect
0x18007d930  mov     rdi, rax
0x18007d933  test    rax, rax
0x18007d936  jnz     loc_18007DA84
0x18007d93c  mov     rdi, cs:WPP_GLOBAL_Control
0x18007d943  cmp     rdi, r13
0x18007d946  jz      short loc_18007D981
0x18007d948  cmp     byte ptr [rdi+19h], 4
0x18007d94c  jb      short loc_18007D981
0x18007d94e  test    byte ptr [rdi+1Ch], 10h
0x18007d952  jz      short loc_18007D981
0x18007d954  mov     rdi, [rdi+10h]
0x18007d958  call    IkeGetTlsPeerAddr
0x18007d95d  mov     rbx, rax
0x18007d960  call    IkeGetTlsMmLuid
0x18007d965  mov     r9, rax
0x18007d968  mov     [rsp+170h+pvPara], rbx
0x18007d96d  mov     edx, 48h ; 'H'
0x18007d972  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x18007d979  mov     rcx, rdi
0x18007d97c  call    WPP_SF_iS
0x18007d981  mov     eax, cs:dword_180173278
0x18007d987  cmp     eax, 4
0x18007d98a  jbe     loc_18007DA3C
0x18007d990  call    IkeGetTlsMmLuid
0x18007d995  mov     [rbp+70h+var_A0], rax
0x18007d999  lea     rax, [rbp+70h+var_A0]
0x18007d99d  mov     [rbp+70h+var_70], rax
0x18007d9a1  mov     [rbp+70h+var_68], 8
0x18007d9a9  call    IkeGetTlsPeerAddr
0x18007d9ae  mov     rdx, rax
0x18007d9b1  lea     rcx, [rbp+70h+var_60]
0x18007d9b5  call    _tlgCreate1Sz_wchar_t
0x18007d9ba  lea     rax, [rbp+70h+var_90]
0x18007d9be  mov     [rbp+70h+var_48], 35h ; '5'
0x18007d9c6  lea     r9, aFoundCertChain; "Found cert chain using certificate hash"...
0x18007d9cd  mov     [rsp+170h+var_148], rax
0x18007d9d2  lea     rdx, byte_180154EE1
0x18007d9d9  mov     dword ptr [rsp+170h+pvPara], 5
0x18007d9e1  lea     rcx, dword_180173278
0x18007d9e8  mov     [rbp+70h+var_50], r9
0x18007d9ec  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18007d9f1  jmp     short loc_18007DA3C
0x18007d9f3  lea     rcx, [rsp+170h+pChainContext]
0x18007d9f8  xor     r9d, r9d
0x18007d9fb  mov     [rsp+170h+var_130], rcx
0x18007da00  lea     rax, [r15+410h]
0x18007da07  mov     [rsp+170h+var_138], rax
0x18007da0c  xor     r8d, r8d
0x18007da0f  lea     rax, [rbp+70h+var_F0]
0x18007da13  xor     edx, edx
0x18007da15  mov     [rsp+170h+var_140], rax
0x18007da1a  mov     rcx, rsi
0x18007da1d  mov     eax, [r14+58h]
0x18007da21  mov     dword ptr [rsp+170h+var_148], eax
0x18007da25  mov     rax, [rsp+170h+var_120]
0x18007da2a  mov     [rsp+170h+pvPara], rax
0x18007da2f  call    IkeChainSelect
0x18007da34  mov     rdi, rax
0x18007da37  test    rax, rax
0x18007da3a  jnz     short loc_18007DA84
0x18007da3c  mov     rdx, [r14+68h]
0x18007da40  lea     rcx, [rbp+70h+var_B8]
0x18007da44  add     rdx, 40h ; '@'
0x18007da48  call    IkeCopyRootPolicyToSA
0x18007da4d  mov     rdi, rax
0x18007da50  test    rax, rax
0x18007da53  jnz     short loc_18007DA84
0x18007da55  mov     rax, [rsp+170h+pChainContext]
0x18007da5a  mov     rbx, [r14+68h]
0x18007da5e  mov     rcx, [rax+10h]
0x18007da62  mov     rax, [rcx]
0x18007da65  mov     rcx, [rax+10h]
0x18007da69  mov     rcx, [rcx]
0x18007da6c  mov     rcx, [rcx+8]; pCertContext
0x18007da70  call    cs:__imp_CertDuplicateCertificateContext
0x18007da76  mov     [rbx+38h], rax
0x18007da7a  mov     rdx, [r14+68h]
0x18007da7e  mov     eax, [rbp+70h+var_A8]
0x18007da81  mov     [rdx+54h], eax
0x18007da84  lea     rcx, [rbp+70h+var_C8]
0x18007da88  call    WfpMemFree
0x18007da8d  test    r12, r12
0x18007da90  jz      short loc_18007DA9B
0x18007da92  mov     rcx, r12; pCertContext
0x18007da95  call    cs:__imp_CertFreeCertificateContext
0x18007da9b  mov     rcx, [rsp+170h+pChainContext]; pChainContext
0x18007daa0  test    rcx, rcx
0x18007daa3  jz      short loc_18007DAAB
0x18007daa5  call    cs:__imp_CertFreeCertificateChain
0x18007daab  test    rsi, rsi
0x18007daae  jz      short loc_18007DABB
0x18007dab0  xor     edx, edx; dwFlags
0x18007dab2  mov     rcx, rsi; hCertStore
0x18007dab5  call    cs:__imp_CertCloseStore
0x18007dabb  xor     edx, edx
0x18007dabd  lea     rcx, aIkefindsspicer; "IkeFindSspiCert"
0x18007dac4  call    TraceLogHelper
0x18007dac9  lea     rdx, aIkefindsspicer; "IkeFindSspiCert"
0x18007dad0  mov     rcx, rdi
0x18007dad3  call    IkeReturnError
0x18007dad8  mov     rcx, [rbp+70h+var_40]
0x18007dadc  xor     rcx, rsp; StackCookie
0x18007dadf  call    __security_check_cookie
0x18007dae4  mov     rbx, [rsp+170h+arg_18]
  ... truncated ...
```
