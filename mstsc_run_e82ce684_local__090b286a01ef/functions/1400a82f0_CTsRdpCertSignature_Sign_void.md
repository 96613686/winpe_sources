# CTsRdpCertSignature::Sign(void)

- ea: `0x1400a82f0`
- end: `0x1400a8a45`
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
- `0x1400a7528`
- `0x1400a7608`
- `0x1400a82f0`
- `0x1400b3ef0`
- `0x140112014`
- `0x140112228`

## import_xrefs

- `msvcrt!wcstombs_s` at `0x1400a8660`
- `msvcrt!wcstombs_s` at `0x1400a8731`
- `msvcrt!wcstombs_s` at `0x1400a8660`
- `msvcrt!wcstombs_s` at `0x1400a8731`
- `msvcrt!malloc` at `0x1400a8517`
- `msvcrt!malloc` at `0x1400a86bd`
- `msvcrt!malloc` at `0x1400a8517`
- `msvcrt!malloc` at `0x1400a86bd`
- `msvcrt!free` at `0x1400a89b0`
- `msvcrt!free` at `0x1400a89be`
- `msvcrt!free` at `0x1400a89b0`
- `msvcrt!free` at `0x1400a89be`
- `KERNEL32!LocalFree` at `0x1400a896a`
- `KERNEL32!LocalFree` at `0x1400a896a`
- `KERNEL32!GetLastError` at `0x1400a8807`
- `KERNEL32!GetLastError` at `0x1400a8844`
- `KERNEL32!GetLastError` at `0x1400a8915`
- `KERNEL32!GetLastError` at `0x1400a8952`
- `KERNEL32!GetLastError` at `0x1400a8807`
- `KERNEL32!GetLastError` at `0x1400a8844`
- `KERNEL32!GetLastError` at `0x1400a8915`
- `KERNEL32!GetLastError` at `0x1400a8952`
- `CRYPT32!CryptSignMessage` at `0x1400a87de`
- `CRYPT32!CryptSignMessage` at `0x1400a88ec`
- `CRYPT32!CryptSignMessage` at `0x1400a87de`
- `CRYPT32!CryptSignMessage` at `0x1400a88ec`
- `CRYPT32!CertFreeCertificateChain` at `0x1400a89a2`
- `CRYPT32!CertFreeCertificateChain` at `0x1400a89a2`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a84d3`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a84d3`
- `ADVAPI32!RegCloseKey` at `0x1400a8a2b`
- `ADVAPI32!RegCloseKey` at `0x1400a8a2b`
- `ADVAPI32!RegQueryValueExW` at `0x1400a8503`
- `ADVAPI32!RegQueryValueExW` at `0x1400a8592`
- `ADVAPI32!RegQueryValueExW` at `0x1400a8503`
- `ADVAPI32!RegQueryValueExW` at `0x1400a8592`

## string_xrefs

- `0x1400a84c5`: `System\CurrentControlSet\Services\TScPubRPC`
- `0x1400a89fc`: `attempt to sign with missing certificate/data`
- `0x1400a8398`: `attempt to sign with invalid signer certificate`
- `0x1400a863f`: `HashAlgorithm registry type is incorrect`

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
0x1400a82f0  push    rbp
0x1400a82f2  push    rbx
0x1400a82f3  push    rsi
0x1400a82f4  push    rdi
0x1400a82f5  push    r12
0x1400a82f7  push    r14
0x1400a82f9  push    r15
0x1400a82fb  lea     rbp, [rsp-27h]
0x1400a8300  sub     rsp, 0F0h
0x1400a8307  xor     edx, edx; Val
0x1400a8309  mov     rdi, rcx
0x1400a830c  lea     rcx, [rbp+57h+pSignPara]; void *
0x1400a8310  lea     r8d, [rdx+78h]; Size
0x1400a8314  call    memset_0
0x1400a8319  mov     rcx, [rdi+38h]
0x1400a831d  xor     esi, esi
0x1400a831f  mov     [rbp+57h+arg_10], esi
0x1400a8322  mov     [rsp+120h+pChainContext], rsi
0x1400a8327  mov     [rbp+57h+arg_0], esi
0x1400a832a  mov     [rbp+57h+var_C8], rsi
0x1400a832e  mov     [rbp+57h+cbData], esi
0x1400a8331  mov     [rbp+57h+hKey], rsi
0x1400a8335  test    rcx, rcx
0x1400a8338  jz      loc_1400A89C6
0x1400a833e  lea     r14, [rdi+18h]
0x1400a8342  cmp     [r14], esi
0x1400a8345  jz      loc_1400A89C6
0x1400a834b  lea     rdx, [rbp+57h+Type]
0x1400a834f  call    TsCryptIsValidRdpSignEndCertificate
0x1400a8354  test    eax, eax
0x1400a8356  jnz     short loc_1400A83A4
0x1400a8358  mov     ebx, 8007000Dh
0x1400a835d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8364  lea     rax, WPP_GLOBAL_Control
0x1400a836b  cmp     rcx, rax
0x1400a836e  jz      loc_1400A8A22
0x1400a8374  test    byte ptr [rcx+1Ch], 8
0x1400a8378  jz      loc_1400A8A22
0x1400a837e  cmp     byte ptr [rcx+19h], 2
0x1400a8382  jb      loc_1400A8A22
0x1400a8388  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a838d  lea     edx, [rsi+13h]
0x1400a8390  mov     dword ptr [rsp+120h+lpcbData], 8007000Dh
0x1400a8398  lea     rcx, aAttemptToSignW; "attempt to sign with invalid signer cer"...
0x1400a839f  jmp     loc_1400A8A03
0x1400a83a4  mov     rcx, [rdi+38h]; pCertContext
0x1400a83a8  lea     rax, [rsp+120h+pChainContext]
0x1400a83ad  mov     [rsp+120h+pcbSignedBlob], rax; __int64
0x1400a83b2  mov     r15, rsi
0x1400a83b5  mov     [rsp+120h+lpcbData], rsi; hAdditionalStore
0x1400a83ba  mov     r12, rsi
0x1400a83bd  mov     dword ptr [rsp+120h+phkResult], esi; DWORD
0x1400a83c1  call    TsCryptConstructCertChain
0x1400a83c6  test    eax, eax
0x1400a83c8  jns     short loc_1400A8437
0x1400a83ca  mov     ebx, 80070490h
0x1400a83cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a83d6  lea     rax, WPP_GLOBAL_Control
0x1400a83dd  cmp     rcx, rax
0x1400a83e0  jz      loc_1400A8996
0x1400a83e6  test    byte ptr [rcx+1Ch], 8
0x1400a83ea  jz      loc_1400A8996
0x1400a83f0  cmp     byte ptr [rcx+19h], 2
0x1400a83f4  jb      loc_1400A8996
0x1400a83fa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a83ff  lea     rcx, aUnableToConstr; "Unable to construct cert chain for sign"...
0x1400a8406  mov     dword ptr [rsp+120h+lpcbData], 80070490h
0x1400a840e  mov     [rsp+120h+phkResult], rcx
0x1400a8413  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x1400a841a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8421  mov     edx, 14h
0x1400a8426  mov     r9d, eax
0x1400a8429  mov     rcx, [rcx+10h]
0x1400a842d  call    WPP_SF_DsD
0x1400a8432  jmp     loc_1400A8996
0x1400a8437  mov     rdx, [rsp+120h+pChainContext]; struct _CERT_CHAIN_CONTEXT *
0x1400a843c  lea     r9, [rbp+57h+var_C8]; struct _CERT_CONTEXT ***
0x1400a8440  lea     r8, [rbp+57h+arg_0]; unsigned int *
0x1400a8444  call    ?CertChainContextToArray@CTsRdpCertSignature@@AEAAJPEBU_CERT_CHAIN_CONTEXT@@PEAKPEAPEAPEBU_CERT_CONTEXT@@@Z; CTsRdpCertSignature::CertChainContextToArray(_CERT_CHAIN_CONTEXT const *,ulong *,_CERT_CONTEXT const * * *)
0x1400a8449  mov     ebx, eax
0x1400a844b  test    eax, eax
0x1400a844d  jns     short loc_1400A84B3
0x1400a844f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8456  lea     rax, WPP_GLOBAL_Control
0x1400a845d  cmp     rcx, rax
0x1400a8460  jz      loc_1400A897E
0x1400a8466  test    byte ptr [rcx+1Ch], 8
0x1400a846a  jz      loc_1400A897E
0x1400a8470  cmp     byte ptr [rcx+19h], 2
0x1400a8474  jb      loc_1400A897E
0x1400a847a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a847f  mov     edx, 15h
0x1400a8484  lea     rcx, aCertchainconte; "CertChainContextToArray failed"
0x1400a848b  mov     dword ptr [rsp+120h+lpcbData], ebx
0x1400a848f  mov     [rsp+120h+phkResult], rcx
0x1400a8494  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x1400a849b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a84a2  mov     r9d, eax
0x1400a84a5  mov     rcx, [rcx+10h]
0x1400a84a9  call    WPP_SF_DsD
0x1400a84ae  jmp     loc_1400A897E
0x1400a84b3  lea     rax, [rbp+57h+hKey]
0x1400a84b7  mov     r9d, 20019h; samDesired
0x1400a84bd  xor     r8d, r8d; ulOptions
0x1400a84c0  mov     [rsp+120h+phkResult], rax; phkResult
0x1400a84c5  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\TS"...
0x1400a84cc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400a84d3  call    cs:__imp_RegOpenKeyExW
0x1400a84d9  test    eax, eax
0x1400a84db  jnz     loc_1400A877A
0x1400a84e1  mov     rcx, [rbp+57h+hKey]; hKey
0x1400a84e5  lea     rax, [rbp+57h+cbData]
0x1400a84e9  mov     [rsp+120h+lpcbData], rax; lpcbData
0x1400a84ee  lea     rdx, aHashalgorithm; "HashAlgorithm"
0x1400a84f5  xor     r9d, r9d; lpType
0x1400a84f8  mov     [rsp+120h+phkResult], rsi; lpData
0x1400a84fd  xor     r8d, r8d; lpReserved
0x1400a8500  mov     [rbp+57h+cbData], esi
0x1400a8503  call    cs:__imp_RegQueryValueExW
0x1400a8509  test    eax, eax
0x1400a850b  jnz     loc_1400A877A
0x1400a8511  mov     ecx, [rbp+57h+cbData]; Size
0x1400a8514  mov     [rbp+57h+Type], esi
0x1400a8517  call    cs:__imp_malloc
0x1400a851d  mov     r15, rax
0x1400a8520  test    rax, rax
0x1400a8523  jnz     short loc_1400A8572
0x1400a8525  mov     ebx, 8007000Eh
0x1400a852a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8531  lea     rax, WPP_GLOBAL_Control
0x1400a8538  cmp     rcx, rax
0x1400a853b  jz      loc_1400A897E
0x1400a8541  test    byte ptr [rcx+1Ch], 8
0x1400a8545  jz      loc_1400A897E
0x1400a854b  cmp     byte ptr [rcx+19h], 2
0x1400a854f  jb      loc_1400A897E
0x1400a8555  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a855a  lea     edx, [r15+16h]
0x1400a855e  mov     dword ptr [rsp+120h+lpcbData], 8007000Eh
0x1400a8566  lea     rcx, aCouldNotAlloca_0; "could not allocate bHashAlgorithm"
0x1400a856d  jmp     loc_1400A848F
0x1400a8572  mov     rcx, [rbp+57h+hKey]; hKey
0x1400a8576  lea     rax, [rbp+57h+cbData]
0x1400a857a  mov     [rsp+120h+lpcbData], rax; lpcbData
0x1400a857f  lea     r9, [rbp+57h+Type]; lpType
0x1400a8583  xor     r8d, r8d; lpReserved
0x1400a8586  mov     [rsp+120h+phkResult], r15; lpData
0x1400a858b  lea     rdx, aHashalgorithm; "HashAlgorithm"
0x1400a8592  call    cs:__imp_RegQueryValueExW
0x1400a8598  mov     ebx, eax
0x1400a859a  test    eax, eax
0x1400a859c  jz      short loc_1400A85F2
0x1400a859e  jle     short loc_1400A85A9
0x1400a85a0  movzx   ebx, ax
0x1400a85a3  or      ebx, 80070000h
0x1400a85a9  test    ebx, ebx
0x1400a85ab  jns     loc_1400A877A
0x1400a85b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a85b8  lea     rax, WPP_GLOBAL_Control
0x1400a85bf  cmp     rcx, rax
0x1400a85c2  jz      loc_1400A897E
0x1400a85c8  test    byte ptr [rcx+1Ch], 8
0x1400a85cc  jz      loc_1400A897E
0x1400a85d2  cmp     byte ptr [rcx+19h], 2
0x1400a85d6  jb      loc_1400A897E
0x1400a85dc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a85e1  mov     edx, 17h
0x1400a85e6  lea     rcx, aRegqueryvaluee_0; "RegQueryValueEx failed"
0x1400a85ed  jmp     loc_1400A848B
0x1400a85f2  cmp     [rbp+57h+Type], 1
0x1400a85f6  mov     [rsp+120h+PtNumOfCharConverted], rsi
0x1400a85fb  jz      short loc_1400A864B
0x1400a85fd  mov     ebx, 80070057h
0x1400a8602  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8609  lea     rax, WPP_GLOBAL_Control
0x1400a8610  cmp     rcx, rax
0x1400a8613  jz      loc_1400A897E
0x1400a8619  test    byte ptr [rcx+1Ch], 8
0x1400a861d  jz      loc_1400A897E
0x1400a8623  cmp     byte ptr [rcx+19h], 2
0x1400a8627  jb      loc_1400A897E
0x1400a862d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a8632  mov     edx, 18h
0x1400a8637  mov     dword ptr [rsp+120h+lpcbData], 80070057h
0x1400a863f  lea     rcx, aHashalgorithmR; "HashAlgorithm registry type is incorrec"...
0x1400a8646  jmp     loc_1400A848F
0x1400a864b  mov     eax, [rbp+57h+cbData]
0x1400a864e  lea     rcx, [rsp+120h+PtNumOfCharConverted]; PtNumOfCharConverted
0x1400a8653  mov     r9, r15; Src
0x1400a8656  mov     [rsp+120h+phkResult], rax; MaxCountInBytes
0x1400a865b  xor     r8d, r8d; DstSizeInBytes
0x1400a865e  xor     edx, edx; Dst
0x1400a8660  call    cs:__imp_wcstombs_s
0x1400a8666  test    eax, eax
0x1400a8668  jz      short loc_1400A86B8
0x1400a866a  mov     ebx, 80004005h
0x1400a866f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8676  lea     rax, WPP_GLOBAL_Control
0x1400a867d  cmp     rcx, rax
0x1400a8680  jz      loc_1400A897E
0x1400a8686  test    byte ptr [rcx+1Ch], 8
0x1400a868a  jz      loc_1400A897E
0x1400a8690  cmp     byte ptr [rcx+19h], 2
0x1400a8694  jb      loc_1400A897E
0x1400a869a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a869f  mov     edx, 19h
0x1400a86a4  mov     dword ptr [rsp+120h+lpcbData], 80004005h
0x1400a86ac  lea     rcx, aWcstombsSFaile; "wcstombs_s failed"
0x1400a86b3  jmp     loc_1400A848F
0x1400a86b8  mov     rcx, [rsp+120h+PtNumOfCharConverted]; Size
0x1400a86bd  call    cs:__imp_malloc
0x1400a86c3  mov     r12, rax
0x1400a86c6  test    rax, rax
0x1400a86c9  jnz     short loc_1400A8719
0x1400a86cb  mov     ebx, 8007000Eh
0x1400a86d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a86d7  lea     rax, WPP_GLOBAL_Control
0x1400a86de  cmp     rcx, rax
0x1400a86e1  jz      loc_1400A897E
0x1400a86e7  test    byte ptr [rcx+1Ch], 8
0x1400a86eb  jz      loc_1400A897E
0x1400a86f1  cmp     byte ptr [rcx+19h], 2
0x1400a86f5  jb      loc_1400A897E
0x1400a86fb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a8700  lea     edx, [r12+1Ah]
0x1400a8705  mov     dword ptr [rsp+120h+lpcbData], 8007000Eh
0x1400a870d  lea     rcx, aCouldNotAlloca; "could not allocate bHashAlgorithmA"
0x1400a8714  jmp     loc_1400A848F
0x1400a8719  mov     eax, [rbp+57h+cbData]
0x1400a871c  lea     rcx, [rsp+120h+PtNumOfCharConverted]; PtNumOfCharConverted
0x1400a8721  mov     r8, [rsp+120h+PtNumOfCharConverted]; DstSizeInBytes
0x1400a8726  mov     r9, r15; Src
0x1400a8729  mov     rdx, r12; Dst
0x1400a872c  mov     [rsp+120h+phkResult], rax; MaxCountInBytes
0x1400a8731  call    cs:__imp_wcstombs_s
0x1400a8737  test    eax, eax
0x1400a8739  jz      short loc_1400A877A
0x1400a873b  mov     ebx, 80004005h
0x1400a8740  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8747  lea     rax, WPP_GLOBAL_Control
0x1400a874e  cmp     rcx, rax
0x1400a8751  jz      loc_1400A897E
0x1400a8757  test    byte ptr [rcx+1Ch], 8
0x1400a875b  jz      loc_1400A897E
0x1400a8761  cmp     byte ptr [rcx+19h], 2
0x1400a8765  jb      loc_1400A897E
0x1400a876b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a8770  mov     edx, 1Bh
0x1400a8775  jmp     loc_1400A86A4
0x1400a877a  mov     rcx, [rbp+57h+var_C8]
0x1400a877e  lea     r9, [rbp+57h+rgpbToBeSigned]; rgpbToBeSigned
0x1400a8782  mov     esi, [rbp+57h+arg_0]
0x1400a8785  mov     edx, 1; fDetachedSignature
0x1400a878a  mov     [rbp+57h+pSignPara.cbSize], 78h ; 'x'
0x1400a8791  test    r12, r12
0x1400a8794  mov     [rbp+57h+pSignPara.dwMsgEncodingType], 10001h
0x1400a879b  mov     r8d, edx; cToBeSigned
0x1400a879e  mov     rax, [rcx]
0x1400a87a1  mov     [rbp+57h+pSignPara.pSigningCert], rax
0x1400a87a5  lea     rax, a21684011013421; "2.16.840.1.101.3.4.2.1"
0x1400a87ac  cmovnz  rax, r12
0x1400a87b0  mov     [rbp+57h+pSignPara.rgpMsgCert], rcx
0x1400a87b4  mov     [rbp+57h+pSignPara.HashAlgorithm.pszObjId], rax
0x1400a87b8  lea     rcx, [rbp+57h+pSignPara]; pSignPara
0x1400a87bc  mov     rax, [rdi+10h]
0x1400a87c0  mov     [rbp+57h+rgpbToBeSigned], rax
0x1400a87c4  lea     rax, [rbp+57h+arg_10]
0x1400a87c8  mov     [rsp+120h+pcbSignedBlob], rax; pcbSignedBlob
0x1400a87cd  mov     [rsp+120h+lpcbData], 0; pbSignedBlob
0x1400a87d6  mov     [rsp+120h+phkResult], r14; rgcbToBeSigned
0x1400a87db  mov     [rbp+57h+pSignPara.cMsgCert], esi
0x1400a87de  call    cs:__imp_CryptSignMessage
0x1400a87e4  test    eax, eax
0x1400a87e6  jnz     short loc_1400A8862
0x1400a87e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a87ef  lea     rax, WPP_GLOBAL_Control
0x1400a87f6  cmp     rcx, rax
0x1400a87f9  jz      short loc_1400A8844
0x1400a87fb  test    byte ptr [rcx+1Ch], 8
0x1400a87ff  jz      short loc_1400A8844
0x1400a8801  cmp     byte ptr [rcx+19h], 2
0x1400a8805  jb      short loc_1400A8844
0x1400a8807  call    cs:__imp_GetLastError
0x1400a880d  mov     ebx, eax
0x1400a880f  test    eax, eax
0x1400a8811  jle     short loc_1400A881C
0x1400a8813  movzx   ebx, ax
0x1400a8816  or      ebx, 80070000h
0x1400a881c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a8821  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8828  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x1400a882f  mov     edx, 1Ch
0x1400a8834  mov     dword ptr [rsp+120h+phkResult], ebx
0x1400a8838  mov     r9d, eax
0x1400a883b  mov     rcx, [rcx+10h]
0x1400a883f  call    WPP_SF_Dd
0x1400a8844  call    cs:__imp_GetLastError
0x1400a884a  mov     ebx, eax
0x1400a884c  test    eax, eax
0x1400a884e  jle     loc_1400A8981
  ... truncated ...
```
