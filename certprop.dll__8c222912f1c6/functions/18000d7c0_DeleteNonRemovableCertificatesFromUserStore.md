# DeleteNonRemovableCertificatesFromUserStore

- ea: `0x18000d7c0`
- end: `0x18000da6a`
- name: `DeleteNonRemovableCertificatesFromUserStore`
- size: `682`
- prototype: `__int64 __fastcall(HCERTSTORE hCertStore)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d588`
- `0x18000fe80`

## callees

- `0x180004600`
- `0x18000d7c0`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9bb`
- `CRYPT32!CertCloseStore` at `0x18000da0d`
- `CRYPT32!CertCloseStore` at `0x18000da0d`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000d922`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000d945`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000d922`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000d945`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000d8ae`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000d8ae`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18000d958`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18000d958`
- `CRYPT32!CertFreeCertificateContext` at `0x18000da02`
- `CRYPT32!CertFreeCertificateContext` at `0x18000da02`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18000d92b`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18000d92b`
- `CRYPT32!CertOpenStore` at `0x18000d845`
- `CRYPT32!CertOpenStore` at `0x18000d845`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000d8d0`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000d8d0`

## pseudocode

```c
__int64 __fastcall DeleteNonRemovableCertificatesFromUserStore(HCERTSTORE hCertStore)
{
  HCERTSTORE v2; // rsi
  DWORD LastError; // ebx
  __int64 v4; // rcx
  STRSAFE_LPSTR v5; // rcx
  const CERT_CONTEXT *v6; // rdi
  const CERT_CONTEXT *v7; // rax
  __int64 v8; // rcx
  const CERT_CONTEXT *v9; // rax
  const CERT_CONTEXT *v10; // rax
  char v11; // bl
  __int64 v12; // rcx
  __int64 v13; // rcx
  DWORD pcbData; // [rsp+68h] [rbp+10h] BYREF

  pcbData = 0;
  WppTraceIndent(hCertStore, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids, WPP_pszIndent);
  }
  v2 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x10000u, L"MY");
  if ( v2 )
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = CertEnumCertificatesInStore(v2, v6);
      LastError = 0;
      v6 = v7;
      if ( !v7 )
        break;
      if ( CertGetCertificateContextProperty(v7, 0x6Au, 0, &pcbData) )
      {
        v9 = CertDuplicateCertificateContext(v6);
        if ( !CertDeleteCertificateFromStore(v9) )
        {
          LastError = GetLastError();
          WppTraceIndent(v13, 2);
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
          {
            WPP_SF_sD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              24,
              (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
              WPP_pszIndent,
              LastError);
          }
          CertFreeCertificateContext(v6);
          break;
        }
        if ( hCertStore )
        {
          v10 = CertDuplicateCertificateContext(v6);
          if ( !CertAddCertificateContextToStore(hCertStore, v10, 3u, 0) )
          {
            v11 = GetLastError();
            WppTraceIndent(v12, 2);
            if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[28] & 1) != 0
              && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
            {
              WPP_SF_sD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                25,
                (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
                WPP_pszIndent,
                v11);
            }
          }
        }
      }
      else if ( GetLastError() == 234 )
      {
        WppTraceIndent(v8, 2);
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
            WPP_pszIndent);
        }
      }
    }
    CertCloseStore(v2, 0);
  }
  else
  {
    LastError = GetLastError();
    WppTraceIndent(v4, 2);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
        WPP_pszIndent,
        LastError);
    }
  }
  WppTraceIndent(v5, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000d7c0  mov     [rsp+arg_0], rbx
0x18000d7c5  mov     [rsp+arg_10], rbp
0x18000d7ca  push    rsi
0x18000d7cb  push    rdi
0x18000d7cc  push    r12
0x18000d7ce  push    r14
0x18000d7d0  push    r15
0x18000d7d2  sub     rsp, 30h
0x18000d7d6  xor     edx, edx
0x18000d7d8  mov     [rsp+58h+pcbData], 0
0x18000d7e0  mov     rbp, rcx
0x18000d7e3  call    WppTraceIndent
0x18000d7e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7ef  lea     r15, WPP_GLOBAL_Control
0x18000d7f6  lea     r12, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18000d7fd  mov     r14d, 2
0x18000d803  cmp     rcx, r15
0x18000d806  jz      short loc_18000D82B
0x18000d808  test    [rcx+1Ch], r14b
0x18000d80c  jz      short loc_18000D82B
0x18000d80e  cmp     byte ptr [rcx+19h], 5
0x18000d812  jb      short loc_18000D82B
0x18000d814  mov     r9, cs:WPP_pszIndent
0x18000d81b  lea     edx, [r14+13h]
0x18000d81f  mov     rcx, [rcx+10h]
0x18000d823  mov     r8, r12
0x18000d826  call    WPP_SF_s
0x18000d82b  xor     edx, edx; dwEncodingType
0x18000d82d  lea     rax, aMy; "MY"
0x18000d834  mov     r9d, 10000h; dwFlags
0x18000d83a  mov     [rsp+58h+pvPara], rax; pvPara
0x18000d83f  xor     r8d, r8d; hCryptProv
0x18000d842  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18000d845  call    cs:__imp_CertOpenStore
0x18000d84b  mov     rsi, rax
0x18000d84e  test    rax, rax
0x18000d851  jnz     short loc_18000D8A6
0x18000d853  call    cs:__imp_GetLastError
0x18000d859  mov     edx, r14d
0x18000d85c  mov     ebx, eax
0x18000d85e  call    WppTraceIndent
0x18000d863  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d86a  cmp     rcx, r15
0x18000d86d  jz      loc_18000DA13
0x18000d873  test    byte ptr [rcx+1Ch], 1
0x18000d877  jz      loc_18000DA13
0x18000d87d  cmp     [rcx+19h], r14b
0x18000d881  jb      loc_18000DA13
0x18000d887  mov     r9, cs:WPP_pszIndent
0x18000d88e  lea     edx, [rsi+16h]
0x18000d891  mov     rcx, [rcx+10h]
0x18000d895  mov     r8, r12
0x18000d898  mov     dword ptr [rsp+58h+pvPara], ebx
0x18000d89c  call    WPP_SF_sD
0x18000d8a1  jmp     loc_18000DA13
0x18000d8a6  xor     edi, edi
0x18000d8a8  mov     rdx, rdi; pPrevCertContext
0x18000d8ab  mov     rcx, rsi; hCertStore
0x18000d8ae  call    cs:__imp_CertEnumCertificatesInStore
0x18000d8b4  xor     ebx, ebx
0x18000d8b6  mov     rdi, rax
0x18000d8b9  test    rax, rax
0x18000d8bc  jz      loc_18000DA08
0x18000d8c2  lea     r9, [rsp+58h+pcbData]; pcbData
0x18000d8c7  xor     r8d, r8d; pvData
0x18000d8ca  lea     edx, [rbx+6Ah]; dwPropId
0x18000d8cd  mov     rcx, rax; pCertContext
0x18000d8d0  call    cs:__imp_CertGetCertificateContextProperty
0x18000d8d6  test    eax, eax
0x18000d8d8  jnz     short loc_18000D91F
0x18000d8da  call    cs:__imp_GetLastError
0x18000d8e0  cmp     eax, 0EAh
0x18000d8e5  jnz     short loc_18000D8A8
0x18000d8e7  mov     edx, r14d
0x18000d8ea  call    WppTraceIndent
0x18000d8ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8f6  cmp     rcx, r15
0x18000d8f9  jz      short loc_18000D8A8
0x18000d8fb  test    byte ptr [rcx+1Ch], 1
0x18000d8ff  jz      short loc_18000D8A8
0x18000d901  cmp     byte ptr [rcx+19h], 4
0x18000d905  jb      short loc_18000D8A8
0x18000d907  mov     r9, cs:WPP_pszIndent
0x18000d90e  lea     edx, [rbx+17h]
0x18000d911  mov     rcx, [rcx+10h]
0x18000d915  mov     r8, r12
0x18000d918  call    WPP_SF_s
0x18000d91d  jmp     short loc_18000D8A8
0x18000d91f  mov     rcx, rdi; pCertContext
0x18000d922  call    cs:__imp_CertDuplicateCertificateContext
0x18000d928  mov     rcx, rax; pCertContext
0x18000d92b  call    cs:__imp_CertDeleteCertificateFromStore
0x18000d931  test    eax, eax
0x18000d933  jz      loc_18000D9BB
0x18000d939  test    rbp, rbp
0x18000d93c  jz      loc_18000D8A8
0x18000d942  mov     rcx, rdi; pCertContext
0x18000d945  call    cs:__imp_CertDuplicateCertificateContext
0x18000d94b  xor     r9d, r9d; ppStoreContext
0x18000d94e  mov     rcx, rbp; hCertStore
0x18000d951  mov     rdx, rax; pCertContext
0x18000d954  lea     r8d, [r9+3]; dwAddDisposition
0x18000d958  call    cs:__imp_CertAddCertificateContextToStore
0x18000d95e  test    eax, eax
0x18000d960  jnz     loc_18000D8A8
0x18000d966  call    cs:__imp_GetLastError
0x18000d96c  mov     edx, r14d
0x18000d96f  mov     ebx, eax
0x18000d971  call    WppTraceIndent
0x18000d976  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d97d  cmp     rcx, r15
0x18000d980  jz      loc_18000D8A8
0x18000d986  test    byte ptr [rcx+1Ch], 1
0x18000d98a  jz      loc_18000D8A8
0x18000d990  cmp     byte ptr [rcx+19h], 3
0x18000d994  jb      loc_18000D8A8
0x18000d99a  mov     r9, cs:WPP_pszIndent
0x18000d9a1  mov     edx, 19h
0x18000d9a6  mov     rcx, [rcx+10h]
0x18000d9aa  mov     r8, r12
0x18000d9ad  mov     dword ptr [rsp+58h+pvPara], ebx
0x18000d9b1  call    WPP_SF_sD
0x18000d9b6  jmp     loc_18000D8A8
0x18000d9bb  call    cs:__imp_GetLastError
0x18000d9c1  mov     edx, r14d
0x18000d9c4  mov     ebx, eax
0x18000d9c6  call    WppTraceIndent
0x18000d9cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9d2  cmp     rcx, r15
0x18000d9d5  jz      short loc_18000D9FF
0x18000d9d7  test    byte ptr [rcx+1Ch], 1
0x18000d9db  jz      short loc_18000D9FF
0x18000d9dd  cmp     [rcx+19h], r14b
0x18000d9e1  jb      short loc_18000D9FF
0x18000d9e3  mov     r9, cs:WPP_pszIndent
0x18000d9ea  mov     edx, 18h
0x18000d9ef  mov     rcx, [rcx+10h]
0x18000d9f3  mov     r8, r12
0x18000d9f6  mov     dword ptr [rsp+58h+pvPara], ebx
0x18000d9fa  call    WPP_SF_sD
0x18000d9ff  mov     rcx, rdi; pCertContext
0x18000da02  call    cs:__imp_CertFreeCertificateContext
0x18000da08  xor     edx, edx; dwFlags
0x18000da0a  mov     rcx, rsi; hCertStore
0x18000da0d  call    cs:__imp_CertCloseStore
0x18000da13  mov     edx, 1
0x18000da18  call    WppTraceIndent
0x18000da1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da24  cmp     rcx, r15
0x18000da27  jz      short loc_18000DA51
0x18000da29  test    [rcx+1Ch], r14b
0x18000da2d  jz      short loc_18000DA51
0x18000da2f  cmp     byte ptr [rcx+19h], 5
0x18000da33  jb      short loc_18000DA51
0x18000da35  mov     r9, cs:WPP_pszIndent
0x18000da3c  mov     edx, 1Ah
0x18000da41  mov     rcx, [rcx+10h]
0x18000da45  mov     r8, r12
0x18000da48  mov     dword ptr [rsp+58h+pvPara], ebx
0x18000da4c  call    WPP_SF_sD
0x18000da51  mov     rbp, [rsp+58h+arg_10]
0x18000da56  mov     eax, ebx
0x18000da58  mov     rbx, [rsp+58h+arg_0]
0x18000da5d  add     rsp, 30h
0x18000da61  pop     r15
0x18000da63  pop     r14
0x18000da65  pop     r12
0x18000da67  pop     rdi
0x18000da68  pop     rsi
0x18000da69  retn
```
