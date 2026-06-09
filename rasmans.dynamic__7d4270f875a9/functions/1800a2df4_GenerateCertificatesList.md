# GenerateCertificatesList

- ea: `0x1800a2df4`
- end: `0x1800a2f0e`
- name: `GenerateCertificatesList`
- size: `282`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a0988`
- `0x1800a117c`

## callees

- `0x1800a2df4`
- `0x1800a2f14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2e4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2e4b`
- `CRYPT32!CertFreeCertificateContext` at `0x1800a2ec7`
- `CRYPT32!CertFreeCertificateContext` at `0x1800a2ec7`
- `CRYPT32!CertCloseStore` at `0x1800a2eda`
- `CRYPT32!CertCloseStore` at `0x1800a2ef0`
- `CRYPT32!CertCloseStore` at `0x1800a2eda`
- `CRYPT32!CertCloseStore` at `0x1800a2ef0`
- `CRYPT32!CertOpenStore` at `0x1800a2e37`
- `CRYPT32!CertOpenStore` at `0x1800a2e98`
- `CRYPT32!CertOpenStore` at `0x1800a2e37`
- `CRYPT32!CertOpenStore` at `0x1800a2e98`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800a2eb1`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800a2eb1`

## pseudocode

```c
__int64 __fastcall GenerateCertificatesList(unsigned int a1, __int64 a2, __int64 a3, int *a4)
{
  int v8; // edi
  HCERTSTORE v9; // rax
  void *v10; // r14
  unsigned int v11; // ebp
  void *v12; // rsi
  HCERTSTORE v13; // rax
  const CERT_CONTEXT *v14; // rax

  v8 = 1;
  if ( a4 )
    *a4 = 1;
  v9 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x20000u, L"My");
  v10 = v9;
  if ( v9 )
  {
    v12 = 0;
    v11 = ListCertChainsInStore(a1, v9, a2, a3);
    if ( !v11 )
    {
      if ( a4 )
      {
        *a4 = 0;
        v13 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x20000u, L"MY");
        v12 = v13;
        if ( v13 )
        {
          v14 = CertEnumCertificatesInStore(v13, 0);
          if ( v14 )
          {
            v8 = 0;
            CertFreeCertificateContext(v14);
          }
          *a4 = v8;
        }
      }
    }
    CertCloseStore(v10, 0);
    if ( v12 )
      CertCloseStore(v12, 0);
  }
  else
  {
    return GetLastError();
  }
  return v11;
}

```

## disassembly

```asm
0x1800a2df4  push    rbx
0x1800a2df6  push    rbp
0x1800a2df7  push    rsi
0x1800a2df8  push    rdi
0x1800a2df9  push    r12
0x1800a2dfb  push    r14
0x1800a2dfd  push    r15
0x1800a2dff  sub     rsp, 30h
0x1800a2e03  mov     rbx, r9
0x1800a2e06  mov     rbp, r8
0x1800a2e09  mov     r15, rdx
0x1800a2e0c  mov     r12d, ecx
0x1800a2e0f  mov     edi, 1
0x1800a2e14  test    r9, r9
0x1800a2e17  jz      short loc_1800A2E1C
0x1800a2e19  mov     [r9], edi
0x1800a2e1c  xor     r8d, r8d; hCryptProv
0x1800a2e1f  lea     rax, aMy; "My"
0x1800a2e26  mov     r9d, 20000h; dwFlags
0x1800a2e2c  mov     [rsp+68h+pvPara], rax; pvPara
0x1800a2e31  mov     edx, edi; dwEncodingType
0x1800a2e33  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x1800a2e37  call    cs:__imp_CertOpenStore
0x1800a2e3e  nop     dword ptr [rax+rax+00h]
0x1800a2e43  mov     r14, rax
0x1800a2e46  test    rax, rax
0x1800a2e49  jnz     short loc_1800A2E5E
0x1800a2e4b  call    cs:__imp_GetLastError
0x1800a2e52  nop     dword ptr [rax+rax+00h]
0x1800a2e57  mov     ebp, eax
0x1800a2e59  jmp     loc_1800A2EFC
0x1800a2e5e  mov     r9, rbp
0x1800a2e61  mov     r8, r15
0x1800a2e64  mov     rdx, r14
0x1800a2e67  mov     ecx, r12d
0x1800a2e6a  xor     esi, esi
0x1800a2e6c  call    ListCertChainsInStore
0x1800a2e71  mov     ebp, eax
0x1800a2e73  test    eax, eax
0x1800a2e75  jnz     short loc_1800A2ED5
0x1800a2e77  test    rbx, rbx
0x1800a2e7a  jz      short loc_1800A2ED5
0x1800a2e7c  lea     rax, aMy_0; "MY"
0x1800a2e83  mov     [rbx], esi
0x1800a2e85  mov     r9d, 20000h; dwFlags
0x1800a2e8b  mov     [rsp+68h+pvPara], rax; pvPara
0x1800a2e90  xor     r8d, r8d; hCryptProv
0x1800a2e93  lea     ecx, [rsi+0Ah]; lpszStoreProvider
0x1800a2e96  mov     edx, edi; dwEncodingType
0x1800a2e98  call    cs:__imp_CertOpenStore
0x1800a2e9f  nop     dword ptr [rax+rax+00h]
0x1800a2ea4  mov     rsi, rax
0x1800a2ea7  test    rax, rax
0x1800a2eaa  jz      short loc_1800A2ED5
0x1800a2eac  xor     edx, edx; pPrevCertContext
0x1800a2eae  mov     rcx, rax; hCertStore
0x1800a2eb1  call    cs:__imp_CertEnumCertificatesInStore
0x1800a2eb8  nop     dword ptr [rax+rax+00h]
0x1800a2ebd  test    rax, rax
0x1800a2ec0  jz      short loc_1800A2ED3
0x1800a2ec2  xor     edi, edi
0x1800a2ec4  mov     rcx, rax; pCertContext
0x1800a2ec7  call    cs:__imp_CertFreeCertificateContext
0x1800a2ece  nop     dword ptr [rax+rax+00h]
0x1800a2ed3  mov     [rbx], edi
0x1800a2ed5  xor     edx, edx; dwFlags
0x1800a2ed7  mov     rcx, r14; hCertStore
0x1800a2eda  call    cs:__imp_CertCloseStore
0x1800a2ee1  nop     dword ptr [rax+rax+00h]
0x1800a2ee6  test    rsi, rsi
0x1800a2ee9  jz      short loc_1800A2EFC
0x1800a2eeb  xor     edx, edx; dwFlags
0x1800a2eed  mov     rcx, rsi; hCertStore
0x1800a2ef0  call    cs:__imp_CertCloseStore
0x1800a2ef7  nop     dword ptr [rax+rax+00h]
0x1800a2efc  mov     eax, ebp
0x1800a2efe  add     rsp, 30h
0x1800a2f02  pop     r15
0x1800a2f04  pop     r14
0x1800a2f06  pop     r12
0x1800a2f08  pop     rdi
0x1800a2f09  pop     rsi
0x1800a2f0a  pop     rbp
0x1800a2f0b  pop     rbx
0x1800a2f0c  retn
```
