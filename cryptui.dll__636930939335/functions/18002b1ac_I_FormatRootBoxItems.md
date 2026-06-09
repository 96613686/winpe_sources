# I_FormatRootBoxItems

- ea: `0x18002b1ac`
- end: `0x18002b555`
- name: `I_FormatRootBoxItems`
- size: `937`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002ad70`

## callees

- `0x18002af3c`
- `0x18002aff8`
- `0x18002b1ac`
- `0x18003a054`
- `0x18003a090`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18002b336`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18002b38c`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18002b336`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18002b38c`
- `CRYPT32!CertCompareCertificateName` at `0x18002b27d`
- `CRYPT32!CertCompareCertificateName` at `0x18002b27d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002b49f`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002b4ed`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002b49f`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002b4ed`
- `CRYPT32!CertNameToStrW` at `0x18002b20f`
- `CRYPT32!CertNameToStrW` at `0x18002b246`
- `CRYPT32!CertNameToStrW` at `0x18002b2b4`
- `CRYPT32!CertNameToStrW` at `0x18002b2e4`
- `CRYPT32!CertNameToStrW` at `0x18002b20f`
- `CRYPT32!CertNameToStrW` at `0x18002b246`
- `CRYPT32!CertNameToStrW` at `0x18002b2b4`
- `CRYPT32!CertNameToStrW` at `0x18002b2e4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002b346`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002b39c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002b346`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002b39c`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x18002b379`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x18002b3bd`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x18002b379`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x18002b3bd`

## pseudocode

```c
__int64 __fastcall I_FormatRootBoxItems(PCCERT_CONTEXT pCertContext, __int64 a2, WCHAR *a3)
{
  DWORD csz; // r15d
  WCHAR *v6; // rax
  WCHAR *v7; // rdi
  DWORD v8; // r15d
  WCHAR *v9; // rax
  WCHAR *v10; // rdi
  PCERT_INFO pCertInfo; // rcx
  PCERT_INFO v12; // r12
  unsigned int v13; // edi
  __int64 cbData; // r14
  BYTE *pbData; // r12
  __int64 v16; // rax
  void *v17; // r15
  int v18; // edx
  _BYTE *v19; // rax
  char v20; // cl
  __int64 v21; // rax
  void *v22; // r12
  struct _FILETIME LocalFileTime; // [rsp+30h] [rbp-D0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v26[128]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v27[128]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR DateStr[128]; // [rsp+1D0h] [rbp+D0h] BYREF

  FormatMsgBoxItem(a3);
  csz = CertNameToStrW(pCertContext->dwCertEncodingType, &pCertContext->pCertInfo->Subject, 0x2000001u, 0, 0);
  v6 = (WCHAR *)PkiNonzeroAlloc(2LL * csz);
  v7 = v6;
  if ( v6 )
    CertNameToStrW(pCertContext->dwCertEncodingType, &pCertContext->pCertInfo->Subject, 0x2000001u, v6, csz);
  FormatMsgBoxItem(a3 + 8);
  PkiFree(v7);
  if ( CertCompareCertificateName(
         pCertContext->dwCertEncodingType,
         &pCertContext->pCertInfo->Subject,
         &pCertContext->pCertInfo->Issuer) )
  {
    FormatMsgBoxItem(a3 + 16);
  }
  else
  {
    v8 = CertNameToStrW(pCertContext->dwCertEncodingType, &pCertContext->pCertInfo->Issuer, 0x2000001u, 0, 0);
    v9 = (WCHAR *)PkiNonzeroAlloc(2LL * v8);
    v10 = v9;
    if ( v9 )
      CertNameToStrW(pCertContext->dwCertEncodingType, &pCertContext->pCertInfo->Issuer, 0x2000001u, v9, v8);
    FormatMsgBoxItem(a3 + 16);
    PkiFree(v10);
  }
  pCertInfo = pCertContext->pCertInfo;
  LocalFileTime = 0;
  DateStr[0] = 0;
  v27[0] = 0;
  SystemTime = 0;
  FileTimeToLocalFileTime(&pCertInfo->NotBefore, &LocalFileTime);
  FileTimeToSystemTime(&LocalFileTime, &SystemTime);
  GetDateFormatW(0x400u, 2u, &SystemTime, 0, DateStr, 128);
  FileTimeToLocalFileTime(&pCertContext->pCertInfo->NotAfter, &LocalFileTime);
  FileTimeToSystemTime(&LocalFileTime, &SystemTime);
  GetDateFormatW(0x400u, 2u, &SystemTime, 0, v27, 128);
  FormatMsgBoxItem(a3 + 24);
  v12 = pCertContext->pCertInfo;
  v13 = 4;
  cbData = v12->SerialNumber.cbData;
  if ( (_DWORD)cbData )
  {
    pbData = v12->SerialNumber.pbData;
    v16 = PkiNonzeroAlloc((unsigned int)cbData);
    v17 = (void *)v16;
    if ( v16 )
    {
      v18 = cbData;
      v19 = (_BYTE *)(v16 + cbData - 1);
      do
      {
        v20 = *pbData++;
        *v19-- = v20;
        --v18;
      }
      while ( v18 );
      v21 = PkiNonzeroAlloc(2LL * (((unsigned int)cbData >> 2) + 2 * (_DWORD)cbData + 1));
      v22 = (void *)v21;
      if ( v21 )
      {
        FormatMsgBoxMultiBytes((unsigned int)cbData, v17, v21);
        FormatMsgBoxItem(a3 + 32);
        v13 = 5;
        PkiFree(v22);
      }
      PkiFree(v17);
    }
  }
  LocalFileTime.dwLowDateTime = 20;
  if ( CertGetCertificateContextProperty(pCertContext, 3u, &SystemTime, (DWORD *)&LocalFileTime) )
  {
    FormatMsgBoxMultiBytes(LocalFileTime.dwLowDateTime, &SystemTime, v26);
    FormatMsgBoxItem(&a3[8 * v13++]);
  }
  if ( CertGetCertificateContextProperty(pCertContext, 4u, &SystemTime, (DWORD *)&LocalFileTime) )
  {
    FormatMsgBoxMultiBytes(LocalFileTime.dwLowDateTime, &SystemTime, v26);
    FormatMsgBoxItem(&a3[8 * v13++]);
  }
  return v13;
}

```

## disassembly

```asm
0x18002b1ac  mov     [rsp-8+arg_8], rbx
0x18002b1b1  push    rbp
0x18002b1b2  push    rsi
0x18002b1b3  push    rdi
0x18002b1b4  push    r12
0x18002b1b6  push    r13
0x18002b1b8  push    r14
0x18002b1ba  push    r15
0x18002b1bc  lea     rbp, [rsp-1E0h]
0x18002b1c4  sub     rsp, 2E0h
0x18002b1cb  mov     rax, cs:__security_cookie
0x18002b1d2  xor     rax, rsp
0x18002b1d5  mov     [rbp+210h+var_40], rax
0x18002b1dc  mov     rsi, r8
0x18002b1df  mov     rbx, rcx
0x18002b1e2  mov     r8d, edx
0x18002b1e5  mov     rcx, rsi; lpBuffer
0x18002b1e8  lea     rdx, [rsi+8]
0x18002b1ec  call    FormatMsgBoxItem
0x18002b1f1  mov     rdx, [rbx+18h]
0x18002b1f5  mov     r12d, 2000001h
0x18002b1fb  mov     ecx, [rbx]; dwCertEncodingType
0x18002b1fd  add     rdx, 50h ; 'P'; pName
0x18002b201  xor     r9d, r9d; psz
0x18002b204  mov     [rsp+310h+csz], 0; csz
0x18002b20c  mov     r8d, r12d; dwStrType
0x18002b20f  call    cs:__imp_CertNameToStrW
0x18002b215  mov     ecx, eax
0x18002b217  add     rcx, rcx; uBytes
0x18002b21a  mov     r15d, eax
0x18002b21d  call    PkiNonzeroAlloc
0x18002b222  lea     r14, Src
0x18002b229  mov     rdi, rax
0x18002b22c  test    rax, rax
0x18002b22f  jz      short loc_18002B251
0x18002b231  mov     rdx, [rbx+18h]
0x18002b235  mov     r9, rax; psz
0x18002b238  mov     ecx, [rbx]; dwCertEncodingType
0x18002b23a  add     rdx, 50h ; 'P'; pName
0x18002b23e  mov     r8d, r12d; dwStrType
0x18002b241  mov     [rsp+310h+csz], r15d; csz
0x18002b246  call    cs:__imp_CertNameToStrW
0x18002b24c  mov     r9, rdi
0x18002b24f  jmp     short loc_18002B254
0x18002b251  mov     r9, r14
0x18002b254  lea     rcx, [rsi+10h]; lpBuffer
0x18002b258  mov     r8d, 0DADh
0x18002b25e  lea     rdx, [rcx+8]
0x18002b262  call    FormatMsgBoxItem
0x18002b267  mov     rcx, rdi; hMem
0x18002b26a  call    PkiFree
0x18002b26f  mov     rdx, [rbx+18h]
0x18002b273  mov     ecx, [rbx]; dwCertEncodingType
0x18002b275  lea     r8, [rdx+30h]; pCertName2
0x18002b279  add     rdx, 50h ; 'P'; pCertName1
0x18002b27d  call    cs:__imp_CertCompareCertificateName
0x18002b283  test    eax, eax
0x18002b285  jz      short loc_18002B29C
0x18002b287  lea     rcx, [rsi+20h]; lpBuffer
0x18002b28b  mov     r8d, 0DAFh
0x18002b291  lea     rdx, [rcx+8]
0x18002b295  call    FormatMsgBoxItem
0x18002b29a  jmp     short loc_18002B30B
0x18002b29c  mov     rdx, [rbx+18h]
0x18002b2a0  xor     r9d, r9d; psz
0x18002b2a3  mov     ecx, [rbx]; dwCertEncodingType
0x18002b2a5  add     rdx, 30h ; '0'; pName
0x18002b2a9  mov     r8d, r12d; dwStrType
0x18002b2ac  mov     [rsp+310h+csz], 0; csz
0x18002b2b4  call    cs:__imp_CertNameToStrW
0x18002b2ba  mov     ecx, eax
0x18002b2bc  add     rcx, rcx; uBytes
0x18002b2bf  mov     r15d, eax
0x18002b2c2  call    PkiNonzeroAlloc
0x18002b2c7  mov     rdi, rax
0x18002b2ca  test    rax, rax
0x18002b2cd  jz      short loc_18002B2ED
0x18002b2cf  mov     rdx, [rbx+18h]
0x18002b2d3  mov     r9, rax; psz
0x18002b2d6  mov     ecx, [rbx]; dwCertEncodingType
0x18002b2d8  add     rdx, 30h ; '0'; pName
0x18002b2dc  mov     r8d, r12d; dwStrType
0x18002b2df  mov     [rsp+310h+csz], r15d; csz
0x18002b2e4  call    cs:__imp_CertNameToStrW
0x18002b2ea  mov     r14, rdi
0x18002b2ed  lea     rcx, [rsi+20h]; lpBuffer
0x18002b2f1  mov     r9, r14
0x18002b2f4  lea     rdx, [rcx+8]
0x18002b2f8  mov     r8d, 0DAEh
0x18002b2fe  call    FormatMsgBoxItem
0x18002b303  mov     rcx, rdi; hMem
0x18002b306  call    PkiFree
0x18002b30b  mov     rcx, [rbx+18h]
0x18002b30f  lea     rdx, [rsp+310h+LocalFileTime]; lpLocalFileTime
0x18002b314  xor     eax, eax
0x18002b316  mov     qword ptr [rsp+310h+LocalFileTime.dwLowDateTime], 0
0x18002b31f  xorps   xmm0, xmm0
0x18002b322  mov     [rbp+210h+DateStr], ax
0x18002b329  add     rcx, 40h ; '@'; lpFileTime
0x18002b32d  mov     [rbp+210h+var_240], ax
0x18002b331  movups  xmmword ptr [rsp+310h+SystemTime.wYear], xmm0
0x18002b336  call    cs:__imp_FileTimeToLocalFileTime
0x18002b33c  lea     rdx, [rsp+310h+SystemTime]; lpSystemTime
0x18002b341  lea     rcx, [rsp+310h+LocalFileTime]; lpFileTime
0x18002b346  call    cs:__imp_FileTimeToSystemTime
0x18002b34c  mov     r15d, 80h
0x18002b352  lea     rax, [rbp+210h+DateStr]
0x18002b359  mov     edi, 400h
0x18002b35e  mov     [rsp+310h+cchDate], r15d; cchDate
0x18002b363  xor     r9d, r9d; lpFormat
0x18002b366  mov     qword ptr [rsp+310h+csz], rax; lpDateStr
0x18002b36b  lea     r8, [rsp+310h+SystemTime]; lpDate
0x18002b370  mov     ecx, edi; Locale
0x18002b372  lea     r14d, [r15-7Eh]
0x18002b376  mov     edx, r14d; dwFlags
0x18002b379  call    cs:__imp_GetDateFormatW
0x18002b37f  mov     rcx, [rbx+18h]
0x18002b383  lea     rdx, [rsp+310h+LocalFileTime]; lpLocalFileTime
0x18002b388  add     rcx, 48h ; 'H'; lpFileTime
0x18002b38c  call    cs:__imp_FileTimeToLocalFileTime
0x18002b392  lea     rdx, [rsp+310h+SystemTime]; lpSystemTime
0x18002b397  lea     rcx, [rsp+310h+LocalFileTime]; lpFileTime
0x18002b39c  call    cs:__imp_FileTimeToSystemTime
0x18002b3a2  lea     rax, [rbp+210h+var_240]
0x18002b3a6  mov     [rsp+310h+cchDate], r15d; cchDate
0x18002b3ab  xor     r9d, r9d; lpFormat
0x18002b3ae  mov     qword ptr [rsp+310h+csz], rax; lpDateStr
0x18002b3b3  lea     r8, [rsp+310h+SystemTime]; lpDate
0x18002b3b8  mov     edx, r14d; dwFlags
0x18002b3bb  mov     ecx, edi; Locale
0x18002b3bd  call    cs:__imp_GetDateFormatW
0x18002b3c3  lea     rcx, [rsi+30h]; lpBuffer
0x18002b3c7  mov     r8d, 0DB3h
0x18002b3cd  lea     rax, [rbp+210h+var_240]
0x18002b3d1  lea     rdx, [rcx+8]
0x18002b3d5  mov     qword ptr [rsp+310h+csz], rax
0x18002b3da  lea     r9, [rbp+210h+DateStr]
0x18002b3e1  call    FormatMsgBoxItem
0x18002b3e6  mov     r12, [rbx+18h]
0x18002b3ea  lea     edi, [r15-7Ch]
0x18002b3ee  mov     r14d, [r12+8]
0x18002b3f3  test    r14d, r14d
0x18002b3f6  jz      loc_18002B485
0x18002b3fc  mov     r12, [r12+10h]
0x18002b401  mov     ecx, r14d; uBytes
0x18002b404  call    PkiNonzeroAlloc
0x18002b409  mov     r15, rax
0x18002b40c  test    rax, rax
0x18002b40f  jz      short loc_18002B485
0x18002b411  lea     rax, [r14-1]
0x18002b415  mov     edx, r14d
0x18002b418  add     rax, r15
0x18002b41b  mov     cl, [r12]
0x18002b41f  inc     r12
0x18002b422  mov     [rax], cl
0x18002b424  dec     rax
0x18002b427  add     edx, 0FFFFFFFFh
0x18002b42a  jnz     short loc_18002B41B
0x18002b42c  mov     eax, r14d
0x18002b42f  lea     ecx, ds:1[r14*2]
0x18002b437  shr     eax, 2
0x18002b43a  add     ecx, eax
0x18002b43c  add     rcx, rcx; uBytes
0x18002b43f  call    PkiNonzeroAlloc
0x18002b444  mov     r12, rax
0x18002b447  test    rax, rax
0x18002b44a  jz      short loc_18002B47D
0x18002b44c  mov     r8, rax
0x18002b44f  mov     rdx, r15
0x18002b452  mov     ecx, r14d
0x18002b455  call    FormatMsgBoxMultiBytes
0x18002b45a  lea     rcx, [rsi+40h]; lpBuffer
0x18002b45e  mov     r9, r12
0x18002b461  lea     rdx, [rcx+8]
0x18002b465  mov     r8d, 0DB0h
0x18002b46b  call    FormatMsgBoxItem
0x18002b470  mov     rcx, r12; hMem
0x18002b473  mov     edi, 5
0x18002b478  call    PkiFree
0x18002b47d  mov     rcx, r15; hMem
0x18002b480  call    PkiFree
0x18002b485  lea     r9, [rsp+310h+LocalFileTime]; pcbData
0x18002b48a  mov     [rsp+310h+LocalFileTime.dwLowDateTime], 14h
0x18002b492  lea     r8, [rsp+310h+SystemTime]; pvData
0x18002b497  mov     edx, 3; dwPropId
0x18002b49c  mov     rcx, rbx; pCertContext
0x18002b49f  call    cs:__imp_CertGetCertificateContextProperty
0x18002b4a5  test    eax, eax
0x18002b4a7  jz      short loc_18002B4DB
0x18002b4a9  mov     ecx, [rsp+310h+LocalFileTime.dwLowDateTime]
0x18002b4ad  lea     r8, [rsp+310h+var_2C0]
0x18002b4b2  lea     rdx, [rsp+310h+SystemTime]
0x18002b4b7  call    FormatMsgBoxMultiBytes
0x18002b4bc  mov     ecx, edi
0x18002b4be  lea     r9, [rsp+310h+var_2C0]
0x18002b4c3  shl     rcx, 4
0x18002b4c7  mov     r8d, 0DB1h
0x18002b4cd  add     rcx, rsi; lpBuffer
0x18002b4d0  lea     rdx, [rcx+8]
0x18002b4d4  call    FormatMsgBoxItem
0x18002b4d9  inc     edi
0x18002b4db  lea     r9, [rsp+310h+LocalFileTime]; pcbData
0x18002b4e0  mov     edx, 4; dwPropId
0x18002b4e5  lea     r8, [rsp+310h+SystemTime]; pvData
0x18002b4ea  mov     rcx, rbx; pCertContext
0x18002b4ed  call    cs:__imp_CertGetCertificateContextProperty
0x18002b4f3  test    eax, eax
0x18002b4f5  jz      short loc_18002B529
0x18002b4f7  mov     ecx, [rsp+310h+LocalFileTime.dwLowDateTime]
0x18002b4fb  lea     r8, [rsp+310h+var_2C0]
0x18002b500  lea     rdx, [rsp+310h+SystemTime]
0x18002b505  call    FormatMsgBoxMultiBytes
0x18002b50a  mov     ecx, edi
0x18002b50c  lea     r9, [rsp+310h+var_2C0]
0x18002b511  shl     rcx, 4
0x18002b515  mov     r8d, 0DB2h
0x18002b51b  add     rcx, rsi; lpBuffer
0x18002b51e  lea     rdx, [rcx+8]
0x18002b522  call    FormatMsgBoxItem
0x18002b527  inc     edi
0x18002b529  mov     eax, edi
0x18002b52b  mov     rcx, [rbp+210h+var_40]
0x18002b532  xor     rcx, rsp; StackCookie
0x18002b535  call    __security_check_cookie
0x18002b53a  mov     rbx, [rsp+310h+arg_8]
0x18002b542  add     rsp, 2E0h
0x18002b549  pop     r15
0x18002b54b  pop     r14
0x18002b54d  pop     r13
0x18002b54f  pop     r12
0x18002b551  pop     rdi
0x18002b552  pop     rsi
0x18002b553  pop     rbp
0x18002b554  retn
```
