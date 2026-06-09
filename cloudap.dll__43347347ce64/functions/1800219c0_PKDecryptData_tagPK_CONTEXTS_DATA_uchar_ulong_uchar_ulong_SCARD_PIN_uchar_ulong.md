# PKDecryptData(_tagPK_CONTEXTS_DATA *,uchar *,ulong,uchar *,ulong,_SCARD_PIN *,uchar * *,ulong *)

- ea: `0x1800219c0`
- end: `0x180022235`
- name: `?PKDecryptData@@YAJPEAU_tagPK_CONTEXTS_DATA@@PEAEK1KPEAU_SCARD_PIN@@PEAPEAEPEAK@Z`
- size: `2165`
- prototype: `int(struct _tagPK_CONTEXTS_DATA *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, struct _SCARD_PIN *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001e130`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x1800219c0`
- `0x180022bc0`
- `0x1800293c0`
- `0x1800301f0`
- `0x1800627c8`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bb8`
- `bcrypt!BCryptDecrypt` at `0x180021faf`
- `bcrypt!BCryptDecrypt` at `0x1800220b9`
- `bcrypt!BCryptDecrypt` at `0x180021faf`
- `bcrypt!BCryptDecrypt` at `0x1800220b9`
- `bcrypt!BCryptDestroyKey` at `0x180022125`
- `bcrypt!BCryptDestroyKey` at `0x180022125`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002216a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002216a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021e8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022026`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021e8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022026`
- `CRYPT32!CertComparePublicKeyInfo` at `0x180021c3f`
- `CRYPT32!CertComparePublicKeyInfo` at `0x180021c3f`
- `CRYPT32!CertCreateCertificateContext` at `0x180021ba9`
- `CRYPT32!CertCreateCertificateContext` at `0x180021ba9`
- `CRYPT32!CertFreeCertificateContext` at `0x180022178`
- `CRYPT32!CertFreeCertificateContext` at `0x180022178`
- `cryptngc!NgcDecryptWithUserIdKeySilent` at `0x180021e07`
- `cryptngc!NgcDecryptWithUserIdKeySilent` at `0x180021e07`

## string_xrefs

- `0x180021b48`: `_ValidateSCardCacheData`
- `0x180021bdd`: `CertCreateCertificateContext`

## pseudocode

```c
__int64 __fastcall PKDecryptData(
        struct _tagPK_CONTEXTS_DATA *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        ULONG cbInput,
        struct _SCARD_PIN *a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  const char *v10; // r9
  char v11; // al
  const char *v12; // rcx
  bool v13; // zf
  _QWORD *v15; // rax
  _QWORD *v16; // r15
  struct _SEC_WINNT_AUTH_DATA_TYPE_SMARTCARD_CONTEXTS_DATA *v17; // r12
  const char *v18; // r9
  unsigned int v19; // r14d
  const char *v20; // rax
  __int64 v21; // rdi
  PCCERT_CONTEXT CertificateContext; // rax
  signed int LastError; // eax
  unsigned int v24; // edi
  const char *v25; // rax
  const char *v26; // rax
  const CERT_CONTEXT *v27; // r12
  const char *v28; // rax
  unsigned int v29; // r15d
  unsigned __int8 *v30; // r14
  int v31; // eax
  BCRYPT_KEY_HANDLE v32; // r15
  const char *v33; // r9
  char v34; // al
  const char *v35; // rcx
  bool v36; // zf
  __int64 v37; // rdx
  const char *v38; // r9
  int v39; // eax
  const char *v40; // r9
  unsigned __int8 *v41; // rax
  const char *v42; // rax
  _BYTE *v43; // rcx
  __int64 v44; // rax
  const char *v45; // r9
  char v46; // al
  const char *v47; // rcx
  bool v48; // zf
  char v49; // al
  HLOCAL pbOutput; // rax
  unsigned __int8 *v51; // r12
  char v52; // al
  char v53; // al
  __int64 v54; // rdx
  unsigned __int8 *v55; // rax
  void *v56; // rcx
  __int64 v57; // rdx
  _BYTE *v58; // rax
  const char *v59; // r9
  const char *v60; // r9
  PUCHAR pbIV; // [rsp+20h] [rbp-59h]
  PUCHAR pbIVa; // [rsp+20h] [rbp-59h]
  PUCHAR pbIVb; // [rsp+20h] [rbp-59h]
  const char *cbIV; // [rsp+28h] [rbp-51h]
  ULONG pcbResult; // [rsp+50h] [rbp-29h] BYREF
  unsigned int uBytes[3]; // [rsp+54h] [rbp-25h] BYREF
  void *Src; // [rsp+60h] [rbp-19h] BYREF
  void *v68; // [rsp+68h] [rbp-11h]
  BCRYPT_KEY_HANDLE hKey; // [rsp+78h] [rbp-1h] BYREF
  unsigned int v70; // [rsp+C0h] [rbp+47h]

  v70 = 0;
  uBytes[0] = 0;
  pcbResult = 0;
  hKey = 0;
  Src = 0;
  if ( a1 )
  {
    v15 = (_QWORD *)*((_QWORD *)a1 + 1);
    if ( *(_DWORD *)a1 )
    {
      if ( !v15 || (v17 = 0, v16 = (_QWORD *)*((_QWORD *)a1 + 1), !*v15) )
      {
        v60 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v60, 1439, "Null Arg(s)", &Class);
        return 3221225485LL;
      }
    }
    else
    {
      if ( !v15 || !*v15 )
      {
        v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v18, 1429, "Null Arg(s)", &Class);
        return 3221225485LL;
      }
      v16 = 0;
      v17 = (struct _SEC_WINNT_AUTH_DATA_TYPE_SMARTCARD_CONTEXTS_DATA *)*((_QWORD *)a1 + 1);
    }
    if ( a4 && cbInput && a7 && a8 )
    {
      *a8 = 0;
      *a7 = 0;
      v19 = _ValidateSCardCacheData(a2, a3);
      if ( v19 )
      {
        v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v19, v20, 1456, "_ValidateSCardCacheData", &Class);
        return v19;
      }
      v13 = *(_DWORD *)a1 == 0;
      v68 = 0;
      if ( v13 )
      {
        v21 = *(_QWORD *)v17;
        CertificateContext = CertCreateCertificateContext(0x10001u, &a2[*((unsigned int *)a2 + 2)], *((_DWORD *)a2 + 3));
        *(_QWORD *)&uBytes[1] = CertificateContext;
        if ( !CertificateContext )
        {
          LastError = GetLastError();
          v24 = LastError;
          if ( LastError > 0 )
            v24 = (unsigned __int16)LastError | 0xC0070000;
          v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v24, v25, 1474, "CertCreateCertificateContext", &Class);
          return v24;
        }
        if ( !CertComparePublicKeyInfo(
                0x10001u,
                (PCERT_PUBLIC_KEY_INFO)(*(_QWORD *)(v21 + 24) + 96LL),
                &CertificateContext->pCertInfo->SubjectPublicKeyInfo) )
        {
          v24 = -1073739509;
          v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221227787LL, v26, 1483, "Public key mismatch", &Class);
          v27 = *(const CERT_CONTEXT **)&uBytes[1];
LABEL_106:
          CertFreeCertificateContext(v27);
LABEL_107:
          v56 = v68;
          if ( v68 )
          {
            v57 = pcbResult;
            v58 = v68;
            if ( pcbResult )
            {
              do
              {
                *v58++ = 0;
                --v57;
              }
              while ( v57 );
            }
            FreeMemory(v56);
          }
          return v24;
        }
        v24 = _DecryptWithSCard(
                v17,
                &a2[*((unsigned int *)a2 + 6)],
                *((_DWORD *)a2 + 7),
                a6,
                (unsigned __int8 **)&Src,
                uBytes);
        if ( v24 )
        {
          v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
          LODWORD(pbIV) = 1493;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v24, v28, pbIV, "_DecryptWithSCard", &Class);
          v29 = uBytes[0];
          v30 = (unsigned __int8 *)Src;
LABEL_98:
          v27 = *(const CERT_CONTEXT **)&uBytes[1];
          goto LABEL_99;
        }
        v29 = uBytes[0];
        v30 = (unsigned __int8 *)Src;
        v70 = uBytes[0];
LABEL_34:
        v31 = _ImportAesKey(&hKey, v30, v29, &a2[*((unsigned int *)a2 + 4)], *((_DWORD *)a2 + 5));
        v32 = hKey;
        v24 = v31;
        if ( v31 )
        {
          v33 = "";
          while ( 1 )
          {
            v34 = *(v33 - 1);
            v35 = v33--;
            v36 = v34 == 92;
            if ( v34 == 92 )
              break;
            if ( v33 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
            {
              v36 = v34 == 92;
              break;
            }
          }
          cbIV = "_ImportAesKey";
          LODWORD(pbIVa) = 1514;
        }
        else
        {
          v24 = BCryptDecrypt(hKey, a4, cbInput, 0, 0, 0, 0, 0, &pcbResult, 1u);
          if ( v24 )
          {
            v33 = "";
            while ( 1 )
            {
              v49 = *(v33 - 1);
              v35 = v33--;
              v36 = v49 == 92;
              if ( v49 == 92 )
                break;
              if ( v33 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
              {
                v36 = v49 == 92;
                break;
              }
            }
            cbIV = "BCryptDecrypt";
            LODWORD(pbIVa) = 1529;
          }
          else
          {
            if ( g_pLsaFunctionTable )
              pbOutput = (HLOCAL)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(pcbResult);
            else
              pbOutput = LocalAlloc(0x40u, pcbResult);
            v68 = pbOutput;
            v51 = (unsigned __int8 *)pbOutput;
            if ( pbOutput )
            {
              v24 = BCryptDecrypt(v32, a4, cbInput, 0, 0, 0, (PUCHAR)pbOutput, pcbResult, &pcbResult, 1u);
              if ( !v24 )
              {
                *a7 = v51;
                v24 = 0;
                v68 = 0;
                *a8 = pcbResult;
LABEL_95:
                if ( v32 )
                  BCryptDestroyKey(v32);
                v29 = v70;
                goto LABEL_98;
              }
              v33 = "";
              while ( 1 )
              {
                v53 = *(v33 - 1);
                v35 = v33--;
                v36 = v53 == 92;
                if ( v53 == 92 )
                  break;
                if ( v33 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
                {
                  v36 = v53 == 92;
                  break;
                }
              }
              cbIV = "BCryptDecrypt";
              LODWORD(pbIVa) = 1549;
            }
            else
            {
              v24 = -1073741801;
              v33 = "";
              while ( 1 )
              {
                v52 = *(v33 - 1);
                v35 = v33--;
                v36 = v52 == 92;
                if ( v52 == 92 )
                  break;
                if ( v33 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
                {
                  v36 = v52 == 92;
                  break;
                }
              }
              cbIV = "AllocateMemory";
              LODWORD(pbIVa) = 1535;
            }
          }
        }
        if ( v36 )
          v33 = v35;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v24, v33, pbIVa, cbIV, &Class);
        goto LABEL_95;
      }
      v37 = v16[1];
      v24 = 0;
      v27 = 0;
      memset(uBytes, 0, sizeof(uBytes));
      Src = 0;
      if ( v37 )
      {
        v39 = NgcDecryptWithUserIdKeySilent(
                *v16,
                v37,
                &a2[*((unsigned int *)a2 + 6)],
                *((unsigned int *)a2 + 7),
                &Src,
                uBytes);
        if ( v39 >= 0 )
        {
          v29 = uBytes[0];
          v70 = uBytes[0];
          if ( g_pLsaFunctionTable )
            v41 = (unsigned __int8 *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(uBytes[0]);
          else
            v41 = (unsigned __int8 *)LocalAlloc(0x40u, uBytes[0]);
          v30 = v41;
          if ( v41 )
          {
            memcpy_0(v41, Src, uBytes[0]);
          }
          else
          {
            v24 = -1073741801;
            v42 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
            LODWORD(pbIVb) = 1098;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v42, pbIVb, "AllocateMemory", &Class);
          }
LABEL_60:
          v43 = Src;
          if ( Src )
          {
            v44 = uBytes[0];
            if ( uBytes[0] )
            {
              do
              {
                *v43++ = 0;
                --v44;
              }
              while ( v44 );
              v43 = Src;
            }
            LocalFree(v43);
          }
          if ( v24 )
          {
            v45 = "";
            while ( 1 )
            {
              v46 = *(v45 - 1);
              v47 = v45--;
              v48 = v46 == 92;
              if ( v46 == 92 )
                break;
              if ( v45 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
              {
                v48 = v46 == 92;
                break;
              }
            }
            if ( v48 )
              v45 = v47;
            LODWORD(pbIVb) = 1504;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v24, v45, pbIVb, "_DecryptWithNgc", &Class);
LABEL_99:
            if ( v30 )
            {
              v54 = v29;
              v55 = v30;
              if ( v29 )
              {
                do
                {
                  *v55++ = 0;
                  --v54;
                }
                while ( v54 );
              }
              if ( g_pLsaFunctionTable )
                ((void (__fastcall *)(unsigned __int8 *, __int64))g_pLsaFunctionTable->FreeLsaHeap)(v30, v54);
              else
                LocalFree(v30);
            }
            if ( !v27 )
              goto LABEL_107;
            goto LABEL_106;
          }
          goto LABEL_34;
        }
        if ( v39 == -2146893775 )
        {
          v24 = -1073740927;
        }
        else if ( v39 == -2146893773 )
        {
          v24 = -1073740928;
        }
        else
        {
          v24 = (unsigned __int16)v39;
          if ( (_WORD)v39 )
            v24 = (unsigned __int16)v39 | 0xC0070000;
        }
        v40 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
        LODWORD(pbIVb) = 1089;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v24, v40, pbIVb, "NgcDecryptWithUserIdKeySilent", &Class);
      }
      else
      {
        v24 = -1073740928;
        v38 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221226368LL, v38, 1061, "NgcMissingDecryptionAuthTicket", &Class);
      }
      v30 = 0;
      v29 = 0;
      goto LABEL_60;
    }
    v59 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v59, 1449, "Null Arg(s)", &Class);
    return 3221225485LL;
  }
  v10 = "";
  while ( 1 )
  {
    v11 = *(v10 - 1);
    v12 = v10--;
    v13 = v11 == 92;
    if ( v11 == 92 )
      break;
    if ( v10 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
    {
      v13 = v11 == 92;
      break;
    }
  }
  if ( v13 )
    v10 = v12;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v10, 1419, "Null Arg(s)", &Class);
  return 3221225485LL;
}

```

## disassembly

```asm
0x1800219c0  mov     [rsp-8+pbInput], r9
0x1800219c5  push    rbp
0x1800219c6  push    rbx
0x1800219c7  push    rsi
0x1800219c8  push    rdi
0x1800219c9  push    r13
0x1800219cb  lea     rbp, [rsp-17h]
0x1800219d0  sub     rsp, 90h
0x1800219d7  xor     ebx, ebx
0x1800219d9  mov     r13, rdx
0x1800219dc  mov     [rbp+37h+arg_0], ebx
0x1800219df  mov     rdi, rcx
0x1800219e2  mov     dword ptr [rbp+37h+uBytes], ebx
0x1800219e5  mov     [rbp+37h+var_60], ebx
0x1800219e8  mov     [rbp+37h+hKey], rbx
0x1800219ec  mov     [rbp+37h+Src], rbx
0x1800219f0  test    rcx, rcx
0x1800219f3  jnz     short loc_180021A71
0x1800219f5  lea     r9, aOnecoreDsExtCl_0+43h; ""
0x1800219fc  lea     rbx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x180021a03  nop     dword ptr [rax+00h]
0x180021a07  nop     word ptr [rax+rax+00000000h]
0x180021a10  movzx   eax, byte ptr [r9-1]
0x180021a15  mov     rcx, r9
0x180021a18  dec     r9
0x180021a1b  cmp     al, 5Ch ; '\'
0x180021a1d  jz      short loc_180021A26
0x180021a1f  cmp     r9, rbx
0x180021a22  ja      short loc_180021A10
0x180021a24  cmp     al, 5Ch ; '\'
0x180021a26  lea     rax, aNullArgS; "Null Arg(s)"
0x180021a2d  cmovz   r9, rcx
0x180021a31  lea     rsi, Class
0x180021a38  mov     r8d, 0C000000Dh
0x180021a3e  mov     [rsp+0B0h+pbOutput], rsi
0x180021a43  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180021a4a  mov     qword ptr [rsp+0B0h+cbIV], rax
0x180021a4f  xor     ecx, ecx
0x180021a51  mov     dword ptr [rsp+0B0h+pbIV], 58Bh
0x180021a59  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180021a5e  mov     eax, 0C000000Dh
0x180021a63  add     rsp, 90h
0x180021a6a  pop     r13
0x180021a6c  pop     rdi
0x180021a6d  pop     rsi
0x180021a6e  pop     rbx
0x180021a6f  pop     rbp
0x180021a70  retn
0x180021a71  mov     rax, [rcx+8]
0x180021a75  mov     [rsp+0B0h+arg_8], r12
0x180021a7d  mov     [rsp+0B0h+var_30], r15
0x180021a85  cmp     [rcx], ebx
0x180021a87  jnz     short loc_180021ACF
0x180021a89  test    rax, rax
0x180021a8c  jz      short loc_180021A9B
0x180021a8e  cmp     [rax], rbx
0x180021a91  jz      short loc_180021A9B
0x180021a93  mov     r15, rbx
0x180021a96  mov     r12, rax
0x180021a99  jmp     short loc_180021AE7
0x180021a9b  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x180021aa2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180021aa7  mov     r9, rax
0x180021aaa  lea     rsi, Class
0x180021ab1  mov     [rsp+0B0h+pbOutput], rsi
0x180021ab6  lea     rax, aNullArgS; "Null Arg(s)"
0x180021abd  mov     qword ptr [rsp+0B0h+cbIV], rax
0x180021ac2  mov     dword ptr [rsp+0B0h+pbIV], 595h
0x180021aca  jmp     loc_180022217
0x180021acf  test    rax, rax
0x180021ad2  jz      loc_1800221E8
0x180021ad8  mov     r12, rbx
0x180021adb  mov     r15, rax
0x180021ade  cmp     [rax], rbx
0x180021ae1  jz      loc_1800221E8
0x180021ae7  test    r9, r9
0x180021aea  jz      loc_1800221B7
0x180021af0  cmp     [rbp+37h+cbInput], ebx
0x180021af3  jz      loc_1800221B7
0x180021af9  mov     rax, [rbp+37h+arg_30]
0x180021afd  test    rax, rax
0x180021b00  jz      loc_1800221B7
0x180021b06  mov     rcx, [rbp+37h+arg_38]
0x180021b0a  test    rcx, rcx
0x180021b0d  jz      loc_1800221B7
0x180021b13  mov     [rcx], ebx
0x180021b15  mov     edx, r8d; unsigned int
0x180021b18  mov     rcx, r13; unsigned __int8 *
0x180021b1b  mov     [rsp+0B0h+var_28], r14
0x180021b23  mov     [rax], rbx
0x180021b26  call    ?_ValidateSCardCacheData@@YAJPEAEK@Z; _ValidateSCardCacheData(uchar *,ulong)
0x180021b2b  mov     r14d, eax
0x180021b2e  test    eax, eax
0x180021b30  jz      short loc_180021B7A
0x180021b32  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x180021b39  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180021b3e  mov     r9, rax
0x180021b41  lea     rsi, Class
0x180021b48  lea     rax, aValidatescardc; "_ValidateSCardCacheData"
0x180021b4f  mov     [rsp+0B0h+pbOutput], rsi
0x180021b54  mov     qword ptr [rsp+0B0h+cbIV], rax
0x180021b59  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180021b60  mov     r8d, r14d
0x180021b63  mov     dword ptr [rsp+0B0h+pbIV], 5B0h
0x180021b6b  xor     ecx, ecx
0x180021b6d  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180021b72  mov     eax, r14d
0x180021b75  jmp     loc_180021C04
0x180021b7a  cmp     dword ptr [rdi], 0
0x180021b7d  lea     rsi, Class
0x180021b84  mov     [rbp+37h+var_48], rbx
0x180021b88  lea     rbx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x180021b8f  jnz     loc_180021D89
0x180021b95  mov     edx, [r13+8]
0x180021b99  mov     ecx, 10001h; dwCertEncodingType
0x180021b9e  mov     r8d, [r13+0Ch]; cbCertEncoded
0x180021ba2  add     rdx, r13; pbCertEncoded
0x180021ba5  mov     rdi, [r12]
0x180021ba9  call    cs:__imp_CertCreateCertificateContext
0x180021baf  mov     qword ptr [rbp+37h+uBytes+4], rax
0x180021bb3  test    rax, rax
0x180021bb6  jnz     short loc_180021C2A
0x180021bb8  call    cs:__imp_GetLastError
0x180021bbe  mov     edi, eax
0x180021bc0  test    eax, eax
0x180021bc2  jle     short loc_180021BCD
0x180021bc4  movzx   edi, ax
0x180021bc7  or      edi, 0C0070000h
0x180021bcd  mov     rcx, rbx; char *
0x180021bd0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180021bd5  mov     r9, rax
0x180021bd8  mov     [rsp+0B0h+pbOutput], rsi
0x180021bdd  lea     rax, aCertcreatecert; "CertCreateCertificateContext"
0x180021be4  mov     r8d, edi
0x180021be7  mov     qword ptr [rsp+0B0h+cbIV], rax
0x180021bec  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180021bf3  xor     ecx, ecx
0x180021bf5  mov     dword ptr [rsp+0B0h+pbIV], 5C2h
0x180021bfd  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180021c02  mov     eax, edi
0x180021c04  mov     r14, [rsp+0B0h+var_28]
0x180021c0c  mov     r12, [rsp+0B0h+arg_8]
0x180021c14  mov     r15, [rsp+0B0h+var_30]
0x180021c1c  add     rsp, 90h
0x180021c23  pop     r13
0x180021c25  pop     rdi
0x180021c26  pop     rsi
0x180021c27  pop     rbx
0x180021c28  pop     rbp
0x180021c29  retn
0x180021c2a  mov     r8, [rax+18h]
0x180021c2e  mov     ecx, 10001h; dwCertEncodingType
0x180021c33  mov     rdx, [rdi+18h]
0x180021c37  add     r8, 60h ; '`'; pPublicKey2
0x180021c3b  add     rdx, 60h ; '`'; pPublicKey1
0x180021c3f  call    cs:__imp_CertComparePublicKeyInfo
0x180021c45  test    eax, eax
0x180021c47  jnz     short loc_180021C8C
0x180021c49  mov     rcx, rbx; char *
0x180021c4c  mov     edi, 0C000090Bh
0x180021c51  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180021c56  mov     r9, rax
0x180021c59  mov     [rsp+0B0h+pbOutput], rsi
0x180021c5e  lea     rax, aPublicKeyMisma; "Public key mismatch"
0x180021c65  mov     r8d, edi
0x180021c68  mov     qword ptr [rsp+0B0h+cbIV], rax
0x180021c6d  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180021c74  xor     ecx, ecx
0x180021c76  mov     dword ptr [rsp+0B0h+pbIV], 5CBh
0x180021c7e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180021c83  mov     r12, qword ptr [rbp+37h+uBytes+4]
0x180021c87  jmp     loc_180022175
0x180021c8c  mov     edx, [r13+18h]
0x180021c90  lea     rax, [rbp+37h+uBytes]
0x180021c94  mov     r9, [rbp+37h+arg_28]; struct _SCARD_PIN *
0x180021c98  add     rdx, r13; unsigned __int8 *
0x180021c9b  mov     r8d, [r13+1Ch]; unsigned int
0x180021c9f  mov     rcx, r12; struct _SEC_WINNT_AUTH_DATA_TYPE_SMARTCARD_CONTEXTS_DATA *
0x180021ca2  mov     qword ptr [rsp+0B0h+cbIV], rax; unsigned int *
0x180021ca7  lea     rax, [rbp+37h+Src]
0x180021cab  mov     [rsp+0B0h+pbIV], rax; unsigned __int8 **
0x180021cb0  call    ?_DecryptWithSCard@@YAJPEAU_SEC_WINNT_AUTH_DATA_TYPE_SMARTCARD_CONTEXTS_DATA@@PEAEKPEAU_SCARD_PIN@@PEAPEAEPEAK@Z; _DecryptWithSCard(_SEC_WINNT_AUTH_DATA_TYPE_SMARTCARD_CONTEXTS_DATA *,uchar *,ulong,_SCARD_PIN *,uchar * *,ulong *)
0x180021cb5  mov     edi, eax
0x180021cb7  test    eax, eax
0x180021cb9  jz      short loc_180021CFD
0x180021cbb  mov     rcx, rbx; char *
0x180021cbe  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180021cc3  mov     r9, rax
0x180021cc6  mov     [rsp+0B0h+pbOutput], rsi
0x180021ccb  lea     rax, aDecryptwithsca; "_DecryptWithSCard"
0x180021cd2  mov     r8d, edi
0x180021cd5  mov     qword ptr [rsp+0B0h+cbIV], rax
0x180021cda  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180021ce1  xor     ecx, ecx
0x180021ce3  mov     dword ptr [rsp+0B0h+pbIV], 5D5h
0x180021ceb  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180021cf0  mov     r15d, dword ptr [rbp+37h+uBytes]
0x180021cf4  mov     r14, [rbp+37h+Src]
0x180021cf8  jmp     loc_18002212F
0x180021cfd  mov     r15d, dword ptr [rbp+37h+uBytes]
0x180021d01  mov     r14, [rbp+37h+Src]
0x180021d05  mov     [rbp+37h+arg_0], r15d
0x180021d09  mov     r9d, [r13+10h]
0x180021d0d  lea     rcx, [rbp+37h+hKey]; void **
0x180021d11  mov     eax, [r13+14h]
0x180021d15  add     r9, r13; unsigned __int8 *
0x180021d18  mov     r8d, r15d; unsigned int
0x180021d1b  mov     dword ptr [rsp+0B0h+pbIV], eax; unsigned int
0x180021d1f  mov     rdx, r14; unsigned __int8 *
0x180021d22  call    ?_ImportAesKey@@YAJPEAPEAXPEAEK1K@Z; _ImportAesKey(void * *,uchar *,ulong,uchar *,ulong)
0x180021d27  mov     r15, [rbp+37h+hKey]
0x180021d2b  mov     edi, eax
0x180021d2d  test    eax, eax
0x180021d2f  jz      loc_180021F79
0x180021d35  lea     r9, aOnecoreDsExtCl_0+43h; ""
0x180021d3c  nop     dword ptr [rax+00h]
0x180021d40  movzx   eax, byte ptr [r9-1]
0x180021d45  mov     rcx, r9
0x180021d48  dec     r9
0x180021d4b  cmp     al, 5Ch ; '\'
0x180021d4d  jz      short loc_180021D56
0x180021d4f  cmp     r9, rbx
0x180021d52  ja      short loc_180021D40
0x180021d54  cmp     al, 5Ch ; '\'
0x180021d56  mov     [rsp+0B0h+pbOutput], rsi
0x180021d5b  lea     rax, aImportaeskey; "_ImportAesKey"
0x180021d62  mov     qword ptr [rsp+0B0h+cbIV], rax
0x180021d67  mov     dword ptr [rsp+0B0h+pbIV], 5EAh
0x180021d6f  cmovz   r9, rcx
0x180021d73  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180021d7a  xor     ecx, ecx
0x180021d7c  mov     r8d, edi
0x180021d7f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180021d84  jmp     loc_18002211D
0x180021d89  mov     rdx, [r15+8]
0x180021d8d  xor     edi, edi
0x180021d8f  mov     qword ptr [rbp+37h+uBytes+4], rdi
0x180021d93  mov     r12d, edi
0x180021d96  mov     dword ptr [rbp+37h+uBytes], edi
0x180021d99  mov     [rbp+37h+Src], rdi
0x180021d9d  test    rdx, rdx
0x180021da0  jnz     short loc_180021DE7
0x180021da2  mov     rcx, rbx; char *
0x180021da5  mov     edi, 0C0000380h
0x180021daa  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180021daf  mov     [rsp+0B0h+pbOutput], rsi
0x180021db4  mov     r9, rax
0x180021db7  lea     rax, aNgcmissingdecr; "NgcMissingDecryptionAuthTicket"
0x180021dbe  mov     qword ptr [rsp+0B0h+cbIV], rax
0x180021dc3  mov     dword ptr [rsp+0B0h+pbIV], 425h
0x180021dcb  mov     r8d, edi
0x180021dce  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180021dd5  xor     ecx, ecx
0x180021dd7  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180021ddc  mov     r14, r12
0x180021ddf  mov     r15d, r12d
0x180021de2  jmp     loc_180021EE7
0x180021de7  mov     r8d, [r13+18h]
0x180021deb  lea     rax, [rbp+37h+uBytes]
0x180021def  mov     r9d, [r13+1Ch]
0x180021df3  add     r8, r13
0x180021df6  mov     rcx, [r15]
0x180021df9  mov     qword ptr [rsp+0B0h+cbIV], rax
0x180021dfe  lea     rax, [rbp+37h+Src]
0x180021e02  mov     [rsp+0B0h+pbIV], rax
0x180021e07  call    cs:__imp_NgcDecryptWithUserIdKeySilent
0x180021e0d  test    eax, eax
0x180021e0f  jns     short loc_180021E63
0x180021e11  cmp     eax, 80090031h
0x180021e16  jnz     short loc_180021E1F
0x180021e18  mov     edi, 0C0000381h
0x180021e1d  jmp     short loc_180021E3A
0x180021e1f  cmp     eax, 80090033h
0x180021e24  jnz     short loc_180021E2D
0x180021e26  mov     edi, 0C0000380h
0x180021e2b  jmp     short loc_180021E3A
0x180021e2d  movzx   edi, ax
0x180021e30  test    edi, edi
0x180021e32  jz      short loc_180021E3A
0x180021e34  or      edi, 0C0070000h
0x180021e3a  mov     rcx, rbx; char *
0x180021e3d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180021e42  mov     [rsp+0B0h+pbOutput], rsi
0x180021e47  mov     r9, rax
0x180021e4a  lea     rax, aNgcdecryptwith_0; "NgcDecryptWithUserIdKeySilent"
0x180021e51  mov     qword ptr [rsp+0B0h+cbIV], rax
0x180021e56  mov     dword ptr [rsp+0B0h+pbIV], 441h
0x180021e5e  jmp     loc_180021DCB
0x180021e63  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180021e6a  mov     r15d, dword ptr [rbp+37h+uBytes]
0x180021e6e  mov     [rbp+37h+arg_0], r15d
0x180021e72  test    rax, rax
0x180021e75  jz      short loc_180021E85
0x180021e77  mov     rax, [rax+28h]
0x180021e7b  mov     ecx, r15d
0x180021e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e83  jmp     short loc_180021E93
0x180021e85  mov     rdx, r15; uBytes
0x180021e88  mov     ecx, 40h ; '@'; uFlags
0x180021e8d  call    cs:__imp_LocalAlloc
  ... truncated ...
```
