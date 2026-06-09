# GetFileContentFromCert(ulong,int,_CERT_CONTEXT const *,uchar * *,ulong *)

- ea: `0x180020f6c`
- end: `0x180021192`
- name: `?GetFileContentFromCert@@YAHKHPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z`
- size: `550`
- prototype: `int(unsigned int, int, const struct _CERT_CONTEXT *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800227f0`

## callees

- `0x180001f66`
- `0x180020f6c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020fff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800210df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021126`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020fff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800210df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021126`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021165`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021035`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002115c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002115c`
- `CRYPT32!CertOpenStore` at `0x180021056`
- `CRYPT32!CertOpenStore` at `0x180021056`
- `CRYPT32!CertCloseStore` at `0x180021178`
- `CRYPT32!CertCloseStore` at `0x180021178`
- `CRYPT32!CertSaveStore` at `0x1800210c6`
- `CRYPT32!CertSaveStore` at `0x18002110e`
- `CRYPT32!CertSaveStore` at `0x1800210c6`
- `CRYPT32!CertSaveStore` at `0x18002110e`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18002107a`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18002107a`
- `CRYPT32!CryptBinaryToStringA` at `0x180020fef`
- `CRYPT32!CryptBinaryToStringA` at `0x180021027`
- `CRYPT32!CryptBinaryToStringA` at `0x180020fef`
- `CRYPT32!CryptBinaryToStringA` at `0x180021027`

## pseudocode

```c
__int64 __fastcall GetFileContentFromCert(int a1, int a2, const struct _CERT_CONTEXT *a3, CHAR **a4, unsigned int *a5)
{
  CHAR *v8; // rbx
  void *v9; // rsi
  unsigned int *v10; // r15
  unsigned int v11; // r14d
  int v12; // ecx
  int v13; // ecx
  DWORD LastError; // ecx
  HCERTSTORE v15; // rax
  CHAR *v17; // rax
  CHAR *v18; // rax
  __int128 pvSaveToPara; // [rsp+30h] [rbp-18h] BYREF
  DWORD pcchString; // [rsp+A8h] [rbp+60h] BYREF

  pcchString = 0;
  v8 = 0;
  v9 = 0;
  pvSaveToPara = 0;
  if ( !a4 )
    goto LABEL_24;
  v10 = a5;
  if ( !a5 || !a3 )
    goto LABEL_24;
  v11 = 1;
  *a4 = 0;
  *v10 = 0;
  v12 = a1 - 1;
  if ( !v12 )
  {
    pcchString = a3->cbCertEncoded;
    v18 = (CHAR *)LocalAlloc(0x40u, pcchString);
    v8 = v18;
    if ( v18 )
    {
      memcpy_0(v18, a3->pbCertEncoded, pcchString);
      goto LABEL_23;
    }
    goto LABEL_21;
  }
  v13 = v12 - 2;
  if ( !v13 )
  {
    v15 = CertOpenStore((LPCSTR)2, 0x10001u, 0, 0, 0);
    v9 = v15;
    if ( !v15 )
      goto LABEL_26;
    if ( !(a2 ? AddChainToStore(v15, a3, 0, 0, 0, 0) : CertAddCertificateContextToStore(v15, a3, 3u, 0)) )
      goto LABEL_26;
    LODWORD(pvSaveToPara) = 0;
    *((_QWORD *)&pvSaveToPara + 1) = 0;
    if ( !CertSaveStore(v9, 0x10001u, 2u, 2u, &pvSaveToPara, 0) )
      goto LABEL_26;
    pcchString = pvSaveToPara;
    v17 = (CHAR *)LocalAlloc(0x40u, (unsigned int)pvSaveToPara);
    v8 = v17;
    if ( v17 )
    {
      *((_QWORD *)&pvSaveToPara + 1) = v17;
      if ( !CertSaveStore(v9, 0x10001u, 2u, 2u, &pvSaveToPara, 0) )
        goto LABEL_26;
      goto LABEL_23;
    }
LABEL_21:
    LastError = -2147024882;
    goto LABEL_25;
  }
  if ( v13 != 1 )
  {
LABEL_24:
    LastError = -2147024809;
    goto LABEL_25;
  }
  if ( CryptBinaryToStringA(a3->pbCertEncoded, a3->cbCertEncoded, 1u, 0, &pcchString) )
  {
    v8 = (CHAR *)LocalAlloc(0x40u, pcchString);
    if ( v8 )
    {
      if ( !CryptBinaryToStringA(a3->pbCertEncoded, a3->cbCertEncoded, 1u, v8, &pcchString) )
        goto LABEL_10;
LABEL_23:
      *v10 = pcchString;
      *a4 = v8;
      goto LABEL_27;
    }
    goto LABEL_21;
  }
LABEL_10:
  LastError = GetLastError();
LABEL_25:
  SetLastError(LastError);
LABEL_26:
  LocalFree(v8);
  v11 = 0;
LABEL_27:
  if ( v9 )
    CertCloseStore(v9, 0);
  return v11;
}

```

## disassembly

```asm
0x180020f6c  push    rbp
0x180020f6e  push    rbx
0x180020f6f  push    rsi
0x180020f70  push    rdi
0x180020f71  push    r12
0x180020f73  push    r13
0x180020f75  push    r14
0x180020f77  push    r15
0x180020f79  mov     rbp, rsp
0x180020f7c  sub     rsp, 48h
0x180020f80  xor     eax, eax
0x180020f82  xorps   xmm0, xmm0
0x180020f85  mov     [rbp+arg_18], eax
0x180020f88  mov     r12, r9
0x180020f8b  mov     rdi, r8
0x180020f8e  mov     r13d, edx
0x180020f91  mov     ebx, eax
0x180020f93  mov     esi, eax
0x180020f95  movups  [rbp+pvSaveToPara], xmm0
0x180020f99  test    r9, r9
0x180020f9c  jz      loc_180021157
0x180020fa2  mov     r15, [rbp+arg_20]
0x180020fa6  test    r15, r15
0x180020fa9  jz      loc_180021157
0x180020faf  test    r8, r8
0x180020fb2  jz      loc_180021157
0x180020fb8  lea     r14d, [rax+1]
0x180020fbc  mov     [r9], rax
0x180020fbf  mov     [r15], eax
0x180020fc2  sub     ecx, r14d
0x180020fc5  jz      loc_18002111A
0x180020fcb  sub     ecx, 2
0x180020fce  jz      short loc_180021042
0x180020fd0  cmp     ecx, r14d
0x180020fd3  jnz     loc_180021157
0x180020fd9  mov     edx, [rdi+10h]; cbBinary
0x180020fdc  lea     rax, [rbp+arg_18]
0x180020fe0  mov     rcx, [rdi+8]; pbBinary
0x180020fe4  xor     r9d, r9d; pszString
0x180020fe7  mov     r8d, r14d; dwFlags
0x180020fea  mov     [rsp+48h+pcchString], rax; pcchString
0x180020fef  call    cs:__imp_CryptBinaryToStringA
0x180020ff5  test    eax, eax
0x180020ff7  jz      short loc_180021035
0x180020ff9  mov     edx, [rbp+arg_18]; uBytes
0x180020ffc  lea     ecx, [rsi+40h]; uFlags
0x180020fff  call    cs:__imp_LocalAlloc
0x180021005  mov     rbx, rax
0x180021008  test    rax, rax
0x18002100b  jz      loc_180021134
0x180021011  mov     edx, [rdi+10h]; cbBinary
0x180021014  lea     rax, [rbp+arg_18]
0x180021018  mov     rcx, [rdi+8]; pbBinary
0x18002101c  mov     r9, rbx; pszString
0x18002101f  mov     r8d, r14d; dwFlags
0x180021022  mov     [rsp+48h+pcchString], rax; pcchString
0x180021027  call    cs:__imp_CryptBinaryToStringA
0x18002102d  test    eax, eax
0x18002102f  jnz     loc_18002114B
0x180021035  call    cs:__imp_GetLastError
0x18002103b  mov     ecx, eax
0x18002103d  jmp     loc_18002115C
0x180021042  xor     r9d, r9d; dwFlags
0x180021045  mov     [rsp+48h+pcchString], rax; pvPara
0x18002104a  xor     r8d, r8d; hCryptProv
0x18002104d  mov     edx, 10001h; dwEncodingType
0x180021052  lea     ecx, [r9+2]; lpszStoreProvider
0x180021056  call    cs:__imp_CertOpenStore
0x18002105c  mov     rsi, rax
0x18002105f  test    rax, rax
0x180021062  jz      loc_180021162
0x180021068  xor     r9d, r9d; void **
0x18002106b  mov     rdx, rdi; pCertContext
0x18002106e  mov     rcx, rax; hCertStore
0x180021071  test    r13d, r13d
0x180021074  jnz     short loc_180021082
0x180021076  lea     r8d, [r9+3]; dwAddDisposition
0x18002107a  call    cs:__imp_CertAddCertificateContextToStore
0x180021080  jmp     short loc_180021093
0x180021082  mov     qword ptr [rsp+48h+dwFlags], rbx; struct _CERT_TRUST_STATUS *
0x180021087  xor     r8d, r8d; unsigned int
0x18002108a  mov     dword ptr [rsp+48h+pcchString], ebx; int
0x18002108e  call    ?AddChainToStore@@YAHPEAXPEBU_CERT_CONTEXT@@KPEAPEAXHPEAU_CERT_TRUST_STATUS@@@Z; AddChainToStore(void *,_CERT_CONTEXT const *,ulong,void * *,int,_CERT_TRUST_STATUS *)
0x180021093  test    eax, eax
0x180021095  jz      loc_180021162
0x18002109b  mov     edi, 2
0x1800210a0  mov     [rsp+48h+dwFlags], ebx; dwFlags
0x1800210a4  lea     rax, [rbp+pvSaveToPara]
0x1800210a8  mov     dword ptr [rbp+pvSaveToPara], ebx
0x1800210ab  mov     r13d, 10001h
0x1800210b1  mov     qword ptr [rbp+pvSaveToPara+8], rbx
0x1800210b5  mov     r9d, edi; dwSaveTo
0x1800210b8  mov     [rsp+48h+pcchString], rax; pvSaveToPara
0x1800210bd  mov     r8d, edi; dwSaveAs
0x1800210c0  mov     edx, r13d; dwEncodingType
0x1800210c3  mov     rcx, rsi; hCertStore
0x1800210c6  call    cs:__imp_CertSaveStore
0x1800210cc  test    eax, eax
0x1800210ce  jz      loc_180021162
0x1800210d4  mov     eax, dword ptr [rbp+pvSaveToPara]
0x1800210d7  lea     ecx, [rdi+3Eh]; uFlags
0x1800210da  mov     edx, eax; uBytes
0x1800210dc  mov     [rbp+arg_18], eax
0x1800210df  call    cs:__imp_LocalAlloc
0x1800210e5  mov     rbx, rax
0x1800210e8  test    rax, rax
0x1800210eb  jz      short loc_180021134
0x1800210ed  mov     qword ptr [rbp+pvSaveToPara+8], rax
0x1800210f1  mov     r9d, edi; dwSaveTo
0x1800210f4  lea     rax, [rbp+pvSaveToPara]
0x1800210f8  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180021100  mov     r8d, edi; dwSaveAs
0x180021103  mov     [rsp+48h+pcchString], rax; pvSaveToPara
0x180021108  mov     edx, r13d; dwEncodingType
0x18002110b  mov     rcx, rsi; hCertStore
0x18002110e  call    cs:__imp_CertSaveStore
0x180021114  test    eax, eax
0x180021116  jnz     short loc_18002114B
0x180021118  jmp     short loc_180021162
0x18002111a  mov     edx, [r8+10h]; uBytes
0x18002111e  mov     ecx, 40h ; '@'; uFlags
0x180021123  mov     [rbp+arg_18], edx
0x180021126  call    cs:__imp_LocalAlloc
0x18002112c  mov     rbx, rax
0x18002112f  test    rax, rax
0x180021132  jnz     short loc_18002113B
0x180021134  mov     ecx, 8007000Eh
0x180021139  jmp     short loc_18002115C
0x18002113b  mov     r8d, [rbp+arg_18]; Size
0x18002113f  mov     rcx, rax; void *
0x180021142  mov     rdx, [rdi+8]; Src
0x180021146  call    memcpy_0
0x18002114b  mov     eax, [rbp+arg_18]
0x18002114e  mov     [r15], eax
0x180021151  mov     [r12], rbx
0x180021155  jmp     short loc_18002116E
0x180021157  mov     ecx, 80070057h; dwErrCode
0x18002115c  call    cs:__imp_SetLastError
0x180021162  mov     rcx, rbx; hMem
0x180021165  call    cs:__imp_LocalFree
0x18002116b  xor     r14d, r14d
0x18002116e  test    rsi, rsi
0x180021171  jz      short loc_18002117E
0x180021173  xor     edx, edx; dwFlags
0x180021175  mov     rcx, rsi; hCertStore
0x180021178  call    cs:__imp_CertCloseStore
0x18002117e  mov     eax, r14d
0x180021181  add     rsp, 48h
0x180021185  pop     r15
0x180021187  pop     r14
0x180021189  pop     r13
0x18002118b  pop     r12
0x18002118d  pop     rdi
0x18002118e  pop     rsi
0x18002118f  pop     rbx
0x180021190  pop     rbp
0x180021191  retn
```
