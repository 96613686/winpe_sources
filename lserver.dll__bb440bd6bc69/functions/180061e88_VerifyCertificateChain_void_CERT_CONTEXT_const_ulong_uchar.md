# VerifyCertificateChain(void *,_CERT_CONTEXT const *,ulong,uchar *)

- ea: `0x180061e88`
- end: `0x1800621ff`
- name: `?VerifyCertificateChain@@YAKPEAXPEBU_CERT_CONTEXT@@KPEAE@Z`
- size: `887`
- prototype: `unsigned int __fastcall(HCERTSTORE hCertStore, PCCERT_CONTEXT pCertContext, DWORD cbCertEncoded, BYTE *pbCertEncoded)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800617a0`

## callees

- `0x18001ae3c`
- `0x18001aea4`
- `0x18005f43c`
- `0x180061e88`

## import_xrefs

- `CRYPT32!CertVerifySubjectCertificateContext` at `0x1800620c3`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x1800620c3`
- `CRYPT32!CertGetIssuerCertificateFromStore` at `0x180062067`
- `CRYPT32!CertGetIssuerCertificateFromStore` at `0x180062067`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180062006`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180062006`
- `CRYPT32!CertCreateCertificateContext` at `0x180061f0c`
- `CRYPT32!CertCreateCertificateContext` at `0x180061f0c`
- `CRYPT32!CertFreeCertificateContext` at `0x180062093`
- `CRYPT32!CertFreeCertificateContext` at `0x180062121`
- `CRYPT32!CertFreeCertificateContext` at `0x180062189`
- `CRYPT32!CertFreeCertificateContext` at `0x18006219d`
- `CRYPT32!CertFreeCertificateContext` at `0x180062093`
- `CRYPT32!CertFreeCertificateContext` at `0x180062121`
- `CRYPT32!CertFreeCertificateContext` at `0x180062189`
- `CRYPT32!CertFreeCertificateContext` at `0x18006219d`
- `ADVAPI32!RegOpenKeyExW` at `0x180061f91`
- `ADVAPI32!RegOpenKeyExW` at `0x180061f91`
- `ADVAPI32!RegCloseKey` at `0x180061ff7`
- `ADVAPI32!RegCloseKey` at `0x180061ff7`
- `KERNEL32!GetLastError` at `0x180061f20`
- `KERNEL32!GetLastError` at `0x1800620df`
- `KERNEL32!GetLastError` at `0x180062160`
- `KERNEL32!GetLastError` at `0x180062173`
- `KERNEL32!GetLastError` at `0x180061f20`
- `KERNEL32!GetLastError` at `0x1800620df`
- `KERNEL32!GetLastError` at `0x180062160`
- `KERNEL32!GetLastError` at `0x180062173`

## pseudocode

```c
__int64 __fastcall VerifyCertificateChain(
        HCERTSTORE hCertStore,
        PCCERT_CONTEXT pCertContext,
        DWORD cbCertEncoded,
        BYTE *pbCertEncoded)
{
  DWORD CertVerificationResult; // ebx
  const CERT_CONTEXT *CertificateContext; // rsi
  const CERT_CONTEXT *IssuerCertificateFromStore; // r15
  const CERT_CONTEXT *v11; // rdi
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD pdwFlags; // [rsp+80h] [rbp+40h] BYREF

  CertVerificationResult = 0;
  CertificateContext = 0;
  pdwFlags = 0;
  IssuerCertificateFromStore = 0;
  hKey = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids,
      L"VerifyCertificateChain");
  if ( !cbCertEncoded
    || !pbCertEncoded
    || (CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded)) != 0 )
  {
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\TermServLicensing\\IgnoreLicenseExpiration",
           0,
           0x20019u,
           &hKey) )
    {
      pdwFlags = 7;
    }
    else
    {
      pdwFlags = 5;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids,
          L"VerifyCertificateChain");
    }
    if ( hKey )
      RegCloseKey(hKey);
    v11 = CertDuplicateCertificateContext(pCertContext);
    if ( v11 )
    {
      while ( 1 )
      {
        IssuerCertificateFromStore = CertGetIssuerCertificateFromStore(hCertStore, v11, 0, &pdwFlags);
        if ( !IssuerCertificateFromStore )
          break;
        CertVerificationResult = GetCertVerificationResult(pdwFlags);
        if ( CertVerificationResult )
          goto LABEL_21;
        pdwFlags = 1;
        CertFreeCertificateContext(v11);
        v11 = IssuerCertificateFromStore;
      }
      if ( !CertificateContext )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids,
            L"VerifyCertificateChain");
        if ( GetLastError() != -2146885625 )
          CertVerificationResult = GetLastError();
        goto LABEL_39;
      }
      pdwFlags = 7;
      if ( CertVerifySubjectCertificateContext(v11, CertificateContext, &pdwFlags) )
      {
        CertVerificationResult = GetCertVerificationResult(pdwFlags);
      }
      else
      {
        CertVerificationResult = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids,
            L"VerifyCertificateChain");
      }
    }
    else
    {
      CertVerificationResult = 87;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids,
          L"VerifyCertificateChain");
LABEL_21:
      if ( !CertificateContext )
        goto LABEL_39;
    }
    CertFreeCertificateContext(CertificateContext);
LABEL_39:
    if ( v11 )
      CertFreeCertificateContext(v11);
    if ( IssuerCertificateFromStore )
      CertFreeCertificateContext(IssuerCertificateFromStore);
    goto LABEL_43;
  }
  CertVerificationResult = GetLastError();
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return CertVerificationResult;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      53,
      WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids,
      L"VerifyCertificateChain");
LABEL_43:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      58,
      (unsigned int)WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids,
      (unsigned int)L"VerifyCertificateChain",
      CertVerificationResult);
  return CertVerificationResult;
}

```

## disassembly

```asm
0x180061e88  mov     [rsp-28h+arg_0], rbx
0x180061e8d  mov     [rsp-28h+arg_8], rsi
0x180061e92  mov     [rsp-28h+arg_18], rdi
0x180061e97  push    rbp
0x180061e98  push    r12
0x180061e9a  push    r13
0x180061e9c  push    r14
0x180061e9e  push    r15
0x180061ea0  mov     rbp, rsp
0x180061ea3  sub     rsp, 40h
0x180061ea7  xor     ebx, ebx
0x180061ea9  xor     esi, esi
0x180061eab  and     [rbp+pdwFlags], ebx
0x180061eae  xor     r15d, r15d
0x180061eb1  and     [rbp+hKey], rbx
0x180061eb5  mov     rdi, r9
0x180061eb8  mov     r14d, r8d
0x180061ebb  mov     r12, rdx
0x180061ebe  mov     r13, rcx
0x180061ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x180061ec8  lea     rax, WPP_GLOBAL_Control
0x180061ecf  cmp     rcx, rax
0x180061ed2  jz      short loc_180061EF7
0x180061ed4  test    dword ptr [rcx+1Ch], 1000h
0x180061edb  jz      short loc_180061EF7
0x180061edd  mov     rcx, [rcx+10h]
0x180061ee1  lea     edx, [rbx+34h]
0x180061ee4  lea     r9, aVerifycertific; "VerifyCertificateChain"
0x180061eeb  lea     r8, WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids
0x180061ef2  call    WPP_SF_S
0x180061ef7  test    r14d, r14d
0x180061efa  jz      short loc_180061F71
0x180061efc  test    rdi, rdi
0x180061eff  jz      short loc_180061F71
0x180061f01  mov     r8d, r14d; cbCertEncoded
0x180061f04  mov     rdx, rdi; pbCertEncoded
0x180061f07  mov     ecx, 1; dwCertEncodingType
0x180061f0c  call    cs:__imp_CertCreateCertificateContext
0x180061f13  nop     dword ptr [rax+rax+00h]
0x180061f18  mov     rsi, rax
0x180061f1b  test    rax, rax
0x180061f1e  jnz     short loc_180061F71
0x180061f20  call    cs:__imp_GetLastError
0x180061f27  nop     dword ptr [rax+rax+00h]
0x180061f2c  mov     ebx, eax
0x180061f2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180061f35  lea     r14, WPP_GLOBAL_Control
0x180061f3c  cmp     rcx, r14
0x180061f3f  jz      loc_1800621DE
0x180061f45  test    dword ptr [rcx+1Ch], 200h
0x180061f4c  jz      loc_1800621A9
0x180061f52  mov     rcx, [rcx+10h]
0x180061f56  lea     edx, [rsi+35h]
0x180061f59  lea     r9, aVerifycertific; "VerifyCertificateChain"
0x180061f60  lea     r8, WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids
0x180061f67  call    WPP_SF_S
0x180061f6c  jmp     loc_1800621A9
0x180061f71  lea     rax, [rbp+hKey]
0x180061f75  mov     r9d, 20019h; samDesired
0x180061f7b  xor     r8d, r8d; ulOptions
0x180061f7e  mov     [rsp+40h+phkResult], rax; phkResult
0x180061f83  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x180061f8a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180061f91  call    cs:__imp_RegOpenKeyExW
0x180061f98  nop     dword ptr [rax+rax+00h]
0x180061f9d  test    eax, eax
0x180061f9f  jnz     short loc_180061FE0
0x180061fa1  mov     [rbp+pdwFlags], 5
0x180061fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180061faf  lea     r14, WPP_GLOBAL_Control
0x180061fb6  cmp     rcx, r14
0x180061fb9  jz      short loc_180061FEE
0x180061fbb  test    dword ptr [rcx+1Ch], 2000h
0x180061fc2  jz      short loc_180061FEE
0x180061fc4  mov     rcx, [rcx+10h]
0x180061fc8  lea     edx, [rax+36h]
0x180061fcb  lea     r9, aVerifycertific; "VerifyCertificateChain"
0x180061fd2  lea     r8, WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids
0x180061fd9  call    WPP_SF_S
0x180061fde  jmp     short loc_180061FEE
0x180061fe0  mov     [rbp+pdwFlags], 7
0x180061fe7  lea     r14, WPP_GLOBAL_Control
0x180061fee  mov     rcx, [rbp+hKey]; hKey
0x180061ff2  test    rcx, rcx
0x180061ff5  jz      short loc_180062003
0x180061ff7  call    cs:__imp_RegCloseKey
0x180061ffe  nop     dword ptr [rax+rax+00h]
0x180062003  mov     rcx, r12; pCertContext
0x180062006  call    cs:__imp_CertDuplicateCertificateContext
0x18006200d  nop     dword ptr [rax+rax+00h]
0x180062012  mov     rdi, rax
0x180062015  test    rax, rax
0x180062018  jnz     short loc_18006205A
0x18006201a  lea     ebx, [rax+57h]
0x18006201d  mov     rcx, cs:WPP_GLOBAL_Control
0x180062024  cmp     rcx, r14
0x180062027  jz      short loc_18006204C
0x180062029  test    dword ptr [rcx+1Ch], 200h
0x180062030  jz      short loc_18006204C
0x180062032  mov     rcx, [rcx+10h]
0x180062036  lea     edx, [rax+37h]
0x180062039  lea     r9, aVerifycertific; "VerifyCertificateChain"
0x180062040  lea     r8, WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids
0x180062047  call    WPP_SF_S
0x18006204c  test    rsi, rsi
0x18006204f  jz      loc_180062181
0x180062055  jmp     loc_18006211E
0x18006205a  lea     r9, [rbp+pdwFlags]; pdwFlags
0x18006205e  xor     r8d, r8d; pPrevIssuerContext
0x180062061  mov     rdx, rdi; pSubjectContext
0x180062064  mov     rcx, r13; hCertStore
0x180062067  call    cs:__imp_CertGetIssuerCertificateFromStore
0x18006206e  nop     dword ptr [rax+rax+00h]
0x180062073  mov     r15, rax
0x180062076  test    rax, rax
0x180062079  jz      short loc_1800620A4
0x18006207b  mov     ecx, [rbp+pdwFlags]; unsigned int
0x18006207e  call    ?GetCertVerificationResult@@YAKK@Z; GetCertVerificationResult(ulong)
0x180062083  mov     ebx, eax
0x180062085  test    eax, eax
0x180062087  jnz     short loc_18006204C
0x180062089  mov     rcx, rdi; pCertContext
0x18006208c  mov     [rbp+pdwFlags], 1
0x180062093  call    cs:__imp_CertFreeCertificateContext
0x18006209a  nop     dword ptr [rax+rax+00h]
0x18006209f  mov     rdi, r15
0x1800620a2  jmp     short loc_18006205A
0x1800620a4  test    rsi, rsi
0x1800620a7  jz      loc_18006212F
0x1800620ad  mov     [rbp+pdwFlags], 7
0x1800620b4  test    rdi, rdi
0x1800620b7  jz      short loc_1800620DF
0x1800620b9  lea     r8, [rbp+pdwFlags]; pdwFlags
0x1800620bd  mov     rdx, rsi; pIssuer
0x1800620c0  mov     rcx, rdi; pSubject
0x1800620c3  call    cs:__imp_CertVerifySubjectCertificateContext
0x1800620ca  nop     dword ptr [rax+rax+00h]
0x1800620cf  test    eax, eax
0x1800620d1  jz      short loc_1800620DF
0x1800620d3  mov     ecx, [rbp+pdwFlags]; unsigned int
0x1800620d6  call    ?GetCertVerificationResult@@YAKK@Z; GetCertVerificationResult(ulong)
0x1800620db  mov     ebx, eax
0x1800620dd  jmp     short loc_18006211E
0x1800620df  call    cs:__imp_GetLastError
0x1800620e6  nop     dword ptr [rax+rax+00h]
0x1800620eb  mov     ebx, eax
0x1800620ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800620f4  cmp     rcx, r14
0x1800620f7  jz      short loc_18006211E
0x1800620f9  test    dword ptr [rcx+1Ch], 200h
0x180062100  jz      short loc_18006211E
0x180062102  mov     rcx, [rcx+10h]
0x180062106  lea     r9, aVerifycertific; "VerifyCertificateChain"
0x18006210d  mov     edx, 38h ; '8'
0x180062112  lea     r8, WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids
0x180062119  call    WPP_SF_S
0x18006211e  mov     rcx, rsi; pCertContext
0x180062121  call    cs:__imp_CertFreeCertificateContext
0x180062128  nop     dword ptr [rax+rax+00h]
0x18006212d  jmp     short loc_180062181
0x18006212f  mov     rcx, cs:WPP_GLOBAL_Control
0x180062136  cmp     rcx, r14
0x180062139  jz      short loc_180062160
0x18006213b  test    dword ptr [rcx+1Ch], 2000h
0x180062142  jz      short loc_180062160
0x180062144  mov     rcx, [rcx+10h]
0x180062148  lea     r9, aVerifycertific; "VerifyCertificateChain"
0x18006214f  mov     edx, 39h ; '9'
0x180062154  lea     r8, WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids
0x18006215b  call    WPP_SF_S
0x180062160  call    cs:__imp_GetLastError
0x180062167  nop     dword ptr [rax+rax+00h]
0x18006216c  cmp     eax, 80092007h
0x180062171  jz      short loc_180062181
0x180062173  call    cs:__imp_GetLastError
0x18006217a  nop     dword ptr [rax+rax+00h]
0x18006217f  mov     ebx, eax
0x180062181  test    rdi, rdi
0x180062184  jz      short loc_180062195
0x180062186  mov     rcx, rdi; pCertContext
0x180062189  call    cs:__imp_CertFreeCertificateContext
0x180062190  nop     dword ptr [rax+rax+00h]
0x180062195  test    r15, r15
0x180062198  jz      short loc_1800621A9
0x18006219a  mov     rcx, r15; pCertContext
0x18006219d  call    cs:__imp_CertFreeCertificateContext
0x1800621a4  nop     dword ptr [rax+rax+00h]
0x1800621a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800621b0  cmp     rcx, r14
0x1800621b3  jz      short loc_1800621DE
0x1800621b5  test    dword ptr [rcx+1Ch], 1000h
0x1800621bc  jz      short loc_1800621DE
0x1800621be  mov     rcx, [rcx+10h]
0x1800621c2  lea     r9, aVerifycertific; "VerifyCertificateChain"
0x1800621c9  mov     edx, 3Ah ; ':'
0x1800621ce  mov     dword ptr [rsp+40h+phkResult], ebx
0x1800621d2  lea     r8, WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids
0x1800621d9  call    WPP_SF_SD
0x1800621de  lea     r11, [rsp+40h+var_s0]
0x1800621e3  mov     eax, ebx
0x1800621e5  mov     rbx, [r11+30h]
0x1800621e9  mov     rsi, [r11+38h]
0x1800621ed  mov     rdi, [r11+48h]
0x1800621f1  mov     rsp, r11
0x1800621f4  pop     r15
0x1800621f6  pop     r14
0x1800621f8  pop     r13
0x1800621fa  pop     r12
0x1800621fc  pop     rbp
0x1800621fd  retn
```
