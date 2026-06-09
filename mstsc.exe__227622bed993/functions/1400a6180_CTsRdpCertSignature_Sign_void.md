# CTsRdpCertSignature::Sign(void)

- ea: `0x1400a6180`
- end: `0x1400a68d5`
- name: `?Sign@CTsRdpCertSignature@@UEAAJXZ`
- size: `1877`
- prototype: `__int64 __fastcall(CTsRdpCertSignature *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x1400a53b8`
- `0x1400a5498`
- `0x1400a6180`
- `0x1400b1d80`
- `0x14010fea4`
- `0x1401100b8`

## import_xrefs

- `msvcrt!wcstombs_s` at `0x1400a64f0`
- `msvcrt!wcstombs_s` at `0x1400a65c1`
- `msvcrt!wcstombs_s` at `0x1400a64f0`
- `msvcrt!wcstombs_s` at `0x1400a65c1`
- `msvcrt!malloc` at `0x1400a63a7`
- `msvcrt!malloc` at `0x1400a654d`
- `msvcrt!malloc` at `0x1400a63a7`
- `msvcrt!malloc` at `0x1400a654d`
- `msvcrt!free` at `0x1400a6840`
- `msvcrt!free` at `0x1400a684e`
- `msvcrt!free` at `0x1400a6840`
- `msvcrt!free` at `0x1400a684e`
- `KERNEL32!LocalFree` at `0x1400a67fa`
- `KERNEL32!LocalFree` at `0x1400a67fa`
- `KERNEL32!GetLastError` at `0x1400a6697`
- `KERNEL32!GetLastError` at `0x1400a66d4`
- `KERNEL32!GetLastError` at `0x1400a67a5`
- `KERNEL32!GetLastError` at `0x1400a67e2`
- `KERNEL32!GetLastError` at `0x1400a6697`
- `KERNEL32!GetLastError` at `0x1400a66d4`
- `KERNEL32!GetLastError` at `0x1400a67a5`
- `KERNEL32!GetLastError` at `0x1400a67e2`
- `CRYPT32!CryptSignMessage` at `0x1400a666e`
- `CRYPT32!CryptSignMessage` at `0x1400a677c`
- `CRYPT32!CryptSignMessage` at `0x1400a666e`
- `CRYPT32!CryptSignMessage` at `0x1400a677c`
- `CRYPT32!CertFreeCertificateChain` at `0x1400a6832`
- `CRYPT32!CertFreeCertificateChain` at `0x1400a6832`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a6363`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a6363`
- `ADVAPI32!RegCloseKey` at `0x1400a68bb`
- `ADVAPI32!RegCloseKey` at `0x1400a68bb`
- `ADVAPI32!RegQueryValueExW` at `0x1400a6393`
- `ADVAPI32!RegQueryValueExW` at `0x1400a6422`
- `ADVAPI32!RegQueryValueExW` at `0x1400a6393`
- `ADVAPI32!RegQueryValueExW` at `0x1400a6422`

## string_xrefs

- `0x1400a6355`: `System\CurrentControlSet\Services\TScPubRPC`
- `0x1400a688c`: `attempt to sign with missing certificate/data`
- `0x1400a6228`: `attempt to sign with invalid signer certificate`
- `0x1400a64cf`: `HashAlgorithm registry type is incorrect`

## pseudocode

```c
__int64 __fastcall CTsRdpCertSignature::Sign(CTsRdpCertSignature *this)
{
  __int64 v2; // rcx
  signed int v3; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  void *v5; // r15
  void *v6; // r12
  CTsRdpCertSignature *v7; // rcx
  unsigned int v8; // eax
  CTsRdpCertSignature *v9; // rcx
  unsigned int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  unsigned int v13; // eax
  LSTATUS v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  int v17; // edx
  unsigned int v18; // eax
  unsigned int v19; // esi
  CHAR *v20; // rax
  signed int LastError; // eax
  unsigned int v22; // ebx
  unsigned int v23; // eax
  signed int v24; // eax
  void *v25; // rsi
  unsigned int v26; // eax
  signed int v27; // eax
  unsigned int v28; // ebx
  unsigned int v29; // eax
  signed int v30; // eax
  unsigned int v31; // eax
  size_t PtNumOfCharConverted; // [rsp+40h] [rbp-89h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+48h] [rbp-81h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-79h] BYREF
  struct _CERT_CONTEXT **v36; // [rsp+58h] [rbp-71h] BYREF
  BYTE *rgpbToBeSigned[2]; // [rsp+60h] [rbp-69h] BYREF
  _CRYPT_SIGN_MESSAGE_PARA pSignPara; // [rsp+70h] [rbp-59h] BYREF
  unsigned int v39; // [rsp+130h] [rbp+67h] BYREF
  DWORD cbData; // [rsp+138h] [rbp+6Fh] BYREF
  DWORD pcbSignedBlob; // [rsp+140h] [rbp+77h] BYREF
  DWORD Type; // [rsp+148h] [rbp+7Fh] BYREF

  memset_0(&pSignPara, 0, sizeof(pSignPara));
  v2 = *((_QWORD *)this + 7);
  pcbSignedBlob = 0;
  pChainContext = 0;
  v39 = 0;
  v36 = 0;
  cbData = 0;
  hKey = 0;
  if ( v2 && *((_DWORD *)this + 6) )
  {
    if ( !(unsigned int)TsCryptIsValidRdpSignEndCertificate(v2, &Type) )
    {
      v3 = -2147024883;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"attempt to sign with invalid signer certificate",
          13);
      }
      goto LABEL_97;
    }
    v5 = 0;
    v6 = 0;
    if ( (int)TsCryptConstructCertChain(*((PCCERT_CONTEXT *)this + 7), 0, 0, (__int64)&pChainContext) < 0 )
    {
      v3 = -2147023728;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
          v8,
          (__int64)"Unable to construct cert chain for signing",
          144);
      }
LABEL_87:
      if ( pChainContext )
        CertFreeCertificateChain(pChainContext);
      if ( v5 )
        free(v5);
      if ( v6 )
        free(v6);
      goto LABEL_97;
    }
    v3 = CTsRdpCertSignature::CertChainContextToArray(v7, pChainContext, &v39, (const struct _CERT_CONTEXT ***)&v36);
    if ( v3 < 0 )
    {
      v9 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_84;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 21;
      v12 = "CertChainContextToArray failed";
      goto LABEL_18;
    }
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\TScPubRPC", 0, 0x20019u, &hKey) )
      goto LABEL_56;
    cbData = 0;
    if ( RegQueryValueExW(hKey, L"HashAlgorithm", 0, 0, 0, &cbData) )
      goto LABEL_56;
    Type = 0;
    v5 = malloc(cbData);
    if ( !v5 )
    {
      v3 = -2147024882;
      v9 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
          v13,
          (__int64)"could not allocate bHashAlgorithm",
          14);
      }
      goto LABEL_84;
    }
    v14 = RegQueryValueExW(hKey, L"HashAlgorithm", 0, &Type, (LPBYTE)v5, &cbData);
    v3 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v3 = (unsigned __int16)v14 | 0x80070000;
      if ( v3 < 0 )
      {
        v9 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_84;
        }
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        v11 = 23;
        v12 = "RegQueryValueEx failed";
LABEL_18:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
          v10,
          (__int64)v12,
          v3);
        goto LABEL_84;
      }
      goto LABEL_56;
    }
    PtNumOfCharConverted = 0;
    if ( Type != 1 )
    {
      v3 = -2147024809;
      v9 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
          v15,
          (__int64)"HashAlgorithm registry type is incorrect",
          87);
      }
      goto LABEL_84;
    }
    if ( wcstombs_s(&PtNumOfCharConverted, 0, 0, (const wchar_t *)v5, cbData) )
    {
      v3 = -2147467259;
      v9 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_84;
      }
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 25;
    }
    else
    {
      v6 = malloc(PtNumOfCharConverted);
      if ( !v6 )
      {
        v3 = -2147024882;
        v9 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
            v18,
            (__int64)"could not allocate bHashAlgorithmA",
            14);
        }
        goto LABEL_84;
      }
      if ( !wcstombs_s(&PtNumOfCharConverted, (char *)v6, PtNumOfCharConverted, (const wchar_t *)v5, cbData) )
      {
LABEL_56:
        v19 = v39;
        pSignPara.cbSize = 120;
        pSignPara.dwMsgEncodingType = 65537;
        pSignPara.pSigningCert = *v36;
        v20 = "2.16.840.1.101.3.4.2.1";
        if ( v6 )
          v20 = (CHAR *)v6;
        pSignPara.rgpMsgCert = (PCCERT_CONTEXT *)v36;
        pSignPara.HashAlgorithm.pszObjId = v20;
        rgpbToBeSigned[0] = *((BYTE **)this + 2);
        pSignPara.cMsgCert = v39;
        if ( !CryptSignMessage(&pSignPara, 1, 1u, (const BYTE **)rgpbToBeSigned, (DWORD *)this + 6, 0, &pcbSignedBlob) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            LastError = GetLastError();
            v22 = LastError;
            if ( LastError > 0 )
              v22 = (unsigned __int16)LastError | 0x80070000;
            v23 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              28,
              WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
              v23,
              v22);
          }
          v24 = GetLastError();
          v3 = v24;
          if ( v24 > 0 )
            v3 = (unsigned __int16)v24 | 0x80070000;
          goto LABEL_85;
        }
        v25 = MIDL_user_allocate(pcbSignedBlob);
        if ( v25 )
        {
          if ( CryptSignMessage(
                 &pSignPara,
                 1,
                 1u,
                 (const BYTE **)rgpbToBeSigned,
                 (DWORD *)this + 6,
                 (BYTE *)v25,
                 &pcbSignedBlob) )
          {
            v3 = 0;
            *((_DWORD *)this + 10) = pcbSignedBlob;
            *((_QWORD *)this + 4) = v25;
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v27 = GetLastError();
              v28 = v27;
              if ( v27 > 0 )
                v28 = (unsigned __int16)v27 | 0x80070000;
              v29 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                30,
                WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
                v29,
                v28);
            }
            v30 = GetLastError();
            v3 = v30;
            if ( v30 > 0 )
              v3 = (unsigned __int16)v30 | 0x80070000;
            LocalFree(v25);
          }
        }
        else
        {
          v9 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v26 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Ds(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
              v26,
              (__int64)"pbSignedBlob");
          }
          v3 = -2147024882;
        }
LABEL_84:
        v19 = v39;
LABEL_85:
        if ( v36 )
          CTsRdpCertSignature::FreeCertArray(v9, v19, (const struct _CERT_CONTEXT **)v36);
        goto LABEL_87;
      }
      v3 = -2147467259;
      v9 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_84;
      }
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 27;
    }
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
      v16,
      (__int64)"wcstombs_s failed",
      5);
    goto LABEL_84;
  }
  v3 = -2147023728;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return (unsigned int)v3;
  }
  v31 = RdpWppGetCurrentThreadActivityIdPrefix();
  WPP_SF_DsD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    18,
    (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
    v31,
    (__int64)"attempt to sign with missing certificate/data",
    144);
LABEL_97:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400a6180  push    rbp
0x1400a6182  push    rbx
0x1400a6183  push    rsi
0x1400a6184  push    rdi
0x1400a6185  push    r12
0x1400a6187  push    r14
0x1400a6189  push    r15
0x1400a618b  lea     rbp, [rsp-27h]
0x1400a6190  sub     rsp, 0F0h
0x1400a6197  xor     edx, edx; Val
0x1400a6199  mov     rdi, rcx
0x1400a619c  lea     rcx, [rbp+57h+pSignPara]; void *
0x1400a61a0  lea     r8d, [rdx+78h]; Size
0x1400a61a4  call    memset_0
0x1400a61a9  mov     rcx, [rdi+38h]
0x1400a61ad  xor     esi, esi
0x1400a61af  mov     [rbp+57h+arg_10], esi
0x1400a61b2  mov     [rsp+120h+pChainContext], rsi
0x1400a61b7  mov     [rbp+57h+arg_0], esi
0x1400a61ba  mov     [rbp+57h+var_C8], rsi
0x1400a61be  mov     [rbp+57h+cbData], esi
0x1400a61c1  mov     [rbp+57h+hKey], rsi
0x1400a61c5  test    rcx, rcx
0x1400a61c8  jz      loc_1400A6856
0x1400a61ce  lea     r14, [rdi+18h]
0x1400a61d2  cmp     [r14], esi
0x1400a61d5  jz      loc_1400A6856
0x1400a61db  lea     rdx, [rbp+57h+Type]
0x1400a61df  call    TsCryptIsValidRdpSignEndCertificate
0x1400a61e4  test    eax, eax
0x1400a61e6  jnz     short loc_1400A6234
0x1400a61e8  mov     ebx, 8007000Dh
0x1400a61ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a61f4  lea     rax, WPP_GLOBAL_Control
0x1400a61fb  cmp     rcx, rax
0x1400a61fe  jz      loc_1400A68B2
0x1400a6204  test    byte ptr [rcx+1Ch], 8
0x1400a6208  jz      loc_1400A68B2
0x1400a620e  cmp     byte ptr [rcx+19h], 2
0x1400a6212  jb      loc_1400A68B2
0x1400a6218  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a621d  lea     edx, [rsi+13h]
0x1400a6220  mov     dword ptr [rsp+120h+lpcbData], 8007000Dh
0x1400a6228  lea     rcx, aAttemptToSignW; "attempt to sign with invalid signer cer"...
0x1400a622f  jmp     loc_1400A6893
0x1400a6234  mov     rcx, [rdi+38h]; pCertContext
0x1400a6238  lea     rax, [rsp+120h+pChainContext]
0x1400a623d  mov     [rsp+120h+pcbSignedBlob], rax; __int64
0x1400a6242  mov     r15, rsi
0x1400a6245  mov     [rsp+120h+lpcbData], rsi; hAdditionalStore
0x1400a624a  mov     r12, rsi
0x1400a624d  mov     dword ptr [rsp+120h+phkResult], esi; DWORD
0x1400a6251  call    TsCryptConstructCertChain
0x1400a6256  test    eax, eax
0x1400a6258  jns     short loc_1400A62C7
0x1400a625a  mov     ebx, 80070490h
0x1400a625f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6266  lea     rax, WPP_GLOBAL_Control
0x1400a626d  cmp     rcx, rax
0x1400a6270  jz      loc_1400A6826
0x1400a6276  test    byte ptr [rcx+1Ch], 8
0x1400a627a  jz      loc_1400A6826
0x1400a6280  cmp     byte ptr [rcx+19h], 2
0x1400a6284  jb      loc_1400A6826
0x1400a628a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a628f  lea     rcx, aUnableToConstr; "Unable to construct cert chain for sign"...
0x1400a6296  mov     dword ptr [rsp+120h+lpcbData], 80070490h
0x1400a629e  mov     [rsp+120h+phkResult], rcx
0x1400a62a3  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x1400a62aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a62b1  mov     edx, 14h
0x1400a62b6  mov     r9d, eax
0x1400a62b9  mov     rcx, [rcx+10h]
0x1400a62bd  call    WPP_SF_DsD
0x1400a62c2  jmp     loc_1400A6826
0x1400a62c7  mov     rdx, [rsp+120h+pChainContext]; struct _CERT_CHAIN_CONTEXT *
0x1400a62cc  lea     r9, [rbp+57h+var_C8]; struct _CERT_CONTEXT ***
0x1400a62d0  lea     r8, [rbp+57h+arg_0]; unsigned int *
0x1400a62d4  call    ?CertChainContextToArray@CTsRdpCertSignature@@AEAAJPEBU_CERT_CHAIN_CONTEXT@@PEAKPEAPEAPEBU_CERT_CONTEXT@@@Z; CTsRdpCertSignature::CertChainContextToArray(_CERT_CHAIN_CONTEXT const *,ulong *,_CERT_CONTEXT const * * *)
0x1400a62d9  mov     ebx, eax
0x1400a62db  test    eax, eax
0x1400a62dd  jns     short loc_1400A6343
0x1400a62df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a62e6  lea     rax, WPP_GLOBAL_Control
0x1400a62ed  cmp     rcx, rax
0x1400a62f0  jz      loc_1400A680E
0x1400a62f6  test    byte ptr [rcx+1Ch], 8
0x1400a62fa  jz      loc_1400A680E
0x1400a6300  cmp     byte ptr [rcx+19h], 2
0x1400a6304  jb      loc_1400A680E
0x1400a630a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a630f  mov     edx, 15h
0x1400a6314  lea     rcx, aCertchainconte; "CertChainContextToArray failed"
0x1400a631b  mov     dword ptr [rsp+120h+lpcbData], ebx
0x1400a631f  mov     [rsp+120h+phkResult], rcx
0x1400a6324  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x1400a632b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6332  mov     r9d, eax
0x1400a6335  mov     rcx, [rcx+10h]
0x1400a6339  call    WPP_SF_DsD
0x1400a633e  jmp     loc_1400A680E
0x1400a6343  lea     rax, [rbp+57h+hKey]
0x1400a6347  mov     r9d, 20019h; samDesired
0x1400a634d  xor     r8d, r8d; ulOptions
0x1400a6350  mov     [rsp+120h+phkResult], rax; phkResult
0x1400a6355  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\TS"...
0x1400a635c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400a6363  call    cs:__imp_RegOpenKeyExW
0x1400a6369  test    eax, eax
0x1400a636b  jnz     loc_1400A660A
0x1400a6371  mov     rcx, [rbp+57h+hKey]; hKey
0x1400a6375  lea     rax, [rbp+57h+cbData]
0x1400a6379  mov     [rsp+120h+lpcbData], rax; lpcbData
0x1400a637e  lea     rdx, aHashalgorithm; "HashAlgorithm"
0x1400a6385  xor     r9d, r9d; lpType
0x1400a6388  mov     [rsp+120h+phkResult], rsi; lpData
0x1400a638d  xor     r8d, r8d; lpReserved
0x1400a6390  mov     [rbp+57h+cbData], esi
0x1400a6393  call    cs:__imp_RegQueryValueExW
0x1400a6399  test    eax, eax
0x1400a639b  jnz     loc_1400A660A
0x1400a63a1  mov     ecx, [rbp+57h+cbData]; Size
0x1400a63a4  mov     [rbp+57h+Type], esi
0x1400a63a7  call    cs:__imp_malloc
0x1400a63ad  mov     r15, rax
0x1400a63b0  test    rax, rax
0x1400a63b3  jnz     short loc_1400A6402
0x1400a63b5  mov     ebx, 8007000Eh
0x1400a63ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a63c1  lea     rax, WPP_GLOBAL_Control
0x1400a63c8  cmp     rcx, rax
0x1400a63cb  jz      loc_1400A680E
0x1400a63d1  test    byte ptr [rcx+1Ch], 8
0x1400a63d5  jz      loc_1400A680E
0x1400a63db  cmp     byte ptr [rcx+19h], 2
0x1400a63df  jb      loc_1400A680E
0x1400a63e5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a63ea  lea     edx, [r15+16h]
0x1400a63ee  mov     dword ptr [rsp+120h+lpcbData], 8007000Eh
0x1400a63f6  lea     rcx, aCouldNotAlloca_0; "could not allocate bHashAlgorithm"
0x1400a63fd  jmp     loc_1400A631F
0x1400a6402  mov     rcx, [rbp+57h+hKey]; hKey
0x1400a6406  lea     rax, [rbp+57h+cbData]
0x1400a640a  mov     [rsp+120h+lpcbData], rax; lpcbData
0x1400a640f  lea     r9, [rbp+57h+Type]; lpType
0x1400a6413  xor     r8d, r8d; lpReserved
0x1400a6416  mov     [rsp+120h+phkResult], r15; lpData
0x1400a641b  lea     rdx, aHashalgorithm; "HashAlgorithm"
0x1400a6422  call    cs:__imp_RegQueryValueExW
0x1400a6428  mov     ebx, eax
0x1400a642a  test    eax, eax
0x1400a642c  jz      short loc_1400A6482
0x1400a642e  jle     short loc_1400A6439
0x1400a6430  movzx   ebx, ax
0x1400a6433  or      ebx, 80070000h
0x1400a6439  test    ebx, ebx
0x1400a643b  jns     loc_1400A660A
0x1400a6441  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6448  lea     rax, WPP_GLOBAL_Control
0x1400a644f  cmp     rcx, rax
0x1400a6452  jz      loc_1400A680E
0x1400a6458  test    byte ptr [rcx+1Ch], 8
0x1400a645c  jz      loc_1400A680E
0x1400a6462  cmp     byte ptr [rcx+19h], 2
0x1400a6466  jb      loc_1400A680E
0x1400a646c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a6471  mov     edx, 17h
0x1400a6476  lea     rcx, aRegqueryvaluee_0; "RegQueryValueEx failed"
0x1400a647d  jmp     loc_1400A631B
0x1400a6482  cmp     [rbp+57h+Type], 1
0x1400a6486  mov     [rsp+120h+PtNumOfCharConverted], rsi
0x1400a648b  jz      short loc_1400A64DB
0x1400a648d  mov     ebx, 80070057h
0x1400a6492  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6499  lea     rax, WPP_GLOBAL_Control
0x1400a64a0  cmp     rcx, rax
0x1400a64a3  jz      loc_1400A680E
0x1400a64a9  test    byte ptr [rcx+1Ch], 8
0x1400a64ad  jz      loc_1400A680E
0x1400a64b3  cmp     byte ptr [rcx+19h], 2
0x1400a64b7  jb      loc_1400A680E
0x1400a64bd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a64c2  mov     edx, 18h
0x1400a64c7  mov     dword ptr [rsp+120h+lpcbData], 80070057h
0x1400a64cf  lea     rcx, aHashalgorithmR; "HashAlgorithm registry type is incorrec"...
0x1400a64d6  jmp     loc_1400A631F
0x1400a64db  mov     eax, [rbp+57h+cbData]
0x1400a64de  lea     rcx, [rsp+120h+PtNumOfCharConverted]; PtNumOfCharConverted
0x1400a64e3  mov     r9, r15; Src
0x1400a64e6  mov     [rsp+120h+phkResult], rax; MaxCountInBytes
0x1400a64eb  xor     r8d, r8d; DstSizeInBytes
0x1400a64ee  xor     edx, edx; Dst
0x1400a64f0  call    cs:__imp_wcstombs_s
0x1400a64f6  test    eax, eax
0x1400a64f8  jz      short loc_1400A6548
0x1400a64fa  mov     ebx, 80004005h
0x1400a64ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6506  lea     rax, WPP_GLOBAL_Control
0x1400a650d  cmp     rcx, rax
0x1400a6510  jz      loc_1400A680E
0x1400a6516  test    byte ptr [rcx+1Ch], 8
0x1400a651a  jz      loc_1400A680E
0x1400a6520  cmp     byte ptr [rcx+19h], 2
0x1400a6524  jb      loc_1400A680E
0x1400a652a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a652f  mov     edx, 19h
0x1400a6534  mov     dword ptr [rsp+120h+lpcbData], 80004005h
0x1400a653c  lea     rcx, aWcstombsSFaile; "wcstombs_s failed"
0x1400a6543  jmp     loc_1400A631F
0x1400a6548  mov     rcx, [rsp+120h+PtNumOfCharConverted]; Size
0x1400a654d  call    cs:__imp_malloc
0x1400a6553  mov     r12, rax
0x1400a6556  test    rax, rax
0x1400a6559  jnz     short loc_1400A65A9
0x1400a655b  mov     ebx, 8007000Eh
0x1400a6560  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6567  lea     rax, WPP_GLOBAL_Control
0x1400a656e  cmp     rcx, rax
0x1400a6571  jz      loc_1400A680E
0x1400a6577  test    byte ptr [rcx+1Ch], 8
0x1400a657b  jz      loc_1400A680E
0x1400a6581  cmp     byte ptr [rcx+19h], 2
0x1400a6585  jb      loc_1400A680E
0x1400a658b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a6590  lea     edx, [r12+1Ah]
0x1400a6595  mov     dword ptr [rsp+120h+lpcbData], 8007000Eh
0x1400a659d  lea     rcx, aCouldNotAlloca; "could not allocate bHashAlgorithmA"
0x1400a65a4  jmp     loc_1400A631F
0x1400a65a9  mov     eax, [rbp+57h+cbData]
0x1400a65ac  lea     rcx, [rsp+120h+PtNumOfCharConverted]; PtNumOfCharConverted
0x1400a65b1  mov     r8, [rsp+120h+PtNumOfCharConverted]; DstSizeInBytes
0x1400a65b6  mov     r9, r15; Src
0x1400a65b9  mov     rdx, r12; Dst
0x1400a65bc  mov     [rsp+120h+phkResult], rax; MaxCountInBytes
0x1400a65c1  call    cs:__imp_wcstombs_s
0x1400a65c7  test    eax, eax
0x1400a65c9  jz      short loc_1400A660A
0x1400a65cb  mov     ebx, 80004005h
0x1400a65d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a65d7  lea     rax, WPP_GLOBAL_Control
0x1400a65de  cmp     rcx, rax
0x1400a65e1  jz      loc_1400A680E
0x1400a65e7  test    byte ptr [rcx+1Ch], 8
0x1400a65eb  jz      loc_1400A680E
0x1400a65f1  cmp     byte ptr [rcx+19h], 2
0x1400a65f5  jb      loc_1400A680E
0x1400a65fb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a6600  mov     edx, 1Bh
0x1400a6605  jmp     loc_1400A6534
0x1400a660a  mov     rcx, [rbp+57h+var_C8]
0x1400a660e  lea     r9, [rbp+57h+rgpbToBeSigned]; rgpbToBeSigned
0x1400a6612  mov     esi, [rbp+57h+arg_0]
0x1400a6615  mov     edx, 1; fDetachedSignature
0x1400a661a  mov     [rbp+57h+pSignPara.cbSize], 78h ; 'x'
0x1400a6621  test    r12, r12
0x1400a6624  mov     [rbp+57h+pSignPara.dwMsgEncodingType], 10001h
0x1400a662b  mov     r8d, edx; cToBeSigned
0x1400a662e  mov     rax, [rcx]
0x1400a6631  mov     [rbp+57h+pSignPara.pSigningCert], rax
0x1400a6635  lea     rax, a21684011013421; "2.16.840.1.101.3.4.2.1"
0x1400a663c  cmovnz  rax, r12
0x1400a6640  mov     [rbp+57h+pSignPara.rgpMsgCert], rcx
0x1400a6644  mov     [rbp+57h+pSignPara.HashAlgorithm.pszObjId], rax
0x1400a6648  lea     rcx, [rbp+57h+pSignPara]; pSignPara
0x1400a664c  mov     rax, [rdi+10h]
0x1400a6650  mov     [rbp+57h+rgpbToBeSigned], rax
0x1400a6654  lea     rax, [rbp+57h+arg_10]
0x1400a6658  mov     [rsp+120h+pcbSignedBlob], rax; pcbSignedBlob
0x1400a665d  mov     [rsp+120h+lpcbData], 0; pbSignedBlob
0x1400a6666  mov     [rsp+120h+phkResult], r14; rgcbToBeSigned
0x1400a666b  mov     [rbp+57h+pSignPara.cMsgCert], esi
0x1400a666e  call    cs:__imp_CryptSignMessage
0x1400a6674  test    eax, eax
0x1400a6676  jnz     short loc_1400A66F2
0x1400a6678  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a667f  lea     rax, WPP_GLOBAL_Control
0x1400a6686  cmp     rcx, rax
0x1400a6689  jz      short loc_1400A66D4
0x1400a668b  test    byte ptr [rcx+1Ch], 8
0x1400a668f  jz      short loc_1400A66D4
0x1400a6691  cmp     byte ptr [rcx+19h], 2
0x1400a6695  jb      short loc_1400A66D4
0x1400a6697  call    cs:__imp_GetLastError
0x1400a669d  mov     ebx, eax
0x1400a669f  test    eax, eax
0x1400a66a1  jle     short loc_1400A66AC
0x1400a66a3  movzx   ebx, ax
0x1400a66a6  or      ebx, 80070000h
0x1400a66ac  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a66b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a66b8  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x1400a66bf  mov     edx, 1Ch
0x1400a66c4  mov     dword ptr [rsp+120h+phkResult], ebx
0x1400a66c8  mov     r9d, eax
0x1400a66cb  mov     rcx, [rcx+10h]
0x1400a66cf  call    WPP_SF_Dd
0x1400a66d4  call    cs:__imp_GetLastError
0x1400a66da  mov     ebx, eax
0x1400a66dc  test    eax, eax
0x1400a66de  jle     loc_1400A6811
  ... truncated ...
```
