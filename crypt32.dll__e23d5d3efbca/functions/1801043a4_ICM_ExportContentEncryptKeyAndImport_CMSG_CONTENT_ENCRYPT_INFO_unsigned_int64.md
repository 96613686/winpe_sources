# ICM_ExportContentEncryptKeyAndImport(_CMSG_CONTENT_ENCRYPT_INFO *,unsigned __int64)

- ea: `0x1801043a4`
- end: `0x1801046f2`
- name: `?ICM_ExportContentEncryptKeyAndImport@@YA_KPEAU_CMSG_CONTENT_ENCRYPT_INFO@@_K@Z`
- size: `846`
- prototype: `unsigned __int64 __fastcall(struct _CMSG_CONTENT_ENCRYPT_INFO *, HCRYPTPROV hProv)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180101a70`
- `0x180101d20`
- `0x180101f20`

## callees

- `0x180028d60`
- `0x18002f0cc`
- `0x18004d730`
- `0x180083980`
- `0x1800bec20`
- `0x1801043a4`
- `0x180107380`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104683`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010441a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010441a`
- `bcrypt!BCryptGenRandom` at `0x18010440b`
- `bcrypt!BCryptGenRandom` at `0x18010440b`
- `CRYPTSP!CryptHashData` at `0x180104459`
- `CRYPTSP!CryptHashData` at `0x180104561`
- `CRYPTSP!CryptHashData` at `0x180104459`
- `CRYPTSP!CryptHashData` at `0x180104561`
- `CRYPTSP!CryptDestroyHash` at `0x180104523`
- `CRYPTSP!CryptDestroyHash` at `0x1801046b6`
- `CRYPTSP!CryptDestroyHash` at `0x180104523`
- `CRYPTSP!CryptDestroyHash` at `0x1801046b6`
- `CRYPTSP!CryptDestroyKey` at `0x180104515`
- `CRYPTSP!CryptDestroyKey` at `0x180104694`
- `CRYPTSP!CryptDestroyKey` at `0x1801046a7`
- `CRYPTSP!CryptDestroyKey` at `0x180104515`
- `CRYPTSP!CryptDestroyKey` at `0x180104694`
- `CRYPTSP!CryptDestroyKey` at `0x1801046a7`
- `CRYPTSP!CryptExportKey` at `0x1801044c4`
- `CRYPTSP!CryptExportKey` at `0x180104503`
- `CRYPTSP!CryptExportKey` at `0x1801044c4`
- `CRYPTSP!CryptExportKey` at `0x180104503`
- `CRYPTSP!CryptCreateHash` at `0x18010443c`
- `CRYPTSP!CryptCreateHash` at `0x180104544`
- `CRYPTSP!CryptCreateHash` at `0x18010443c`
- `CRYPTSP!CryptCreateHash` at `0x180104544`
- `CRYPTSP!CryptImportKey` at `0x1801045d8`
- `CRYPTSP!CryptImportKey` at `0x1801045d8`
- `CRYPTSP!CryptSetKeyParam` at `0x1801044a1`
- `CRYPTSP!CryptSetKeyParam` at `0x1801045a5`
- `CRYPTSP!CryptSetKeyParam` at `0x18010462c`
- `CRYPTSP!CryptSetKeyParam` at `0x180104660`
- `CRYPTSP!CryptSetKeyParam` at `0x180104679`
- `CRYPTSP!CryptSetKeyParam` at `0x1801044a1`
- `CRYPTSP!CryptSetKeyParam` at `0x1801045a5`
- `CRYPTSP!CryptSetKeyParam` at `0x18010462c`
- `CRYPTSP!CryptSetKeyParam` at `0x180104660`
- `CRYPTSP!CryptSetKeyParam` at `0x180104679`
- `CRYPTSP!CryptDeriveKey` at `0x180104482`
- `CRYPTSP!CryptDeriveKey` at `0x18010458a`
- `CRYPTSP!CryptDeriveKey` at `0x180104482`
- `CRYPTSP!CryptDeriveKey` at `0x18010458a`

## pseudocode

```c
HCRYPTKEY __fastcall ICM_ExportContentEncryptKeyAndImport(struct _CMSG_CONTENT_ENCRYPT_INFO *a1, HCRYPTPROV hProv)
{
  HCRYPTPROV_LEGACY hCryptProv; // rsi
  BYTE *v5; // rdi
  int IsSP3CompatibleEncrypt; // eax
  DWORD LastError; // ebx
  HCRYPTKEY phKey; // [rsp+30h] [rbp-29h] BYREF
  DWORD dwDataLen; // [rsp+38h] [rbp-21h] BYREF
  HCRYPTHASH hHash; // [rsp+40h] [rbp-19h] BYREF
  BYTE v12[4]; // [rsp+48h] [rbp-11h] BYREF
  unsigned int v13; // [rsp+4Ch] [rbp-Dh] BYREF
  HCRYPTKEY hKey; // [rsp+50h] [rbp-9h] BYREF
  BYTE pbData[4]; // [rsp+58h] [rbp-1h] BYREF
  unsigned int v16; // [rsp+5Ch] [rbp+3h] BYREF
  BYTE v17[4]; // [rsp+60h] [rbp+7h] BYREF
  int v18; // [rsp+64h] [rbp+Bh]
  BYTE *v19; // [rsp+68h] [rbp+Fh]
  UCHAR pbBuffer[8]; // [rsp+70h] [rbp+17h] BYREF
  BYTE v21[16]; // [rsp+78h] [rbp+1Fh] BYREF

  hCryptProv = a1->hCryptProv;
  hHash = 0;
  phKey = 0;
  hKey = 0;
  dwDataLen = 0;
  v13 = 0;
  *(_DWORD *)v12 = 0;
  v5 = 0;
  v16 = 0;
  *(_DWORD *)pbData = 40;
  if ( BCryptGenRandom(0, pbBuffer, 8u, 2u) < 0 )
  {
    SetLastError(0x54Fu);
    goto LABEL_22;
  }
  if ( !CryptCreateHash(hCryptProv, 0x8004u, 0, 0, &hHash) )
    goto LABEL_22;
  if ( !CryptHashData(hHash, pbBuffer, 8u, 0) )
    goto LABEL_22;
  if ( !CryptDeriveKey(hCryptProv, 0x6602u, hHash, 0x280000u, &phKey) )
    goto LABEL_22;
  CryptSetKeyParam(phKey, 0x13u, pbData, 0);
  if ( !CryptExportKey(a1->hContentEncryptKey, phKey, 0xBu, 0, 0, &dwDataLen)
    || (v5 = (BYTE *)PkiAlloc(dwDataLen)) == 0
    || !CryptExportKey(a1->hContentEncryptKey, phKey, 0xBu, 0, v5, &dwDataLen)
    || (CryptDestroyKey(phKey),
        phKey = 0,
        CryptDestroyHash(hHash),
        hHash = 0,
        !CryptCreateHash(hProv, 0x8004u, 0, 0, &hHash))
    || !CryptHashData(hHash, pbBuffer, 8u, 0)
    || !CryptDeriveKey(hProv, 0x6602u, hHash, 0x280000u, &phKey)
    || (CryptSetKeyParam(phKey, 0x13u, pbData, 0),
        IsSP3CompatibleEncrypt = ICM_IsSP3CompatibleEncrypt(a1),
        !CryptImportKey(hProv, v5, dwDataLen, phKey, IsSP3CompatibleEncrypt != 0 ? 1 : 17, &hKey))
    || !(unsigned int)ICM_GetEncryptParameters(&a1->ContentEncryptionAlgorithm, &v13, (unsigned int *)v12, v21, &v16, 0) )
  {
LABEL_22:
    LastError = GetLastError();
    if ( hKey )
    {
      CryptDestroyKey(hKey);
      hKey = 0;
    }
    goto LABEL_24;
  }
  LastError = 0;
  if ( v13 == 26114 && *(_DWORD *)v12 )
    CryptSetKeyParam(hKey, 0x13u, v12, 0);
  if ( v16 )
  {
    if ( v13 == 26625 )
    {
      v18 = 0;
      v19 = v21;
      *(_DWORD *)v17 = v16;
      if ( CryptSetKeyParam(hKey, 0xAu, v17, 0) )
        goto LABEL_24;
    }
    else if ( CryptSetKeyParam(hKey, 1u, v21, 0) )
    {
      goto LABEL_24;
    }
    goto LABEL_22;
  }
LABEL_24:
  if ( phKey )
    CryptDestroyKey(phKey);
  if ( hHash )
    CryptDestroyHash(hHash);
  PkiDefaultCryptFree(v5);
  ICM_SetLastError(LastError);
  return hKey;
}

```

## disassembly

```asm
0x1801043a4  mov     [rsp-8+arg_10], rbx
0x1801043a9  push    rbp
0x1801043aa  push    rsi
0x1801043ab  push    rdi
0x1801043ac  push    r14
0x1801043ae  push    r15
0x1801043b0  lea     rbp, [rsp-37h]
0x1801043b5  sub     rsp, 90h
0x1801043bc  mov     rax, cs:__security_cookie
0x1801043c3  xor     rax, rsp
0x1801043c6  mov     [rbp+57h+var_28], rax
0x1801043ca  mov     rsi, [rcx+8]
0x1801043ce  xor     r15d, r15d
0x1801043d1  mov     r14, rdx
0x1801043d4  mov     [rbp+57h+hHash], r15
0x1801043d8  mov     rbx, rcx
0x1801043db  mov     [rbp+57h+phKey], r15
0x1801043df  lea     rdx, [rbp+57h+pbBuffer]; pbBuffer
0x1801043e3  mov     [rbp+57h+hKey], r15
0x1801043e7  lea     r9d, [r15+2]; dwFlags
0x1801043eb  mov     [rbp+57h+dwDataLen], r15d
0x1801043ef  lea     r8d, [r15+8]; cbBuffer
0x1801043f3  mov     [rbp+57h+var_64], r15d
0x1801043f7  xor     ecx, ecx; hAlgorithm
0x1801043f9  mov     dword ptr [rbp+57h+var_68], r15d
0x1801043fd  mov     edi, r15d
0x180104400  mov     [rbp+57h+var_54], r15d
0x180104404  mov     dword ptr [rbp+57h+pbData], 28h ; '('
0x18010440b  call    cs:__imp_BCryptGenRandom
0x180104411  test    eax, eax
0x180104413  jns     short loc_180104425
0x180104415  mov     ecx, 54Fh; dwErrCode
0x18010441a  call    cs:__imp_SetLastError
0x180104420  jmp     loc_180104683
0x180104425  lea     rax, [rbp+57h+hHash]
0x180104429  xor     r9d, r9d; dwFlags
0x18010442c  xor     r8d, r8d; hKey
0x18010442f  mov     [rsp+0B0h+phHash], rax; phHash
0x180104434  mov     edx, 8004h; Algid
0x180104439  mov     rcx, rsi; hProv
0x18010443c  call    cs:__imp_CryptCreateHash
0x180104442  test    eax, eax
0x180104444  jz      loc_180104683
0x18010444a  mov     rcx, [rbp+57h+hHash]; hHash
0x18010444e  lea     rdx, [rbp+57h+pbBuffer]; pbData
0x180104452  xor     r9d, r9d; dwFlags
0x180104455  lea     r8d, [r9+8]; dwDataLen
0x180104459  call    cs:__imp_CryptHashData
0x18010445f  test    eax, eax
0x180104461  jz      loc_180104683
0x180104467  mov     r8, [rbp+57h+hHash]; hBaseData
0x18010446b  lea     rax, [rbp+57h+phKey]
0x18010446f  mov     r9d, 280000h; dwFlags
0x180104475  mov     [rsp+0B0h+phHash], rax; phKey
0x18010447a  mov     edx, 6602h; Algid
0x18010447f  mov     rcx, rsi; hProv
0x180104482  call    cs:__imp_CryptDeriveKey
0x180104488  test    eax, eax
0x18010448a  jz      loc_180104683
0x180104490  mov     rcx, [rbp+57h+phKey]; hKey
0x180104494  lea     r8, [rbp+57h+pbData]; pbData
0x180104498  xor     r9d, r9d; dwFlags
0x18010449b  lea     esi, [r9+13h]
0x18010449f  mov     edx, esi; dwParam
0x1801044a1  call    cs:__imp_CryptSetKeyParam
0x1801044a7  mov     rdx, [rbp+57h+phKey]; hExpKey
0x1801044ab  lea     rax, [rbp+57h+dwDataLen]
0x1801044af  mov     rcx, [rbx+58h]; hKey
0x1801044b3  lea     r8d, [rsi-8]; dwBlobType
0x1801044b7  mov     [rsp+0B0h+pdwDataLen], rax; pdwDataLen
0x1801044bc  xor     r9d, r9d; dwFlags
0x1801044bf  mov     [rsp+0B0h+phHash], r15; pbData
0x1801044c4  call    cs:__imp_CryptExportKey
0x1801044ca  test    eax, eax
0x1801044cc  jz      loc_180104683
0x1801044d2  mov     ecx, [rbp+57h+dwDataLen]; uBytes
0x1801044d5  call    PkiAlloc
0x1801044da  mov     rdi, rax
0x1801044dd  test    rax, rax
0x1801044e0  jz      loc_180104683
0x1801044e6  mov     rdx, [rbp+57h+phKey]; hExpKey
0x1801044ea  lea     rax, [rbp+57h+dwDataLen]
0x1801044ee  mov     rcx, [rbx+58h]; hKey
0x1801044f2  lea     r8d, [rsi-8]; dwBlobType
0x1801044f6  mov     [rsp+0B0h+pdwDataLen], rax; pdwDataLen
0x1801044fb  xor     r9d, r9d; dwFlags
0x1801044fe  mov     [rsp+0B0h+phHash], rdi; pbData
0x180104503  call    cs:__imp_CryptExportKey
0x180104509  test    eax, eax
0x18010450b  jz      loc_180104683
0x180104511  mov     rcx, [rbp+57h+phKey]; hKey
0x180104515  call    cs:__imp_CryptDestroyKey
0x18010451b  mov     rcx, [rbp+57h+hHash]; hHash
0x18010451f  mov     [rbp+57h+phKey], r15
0x180104523  call    cs:__imp_CryptDestroyHash
0x180104529  lea     rax, [rbp+57h+hHash]
0x18010452d  mov     [rbp+57h+hHash], r15
0x180104531  xor     r9d, r9d; dwFlags
0x180104534  mov     [rsp+0B0h+phHash], rax; phHash
0x180104539  xor     r8d, r8d; hKey
0x18010453c  mov     edx, 8004h; Algid
0x180104541  mov     rcx, r14; hProv
0x180104544  call    cs:__imp_CryptCreateHash
0x18010454a  test    eax, eax
0x18010454c  jz      loc_180104683
0x180104552  mov     rcx, [rbp+57h+hHash]; hHash
0x180104556  lea     r8d, [rsi-0Bh]; dwDataLen
0x18010455a  xor     r9d, r9d; dwFlags
0x18010455d  lea     rdx, [rbp+57h+pbBuffer]; pbData
0x180104561  call    cs:__imp_CryptHashData
0x180104567  test    eax, eax
0x180104569  jz      loc_180104683
0x18010456f  mov     r8, [rbp+57h+hHash]; hBaseData
0x180104573  lea     rax, [rbp+57h+phKey]
0x180104577  mov     r9d, 280000h; dwFlags
0x18010457d  mov     [rsp+0B0h+phHash], rax; phKey
0x180104582  mov     edx, 6602h; Algid
0x180104587  mov     rcx, r14; hProv
0x18010458a  call    cs:__imp_CryptDeriveKey
0x180104590  test    eax, eax
0x180104592  jz      loc_180104683
0x180104598  mov     rcx, [rbp+57h+phKey]; hKey
0x18010459c  lea     r8, [rbp+57h+pbData]; pbData
0x1801045a0  xor     r9d, r9d; dwFlags
0x1801045a3  mov     edx, esi; dwParam
0x1801045a5  call    cs:__imp_CryptSetKeyParam
0x1801045ab  mov     rcx, rbx; struct _CMSG_CONTENT_ENCRYPT_INFO *
0x1801045ae  call    ?ICM_IsSP3CompatibleEncrypt@@YAHPEAU_CMSG_CONTENT_ENCRYPT_INFO@@@Z; ICM_IsSP3CompatibleEncrypt(_CMSG_CONTENT_ENCRYPT_INFO *)
0x1801045b3  mov     r9, [rbp+57h+phKey]; hPubKey
0x1801045b7  neg     eax
0x1801045b9  mov     r8d, [rbp+57h+dwDataLen]; dwDataLen
0x1801045bd  lea     rax, [rbp+57h+hKey]
0x1801045c1  sbb     edx, edx
0x1801045c3  mov     [rsp+0B0h+pdwDataLen], rax; phKey
0x1801045c8  and     edx, 0FFFFFFF0h
0x1801045cb  mov     rcx, r14; hProv
0x1801045ce  add     edx, 11h
0x1801045d1  mov     dword ptr [rsp+0B0h+phHash], edx; dwFlags
0x1801045d5  mov     rdx, rdi; pbData
0x1801045d8  call    cs:__imp_CryptImportKey
0x1801045de  test    eax, eax
0x1801045e0  jz      loc_180104683
0x1801045e6  lea     rax, [rbp+57h+var_54]
0x1801045ea  mov     [rsp+0B0h+pdwDataLen], r15; struct _CRYPT_OID_INFO **
0x1801045ef  lea     rcx, [rbx+10h]; struct _CRYPT_ALGORITHM_IDENTIFIER *
0x1801045f3  mov     [rsp+0B0h+phHash], rax; unsigned int *
0x1801045f8  lea     r9, [rbp+57h+var_38]; unsigned __int8 *
0x1801045fc  lea     r8, [rbp+57h+var_68]; unsigned int *
0x180104600  lea     rdx, [rbp+57h+var_64]; unsigned int *
0x180104604  call    ?ICM_GetEncryptParameters@@YAHPEAU_CRYPT_ALGORITHM_IDENTIFIER@@PEAK1QEAE1PEAPEBU_CRYPT_OID_INFO@@@Z; ICM_GetEncryptParameters(_CRYPT_ALGORITHM_IDENTIFIER *,ulong *,ulong *,uchar * const,ulong *,_CRYPT_OID_INFO const * *)
0x180104609  test    eax, eax
0x18010460b  jz      short loc_180104683
0x18010460d  mov     ebx, r15d
0x180104610  cmp     [rbp+57h+var_64], 6602h
0x180104617  jnz     short loc_180104632
0x180104619  cmp     dword ptr [rbp+57h+var_68], r15d
0x18010461d  jz      short loc_180104632
0x18010461f  mov     rcx, [rbp+57h+hKey]; hKey
0x180104623  lea     r8, [rbp+57h+var_68]; pbData
0x180104627  xor     r9d, r9d; dwFlags
0x18010462a  mov     edx, esi; dwParam
0x18010462c  call    cs:__imp_CryptSetKeyParam
0x180104632  mov     eax, [rbp+57h+var_54]
0x180104635  test    eax, eax
0x180104637  jz      short loc_18010469E
0x180104639  xor     r9d, r9d; dwFlags
0x18010463c  cmp     [rbp+57h+var_64], 6801h
0x180104643  jnz     short loc_18010466C
0x180104645  lea     rcx, [rbp+57h+var_38]
0x180104649  mov     [rbp+57h+var_4C], r15d
0x18010464d  mov     [rbp+57h+var_48], rcx
0x180104651  lea     r8, [rbp+57h+var_50]; pbData
0x180104655  mov     rcx, [rbp+57h+hKey]; hKey
0x180104659  lea     edx, [r9+0Ah]; dwParam
0x18010465d  mov     dword ptr [rbp+57h+var_50], eax
0x180104660  call    cs:__imp_CryptSetKeyParam
0x180104666  test    eax, eax
0x180104668  jz      short loc_180104683
0x18010466a  jmp     short loc_18010469E
0x18010466c  mov     rcx, [rbp+57h+hKey]; hKey
0x180104670  lea     r8, [rbp+57h+var_38]; pbData
0x180104674  mov     edx, 1; dwParam
0x180104679  call    cs:__imp_CryptSetKeyParam
0x18010467f  test    eax, eax
0x180104681  jnz     short loc_18010469E
0x180104683  call    cs:__imp_GetLastError
0x180104689  mov     rcx, [rbp+57h+hKey]; hKey
0x18010468d  mov     ebx, eax
0x18010468f  test    rcx, rcx
0x180104692  jz      short loc_18010469E
0x180104694  call    cs:__imp_CryptDestroyKey
0x18010469a  mov     [rbp+57h+hKey], r15
0x18010469e  mov     rcx, [rbp+57h+phKey]; hKey
0x1801046a2  test    rcx, rcx
0x1801046a5  jz      short loc_1801046AD
0x1801046a7  call    cs:__imp_CryptDestroyKey
0x1801046ad  mov     rcx, [rbp+57h+hHash]; hHash
0x1801046b1  test    rcx, rcx
0x1801046b4  jz      short loc_1801046BC
0x1801046b6  call    cs:__imp_CryptDestroyHash
0x1801046bc  mov     rcx, rdi; hMem
0x1801046bf  call    PkiDefaultCryptFree
0x1801046c4  mov     ecx, ebx; unsigned int
0x1801046c6  call    ?ICM_SetLastError@@YAXK@Z; ICM_SetLastError(ulong)
0x1801046cb  mov     rax, [rbp+57h+hKey]
0x1801046cf  mov     rcx, [rbp+57h+var_28]
0x1801046d3  xor     rcx, rsp; StackCookie
0x1801046d6  call    __security_check_cookie
0x1801046db  mov     rbx, [rsp+0B0h+arg_10]
0x1801046e3  add     rsp, 90h
0x1801046ea  pop     r15
0x1801046ec  pop     r14
0x1801046ee  pop     rdi
0x1801046ef  pop     rsi
0x1801046f0  pop     rbp
0x1801046f1  retn
```
