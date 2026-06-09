# cpCertMatchFilter(_CERT_CONTEXT const *,_CERTFILTERDATA *,bool *)

- ea: `0x1800168e8`
- end: `0x180016da5`
- name: `?cpCertMatchFilter@@YAJPEBU_CERT_CONTEXT@@PEAU_CERTFILTERDATA@@PEA_N@Z`
- size: `1213`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, struct _CERTFILTERDATA *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015b20`

## callees

- `0x18000ba10`
- `0x1800166c8`
- `0x1800168e8`
- `0x180016dac`
- `0x180017030`
- `0x1800170dc`
- `0x180017464`
- `0x180017bfc`
- `0x180020f80`
- `0x180039740`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016d76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016d76`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800169f7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016a10`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800169f7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016a10`
- `CRYPT32!CertGetIntendedKeyUsage` at `0x180016cda`
- `CRYPT32!CertGetIntendedKeyUsage` at `0x180016cda`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180016ca5`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180016ca5`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180016d56`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180016d56`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180016946`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180016946`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18001695f`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180016d6b`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18001695f`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180016d6b`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x1800169c8`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016a79`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016ade`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016b51`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016bb4`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016c2e`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016d3a`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x1800169c8`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016a79`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016ade`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016b51`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016bb4`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016c2e`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016d3a`

## pseudocode

```c
__int64 __fastcall cpCertMatchFilter(PCCERT_CONTEXT pCertContext, struct _CERTFILTERDATA *a2, bool *a3)
{
  int CertIdString; // eax
  unsigned __int16 *v6; // r14
  unsigned int v7; // ebx
  unsigned int v8; // ecx
  unsigned int v9; // r13d
  const char *const *v10; // r8
  unsigned int v11; // edx
  const unsigned __int8 *v12; // r8
  const unsigned __int16 *v13; // rdx
  const struct CERTFILTERSTRING *v14; // r9
  int v15; // r12d
  int v16; // r15d
  PCCERT_CONTEXT v17; // rbx
  struct _CERT_INFO *pCertInfo; // rdx
  int v19; // r8d
  unsigned int v20; // edx
  struct CERTFILTERSTRING *v22; // [rsp+20h] [rbp-59h]
  int v23; // [rsp+40h] [rbp-39h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-31h] BYREF
  PCCERT_CONTEXT pCertContexta; // [rsp+50h] [rbp-29h]
  bool *v26; // [rsp+58h] [rbp-21h]
  unsigned __int16 v27[28]; // [rsp+60h] [rbp-19h] BYREF

  v26 = a3;
  *(_QWORD *)pcbData = 0;
  v23 = 0;
  *a3 = 0;
  pCertContexta = pCertContext;
  CertIdString = myGetCertIdString(pCertContext, (unsigned __int16 **)pcbData);
  v6 = *(unsigned __int16 **)pcbData;
  v7 = CertIdString;
  if ( !CertIdString )
  {
    v9 = 0;
    CSPrintErrorLineFileData(*(const unsigned __int16 **)pcbData, 0x690019Bu, 0);
    v10 = (const char *const *)*((_QWORD *)a2 + 10);
    if ( v10 )
    {
      CertIdString = cpCertMatchEKUOrApplicationPolicies(
                       pCertContext,
                       *((_DWORD *)a2 + 18),
                       v10,
                       *((_DWORD *)a2 + 23),
                       *((struct CERTFILTERSTRING **)a2 + 12),
                       (*(_DWORD *)a2 >> 29) & 1,
                       *((unsigned __int8 *)a2 + 88),
                       &v23);
      v7 = CertIdString;
      if ( CertIdString )
      {
        v8 = 111149467;
        goto LABEL_3;
      }
      if ( !v23 )
      {
        v11 = 111411611;
LABEL_9:
        CSPrintErrorLineFileData2(v6, v11, -2146885628, -2146885628);
LABEL_82:
        v7 = 0;
        goto LABEL_83;
      }
      v9 = 8;
    }
    if ( (*((_BYTE *)a2 + 4) & 0x10) != 0 )
    {
      if ( (*((_DWORD *)a2 + 31) || *((_DWORD *)a2 + 32))
        && CompareFileTime(&pCertContext->pCertInfo->NotAfter, (const FILETIME *)((char *)a2 + 124)) <= 0
        || CompareFileTime(&pCertContext->pCertInfo->NotAfter, (const FILETIME *)((char *)a2 + 132)) >= 0 )
      {
        v11 = 112263579;
        goto LABEL_9;
      }
      v23 = 1;
      v9 |= 0x10u;
    }
    v12 = (const unsigned __int8 *)*((_QWORD *)a2 + 14);
    pcbData[0] = 0;
    if ( v12 )
    {
      CertIdString = myCertHashMatch(pCertContext, *((unsigned int *)a2 + 30), v12, &v23);
      v7 = CertIdString;
      if ( CertIdString )
      {
        v8 = 114164123;
        goto LABEL_3;
      }
      v15 = 1;
      if ( v23 )
      {
LABEL_28:
        v16 = 1;
        if ( (*((_BYTE *)a2 + 4) & 2) == 0 )
          goto LABEL_49;
        goto LABEL_31;
      }
      CSPrintErrorLineFileData2(v6, 0x6D7019Bu, -2146885628, -2146885628);
    }
    else
    {
      v15 = 0;
    }
    v13 = (const unsigned __int16 *)*((_QWORD *)a2 + 13);
    v16 = 0;
    if ( v13 )
    {
      CertIdString = cpSerialNumberMatch(&pCertContexta->pCertInfo->SerialNumber, v13, &v23);
      v7 = CertIdString;
      if ( CertIdString )
      {
        v8 = 115343771;
        goto LABEL_3;
      }
      ++v15;
      if ( v23 )
        goto LABEL_28;
      CSPrintErrorLineFileData2(v6, 0x6E9019Bu, -2146885628, -2146885628);
    }
LABEL_31:
    v14 = (struct _CERTFILTERDATA *)((char *)a2 + 32);
    if ( *((_QWORD *)a2 + 1) || *(_QWORD *)v14 )
    {
      CertIdString = cpNameBlobMatch2(
                       &pCertContexta->pCertInfo->Subject,
                       v13,
                       (struct _CERTFILTERDATA *)((char *)a2 + 8),
                       v14,
                       (int)v22,
                       (int *)pcbData,
                       &v23);
      v7 = CertIdString;
      if ( CertIdString )
      {
        v8 = 116916635;
        goto LABEL_3;
      }
      if ( pcbData[0] )
        v9 |= 2u;
      ++v15;
      if ( v23 )
        ++v16;
      else
        CSPrintErrorLineFileData2(v6, 0x705019Bu, -2146885628, -2146885628);
    }
    if ( !v16 || (*((_BYTE *)a2 + 4) & 2) != 0 )
    {
      CertIdString = cpExtensionMatch(pCertContexta, v6, a2, (int *)pcbData, &v23);
      v7 = CertIdString;
      if ( CertIdString )
      {
        v8 = 118489499;
        goto LABEL_3;
      }
      if ( pcbData[0] )
        v9 |= 2u;
      ++v15;
      if ( v23 )
        ++v16;
      else
        CSPrintErrorLineFileData2(v6, 0x71D019Bu, -2146885628, -2146885628);
    }
LABEL_49:
    if ( *((_QWORD *)a2 + 1) || *((_QWORD *)a2 + 2) || *((_QWORD *)a2 + 3) )
    {
      pcbData[0] = 0;
      CertIdString = cpKeyProvInfoMatch(
                       pCertContexta,
                       (struct _CERTFILTERDATA *)((char *)a2 + 8),
                       (struct _CERTFILTERDATA *)((char *)a2 + 16),
                       (unsigned int)v14,
                       (int *)pcbData,
                       &v23);
      v7 = CertIdString;
      if ( CertIdString )
      {
        v8 = 120390043;
        goto LABEL_3;
      }
      ++v15;
      if ( v23 )
      {
        ++v16;
        if ( pcbData[0] )
          v9 |= 4u;
      }
      else
      {
        CSPrintErrorLineFileData2(v6, 0x73A019Bu, -2146885628, -2146885628);
      }
    }
    if ( !v16 && v15 && *((_BYTE *)a2 + 141) )
    {
      v11 = 121569691;
      goto LABEL_9;
    }
    v17 = pCertContexta;
    if ( (*(_DWORD *)a2 & 0x4000000) != 0 && pCertContexta->pCertInfo->dwVersion )
    {
      v11 = 122290587;
      goto LABEL_9;
    }
    if ( (*(_DWORD *)a2 & 0x8000000) != 0 && pCertContexta->pCertInfo->dwVersion != 2 )
    {
      v11 = 122945947;
      goto LABEL_9;
    }
    if ( *(int *)a2 < 0 )
    {
      pcbData[0] = 0;
      if ( !CertGetCertificateContextProperty(pCertContexta, 2u, 0, pcbData) )
      {
        v11 = 124060059;
        goto LABEL_9;
      }
    }
    if ( (*(_DWORD *)a2 & 0x2000000) != 0 )
    {
      pCertInfo = v17->pCertInfo;
      pcbData[0] = 0;
      if ( !CertGetIntendedKeyUsage(1u, pCertInfo, (BYTE *)pcbData, 4u) )
      {
        v19 = -2146885628;
        v20 = 125305243;
        goto LABEL_81;
      }
      if ( (pcbData[0] & 0x28) == 0 )
      {
        v11 = 125698459;
        goto LABEL_9;
      }
    }
    if ( !*((_BYTE *)a2 + 141) && v9 != *((_DWORD *)a2 + 1) )
    {
      LODWORD(v22) = *((_DWORD *)a2 + 1);
      StringCchPrintfW(v27, 0x1Au, L"%x!=%x", v9, v22);
      CSPrintErrorLineFileData2(v27, 0x78E019Bu, -2146885628, -2146885628);
      v11 = 126812571;
      goto LABEL_9;
    }
    *v26 = 1;
    if ( !DbgIsSSActive(1u) )
      goto LABEL_82;
    v19 = 0;
    v20 = 127140251;
LABEL_81:
    CSPrintErrorLineFileData(v6, v20, v19);
    goto LABEL_82;
  }
  v8 = 109969819;
LABEL_3:
  CSPrintErrorLineFile(v8, CertIdString);
LABEL_83:
  LocalFree(v6);
  return v7;
}

```

## disassembly

```asm
0x1800168e8  mov     [rsp-8+arg_18], rbx
0x1800168ed  push    rbp
0x1800168ee  push    rsi
0x1800168ef  push    rdi
0x1800168f0  push    r12
0x1800168f2  push    r13
0x1800168f4  push    r14
0x1800168f6  push    r15
0x1800168f8  lea     rbp, [rsp-27h]
0x1800168fd  sub     rsp, 0A0h
0x180016904  mov     rax, cs:__security_cookie
0x18001690b  xor     rax, rsp
0x18001690e  mov     [rbp+57h+var_38], rax
0x180016912  xor     edi, edi
0x180016914  mov     [rbp+57h+var_78], r8
0x180016918  mov     rsi, rdx
0x18001691b  mov     qword ptr [rbp+57h+pcbData], rdi
0x18001691f  lea     rdx, [rbp+57h+pcbData]; unsigned __int16 **
0x180016923  mov     [rbp+57h+var_90], edi
0x180016926  mov     [r8], dil
0x180016929  mov     r15, rcx
0x18001692c  mov     [rbp+57h+pCertContext], rcx
0x180016930  call    ?myGetCertIdString@@YAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; myGetCertIdString(_CERT_CONTEXT const *,ushort * *)
0x180016935  mov     r14, qword ptr [rbp+57h+pcbData]
0x180016939  mov     ebx, eax
0x18001693b  test    eax, eax
0x18001693d  jz      short loc_180016951
0x18001693f  mov     ecx, 68E019Bh
0x180016944  mov     edx, eax
0x180016946  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001694c  jmp     loc_180016D73
0x180016951  xor     r8d, r8d
0x180016954  mov     edx, 690019Bh
0x180016959  mov     rcx, r14
0x18001695c  mov     r13d, edi
0x18001695f  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x180016965  mov     r8, [rsi+50h]; char **
0x180016969  test    r8, r8
0x18001696c  jz      short loc_1800169D9
0x18001696e  mov     ecx, [rsi]
0x180016970  lea     rdx, [rbp+57h+var_90]
0x180016974  movzx   eax, byte ptr [rsi+58h]
0x180016978  mov     r9d, [rsi+5Ch]; unsigned int
0x18001697c  mov     [rsp+0D0h+var_98], rdx; int *
0x180016981  mov     edx, [rsi+48h]; unsigned int
0x180016984  mov     dword ptr [rsp+0D0h+var_A0], eax; int
0x180016988  mov     rax, [rsi+60h]
0x18001698c  shr     ecx, 1Dh
0x18001698f  and     ecx, 1
0x180016992  mov     dword ptr [rsp+0D0h+var_A8], ecx; int
0x180016996  mov     rcx, r15; pCertContext
0x180016999  mov     [rsp+0D0h+var_B0], rax; int
0x18001699e  call    ?cpCertMatchEKUOrApplicationPolicies@@YAJPEBU_CERT_CONTEXT@@KPEBQEBDKPEAVCERTFILTERSTRING@@HHPEAH@Z; cpCertMatchEKUOrApplicationPolicies(_CERT_CONTEXT const *,ulong,char const * const *,ulong,CERTFILTERSTRING *,int,int,int *)
0x1800169a3  mov     ebx, eax
0x1800169a5  test    eax, eax
0x1800169a7  jz      short loc_1800169B0
0x1800169a9  mov     ecx, 6A0019Bh
0x1800169ae  jmp     short loc_180016944
0x1800169b0  cmp     [rbp+57h+var_90], edi
0x1800169b3  jnz     short loc_1800169D3
0x1800169b5  mov     edx, 6A4019Bh
0x1800169ba  mov     edi, 80092004h
0x1800169bf  mov     r8d, edi
0x1800169c2  mov     r9d, edi
0x1800169c5  mov     rcx, r14
0x1800169c8  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800169ce  jmp     loc_180016D71
0x1800169d3  mov     r13d, 8
0x1800169d9  test    byte ptr [rsi+4], 10h
0x1800169dd  jz      short loc_180016A25
0x1800169df  lea     rdx, [rsi+7Ch]; lpFileTime2
0x1800169e3  cmp     [rdx], edi
0x1800169e5  jnz     short loc_1800169EF
0x1800169e7  cmp     [rsi+80h], edi
0x1800169ed  jz      short loc_180016A01
0x1800169ef  mov     rcx, [r15+18h]
0x1800169f3  add     rcx, 48h ; 'H'; lpFileTime1
0x1800169f7  call    cs:__imp_CompareFileTime
0x1800169fd  test    eax, eax
0x1800169ff  jle     short loc_180016A55
0x180016a01  mov     rcx, [r15+18h]
0x180016a05  lea     rdx, [rsi+84h]; lpFileTime2
0x180016a0c  add     rcx, 48h ; 'H'; lpFileTime1
0x180016a10  call    cs:__imp_CompareFileTime
0x180016a16  test    eax, eax
0x180016a18  jns     short loc_180016A55
0x180016a1a  mov     [rbp+57h+var_90], 1
0x180016a21  or      r13d, 10h
0x180016a25  mov     r8, [rsi+70h]; Buf2
0x180016a29  mov     [rbp+57h+pcbData], edi
0x180016a2c  mov     edi, 80092004h
0x180016a31  test    r8, r8
0x180016a34  jz      short loc_180016A81
0x180016a36  mov     edx, [rsi+78h]; Size
0x180016a39  lea     r9, [rbp+57h+var_90]; int *
0x180016a3d  mov     rcx, r15; pCertContext
0x180016a40  call    ?myCertHashMatch@@YAJPEBU_CERT_CONTEXT@@KPEBEPEAH@Z; myCertHashMatch(_CERT_CONTEXT const *,ulong,uchar const *,int *)
0x180016a45  mov     ebx, eax
0x180016a47  test    eax, eax
0x180016a49  jz      short loc_180016A5F
0x180016a4b  mov     ecx, 6CE019Bh
0x180016a50  jmp     loc_180016944
0x180016a55  mov     edx, 6B1019Bh
0x180016a5a  jmp     loc_1800169BA
0x180016a5f  cmp     [rbp+57h+var_90], 0
0x180016a63  mov     r12d, 1
0x180016a69  jnz     short loc_180016ABE
0x180016a6b  mov     r9d, edi
0x180016a6e  mov     r8d, edi
0x180016a71  mov     edx, 6D7019Bh
0x180016a76  mov     rcx, r14
0x180016a79  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180016a7f  jmp     short loc_180016A84
0x180016a81  xor     r12d, r12d
0x180016a84  mov     rdx, [rsi+68h]; unsigned __int16 *
0x180016a88  xor     r15d, r15d
0x180016a8b  test    rdx, rdx
0x180016a8e  jz      short loc_180016AE4
0x180016a90  mov     rcx, [rbp+57h+pCertContext]
0x180016a94  lea     r8, [rbp+57h+var_90]; int *
0x180016a98  mov     rcx, [rcx+18h]
0x180016a9c  add     rcx, 8; struct _CRYPTOAPI_BLOB *
0x180016aa0  call    ?cpSerialNumberMatch@@YAJPEBU_CRYPTOAPI_BLOB@@PEBGPEAH@Z; cpSerialNumberMatch(_CRYPTOAPI_BLOB const *,ushort const *,int *)
0x180016aa5  mov     ebx, eax
0x180016aa7  test    eax, eax
0x180016aa9  jz      short loc_180016AB5
0x180016aab  mov     ecx, 6E0019Bh
0x180016ab0  jmp     loc_180016944
0x180016ab5  inc     r12d
0x180016ab8  cmp     [rbp+57h+var_90], r15d
0x180016abc  jz      short loc_180016AD0
0x180016abe  test    byte ptr [rsi+4], 2
0x180016ac2  mov     r15d, 1
0x180016ac8  jz      loc_180016BBA
0x180016ace  jmp     short loc_180016AE4
0x180016ad0  mov     r9d, edi
0x180016ad3  mov     r8d, edi
0x180016ad6  mov     edx, 6E9019Bh
0x180016adb  mov     rcx, r14
0x180016ade  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180016ae4  lea     r8, [rsi+8]; struct CERTFILTERSTRING *
0x180016ae8  cmp     qword ptr [r8], 0
0x180016aec  lea     r9, [rsi+20h]; struct CERTFILTERSTRING *
0x180016af0  jnz     short loc_180016AF8
0x180016af2  cmp     qword ptr [r9], 0
0x180016af6  jz      short loc_180016B57
0x180016af8  mov     rax, [rbp+57h+pCertContext]
0x180016afc  mov     rcx, [rax+18h]
0x180016b00  lea     rax, [rbp+57h+var_90]
0x180016b04  mov     [rsp+0D0h+var_A0], rax; int *
0x180016b09  add     rcx, 50h ; 'P'; struct _CRYPTOAPI_BLOB *
0x180016b0d  lea     rax, [rbp+57h+pcbData]
0x180016b11  mov     [rsp+0D0h+var_A8], rax; int *
0x180016b16  call    ?cpNameBlobMatch2@@YAJPEBU_CRYPTOAPI_BLOB@@PEBGPEBVCERTFILTERSTRING@@2HPEAH3@Z; cpNameBlobMatch2(_CRYPTOAPI_BLOB const *,ushort const *,CERTFILTERSTRING const *,CERTFILTERSTRING const *,int,int *,int *)
0x180016b1b  mov     ebx, eax
0x180016b1d  test    eax, eax
0x180016b1f  jz      short loc_180016B2B
0x180016b21  mov     ecx, 6F8019Bh
0x180016b26  jmp     loc_180016944
0x180016b2b  cmp     [rbp+57h+pcbData], 0
0x180016b2f  jz      short loc_180016B35
0x180016b31  or      r13d, 2
0x180016b35  inc     r12d
0x180016b38  cmp     [rbp+57h+var_90], 0
0x180016b3c  jz      short loc_180016B43
0x180016b3e  inc     r15d
0x180016b41  jmp     short loc_180016B57
0x180016b43  mov     r9d, edi
0x180016b46  mov     r8d, edi
0x180016b49  mov     edx, 705019Bh
0x180016b4e  mov     rcx, r14
0x180016b51  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180016b57  test    r15d, r15d
0x180016b5a  jz      short loc_180016B62
0x180016b5c  test    byte ptr [rsi+4], 2
0x180016b60  jz      short loc_180016BBA
0x180016b62  mov     rcx, [rbp+57h+pCertContext]; pCertContext
0x180016b66  lea     rax, [rbp+57h+var_90]
0x180016b6a  lea     r9, [rbp+57h+pcbData]; int *
0x180016b6e  mov     [rsp+0D0h+var_B0], rax; int *
0x180016b73  mov     r8, rsi; struct _CERTFILTERDATA *
0x180016b76  mov     rdx, r14; unsigned __int16 *
0x180016b79  call    ?cpExtensionMatch@@YAJPEBU_CERT_CONTEXT@@PEBGPEAU_CERTFILTERDATA@@PEAH3@Z; cpExtensionMatch(_CERT_CONTEXT const *,ushort const *,_CERTFILTERDATA *,int *,int *)
0x180016b7e  mov     ebx, eax
0x180016b80  test    eax, eax
0x180016b82  jz      short loc_180016B8E
0x180016b84  mov     ecx, 710019Bh
0x180016b89  jmp     loc_180016944
0x180016b8e  cmp     [rbp+57h+pcbData], 0
0x180016b92  jz      short loc_180016B98
0x180016b94  or      r13d, 2
0x180016b98  inc     r12d
0x180016b9b  cmp     [rbp+57h+var_90], 0
0x180016b9f  jz      short loc_180016BA6
0x180016ba1  inc     r15d
0x180016ba4  jmp     short loc_180016BBA
0x180016ba6  mov     r9d, edi
0x180016ba9  mov     r8d, edi
0x180016bac  mov     edx, 71D019Bh
0x180016bb1  mov     rcx, r14
0x180016bb4  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180016bba  lea     rdx, [rsi+8]; struct CERTFILTERSTRING *
0x180016bbe  cmp     qword ptr [rdx], 0
0x180016bc2  jnz     short loc_180016BD2
0x180016bc4  cmp     qword ptr [rsi+10h], 0
0x180016bc9  jnz     short loc_180016BD2
0x180016bcb  cmp     qword ptr [rsi+18h], 0
0x180016bd0  jz      short loc_180016C34
0x180016bd2  mov     rcx, [rbp+57h+pCertContext]; struct _CERT_CONTEXT *
0x180016bd6  lea     rax, [rbp+57h+var_90]
0x180016bda  mov     [rsp+0D0h+var_A8], rax; int *
0x180016bdf  lea     r8, [rsi+10h]; struct CERTFILTERSTRING *
0x180016be3  lea     rax, [rbp+57h+pcbData]
0x180016be7  mov     [rbp+57h+pcbData], 0
0x180016bee  mov     [rsp+0D0h+var_B0], rax; int *
0x180016bf3  call    ?cpKeyProvInfoMatch@@YAJPEBU_CERT_CONTEXT@@PEBVCERTFILTERSTRING@@1KPEAH2@Z; cpKeyProvInfoMatch(_CERT_CONTEXT const *,CERTFILTERSTRING const *,CERTFILTERSTRING const *,ulong,int *,int *)
0x180016bf8  mov     ebx, eax
0x180016bfa  test    eax, eax
0x180016bfc  jz      short loc_180016C08
0x180016bfe  mov     ecx, 72D019Bh
0x180016c03  jmp     loc_180016944
0x180016c08  inc     r12d
0x180016c0b  cmp     [rbp+57h+var_90], 0
0x180016c0f  jz      short loc_180016C20
0x180016c11  inc     r15d
0x180016c14  cmp     [rbp+57h+pcbData], 0
0x180016c18  jz      short loc_180016C34
0x180016c1a  or      r13d, 4
0x180016c1e  jmp     short loc_180016C34
0x180016c20  mov     r9d, edi
0x180016c23  mov     r8d, edi
0x180016c26  mov     edx, 73A019Bh
0x180016c2b  mov     rcx, r14
0x180016c2e  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180016c34  test    r15d, r15d
0x180016c37  jnz     short loc_180016C51
0x180016c39  test    r12d, r12d
0x180016c3c  jz      short loc_180016C51
0x180016c3e  cmp     [rsi+8Dh], r15b
0x180016c45  jz      short loc_180016C51
0x180016c47  mov     edx, 73F019Bh
0x180016c4c  jmp     loc_1800169BF
0x180016c51  test    dword ptr [rsi], 4000000h
0x180016c57  mov     rbx, [rbp+57h+pCertContext]
0x180016c5b  jz      short loc_180016C70
0x180016c5d  mov     rax, [rbx+18h]
0x180016c61  cmp     dword ptr [rax], 0
0x180016c64  jz      short loc_180016C70
0x180016c66  mov     edx, 74A019Bh
0x180016c6b  jmp     loc_1800169BF
0x180016c70  test    dword ptr [rsi], 8000000h
0x180016c76  jz      short loc_180016C8B
0x180016c78  mov     rax, [rbx+18h]
0x180016c7c  cmp     dword ptr [rax], 2
0x180016c7f  jz      short loc_180016C8B
0x180016c81  mov     edx, 754019Bh
0x180016c86  jmp     loc_1800169BF
0x180016c8b  cmp     dword ptr [rsi], 0
0x180016c8e  jge     short loc_180016CB9
0x180016c90  xor     r8d, r8d; pvData
0x180016c93  mov     [rbp+57h+pcbData], 0
0x180016c9a  lea     r9, [rbp+57h+pcbData]; pcbData
0x180016c9e  mov     rcx, rbx; pCertContext
0x180016ca1  lea     edx, [r8+2]; dwPropId
0x180016ca5  call    cs:__imp_CertGetCertificateContextProperty
0x180016cab  test    eax, eax
0x180016cad  jnz     short loc_180016CB9
0x180016caf  mov     edx, 765019Bh
0x180016cb4  jmp     loc_1800169BF
0x180016cb9  test    dword ptr [rsi], 2000000h
0x180016cbf  jz      short loc_180016CFE
0x180016cc1  mov     rdx, [rbx+18h]; pCertInfo
0x180016cc5  lea     r8, [rbp+57h+pcbData]; pbKeyUsage
0x180016cc9  mov     r9d, 4; cbKeyUsage
0x180016ccf  mov     [rbp+57h+pcbData], 0
0x180016cd6  lea     ecx, [r9-3]; dwCertEncodingType
0x180016cda  call    cs:__imp_CertGetIntendedKeyUsage
0x180016ce0  test    eax, eax
0x180016ce2  jnz     short loc_180016CEE
0x180016ce4  mov     r8d, edi
0x180016ce7  mov     edx, 778019Bh
0x180016cec  jmp     short loc_180016D68
0x180016cee  test    byte ptr [rbp+57h+pcbData], 28h
0x180016cf2  jnz     short loc_180016CFE
0x180016cf4  mov     edx, 77E019Bh
0x180016cf9  jmp     loc_1800169BF
0x180016cfe  cmp     byte ptr [rsi+8Dh], 0
0x180016d05  jnz     short loc_180016D4A
0x180016d07  mov     eax, [rsi+4]
0x180016d0a  cmp     r13d, eax
0x180016d0d  jz      short loc_180016D4A
0x180016d0f  mov     r9d, r13d
0x180016d12  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180016d16  lea     r8, aXX; "%x!=%x"
0x180016d1d  mov     edx, 1Ah; unsigned __int64
0x180016d22  lea     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x180016d26  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016d2b  mov     r9d, edi
0x180016d2e  lea     rcx, [rbp+57h+var_70]
0x180016d32  mov     r8d, edi
  ... truncated ...
```
