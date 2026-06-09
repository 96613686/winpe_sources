# _InitEncodedCertIncludingSigners

- ea: `0x18005d024`
- end: `0x18005d1cf`
- name: `_InitEncodedCertIncludingSigners`
- size: `427`
- prototype: `__int64 __usercall@<rax>(HCERTSTORE hCertStore@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800598e0`

## callees

- `0x18005cce4`
- `0x18005d024`
- `0x1800cc996`

## import_xrefs

- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18005d160`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18005d160`
- `CRYPT32!CertAddStoreToCollection` at `0x18005d0e6`
- `CRYPT32!CertAddStoreToCollection` at `0x18005d122`
- `CRYPT32!CertAddStoreToCollection` at `0x18005d0e6`
- `CRYPT32!CertAddStoreToCollection` at `0x18005d122`
- `CRYPT32!CertOpenStore` at `0x18005d0c8`
- `CRYPT32!CertOpenStore` at `0x18005d108`
- `CRYPT32!CertOpenStore` at `0x18005d0c8`
- `CRYPT32!CertOpenStore` at `0x18005d108`
- `CRYPT32!CertFreeCertificateContext` at `0x18005d0a1`
- `CRYPT32!CertFreeCertificateContext` at `0x18005d0a1`
- `CRYPT32!CertCloseStore` at `0x18005d12f`
- `CRYPT32!CertCloseStore` at `0x18005d1b2`
- `CRYPT32!CertCloseStore` at `0x18005d12f`
- `CRYPT32!CertCloseStore` at `0x18005d1b2`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18005d070`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18005d070`

## pseudocode

```c
__int64 __fastcall InitEncodedCertIncludingSigners(
        HCERTSTORE hCertStore,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  void *v7; // rdi
  __int64 v8; // rsi
  PCCERT_CONTEXT v11; // rbx
  __int64 v12; // r15
  DWORD *v13; // r12
  DWORD *v14; // r14
  unsigned int v15; // eax
  HCERTSTORE v16; // rax
  HCERTSTORE v17; // rax
  void *v18; // r14
  BOOL v19; // ebx
  unsigned int inited; // ebx
  __int64 v22; // [rsp+80h] [rbp+18h]

  v22 = a3;
  v7 = 0;
  v8 = 0;
  if ( a2 )
  {
    while ( 2 )
    {
      v11 = 0;
      v12 = *(_QWORD *)(96 * v8 + a3 + 8);
      v13 = (DWORD *)(v12 + 16);
      v14 = (DWORD *)(v12 + 16);
      while ( 1 )
      {
        v11 = CertEnumCertificatesInStore(hCertStore, v11);
        if ( !v11 )
          break;
        v14 = (DWORD *)(v12 + 16);
        v15 = *(_DWORD *)(v12 + 16);
        if ( v15 == v11->cbCertEncoded && !memcmp_0(*(const void **)(v12 + 8), v11->pbCertEncoded, v15) )
        {
          CertFreeCertificateContext(v11);
          goto LABEL_15;
        }
      }
      if ( v7 )
      {
        v13 = v14;
      }
      else
      {
        v16 = CertOpenStore((LPCSTR)0xB, 1u, 0, 0, 0);
        v7 = v16;
        if ( !v16 )
          break;
        if ( !CertAddStoreToCollection(v16, hCertStore, 0, 0) )
          break;
        v17 = CertOpenStore((LPCSTR)2, 1u, 0, 0, 0);
        v18 = v17;
        if ( !v17 )
          break;
        v19 = CertAddStoreToCollection(v7, v17, 1u, 1u);
        CertCloseStore(v18, 0);
        if ( !v19 )
          break;
        hCertStore = v7;
      }
      CertAddEncodedCertificateToStore(v7, *(_DWORD *)v12, *(const BYTE **)(v12 + 8), *v13, 4u, 0);
LABEL_15:
      a3 = v22;
      v8 = (unsigned int)(v8 + 1);
      if ( (unsigned int)v8 < a2 )
        continue;
      break;
    }
  }
  inited = InitEncodedCert(hCertStore, a7);
  if ( v7 )
    CertCloseStore(v7, 0);
  return inited;
}

```

## disassembly

```asm
0x18005d024  mov     [rsp+arg_0], rbx
0x18005d029  mov     [rsp+arg_18], r9
0x18005d02e  mov     [rsp+arg_10], r8
0x18005d033  push    rbp
0x18005d034  push    rsi
0x18005d035  push    rdi
0x18005d036  push    r12
0x18005d038  push    r13
0x18005d03a  push    r14
0x18005d03c  push    r15
0x18005d03e  sub     rsp, 30h
0x18005d042  xor     edi, edi
0x18005d044  xor     esi, esi
0x18005d046  mov     r13d, edx
0x18005d049  mov     rbp, rcx
0x18005d04c  test    edx, edx
0x18005d04e  jz      loc_18005D179
0x18005d054  lea     rdx, [rsi+rsi*2]
0x18005d058  shl     rdx, 5
0x18005d05c  xor     ebx, ebx
0x18005d05e  mov     r15, [rdx+r8+8]
0x18005d063  lea     r12, [r15+10h]
0x18005d067  mov     r14, r12
0x18005d06a  mov     rdx, rbx; pPrevCertContext
0x18005d06d  mov     rcx, rbp; hCertStore
0x18005d070  call    cs:__imp_CertEnumCertificatesInStore
0x18005d076  mov     rbx, rax
0x18005d079  test    rax, rax
0x18005d07c  jz      short loc_18005D0AC
0x18005d07e  lea     r14, [r15+10h]
0x18005d082  mov     eax, [r14]
0x18005d085  cmp     eax, [rbx+10h]
0x18005d088  jnz     short loc_18005D06A
0x18005d08a  mov     rdx, [rbx+8]; Buf2
0x18005d08e  mov     r8d, eax; Size
0x18005d091  mov     rcx, [r15+8]; Buf1
0x18005d095  call    memcmp_0
0x18005d09a  test    eax, eax
0x18005d09c  jnz     short loc_18005D06A
0x18005d09e  mov     rcx, rbx; pCertContext
0x18005d0a1  call    cs:__imp_CertFreeCertificateContext
0x18005d0a7  jmp     loc_18005D166
0x18005d0ac  test    rdi, rdi
0x18005d0af  jnz     loc_18005D13E
0x18005d0b5  lea     ebx, [rdi+1]
0x18005d0b8  mov     [rsp+68h+pvPara], rdi; pvPara
0x18005d0bd  mov     edx, ebx; dwEncodingType
0x18005d0bf  lea     ecx, [rdi+0Bh]; lpszStoreProvider
0x18005d0c2  xor     r9d, r9d; dwFlags
0x18005d0c5  xor     r8d, r8d; hCryptProv
0x18005d0c8  call    cs:__imp_CertOpenStore
0x18005d0ce  mov     rdi, rax
0x18005d0d1  test    rax, rax
0x18005d0d4  jz      loc_18005D179
0x18005d0da  xor     r9d, r9d; dwPriority
0x18005d0dd  xor     r8d, r8d; dwUpdateFlags
0x18005d0e0  mov     rdx, rbp; hSiblingStore
0x18005d0e3  mov     rcx, rax; hCollectionStore
0x18005d0e6  call    cs:__imp_CertAddStoreToCollection
0x18005d0ec  test    eax, eax
0x18005d0ee  jz      loc_18005D179
0x18005d0f4  xor     r9d, r9d; dwFlags
0x18005d0f7  mov     [rsp+68h+pvPara], 0; pvPara
0x18005d100  xor     r8d, r8d; hCryptProv
0x18005d103  lea     ecx, [rbx+1]; lpszStoreProvider
0x18005d106  mov     edx, ebx; dwEncodingType
0x18005d108  call    cs:__imp_CertOpenStore
0x18005d10e  mov     r14, rax
0x18005d111  test    rax, rax
0x18005d114  jz      short loc_18005D179
0x18005d116  mov     r9d, ebx; dwPriority
0x18005d119  mov     r8d, ebx; dwUpdateFlags
0x18005d11c  mov     rdx, rax; hSiblingStore
0x18005d11f  mov     rcx, rdi; hCollectionStore
0x18005d122  call    cs:__imp_CertAddStoreToCollection
0x18005d128  xor     edx, edx; dwFlags
0x18005d12a  mov     rcx, r14; hCertStore
0x18005d12d  mov     ebx, eax
0x18005d12f  call    cs:__imp_CertCloseStore
0x18005d135  test    ebx, ebx
0x18005d137  jz      short loc_18005D179
0x18005d139  mov     rbp, rdi
0x18005d13c  jmp     short loc_18005D141
0x18005d13e  mov     r12, r14
0x18005d141  mov     r9d, [r12]; cbCertEncoded
0x18005d145  mov     rcx, rdi; hCertStore
0x18005d148  mov     r8, [r15+8]; pbCertEncoded
0x18005d14c  mov     edx, [r15]; dwCertEncodingType
0x18005d14f  mov     [rsp+68h+ppCertContext], 0; ppCertContext
0x18005d158  mov     dword ptr [rsp+68h+pvPara], 4; dwAddDisposition
0x18005d160  call    cs:__imp_CertAddEncodedCertificateToStore
0x18005d166  mov     r8, [rsp+68h+arg_10]
0x18005d16e  inc     esi
0x18005d170  cmp     esi, r13d
0x18005d173  jb      loc_18005D054
0x18005d179  mov     rax, [rsp+68h+arg_30]
0x18005d181  mov     rcx, rbp; hCertStore
0x18005d184  mov     r9, [rsp+68h+arg_28]
0x18005d18c  mov     r8, [rsp+68h+arg_20]
0x18005d194  mov     rdx, [rsp+68h+arg_18]
0x18005d19c  mov     [rsp+68h+pvPara], rax; __int64
0x18005d1a1  call    _InitEncodedCert
0x18005d1a6  mov     ebx, eax
0x18005d1a8  test    rdi, rdi
0x18005d1ab  jz      short loc_18005D1B8
0x18005d1ad  xor     edx, edx; dwFlags
0x18005d1af  mov     rcx, rdi; hCertStore
0x18005d1b2  call    cs:__imp_CertCloseStore
0x18005d1b8  mov     eax, ebx
0x18005d1ba  mov     rbx, [rsp+68h+arg_0]
0x18005d1bf  add     rsp, 30h
0x18005d1c3  pop     r15
0x18005d1c5  pop     r14
0x18005d1c7  pop     r13
0x18005d1c9  pop     r12
0x18005d1cb  pop     rdi
0x18005d1cc  pop     rsi
0x18005d1cd  pop     rbp
0x18005d1ce  retn
```
