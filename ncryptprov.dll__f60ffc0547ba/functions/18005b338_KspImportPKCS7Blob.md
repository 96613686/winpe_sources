# KspImportPKCS7Blob

- ea: `0x18005b338`
- end: `0x18005b80f`
- name: `KspImportPKCS7Blob`
- size: `1239`
- prototype: `__int64 __fastcall(__int64, __int64 *, int, const BYTE *, DWORD cbEncryptedBlob, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18002b460`

## callees

- `0x1800086d0`
- `0x180009f60`
- `0x18000af80`
- `0x18000afd0`
- `0x18000dab0`
- `0x180017580`
- `0x180019d90`
- `0x18002a0c0`
- `0x18005100c`
- `0x18005a2e4`
- `0x18005a468`
- `0x18005b338`
- `0x180062280`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b4cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b5c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b4cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b5c9`
- `bcrypt!BCryptGetProperty` at `0x18005b744`
- `bcrypt!BCryptGetProperty` at `0x18005b744`
- `CRYPT32!CertCloseStore` at `0x18005b7ad`
- `CRYPT32!CertCloseStore` at `0x18005b7ad`
- `CRYPT32!CryptDecryptMessage` at `0x18005b4bd`
- `CRYPT32!CryptDecryptMessage` at `0x18005b5b9`
- `CRYPT32!CryptDecryptMessage` at `0x18005b4bd`
- `CRYPT32!CryptDecryptMessage` at `0x18005b5b9`
- `CRYPT32!CertOpenStore` at `0x18005b432`
- `CRYPT32!CertOpenStore` at `0x18005b432`

## string_xrefs

- `0x18005b3d4`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x18005b459`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x18005b4df`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x18005b5db`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x18005b61d`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x18005b686`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`

## pseudocode

```c
__int64 __fastcall KspImportPKCS7Blob(
        __int64 a1,
        __int64 *a2,
        int a3,
        const BYTE *a4,
        DWORD cbEncryptedBlob,
        unsigned int a6)
{
  __int64 *v8; // rdi
  __int64 v9; // rsi
  unsigned int v10; // ebx
  int v11; // edx
  void *v12; // r15
  DWORD LastError; // eax
  DWORD v14; // eax
  unsigned __int64 v15; // r14
  DWORD *p_pcbDecrypted; // rdi
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  DWORD *v21; // rax
  DWORD v22; // eax
  __int64 v23; // r9
  __int64 v24; // rcx
  unsigned int NewKeyObject; // eax
  __int64 v26; // rdx
  unsigned int UserStorageArea; // eax
  __int64 v28; // rax
  DWORD *v29; // rcx
  __int64 v30; // r8
  int v31; // ecx
  __int64 v33; // [rsp+0h] [rbp-30h] BYREF
  void *pvPara; // [rsp+20h] [rbp-10h]
  DWORD pcbDecrypted; // [rsp+30h] [rbp+0h] BYREF
  unsigned int v36; // [rsp+34h] [rbp+4h] BYREF
  __int64 *v37; // [rsp+38h] [rbp+8h] BYREF
  ULONG pcbResult; // [rsp+40h] [rbp+10h] BYREF
  __int64 v39; // [rsp+48h] [rbp+18h] BYREF
  HCERTSTORE hCertStore; // [rsp+50h] [rbp+20h] BYREF
  __int64 v41; // [rsp+58h] [rbp+28h] BYREF
  __int64 v42; // [rsp+60h] [rbp+30h] BYREF
  __int64 v43; // [rsp+68h] [rbp+38h] BYREF
  __int64 v44; // [rsp+70h] [rbp+40h]
  _BYTE pDecryptPara[32]; // [rsp+78h] [rbp+48h] BYREF

  v37 = a2;
  LODWORD(v44) = 0;
  v43 = 0;
  pcbDecrypted = 0;
  v8 = a2;
  v36 = 0;
  pcbResult = 0;
  hCertStore = 0;
  v9 = 0;
  v41 = 0;
  v42 = 0;
  v39 = 0;
  memset(pDecryptPara, 0, sizeof(pDecryptPara));
  if ( !(unsigned int)CheckPKCS7BlobArgs(a3, (unsigned int)&v41, 0, 0, (__int64)&v42, 1) )
  {
    v10 = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", 1668);
    goto LABEL_46;
  }
  v12 = 0;
  if ( v42 )
    v12 = *(void **)(v42 + 8);
  v44 = *(_QWORD *)(v41 + 8);
  LODWORD(v43) = *(_DWORD *)v41;
  hCertStore = CertOpenStore((LPCSTR)6, 0x10001u, 0, 0x2000u, &v43);
  if ( !hCertStore )
  {
    LastError = GetLastError();
    DebugTraceError(LastError, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", 1688);
    v10 = -2146893785;
    goto LABEL_46;
  }
  *(_QWORD *)&pDecryptPara[16] = &hCertStore;
  *(_QWORD *)&pDecryptPara[8] = 1;
  *(_QWORD *)&pDecryptPara[24] = 64;
  *(_QWORD *)pDecryptPara = 0x1000000000020LL;
  if ( !CryptDecryptMessage((PCRYPT_DECRYPT_MESSAGE_PARA)pDecryptPara, a4, cbEncryptedBlob, 0, &pcbDecrypted, 0) )
  {
    v14 = GetLastError();
    DebugTraceError(v14, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", 1710);
    v10 = -2146893819;
    goto LABEL_46;
  }
  v15 = pcbDecrypted;
  p_pcbDecrypted = 0;
  v10 = 8;
  if ( !pcbDecrypted
    || pcbDecrypted > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)pcbDecrypted + g_ulAdditionalProbeSize + 8 < pcbDecrypted
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_57;
  }
  v17 = v15 + 23;
  if ( v15 + 23 <= v15 + 8 )
    v17 = 0xFFFFFFFFFFFFFF0LL;
  v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
  v19 = alloca(v18);
  v20 = alloca(v18);
  p_pcbDecrypted = &pcbDecrypted;
  if ( &v33 == (__int64 *)-48LL || (pcbDecrypted = 1801679955, (p_pcbDecrypted = (DWORD *)&v37) == 0) )
  {
LABEL_57:
    if ( v15 + 8 >= v15 )
    {
      v21 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_pcbDecrypted = v21;
      if ( v21 )
      {
        *v21 = 1885431112;
        p_pcbDecrypted = v21 + 2;
      }
    }
  }
  if ( p_pcbDecrypted )
  {
    if ( !CryptDecryptMessage(
            (PCRYPT_DECRYPT_MESSAGE_PARA)pDecryptPara,
            a4,
            cbEncryptedBlob,
            (BYTE *)p_pcbDecrypted,
            &pcbDecrypted,
            0) )
    {
      v22 = GetLastError();
      DebugTraceError(v22, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", 1731);
      v10 = -2146893819;
LABEL_41:
      v28 = pcbDecrypted;
      v29 = p_pcbDecrypted;
      if ( pcbDecrypted )
      {
        do
        {
          *(_BYTE *)v29 = 0;
          v29 = (DWORD *)((char *)v29 + 1);
          --v28;
        }
        while ( v28 );
      }
      if ( *(p_pcbDecrypted - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      goto LABEL_45;
    }
    if ( !(unsigned int)GetBlobAlgInfo(p_pcbDecrypted, pcbDecrypted, &v36) )
    {
      v10 = -2146893785;
      v23 = 1743;
      v24 = 2148073511LL;
LABEL_25:
      DebugTraceError(v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", v23);
      goto LABEL_41;
    }
    if ( !KspFindSupportedAlgById(v36) )
    {
      v10 = -2146893783;
      v23 = 1752;
      v24 = 2148073513LL;
      goto LABEL_25;
    }
    NewKeyObject = CreateNewKeyObject(v12, a6, (__int64)&v39);
    v10 = NewKeyObject;
    if ( NewKeyObject )
    {
      DebugTraceError(NewKeyObject, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", 1765);
      v9 = v39;
      goto LABEL_41;
    }
    v9 = v39;
    UserStorageArea = GetUserStorageArea(
                        *(unsigned int *)(v39 + 32),
                        v26,
                        *(unsigned int *)(v39 + 528),
                        *(_QWORD *)(a1 + 40),
                        v39 + 72);
    v10 = UserStorageArea;
    if ( UserStorageArea )
    {
      v23 = 1777;
    }
    else
    {
      UserStorageArea = SetPrivateKeyProperty(v9, L"PRIVATEBLOB", (__int64)p_pcbDecrypted, pcbDecrypted);
      v10 = UserStorageArea;
      if ( !UserStorageArea )
      {
        if ( (a6 & 0x400) == 0 )
        {
          UserStorageArea = SPCryptFinalizeKey(a1, v9, a6);
          v10 = UserStorageArea;
          if ( UserStorageArea )
          {
            v23 = 1803;
            goto LABEL_32;
          }
          UserStorageArea = BCryptGetProperty(
                              *(BCRYPT_HANDLE *)(v9 + 104),
                              L"KeyStrength",
                              (PUCHAR)(v9 + 28),
                              4u,
                              &pcbResult,
                              0);
          v10 = UserStorageArea;
          if ( UserStorageArea )
          {
            v23 = 1817;
            goto LABEL_32;
          }
        }
        *v37 = v9;
        v9 = 0;
        v10 = 0;
        goto LABEL_41;
      }
      v23 = 1790;
    }
LABEL_32:
    v24 = UserStorageArea;
    goto LABEL_25;
  }
LABEL_45:
  v8 = v37;
LABEL_46:
  if ( hCertStore )
    CertCloseStore(hCertStore, 1u);
  if ( v10 )
  {
    if ( !v9 )
      return v10;
    LODWORD(pvPara) = v10;
    LODWORD(v30) = v9;
    v31 = 0;
  }
  else
  {
    v30 = *v8;
    v31 = 1;
    LODWORD(pvPara) = 0;
  }
  KspCryptAuditKeyMigrationOperation(v31, v11, v30, 2465, (_DWORD)pvPara);
  if ( v9 )
    DeleteKeyObject((void *)v9);
  return v10;
}

```

## disassembly

```asm
0x18005b338  push    rbp
0x18005b33a  push    rbx
0x18005b33b  push    rsi
0x18005b33c  push    rdi
0x18005b33d  push    r12
0x18005b33f  push    r13
0x18005b341  push    r14
0x18005b343  push    r15
0x18005b345  sub     rsp, 0A8h
0x18005b34c  lea     rbp, [rsp+30h]
0x18005b351  mov     rax, cs:__security_cookie
0x18005b358  xor     rax, rbp
0x18005b35b  mov     [rbp+0B0h+var_48], rax
0x18005b35f  mov     r13, rcx
0x18005b362  mov     [rbp+0B0h+var_A8], rdx
0x18005b366  xor     ecx, ecx
0x18005b368  mov     dword ptr [rsp+0E0h+ppXchgCert], 1
0x18005b370  mov     qword ptr [rbp+0B0h+var_74], rcx
0x18005b374  mov     rax, r8
0x18005b377  mov     [rbp+38h], rcx
0x18005b37b  mov     r12, r9
0x18005b37e  mov     [rbp+0B0h+pcbDecrypted], ecx
0x18005b381  mov     rdi, rdx
0x18005b384  mov     [rbp+0B0h+var_AC], ecx
0x18005b387  lea     rdx, [rbp+0B0h+var_88]
0x18005b38b  mov     [rbp+0B0h+pcbResult], ecx
0x18005b38e  xorps   xmm0, xmm0
0x18005b391  mov     [rbp+0B0h+hCertStore], rcx
0x18005b395  xor     esi, esi
0x18005b397  lea     rcx, [rbp+0B0h+var_80]
0x18005b39b  mov     [rbp+0B0h+var_88], 0
0x18005b3a3  mov     [rsp+0E0h+pvPara], rcx
0x18005b3a8  xor     r9d, r9d
0x18005b3ab  mov     rcx, rax
0x18005b3ae  mov     [rbp+0B0h+var_80], 0
0x18005b3b6  xor     r8d, r8d
0x18005b3b9  mov     [rbp+0B0h+var_98], rsi
0x18005b3bd  movups  xmmword ptr [rbp+0B0h+pDecryptPara], xmm0
0x18005b3c1  movups  xmmword ptr [rbp+0B0h+pDecryptPara+10h], xmm0
0x18005b3c5  call    CheckPKCS7BlobArgs
0x18005b3ca  test    eax, eax
0x18005b3cc  jnz     short loc_18005B3F6
0x18005b3ce  mov     r9d, 684h
0x18005b3d4  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005b3db  lea     rdx, aStatus; "Status"
0x18005b3e2  mov     ecx, 80090027h
0x18005b3e7  mov     ebx, 80090027h
0x18005b3ec  call    DebugTraceError
0x18005b3f1  jmp     loc_18005B79F
0x18005b3f6  mov     rax, [rbp+0B0h+var_80]
0x18005b3fa  xor     r15d, r15d
0x18005b3fd  test    rax, rax
0x18005b400  jz      short loc_18005B406
0x18005b402  mov     r15, [rax+8]
0x18005b406  mov     rcx, [rbp+0B0h+var_88]
0x18005b40a  xor     r8d, r8d; hCryptProv
0x18005b40d  mov     r9d, 2000h; dwFlags
0x18005b413  mov     edx, 10001h; dwEncodingType
0x18005b418  mov     rax, [rcx+8]
0x18005b41c  mov     qword ptr [rbp+0B0h+var_74+4], rax
0x18005b420  mov     eax, [rcx]
0x18005b422  lea     ecx, [r8+6]; lpszStoreProvider
0x18005b426  mov     [rbp+0B0h+var_78], eax
0x18005b429  lea     rax, [rbp+0B0h+var_78]
0x18005b42d  mov     [rsp+0E0h+pvPara], rax; pvPara
0x18005b432  call    cs:__imp_CertOpenStore
0x18005b439  nop     dword ptr [rax+rax+00h]
0x18005b43e  mov     [rbp+0B0h+hCertStore], rax
0x18005b442  test    rax, rax
0x18005b445  jnz     short loc_18005B478
0x18005b447  call    cs:__imp_GetLastError
0x18005b44e  nop     dword ptr [rax+rax+00h]
0x18005b453  mov     r9d, 698h
0x18005b459  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005b460  mov     ecx, eax
0x18005b462  lea     rdx, aGetlasterror; "GetLastError()"
0x18005b469  call    DebugTraceError
0x18005b46e  mov     ebx, 80090027h
0x18005b473  jmp     loc_18005B79F
0x18005b478  mov     r8d, [rbp+0B0h+cbEncryptedBlob]; cbEncryptedBlob
0x18005b47f  lea     rax, [rbp+0B0h+hCertStore]
0x18005b483  mov     qword ptr [rbp+0B0h+pDecryptPara+10h], rax
0x18005b487  lea     rcx, [rbp+0B0h+pDecryptPara]; pDecryptPara
0x18005b48b  lea     rax, [rbp+0B0h+pcbDecrypted]
0x18005b48f  mov     [rsp+0E0h+ppXchgCert], rsi; ppXchgCert
0x18005b494  xor     r9d, r9d; pbDecrypted
0x18005b497  mov     [rsp+0E0h+pvPara], rax; pcbDecrypted
0x18005b49c  mov     rdx, r12; pbEncryptedBlob
0x18005b49f  mov     qword ptr [rbp+0B0h+pDecryptPara+8], 1
0x18005b4a7  mov     qword ptr [rbp+0B0h+pDecryptPara+18h], 40h ; '@'
0x18005b4af  mov     dword ptr [rbp+0B0h+pDecryptPara], 20h ; ' '
0x18005b4b6  mov     dword ptr [rbp+0B0h+pDecryptPara+4], 10000h
0x18005b4bd  call    cs:__imp_CryptDecryptMessage
0x18005b4c4  nop     dword ptr [rax+rax+00h]
0x18005b4c9  test    eax, eax
0x18005b4cb  jnz     short loc_18005B4FE
0x18005b4cd  call    cs:__imp_GetLastError
0x18005b4d4  nop     dword ptr [rax+rax+00h]
0x18005b4d9  mov     r9d, 6AEh
0x18005b4df  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005b4e6  mov     ecx, eax
0x18005b4e8  lea     rdx, aGetlasterror; "GetLastError()"
0x18005b4ef  call    DebugTraceError
0x18005b4f4  mov     ebx, 80090005h
0x18005b4f9  jmp     loc_18005B79F
0x18005b4fe  mov     r14d, [rbp+0B0h+pcbDecrypted]
0x18005b502  xor     edi, edi
0x18005b504  lea     ebx, [rdi+8]
0x18005b507  test    r14, r14
0x18005b50a  jz      short loc_18005B56B
0x18005b50c  cmp     r14, cs:g_ulMaxStackAllocSize
0x18005b513  ja      short loc_18005B56B
0x18005b515  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005b51c  add     rcx, rbx
0x18005b51f  add     rcx, r14
0x18005b522  cmp     rcx, r14
0x18005b525  jb      short loc_18005B56B
0x18005b527  call    VerifyStackAvailable
0x18005b52c  test    eax, eax
0x18005b52e  jz      short loc_18005B56B
0x18005b530  lea     rax, [r14+8]
0x18005b534  lea     rcx, [rax+0Fh]
0x18005b538  cmp     rcx, rax
0x18005b53b  ja      short loc_18005B547
0x18005b53d  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18005b547  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005b54b  mov     rax, rcx
0x18005b54e  call    _alloca_probe
0x18005b553  sub     rsp, rcx
0x18005b556  lea     rdi, [rsp+0E0h+pcbDecrypted]
0x18005b55b  test    rdi, rdi
0x18005b55e  jz      short loc_18005B56B
0x18005b560  mov     dword ptr [rdi], 6B637453h
0x18005b566  add     rdi, rbx
0x18005b569  jnz     short loc_18005B591
0x18005b56b  lea     rcx, [r14+8]
0x18005b56f  cmp     rcx, r14
0x18005b572  jb      short loc_18005B591
0x18005b574  mov     rax, cs:g_pfnAllocate
0x18005b57b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b580  mov     rdi, rax
0x18005b583  test    rax, rax
0x18005b586  jz      short loc_18005B591
0x18005b588  mov     dword ptr [rax], 70616548h
0x18005b58e  add     rdi, rbx
0x18005b591  test    rdi, rdi
0x18005b594  jz      loc_18005B79B
0x18005b59a  mov     r8d, [rbp+0B0h+cbEncryptedBlob]; cbEncryptedBlob
0x18005b5a1  lea     rax, [rbp+0B0h+pcbDecrypted]
0x18005b5a5  mov     [rsp+0E0h+ppXchgCert], rsi; ppXchgCert
0x18005b5aa  lea     rcx, [rbp+0B0h+pDecryptPara]; pDecryptPara
0x18005b5ae  mov     r9, rdi; pbDecrypted
0x18005b5b1  mov     [rsp+0E0h+pvPara], rax; pcbDecrypted
0x18005b5b6  mov     rdx, r12; pbEncryptedBlob
0x18005b5b9  call    cs:__imp_CryptDecryptMessage
0x18005b5c0  nop     dword ptr [rax+rax+00h]
0x18005b5c5  test    eax, eax
0x18005b5c7  jnz     short loc_18005B5FA
0x18005b5c9  call    cs:__imp_GetLastError
0x18005b5d0  nop     dword ptr [rax+rax+00h]
0x18005b5d5  mov     r9d, 6C3h
0x18005b5db  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005b5e2  mov     ecx, eax
0x18005b5e4  lea     rdx, aGetlasterror; "GetLastError()"
0x18005b5eb  call    DebugTraceError
0x18005b5f0  mov     ebx, 80090005h
0x18005b5f5  jmp     loc_18005B76C
0x18005b5fa  mov     edx, [rbp+0B0h+pcbDecrypted]
0x18005b5fd  lea     r8, [rbp+0B0h+var_AC]
0x18005b601  mov     rcx, rdi
0x18005b604  call    GetBlobAlgInfo
0x18005b609  test    eax, eax
0x18005b60b  jnz     short loc_18005B635
0x18005b60d  mov     ebx, 80090027h
0x18005b612  mov     r9d, 6CFh
0x18005b618  mov     ecx, 80090027h
0x18005b61d  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005b624  lea     rdx, aStatus; "Status"
0x18005b62b  call    DebugTraceError
0x18005b630  jmp     loc_18005B76C
0x18005b635  mov     ecx, [rbp+0B0h+var_AC]
0x18005b638  call    KspFindSupportedAlgById
0x18005b63d  test    rax, rax
0x18005b640  jnz     short loc_18005B654
0x18005b642  mov     ebx, 80090029h
0x18005b647  mov     r9d, 6D8h
0x18005b64d  mov     ecx, 80090029h
0x18005b652  jmp     short loc_18005B61D
0x18005b654  mov     r14d, [rbp+0B0h+arg_28]
0x18005b65b  lea     rcx, [rbp+0B0h+var_98]
0x18005b65f  mov     [rsp+0E0h+ppXchgCert], rcx; __int64
0x18005b664  xor     r9d, r9d
0x18005b667  mov     rcx, r15; Src
0x18005b66a  mov     dword ptr [rsp+0E0h+pvPara], r14d; int
0x18005b66f  mov     r8, rax
0x18005b672  mov     rdx, r13
0x18005b675  call    CreateNewKeyObject
0x18005b67a  mov     ebx, eax
0x18005b67c  test    eax, eax
0x18005b67e  jz      short loc_18005B6A4
0x18005b680  mov     r9d, 6E5h
0x18005b686  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005b68d  lea     rdx, aStatus; "Status"
0x18005b694  mov     ecx, eax
0x18005b696  call    DebugTraceError
0x18005b69b  mov     rsi, [rbp+0B0h+var_98]
0x18005b69f  jmp     loc_18005B76C
0x18005b6a4  mov     rsi, [rbp+0B0h+var_98]
0x18005b6a8  mov     r9, [r13+28h]
0x18005b6ac  mov     r8d, [rsi+210h]
0x18005b6b3  lea     rax, [rsi+48h]
0x18005b6b7  mov     ecx, [rsi+20h]
0x18005b6ba  mov     [rsp+0E0h+pvPara], rax
0x18005b6bf  call    GetUserStorageArea
0x18005b6c4  mov     ebx, eax
0x18005b6c6  test    eax, eax
0x18005b6c8  jz      short loc_18005B6D7
0x18005b6ca  mov     r9d, 6F1h
0x18005b6d0  mov     ecx, eax
0x18005b6d2  jmp     loc_18005B61D
0x18005b6d7  mov     r9d, [rbp+0B0h+pcbDecrypted]
0x18005b6db  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x18005b6e2  mov     r8, rdi
0x18005b6e5  mov     rcx, rsi
0x18005b6e8  call    SetPrivateKeyProperty
0x18005b6ed  mov     ebx, eax
0x18005b6ef  test    eax, eax
0x18005b6f1  jz      short loc_18005B6FB
0x18005b6f3  mov     r9d, 6FEh
0x18005b6f9  jmp     short loc_18005B6D0
0x18005b6fb  bt      r14d, 0Ah
0x18005b700  jb      short loc_18005B761
0x18005b702  mov     r8d, r14d
0x18005b705  mov     rdx, rsi
0x18005b708  mov     rcx, r13
0x18005b70b  call    SPCryptFinalizeKey
0x18005b710  mov     ebx, eax
0x18005b712  test    eax, eax
0x18005b714  jz      short loc_18005B71E
0x18005b716  mov     r9d, 70Bh
0x18005b71c  jmp     short loc_18005B6D0
0x18005b71e  mov     rcx, [rsi+68h]; hObject
0x18005b722  lea     rax, [rbp+0B0h+pcbResult]
0x18005b726  lea     r8, [rsi+1Ch]; pbOutput
0x18005b72a  mov     dword ptr [rsp+0E0h+ppXchgCert], 0; dwFlags
0x18005b732  mov     r9d, 4; cbOutput
0x18005b738  mov     [rsp+0E0h+pvPara], rax; pcbResult
0x18005b73d  lea     rdx, aKeystrength; "KeyStrength"
0x18005b744  call    cs:__imp_BCryptGetProperty
0x18005b74b  nop     dword ptr [rax+rax+00h]
0x18005b750  mov     ebx, eax
0x18005b752  test    eax, eax
0x18005b754  jz      short loc_18005B761
0x18005b756  mov     r9d, 719h
0x18005b75c  jmp     loc_18005B6D0
0x18005b761  mov     rax, [rbp+0B0h+var_A8]
0x18005b765  mov     [rax], rsi
0x18005b768  xor     esi, esi
0x18005b76a  xor     ebx, ebx
0x18005b76c  mov     eax, [rbp+0B0h+pcbDecrypted]
0x18005b76f  mov     rcx, rdi
0x18005b772  test    rax, rax
0x18005b775  jz      short loc_18005B783
0x18005b777  mov     byte ptr [rcx], 0
0x18005b77a  inc     rcx
0x18005b77d  sub     rax, 1
0x18005b781  jnz     short loc_18005B777
0x18005b783  lea     rcx, [rdi-8]
0x18005b787  cmp     dword ptr [rcx], 70616548h
0x18005b78d  jnz     short loc_18005B79B
0x18005b78f  mov     rax, cs:g_pfnFree
0x18005b796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b79b  mov     rdi, [rbp+0B0h+var_A8]
0x18005b79f  mov     rcx, [rbp+0B0h+hCertStore]; hCertStore
0x18005b7a3  test    rcx, rcx
0x18005b7a6  jz      short loc_18005B7B9
0x18005b7a8  mov     edx, 1; dwFlags
0x18005b7ad  call    cs:__imp_CertCloseStore
0x18005b7b4  nop     dword ptr [rax+rax+00h]
0x18005b7b9  test    ebx, ebx
0x18005b7bb  jnz     short loc_18005B7C9
0x18005b7bd  mov     r8, [rdi]
0x18005b7c0  lea     ecx, [rbx+1]
0x18005b7c3  mov     dword ptr [rsp+0E0h+pvPara], ebx
0x18005b7c7  jmp     short loc_18005B7D7
0x18005b7c9  test    rsi, rsi
0x18005b7cc  jz      short loc_18005B7EF
0x18005b7ce  mov     dword ptr [rsp+0E0h+pvPara], ebx
0x18005b7d2  mov     r8, rsi
0x18005b7d5  xor     ecx, ecx
0x18005b7d7  mov     r9d, 9A1h
0x18005b7dd  call    KspCryptAuditKeyMigrationOperation
0x18005b7e2  test    rsi, rsi
0x18005b7e5  jz      short loc_18005B7EF
0x18005b7e7  mov     rcx, rsi; void *
0x18005b7ea  call    DeleteKeyObject
0x18005b7ef  mov     eax, ebx
0x18005b7f1  mov     rcx, [rbp+0B0h+var_48]
0x18005b7f5  xor     rcx, rbp; StackCookie
0x18005b7f8  call    __security_check_cookie
  ... truncated ...
```
