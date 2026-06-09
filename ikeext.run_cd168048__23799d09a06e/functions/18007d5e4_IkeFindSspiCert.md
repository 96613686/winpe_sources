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
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  int TlsMmLuid; // eax
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdi
  __int64 v33; // rbx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  int v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rax
  int v41; // r8d
  int v42; // r9d
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rdi
  __int64 v48; // rbx
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r9
  int v53; // eax
  __int64 v54; // rcx
  __int64 v55; // rax
  int v56; // r8d
  __int64 v57; // rbx
  __int64 v59; // [rsp+50h] [rbp-B0h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v61[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v62; // [rsp+68h] [rbp-98h]
  PCCERT_CHAIN_CONTEXT pChainContext[2]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v64[8]; // [rsp+80h] [rbp-80h] BYREF
  int v65; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v66; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v67[16]; // [rsp+B8h] [rbp-48h] BYREF
  int v68; // [rsp+C8h] [rbp-38h]
  _QWORD v69[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v70[32]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v71; // [rsp+100h] [rbp+0h]
  __int64 v72; // [rsp+108h] [rbp+8h]
  _BYTE v73[16]; // [rsp+110h] [rbp+10h] BYREF
  const char *v74; // [rsp+120h] [rbp+20h]
  __int64 v75; // [rsp+128h] [rbp+28h]

  v59 = 0;
  pChainContext[0] = 0;
  memset_0(v64, 0, 0x50u);
  v6 = 0;
  v61[1] = 0;
  pCertContext = 0;
  TraceLogHelper("IkeFindSspiCert", 1);
  if ( (unsigned int)IkeIsImpersonationActiveInitiator(a1, a2) && (unsigned int)IkeIsImpersonationUser(a1, a3) )
  {
    v7 = 98305;
    v64[3] = 1;
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
  AuthConfig = IkeFindAuthConfig(a1, a2, *(unsigned int *)(a3 + 88), &v59);
  if ( !AuthConfig )
  {
    v15 = IkeSaToAuthInfo(a1, a2);
    v69[0] = v15;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v18 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v14);
      TlsMmLuid = IkeGetTlsMmLuid(v21, v20, v22, v23);
      WPP_SF_iS(v18, 70, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, TlsMmLuid, TlsPeerAddr);
      v15 = v69[0];
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v69[0] = IkeGetTlsMmLuid(v14, v13, v16, v17);
      v71 = v69;
      v72 = 8;
      v26 = IkeGetTlsPeerAddr(v25);
      tlgCreate1Sz_wchar_t(v73, v26);
      v75 = 36;
      v74 = "Looking up local cert chain for SSL";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_180154F1F,
        v27,
        v28,
        5,
        (__int64)v70);
    }
    v64[0] = *(_DWORD *)(v15 + 12);
    v64[2] = 1;
    v64[4] = 0;
    AuthConfig = IkeGetOptionalLocalCertHashFromAcquire(a1, a2, &v65);
    if ( !AuthConfig )
    {
      if ( !v65 )
      {
        AuthConfig = IkeChainSelect(
                       (_DWORD)v8,
                       0,
                       0,
                       0,
                       v59,
                       *(_DWORD *)(a3 + 88),
                       (__int64)v64,
                       a1 + 1040,
                       (__int64)pChainContext);
        if ( AuthConfig )
          goto LABEL_35;
        goto LABEL_33;
      }
      v61[0] = v65;
      v62 = v66;
      IkeCertFindByHash(v8, v61, &pCertContext);
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
        v32 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v33 = IkeGetTlsPeerAddr(v9);
        v38 = IkeGetTlsMmLuid(v35, v34, v36, v37);
        WPP_SF_iS(v32, 71, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v38, v33);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v69[0] = IkeGetTlsMmLuid(v9, v29, v30, v31);
        v71 = v69;
        v72 = 8;
        v40 = IkeGetTlsPeerAddr(v39);
        tlgCreate1Sz_wchar_t(v73, v40);
        v75 = 47;
        v74 = "Found cert using certificate hash from acquire";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)byte_180154EE1,
          v41,
          v42,
          5,
          (__int64)v70);
      }
      IkeDumpCert(v6);
      AuthConfig = IkeChainSelect(
                     (_DWORD)v8,
                     (_DWORD)v6,
                     0,
                     0,
                     v59,
                     *(_DWORD *)(a3 + 88),
                     (__int64)v64,
                     a1 + 1040,
                     (__int64)pChainContext);
      if ( !AuthConfig )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v47 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v48 = IkeGetTlsPeerAddr(v44);
          v53 = IkeGetTlsMmLuid(v50, v49, v51, v52);
          WPP_SF_iS(v47, 72, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v53, v48);
        }
        if ( (unsigned int)dword_180173278 > 4 )
        {
          v69[0] = IkeGetTlsMmLuid(v44, v43, v45, v46);
          v71 = v69;
          v72 = 8;
          v55 = IkeGetTlsPeerAddr(v54);
          tlgCreate1Sz_wchar_t(v73, v55);
          v75 = 53;
          v74 = "Found cert chain using certificate hash from acquire";
          tlgWriteTransfer_EtwEventWriteTransfer(
            (unsigned int)&dword_180173278,
            (unsigned int)byte_180154F5D,
            v56,
            (unsigned int)"Found cert chain using certificate hash from acquire",
            5,
            (__int64)v70);
        }
LABEL_33:
        AuthConfig = IkeCopyRootPolicyToSA(v67, *(_QWORD *)(a3 + 104) + 64LL);
        if ( !AuthConfig )
        {
          v57 = *(_QWORD *)(a3 + 104);
          *(_QWORD *)(v57 + 56) = CertDuplicateCertificateContext((*(*pChainContext[0]->rgpChain)->rgpElement)->pCertContext);
          *(_DWORD *)(*(_QWORD *)(a3 + 104) + 84LL) = v68;
        }
      }
    }
  }
LABEL_35:
  WfpMemFree(&v66);
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
0x18007d7a7  lea     rdx, byte_180154F1F
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
0x18007d8d2  lea     rdx, byte_180154EE1
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
0x18007d9d2  lea     rdx, byte_180154F5D
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
