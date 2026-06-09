# GetCertificate(ulong,uchar *,unsigned __int64,_CERT_CONTEXT const * *,void * *)

- ea: `0x18005f58c`
- end: `0x18005f776`
- name: `?GetCertificate@@YAKKPEAE_KPEAPEBU_CERT_CONTEXT@@PEAPEAX@Z`
- size: `490`
- prototype: `unsigned int(unsigned int, unsigned __int8 *, unsigned __int64, const struct _CERT_CONTEXT **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800617a0`

## callees

- `0x18001ae3c`
- `0x18001aea4`
- `0x18005f58c`

## import_xrefs

- `CRYPT32!CertFindCertificateInStore` at `0x18005f735`
- `CRYPT32!CertFindCertificateInStore` at `0x18005f735`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18005f6d3`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18005f6d3`
- `CRYPT32!CertOpenStore` at `0x18005f63c`
- `CRYPT32!CertOpenStore` at `0x18005f63c`
- `KERNEL32!GetLastError` at `0x18005f650`
- `KERNEL32!GetLastError` at `0x18005f6e7`
- `KERNEL32!GetLastError` at `0x18005f650`
- `KERNEL32!GetLastError` at `0x18005f6e7`

## pseudocode

```c
__int64 __fastcall GetCertificate(
        int a1,
        unsigned __int8 *a2,
        HCRYPTPROV_LEGACY a3,
        const struct _CERT_CONTEXT **a4,
        void **a5)
{
  DWORD LastError; // ebx
  PCCERT_CONTEXT v7; // rdi
  HCERTSTORE v11; // rax
  PVOID *v12; // rcx
  __int64 v13; // rdx
  const CERT_CONTEXT *pPrevCertContext; // rcx
  PCCERT_CONTEXT CertificateInStore; // rax
  _DWORD pvPara[2]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int8 *v18; // [rsp+38h] [rbp-30h]

  LastError = 0;
  pvPara[1] = 0;
  v7 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids,
      L"GetCertificate");
  if ( !a4 || !a5 )
    return 87;
  *a4 = 0;
  *a5 = 0;
  pvPara[0] = a1;
  v18 = a2;
  v11 = CertOpenStore("PKCS7", 0x10001u, a3, 1u, pvPara);
  *a5 = v11;
  if ( v11 )
  {
    v7 = CertEnumCertificatesInStore(v11, 0);
    if ( v7 )
    {
      pPrevCertContext = 0;
      while ( 1 )
      {
        CertificateInStore = CertFindCertificateInStore(
                               *a5,
                               0x10001u,
                               0,
                               0x20004u,
                               &v7->pCertInfo->Subject,
                               pPrevCertContext);
        pPrevCertContext = CertificateInStore;
        if ( !CertificateInStore )
          break;
        v7 = CertificateInStore;
      }
      goto LABEL_11;
    }
    LastError = GetLastError();
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_12;
    v13 = 50;
  }
  else
  {
    LastError = GetLastError();
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_12;
    v13 = 49;
  }
  WPP_SF_S(v12[2], v13, WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids, L"GetCertificate");
LABEL_11:
  v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_12:
  *a4 = v7;
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x1000) != 0 )
    WPP_SF_SD(
      (unsigned int)v12[2],
      51,
      (unsigned int)WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids,
      (unsigned int)L"GetCertificate",
      LastError);
  return LastError;
}

```

## disassembly

```asm
0x18005f58c  mov     rax, rsp
0x18005f58f  mov     [rax+8], rbx
0x18005f593  mov     [rax+10h], rbp
0x18005f597  mov     [rax+18h], rsi
0x18005f59b  push    rdi
0x18005f59c  push    r12
0x18005f59e  push    r13
0x18005f5a0  push    r14
0x18005f5a2  push    r15
0x18005f5a4  sub     rsp, 40h
0x18005f5a8  xor     ebx, ebx
0x18005f5aa  mov     r14, r9
0x18005f5ad  mov     [rax-34h], ebx
0x18005f5b0  mov     edi, ebx
0x18005f5b2  mov     rbp, r8
0x18005f5b5  mov     r15, rdx
0x18005f5b8  mov     r12d, ecx
0x18005f5bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f5c2  lea     r13, WPP_GLOBAL_Control
0x18005f5c9  cmp     rcx, r13
0x18005f5cc  jz      short loc_18005F5F1
0x18005f5ce  test    dword ptr [rcx+1Ch], 1000h
0x18005f5d5  jz      short loc_18005F5F1
0x18005f5d7  mov     rcx, [rcx+10h]
0x18005f5db  lea     edx, [rbx+30h]
0x18005f5de  lea     r9, aGetcertificate; "GetCertificate"
0x18005f5e5  lea     r8, WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids
0x18005f5ec  call    WPP_SF_S
0x18005f5f1  test    r14, r14
0x18005f5f4  jz      loc_18005F752
0x18005f5fa  mov     rsi, [rsp+68h+arg_20]
0x18005f602  test    rsi, rsi
0x18005f605  jz      loc_18005F752
0x18005f60b  mov     r8, rbp; hCryptProv
0x18005f60e  mov     [r14], rbx
0x18005f611  lea     rax, [rsp+68h+var_38]
0x18005f616  mov     [rsi], rbx
0x18005f619  mov     ebp, 10001h
0x18005f61e  mov     [rsp+68h+var_38], r12d
0x18005f623  mov     edx, ebp; dwEncodingType
0x18005f625  mov     [rsp+68h+var_30], r15
0x18005f62a  mov     r9d, 1; dwFlags
0x18005f630  mov     [rsp+68h+pvPara], rax; pvPara
0x18005f635  lea     rcx, szStoreProvider; "PKCS7"
0x18005f63c  call    cs:__imp_CertOpenStore
0x18005f643  nop     dword ptr [rax+rax+00h]
0x18005f648  mov     [rsi], rax
0x18005f64b  test    rax, rax
0x18005f64e  jnz     short loc_18005F6CE
0x18005f650  call    cs:__imp_GetLastError
0x18005f657  nop     dword ptr [rax+rax+00h]
0x18005f65c  mov     ebx, eax
0x18005f65e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f665  cmp     rcx, r13
0x18005f668  jz      short loc_18005F696
0x18005f66a  test    dword ptr [rcx+1Ch], 200h
0x18005f671  jz      short loc_18005F696
0x18005f673  mov     edx, 31h ; '1'
0x18005f678  mov     rcx, [rcx+10h]
0x18005f67c  lea     r9, aGetcertificate; "GetCertificate"
0x18005f683  lea     r8, WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids
0x18005f68a  call    WPP_SF_S
0x18005f68f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f696  mov     [r14], rdi
0x18005f699  cmp     rcx, r13
0x18005f69c  jz      short loc_18005F6C7
0x18005f69e  test    dword ptr [rcx+1Ch], 1000h
0x18005f6a5  jz      short loc_18005F6C7
0x18005f6a7  mov     rcx, [rcx+10h]
0x18005f6ab  lea     r9, aGetcertificate; "GetCertificate"
0x18005f6b2  mov     edx, 33h ; '3'
0x18005f6b7  mov     dword ptr [rsp+68h+pvPara], ebx
0x18005f6bb  lea     r8, WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids
0x18005f6c2  call    WPP_SF_SD
0x18005f6c7  mov     eax, ebx
0x18005f6c9  jmp     loc_18005F757
0x18005f6ce  xor     edx, edx; pPrevCertContext
0x18005f6d0  mov     rcx, rax; hCertStore
0x18005f6d3  call    cs:__imp_CertEnumCertificatesInStore
0x18005f6da  nop     dword ptr [rax+rax+00h]
0x18005f6df  mov     rdi, rax
0x18005f6e2  test    rax, rax
0x18005f6e5  jnz     short loc_18005F712
0x18005f6e7  call    cs:__imp_GetLastError
0x18005f6ee  nop     dword ptr [rax+rax+00h]
0x18005f6f3  mov     ebx, eax
0x18005f6f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f6fc  cmp     rcx, r13
0x18005f6ff  jz      short loc_18005F696
0x18005f701  test    dword ptr [rcx+1Ch], 200h
0x18005f708  jz      short loc_18005F696
0x18005f70a  lea     edx, [rdi+32h]
0x18005f70d  jmp     loc_18005F678
0x18005f712  mov     rcx, rbx
0x18005f715  mov     rax, [rdi+18h]
0x18005f719  mov     r9d, 20004h; dwFindType
0x18005f71f  mov     [rsp+68h+pPrevCertContext], rcx; pPrevCertContext
0x18005f724  add     rax, 50h ; 'P'
0x18005f728  mov     rcx, [rsi]; hCertStore
0x18005f72b  xor     r8d, r8d; dwFindFlags
0x18005f72e  mov     edx, ebp; dwCertEncodingType
0x18005f730  mov     [rsp+68h+pvPara], rax; pvFindPara
0x18005f735  call    cs:__imp_CertFindCertificateInStore
0x18005f73c  nop     dword ptr [rax+rax+00h]
0x18005f741  mov     rcx, rax
0x18005f744  test    rax, rax
0x18005f747  jz      loc_18005F68F
0x18005f74d  mov     rdi, rax
0x18005f750  jmp     short loc_18005F715
0x18005f752  mov     eax, 57h ; 'W'
0x18005f757  lea     r11, [rsp+68h+var_28]
0x18005f75c  mov     rbx, [r11+30h]
0x18005f760  mov     rbp, [r11+38h]
0x18005f764  mov     rsi, [r11+40h]
0x18005f768  mov     rsp, r11
0x18005f76b  pop     r15
0x18005f76d  pop     r14
0x18005f76f  pop     r13
0x18005f771  pop     r12
0x18005f773  pop     rdi
0x18005f774  retn
```
