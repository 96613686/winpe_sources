# OpenAllStore(ulong,void * * const,void * *,void * *,void * *,void * *)

- ea: `0x18005b8b8`
- end: `0x18005ba29`
- name: `?OpenAllStore@@YAPEAXKQEAPEAXPEAPEAX111@Z`
- size: `369`
- prototype: `void *__fastcall(unsigned int, void **const, void **, void **, void **, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18005be40`

## callees

- `0x18005b8b8`

## import_xrefs

- `CRYPT32!CertAddStoreToCollection` at `0x18005b911`
- `CRYPT32!CertAddStoreToCollection` at `0x18005b958`
- `CRYPT32!CertAddStoreToCollection` at `0x18005b998`
- `CRYPT32!CertAddStoreToCollection` at `0x18005b9d1`
- `CRYPT32!CertAddStoreToCollection` at `0x18005ba11`
- `CRYPT32!CertAddStoreToCollection` at `0x18005b911`
- `CRYPT32!CertAddStoreToCollection` at `0x18005b958`
- `CRYPT32!CertAddStoreToCollection` at `0x18005b998`
- `CRYPT32!CertAddStoreToCollection` at `0x18005b9d1`
- `CRYPT32!CertAddStoreToCollection` at `0x18005ba11`
- `CRYPT32!CertOpenStore` at `0x18005b8ec`
- `CRYPT32!CertOpenStore` at `0x18005b93e`
- `CRYPT32!CertOpenStore` at `0x18005b976`
- `CRYPT32!CertOpenStore` at `0x18005b9b6`
- `CRYPT32!CertOpenStore` at `0x18005b9ef`
- `CRYPT32!CertOpenStore` at `0x18005b8ec`
- `CRYPT32!CertOpenStore` at `0x18005b93e`
- `CRYPT32!CertOpenStore` at `0x18005b976`
- `CRYPT32!CertOpenStore` at `0x18005b9b6`
- `CRYPT32!CertOpenStore` at `0x18005b9ef`

## pseudocode

```c
HCERTSTORE __fastcall OpenAllStore(unsigned int a1, void **const a2, void **a3, void **a4, void **a5, void **a6)
{
  HCERTSTORE result; // rax
  void *v11; // rbx
  __int64 i; // rdi
  HCERTSTORE v13; // rax
  HCERTSTORE v14; // rax
  HCERTSTORE v15; // rax
  HCERTSTORE v16; // rax

  result = CertOpenStore((LPCSTR)0xB, 1u, 0, 0, 0);
  v11 = result;
  if ( result )
  {
    for ( i = 0; (unsigned int)i < a1; i = (unsigned int)(i + 1) )
      CertAddStoreToCollection(v11, a2[i], 0, 0);
    v13 = CertOpenStore((LPCSTR)9, 1u, 0, 0x10000u, "AddressBook");
    *a3 = v13;
    if ( v13 )
      CertAddStoreToCollection(v11, v13, 0, 0);
    v14 = CertOpenStore((LPCSTR)9, 1u, 0, 0x10000u, "My");
    *a5 = v14;
    if ( v14 )
      CertAddStoreToCollection(v11, v14, 0, 0);
    v15 = CertOpenStore((LPCSTR)9, 1u, 0, 0x10000u, "CA");
    *a4 = v15;
    if ( v15 )
      CertAddStoreToCollection(v11, v15, 0, 0);
    v16 = CertOpenStore((LPCSTR)9, 1u, 0, 0x10000u, "Root");
    *a6 = v16;
    if ( v16 )
      CertAddStoreToCollection(v11, v16, 0, 0);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x18005b8b8  push    rbx
0x18005b8ba  push    rbp
0x18005b8bb  push    rsi
0x18005b8bc  push    rdi
0x18005b8bd  push    r12
0x18005b8bf  push    r14
0x18005b8c1  push    r15
0x18005b8c3  sub     rsp, 30h
0x18005b8c7  mov     rbp, r9
0x18005b8ca  mov     [rsp+68h+pvPara], 0; pvPara
0x18005b8d3  xor     r9d, r9d; dwFlags
0x18005b8d6  mov     r15, r8
0x18005b8d9  mov     r14, rdx
0x18005b8dc  mov     esi, ecx
0x18005b8de  xor     r8d, r8d; hCryptProv
0x18005b8e1  lea     r12d, [r9+1]
0x18005b8e5  mov     edx, r12d; dwEncodingType
0x18005b8e8  lea     ecx, [r9+0Bh]; lpszStoreProvider
0x18005b8ec  call    cs:__imp_CertOpenStore
0x18005b8f2  mov     rbx, rax
0x18005b8f5  test    rax, rax
0x18005b8f8  jz      loc_18005BA1A
0x18005b8fe  xor     edi, edi
0x18005b900  test    esi, esi
0x18005b902  jz      short loc_18005B91E
0x18005b904  mov     rdx, [r14+rdi*8]; hSiblingStore
0x18005b908  xor     r9d, r9d; dwPriority
0x18005b90b  xor     r8d, r8d; dwUpdateFlags
0x18005b90e  mov     rcx, rbx; hCollectionStore
0x18005b911  call    cs:__imp_CertAddStoreToCollection
0x18005b917  add     edi, r12d
0x18005b91a  cmp     edi, esi
0x18005b91c  jb      short loc_18005B904
0x18005b91e  xor     r8d, r8d; hCryptProv
0x18005b921  lea     rax, aAddressbook_0; "AddressBook"
0x18005b928  mov     edi, 10000h
0x18005b92d  mov     [rsp+68h+pvPara], rax; pvPara
0x18005b932  mov     r9d, edi; dwFlags
0x18005b935  mov     edx, r12d; dwEncodingType
0x18005b938  lea     esi, [r8+9]
0x18005b93c  mov     ecx, esi; lpszStoreProvider
0x18005b93e  call    cs:__imp_CertOpenStore
0x18005b944  mov     [r15], rax
0x18005b947  test    rax, rax
0x18005b94a  jz      short loc_18005B95E
0x18005b94c  xor     r9d, r9d; dwPriority
0x18005b94f  xor     r8d, r8d; dwUpdateFlags
0x18005b952  mov     rdx, rax; hSiblingStore
0x18005b955  mov     rcx, rbx; hCollectionStore
0x18005b958  call    cs:__imp_CertAddStoreToCollection
0x18005b95e  lea     rax, aMy_0; "My"
0x18005b965  mov     r9d, edi; dwFlags
0x18005b968  xor     r8d, r8d; hCryptProv
0x18005b96b  mov     [rsp+68h+pvPara], rax; pvPara
0x18005b970  mov     edx, r12d; dwEncodingType
0x18005b973  mov     rcx, rsi; lpszStoreProvider
0x18005b976  call    cs:__imp_CertOpenStore
0x18005b97c  mov     rcx, [rsp+68h+arg_20]
0x18005b984  mov     [rcx], rax
0x18005b987  test    rax, rax
0x18005b98a  jz      short loc_18005B99E
0x18005b98c  xor     r9d, r9d; dwPriority
0x18005b98f  xor     r8d, r8d; dwUpdateFlags
0x18005b992  mov     rdx, rax; hSiblingStore
0x18005b995  mov     rcx, rbx; hCollectionStore
0x18005b998  call    cs:__imp_CertAddStoreToCollection
0x18005b99e  lea     rax, aCa; "CA"
0x18005b9a5  mov     r9d, edi; dwFlags
0x18005b9a8  xor     r8d, r8d; hCryptProv
0x18005b9ab  mov     [rsp+68h+pvPara], rax; pvPara
0x18005b9b0  mov     edx, r12d; dwEncodingType
0x18005b9b3  mov     rcx, rsi; lpszStoreProvider
0x18005b9b6  call    cs:__imp_CertOpenStore
0x18005b9bc  mov     [rbp+0], rax
0x18005b9c0  test    rax, rax
0x18005b9c3  jz      short loc_18005B9D7
0x18005b9c5  xor     r9d, r9d; dwPriority
0x18005b9c8  xor     r8d, r8d; dwUpdateFlags
0x18005b9cb  mov     rdx, rax; hSiblingStore
0x18005b9ce  mov     rcx, rbx; hCollectionStore
0x18005b9d1  call    cs:__imp_CertAddStoreToCollection
0x18005b9d7  lea     rax, aRoot; "Root"
0x18005b9de  mov     r9d, edi; dwFlags
0x18005b9e1  xor     r8d, r8d; hCryptProv
0x18005b9e4  mov     [rsp+68h+pvPara], rax; pvPara
0x18005b9e9  mov     edx, r12d; dwEncodingType
0x18005b9ec  mov     rcx, rsi; lpszStoreProvider
0x18005b9ef  call    cs:__imp_CertOpenStore
0x18005b9f5  mov     rcx, [rsp+68h+arg_28]
0x18005b9fd  mov     [rcx], rax
0x18005ba00  test    rax, rax
0x18005ba03  jz      short loc_18005BA17
0x18005ba05  xor     r9d, r9d; dwPriority
0x18005ba08  xor     r8d, r8d; dwUpdateFlags
0x18005ba0b  mov     rdx, rax; hSiblingStore
0x18005ba0e  mov     rcx, rbx; hCollectionStore
0x18005ba11  call    cs:__imp_CertAddStoreToCollection
0x18005ba17  mov     rax, rbx
0x18005ba1a  add     rsp, 30h
0x18005ba1e  pop     r15
0x18005ba20  pop     r14
0x18005ba22  pop     r12
0x18005ba24  pop     rdi
0x18005ba25  pop     rsi
0x18005ba26  pop     rbp
0x18005ba27  pop     rbx
0x18005ba28  retn
```
