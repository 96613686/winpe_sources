# TLSVerifyCertChainInMomory

- ea: `0x180026ac4`
- end: `0x180026bda`
- name: `TLSVerifyCertChainInMomory`
- size: `278`
- prototype: `__int64 __fastcall(HCRYPTPROV_LEGACY hCryptProv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014310`

## callees

- `0x180025f9c`
- `0x180026ac4`

## import_xrefs

- `CRYPT32!CertEnumCertificatesInStore` at `0x180026b49`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180026b49`
- `CRYPT32!CertOpenStore` at `0x180026b1c`
- `CRYPT32!CertOpenStore` at `0x180026b1c`
- `CRYPT32!CertFreeCertificateContext` at `0x180026b8e`
- `CRYPT32!CertFreeCertificateContext` at `0x180026b8e`
- `CRYPT32!CertCloseStore` at `0x180026ba2`
- `CRYPT32!CertCloseStore` at `0x180026ba2`
- `KERNEL32!GetLastError` at `0x180026b30`
- `KERNEL32!GetLastError` at `0x180026b5d`
- `KERNEL32!GetLastError` at `0x180026b30`
- `KERNEL32!GetLastError` at `0x180026b5d`
- `KERNEL32!SetLastError` at `0x180026bbb`
- `KERNEL32!SetLastError` at `0x180026bbb`

## pseudocode

```c
__int64 __fastcall TLSVerifyCertChainInMomory(HCRYPTPROV_LEGACY hCryptProv, __int64 a2, int a3)
{
  PCCERT_CONTEXT v3; // rsi
  HCERTSTORE v4; // rdi
  unsigned int v5; // ebx
  __int64 v6; // rcx
  unsigned int v7; // eax
  _DWORD pvPara[2]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v10; // [rsp+38h] [rbp-10h]
  struct _FILETIME v11; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0;
  pvPara[1] = 0;
  v11 = 0;
  if ( hCryptProv && a2 && a3 )
  {
    v10 = a2;
    pvPara[0] = a3;
    v4 = CertOpenStore("PKCS7", 0x10001u, hCryptProv, 1u, pvPara);
    if ( v4 )
    {
      while ( 1 )
      {
        v3 = CertEnumCertificatesInStore(v4, v3);
        if ( !v3 && GetLastError() == -2146885628 )
          break;
        v7 = TLSVerifyCertChain(v6, v4, v3, &v11);
        v5 = v7;
        if ( !v3 )
          goto LABEL_11;
        if ( v7 )
        {
          CertFreeCertificateContext(v3);
          goto LABEL_11;
        }
      }
      v5 = 0;
LABEL_11:
      CertCloseStore(v4, 1u);
    }
    else
    {
      return GetLastError();
    }
  }
  else
  {
    v5 = 87;
    SetLastError(0x57u);
  }
  return v5;
}

```

## disassembly

```asm
0x180026ac4  mov     rax, rsp
0x180026ac7  mov     [rax+10h], rbx
0x180026acb  mov     [rax+18h], rsi
0x180026acf  push    rdi
0x180026ad0  sub     rsp, 40h
0x180026ad4  xor     esi, esi
0x180026ad6  and     [rax-14h], esi
0x180026ad9  and     [rax+8], rsi
0x180026add  test    rcx, rcx
0x180026ae0  jz      loc_180026BB4
0x180026ae6  test    rdx, rdx
0x180026ae9  jz      loc_180026BB4
0x180026aef  test    r8d, r8d
0x180026af2  jz      loc_180026BB4
0x180026af8  mov     [rax-10h], rdx
0x180026afc  lea     r9d, [rsi+1]; dwFlags
0x180026b00  mov     [rax-18h], r8d
0x180026b04  lea     rax, [rax-18h]
0x180026b08  mov     r8, rcx; hCryptProv
0x180026b0b  mov     [rsp+48h+pvPara], rax; pvPara
0x180026b10  lea     rcx, szStoreProvider; "PKCS7"
0x180026b17  mov     edx, 10001h; dwEncodingType
0x180026b1c  call    cs:__imp_CertOpenStore
0x180026b23  nop     dword ptr [rax+rax+00h]
0x180026b28  mov     rdi, rax
0x180026b2b  test    rax, rax
0x180026b2e  jnz     short loc_180026B43
0x180026b30  call    cs:__imp_GetLastError
0x180026b37  nop     dword ptr [rax+rax+00h]
0x180026b3c  mov     ebx, eax
0x180026b3e  jmp     loc_180026BC7
0x180026b43  mov     rdx, rsi; pPrevCertContext
0x180026b46  mov     rcx, rdi; hCertStore
0x180026b49  call    cs:__imp_CertEnumCertificatesInStore
0x180026b50  nop     dword ptr [rax+rax+00h]
0x180026b55  mov     rsi, rax
0x180026b58  test    rax, rax
0x180026b5b  jnz     short loc_180026B70
0x180026b5d  call    cs:__imp_GetLastError
0x180026b64  nop     dword ptr [rax+rax+00h]
0x180026b69  cmp     eax, 80092004h
0x180026b6e  jz      short loc_180026BB0
0x180026b70  lea     r9, [rsp+48h+arg_0]; struct _FILETIME *
0x180026b75  mov     r8, rsi; struct _CERT_CONTEXT *
0x180026b78  mov     rdx, rdi; void *
0x180026b7b  call    ?TLSVerifyCertChain@@YAK_KPEAXPEBU_CERT_CONTEXT@@PEAU_FILETIME@@@Z; TLSVerifyCertChain(unsigned __int64,void *,_CERT_CONTEXT const *,_FILETIME *)
0x180026b80  mov     ebx, eax
0x180026b82  test    rsi, rsi
0x180026b85  jz      short loc_180026B9A
0x180026b87  test    eax, eax
0x180026b89  jz      short loc_180026B43
0x180026b8b  mov     rcx, rsi; pCertContext
0x180026b8e  call    cs:__imp_CertFreeCertificateContext
0x180026b95  nop     dword ptr [rax+rax+00h]
0x180026b9a  mov     edx, 1; dwFlags
0x180026b9f  mov     rcx, rdi; hCertStore
0x180026ba2  call    cs:__imp_CertCloseStore
0x180026ba9  nop     dword ptr [rax+rax+00h]
0x180026bae  jmp     short loc_180026BC7
0x180026bb0  xor     ebx, ebx
0x180026bb2  jmp     short loc_180026B9A
0x180026bb4  mov     ebx, 57h ; 'W'
0x180026bb9  mov     ecx, ebx; dwErrCode
0x180026bbb  call    cs:__imp_SetLastError
0x180026bc2  nop     dword ptr [rax+rax+00h]
0x180026bc7  mov     rsi, [rsp+48h+arg_10]
0x180026bcc  mov     eax, ebx
0x180026bce  mov     rbx, [rsp+48h+arg_8]
0x180026bd3  add     rsp, 40h
0x180026bd7  pop     rdi
0x180026bd8  retn
```
