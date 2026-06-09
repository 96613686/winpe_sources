# cpCertMatchFilter(_CERT_CONTEXT const *,_CERTFILTERDATA *,bool *)

- ea: `0x18001f61c`
- end: `0x18001fafb`
- name: `?cpCertMatchFilter@@YAJPEBU_CERT_CONTEXT@@PEAU_CERTFILTERDATA@@PEA_N@Z`
- size: `1247`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, struct _CERTFILTERDATA *, bool *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020be4`

## callees

- `0x180008400`
- `0x180008610`
- `0x180008900`
- `0x18000a320`
- `0x18001e4f8`
- `0x18001f3f8`
- `0x18001f61c`
- `0x18001fb04`
- `0x18001fd84`
- `0x18001fe30`
- `0x1800201bc`
- `0x180020958`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001facc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001facc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001f723`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001f73c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001f723`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001f73c`
- `CRYPT32!CertGetIntendedKeyUsage` at `0x18001fa24`
- `CRYPT32!CertGetIntendedKeyUsage` at `0x18001fa24`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001f9e9`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001f9e9`

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
  int v12; // r9d
  int v13; // r8d
  const unsigned __int8 *v14; // r8
  const unsigned __int16 *v15; // rdx
  const struct CERTFILTERSTRING *v16; // r9
  int v17; // r12d
  int v18; // r15d
  PCCERT_CONTEXT v19; // rbx
  struct _CERT_INFO *pCertInfo; // rdx
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
    CSPrintErrorLineFileData2(*(const unsigned __int16 **)pcbData, 0x690019Bu, 0, 0);
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
        v12 = -2146885628;
        v13 = -2146885628;
        goto LABEL_80;
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
        v12 = -2146885628;
        v13 = -2146885628;
        goto LABEL_80;
      }
      v23 = 1;
      v9 |= 0x10u;
    }
    v14 = (const unsigned __int8 *)*((_QWORD *)a2 + 14);
    pcbData[0] = 0;
    if ( v14 )
    {
      CertIdString = myCertHashMatch(pCertContext, *((unsigned int *)a2 + 30), v14, &v23);
      v7 = CertIdString;
      if ( CertIdString )
      {
        v8 = 114164123;
        goto LABEL_3;
      }
      v17 = 1;
      if ( v23 )
      {
LABEL_27:
        v18 = 1;
        if ( (*((_BYTE *)a2 + 4) & 2) == 0 )
          goto LABEL_48;
        goto LABEL_30;
      }
      CSPrintErrorLineFileData2(v6, 0x6D7019Bu, -2146885628, -2146885628);
    }
    else
    {
      v17 = 0;
    }
    v15 = (const unsigned __int16 *)*((_QWORD *)a2 + 13);
    v18 = 0;
    if ( v15 )
    {
      CertIdString = cpSerialNumberMatch(&pCertContexta->pCertInfo->SerialNumber, v15, &v23);
      v7 = CertIdString;
      if ( CertIdString )
      {
        v8 = 115343771;
        goto LABEL_3;
      }
      ++v17;
      if ( v23 )
        goto LABEL_27;
      CSPrintErrorLineFileData2(v6, 0x6E9019Bu, -2146885628, -2146885628);
    }
LABEL_30:
    v16 = (struct _CERTFILTERDATA *)((char *)a2 + 32);
    if ( *((_QWORD *)a2 + 1) || *(_QWORD *)v16 )
    {
      CertIdString = cpNameBlobMatch2(
                       &pCertContexta->pCertInfo->Subject,
                       v15,
                       (struct _CERTFILTERDATA *)((char *)a2 + 8),
                       v16,
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
      ++v17;
      if ( v23 )
        ++v18;
      else
        CSPrintErrorLineFileData2(v6, 0x705019Bu, -2146885628, -2146885628);
    }
    if ( !v18 || (*((_BYTE *)a2 + 4) & 2) != 0 )
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
      ++v17;
      if ( v23 )
        ++v18;
      else
        CSPrintErrorLineFileData2(v6, 0x71D019Bu, -2146885628, -2146885628);
    }
LABEL_48:
    if ( *((_QWORD *)a2 + 1) || *((_QWORD *)a2 + 2) || *((_QWORD *)a2 + 3) )
    {
      pcbData[0] = 0;
      CertIdString = cpKeyProvInfoMatch(
                       pCertContexta,
                       (struct _CERTFILTERDATA *)((char *)a2 + 8),
                       (struct _CERTFILTERDATA *)((char *)a2 + 16),
                       (unsigned int)v16,
                       (int *)pcbData,
                       &v23);
      v7 = CertIdString;
      if ( CertIdString )
      {
        v8 = 120390043;
        goto LABEL_3;
      }
      ++v17;
      if ( v23 )
      {
        ++v18;
        if ( pcbData[0] )
          v9 |= 4u;
      }
      else
      {
        CSPrintErrorLineFileData2(v6, 0x73A019Bu, -2146885628, -2146885628);
      }
    }
    if ( !v18 && v17 && *((_BYTE *)a2 + 141) )
    {
      v12 = -2146885628;
      v13 = -2146885628;
      v11 = 121569691;
    }
    else
    {
      v19 = pCertContexta;
      if ( (*(_DWORD *)a2 & 0x4000000) != 0 && pCertContexta->pCertInfo->dwVersion )
      {
        v12 = -2146885628;
        v13 = -2146885628;
        v11 = 122290587;
      }
      else if ( (*(_DWORD *)a2 & 0x8000000) == 0 || pCertContexta->pCertInfo->dwVersion == 2 )
      {
        if ( *(int *)a2 >= 0 || (pcbData[0] = 0, CertGetCertificateContextProperty(pCertContexta, 2u, 0, pcbData)) )
        {
          if ( (*(_DWORD *)a2 & 0x2000000) != 0 )
          {
            pCertInfo = v19->pCertInfo;
            pcbData[0] = 0;
            if ( !CertGetIntendedKeyUsage(1u, pCertInfo, (BYTE *)pcbData, 4u) )
            {
              v12 = 0;
              v13 = -2146885628;
              v11 = 125305243;
              goto LABEL_80;
            }
            if ( (pcbData[0] & 0x28) == 0 )
            {
              v12 = -2146885628;
              v13 = -2146885628;
              v11 = 125698459;
              goto LABEL_80;
            }
          }
          if ( *((_BYTE *)a2 + 141) || v9 == *((_DWORD *)a2 + 1) )
          {
            *v26 = 1;
            if ( !(unsigned int)DbgIsSSActive(1u) )
            {
LABEL_81:
              v7 = 0;
              goto LABEL_82;
            }
            v12 = 0;
            v11 = 127140251;
            v13 = 0;
          }
          else
          {
            LODWORD(v22) = *((_DWORD *)a2 + 1);
            StringCchPrintfW(v27, 0x1Au, L"%x!=%x", v9, v22);
            CSPrintErrorLineFileData2(v27, 0x78E019Bu, -2146885628, -2146885628);
            v12 = -2146885628;
            v13 = -2146885628;
            v11 = 126812571;
          }
        }
        else
        {
          v12 = -2146885628;
          v13 = -2146885628;
          v11 = 124060059;
        }
      }
      else
      {
        v12 = -2146885628;
        v13 = -2146885628;
        v11 = 122945947;
      }
    }
LABEL_80:
    CSPrintErrorLineFileData2(v6, v11, v13, v12);
    goto LABEL_81;
  }
  v8 = 109969819;
LABEL_3:
  CSPrintErrorLineFile(v8, CertIdString);
LABEL_82:
  LocalFree(v6);
  return v7;
}

```

## disassembly

```asm
0x18001f61c  mov     [rsp-8+arg_18], rbx
0x18001f621  push    rbp
0x18001f622  push    rsi
0x18001f623  push    rdi
0x18001f624  push    r12
0x18001f626  push    r13
0x18001f628  push    r14
0x18001f62a  push    r15
0x18001f62c  lea     rbp, [rsp-27h]
0x18001f631  sub     rsp, 0A0h
0x18001f638  mov     rax, cs:__security_cookie
0x18001f63f  xor     rax, rsp
0x18001f642  mov     [rbp+57h+var_38], rax
0x18001f646  xor     edi, edi
0x18001f648  mov     [rbp+57h+var_78], r8
0x18001f64c  mov     rsi, rdx
0x18001f64f  mov     qword ptr [rbp+57h+pcbData], rdi
0x18001f653  lea     rdx, [rbp+57h+pcbData]; unsigned __int16 **
0x18001f657  mov     [rbp+57h+var_90], edi
0x18001f65a  mov     [r8], dil
0x18001f65d  mov     r15, rcx
0x18001f660  mov     [rbp+57h+pCertContext], rcx
0x18001f664  call    ?myGetCertIdString@@YAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; myGetCertIdString(_CERT_CONTEXT const *,ushort * *)
0x18001f669  mov     r14, qword ptr [rbp+57h+pcbData]
0x18001f66d  mov     ebx, eax
0x18001f66f  test    eax, eax
0x18001f671  jz      short loc_18001F684
0x18001f673  mov     ecx, 68E019Bh; unsigned int
0x18001f678  mov     edx, eax; int
0x18001f67a  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001f67f  jmp     loc_18001FAC9
0x18001f684  xor     r9d, r9d; int
0x18001f687  xor     r8d, r8d; int
0x18001f68a  mov     edx, 690019Bh; unsigned int
0x18001f68f  mov     rcx, r14; unsigned __int16 *
0x18001f692  mov     r13d, edi
0x18001f695  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18001f69a  mov     r8, [rsi+50h]; char **
0x18001f69e  test    r8, r8
0x18001f6a1  jz      short loc_18001F705
0x18001f6a3  mov     ecx, [rsi]
0x18001f6a5  lea     rdx, [rbp+57h+var_90]
0x18001f6a9  movzx   eax, byte ptr [rsi+58h]
0x18001f6ad  mov     r9d, [rsi+5Ch]; unsigned int
0x18001f6b1  mov     [rsp+0D0h+var_98], rdx; int *
0x18001f6b6  mov     edx, [rsi+48h]; unsigned int
0x18001f6b9  mov     dword ptr [rsp+0D0h+var_A0], eax; int
0x18001f6bd  mov     rax, [rsi+60h]
0x18001f6c1  shr     ecx, 1Dh
0x18001f6c4  and     ecx, 1
0x18001f6c7  mov     dword ptr [rsp+0D0h+var_A8], ecx; int
0x18001f6cb  mov     rcx, r15; pCertContext
0x18001f6ce  mov     [rsp+0D0h+var_B0], rax; int
0x18001f6d3  call    ?cpCertMatchEKUOrApplicationPolicies@@YAJPEBU_CERT_CONTEXT@@KPEBQEBDKPEAVCERTFILTERSTRING@@HHPEAH@Z; cpCertMatchEKUOrApplicationPolicies(_CERT_CONTEXT const *,ulong,char const * const *,ulong,CERTFILTERSTRING *,int,int,int *)
0x18001f6d8  mov     ebx, eax
0x18001f6da  test    eax, eax
0x18001f6dc  jz      short loc_18001F6E5
0x18001f6de  mov     ecx, 6A0019Bh
0x18001f6e3  jmp     short loc_18001F678
0x18001f6e5  cmp     [rbp+57h+var_90], edi
0x18001f6e8  jnz     short loc_18001F6FF
0x18001f6ea  mov     edi, 80092004h
0x18001f6ef  mov     edx, 6A4019Bh
0x18001f6f4  mov     r9d, edi
0x18001f6f7  mov     r8d, edi
0x18001f6fa  jmp     loc_18001FABF
0x18001f6ff  mov     r13d, 8
0x18001f705  test    byte ptr [rsi+4], 10h
0x18001f709  jz      short loc_18001F751
0x18001f70b  lea     rdx, [rsi+7Ch]; lpFileTime2
0x18001f70f  cmp     [rdx], edi
0x18001f711  jnz     short loc_18001F71B
0x18001f713  cmp     [rsi+80h], edi
0x18001f719  jz      short loc_18001F72D
0x18001f71b  mov     rcx, [r15+18h]
0x18001f71f  add     rcx, 48h ; 'H'; lpFileTime1
0x18001f723  call    cs:__imp_CompareFileTime
0x18001f729  test    eax, eax
0x18001f72b  jle     short loc_18001F781
0x18001f72d  mov     rcx, [r15+18h]
0x18001f731  lea     rdx, [rsi+84h]; lpFileTime2
0x18001f738  add     rcx, 48h ; 'H'; lpFileTime1
0x18001f73c  call    cs:__imp_CompareFileTime
0x18001f742  test    eax, eax
0x18001f744  jns     short loc_18001F781
0x18001f746  mov     [rbp+57h+var_90], 1
0x18001f74d  or      r13d, 10h
0x18001f751  mov     r8, [rsi+70h]; Buf2
0x18001f755  mov     [rbp+57h+pcbData], edi
0x18001f758  mov     edi, 80092004h
0x18001f75d  test    r8, r8
0x18001f760  jz      short loc_18001F7B7
0x18001f762  mov     edx, [rsi+78h]; Size
0x18001f765  lea     r9, [rbp+57h+var_90]; int *
0x18001f769  mov     rcx, r15; pCertContext
0x18001f76c  call    ?myCertHashMatch@@YAJPEBU_CERT_CONTEXT@@KPEBEPEAH@Z; myCertHashMatch(_CERT_CONTEXT const *,ulong,uchar const *,int *)
0x18001f771  mov     ebx, eax
0x18001f773  test    eax, eax
0x18001f775  jz      short loc_18001F796
0x18001f777  mov     ecx, 6CE019Bh
0x18001f77c  jmp     loc_18001F678
0x18001f781  mov     edi, 80092004h
0x18001f786  mov     edx, 6B1019Bh
0x18001f78b  mov     r9d, edi
0x18001f78e  mov     r8d, edi
0x18001f791  jmp     loc_18001FABF
0x18001f796  cmp     [rbp+57h+var_90], 0
0x18001f79a  mov     r12d, 1
0x18001f7a0  jnz     short loc_18001F7F4
0x18001f7a2  mov     r9d, edi; int
0x18001f7a5  mov     r8d, edi; int
0x18001f7a8  mov     edx, 6D7019Bh; unsigned int
0x18001f7ad  mov     rcx, r14; unsigned __int16 *
0x18001f7b0  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18001f7b5  jmp     short loc_18001F7BA
0x18001f7b7  xor     r12d, r12d
0x18001f7ba  mov     rdx, [rsi+68h]; unsigned __int16 *
0x18001f7be  xor     r15d, r15d
0x18001f7c1  test    rdx, rdx
0x18001f7c4  jz      short loc_18001F819
0x18001f7c6  mov     rcx, [rbp+57h+pCertContext]
0x18001f7ca  lea     r8, [rbp+57h+var_90]; int *
0x18001f7ce  mov     rcx, [rcx+18h]
0x18001f7d2  add     rcx, 8; struct _CRYPTOAPI_BLOB *
0x18001f7d6  call    ?cpSerialNumberMatch@@YAJPEBU_CRYPTOAPI_BLOB@@PEBGPEAH@Z; cpSerialNumberMatch(_CRYPTOAPI_BLOB const *,ushort const *,int *)
0x18001f7db  mov     ebx, eax
0x18001f7dd  test    eax, eax
0x18001f7df  jz      short loc_18001F7EB
0x18001f7e1  mov     ecx, 6E0019Bh
0x18001f7e6  jmp     loc_18001F678
0x18001f7eb  inc     r12d
0x18001f7ee  cmp     [rbp+57h+var_90], r15d
0x18001f7f2  jz      short loc_18001F806
0x18001f7f4  test    byte ptr [rsi+4], 2
0x18001f7f8  mov     r15d, 1
0x18001f7fe  jz      loc_18001F8ED
0x18001f804  jmp     short loc_18001F819
0x18001f806  mov     r9d, edi; int
0x18001f809  mov     r8d, edi; int
0x18001f80c  mov     edx, 6E9019Bh; unsigned int
0x18001f811  mov     rcx, r14; unsigned __int16 *
0x18001f814  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18001f819  lea     r8, [rsi+8]; struct CERTFILTERSTRING *
0x18001f81d  cmp     qword ptr [r8], 0
0x18001f821  lea     r9, [rsi+20h]; struct CERTFILTERSTRING *
0x18001f825  jnz     short loc_18001F82D
0x18001f827  cmp     qword ptr [r9], 0
0x18001f82b  jz      short loc_18001F88B
0x18001f82d  mov     rax, [rbp+57h+pCertContext]
0x18001f831  mov     rcx, [rax+18h]
0x18001f835  lea     rax, [rbp+57h+var_90]
0x18001f839  mov     [rsp+0D0h+var_A0], rax; int *
0x18001f83e  add     rcx, 50h ; 'P'; struct _CRYPTOAPI_BLOB *
0x18001f842  lea     rax, [rbp+57h+pcbData]
0x18001f846  mov     [rsp+0D0h+var_A8], rax; int *
0x18001f84b  call    ?cpNameBlobMatch2@@YAJPEBU_CRYPTOAPI_BLOB@@PEBGPEBVCERTFILTERSTRING@@2HPEAH3@Z; cpNameBlobMatch2(_CRYPTOAPI_BLOB const *,ushort const *,CERTFILTERSTRING const *,CERTFILTERSTRING const *,int,int *,int *)
0x18001f850  mov     ebx, eax
0x18001f852  test    eax, eax
0x18001f854  jz      short loc_18001F860
0x18001f856  mov     ecx, 6F8019Bh
0x18001f85b  jmp     loc_18001F678
0x18001f860  cmp     [rbp+57h+pcbData], 0
0x18001f864  jz      short loc_18001F86A
0x18001f866  or      r13d, 2
0x18001f86a  inc     r12d
0x18001f86d  cmp     [rbp+57h+var_90], 0
0x18001f871  jz      short loc_18001F878
0x18001f873  inc     r15d
0x18001f876  jmp     short loc_18001F88B
0x18001f878  mov     r9d, edi; int
0x18001f87b  mov     r8d, edi; int
0x18001f87e  mov     edx, 705019Bh; unsigned int
0x18001f883  mov     rcx, r14; unsigned __int16 *
0x18001f886  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18001f88b  test    r15d, r15d
0x18001f88e  jz      short loc_18001F896
0x18001f890  test    byte ptr [rsi+4], 2
0x18001f894  jz      short loc_18001F8ED
0x18001f896  mov     rcx, [rbp+57h+pCertContext]; pCertContext
0x18001f89a  lea     rax, [rbp+57h+var_90]
0x18001f89e  lea     r9, [rbp+57h+pcbData]; int *
0x18001f8a2  mov     [rsp+0D0h+var_B0], rax; int *
0x18001f8a7  mov     r8, rsi; struct _CERTFILTERDATA *
0x18001f8aa  mov     rdx, r14; unsigned __int16 *
0x18001f8ad  call    ?cpExtensionMatch@@YAJPEBU_CERT_CONTEXT@@PEBGPEAU_CERTFILTERDATA@@PEAH3@Z; cpExtensionMatch(_CERT_CONTEXT const *,ushort const *,_CERTFILTERDATA *,int *,int *)
0x18001f8b2  mov     ebx, eax
0x18001f8b4  test    eax, eax
0x18001f8b6  jz      short loc_18001F8C2
0x18001f8b8  mov     ecx, 710019Bh
0x18001f8bd  jmp     loc_18001F678
0x18001f8c2  cmp     [rbp+57h+pcbData], 0
0x18001f8c6  jz      short loc_18001F8CC
0x18001f8c8  or      r13d, 2
0x18001f8cc  inc     r12d
0x18001f8cf  cmp     [rbp+57h+var_90], 0
0x18001f8d3  jz      short loc_18001F8DA
0x18001f8d5  inc     r15d
0x18001f8d8  jmp     short loc_18001F8ED
0x18001f8da  mov     r9d, edi; int
0x18001f8dd  mov     r8d, edi; int
0x18001f8e0  mov     edx, 71D019Bh; unsigned int
0x18001f8e5  mov     rcx, r14; unsigned __int16 *
0x18001f8e8  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18001f8ed  lea     rdx, [rsi+8]; struct CERTFILTERSTRING *
0x18001f8f1  cmp     qword ptr [rdx], 0
0x18001f8f5  jnz     short loc_18001F905
0x18001f8f7  cmp     qword ptr [rsi+10h], 0
0x18001f8fc  jnz     short loc_18001F905
0x18001f8fe  cmp     qword ptr [rsi+18h], 0
0x18001f903  jz      short loc_18001F966
0x18001f905  mov     rcx, [rbp+57h+pCertContext]; struct _CERT_CONTEXT *
0x18001f909  lea     rax, [rbp+57h+var_90]
0x18001f90d  mov     [rsp+0D0h+var_A8], rax; int *
0x18001f912  lea     r8, [rsi+10h]; struct CERTFILTERSTRING *
0x18001f916  lea     rax, [rbp+57h+pcbData]
0x18001f91a  mov     [rbp+57h+pcbData], 0
0x18001f921  mov     [rsp+0D0h+var_B0], rax; int *
0x18001f926  call    ?cpKeyProvInfoMatch@@YAJPEBU_CERT_CONTEXT@@PEBVCERTFILTERSTRING@@1KPEAH2@Z; cpKeyProvInfoMatch(_CERT_CONTEXT const *,CERTFILTERSTRING const *,CERTFILTERSTRING const *,ulong,int *,int *)
0x18001f92b  mov     ebx, eax
0x18001f92d  test    eax, eax
0x18001f92f  jz      short loc_18001F93B
0x18001f931  mov     ecx, 72D019Bh
0x18001f936  jmp     loc_18001F678
0x18001f93b  inc     r12d
0x18001f93e  cmp     [rbp+57h+var_90], 0
0x18001f942  jz      short loc_18001F953
0x18001f944  inc     r15d
0x18001f947  cmp     [rbp+57h+pcbData], 0
0x18001f94b  jz      short loc_18001F966
0x18001f94d  or      r13d, 4
0x18001f951  jmp     short loc_18001F966
0x18001f953  mov     r9d, edi; int
0x18001f956  mov     r8d, edi; int
0x18001f959  mov     edx, 73A019Bh; unsigned int
0x18001f95e  mov     rcx, r14; unsigned __int16 *
0x18001f961  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18001f966  test    r15d, r15d
0x18001f969  jnz     short loc_18001F989
0x18001f96b  test    r12d, r12d
0x18001f96e  jz      short loc_18001F989
0x18001f970  cmp     [rsi+8Dh], r15b
0x18001f977  jz      short loc_18001F989
0x18001f979  mov     r9d, edi
0x18001f97c  mov     r8d, edi
0x18001f97f  mov     edx, 73F019Bh
0x18001f984  jmp     loc_18001FABF
0x18001f989  test    dword ptr [rsi], 4000000h
0x18001f98f  mov     rbx, [rbp+57h+pCertContext]
0x18001f993  jz      short loc_18001F9AE
0x18001f995  mov     rax, [rbx+18h]
0x18001f999  cmp     dword ptr [rax], 0
0x18001f99c  jz      short loc_18001F9AE
0x18001f99e  mov     r9d, edi
0x18001f9a1  mov     r8d, edi
0x18001f9a4  mov     edx, 74A019Bh
0x18001f9a9  jmp     loc_18001FABF
0x18001f9ae  test    dword ptr [rsi], 8000000h
0x18001f9b4  jz      short loc_18001F9CF
0x18001f9b6  mov     rax, [rbx+18h]
0x18001f9ba  cmp     dword ptr [rax], 2
0x18001f9bd  jz      short loc_18001F9CF
0x18001f9bf  mov     r9d, edi
0x18001f9c2  mov     r8d, edi
0x18001f9c5  mov     edx, 754019Bh
0x18001f9ca  jmp     loc_18001FABF
0x18001f9cf  cmp     dword ptr [rsi], 0
0x18001f9d2  jge     short loc_18001FA03
0x18001f9d4  xor     r8d, r8d; pvData
0x18001f9d7  mov     [rbp+57h+pcbData], 0
0x18001f9de  lea     r9, [rbp+57h+pcbData]; pcbData
0x18001f9e2  mov     rcx, rbx; pCertContext
0x18001f9e5  lea     edx, [r8+2]; dwPropId
0x18001f9e9  call    cs:__imp_CertGetCertificateContextProperty
0x18001f9ef  test    eax, eax
0x18001f9f1  jnz     short loc_18001FA03
0x18001f9f3  mov     r9d, edi
0x18001f9f6  mov     r8d, edi
0x18001f9f9  mov     edx, 765019Bh
0x18001f9fe  jmp     loc_18001FABF
0x18001fa03  test    dword ptr [rsi], 2000000h
0x18001fa09  jz      short loc_18001FA51
0x18001fa0b  mov     rdx, [rbx+18h]; pCertInfo
0x18001fa0f  lea     r8, [rbp+57h+pcbData]; pbKeyUsage
0x18001fa13  mov     r9d, 4; cbKeyUsage
0x18001fa19  mov     [rbp+57h+pcbData], 0
0x18001fa20  lea     ecx, [r9-3]; dwCertEncodingType
0x18001fa24  call    cs:__imp_CertGetIntendedKeyUsage
0x18001fa2a  test    eax, eax
0x18001fa2c  jnz     short loc_18001FA3E
0x18001fa2e  xor     r9d, r9d
0x18001fa31  mov     r8d, edi
0x18001fa34  mov     edx, 778019Bh
0x18001fa39  jmp     loc_18001FABF
0x18001fa3e  test    byte ptr [rbp+57h+pcbData], 28h
0x18001fa42  jnz     short loc_18001FA51
0x18001fa44  mov     r9d, edi
0x18001fa47  mov     r8d, edi
0x18001fa4a  mov     edx, 77E019Bh
0x18001fa4f  jmp     short loc_18001FABF
0x18001fa51  cmp     byte ptr [rsi+8Dh], 0
  ... truncated ...
```
