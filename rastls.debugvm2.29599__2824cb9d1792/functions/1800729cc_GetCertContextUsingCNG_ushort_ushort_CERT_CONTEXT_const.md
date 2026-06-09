# GetCertContextUsingCNG(ushort *,ushort *,_CERT_CONTEXT const * *)

- ea: `0x1800729cc`
- end: `0x180072e42`
- name: `?GetCertContextUsingCNG@@YAKPEAG0PEAPEBU_CERT_CONTEXT@@@Z`
- size: `1142`
- prototype: `unsigned int __fastcall(LPCWSTR pszProviderName, unsigned __int16 *, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180072e48`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18000f350`
- `0x18006564c`
- `0x1800723b0`
- `0x1800729cc`
- `0x180072fe4`
- `0x1800746b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072d48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072d48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072db9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072dc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072dcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072db9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072dc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072dcc`
- `CRYPT32!CertFreeCertificateContext` at `0x180072e1b`
- `CRYPT32!CertFreeCertificateContext` at `0x180072e1b`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180072d3e`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180072d3e`
- `CRYPT32!CertCreateCertificateContext` at `0x180072bfc`
- `CRYPT32!CertCreateCertificateContext` at `0x180072bfc`
- `ncrypt!NCryptFreeBuffer` at `0x180072c39`
- `ncrypt!NCryptFreeBuffer` at `0x180072dea`
- `ncrypt!NCryptFreeBuffer` at `0x180072df9`
- `ncrypt!NCryptFreeBuffer` at `0x180072c39`
- `ncrypt!NCryptFreeBuffer` at `0x180072dea`
- `ncrypt!NCryptFreeBuffer` at `0x180072df9`
- `ncrypt!NCryptOpenStorageProvider` at `0x180072a5a`
- `ncrypt!NCryptOpenStorageProvider` at `0x180072a5a`
- `ncrypt!NCryptSetProperty` at `0x180072ac8`
- `ncrypt!NCryptSetProperty` at `0x180072ac8`
- `ncrypt!NCryptEnumKeys` at `0x180072c59`
- `ncrypt!NCryptEnumKeys` at `0x180072c59`
- `ncrypt!NCryptOpenKey` at `0x180072b4f`
- `ncrypt!NCryptOpenKey` at `0x180072b4f`
- `ncrypt!NCryptFreeObject` at `0x180072ddb`
- `ncrypt!NCryptFreeObject` at `0x180072e08`
- `ncrypt!NCryptFreeObject` at `0x180072ddb`
- `ncrypt!NCryptFreeObject` at `0x180072e08`

## string_xrefs

- `0x180072ac1`: `SmartCardReader`

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
0x1800729cc  mov     [rsp-8+arg_0], rbx
0x1800729d1  push    rbp
0x1800729d2  push    rsi
0x1800729d3  push    rdi
0x1800729d4  push    r12
0x1800729d6  push    r13
0x1800729d8  push    r14
0x1800729da  push    r15
0x1800729dc  lea     rbp, [rsp-27h]
0x1800729e1  sub     rsp, 90h
0x1800729e8  xor     r13d, r13d
0x1800729eb  xorps   xmm0, xmm0
0x1800729ee  mov     r14d, r13d
0x1800729f1  mov     [rbp+57h+pbCertEncoded], r13
0x1800729f5  mov     [rbp+57h+cbCertEncoded], r13d
0x1800729f9  mov     esi, r13d
0x1800729fc  mov     [rbp+57h+pszKeyName], r13
0x180072a00  mov     r12, r8
0x180072a03  mov     [rbp+57h+phProvider], r13
0x180072a07  mov     rdi, rdx
0x180072a0a  mov     [rbp+57h+phKey], r13
0x180072a0e  mov     r15, rcx
0x180072a11  movups  [rbp+57h+pvData], xmm0
0x180072a15  mov     [rbp+57h+var_78], r13
0x180072a19  movups  [rbp+57h+var_50], xmm0
0x180072a1d  mov     [rbp+57h+pvInput], r13
0x180072a21  movups  [rbp+57h+var_40], xmm0
0x180072a25  mov     [rbp+57h+ppEnumState], r13
0x180072a29  mov     rcx, cs:WPP_GLOBAL_Control
0x180072a30  lea     rax, WPP_GLOBAL_Control
0x180072a37  cmp     rcx, rax
0x180072a3a  jz      short loc_180072A50
0x180072a3c  mov     rcx, [rcx+10h]
0x180072a40  lea     edx, [r13+22h]
0x180072a44  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180072a4b  call    WPP_SF_
0x180072a50  xor     r8d, r8d; dwFlags
0x180072a53  lea     rcx, [rbp+57h+phProvider]; phProvider
0x180072a57  mov     rdx, r15; pszProviderName
0x180072a5a  call    cs:__imp_NCryptOpenStorageProvider
0x180072a60  mov     ebx, eax
0x180072a62  test    eax, eax
0x180072a64  jz      short loc_180072A9F
0x180072a66  mov     rcx, cs:WPP_GLOBAL_Control
0x180072a6d  lea     rax, WPP_GLOBAL_Control
0x180072a74  cmp     rcx, rax
0x180072a77  jz      loc_180072DB6
0x180072a7d  mov     edx, 23h ; '#'
0x180072a82  mov     rcx, [rcx+10h]
0x180072a86  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180072a8d  mov     r9d, ebx
0x180072a90  mov     qword ptr [rsp+0C0h+dwFlags], r15
0x180072a95  call    WPP_SF_DS
0x180072a9a  jmp     loc_180072DB6
0x180072a9f  or      r9, 0FFFFFFFFFFFFFFFFh
0x180072aa3  inc     r9
0x180072aa6  cmp     [rdi+r9*2], r13w
0x180072aab  jnz     short loc_180072AA3
0x180072aad  mov     rcx, [rbp+57h+phProvider]; hObject
0x180072ab1  lea     r9d, ds:2[r9*2]; cbInput
0x180072ab9  mov     r8, rdi; pbInput
0x180072abc  mov     [rsp+0C0h+dwFlags], r13d; dwFlags
0x180072ac1  lea     rdx, aSmartcardreade; "SmartCardReader"
0x180072ac8  call    cs:__imp_NCryptSetProperty
0x180072ace  mov     ebx, eax
0x180072ad0  test    eax, eax
0x180072ad2  jz      short loc_180072B08
0x180072ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x180072adb  lea     rax, WPP_GLOBAL_Control
0x180072ae2  cmp     rcx, rax
0x180072ae5  jz      loc_180072DB6
0x180072aeb  mov     edx, 24h ; '$'
0x180072af0  mov     r9d, ebx
0x180072af3  mov     rcx, [rcx+10h]
0x180072af7  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180072afe  call    WPP_SF_d
0x180072b03  jmp     loc_180072DB6
0x180072b08  lea     rdx, [rbp+57h+pszKeyName]; unsigned __int16 **
0x180072b0c  mov     rcx, rdi; unsigned __int16 *
0x180072b0f  call    ?GetFormattedCardName@@YAKPEBGPEAPEAG@Z; GetFormattedCardName(ushort const *,ushort * *)
0x180072b14  mov     ebx, eax
0x180072b16  test    eax, eax
0x180072b18  jz      short loc_180072B38
0x180072b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180072b21  lea     rax, WPP_GLOBAL_Control
0x180072b28  cmp     rcx, rax
0x180072b2b  jz      loc_180072DB6
0x180072b31  mov     edx, 25h ; '%'
0x180072b36  jmp     short loc_180072AF0
0x180072b38  mov     r8, [rbp+57h+pszKeyName]; pszKeyName
0x180072b3c  lea     rdx, [rbp+57h+phKey]; phKey
0x180072b40  mov     rcx, [rbp+57h+phProvider]; hProvider
0x180072b44  xor     r9d, r9d; dwLegacyKeySpec
0x180072b47  mov     [rsp+0C0h+dwFlags], 40h ; '@'; unsigned int
0x180072b4f  call    cs:__imp_NCryptOpenKey
0x180072b55  mov     ebx, eax
0x180072b57  test    eax, eax
0x180072b59  jz      short loc_180072B7C
0x180072b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180072b62  lea     rax, WPP_GLOBAL_Control
0x180072b69  cmp     rcx, rax
0x180072b6c  jz      loc_180072DB6
0x180072b72  mov     edx, 26h ; '&'
0x180072b77  jmp     loc_180072A82
0x180072b7c  mov     rcx, [rbp+57h+phKey]; hObject
0x180072b80  lea     r8, [rbp+57h+var_78]; unsigned __int8 **
0x180072b84  xor     r9d, r9d; unsigned int *
0x180072b87  lea     rdx, aName; "Name"
0x180072b8e  call    ?CNGGetProperty@@YAK_KPEBGPEAPEAEPEAKK@Z; CNGGetProperty(unsigned __int64,ushort const *,uchar * *,ulong *,ulong)
0x180072b93  mov     ebx, eax
0x180072b95  test    eax, eax
0x180072b97  jnz     loc_180072DB2
0x180072b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180072ba4  lea     rdi, WPP_GLOBAL_Control
0x180072bab  mov     rsi, [rbp+57h+var_78]
0x180072baf  cmp     rcx, rdi
0x180072bb2  jz      short loc_180072BCA
0x180072bb4  mov     rcx, [rcx+10h]
0x180072bb8  lea     edx, [rax+27h]
0x180072bbb  mov     r9, rsi
0x180072bbe  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180072bc5  call    WPP_SF_S
0x180072bca  mov     rcx, [rbp+57h+phKey]; hObject
0x180072bce  lea     r9, [rbp+57h+cbCertEncoded]; unsigned int *
0x180072bd2  lea     r8, [rbp+57h+pbCertEncoded]; unsigned __int8 **
0x180072bd6  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180072bdd  call    ?CNGGetProperty@@YAK_KPEBGPEAPEAEPEAKK@Z; CNGGetProperty(unsigned __int64,ushort const *,uchar * *,ulong *,ulong)
0x180072be2  mov     r14, [rbp+57h+pbCertEncoded]
0x180072be6  mov     ebx, eax
0x180072be8  test    eax, eax
0x180072bea  jnz     loc_180072DB6
0x180072bf0  mov     r8d, [rbp+57h+cbCertEncoded]; cbCertEncoded
0x180072bf4  mov     rdx, r14; pbCertEncoded
0x180072bf7  mov     ecx, 10001h; dwCertEncodingType
0x180072bfc  call    cs:__imp_CertCreateCertificateContext
0x180072c02  mov     [r12], rax
0x180072c06  test    rax, rax
0x180072c09  jnz     short loc_180072C30
0x180072c0b  call    cs:__imp_GetLastError
0x180072c11  mov     ebx, eax
0x180072c13  mov     rcx, cs:WPP_GLOBAL_Control
0x180072c1a  cmp     rcx, rdi
0x180072c1d  jz      loc_180072DB6
0x180072c23  mov     edx, 28h ; '('
0x180072c28  mov     r9d, eax
0x180072c2b  jmp     loc_180072AF3
0x180072c30  mov     rcx, [rbp+57h+pvInput]; pvInput
0x180072c34  test    rcx, rcx
0x180072c37  jz      short loc_180072C43
0x180072c39  call    cs:__imp_NCryptFreeBuffer
0x180072c3f  mov     [rbp+57h+pvInput], r13
0x180072c43  mov     rcx, [rbp+57h+phProvider]; hProvider
0x180072c47  lea     r9, [rbp+57h+ppEnumState]; ppEnumState
0x180072c4b  lea     r8, [rbp+57h+pvInput]; ppKeyName
0x180072c4f  mov     [rsp+0C0h+dwFlags], 40h ; '@'; dwFlags
0x180072c57  xor     edx, edx; pszScope
0x180072c59  call    cs:__imp_NCryptEnumKeys
0x180072c5f  test    eax, eax
0x180072c61  jnz     loc_180072D66
0x180072c67  mov     r10, cs:WPP_GLOBAL_Control
0x180072c6e  cmp     r10, rdi
0x180072c71  jz      short loc_180072C94
0x180072c73  mov     r9, [rbp+57h+pvInput]
0x180072c77  lea     edx, [rax+2Ah]
0x180072c7a  mov     rcx, [r10+10h]
0x180072c7e  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180072c85  mov     r9, [r9]
0x180072c88  call    WPP_SF_S
0x180072c8d  mov     r10, cs:WPP_GLOBAL_Control
0x180072c94  mov     rcx, [rbp+57h+pvInput]
0x180072c98  cmp     dword ptr [rcx+10h], 2
0x180072c9c  jz      short loc_180072C34
0x180072c9e  cmp     r10, rdi
0x180072ca1  jz      short loc_180072CC3
0x180072ca3  mov     rcx, [r10+10h]
0x180072ca7  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180072cae  mov     edx, 2Bh ; '+'
0x180072cb3  call    WPP_SF_
0x180072cb8  mov     rcx, [rbp+57h+pvInput]
0x180072cbc  mov     r10, cs:WPP_GLOBAL_Control
0x180072cc3  mov     rax, [rcx]
0x180072cc6  mov     r9, rsi
0x180072cc9  sub     r9, rax
0x180072ccc  movzx   r8d, word ptr [rax]
0x180072cd0  movzx   edx, word ptr [rax+r9]
0x180072cd5  sub     r8d, edx
0x180072cd8  jnz     short loc_180072CE2
0x180072cda  add     rax, 2
0x180072cde  test    edx, edx
0x180072ce0  jnz     short loc_180072CCC
0x180072ce2  test    r8d, r8d
0x180072ce5  jnz     loc_180072C34
0x180072ceb  cmp     r10, rdi
0x180072cee  jz      short loc_180072D0E
0x180072cf0  mov     eax, [rcx+14h]
0x180072cf3  mov     r9, [rcx]
0x180072cf6  mov     [rsp+0C0h+var_98], eax
0x180072cfa  mov     eax, [rcx+10h]
0x180072cfd  mov     rcx, [r10+10h]
0x180072d01  mov     [rsp+0C0h+dwFlags], eax
0x180072d05  call    WPP_SF_SDD
0x180072d0a  mov     rcx, [rbp+57h+pvInput]
0x180072d0e  mov     eax, r13d
0x180072d11  mov     qword ptr [rbp+57h+pvData], rsi
0x180072d15  mov     qword ptr [rbp+57h+pvData+8], r15
0x180072d19  lea     r9, [rbp+57h+pvData]; pvData
0x180072d1d  mov     qword ptr [rbp+57h+var_50], r13
0x180072d21  mov     dword ptr [rbp+57h+var_50+8], r13d
0x180072d25  mov     qword ptr [rbp+57h+var_40], r13
0x180072d29  cmp     dword ptr [rcx+10h], 1
0x180072d2d  mov     rcx, [r12]; pCertContext
0x180072d31  setz    al
0x180072d34  xor     r8d, r8d; dwFlags
0x180072d37  mov     dword ptr [rbp+57h+var_40+8], eax
0x180072d3a  lea     edx, [r8+2]; dwPropId
0x180072d3e  call    cs:__imp_CertSetCertificateContextProperty
0x180072d44  test    eax, eax
0x180072d46  jnz     short loc_180072DB6
0x180072d48  call    cs:__imp_GetLastError
0x180072d4e  mov     ebx, eax
0x180072d50  mov     rcx, cs:WPP_GLOBAL_Control
0x180072d57  cmp     rcx, rdi
0x180072d5a  jz      short loc_180072DB6
0x180072d5c  mov     edx, 2Eh ; '.'
0x180072d61  jmp     loc_180072C28
0x180072d66  mov     rcx, cs:WPP_GLOBAL_Control
0x180072d6d  cmp     rcx, rdi
0x180072d70  jz      short loc_180072DAB
0x180072d72  mov     rcx, [rcx+10h]
0x180072d76  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180072d7d  mov     edx, 29h ; ')'
0x180072d82  mov     r9d, eax
0x180072d85  call    WPP_SF_d
0x180072d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180072d91  cmp     rcx, rdi
0x180072d94  jz      short loc_180072DAB
0x180072d96  mov     rcx, [rcx+10h]
0x180072d9a  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180072da1  mov     edx, 2Dh ; '-'
0x180072da6  call    WPP_SF_
0x180072dab  mov     ebx, 8009000Dh
0x180072db0  jmp     short loc_180072DB6
0x180072db2  mov     rsi, [rbp+57h+var_78]
0x180072db6  mov     rcx, r14; hMem
0x180072db9  call    cs:__imp_LocalFree
0x180072dbf  mov     rcx, [rbp+57h+pszKeyName]; hMem
0x180072dc3  call    cs:__imp_LocalFree
0x180072dc9  mov     rcx, rsi; hMem
0x180072dcc  call    cs:__imp_LocalFree
0x180072dd2  mov     rcx, [rbp+57h+phProvider]; hObject
0x180072dd6  test    rcx, rcx
0x180072dd9  jz      short loc_180072DE1
0x180072ddb  call    cs:__imp_NCryptFreeObject
0x180072de1  mov     rcx, [rbp+57h+pvInput]; pvInput
0x180072de5  test    rcx, rcx
0x180072de8  jz      short loc_180072DF0
0x180072dea  call    cs:__imp_NCryptFreeBuffer
0x180072df0  mov     rcx, [rbp+57h+ppEnumState]; pvInput
0x180072df4  test    rcx, rcx
0x180072df7  jz      short loc_180072DFF
0x180072df9  call    cs:__imp_NCryptFreeBuffer
0x180072dff  mov     rcx, [rbp+57h+phKey]; hObject
0x180072e03  test    rcx, rcx
0x180072e06  jz      short loc_180072E0E
0x180072e08  call    cs:__imp_NCryptFreeObject
0x180072e0e  mov     rcx, [r12]; pCertContext
0x180072e12  test    rcx, rcx
0x180072e15  jz      short loc_180072E25
0x180072e17  test    ebx, ebx
0x180072e19  jz      short loc_180072E25
0x180072e1b  call    cs:__imp_CertFreeCertificateContext
0x180072e21  mov     [r12], r13
0x180072e25  mov     eax, ebx
0x180072e27  mov     rbx, [rsp+0C0h+arg_0]
0x180072e2f  add     rsp, 90h
0x180072e36  pop     r15
0x180072e38  pop     r14
0x180072e3a  pop     r13
0x180072e3c  pop     r12
0x180072e3e  pop     rdi
0x180072e3f  pop     rsi
0x180072e40  pop     rbp
0x180072e41  retn
```
