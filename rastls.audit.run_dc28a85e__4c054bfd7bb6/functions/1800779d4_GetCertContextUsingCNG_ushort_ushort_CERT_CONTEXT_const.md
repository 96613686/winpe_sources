# GetCertContextUsingCNG(ushort *,ushort *,_CERT_CONTEXT const * *)

- ea: `0x1800779d4`
- end: `0x180077eb1`
- name: `?GetCertContextUsingCNG@@YAKPEAG0PEAPEBU_CERT_CONTEXT@@@Z`
- size: `1245`
- prototype: `unsigned int __fastcall(LPCWSTR pszProviderName, unsigned __int16 *, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180077eb8`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180010140`
- `0x180069258`
- `0x1800772f0`
- `0x1800779d4`
- `0x180078070`
- `0x180079970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077d80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077df7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077e07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077e16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077df7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077e07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077e16`
- `CRYPT32!CertFreeCertificateContext` at `0x180077e83`
- `CRYPT32!CertFreeCertificateContext` at `0x180077e83`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180077d70`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180077d70`
- `CRYPT32!CertCreateCertificateContext` at `0x180077c16`
- `CRYPT32!CertCreateCertificateContext` at `0x180077c16`
- `ncrypt!NCryptFreeBuffer` at `0x180077c5f`
- `ncrypt!NCryptFreeBuffer` at `0x180077e40`
- `ncrypt!NCryptFreeBuffer` at `0x180077e55`
- `ncrypt!NCryptFreeBuffer` at `0x180077c5f`
- `ncrypt!NCryptFreeBuffer` at `0x180077e40`
- `ncrypt!NCryptFreeBuffer` at `0x180077e55`
- `ncrypt!NCryptOpenStorageProvider` at `0x180077a62`
- `ncrypt!NCryptOpenStorageProvider` at `0x180077a62`
- `ncrypt!NCryptSetProperty` at `0x180077ad6`
- `ncrypt!NCryptSetProperty` at `0x180077ad6`
- `ncrypt!NCryptEnumKeys` at `0x180077c85`
- `ncrypt!NCryptEnumKeys` at `0x180077c85`
- `ncrypt!NCryptOpenKey` at `0x180077b63`
- `ncrypt!NCryptOpenKey` at `0x180077b63`
- `ncrypt!NCryptFreeObject` at `0x180077e2b`
- `ncrypt!NCryptFreeObject` at `0x180077e6a`
- `ncrypt!NCryptFreeObject` at `0x180077e2b`
- `ncrypt!NCryptFreeObject` at `0x180077e6a`

## string_xrefs

- `0x180077acf`: `SmartCardReader`

## pseudocode

```c
__int64 __fastcall GetCertContextUsingCNG(LPCWSTR pszProviderName, BYTE *a2, const struct _CERT_CONTEXT **a3)
{
  BYTE *v3; // r14
  unsigned __int8 *v4; // rsi
  unsigned int FormattedCardName; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v9; // rcx
  int v10; // edx
  __int64 v11; // r9
  struct _EAPTLS_CONTROL_BLOCK *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned int v15; // eax
  const struct _CERT_CONTEXT *CertificateContext; // rax
  DWORD LastError; // eax
  _DWORD *v18; // rcx
  unsigned int v19; // eax
  struct _EAPTLS_CONTROL_BLOCK *v20; // r10
  unsigned __int16 *v21; // rax
  int v22; // edx
  int v23; // r8d
  bool v24; // zf
  const CERT_CONTEXT *v25; // rcx
  unsigned int dwFlags; // [rsp+20h] [rbp-49h]
  unsigned int dwFlagsa; // [rsp+20h] [rbp-49h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+30h] [rbp-39h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+38h] [rbp-31h] BYREF
  BYTE *pbCertEncoded; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int8 *v32; // [rsp+48h] [rbp-21h] BYREF
  LPCWSTR pszKeyName; // [rsp+50h] [rbp-19h] BYREF
  PVOID ppEnumState; // [rsp+58h] [rbp-11h] BYREF
  __int128 pvData; // [rsp+60h] [rbp-9h] BYREF
  __int128 v36; // [rsp+70h] [rbp+7h]
  __int128 v37; // [rsp+80h] [rbp+17h]
  DWORD cbCertEncoded; // [rsp+E0h] [rbp+77h] BYREF
  PVOID pvInput; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = 0;
  pbCertEncoded = 0;
  cbCertEncoded = 0;
  v4 = 0;
  pszKeyName = 0;
  phProvider = 0;
  phKey = 0;
  pvData = 0;
  v32 = 0;
  v36 = 0;
  pvInput = 0;
  v37 = 0;
  ppEnumState = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids);
  FormattedCardName = NCryptOpenStorageProvider(&phProvider, pszProviderName, 0);
  if ( FormattedCardName )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_51;
    v10 = 35;
    goto LABEL_6;
  }
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)&a2[2 * v11] );
  FormattedCardName = NCryptSetProperty(phProvider, L"SmartCardReader", a2, 2 * v11 + 2, 0);
  if ( FormattedCardName )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_51;
    v13 = 36;
    goto LABEL_12;
  }
  FormattedCardName = GetFormattedCardName((const unsigned __int16 *)a2, (unsigned __int16 **)&pszKeyName);
  if ( FormattedCardName )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v13 = 37;
LABEL_12:
      v14 = FormattedCardName;
LABEL_13:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, v14);
    }
  }
  else
  {
    FormattedCardName = NCryptOpenKey(phProvider, &phKey, pszKeyName, 0, 0x40u);
    if ( FormattedCardName )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v10 = 38;
LABEL_6:
        WPP_SF_DS(
          *((_QWORD *)v9 + 2),
          v10,
          (unsigned int)&WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids,
          FormattedCardName,
          (__int64)pszProviderName);
      }
    }
    else
    {
      FormattedCardName = CNGGetProperty(phKey, L"Name", &v32, 0, dwFlags);
      if ( FormattedCardName )
      {
        v4 = v32;
      }
      else
      {
        v4 = v32;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, v32);
        v15 = CNGGetProperty(phKey, L"SmartCardKeyCertificate", &pbCertEncoded, &cbCertEncoded, dwFlagsa);
        v3 = pbCertEncoded;
        FormattedCardName = v15;
        if ( !v15 )
        {
          CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded, cbCertEncoded);
          *a3 = CertificateContext;
          if ( CertificateContext )
          {
            v18 = pvInput;
            while ( 1 )
            {
              if ( v18 )
              {
                NCryptFreeBuffer(v18);
                pvInput = 0;
              }
              v19 = NCryptEnumKeys(phProvider, 0, (NCryptKeyName **)&pvInput, &ppEnumState, 0x40u);
              if ( v19 )
              {
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    41,
                    &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids,
                    v19);
                  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids);
                }
                FormattedCardName = -2146893811;
                goto LABEL_51;
              }
              v20 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  42,
                  &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids,
                  *(_QWORD *)pvInput);
                v20 = WPP_GLOBAL_Control;
              }
              v18 = pvInput;
              if ( *((_DWORD *)pvInput + 4) != 2 )
              {
                if ( v20 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                {
                  WPP_SF_(*((_QWORD *)v20 + 2), 43, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids);
                  v18 = pvInput;
                  v20 = WPP_GLOBAL_Control;
                }
                v21 = *(unsigned __int16 **)v18;
                do
                {
                  v22 = *(unsigned __int16 *)&v4[(_QWORD)v21 - *(_QWORD *)v18];
                  v23 = *v21 - v22;
                  if ( v23 )
                    break;
                  ++v21;
                }
                while ( v22 );
                if ( !v23 )
                  break;
              }
            }
            if ( v20 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
              WPP_SF_SDD(*((_QWORD *)v20 + 2), v22, 0, *(_QWORD *)v18, v18[4], v18[5]);
              v18 = pvInput;
            }
            *(_QWORD *)&pvData = v4;
            *((_QWORD *)&pvData + 1) = pszProviderName;
            *(_QWORD *)&v36 = 0;
            DWORD2(v36) = 0;
            *(_QWORD *)&v37 = 0;
            v24 = v18[4] == 1;
            v25 = *a3;
            DWORD2(v37) = v24;
            if ( !CertSetCertificateContextProperty(v25, 2u, 0, &pvData) )
            {
              LastError = GetLastError();
              FormattedCardName = LastError;
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              {
                v13 = 46;
                goto LABEL_27;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            FormattedCardName = LastError;
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
              v13 = 40;
LABEL_27:
              v14 = LastError;
              goto LABEL_13;
            }
          }
        }
      }
    }
  }
LABEL_51:
  LocalFree(v3);
  LocalFree((HLOCAL)pszKeyName);
  LocalFree(v4);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( pvInput )
    NCryptFreeBuffer(pvInput);
  if ( ppEnumState )
    NCryptFreeBuffer(ppEnumState);
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( *a3 && FormattedCardName )
  {
    CertFreeCertificateContext(*a3);
    *a3 = 0;
  }
  return FormattedCardName;
}

```

## disassembly

```asm
0x1800779d4  mov     [rsp-8+arg_0], rbx
0x1800779d9  push    rbp
0x1800779da  push    rsi
0x1800779db  push    rdi
0x1800779dc  push    r12
0x1800779de  push    r13
0x1800779e0  push    r14
0x1800779e2  push    r15
0x1800779e4  lea     rbp, [rsp-27h]
0x1800779e9  sub     rsp, 90h
0x1800779f0  xor     r13d, r13d
0x1800779f3  xorps   xmm0, xmm0
0x1800779f6  mov     r14d, r13d
0x1800779f9  mov     [rbp+57h+pbCertEncoded], r13
0x1800779fd  mov     [rbp+57h+cbCertEncoded], r13d
0x180077a01  mov     esi, r13d
0x180077a04  mov     [rbp+57h+pszKeyName], r13
0x180077a08  mov     r12, r8
0x180077a0b  mov     [rbp+57h+phProvider], r13
0x180077a0f  mov     rdi, rdx
0x180077a12  mov     [rbp+57h+phKey], r13
0x180077a16  mov     r15, rcx
0x180077a19  movups  [rbp+57h+pvData], xmm0
0x180077a1d  mov     [rbp+57h+var_78], r13
0x180077a21  movups  [rbp+57h+var_50], xmm0
0x180077a25  mov     [rbp+57h+pvInput], r13
0x180077a29  movups  [rbp+57h+var_40], xmm0
0x180077a2d  mov     [rbp+57h+ppEnumState], r13
0x180077a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180077a38  lea     rax, WPP_GLOBAL_Control
0x180077a3f  cmp     rcx, rax
0x180077a42  jz      short loc_180077A58
0x180077a44  mov     rcx, [rcx+10h]
0x180077a48  lea     edx, [r13+22h]
0x180077a4c  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180077a53  call    WPP_SF_
0x180077a58  xor     r8d, r8d; dwFlags
0x180077a5b  lea     rcx, [rbp+57h+phProvider]; phProvider
0x180077a5f  mov     rdx, r15; pszProviderName
0x180077a62  call    cs:__imp_NCryptOpenStorageProvider
0x180077a69  nop     dword ptr [rax+rax+00h]
0x180077a6e  mov     ebx, eax
0x180077a70  test    eax, eax
0x180077a72  jz      short loc_180077AAD
0x180077a74  mov     rcx, cs:WPP_GLOBAL_Control
0x180077a7b  lea     rax, WPP_GLOBAL_Control
0x180077a82  cmp     rcx, rax
0x180077a85  jz      loc_180077DF4
0x180077a8b  mov     edx, 23h ; '#'
0x180077a90  mov     rcx, [rcx+10h]
0x180077a94  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180077a9b  mov     r9d, ebx
0x180077a9e  mov     qword ptr [rsp+0C0h+dwFlags], r15
0x180077aa3  call    WPP_SF_DS
0x180077aa8  jmp     loc_180077DF4
0x180077aad  or      r9, 0FFFFFFFFFFFFFFFFh
0x180077ab1  inc     r9
0x180077ab4  cmp     [rdi+r9*2], r13w
0x180077ab9  jnz     short loc_180077AB1
0x180077abb  mov     rcx, [rbp+57h+phProvider]; hObject
0x180077abf  lea     r9d, ds:2[r9*2]; cbInput
0x180077ac7  mov     r8, rdi; pbInput
0x180077aca  mov     [rsp+0C0h+dwFlags], r13d; dwFlags
0x180077acf  lea     rdx, aSmartcardreade; "SmartCardReader"
0x180077ad6  call    cs:__imp_NCryptSetProperty
0x180077add  nop     dword ptr [rax+rax+00h]
0x180077ae2  mov     ebx, eax
0x180077ae4  test    eax, eax
0x180077ae6  jz      short loc_180077B1C
0x180077ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180077aef  lea     rax, WPP_GLOBAL_Control
0x180077af6  cmp     rcx, rax
0x180077af9  jz      loc_180077DF4
0x180077aff  mov     edx, 24h ; '$'
0x180077b04  mov     r9d, ebx
0x180077b07  mov     rcx, [rcx+10h]
0x180077b0b  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180077b12  call    WPP_SF_d
0x180077b17  jmp     loc_180077DF4
0x180077b1c  lea     rdx, [rbp+57h+pszKeyName]; unsigned __int16 **
0x180077b20  mov     rcx, rdi; unsigned __int16 *
0x180077b23  call    ?GetFormattedCardName@@YAKPEBGPEAPEAG@Z; GetFormattedCardName(ushort const *,ushort * *)
0x180077b28  mov     ebx, eax
0x180077b2a  test    eax, eax
0x180077b2c  jz      short loc_180077B4C
0x180077b2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180077b35  lea     rax, WPP_GLOBAL_Control
0x180077b3c  cmp     rcx, rax
0x180077b3f  jz      loc_180077DF4
0x180077b45  mov     edx, 25h ; '%'
0x180077b4a  jmp     short loc_180077B04
0x180077b4c  mov     r8, [rbp+57h+pszKeyName]; pszKeyName
0x180077b50  lea     rdx, [rbp+57h+phKey]; phKey
0x180077b54  mov     rcx, [rbp+57h+phProvider]; hProvider
0x180077b58  xor     r9d, r9d; dwLegacyKeySpec
0x180077b5b  mov     [rsp+0C0h+dwFlags], 40h ; '@'; unsigned int
0x180077b63  call    cs:__imp_NCryptOpenKey
0x180077b6a  nop     dword ptr [rax+rax+00h]
0x180077b6f  mov     ebx, eax
0x180077b71  test    eax, eax
0x180077b73  jz      short loc_180077B96
0x180077b75  mov     rcx, cs:WPP_GLOBAL_Control
0x180077b7c  lea     rax, WPP_GLOBAL_Control
0x180077b83  cmp     rcx, rax
0x180077b86  jz      loc_180077DF4
0x180077b8c  mov     edx, 26h ; '&'
0x180077b91  jmp     loc_180077A90
0x180077b96  mov     rcx, [rbp+57h+phKey]; hObject
0x180077b9a  lea     r8, [rbp+57h+var_78]; unsigned __int8 **
0x180077b9e  xor     r9d, r9d; unsigned int *
0x180077ba1  lea     rdx, aName; "Name"
0x180077ba8  call    ?CNGGetProperty@@YAK_KPEBGPEAPEAEPEAKK@Z; CNGGetProperty(unsigned __int64,ushort const *,uchar * *,ulong *,ulong)
0x180077bad  mov     ebx, eax
0x180077baf  test    eax, eax
0x180077bb1  jnz     loc_180077DF0
0x180077bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180077bbe  lea     rdi, WPP_GLOBAL_Control
0x180077bc5  mov     rsi, [rbp+57h+var_78]
0x180077bc9  cmp     rcx, rdi
0x180077bcc  jz      short loc_180077BE4
0x180077bce  mov     rcx, [rcx+10h]
0x180077bd2  lea     edx, [rax+27h]
0x180077bd5  mov     r9, rsi
0x180077bd8  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180077bdf  call    WPP_SF_S
0x180077be4  mov     rcx, [rbp+57h+phKey]; hObject
0x180077be8  lea     r9, [rbp+57h+cbCertEncoded]; unsigned int *
0x180077bec  lea     r8, [rbp+57h+pbCertEncoded]; unsigned __int8 **
0x180077bf0  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180077bf7  call    ?CNGGetProperty@@YAK_KPEBGPEAPEAEPEAKK@Z; CNGGetProperty(unsigned __int64,ushort const *,uchar * *,ulong *,ulong)
0x180077bfc  mov     r14, [rbp+57h+pbCertEncoded]
0x180077c00  mov     ebx, eax
0x180077c02  test    eax, eax
0x180077c04  jnz     loc_180077DF4
0x180077c0a  mov     r8d, [rbp+57h+cbCertEncoded]; cbCertEncoded
0x180077c0e  mov     rdx, r14; pbCertEncoded
0x180077c11  mov     ecx, 10001h; dwCertEncodingType
0x180077c16  call    cs:__imp_CertCreateCertificateContext
0x180077c1d  nop     dword ptr [rax+rax+00h]
0x180077c22  mov     [r12], rax
0x180077c26  test    rax, rax
0x180077c29  jnz     short loc_180077C56
0x180077c2b  call    cs:__imp_GetLastError
0x180077c32  nop     dword ptr [rax+rax+00h]
0x180077c37  mov     ebx, eax
0x180077c39  mov     rcx, cs:WPP_GLOBAL_Control
0x180077c40  cmp     rcx, rdi
0x180077c43  jz      loc_180077DF4
0x180077c49  mov     edx, 28h ; '('
0x180077c4e  mov     r9d, eax
0x180077c51  jmp     loc_180077B07
0x180077c56  mov     rcx, [rbp+57h+pvInput]; pvInput
0x180077c5a  test    rcx, rcx
0x180077c5d  jz      short loc_180077C6F
0x180077c5f  call    cs:__imp_NCryptFreeBuffer
0x180077c66  nop     dword ptr [rax+rax+00h]
0x180077c6b  mov     [rbp+57h+pvInput], r13
0x180077c6f  mov     rcx, [rbp+57h+phProvider]; hProvider
0x180077c73  lea     r9, [rbp+57h+ppEnumState]; ppEnumState
0x180077c77  lea     r8, [rbp+57h+pvInput]; ppKeyName
0x180077c7b  mov     [rsp+0C0h+dwFlags], 40h ; '@'; dwFlags
0x180077c83  xor     edx, edx; pszScope
0x180077c85  call    cs:__imp_NCryptEnumKeys
0x180077c8c  nop     dword ptr [rax+rax+00h]
0x180077c91  test    eax, eax
0x180077c93  jnz     loc_180077DA4
0x180077c99  mov     r10, cs:WPP_GLOBAL_Control
0x180077ca0  cmp     r10, rdi
0x180077ca3  jz      short loc_180077CC6
0x180077ca5  mov     r9, [rbp+57h+pvInput]
0x180077ca9  lea     edx, [rax+2Ah]
0x180077cac  mov     rcx, [r10+10h]
0x180077cb0  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180077cb7  mov     r9, [r9]
0x180077cba  call    WPP_SF_S
0x180077cbf  mov     r10, cs:WPP_GLOBAL_Control
0x180077cc6  mov     rcx, [rbp+57h+pvInput]
0x180077cca  cmp     dword ptr [rcx+10h], 2
0x180077cce  jz      short loc_180077C5A
0x180077cd0  cmp     r10, rdi
0x180077cd3  jz      short loc_180077CF5
0x180077cd5  mov     rcx, [r10+10h]
0x180077cd9  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180077ce0  mov     edx, 2Bh ; '+'
0x180077ce5  call    WPP_SF_
0x180077cea  mov     rcx, [rbp+57h+pvInput]
0x180077cee  mov     r10, cs:WPP_GLOBAL_Control
0x180077cf5  mov     rax, [rcx]
0x180077cf8  mov     r9, rsi
0x180077cfb  sub     r9, rax
0x180077cfe  movzx   r8d, word ptr [rax]
0x180077d02  movzx   edx, word ptr [rax+r9]
0x180077d07  sub     r8d, edx
0x180077d0a  jnz     short loc_180077D14
0x180077d0c  add     rax, 2
0x180077d10  test    edx, edx
0x180077d12  jnz     short loc_180077CFE
0x180077d14  test    r8d, r8d
0x180077d17  jnz     loc_180077C5A
0x180077d1d  cmp     r10, rdi
0x180077d20  jz      short loc_180077D40
0x180077d22  mov     eax, [rcx+14h]
0x180077d25  mov     r9, [rcx]
0x180077d28  mov     [rsp+0C0h+var_98], eax
0x180077d2c  mov     eax, [rcx+10h]
0x180077d2f  mov     rcx, [r10+10h]
0x180077d33  mov     [rsp+0C0h+dwFlags], eax
0x180077d37  call    WPP_SF_SDD
0x180077d3c  mov     rcx, [rbp+57h+pvInput]
0x180077d40  mov     eax, r13d
0x180077d43  mov     qword ptr [rbp+57h+pvData], rsi
0x180077d47  mov     qword ptr [rbp+57h+pvData+8], r15
0x180077d4b  lea     r9, [rbp+57h+pvData]; pvData
0x180077d4f  mov     qword ptr [rbp+57h+var_50], r13
0x180077d53  mov     dword ptr [rbp+57h+var_50+8], r13d
0x180077d57  mov     qword ptr [rbp+57h+var_40], r13
0x180077d5b  cmp     dword ptr [rcx+10h], 1
0x180077d5f  mov     rcx, [r12]; pCertContext
0x180077d63  setz    al
0x180077d66  xor     r8d, r8d; dwFlags
0x180077d69  mov     dword ptr [rbp+57h+var_40+8], eax
0x180077d6c  lea     edx, [r8+2]; dwPropId
0x180077d70  call    cs:__imp_CertSetCertificateContextProperty
0x180077d77  nop     dword ptr [rax+rax+00h]
0x180077d7c  test    eax, eax
0x180077d7e  jnz     short loc_180077DF4
0x180077d80  call    cs:__imp_GetLastError
0x180077d87  nop     dword ptr [rax+rax+00h]
0x180077d8c  mov     ebx, eax
0x180077d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180077d95  cmp     rcx, rdi
0x180077d98  jz      short loc_180077DF4
0x180077d9a  mov     edx, 2Eh ; '.'
0x180077d9f  jmp     loc_180077C4E
0x180077da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180077dab  cmp     rcx, rdi
0x180077dae  jz      short loc_180077DE9
0x180077db0  mov     rcx, [rcx+10h]
0x180077db4  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180077dbb  mov     edx, 29h ; ')'
0x180077dc0  mov     r9d, eax
0x180077dc3  call    WPP_SF_d
0x180077dc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180077dcf  cmp     rcx, rdi
0x180077dd2  jz      short loc_180077DE9
0x180077dd4  mov     rcx, [rcx+10h]
0x180077dd8  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180077ddf  mov     edx, 2Dh ; '-'
0x180077de4  call    WPP_SF_
0x180077de9  mov     ebx, 8009000Dh
0x180077dee  jmp     short loc_180077DF4
0x180077df0  mov     rsi, [rbp+57h+var_78]
0x180077df4  mov     rcx, r14; hMem
0x180077df7  call    cs:__imp_LocalFree
0x180077dfe  nop     dword ptr [rax+rax+00h]
0x180077e03  mov     rcx, [rbp+57h+pszKeyName]; hMem
0x180077e07  call    cs:__imp_LocalFree
0x180077e0e  nop     dword ptr [rax+rax+00h]
0x180077e13  mov     rcx, rsi; hMem
0x180077e16  call    cs:__imp_LocalFree
0x180077e1d  nop     dword ptr [rax+rax+00h]
0x180077e22  mov     rcx, [rbp+57h+phProvider]; hObject
0x180077e26  test    rcx, rcx
0x180077e29  jz      short loc_180077E37
0x180077e2b  call    cs:__imp_NCryptFreeObject
0x180077e32  nop     dword ptr [rax+rax+00h]
0x180077e37  mov     rcx, [rbp+57h+pvInput]; pvInput
0x180077e3b  test    rcx, rcx
0x180077e3e  jz      short loc_180077E4C
0x180077e40  call    cs:__imp_NCryptFreeBuffer
0x180077e47  nop     dword ptr [rax+rax+00h]
0x180077e4c  mov     rcx, [rbp+57h+ppEnumState]; pvInput
0x180077e50  test    rcx, rcx
0x180077e53  jz      short loc_180077E61
0x180077e55  call    cs:__imp_NCryptFreeBuffer
0x180077e5c  nop     dword ptr [rax+rax+00h]
0x180077e61  mov     rcx, [rbp+57h+phKey]; hObject
0x180077e65  test    rcx, rcx
0x180077e68  jz      short loc_180077E76
0x180077e6a  call    cs:__imp_NCryptFreeObject
0x180077e71  nop     dword ptr [rax+rax+00h]
0x180077e76  mov     rcx, [r12]; pCertContext
0x180077e7a  test    rcx, rcx
0x180077e7d  jz      short loc_180077E93
0x180077e7f  test    ebx, ebx
0x180077e81  jz      short loc_180077E93
0x180077e83  call    cs:__imp_CertFreeCertificateContext
0x180077e8a  nop     dword ptr [rax+rax+00h]
0x180077e8f  mov     [r12], r13
0x180077e93  mov     eax, ebx
0x180077e95  mov     rbx, [rsp+0C0h+arg_0]
0x180077e9d  add     rsp, 90h
0x180077ea4  pop     r15
0x180077ea6  pop     r14
0x180077ea8  pop     r13
0x180077eaa  pop     r12
0x180077eac  pop     rdi
0x180077ead  pop     rsi
0x180077eae  pop     rbp
0x180077eaf  retn
  ... truncated ...
```
