# GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)

- ea: `0x18001d590`
- end: `0x18001d6c3`
- name: `?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z`
- size: `307`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, const struct _CERT_CONTEXT **, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001d3fc`

## callees

- `0x18001d590`
- `0x18001d6cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d5ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d5ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d5db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d67f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d5db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d67f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d68e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d68e`
- `DMCmnUtils!HexStringToBinary` at `0x18001d5c8`
- `DMCmnUtils!HexStringToBinary` at `0x18001d611`
- `DMCmnUtils!HexStringToBinary` at `0x18001d5c8`
- `DMCmnUtils!HexStringToBinary` at `0x18001d611`
- `CRYPT32!CertFreeCertificateContext` at `0x18001d6ac`
- `CRYPT32!CertFreeCertificateContext` at `0x18001d6ac`
- `CRYPT32!CertCloseStore` at `0x18001d69e`
- `CRYPT32!CertCloseStore` at `0x18001d69e`

## pseudocode

```c
__int64 __fastcall GetInstalledCert(
        const unsigned __int16 *a1,
        void **a2,
        const struct _CERT_CONTEXT **a3,
        __int64 a4,
        unsigned int *a5)
{
  unsigned int *v5; // rsi
  const CERT_CONTEXT *v8; // rdi
  int InstalledCertHelper; // ebx
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  HANDLE v15; // rax
  const struct _CERT_CONTEXT *v17; // [rsp+30h] [rbp-20h] BYREF
  SIZE_T dwBytes[2]; // [rsp+38h] [rbp-18h] BYREF

  v5 = 0;
  a5 = 0;
  v8 = 0;
  v17 = 0;
  *(_OWORD *)dwBytes = 0;
  InstalledCertHelper = HexStringToBinary(a1, 0, dwBytes, 1);
  if ( InstalledCertHelper >= 0 )
  {
    v11 = dwBytes[0];
    ProcessHeap = GetProcessHeap();
    dwBytes[1] = (SIZE_T)HeapAlloc(ProcessHeap, 8u, v11);
    if ( dwBytes[1] )
    {
      InstalledCertHelper = HexStringToBinary(a1, dwBytes[1], dwBytes, 1);
      if ( InstalledCertHelper >= 0 )
      {
        InstalledCertHelper = GetInstalledCertHelper(v13, 655360, dwBytes, &a5, &v17);
        if ( InstalledCertHelper >= 0
          || (InstalledCertHelper = GetInstalledCertHelper(v14, 0x10000, dwBytes, &a5, &v17), InstalledCertHelper >= 0) )
        {
          *a2 = a5;
          *a3 = v17;
        }
        else
        {
          v5 = a5;
          v8 = v17;
        }
      }
    }
    else
    {
      InstalledCertHelper = -2147024882;
    }
  }
  if ( dwBytes[1] )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, (LPVOID)dwBytes[1]);
  }
  if ( v5 )
    CertCloseStore(v5, 0);
  if ( v8 )
    CertFreeCertificateContext(v8);
  return (unsigned int)InstalledCertHelper;
}

```

## disassembly

```asm
0x18001d590  push    rbp
0x18001d592  push    rbx
0x18001d593  push    rsi
0x18001d594  push    rdi
0x18001d595  push    r12
0x18001d597  push    r14
0x18001d599  push    r15
0x18001d59b  mov     rbp, rsp
0x18001d59e  sub     rsp, 50h
0x18001d5a2  xor     esi, esi
0x18001d5a4  mov     r15, r8
0x18001d5a7  mov     r12, rdx
0x18001d5aa  mov     [rbp+arg_20], rsi
0x18001d5ae  xorps   xmm0, xmm0
0x18001d5b1  lea     r8, [rbp+dwBytes]
0x18001d5b5  xor     edi, edi
0x18001d5b7  xor     edx, edx
0x18001d5b9  lea     r9d, [rsi+1]
0x18001d5bd  mov     [rbp+var_20], rdi
0x18001d5c1  mov     r14, rcx
0x18001d5c4  movups  xmmword ptr [rbp+dwBytes], xmm0
0x18001d5c8  call    cs:__imp_HexStringToBinary
0x18001d5ce  mov     ebx, eax
0x18001d5d0  test    eax, eax
0x18001d5d2  js      loc_18001D678
0x18001d5d8  mov     ebx, dword ptr [rbp+dwBytes]
0x18001d5db  call    cs:__imp_GetProcessHeap
0x18001d5e1  mov     r8d, ebx; dwBytes
0x18001d5e4  lea     edx, [rsi+8]; dwFlags
0x18001d5e7  mov     rcx, rax; hHeap
0x18001d5ea  call    cs:__imp_HeapAlloc
0x18001d5f0  mov     [rbp+dwBytes+8], rax
0x18001d5f4  test    rax, rax
0x18001d5f7  jnz     short loc_18001D600
0x18001d5f9  mov     ebx, 8007000Eh
0x18001d5fe  jmp     short loc_18001D678
0x18001d600  mov     rdx, [rbp+dwBytes+8]
0x18001d604  lea     r8, [rbp+dwBytes]
0x18001d608  mov     r9d, 1
0x18001d60e  mov     rcx, r14
0x18001d611  call    cs:__imp_HexStringToBinary
0x18001d617  mov     ebx, eax
0x18001d619  test    eax, eax
0x18001d61b  js      short loc_18001D678
0x18001d61d  lea     rax, [rbp+var_20]
0x18001d621  mov     edx, 0A0000h
0x18001d626  lea     r9, [rbp+arg_20]
0x18001d62a  mov     [rsp+50h+var_30], rax
0x18001d62f  lea     r8, [rbp+dwBytes]
0x18001d633  call    GetInstalledCertHelper
0x18001d638  mov     ebx, eax
0x18001d63a  test    eax, eax
0x18001d63c  jns     short loc_18001D669
0x18001d63e  lea     rax, [rbp+var_20]
0x18001d642  mov     edx, 10000h
0x18001d647  lea     r9, [rbp+arg_20]
0x18001d64b  mov     [rsp+50h+var_30], rax
0x18001d650  lea     r8, [rbp+dwBytes]
0x18001d654  call    GetInstalledCertHelper
0x18001d659  mov     ebx, eax
0x18001d65b  test    eax, eax
0x18001d65d  jns     short loc_18001D669
0x18001d65f  mov     rsi, [rbp+arg_20]
0x18001d663  mov     rdi, [rbp+var_20]
0x18001d667  jmp     short loc_18001D678
0x18001d669  mov     rax, [rbp+arg_20]
0x18001d66d  mov     [r12], rax
0x18001d671  mov     rax, [rbp+var_20]
0x18001d675  mov     [r15], rax
0x18001d678  cmp     [rbp+dwBytes+8], 0
0x18001d67d  jz      short loc_18001D694
0x18001d67f  call    cs:__imp_GetProcessHeap
0x18001d685  mov     r8, [rbp+dwBytes+8]; lpMem
0x18001d689  xor     edx, edx; dwFlags
0x18001d68b  mov     rcx, rax; hHeap
0x18001d68e  call    cs:__imp_HeapFree
0x18001d694  test    rsi, rsi
0x18001d697  jz      short loc_18001D6A4
0x18001d699  xor     edx, edx; dwFlags
0x18001d69b  mov     rcx, rsi; hCertStore
0x18001d69e  call    cs:__imp_CertCloseStore
0x18001d6a4  test    rdi, rdi
0x18001d6a7  jz      short loc_18001D6B2
0x18001d6a9  mov     rcx, rdi; pCertContext
0x18001d6ac  call    cs:__imp_CertFreeCertificateContext
0x18001d6b2  mov     eax, ebx
0x18001d6b4  add     rsp, 50h
0x18001d6b8  pop     r15
0x18001d6ba  pop     r14
0x18001d6bc  pop     r12
0x18001d6be  pop     rdi
0x18001d6bf  pop     rsi
0x18001d6c0  pop     rbx
0x18001d6c1  pop     rbp
0x18001d6c2  retn
```
