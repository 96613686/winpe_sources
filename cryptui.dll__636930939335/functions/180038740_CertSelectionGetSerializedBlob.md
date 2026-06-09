# CertSelectionGetSerializedBlob

- ea: `0x180038740`
- end: `0x180038848`
- name: `CertSelectionGetSerializedBlob`
- size: `264`
- prototype: `HRESULT __stdcall(PCERT_SELECTUI_INPUT pcsi, void **ppOutBuffer, ULONG *pulOutBufferSize)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800385c4`
- `0x180038740`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x1800387c9`
- `CRYPT32!CertOpenStore` at `0x1800387c9`
- `CRYPT32!CertCloseStore` at `0x18003882c`
- `CRYPT32!CertCloseStore` at `0x18003882c`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800387fd`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800387fd`

## pseudocode

```c
HRESULT __stdcall CertSelectionGetSerializedBlob(
        PCERT_SELECTUI_INPUT pcsi,
        void **ppOutBuffer,
        ULONG *pulOutBufferSize)
{
  HCERTSTORE i; // rdi
  HCERTSTORE hStore; // rcx
  HRESULT v8; // ebx
  DWORD cChain; // r15d
  __int64 v10; // rbp

  if ( pcsi && ppOutBuffer && pulOutBufferSize && (!pcsi->hStore || !pcsi->prgpChain) )
  {
    i = 0;
    *ppOutBuffer = 0;
    *pulOutBufferSize = 0;
    hStore = pcsi->hStore;
    if ( hStore )
    {
      v8 = SerializeStore(hStore, 0, ppOutBuffer, pulOutBufferSize);
      if ( v8 )
        return v8;
    }
    else if ( pcsi->prgpChain )
    {
      cChain = pcsi->cChain;
      v10 = 0;
      for ( i = CertOpenStore("Memory", 0, 0, 0, 0); (unsigned int)v10 < cChain; v10 = (unsigned int)(v10 + 1) )
        CertAddCertificateContextToStore(i, (*(*pcsi->prgpChain[v10]->rgpChain)->rgpElement)->pCertContext, 4u, 0);
      v8 = SerializeStore(i, 0, ppOutBuffer, pulOutBufferSize);
      if ( v8 )
        goto LABEL_14;
    }
    v8 = 0;
LABEL_14:
    if ( i )
      CertCloseStore(i, 0);
    return v8;
  }
  return -2147024809;
}

```

## disassembly

```asm
0x180038740  push    rbx
0x180038742  push    rbp
0x180038743  push    rsi
0x180038744  push    rdi
0x180038745  push    r14
0x180038747  push    r15
0x180038749  sub     rsp, 38h
0x18003874d  mov     rsi, r8
0x180038750  mov     r14, rdx
0x180038753  mov     rbx, rcx
0x180038756  test    rcx, rcx
0x180038759  jz      loc_180038836
0x18003875f  test    rdx, rdx
0x180038762  jz      loc_180038836
0x180038768  test    r8, r8
0x18003876b  jz      loc_180038836
0x180038771  cmp     qword ptr [rcx], 0
0x180038775  jz      short loc_180038782
0x180038777  cmp     qword ptr [rcx+8], 0
0x18003877c  jnz     loc_180038836
0x180038782  xor     edi, edi
0x180038784  mov     [rdx], rdi
0x180038787  mov     [r8], edi
0x18003878a  mov     rcx, [rcx]; hCertStore
0x18003878d  test    rcx, rcx
0x180038790  jz      short loc_1800387AB
0x180038792  mov     r9, rsi; unsigned int *
0x180038795  mov     r8, r14; void **
0x180038798  xor     edx, edx; unsigned int
0x18003879a  call    ?SerializeStore@@YAJPEAXKPEAPEAXPEAK@Z; SerializeStore(void *,ulong,void * *,ulong *)
0x18003879f  mov     ebx, eax
0x1800387a1  test    eax, eax
0x1800387a3  jnz     loc_180038832
0x1800387a9  jmp     short loc_180038820
0x1800387ab  cmp     [rbx+8], rdi
0x1800387af  jz      short loc_180038820
0x1800387b1  mov     r15d, [rbx+10h]
0x1800387b5  lea     rcx, aMemory; "Memory"
0x1800387bc  xor     r9d, r9d; dwFlags
0x1800387bf  mov     [rsp+68h+pvPara], rdi; pvPara
0x1800387c4  xor     r8d, r8d; hCryptProv
0x1800387c7  xor     edx, edx; dwEncodingType
0x1800387c9  call    cs:__imp_CertOpenStore
0x1800387cf  xor     ebp, ebp
0x1800387d1  mov     rdi, rax
0x1800387d4  test    r15d, r15d
0x1800387d7  jz      short loc_18003880A
0x1800387d9  mov     rcx, [rbx+8]
0x1800387dd  xor     r9d, r9d; ppStoreContext
0x1800387e0  mov     rdx, [rcx+rbp*8]
0x1800387e4  lea     r8d, [r9+4]; dwAddDisposition
0x1800387e8  mov     rcx, [rdx+10h]
0x1800387ec  mov     rdx, [rcx]
0x1800387ef  mov     rcx, [rdx+10h]
0x1800387f3  mov     rdx, [rcx]
0x1800387f6  mov     rcx, rdi; hCertStore
0x1800387f9  mov     rdx, [rdx+8]; pCertContext
0x1800387fd  call    cs:__imp_CertAddCertificateContextToStore
0x180038803  inc     ebp
0x180038805  cmp     ebp, r15d
0x180038808  jb      short loc_1800387D9
0x18003880a  mov     r9, rsi; unsigned int *
0x18003880d  mov     r8, r14; void **
0x180038810  xor     edx, edx; unsigned int
0x180038812  mov     rcx, rdi; hCertStore
0x180038815  call    ?SerializeStore@@YAJPEAXKPEAPEAXPEAK@Z; SerializeStore(void *,ulong,void * *,ulong *)
0x18003881a  mov     ebx, eax
0x18003881c  test    eax, eax
0x18003881e  jnz     short loc_180038822
0x180038820  xor     ebx, ebx
0x180038822  test    rdi, rdi
0x180038825  jz      short loc_180038832
0x180038827  xor     edx, edx; dwFlags
0x180038829  mov     rcx, rdi; hCertStore
0x18003882c  call    cs:__imp_CertCloseStore
0x180038832  mov     eax, ebx
0x180038834  jmp     short loc_18003883B
0x180038836  mov     eax, 80070057h
0x18003883b  add     rsp, 38h
0x18003883f  pop     r15
0x180038841  pop     r14
0x180038843  pop     rdi
0x180038844  pop     rsi
0x180038845  pop     rbp
0x180038846  pop     rbx
0x180038847  retn
```
