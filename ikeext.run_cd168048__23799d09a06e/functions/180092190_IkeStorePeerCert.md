# IkeStorePeerCert

- ea: `0x180092190`
- end: `0x18009234a`
- name: `IkeStorePeerCert`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180091350`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x180050850`
- `0x180090700`
- `0x180092190`
- `0x180092350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800922fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800922fe`
- `CRYPT32!CertCreateCertificateContext` at `0x180092229`
- `CRYPT32!CertCreateCertificateContext` at `0x180092229`
- `CRYPT32!CertFreeCertificateContext` at `0x1800922b4`
- `CRYPT32!CertFreeCertificateContext` at `0x1800922b4`
- `CRYPT32!CertOpenStore` at `0x180092262`
- `CRYPT32!CertOpenStore` at `0x1800922f0`
- `CRYPT32!CertOpenStore` at `0x180092262`
- `CRYPT32!CertOpenStore` at `0x1800922f0`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18009228c`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18009228c`

## string_xrefs

- `0x18009223d`: `CertCreateCertificateContext`
- `0x180092276`: `CertOpenStore`
- `0x180092304`: `CertOpenStore`

## pseudocode

```c
__int64 __fastcall IkeStorePeerCert(__int64 a1, unsigned __int8 a2, __int64 a3)
{
  int v3; // r14d
  __int64 v5; // rbx
  __int64 v7; // rdx
  HCERTSTORE *CertInfo; // rsi
  __int64 v9; // rcx
  __int64 v10; // r8
  const char *v11; // rdx
  __int64 v12; // rax
  const CERT_CONTEXT *CertificateContext; // rdi
  DWORD LastError; // eax
  HCERTSTORE v15; // rax
  DWORD v16; // eax
  __int64 v17; // rcx
  const char *v18; // rdx
  HCERTSTORE v19; // rax
  __int128 pvPara; // [rsp+30h] [rbp-58h] BYREF

  v3 = a2;
  v5 = 0;
  pvPara = 0;
  TraceLogHelper("IkeStorePeerCert", 1);
  CertInfo = (HCERTSTORE *)IkeGetCertInfo(a1);
  v9 = (unsigned int)(v3 - 1);
  if ( v3 != 1 )
  {
    if ( v3 != 4 )
    {
      v9 = (unsigned int)(v3 - 12);
      if ( (unsigned int)v9 < 2 )
      {
        LOBYTE(v7) = v3;
        v12 = IkeStorePeerUrlEncodedCerts(a1, v7, a3);
LABEL_20:
        v5 = v12;
        goto LABEL_21;
      }
      goto LABEL_4;
    }
    CertificateContext = CertCreateCertificateContext(1u, *(const BYTE **)(a3 + 8), *(_DWORD *)a3);
    if ( !CertificateContext )
    {
      LastError = GetLastError();
      v11 = "CertCreateCertificateContext";
LABEL_18:
      v10 = LastError;
      goto LABEL_19;
    }
    v15 = *CertInfo;
    if ( *CertInfo || (v15 = CertOpenStore((LPCSTR)2, 1u, 0, 1u, 0), (*CertInfo = v15) != 0) )
    {
      if ( CertAddCertificateContextToStore(v15, CertificateContext, 3u, 0) )
      {
LABEL_14:
        CertFreeCertificateContext(CertificateContext);
        goto LABEL_21;
      }
      v16 = GetLastError();
      v18 = "CertAddCertificateContextToStore";
    }
    else
    {
      v16 = GetLastError();
      v18 = "CertOpenStore";
    }
    v5 = WfpReportSysErrorAsWinError(v17, v18, v16, 1);
    goto LABEL_14;
  }
  *((_QWORD *)&pvPara + 1) = *(_QWORD *)(a3 + 8);
  LODWORD(pvPara) = *(_DWORD *)a3;
  if ( *CertInfo )
  {
LABEL_4:
    v10 = 13835;
    v11 = "IkeStorePeerCert";
LABEL_19:
    v12 = WfpReportSysErrorAsWinError(v9, v11, v10, 1);
    goto LABEL_20;
  }
  v19 = CertOpenStore((LPCSTR)5, 0x10001u, 0, 0x8001u, &pvPara);
  *CertInfo = v19;
  if ( !v19 )
  {
    LastError = GetLastError();
    v11 = "CertOpenStore";
    goto LABEL_18;
  }
LABEL_21:
  TraceLogHelper("IkeStorePeerCert", 0);
  return IkeReturnError(v5, "IkeStorePeerCert");
}

```

## disassembly

```asm
0x180092190  push    rbx
0x180092192  push    rbp
0x180092193  push    rsi
0x180092194  push    rdi
0x180092195  push    r12
0x180092197  push    r14
0x180092199  push    r15
0x18009219b  sub     rsp, 50h
0x18009219f  mov     rax, cs:__security_cookie
0x1800921a6  xor     rax, rsp
0x1800921a9  mov     [rsp+88h+var_48], rax
0x1800921ae  movzx   r14d, dl
0x1800921b2  lea     r12, aIkestorepeerce; "IkeStorePeerCert"
0x1800921b9  mov     rbp, rcx
0x1800921bc  xorps   xmm0, xmm0
0x1800921bf  xor     ebx, ebx
0x1800921c1  mov     rcx, r12
0x1800921c4  mov     rdi, r8
0x1800921c7  movups  [rsp+88h+var_58], xmm0
0x1800921cc  lea     r15d, [rbx+1]
0x1800921d0  mov     edx, r15d
0x1800921d3  call    TraceLogHelper
0x1800921d8  mov     rcx, rbp
0x1800921db  call    IkeGetCertInfo
0x1800921e0  mov     ecx, r14d
0x1800921e3  mov     rsi, rax
0x1800921e6  sub     ecx, r15d
0x1800921e9  jz      loc_1800922BC
0x1800921ef  sub     ecx, 3
0x1800921f2  jz      short loc_18009221F
0x1800921f4  sub     ecx, 8
0x1800921f7  jz      short loc_18009220C
0x1800921f9  cmp     ecx, r15d
0x1800921fc  jz      short loc_18009220C
0x1800921fe  mov     r8d, 360Bh
0x180092204  mov     rdx, r12
0x180092207  jmp     loc_18009230E
0x18009220c  mov     r8, rdi
0x18009220f  mov     dl, r14b
0x180092212  mov     rcx, rbp
0x180092215  call    IkeStorePeerUrlEncodedCerts
0x18009221a  jmp     loc_180092316
0x18009221f  mov     r8d, [rdi]; cbCertEncoded
0x180092222  mov     ecx, r15d; dwCertEncodingType
0x180092225  mov     rdx, [rdi+8]; pbCertEncoded
0x180092229  call    cs:__imp_CertCreateCertificateContext
0x18009222f  mov     rdi, rax
0x180092232  test    rax, rax
0x180092235  jnz     short loc_180092249
0x180092237  call    cs:__imp_GetLastError
0x18009223d  lea     rdx, aCertcreatecert_0; "CertCreateCertificateContext"
0x180092244  jmp     loc_18009230B
0x180092249  mov     rax, [rsi]
0x18009224c  test    rax, rax
0x18009224f  jnz     short loc_18009227F
0x180092251  mov     r9d, r15d; dwFlags
0x180092254  mov     [rsp+88h+pvPara], rbx; pvPara
0x180092259  xor     r8d, r8d; hCryptProv
0x18009225c  lea     ecx, [rax+2]; lpszStoreProvider
0x18009225f  mov     edx, r15d; dwEncodingType
0x180092262  call    cs:__imp_CertOpenStore
0x180092268  mov     [rsi], rax
0x18009226b  test    rax, rax
0x18009226e  jnz     short loc_18009227F
0x180092270  call    cs:__imp_GetLastError
0x180092276  lea     rdx, aCertopenstore_0; "CertOpenStore"
0x18009227d  jmp     short loc_1800922A3
0x18009227f  xor     r9d, r9d; ppStoreContext
0x180092282  mov     rdx, rdi; pCertContext
0x180092285  mov     rcx, rax; hCertStore
0x180092288  lea     r8d, [r9+3]; dwAddDisposition
0x18009228c  call    cs:__imp_CertAddCertificateContextToStore
0x180092292  test    eax, eax
0x180092294  jnz     short loc_1800922B1
0x180092296  call    cs:__imp_GetLastError
0x18009229c  lea     rdx, aCertaddcertifi_0; "CertAddCertificateContextToStore"
0x1800922a3  mov     r9d, r15d
0x1800922a6  mov     r8d, eax
0x1800922a9  call    WfpReportSysErrorAsWinError
0x1800922ae  mov     rbx, rax
0x1800922b1  mov     rcx, rdi; pCertContext
0x1800922b4  call    cs:__imp_CertFreeCertificateContext
0x1800922ba  jmp     short loc_180092319
0x1800922bc  mov     rax, [rdi+8]
0x1800922c0  mov     qword ptr [rsp+88h+var_58+8], rax
0x1800922c5  mov     eax, [rdi]
0x1800922c7  mov     dword ptr [rsp+88h+var_58], eax
0x1800922cb  cmp     [rsi], rbx
0x1800922ce  jnz     loc_1800921FE
0x1800922d4  xor     r8d, r8d; hCryptProv
0x1800922d7  lea     rax, [rsp+88h+var_58]
0x1800922dc  mov     r9d, 8001h; dwFlags
0x1800922e2  mov     [rsp+88h+pvPara], rax; pvPara
0x1800922e7  mov     edx, 10001h; dwEncodingType
0x1800922ec  lea     ecx, [r8+5]; lpszStoreProvider
0x1800922f0  call    cs:__imp_CertOpenStore
0x1800922f6  mov     [rsi], rax
0x1800922f9  test    rax, rax
0x1800922fc  jnz     short loc_180092319
0x1800922fe  call    cs:__imp_GetLastError
0x180092304  lea     rdx, aCertopenstore_0; "CertOpenStore"
0x18009230b  mov     r8d, eax
0x18009230e  mov     r9d, r15d
0x180092311  call    WfpReportSysErrorAsWinError
0x180092316  mov     rbx, rax
0x180092319  xor     edx, edx
0x18009231b  mov     rcx, r12
0x18009231e  call    TraceLogHelper
0x180092323  mov     rdx, r12
0x180092326  mov     rcx, rbx
0x180092329  call    IkeReturnError
0x18009232e  mov     rcx, [rsp+88h+var_48]
0x180092333  xor     rcx, rsp; StackCookie
0x180092336  call    __security_check_cookie
0x18009233b  add     rsp, 50h
0x18009233f  pop     r15
0x180092341  pop     r14
0x180092343  pop     r12
0x180092345  pop     rdi
0x180092346  pop     rsi
0x180092347  pop     rbp
0x180092348  pop     rbx
0x180092349  retn
```
