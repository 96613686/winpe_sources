# CreateObjectContext

- ea: `0x1800185a0`
- end: `0x1800187b5`
- name: `CreateObjectContext`
- size: `533`
- prototype: `int __fastcall(char, __int64, DWORD, int, HCERTSTORE *)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001d0d8`
- `0x1800251b0`
- `0x1800251e0`
- `0x180025210`

## callees

- `0x1800185a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001870a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001870a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186e7`
- `CRYPT32!CertEnumCRLsInStore` at `0x180018719`
- `CRYPT32!CertEnumCRLsInStore` at `0x180018719`
- `CRYPT32!I_CertUpdateStore` at `0x18001869c`
- `CRYPT32!I_CertUpdateStore` at `0x18001869c`
- `CRYPT32!CryptQueryObject` at `0x180018659`
- `CRYPT32!CryptQueryObject` at `0x180018799`
- `CRYPT32!CryptQueryObject` at `0x180018659`
- `CRYPT32!CryptQueryObject` at `0x180018799`
- `CRYPT32!CertCloseStore` at `0x1800186ab`
- `CRYPT32!CertCloseStore` at `0x1800186c7`
- `CRYPT32!CertCloseStore` at `0x1800186ab`
- `CRYPT32!CertCloseStore` at `0x1800186c7`
- `CRYPT32!CertDeleteCRLFromStore` at `0x18001872b`
- `CRYPT32!CertDeleteCRLFromStore` at `0x18001872b`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180018736`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180018736`
- `CRYPT32!CertOpenStore` at `0x1800185d6`
- `CRYPT32!CertOpenStore` at `0x1800185d6`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180018675`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180018675`

## pseudocode

```c
int __fastcall CreateObjectContext(char a1, __int64 a2, DWORD a3, int a4, HCERTSTORE *a5)
{
  HCERTSTORE v7; // rax
  void *v8; // rbp
  int updated; // edi
  DWORD LastError; // r12d
  int v11; // esi
  unsigned int v12; // r14d
  _BYTE **v13; // rdx
  const CERT_CONTEXT *v14; // rax
  const CRL_CONTEXT *v15; // rax
  const void *v16; // rdx
  HCERTSTORE *phCertStore; // rax
  DWORD v18; // r8d
  HCERTSTORE hCertStore; // [rsp+60h] [rbp-58h] BYREF

  if ( (a1 & 1) != 0 )
  {
    v7 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
    v8 = v7;
    if ( v7 )
    {
      updated = 1;
      LastError = 0;
      v11 = 0;
      v12 = 0;
      while ( v12 < *(_DWORD *)a2 )
      {
        v13 = (_BYTE **)(*(_QWORD *)(a2 + 8) + 16LL * v12);
        hCertStore = 0;
        if ( *(_DWORD *)v13 && (*(_DWORD *)v13 != 1 || *v13[1]) )
        {
          if ( CryptQueryObject(2u, v13, a3, 0xEu, 0, 0, 0, 0, &hCertStore, 0, 0) )
          {
            if ( a4 )
            {
              if ( (a3 & 2) == 0 )
              {
                while ( 1 )
                {
                  v14 = CertEnumCertificatesInStore(hCertStore, 0);
                  if ( !v14 )
                    break;
                  CertDeleteCertificateFromStore(v14);
                }
              }
              if ( (a3 & 8) == 0 )
              {
                while ( 1 )
                {
                  v15 = CertEnumCRLsInStore(hCertStore, 0);
                  if ( !v15 )
                    break;
                  CertDeleteCRLFromStore(v15);
                }
              }
            }
            updated = I_CertUpdateStore(v8, hCertStore, 0, 0);
            CertCloseStore(hCertStore, 0);
            v11 = 1;
          }
          else if ( !v11 )
          {
            v11 = -1;
            LastError = GetLastError();
          }
        }
        ++v12;
        if ( updated != 1 )
          goto LABEL_14;
      }
      if ( v11 < 0 )
      {
        updated = 0;
        SetLastError(LastError);
LABEL_14:
        CertCloseStore(v8, 0);
        goto LABEL_15;
      }
      *a5 = v8;
LABEL_15:
      LODWORD(v7) = updated;
    }
  }
  else
  {
    v16 = *(const void **)(a2 + 8);
    phCertStore = 0;
    if ( !a4 )
      phCertStore = a5;
    v18 = a3 & 0xE;
    if ( !a4 )
      v18 = a3;
    LODWORD(v7) = CryptQueryObject(
                    2u,
                    v16,
                    v18,
                    0xEu,
                    0,
                    0,
                    0,
                    0,
                    phCertStore,
                    0,
                    (const void **)((unsigned __int64)a5 & -(__int64)(a4 != 0)));
  }
  return (int)v7;
}

```

## disassembly

```asm
0x1800185a0  mov     [rsp+arg_8], rdx
0x1800185a5  push    rbx
0x1800185a6  push    rbp
0x1800185a7  push    rsi
0x1800185a8  push    rdi
0x1800185a9  push    r12
0x1800185ab  push    r13
0x1800185ad  push    r14
0x1800185af  push    r15
0x1800185b1  sub     rsp, 78h
0x1800185b5  mov     r13d, r9d
0x1800185b8  mov     r15d, r8d
0x1800185bb  test    cl, 1
0x1800185be  jz      loc_180018741
0x1800185c4  xor     ebx, ebx
0x1800185c6  xor     r9d, r9d; dwFlags
0x1800185c9  xor     r8d, r8d; hCryptProv
0x1800185cc  mov     [rsp+0B8h+pvPara], rbx; pvPara
0x1800185d1  xor     edx, edx; dwEncodingType
0x1800185d3  lea     ecx, [rbx+2]; lpszStoreProvider
0x1800185d6  call    cs:__imp_CertOpenStore
0x1800185dc  mov     rbp, rax
0x1800185df  test    rax, rax
0x1800185e2  jz      loc_180018703
0x1800185e8  lea     edi, [rbx+1]
0x1800185eb  mov     r12d, ebx
0x1800185ee  mov     esi, ebx
0x1800185f0  mov     r14d, ebx
0x1800185f3  mov     rax, [rsp+0B8h+arg_8]
0x1800185fb  cmp     r14d, [rax]
0x1800185fe  jnb     loc_1800186F2
0x180018604  mov     edx, r14d
0x180018607  shl     rdx, 4
0x18001860b  add     rdx, [rax+8]; pvObject
0x18001860f  mov     [rsp+0B8h+hCertStore], rbx
0x180018614  cmp     [rdx], ebx
0x180018616  jz      loc_1800186B6
0x18001861c  cmp     dword ptr [rdx], 1
0x18001861f  jz      loc_1800187A4
0x180018625  mov     [rsp+0B8h+ppvContext], rbx; ppvContext
0x18001862a  lea     rax, [rsp+0B8h+hCertStore]
0x18001862f  mov     [rsp+0B8h+phMsg], rbx; phMsg
0x180018634  mov     r9d, 0Eh; dwExpectedFormatTypeFlags
0x18001863a  mov     [rsp+0B8h+phCertStore], rax; phCertStore
0x18001863f  mov     r8d, r15d; dwExpectedContentTypeFlags
0x180018642  mov     [rsp+0B8h+pdwFormatType], rbx; pdwFormatType
0x180018647  mov     [rsp+0B8h+pdwContentType], rbx; pdwContentType
0x18001864c  mov     [rsp+0B8h+pdwMsgAndCertEncodingType], rbx; pdwMsgAndCertEncodingType
0x180018651  lea     ecx, [r9-0Ch]; dwObjectType
0x180018655  mov     dword ptr [rsp+0B8h+pvPara], ebx; dwFlags
0x180018659  call    cs:__imp_CryptQueryObject
0x18001865f  test    eax, eax
0x180018661  jz      short loc_1800186E0
0x180018663  test    r13d, r13d
0x180018666  jz      short loc_18001868E
0x180018668  test    r15b, 2
0x18001866c  jnz     short loc_180018684
0x18001866e  mov     rcx, [rsp+0B8h+hCertStore]; hCertStore
0x180018673  xor     edx, edx; pPrevCertContext
0x180018675  call    cs:__imp_CertEnumCertificatesInStore
0x18001867b  test    rax, rax
0x18001867e  jnz     loc_180018733
0x180018684  test    r15b, 8
0x180018688  jz      loc_180018712
0x18001868e  mov     rdx, [rsp+0B8h+hCertStore]
0x180018693  xor     r9d, r9d
0x180018696  xor     r8d, r8d
0x180018699  mov     rcx, rbp
0x18001869c  call    cs:__imp_I_CertUpdateStore
0x1800186a2  mov     rcx, [rsp+0B8h+hCertStore]; hCertStore
0x1800186a7  xor     edx, edx; dwFlags
0x1800186a9  mov     edi, eax
0x1800186ab  call    cs:__imp_CertCloseStore
0x1800186b1  mov     esi, 1
0x1800186b6  inc     r14d
0x1800186b9  cmp     edi, 1
0x1800186bc  jz      loc_1800185F3
0x1800186c2  xor     edx, edx; dwFlags
0x1800186c4  mov     rcx, rbp; hCertStore
0x1800186c7  call    cs:__imp_CertCloseStore
0x1800186cd  mov     eax, edi
0x1800186cf  add     rsp, 78h
0x1800186d3  pop     r15
0x1800186d5  pop     r14
0x1800186d7  pop     r13
0x1800186d9  pop     r12
0x1800186db  pop     rdi
0x1800186dc  pop     rsi
0x1800186dd  pop     rbp
0x1800186de  pop     rbx
0x1800186df  retn
0x1800186e0  test    esi, esi
0x1800186e2  jnz     short loc_1800186B6
0x1800186e4  or      esi, 0FFFFFFFFh
0x1800186e7  call    cs:__imp_GetLastError
0x1800186ed  mov     r12d, eax
0x1800186f0  jmp     short loc_1800186B6
0x1800186f2  test    esi, esi
0x1800186f4  js      short loc_180018705
0x1800186f6  mov     rcx, [rsp+0B8h+arg_20]
0x1800186fe  mov     [rcx], rbp
0x180018701  jmp     short loc_1800186CD
0x180018703  jmp     short loc_1800186CF
0x180018705  mov     ecx, r12d; dwErrCode
0x180018708  mov     edi, ebx
0x18001870a  call    cs:__imp_SetLastError
0x180018710  jmp     short loc_1800186C2
0x180018712  mov     rcx, [rsp+0B8h+hCertStore]; hCertStore
0x180018717  xor     edx, edx; pPrevCrlContext
0x180018719  call    cs:__imp_CertEnumCRLsInStore
0x18001871f  test    rax, rax
0x180018722  jz      loc_18001868E
0x180018728  mov     rcx, rax; pCrlContext
0x18001872b  call    cs:__imp_CertDeleteCRLFromStore
0x180018731  jmp     short loc_180018712
0x180018733  mov     rcx, rax; pCertContext
0x180018736  call    cs:__imp_CertDeleteCertificateFromStore
0x18001873c  jmp     loc_18001866E
0x180018741  mov     rdx, [rdx+8]; pvObject
0x180018745  mov     eax, r13d
0x180018748  neg     eax
0x18001874a  sbb     rcx, rcx
0x18001874d  xor     ebx, ebx
0x18001874f  and     rcx, [rsp+0B8h+arg_20]
0x180018757  mov     eax, ebx
0x180018759  mov     [rsp+0B8h+ppvContext], rcx; ppvContext
0x18001875e  test    r13d, r13d
0x180018761  mov     [rsp+0B8h+phMsg], rbx; phMsg
0x180018766  cmovz   rax, [rsp+0B8h+arg_20]
0x18001876f  lea     r9d, [rbx+0Eh]; dwExpectedFormatTypeFlags
0x180018773  mov     [rsp+0B8h+phCertStore], rax; phCertStore
0x180018778  lea     ecx, [rbx+2]; dwObjectType
0x18001877b  and     r8d, 0Eh
0x18001877f  mov     [rsp+0B8h+pdwFormatType], rbx; pdwFormatType
0x180018784  test    r13d, r13d
0x180018787  mov     [rsp+0B8h+pdwContentType], rbx; pdwContentType
0x18001878c  mov     [rsp+0B8h+pdwMsgAndCertEncodingType], rbx; pdwMsgAndCertEncodingType
0x180018791  cmovz   r8d, r15d; dwExpectedContentTypeFlags
0x180018795  mov     dword ptr [rsp+0B8h+pvPara], ebx; dwFlags
0x180018799  call    cs:__imp_CryptQueryObject
0x18001879f  jmp     loc_1800186CF
0x1800187a4  mov     rax, [rdx+8]
0x1800187a8  cmp     [rax], bl
0x1800187aa  jz      loc_1800186B6
0x1800187b0  jmp     loc_180018625
```
