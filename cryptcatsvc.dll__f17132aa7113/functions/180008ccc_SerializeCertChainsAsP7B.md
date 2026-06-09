# SerializeCertChainsAsP7B

- ea: `0x180008ccc`
- end: `0x180008ee2`
- name: `SerializeCertChainsAsP7B`
- size: `534`
- prototype: `__int64 __fastcall(__int64, int *, HLOCAL *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010b3c`

## callees

- `0x180008800`
- `0x180008ccc`
- `0x18000be40`

## import_xrefs

- `CRYPT32!CertAddCertificateContextToStore` at `0x180008e3f`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180008e3f`
- `CRYPT32!CertSaveStore` at `0x180008d60`
- `CRYPT32!CertSaveStore` at `0x180008da7`
- `CRYPT32!CertSaveStore` at `0x180008d60`
- `CRYPT32!CertSaveStore` at `0x180008da7`
- `CRYPT32!CertCloseStore` at `0x180008dde`
- `CRYPT32!CertCloseStore` at `0x180008dde`
- `CRYPT32!CertOpenStore` at `0x180008d1b`
- `CRYPT32!CertOpenStore` at `0x180008d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008d77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008dc2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008d77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008dc2`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180008e70`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180008e70`

## pseudocode

```c
__int64 __fastcall SerializeCertChainsAsP7B(__int64 a1, int *a2, HLOCAL *a3)
{
  HLOCAL v3; // rdi
  __int64 v4; // rbp
  HCERTSTORE v8; // r14
  int v9; // ebx
  DWORD LastError; // ebx
  int v12; // esi
  __int64 v13; // rcx
  unsigned int i; // esi
  __int128 pvSaveToPara; // [rsp+30h] [rbp-58h] BYREF

  v3 = *a3;
  v4 = (unsigned int)*a2;
  pvSaveToPara = 0;
  v8 = CertOpenStore((LPCSTR)2, 0x10001u, 0, 0x80u, 0);
  if ( v8 )
  {
    v9 = *(_DWORD *)(**(_QWORD **)(a1 + 16) + 12LL);
    while ( v9 )
    {
      if ( !CertAddCertificateContextToStore(
              v8,
              *(PCCERT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(**(_QWORD **)(a1 + 16) + 16LL) + 8LL * (unsigned int)--v9)
                                + 8LL),
              4u,
              0) )
        goto LABEL_17;
    }
    if ( !CertSaveStore(v8, 0x10001u, 2u, 2u, &pvSaveToPara, 0) )
      goto LABEL_17;
    *((_QWORD *)&pvSaveToPara + 1) = LocalAlloc(0x40u, (unsigned int)pvSaveToPara);
    if ( !*((_QWORD *)&pvSaveToPara + 1) )
    {
LABEL_9:
      LastError = 14;
      goto LABEL_10;
    }
    if ( CertSaveStore(v8, 0x10001u, 2u, 2u, &pvSaveToPara, 0) )
    {
      if ( (_DWORD)v4 )
      {
        v12 = v4 + 1;
        v3 = LocalReAlloc(v3, 16LL * (unsigned int)(v4 + 1), 0x42u);
        if ( !v3 )
          goto LABEL_9;
      }
      else
      {
        v3 = LocalAlloc(0x40u, 0x10u);
        if ( !v3 )
          goto LABEL_9;
        v12 = 1;
      }
      v13 = 2 * v4;
      LastError = 0;
      LODWORD(v4) = v12;
      *((_DWORD *)v3 + 2 * v13) = pvSaveToPara;
      *((_QWORD *)v3 + v13 + 1) = *((_QWORD *)&pvSaveToPara + 1);
      *a2 = v12;
      *a3 = v3;
      v3 = 0;
      *((_QWORD *)&pvSaveToPara + 1) = 0;
    }
    else
    {
LABEL_17:
      LastError = GetLastError();
    }
LABEL_10:
    CertCloseStore(v8, 0);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( v3 )
  {
    for ( i = 0; i < (unsigned int)v4; ++i )
      MIDL_user_free(*((void **)v3 + 2 * i + 1));
    MIDL_user_free(v3);
  }
  if ( *((_QWORD *)&pvSaveToPara + 1) )
    MIDL_user_free(*((void **)&pvSaveToPara + 1));
  return LastError;
}

```

## disassembly

```asm
0x180008ccc  push    rbx
0x180008cce  push    rbp
0x180008ccf  push    rsi
0x180008cd0  push    rdi
0x180008cd1  push    r12
0x180008cd3  push    r14
0x180008cd5  push    r15
0x180008cd7  sub     rsp, 50h
0x180008cdb  mov     rax, cs:__security_cookie
0x180008ce2  xor     rax, rsp
0x180008ce5  mov     [rsp+88h+var_48], rax
0x180008cea  mov     rdi, [r8]
0x180008ced  mov     r9d, 80h; dwFlags
0x180008cf3  mov     ebp, [rdx]
0x180008cf5  mov     r12, r8
0x180008cf8  mov     r15, rdx
0x180008cfb  mov     [rsp+88h+pvPara], 0; pvPara
0x180008d04  mov     rsi, rcx
0x180008d07  xorps   xmm0, xmm0
0x180008d0a  lea     ecx, [r9-7Eh]; lpszStoreProvider
0x180008d0e  xor     r8d, r8d; hCryptProv
0x180008d11  mov     edx, 10001h; dwEncodingType
0x180008d16  movups  [rsp+88h+pvSaveToPara], xmm0
0x180008d1b  call    cs:__imp_CertOpenStore
0x180008d21  mov     r14, rax
0x180008d24  test    rax, rax
0x180008d27  jz      loc_180008E19
0x180008d2d  mov     rax, [rsi+10h]
0x180008d31  mov     rcx, [rax]
0x180008d34  mov     ebx, [rcx+0Ch]
0x180008d37  mov     rcx, r14; hCertStore
0x180008d3a  test    ebx, ebx
0x180008d3c  jnz     loc_180008E23
0x180008d42  mov     [rsp+88h+dwFlags], ebx; dwFlags
0x180008d46  lea     rax, [rsp+88h+pvSaveToPara]
0x180008d4b  mov     ebx, 2
0x180008d50  mov     [rsp+88h+pvPara], rax; pvSaveToPara
0x180008d55  mov     r9d, ebx; dwSaveTo
0x180008d58  mov     r8d, ebx; dwSaveAs
0x180008d5b  mov     edx, 10001h; dwEncodingType
0x180008d60  call    cs:__imp_CertSaveStore
0x180008d66  test    eax, eax
0x180008d68  jz      loc_180008E4D
0x180008d6e  mov     edx, dword ptr [rsp+88h+pvSaveToPara]; uBytes
0x180008d72  lea     esi, [rbx+3Eh]
0x180008d75  mov     ecx, esi; uFlags
0x180008d77  call    cs:__imp_LocalAlloc
0x180008d7d  mov     qword ptr [rsp+88h+pvSaveToPara+8], rax
0x180008d82  test    rax, rax
0x180008d85  jz      short loc_180008DD4
0x180008d87  lea     rax, [rsp+88h+pvSaveToPara]
0x180008d8c  mov     [rsp+88h+dwFlags], 0; dwFlags
0x180008d94  mov     r9d, ebx; dwSaveTo
0x180008d97  mov     [rsp+88h+pvPara], rax; pvSaveToPara
0x180008d9c  mov     r8d, ebx; dwSaveAs
0x180008d9f  mov     edx, 10001h; dwEncodingType
0x180008da4  mov     rcx, r14; hCertStore
0x180008da7  call    cs:__imp_CertSaveStore
0x180008dad  test    eax, eax
0x180008daf  jz      loc_180008E4D
0x180008db5  test    ebp, ebp
0x180008db7  jnz     loc_180008E5E
0x180008dbd  lea     edx, [rbx+0Eh]; uBytes
0x180008dc0  mov     ecx, esi; uFlags
0x180008dc2  call    cs:__imp_LocalAlloc
0x180008dc8  mov     rdi, rax
0x180008dcb  test    rax, rax
0x180008dce  jnz     loc_180008E57
0x180008dd4  mov     ebx, 0Eh
0x180008dd9  xor     edx, edx; dwFlags
0x180008ddb  mov     rcx, r14; hCertStore
0x180008dde  call    cs:__imp_CertCloseStore
0x180008de4  test    rdi, rdi
0x180008de7  jnz     loc_180008EB0
0x180008ded  mov     rcx, qword ptr [rsp+88h+pvSaveToPara+8]; void *
0x180008df2  test    rcx, rcx
0x180008df5  jnz     loc_180008ED8
0x180008dfb  mov     eax, ebx
0x180008dfd  mov     rcx, [rsp+88h+var_48]
0x180008e02  xor     rcx, rsp; StackCookie
0x180008e05  call    __security_check_cookie
0x180008e0a  add     rsp, 50h
0x180008e0e  pop     r15
0x180008e10  pop     r14
0x180008e12  pop     r12
0x180008e14  pop     rdi
0x180008e15  pop     rsi
0x180008e16  pop     rbp
0x180008e17  pop     rbx
0x180008e18  retn
0x180008e19  call    cs:__imp_GetLastError
0x180008e1f  mov     ebx, eax
0x180008e21  jmp     short loc_180008DE4
0x180008e23  mov     rax, [rsi+10h]
0x180008e27  xor     r9d, r9d; ppStoreContext
0x180008e2a  dec     ebx
0x180008e2c  mov     rax, [rax]
0x180008e2f  lea     r8d, [r9+4]; dwAddDisposition
0x180008e33  mov     rax, [rax+10h]
0x180008e37  mov     rdx, [rax+rbx*8]
0x180008e3b  mov     rdx, [rdx+8]; pCertContext
0x180008e3f  call    cs:__imp_CertAddCertificateContextToStore
0x180008e45  test    eax, eax
0x180008e47  jnz     loc_180008D37
0x180008e4d  call    cs:__imp_GetLastError
0x180008e53  mov     ebx, eax
0x180008e55  jmp     short loc_180008DD9
0x180008e57  mov     esi, 1
0x180008e5c  jmp     short loc_180008E82
0x180008e5e  lea     esi, [rbp+1]
0x180008e61  mov     r8d, 42h ; 'B'; uFlags
0x180008e67  mov     edx, esi
0x180008e69  mov     rcx, rdi; hMem
0x180008e6c  shl     rdx, 4; uBytes
0x180008e70  call    cs:__imp_LocalReAlloc
0x180008e76  mov     rdi, rax
0x180008e79  test    rax, rax
0x180008e7c  jz      loc_180008DD4
0x180008e82  mov     eax, dword ptr [rsp+88h+pvSaveToPara]
0x180008e86  mov     rcx, rbp
0x180008e89  add     rcx, rcx
0x180008e8c  xor     ebx, ebx
0x180008e8e  mov     ebp, esi
0x180008e90  mov     [rdi+rcx*8], eax
0x180008e93  mov     rax, qword ptr [rsp+88h+pvSaveToPara+8]
0x180008e98  mov     [rdi+rcx*8+8], rax
0x180008e9d  mov     [r15], esi
0x180008ea0  mov     [r12], rdi
0x180008ea4  xor     edi, edi
0x180008ea6  mov     qword ptr [rsp+88h+pvSaveToPara+8], rbx
0x180008eab  jmp     loc_180008DD9
0x180008eb0  xor     esi, esi
0x180008eb2  test    ebp, ebp
0x180008eb4  jz      short loc_180008ECB
0x180008eb6  mov     ecx, esi
0x180008eb8  add     rcx, rcx
0x180008ebb  mov     rcx, [rdi+rcx*8+8]; void *
0x180008ec0  call    MIDL_user_free
0x180008ec5  inc     esi
0x180008ec7  cmp     esi, ebp
0x180008ec9  jb      short loc_180008EB6
0x180008ecb  mov     rcx, rdi; void *
0x180008ece  call    MIDL_user_free
0x180008ed3  jmp     loc_180008DED
0x180008ed8  call    MIDL_user_free
0x180008edd  jmp     loc_180008DFB
```
