# RecoverFindRecoveryPublic(void *,void *,_CERT_CONTEXT const * *,uchar *,int)

- ea: `0x180037ba8`
- end: `0x180037e90`
- name: `?RecoverFindRecoveryPublic@@YAKPEAX0PEAPEBU_CERT_CONTEXT@@PEAEH@Z`
- size: `744`
- prototype: `__int64 __fastcall(void *, HLOCAL, const struct _CERT_CONTEXT **, unsigned __int8 *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180038234`
- `0x180038874`

## callees

- `0x180003080`
- `0x180007f10`
- `0x18001c9c0`
- `0x180029adc`
- `0x180037ba8`
- `0x1800382f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037c58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037d0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037c58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037d0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037dd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037e14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037e3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037e14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037e3f`
- `CRYPT32!CertFreeCertificateContext` at `0x180037e53`
- `CRYPT32!CertFreeCertificateContext` at `0x180037e53`
- `CRYPT32!CertCloseStore` at `0x180037e69`
- `CRYPT32!CertCloseStore` at `0x180037e69`
- `CRYPT32!CertFindCertificateInStore` at `0x180037d4d`
- `CRYPT32!CertFindCertificateInStore` at `0x180037dbc`
- `CRYPT32!CertFindCertificateInStore` at `0x180037d4d`
- `CRYPT32!CertFindCertificateInStore` at `0x180037dbc`
- `CRYPT32!CertOpenStore` at `0x180037cfa`
- `CRYPT32!CertOpenStore` at `0x180037cfa`

## string_xrefs

- `0x180037de2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
__int64 __fastcall RecoverFindRecoveryPublic(
        void *a1,
        HLOCAL a2,
        const struct _CERT_CONTEXT **a3,
        unsigned __int8 *a4,
        int a5)
{
  BYTE *v5; // rdi
  DWORD v6; // r15d
  HLOCAL v7; // r14
  void *v10; // rax
  unsigned int LastError; // ebx
  void *v12; // r12
  DWORD v13; // eax
  unsigned int v14; // eax
  HCERTSTORE v15; // rax
  PCCERT_CONTEXT pPrevCertContext; // rsi
  __int64 v17; // rcx
  BYTE *v18; // rax
  DWORD v20; // [rsp+30h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-28h] BYREF
  BYTE *v22; // [rsp+40h] [rbp-20h] BYREF
  __int128 pvFindPara; // [rsp+48h] [rbp-18h] BYREF

  v5 = 0;
  v6 = 0;
  v7 = 0;
  v22 = 0;
  hMem = 0;
  v20 = 0;
  v10 = a1;
  pvFindPara = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids);
    v10 = a1;
  }
  if ( !a3 || !v10 && a5 )
    return 87;
  v12 = 0;
  if ( a2 )
    goto LABEL_12;
  if ( (unsigned int)GetTokenUserSid(v10, &hMem) )
  {
    v7 = hMem;
    a2 = hMem;
LABEL_12:
    v14 = RecoveryRetrieveSupplementalCredential((__int64)a2, &v22, &v20);
    v5 = v22;
    LastError = v14;
    if ( v14 )
    {
      v6 = v20;
    }
    else
    {
      v6 = v20;
      if ( v22
        && v20 >= 0x10
        && *(_DWORD *)v22 == 1
        && *((_DWORD *)v22 + 1) <= 0xFFFFu
        && *((_DWORD *)v22 + 2) <= 0xFFFFu
        && *((_DWORD *)v22 + 3) <= 0xFFFFu
        && v20 >= *((unsigned int *)v22 + 1)
                + 16LL
                + *((unsigned int *)v22 + 2)
                + (unsigned __int64)*((unsigned int *)v22 + 3) )
      {
        v15 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x28000u, L"Recovery");
        v12 = v15;
        if ( v15 )
        {
          LODWORD(pvFindPara) = *((_DWORD *)v5 + 1);
          *((_QWORD *)&pvFindPara + 1) = v5 + 16;
          pPrevCertContext = CertFindCertificateInStore(v15, 1u, 0, 0x10000u, &pvFindPara, 0);
          if ( pPrevCertContext )
          {
            if ( a5 )
            {
              while ( 1 )
              {
                LastError = LogonCredVerifySignature(
                              a1,
                              pPrevCertContext->pbCertEncoded,
                              pPrevCertContext->cbCertEncoded,
                              a4,
                              (struct _CRED_SIGNATURE *)&v5[*((unsigned int *)v5 + 1) + 16],
                              *((_DWORD *)v5 + 2));
                if ( !LastError )
                  break;
                pPrevCertContext = CertFindCertificateInStore(v12, 1u, 0, 0x10000u, &pvFindPara, pPrevCertContext);
                if ( !pPrevCertContext )
                  goto LABEL_27;
              }
            }
            else
            {
              LastError = 0;
            }
            *a3 = pPrevCertContext;
          }
          else
          {
LABEL_27:
            LastError = GetLastError();
            DebugTraceError(
              LastError,
              "dwError",
              "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp",
              544);
          }
        }
        else
        {
          LastError = GetLastError();
        }
      }
      else
      {
        LastError = 13;
      }
    }
    goto LABEL_31;
  }
  v13 = GetLastError();
  v7 = hMem;
  LastError = v13;
LABEL_31:
  if ( v7 )
    LocalFree(v7);
  if ( v5 )
  {
    v17 = v6;
    v18 = v5;
    if ( v6 )
    {
      do
      {
        *v18++ = 0;
        --v17;
      }
      while ( v17 );
    }
    LocalFree(v5);
  }
  if ( v12 )
    CertCloseStore(v12, 0);
  return LastError;
}

```

## disassembly

```asm
0x180037ba8  mov     rax, rsp
0x180037bab  mov     [rax+10h], rbx
0x180037baf  mov     [rax+20h], r9
0x180037bb3  mov     [rax+18h], r8
0x180037bb7  mov     [rax+8], rcx
0x180037bbb  push    rbp
0x180037bbc  push    rsi
0x180037bbd  push    rdi
0x180037bbe  push    r12
0x180037bc0  push    r13
0x180037bc2  push    r14
0x180037bc4  push    r15
0x180037bc6  mov     rbp, rsp
0x180037bc9  sub     rsp, 60h
0x180037bcd  xor     edi, edi
0x180037bcf  xor     r15d, r15d
0x180037bd2  xor     r14d, r14d
0x180037bd5  mov     [rbp+var_20], rdi
0x180037bd9  xorps   xmm0, xmm0
0x180037bdc  mov     [rbp+hMem], r14
0x180037be0  mov     rsi, r8
0x180037be3  mov     [rbp+var_30], r15d
0x180037be7  mov     rbx, rdx
0x180037bea  mov     rax, rcx
0x180037bed  movups  [rbp+pvFindPara], xmm0
0x180037bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180037bf8  lea     rdx, WPP_GLOBAL_Control
0x180037bff  cmp     rcx, rdx
0x180037c02  jz      short loc_180037C21
0x180037c04  test    byte ptr [rcx+1Ch], 4
0x180037c08  jz      short loc_180037C21
0x180037c0a  mov     rcx, [rcx+10h]
0x180037c0e  lea     edx, [rdi+0Eh]
0x180037c11  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x180037c18  call    WPP_SF_
0x180037c1d  mov     rax, [rbp+ExistingTokenHandle]
0x180037c21  test    rsi, rsi
0x180037c24  jnz     short loc_180037C30
0x180037c26  mov     ebx, 57h ; 'W'
0x180037c2b  jmp     loc_180037E75
0x180037c30  mov     r13d, [rbp+arg_20]
0x180037c34  test    rax, rax
0x180037c37  jnz     short loc_180037C3E
0x180037c39  test    r13d, r13d
0x180037c3c  jnz     short loc_180037C26
0x180037c3e  xor     esi, esi
0x180037c40  xor     r12d, r12d
0x180037c43  test    rbx, rbx
0x180037c46  jnz     short loc_180037C76
0x180037c48  lea     rdx, [rbp+hMem]
0x180037c4c  mov     rcx, rax
0x180037c4f  call    GetTokenUserSid
0x180037c54  test    eax, eax
0x180037c56  jnz     short loc_180037C6F
0x180037c58  call    cs:__imp_GetLastError
0x180037c5f  nop     dword ptr [rax+rax+00h]
0x180037c64  mov     r14, [rbp+hMem]
0x180037c68  mov     ebx, eax
0x180037c6a  jmp     loc_180037E0C
0x180037c6f  mov     r14, [rbp+hMem]
0x180037c73  mov     rbx, r14
0x180037c76  lea     r8, [rbp+var_30]
0x180037c7a  mov     rcx, rbx
0x180037c7d  lea     rdx, [rbp+var_20]
0x180037c81  call    RecoveryRetrieveSupplementalCredential
0x180037c86  mov     rdi, [rbp+var_20]
0x180037c8a  mov     ebx, eax
0x180037c8c  test    eax, eax
0x180037c8e  jnz     loc_180037E08
0x180037c94  mov     r15d, [rbp+var_30]
0x180037c98  test    rdi, rdi
0x180037c9b  jz      short loc_180037CA8
0x180037c9d  cmp     r15d, 10h
0x180037ca1  jb      short loc_180037CA8
0x180037ca3  cmp     dword ptr [rdi], 1
0x180037ca6  jz      short loc_180037CB2
0x180037ca8  mov     ebx, 0Dh
0x180037cad  jmp     loc_180037E0C
0x180037cb2  mov     eax, 0FFFFh
0x180037cb7  cmp     [rdi+4], eax
0x180037cba  ja      short loc_180037CA8
0x180037cbc  cmp     [rdi+8], eax
0x180037cbf  ja      short loc_180037CA8
0x180037cc1  cmp     [rdi+0Ch], eax
0x180037cc4  ja      short loc_180037CA8
0x180037cc6  mov     eax, [rdi+8]
0x180037cc9  mov     ecx, [rdi+0Ch]
0x180037ccc  add     rcx, rax
0x180037ccf  mov     eax, [rdi+4]
0x180037cd2  add     rax, 10h
0x180037cd6  add     rcx, rax
0x180037cd9  cmp     r15, rcx
0x180037cdc  jb      short loc_180037CA8
0x180037cde  xor     r8d, r8d; hCryptProv
0x180037ce1  lea     rax, aRecovery_0; "Recovery"
0x180037ce8  mov     r9d, 28000h; dwFlags
0x180037cee  mov     [rsp+60h+pvPara], rax; pvPara
0x180037cf3  lea     edx, [r8+1]; dwEncodingType
0x180037cf7  lea     ecx, [rdx+9]; lpszStoreProvider
0x180037cfa  call    cs:__imp_CertOpenStore
0x180037d01  nop     dword ptr [rax+rax+00h]
0x180037d06  mov     r12, rax
0x180037d09  test    rax, rax
0x180037d0c  jnz     short loc_180037D21
0x180037d0e  call    cs:__imp_GetLastError
0x180037d15  nop     dword ptr [rax+rax+00h]
0x180037d1a  mov     ebx, eax
0x180037d1c  jmp     loc_180037E0C
0x180037d21  mov     eax, [rdi+4]
0x180037d24  xor     r8d, r8d; dwFindFlags
0x180037d27  mov     dword ptr [rbp+pvFindPara], eax
0x180037d2a  mov     r9d, 10000h; dwFindType
0x180037d30  lea     rax, [rdi+10h]
0x180037d34  mov     [rsp+60h+pPrevCertContext], rsi; pPrevCertContext
0x180037d39  mov     qword ptr [rbp+pvFindPara+8], rax
0x180037d3d  mov     rcx, r12; hCertStore
0x180037d40  lea     rax, [rbp+pvFindPara]
0x180037d44  lea     edx, [r8+1]; dwCertEncodingType
0x180037d48  mov     [rsp+60h+pvPara], rax; pvFindPara
0x180037d4d  call    cs:__imp_CertFindCertificateInStore
0x180037d54  nop     dword ptr [rax+rax+00h]
0x180037d59  mov     rsi, rax
0x180037d5c  test    rax, rax
0x180037d5f  jz      short loc_180037DD0
0x180037d61  test    r13d, r13d
0x180037d64  jz      loc_180037DFB
0x180037d6a  mov     r13, [rbp+ExistingTokenHandle]
0x180037d6e  mov     ecx, [rdi+8]
0x180037d71  mov     edx, [rdi+4]
0x180037d74  mov     r9, [rbp+arg_18]
0x180037d78  add     rdx, 10h
0x180037d7c  mov     r8d, [rsi+10h]
0x180037d80  add     rdx, rdi
0x180037d83  mov     dword ptr [rsp+60h+pPrevCertContext], ecx; int
0x180037d87  mov     rcx, r13; ExistingTokenHandle
0x180037d8a  mov     [rsp+60h+pvPara], rdx; struct _CRED_SIGNATURE *
0x180037d8f  mov     rdx, [rsi+8]
0x180037d93  call    LogonCredVerifySignature
0x180037d98  mov     ebx, eax
0x180037d9a  test    eax, eax
0x180037d9c  jz      short loc_180037DFD
0x180037d9e  xor     r8d, r8d; dwFindFlags
0x180037da1  mov     [rsp+60h+pPrevCertContext], rsi; pPrevCertContext
0x180037da6  lea     rax, [rbp+pvFindPara]
0x180037daa  mov     r9d, 10000h; dwFindType
0x180037db0  mov     rcx, r12; hCertStore
0x180037db3  mov     [rsp+60h+pvPara], rax; pvFindPara
0x180037db8  lea     edx, [r8+1]; dwCertEncodingType
0x180037dbc  call    cs:__imp_CertFindCertificateInStore
0x180037dc3  nop     dword ptr [rax+rax+00h]
0x180037dc8  mov     rsi, rax
0x180037dcb  test    rax, rax
0x180037dce  jnz     short loc_180037D6E
0x180037dd0  call    cs:__imp_GetLastError
0x180037dd7  nop     dword ptr [rax+rax+00h]
0x180037ddc  mov     r9d, 220h
0x180037de2  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180037de9  mov     ecx, eax
0x180037deb  lea     rdx, aDwerror; "dwError"
0x180037df2  mov     ebx, eax
0x180037df4  call    DebugTraceError
0x180037df9  jmp     short loc_180037E0C
0x180037dfb  xor     ebx, ebx
0x180037dfd  mov     rax, [rbp+arg_10]
0x180037e01  mov     [rax], rsi
0x180037e04  xor     esi, esi
0x180037e06  jmp     short loc_180037E0C
0x180037e08  mov     r15d, [rbp+var_30]
0x180037e0c  test    r14, r14
0x180037e0f  jz      short loc_180037E20
0x180037e11  mov     rcx, r14; hMem
0x180037e14  call    cs:__imp_LocalFree
0x180037e1b  nop     dword ptr [rax+rax+00h]
0x180037e20  test    rdi, rdi
0x180037e23  jz      short loc_180037E4B
0x180037e25  mov     ecx, r15d
0x180037e28  mov     rax, rdi
0x180037e2b  test    r15d, r15d
0x180037e2e  jz      short loc_180037E3C
0x180037e30  mov     byte ptr [rax], 0
0x180037e33  inc     rax
0x180037e36  sub     rcx, 1
0x180037e3a  jnz     short loc_180037E30
0x180037e3c  mov     rcx, rdi; hMem
0x180037e3f  call    cs:__imp_LocalFree
0x180037e46  nop     dword ptr [rax+rax+00h]
0x180037e4b  test    rsi, rsi
0x180037e4e  jz      short loc_180037E5F
0x180037e50  mov     rcx, rsi; pCertContext
0x180037e53  call    cs:__imp_CertFreeCertificateContext
0x180037e5a  nop     dword ptr [rax+rax+00h]
0x180037e5f  test    r12, r12
0x180037e62  jz      short loc_180037E75
0x180037e64  xor     edx, edx; dwFlags
0x180037e66  mov     rcx, r12; hCertStore
0x180037e69  call    cs:__imp_CertCloseStore
0x180037e70  nop     dword ptr [rax+rax+00h]
0x180037e75  mov     eax, ebx
0x180037e77  mov     rbx, [rsp+60h+arg_8]
0x180037e7f  add     rsp, 60h
0x180037e83  pop     r15
0x180037e85  pop     r14
0x180037e87  pop     r13
0x180037e89  pop     r12
0x180037e8b  pop     rdi
0x180037e8c  pop     rsi
0x180037e8d  pop     rbp
0x180037e8e  retn
```
