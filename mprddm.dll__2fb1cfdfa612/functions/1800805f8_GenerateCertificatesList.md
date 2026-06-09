# GenerateCertificatesList

- ea: `0x1800805f8`
- end: `0x1800806e7`
- name: `GenerateCertificatesList`
- size: `239`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18007e3e0`
- `0x18007eb50`

## callees

- `0x1800805f8`
- `0x1800806f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180080649`
- `KERNEL32!GetLastError` at `0x180080649`
- `CRYPT32!CertOpenStore` at `0x18008063b`
- `CRYPT32!CertOpenStore` at `0x180080690`
- `CRYPT32!CertOpenStore` at `0x18008063b`
- `CRYPT32!CertOpenStore` at `0x180080690`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800806a3`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800806a3`
- `CRYPT32!CertFreeCertificateContext` at `0x1800806b3`
- `CRYPT32!CertFreeCertificateContext` at `0x1800806b3`
- `CRYPT32!CertCloseStore` at `0x1800806c0`
- `CRYPT32!CertCloseStore` at `0x1800806d0`
- `CRYPT32!CertCloseStore` at `0x1800806c0`
- `CRYPT32!CertCloseStore` at `0x1800806d0`

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
0x1800805f8  push    rbx
0x1800805fa  push    rbp
0x1800805fb  push    rsi
0x1800805fc  push    rdi
0x1800805fd  push    r12
0x1800805ff  push    r14
0x180080601  push    r15
0x180080603  sub     rsp, 30h
0x180080607  mov     rbx, r9
0x18008060a  mov     rbp, r8
0x18008060d  mov     r15, rdx
0x180080610  mov     r12d, ecx
0x180080613  mov     edi, 1
0x180080618  test    r9, r9
0x18008061b  jz      short loc_180080620
0x18008061d  mov     [r9], edi
0x180080620  xor     r8d, r8d; hCryptProv
0x180080623  lea     rax, aMy; "My"
0x18008062a  mov     r9d, 20000h; dwFlags
0x180080630  mov     [rsp+68h+pvPara], rax; pvPara
0x180080635  mov     edx, edi; dwEncodingType
0x180080637  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x18008063b  call    cs:__imp_CertOpenStore
0x180080641  mov     r14, rax
0x180080644  test    rax, rax
0x180080647  jnz     short loc_180080656
0x180080649  call    cs:__imp_GetLastError
0x18008064f  mov     ebp, eax
0x180080651  jmp     loc_1800806D6
0x180080656  mov     r9, rbp
0x180080659  mov     r8, r15
0x18008065c  mov     rdx, r14
0x18008065f  mov     ecx, r12d
0x180080662  xor     esi, esi
0x180080664  call    ListCertChainsInStore
0x180080669  mov     ebp, eax
0x18008066b  test    eax, eax
0x18008066d  jnz     short loc_1800806BB
0x18008066f  test    rbx, rbx
0x180080672  jz      short loc_1800806BB
0x180080674  lea     rax, aMy_0; "MY"
0x18008067b  mov     [rbx], esi
0x18008067d  mov     r9d, 20000h; dwFlags
0x180080683  mov     [rsp+68h+pvPara], rax; pvPara
0x180080688  xor     r8d, r8d; hCryptProv
0x18008068b  lea     ecx, [rsi+0Ah]; lpszStoreProvider
0x18008068e  mov     edx, edi; dwEncodingType
0x180080690  call    cs:__imp_CertOpenStore
0x180080696  mov     rsi, rax
0x180080699  test    rax, rax
0x18008069c  jz      short loc_1800806BB
0x18008069e  xor     edx, edx; pPrevCertContext
0x1800806a0  mov     rcx, rax; hCertStore
0x1800806a3  call    cs:__imp_CertEnumCertificatesInStore
0x1800806a9  test    rax, rax
0x1800806ac  jz      short loc_1800806B9
0x1800806ae  xor     edi, edi
0x1800806b0  mov     rcx, rax; pCertContext
0x1800806b3  call    cs:__imp_CertFreeCertificateContext
0x1800806b9  mov     [rbx], edi
0x1800806bb  xor     edx, edx; dwFlags
0x1800806bd  mov     rcx, r14; hCertStore
0x1800806c0  call    cs:__imp_CertCloseStore
0x1800806c6  test    rsi, rsi
0x1800806c9  jz      short loc_1800806D6
0x1800806cb  xor     edx, edx; dwFlags
0x1800806cd  mov     rcx, rsi; hCertStore
0x1800806d0  call    cs:__imp_CertCloseStore
0x1800806d6  mov     eax, ebp
0x1800806d8  add     rsp, 30h
0x1800806dc  pop     r15
0x1800806de  pop     r14
0x1800806e0  pop     r12
0x1800806e2  pop     rdi
0x1800806e3  pop     rsi
0x1800806e4  pop     rbp
0x1800806e5  pop     rbx
0x1800806e6  retn
```
