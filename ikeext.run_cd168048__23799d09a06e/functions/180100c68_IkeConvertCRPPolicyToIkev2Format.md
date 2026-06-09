# IkeConvertCRPPolicyToIkev2Format

- ea: `0x180100c68`
- end: `0x180100ff9`
- name: `IkeConvertCRPPolicyToIkev2Format`
- size: `913`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18010130c`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bc40`
- `0x180100c68`
- `0x180101294`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180100d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180100f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180100d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180100f5a`
- `CRYPT32!CertFreeCertificateContext` at `0x180100f2e`
- `CRYPT32!CertFreeCertificateContext` at `0x180100f96`
- `CRYPT32!CertFreeCertificateContext` at `0x180100f2e`
- `CRYPT32!CertFreeCertificateContext` at `0x180100f96`
- `CRYPT32!CertOpenStore` at `0x180100d01`
- `CRYPT32!CertOpenStore` at `0x180100d38`
- `CRYPT32!CertOpenStore` at `0x180100d01`
- `CRYPT32!CertOpenStore` at `0x180100d38`
- `CRYPT32!CertCloseStore` at `0x180100fa6`
- `CRYPT32!CertCloseStore` at `0x180100fb6`
- `CRYPT32!CertCloseStore` at `0x180100fa6`
- `CRYPT32!CertCloseStore` at `0x180100fb6`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x180100f07`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x180100f07`
- `CRYPT32!CertFindCertificateInStore` at `0x180100d9d`
- `CRYPT32!CertFindCertificateInStore` at `0x180100dda`
- `CRYPT32!CertFindCertificateInStore` at `0x180100d9d`
- `CRYPT32!CertFindCertificateInStore` at `0x180100dda`

## string_xrefs

- `0x180100d15`: `CertOpenStore`

## pseudocode

```c
__int64 __fastcall IkeConvertCRPPolicyToIkev2Format(__int64 a1, unsigned int a2, _QWORD *a3, unsigned int *a4)
{
  __int64 v4; // rdi
  PCCERT_CONTEXT CertificateInStore; // rbx
  HCERTSTORE v6; // r13
  __int64 v7; // rsi
  HCERTSTORE v8; // r14
  DWORD LastError; // eax
  __int64 v10; // rcx
  const char *v11; // rdx
  unsigned int v12; // r15d
  unsigned int v13; // r12d
  __int64 v14; // rcx
  __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  int TlsMmLuid; // eax
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // r8d
  int v30; // r9d
  __int64 pcbComputedHash; // r15
  int v34; // [rsp+48h] [rbp-81h]
  __int128 pvFindPara; // [rsp+68h] [rbp-61h] BYREF
  __int64 v39; // [rsp+78h] [rbp-51h] BYREF
  _BYTE v40[32]; // [rsp+80h] [rbp-49h] BYREF
  __int64 *v41; // [rsp+A0h] [rbp-29h]
  __int64 v42; // [rsp+A8h] [rbp-21h]
  _BYTE v43[16]; // [rsp+B0h] [rbp-19h] BYREF
  const char *v44; // [rsp+C0h] [rbp-9h]
  __int64 v45; // [rsp+C8h] [rbp-1h]

  v4 = a2;
  CertificateInStore = 0;
  v6 = 0;
  pvFindPara = 0;
  TraceLogHelper("IkeConvertCRPPolicyToIkev2Format", 1);
  v7 = WfpMemAlloc(56 * v4, 8u);
  if ( v7 )
  {
    v8 = 0;
    goto LABEL_26;
  }
  v8 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, L"Root");
  if ( !v8 )
  {
    LastError = GetLastError();
    v11 = "CertOpenStore";
    goto LABEL_23;
  }
  v12 = 0;
  v13 = 0;
  v34 = 0;
  v6 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, L"CA");
  if ( !(_DWORD)v4 )
  {
LABEL_21:
    *a3 = 0;
    *a4 = v12;
    goto LABEL_30;
  }
  v14 = a1;
  while ( 1 )
  {
    v15 = 56LL * v13;
    if ( (*(_BYTE *)(v15 + v14 + 48) & 2) == 0 )
      break;
LABEL_20:
    if ( ++v13 >= a2 )
      goto LABEL_21;
  }
  *((_QWORD *)&pvFindPara + 1) = *(_QWORD *)(v15 + v14 + 8);
  LODWORD(pvFindPara) = *(_DWORD *)(v15 + v14);
  CertificateInStore = CertFindCertificateInStore(v8, 0x10001u, 0, 0x20007u, &pvFindPara, 0);
  if ( !CertificateInStore
    && ((*(_BYTE *)(v15 + a1 + 48) & 8) == 0
     || (CertificateInStore = CertFindCertificateInStore(v6, 0x10001u, 0, 0x20007u, &pvFindPara, 0)) == 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v20 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v17);
      TlsMmLuid = IkeGetTlsMmLuid(v23, v22, v24, v25);
      WPP_SF_iS(v20, 11, (unsigned int)WPP_8bd80daa5f233ec3c23f5c1a14d180b4_Traceguids, TlsMmLuid, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v39 = IkeGetTlsMmLuid(v17, v16, v18, v19);
      v41 = &v39;
      v42 = 8;
      v28 = IkeGetTlsPeerAddr(v27);
      tlgCreate1Sz_wchar_t(v43, v28);
      v45 = 67;
      v44 = "CertFindCertificateInStore didn't find any matching cert, ignoring";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&word_180164E76,
        v29,
        v30,
        5,
        (__int64)v40);
    }
    goto LABEL_19;
  }
  pcbComputedHash = 56LL * v12;
  v7 = WfpMemAlloc(0x14u, 8u);
  if ( v7 )
    goto LABEL_26;
  *(_DWORD *)pcbComputedHash = 20;
  if ( CryptHashPublicKeyInfo(
         0,
         0x8004u,
         0,
         0x10001u,
         &CertificateInStore->pCertInfo->SubjectPublicKeyInfo,
         *(BYTE **)(pcbComputedHash + 8),
         (DWORD *)pcbComputedHash) )
  {
    *(_DWORD *)(pcbComputedHash + 48) = *(_DWORD *)(v15 + a1 + 48);
    v12 = ++v34;
    CertFreeCertificateContext(CertificateInStore);
LABEL_19:
    v14 = a1;
    goto LABEL_20;
  }
  LastError = GetLastError();
  v11 = "CryptHashPublicKeyInfo";
LABEL_23:
  v7 = WfpReportSysErrorAsWinError(v10, v11, LastError, 1);
  if ( v7 )
LABEL_26:
    IkeFreeCRPRootList(0, a2);
  if ( CertificateInStore )
    CertFreeCertificateContext(CertificateInStore);
  if ( v8 )
LABEL_30:
    CertCloseStore(v8, 0);
  if ( v6 )
    CertCloseStore(v6, 0);
  TraceLogHelper("IkeConvertCRPPolicyToIkev2Format", 0);
  return IkeReturnError(v7, "IkeConvertCRPPolicyToIkev2Format");
}

```

## disassembly

```asm
0x180100c68  push    rbp
0x180100c6a  push    rbx
0x180100c6b  push    rsi
0x180100c6c  push    rdi
0x180100c6d  push    r12
0x180100c6f  push    r13
0x180100c71  push    r14
0x180100c73  push    r15
0x180100c75  lea     rbp, [rsp-1Fh]
0x180100c7a  sub     rsp, 0E8h
0x180100c81  mov     rax, cs:__security_cookie
0x180100c88  xor     rax, rsp
0x180100c8b  mov     [rbp+57h+var_50], rax
0x180100c8f  mov     edi, edx
0x180100c91  xorps   xmm0, xmm0
0x180100c94  mov     [rsp+120h+var_E0], rcx
0x180100c99  xor     ebx, ebx
0x180100c9b  lea     rcx, aIkeconvertcrpp; "IkeConvertCRPPolicyToIkev2Format"
0x180100ca2  mov     [rbp+57h+var_C0], r9
0x180100ca6  mov     [rbp+57h+var_C8], r8
0x180100caa  xor     r13d, r13d
0x180100cad  mov     [rbp+57h+var_D4], edi
0x180100cb0  lea     edx, [rbx+1]
0x180100cb3  mov     [rbp+57h+var_D0], 0
0x180100cbb  movups  [rbp+57h+pvFindPara], xmm0
0x180100cbf  call    TraceLogHelper
0x180100cc4  imul    rcx, rdi, 38h ; '8'; dwBytes
0x180100cc8  lea     r8, [rbp+57h+var_D0]
0x180100ccc  lea     edx, [rbx+8]; dwFlags
0x180100ccf  call    WfpMemAlloc
0x180100cd4  mov     rsi, rax
0x180100cd7  test    rax, rax
0x180100cda  jnz     loc_180100F7F
0x180100ce0  lea     rax, aRoot; "Root"
0x180100ce7  mov     r15d, 20000h
0x180100ced  lea     r12d, [rbx+0Ah]
0x180100cf1  mov     [rsp+120h+pvPara], rax; pvPara
0x180100cf6  mov     r9d, r15d; dwFlags
0x180100cf9  mov     ecx, r12d; lpszStoreProvider
0x180100cfc  xor     r8d, r8d; hCryptProv
0x180100cff  xor     edx, edx; dwEncodingType
0x180100d01  call    cs:__imp_CertOpenStore
0x180100d07  mov     r14, rax
0x180100d0a  test    rax, rax
0x180100d0d  jnz     short loc_180100D21
0x180100d0f  call    cs:__imp_GetLastError
0x180100d15  lea     rdx, aCertopenstore_0; "CertOpenStore"
0x180100d1c  jmp     loc_180100F67
0x180100d21  lea     rax, aCa; "CA"
0x180100d28  mov     r9d, r15d; dwFlags
0x180100d2b  xor     r8d, r8d; hCryptProv
0x180100d2e  mov     [rsp+120h+pvPara], rax; pvPara
0x180100d33  xor     edx, edx; dwEncodingType
0x180100d35  mov     rcx, r12; lpszStoreProvider
0x180100d38  call    cs:__imp_CertOpenStore
0x180100d3e  xor     r15d, r15d
0x180100d41  xor     r12d, r12d
0x180100d44  mov     [rsp+120h+var_D8], r15d
0x180100d49  mov     r13, rax
0x180100d4c  test    edi, edi
0x180100d4e  jz      loc_180100F46
0x180100d54  mov     rcx, [rsp+120h+var_E0]
0x180100d59  mov     eax, r12d
0x180100d5c  imul    rdi, rax, 38h ; '8'
0x180100d60  test    byte ptr [rdi+rcx+30h], 2
0x180100d65  jnz     loc_180100F39
0x180100d6b  mov     rax, [rdi+rcx+8]
0x180100d70  mov     r9d, 20007h; dwFindType
0x180100d76  mov     qword ptr [rbp+57h+pvFindPara+8], rax
0x180100d7a  xor     r8d, r8d; dwFindFlags
0x180100d7d  mov     eax, [rdi+rcx]
0x180100d80  mov     edx, 10001h; dwCertEncodingType
0x180100d85  mov     dword ptr [rbp+57h+pvFindPara], eax
0x180100d88  mov     rcx, r14; hCertStore
0x180100d8b  lea     rax, [rbp+57h+pvFindPara]
0x180100d8f  mov     [rsp+120h+pPrevCertContext], 0; pPrevCertContext
0x180100d98  mov     [rsp+120h+pvPara], rax; pvFindPara
0x180100d9d  call    cs:__imp_CertFindCertificateInStore
0x180100da3  mov     rbx, rax
0x180100da6  test    rax, rax
0x180100da9  jnz     loc_180100EAD
0x180100daf  mov     rax, [rsp+120h+var_E0]
0x180100db4  test    byte ptr [rdi+rax+30h], 8
0x180100db9  jz      short loc_180100DEC
0x180100dbb  lea     rax, [rbp+57h+pvFindPara]
0x180100dbf  mov     [rsp+120h+pPrevCertContext], rbx; pPrevCertContext
0x180100dc4  mov     r9d, 20007h; dwFindType
0x180100dca  mov     [rsp+120h+pvPara], rax; pvFindPara
0x180100dcf  xor     r8d, r8d; dwFindFlags
0x180100dd2  mov     edx, 10001h; dwCertEncodingType
0x180100dd7  mov     rcx, r13; hCertStore
0x180100dda  call    cs:__imp_CertFindCertificateInStore
0x180100de0  mov     rbx, rax
0x180100de3  test    rax, rax
0x180100de6  jnz     loc_180100EAD
0x180100dec  mov     rdi, cs:WPP_GLOBAL_Control
0x180100df3  lea     rax, WPP_GLOBAL_Control
0x180100dfa  cmp     rdi, rax
0x180100dfd  jz      short loc_180100E38
0x180100dff  cmp     byte ptr [rdi+19h], 4
0x180100e03  jb      short loc_180100E38
0x180100e05  test    byte ptr [rdi+1Ch], 10h
0x180100e09  jz      short loc_180100E38
0x180100e0b  mov     rdi, [rdi+10h]
0x180100e0f  call    IkeGetTlsPeerAddr
0x180100e14  mov     rbx, rax
0x180100e17  call    IkeGetTlsMmLuid
0x180100e1c  mov     r9, rax
0x180100e1f  mov     [rsp+120h+pvPara], rbx
0x180100e24  mov     edx, 0Bh
0x180100e29  lea     r8, WPP_8bd80daa5f233ec3c23f5c1a14d180b4_Traceguids
0x180100e30  mov     rcx, rdi
0x180100e33  call    WPP_SF_iS
0x180100e38  mov     eax, cs:dword_180173278
0x180100e3e  cmp     eax, 4
0x180100e41  jbe     loc_180100F34
0x180100e47  call    IkeGetTlsMmLuid
0x180100e4c  mov     [rbp+57h+var_A8], rax
0x180100e50  lea     rax, [rbp+57h+var_A8]
0x180100e54  mov     [rbp+57h+var_80], rax
0x180100e58  mov     [rbp+57h+var_78], 8
0x180100e60  call    IkeGetTlsPeerAddr
0x180100e65  mov     rdx, rax
0x180100e68  lea     rcx, [rbp+57h+var_70]
0x180100e6c  call    _tlgCreate1Sz_wchar_t
0x180100e71  lea     rcx, aCertfindcertif_0; "CertFindCertificateInStore didn't find "...
0x180100e78  mov     [rbp+57h+var_58], 43h ; 'C'
0x180100e80  lea     rax, [rbp+57h+var_A0]
0x180100e84  mov     [rbp+57h+var_60], rcx
0x180100e88  mov     [rsp+120h+pPrevCertContext], rax
0x180100e8d  lea     rcx, dword_180173278
0x180100e94  lea     rdx, word_180164E76
0x180100e9b  mov     dword ptr [rsp+120h+pvPara], 5
0x180100ea3  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180100ea8  jmp     loc_180100F34
0x180100ead  mov     eax, r15d
0x180100eb0  mov     edx, 8; dwFlags
0x180100eb5  imul    r15, rax, 38h ; '8'
0x180100eb9  lea     ecx, [rdx+0Ch]; dwBytes
0x180100ebc  add     r15, [rbp+57h+var_D0]
0x180100ec0  lea     r8, [r15+8]
0x180100ec4  call    WfpMemAlloc
0x180100ec9  mov     rsi, rax
0x180100ecc  test    rax, rax
0x180100ecf  jnz     loc_180100F82
0x180100ed5  mov     dword ptr [r15], 14h
0x180100edc  mov     r9d, 10001h; dwCertEncodingType
0x180100ee2  mov     rcx, [rbx+18h]
0x180100ee6  xor     r8d, r8d; dwFlags
0x180100ee9  mov     rax, [r15+8]
0x180100eed  add     rcx, 60h ; '`'
0x180100ef1  mov     [rsp+120h+pcbComputedHash], r15; pcbComputedHash
0x180100ef6  mov     edx, 8004h; Algid
0x180100efb  mov     [rsp+120h+pPrevCertContext], rax; pbComputedHash
0x180100f00  mov     [rsp+120h+pvPara], rcx; pInfo
0x180100f05  xor     ecx, ecx; hCryptProv
0x180100f07  call    cs:__imp_CryptHashPublicKeyInfo
0x180100f0d  test    eax, eax
0x180100f0f  jz      short loc_180100F5A
0x180100f11  mov     rax, [rsp+120h+var_E0]
0x180100f16  mov     rcx, rbx; pCertContext
0x180100f19  mov     eax, [rdi+rax+30h]
0x180100f1d  mov     [r15+30h], eax
0x180100f21  mov     r15d, [rsp+120h+var_D8]
0x180100f26  inc     r15d
0x180100f29  mov     [rsp+120h+var_D8], r15d
0x180100f2e  call    cs:__imp_CertFreeCertificateContext
0x180100f34  mov     rcx, [rsp+120h+var_E0]
0x180100f39  inc     r12d
0x180100f3c  cmp     r12d, [rbp+57h+var_D4]
0x180100f40  jb      loc_180100D59
0x180100f46  mov     rax, [rbp+57h+var_D0]
0x180100f4a  mov     rcx, [rbp+57h+var_C8]
0x180100f4e  mov     [rcx], rax
0x180100f51  mov     rax, [rbp+57h+var_C0]
0x180100f55  mov     [rax], r15d
0x180100f58  jmp     short loc_180100FA1
0x180100f5a  call    cs:__imp_GetLastError
0x180100f60  lea     rdx, aCrypthashpubli_0; "CryptHashPublicKeyInfo"
0x180100f67  mov     r9d, 1
0x180100f6d  mov     r8d, eax
0x180100f70  call    WfpReportSysErrorAsWinError
0x180100f75  mov     rsi, rax
0x180100f78  test    rax, rax
0x180100f7b  jz      short loc_180100F8E
0x180100f7d  jmp     short loc_180100F82
0x180100f7f  xor     r14d, r14d
0x180100f82  mov     edx, [rbp+57h+var_D4]
0x180100f85  mov     rcx, [rbp+57h+var_D0]
0x180100f89  call    IkeFreeCRPRootList
0x180100f8e  test    rbx, rbx
0x180100f91  jz      short loc_180100F9C
0x180100f93  mov     rcx, rbx; pCertContext
0x180100f96  call    cs:__imp_CertFreeCertificateContext
0x180100f9c  test    r14, r14
0x180100f9f  jz      short loc_180100FAC
0x180100fa1  xor     edx, edx; dwFlags
0x180100fa3  mov     rcx, r14; hCertStore
0x180100fa6  call    cs:__imp_CertCloseStore
0x180100fac  test    r13, r13
0x180100faf  jz      short loc_180100FBC
0x180100fb1  xor     edx, edx; dwFlags
0x180100fb3  mov     rcx, r13; hCertStore
0x180100fb6  call    cs:__imp_CertCloseStore
0x180100fbc  xor     edx, edx
0x180100fbe  lea     rcx, aIkeconvertcrpp; "IkeConvertCRPPolicyToIkev2Format"
0x180100fc5  call    TraceLogHelper
0x180100fca  lea     rdx, aIkeconvertcrpp; "IkeConvertCRPPolicyToIkev2Format"
0x180100fd1  mov     rcx, rsi
0x180100fd4  call    IkeReturnError
0x180100fd9  mov     rcx, [rbp+57h+var_50]
0x180100fdd  xor     rcx, rsp; StackCookie
0x180100fe0  call    __security_check_cookie
0x180100fe5  add     rsp, 0E8h
0x180100fec  pop     r15
0x180100fee  pop     r14
0x180100ff0  pop     r13
0x180100ff2  pop     r12
0x180100ff4  pop     rdi
0x180100ff5  pop     rsi
0x180100ff6  pop     rbx
0x180100ff7  pop     rbp
0x180100ff8  retn
```
