# GenerateCertificatesList

- ea: `0x180085f44`
- end: `0x180086077`
- name: `GenerateCertificatesList`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180083654`
- `0x180083de8`

## callees

- `0x180085f44`
- `0x180086080`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180085fa6`
- `KERNEL32!GetLastError` at `0x180085fa6`
- `CRYPT32!CertOpenStore` at `0x180085f92`
- `CRYPT32!CertOpenStore` at `0x180085ff2`
- `CRYPT32!CertOpenStore` at `0x180085f92`
- `CRYPT32!CertOpenStore` at `0x180085ff2`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18008600d`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18008600d`
- `CRYPT32!CertFreeCertificateContext` at `0x180086026`
- `CRYPT32!CertFreeCertificateContext` at `0x180086026`
- `CRYPT32!CertCloseStore` at `0x180086039`
- `CRYPT32!CertCloseStore` at `0x18008604f`
- `CRYPT32!CertCloseStore` at `0x180086039`
- `CRYPT32!CertCloseStore` at `0x18008604f`

## pseudocode

```c
__int64 __fastcall GenerateCertificatesList(unsigned int a1, __int64 a2, __int64 a3, int *a4)
{
  void *v4; // rdi
  HCERTSTORE v9; // rax
  void *v10; // r14
  unsigned int v11; // esi
  HCERTSTORE v12; // rax
  int v13; // ebp
  const CERT_CONTEXT *v14; // rax

  v4 = 0;
  if ( a4 )
    *a4 = 1;
  v9 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x20000u, L"My");
  v10 = v9;
  if ( v9 )
  {
    v11 = ListCertChainsInStore(a1, v9, a2, a3);
    if ( !v11 )
    {
      if ( a4 )
      {
        *a4 = 0;
        v12 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x20000u, L"MY");
        v4 = v12;
        if ( v12 )
        {
          v13 = 0;
          v14 = CertEnumCertificatesInStore(v12, 0);
          if ( v14 )
            CertFreeCertificateContext(v14);
          else
            v13 = 1;
          *a4 = v13;
        }
      }
    }
    CertCloseStore(v10, 0);
    if ( v4 )
      CertCloseStore(v4, 0);
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
0x180085f44  mov     [rsp+arg_0], rbx
0x180085f49  mov     [rsp+arg_8], rbp
0x180085f4e  mov     [rsp+arg_10], rsi
0x180085f53  push    rdi
0x180085f54  push    r14
0x180085f56  push    r15
0x180085f58  sub     rsp, 30h
0x180085f5c  xor     edi, edi
0x180085f5e  mov     rbx, r9
0x180085f61  mov     rsi, r8
0x180085f64  mov     rbp, rdx
0x180085f67  mov     r15d, ecx
0x180085f6a  test    r9, r9
0x180085f6d  jz      short loc_180085F76
0x180085f6f  mov     dword ptr [r9], 1
0x180085f76  xor     r8d, r8d; hCryptProv
0x180085f79  lea     rax, aMy; "My"
0x180085f80  mov     r9d, 20000h; dwFlags
0x180085f86  mov     [rsp+48h+pvPara], rax; pvPara
0x180085f8b  lea     edx, [r8+1]; dwEncodingType
0x180085f8f  lea     ecx, [rdx+9]; lpszStoreProvider
0x180085f92  call    cs:__imp_CertOpenStore
0x180085f99  nop     dword ptr [rax+rax+00h]
0x180085f9e  mov     r14, rax
0x180085fa1  test    rax, rax
0x180085fa4  jnz     short loc_180085FB9
0x180085fa6  call    cs:__imp_GetLastError
0x180085fad  nop     dword ptr [rax+rax+00h]
0x180085fb2  mov     esi, eax
0x180085fb4  jmp     loc_18008605B
0x180085fb9  mov     r9, rsi
0x180085fbc  mov     r8, rbp
0x180085fbf  mov     rdx, r14
0x180085fc2  mov     ecx, r15d
0x180085fc5  call    ListCertChainsInStore
0x180085fca  mov     esi, eax
0x180085fcc  test    eax, eax
0x180085fce  jnz     short loc_180086034
0x180085fd0  test    rbx, rbx
0x180085fd3  jz      short loc_180086034
0x180085fd5  and     [rbx], edi
0x180085fd7  lea     rax, aMy_0; "MY"
0x180085fde  mov     r9d, 20000h; dwFlags
0x180085fe4  mov     [rsp+48h+pvPara], rax; pvPara
0x180085fe9  xor     r8d, r8d; hCryptProv
0x180085fec  lea     edx, [rsi+1]; dwEncodingType
0x180085fef  lea     ecx, [rsi+0Ah]; lpszStoreProvider
0x180085ff2  call    cs:__imp_CertOpenStore
0x180085ff9  nop     dword ptr [rax+rax+00h]
0x180085ffe  mov     rdi, rax
0x180086001  test    rax, rax
0x180086004  jz      short loc_180086034
0x180086006  xor     edx, edx; pPrevCertContext
0x180086008  mov     rcx, rax; hCertStore
0x18008600b  xor     ebp, ebp
0x18008600d  call    cs:__imp_CertEnumCertificatesInStore
0x180086014  nop     dword ptr [rax+rax+00h]
0x180086019  test    rax, rax
0x18008601c  jnz     short loc_180086023
0x18008601e  lea     ebp, [rsi+1]
0x180086021  jmp     short loc_180086032
0x180086023  mov     rcx, rax; pCertContext
0x180086026  call    cs:__imp_CertFreeCertificateContext
0x18008602d  nop     dword ptr [rax+rax+00h]
0x180086032  mov     [rbx], ebp
0x180086034  xor     edx, edx; dwFlags
0x180086036  mov     rcx, r14; hCertStore
0x180086039  call    cs:__imp_CertCloseStore
0x180086040  nop     dword ptr [rax+rax+00h]
0x180086045  test    rdi, rdi
0x180086048  jz      short loc_18008605B
0x18008604a  xor     edx, edx; dwFlags
0x18008604c  mov     rcx, rdi; hCertStore
0x18008604f  call    cs:__imp_CertCloseStore
0x180086056  nop     dword ptr [rax+rax+00h]
0x18008605b  mov     rbx, [rsp+48h+arg_0]
0x180086060  mov     eax, esi
0x180086062  mov     rsi, [rsp+48h+arg_10]
0x180086067  mov     rbp, [rsp+48h+arg_8]
0x18008606c  add     rsp, 30h
0x180086070  pop     r15
0x180086072  pop     r14
0x180086074  pop     rdi
0x180086075  retn
```
