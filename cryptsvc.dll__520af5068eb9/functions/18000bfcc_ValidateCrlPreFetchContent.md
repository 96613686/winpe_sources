# ValidateCrlPreFetchContent

- ea: `0x18000bfcc`
- end: `0x18000c0bf`
- name: `ValidateCrlPreFetchContent`
- size: `243`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003c90`

## callees

- `0x18000bfcc`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x18000c0ae`
- `CRYPT32!CertCloseStore` at `0x18000c0ae`
- `CRYPT32!CertFreeCRLContext` at `0x18000c09e`
- `CRYPT32!CertFreeCRLContext` at `0x18000c09e`
- `CRYPT32!CertEnumCRLsInStore` at `0x18000c049`
- `CRYPT32!CertEnumCRLsInStore` at `0x18000c049`
- `CRYPT32!CryptQueryObject` at `0x18000c035`
- `CRYPT32!CryptQueryObject` at `0x18000c035`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000c06a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000c07e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000c06a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000c07e`

## pseudocode

```c
__int64 __fastcall ValidateCrlPreFetchContent(__int64 a1)
{
  __int64 v1; // rdx
  unsigned int v2; // edi
  PCCRL_CONTEXT v4; // rax
  const CRL_CONTEXT *v5; // rsi
  const FILETIME *pCrlInfo; // rcx
  const FILETIME *v7; // rbx
  HCERTSTORE hCertStore; // [rsp+90h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 216);
  v2 = -1;
  hCertStore = 0;
  if ( CryptQueryObject(2u, *(const void **)(v1 + 8), 0x108u, 0xEu, 0, 0, 0, 0, &hCertStore, 0, 0) )
  {
    v4 = CertEnumCRLsInStore(hCertStore, 0);
    v5 = v4;
    if ( v4 )
    {
      pCrlInfo = (const FILETIME *)v4->pCrlInfo;
      v7 = pCrlInfo + 7;
      if ( CompareFileTime(pCrlInfo + 6, (const FILETIME *)(a1 + 152)) > 0
        || CompareFileTime(v7, (const FILETIME *)(a1 + 160)) > 0 )
      {
        v2 = 1;
        *(FILETIME *)(a1 + 240) = *v7;
      }
      else
      {
        v2 = 0;
      }
      CertFreeCRLContext(v5);
    }
    CertCloseStore(hCertStore, 0);
  }
  return v2;
}

```

## disassembly

```asm
0x18000bfcc  mov     r11, rsp
0x18000bfcf  push    rbx
0x18000bfd0  push    rbp
0x18000bfd1  push    rsi
0x18000bfd2  push    rdi
0x18000bfd3  sub     rsp, 68h
0x18000bfd7  mov     rdx, [rcx+0D8h]
0x18000bfde  lea     rax, [r11+8]
0x18000bfe2  mov     qword ptr [r11-38h], 0
0x18000bfea  or      edi, 0FFFFFFFFh
0x18000bfed  mov     qword ptr [r11-40h], 0
0x18000bff5  mov     rbp, rcx
0x18000bff8  mov     [r11-48h], rax
0x18000bffc  mov     r8d, 108h; dwExpectedContentTypeFlags
0x18000c002  mov     qword ptr [r11-50h], 0
0x18000c00a  mov     qword ptr [r11-58h], 0
0x18000c012  lea     r9d, [rdi+0Fh]; dwExpectedFormatTypeFlags
0x18000c016  mov     qword ptr [r11+8], 0
0x18000c01e  lea     ecx, [rdi+3]; dwObjectType
0x18000c021  mov     rdx, [rdx+8]; pvObject
0x18000c025  mov     qword ptr [r11-60h], 0
0x18000c02d  mov     [rsp+88h+dwFlags], 0; dwFlags
0x18000c035  call    cs:__imp_CryptQueryObject
0x18000c03b  test    eax, eax
0x18000c03d  jz      short loc_18000C0B4
0x18000c03f  mov     rcx, [rsp+88h+hCertStore]; hCertStore
0x18000c047  xor     edx, edx; pPrevCrlContext
0x18000c049  call    cs:__imp_CertEnumCRLsInStore
0x18000c04f  mov     rsi, rax
0x18000c052  test    rax, rax
0x18000c055  jz      short loc_18000C0A4
0x18000c057  mov     rcx, [rax+18h]
0x18000c05b  lea     rdx, [rbp+98h]; lpFileTime2
0x18000c062  lea     rbx, [rcx+38h]
0x18000c066  add     rcx, 30h ; '0'; lpFileTime1
0x18000c06a  call    cs:__imp_CompareFileTime
0x18000c070  test    eax, eax
0x18000c072  jg      short loc_18000C08C
0x18000c074  lea     rdx, [rbp+0A0h]; lpFileTime2
0x18000c07b  mov     rcx, rbx; lpFileTime1
0x18000c07e  call    cs:__imp_CompareFileTime
0x18000c084  test    eax, eax
0x18000c086  jg      short loc_18000C08C
0x18000c088  xor     edi, edi
0x18000c08a  jmp     short loc_18000C09B
0x18000c08c  mov     rcx, [rbx]
0x18000c08f  mov     edi, 1
0x18000c094  mov     [rbp+0F0h], rcx
0x18000c09b  mov     rcx, rsi; pCrlContext
0x18000c09e  call    cs:__imp_CertFreeCRLContext
0x18000c0a4  mov     rcx, [rsp+88h+hCertStore]; hCertStore
0x18000c0ac  xor     edx, edx; dwFlags
0x18000c0ae  call    cs:__imp_CertCloseStore
0x18000c0b4  mov     eax, edi
0x18000c0b6  add     rsp, 68h
0x18000c0ba  pop     rdi
0x18000c0bb  pop     rsi
0x18000c0bc  pop     rbp
0x18000c0bd  pop     rbx
0x18000c0be  retn
```
