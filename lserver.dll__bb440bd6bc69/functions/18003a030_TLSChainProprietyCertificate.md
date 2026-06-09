# TLSChainProprietyCertificate

- ea: `0x18003a030`
- end: `0x18003a1f0`
- name: `TLSChainProprietyCertificate`
- size: `448`
- prototype: `__int64 __usercall@<rax>(unsigned __int64@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180018510`

## callees

- `0x180038d4c`
- `0x180039148`
- `0x18003a030`

## import_xrefs

- `CRYPT32!CertEnumCertificatesInStore` at `0x18003a0d2`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18003a153`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18003a0d2`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18003a153`
- `CRYPT32!CertOpenStore` at `0x18003a09c`
- `CRYPT32!CertOpenStore` at `0x18003a09c`
- `CRYPT32!CertCloseStore` at `0x18003a1c8`
- `CRYPT32!CertCloseStore` at `0x18003a1c8`
- `KERNEL32!GetLastError` at `0x18003a0b0`
- `KERNEL32!GetLastError` at `0x18003a0e3`
- `KERNEL32!GetLastError` at `0x18003a12b`
- `KERNEL32!GetLastError` at `0x18003a1a5`
- `KERNEL32!GetLastError` at `0x18003a0b0`
- `KERNEL32!GetLastError` at `0x18003a0e3`
- `KERNEL32!GetLastError` at `0x18003a12b`
- `KERNEL32!GetLastError` at `0x18003a1a5`
- `KERNEL32!LocalAlloc` at `0x18003a117`
- `KERNEL32!LocalAlloc` at `0x18003a117`
- `KERNEL32!SetLastError` at `0x18003a06c`
- `KERNEL32!SetLastError` at `0x18003a06c`

## pseudocode

```c
__int64 __fastcall TLSChainProprietyCertificate(
        HCRYPTPROV_LEGACY a1,
        int a2,
        __int64 a3,
        int a4,
        struct _Cert_Chain **a5,
        unsigned int *a6)
{
  int v6; // esi
  int v7; // ebp
  DWORD LastError; // ebx
  HCERTSTORE v11; // rdi
  const CERT_CONTEXT *v12; // rdx
  PCCERT_CONTEXT v13; // rax
  unsigned int v14; // eax
  unsigned int *v15; // rbp
  struct _Cert_Chain *v16; // rsi
  DWORD v17; // eax
  const struct _CERT_CONTEXT *v18; // rbx
  PCCERT_CONTEXT v19; // rax
  _DWORD pvPara[2]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v22; // [rsp+38h] [rbp-20h]
  unsigned int v23; // [rsp+78h] [rbp+20h] BYREF

  pvPara[1] = 0;
  v6 = 0;
  v23 = 0;
  v7 = 0;
  v22 = a3;
  pvPara[0] = a4;
  if ( a1 )
  {
    v11 = CertOpenStore("PKCS7", 0x10001u, a1, 1u, pvPara);
    if ( v11 )
    {
      v12 = 0;
      while ( 1 )
      {
        v13 = CertEnumCertificatesInStore(v11, v12);
        if ( !v13 )
          break;
        ++v6;
        v12 = v13;
        v7 += v13->cbCertEncoded;
      }
      LastError = GetLastError();
      if ( LastError == -2146885628 )
      {
        v14 = v7 + 8 * v6 + 16;
        v15 = a6;
        *a6 = v14;
        v16 = (struct _Cert_Chain *)LocalAlloc(0x40u, v14);
        if ( v16 )
        {
          *(_DWORD *)v16 = a2 != 0 ? -2147483646 : 2;
          v18 = 0;
          while ( 1 )
          {
            v19 = CertEnumCertificatesInStore(v11, v18);
            v18 = v19;
            if ( !v19 )
              break;
            if ( (unsigned int)IsHydraClientCertficate(v19->pCertInfo) )
            {
              LastError = ChainProprietyCert(a1, v11, v18, v16, &v23, *v15);
              *a5 = v16;
              goto LABEL_18;
            }
          }
          v17 = GetLastError();
          if ( v17 == -2146885628 )
            v17 = 87;
        }
        else
        {
          v17 = GetLastError();
        }
        LastError = v17;
      }
LABEL_18:
      CertCloseStore(v11, 1u);
    }
    else
    {
      return GetLastError();
    }
  }
  else
  {
    LastError = 87;
    SetLastError(0x57u);
  }
  return LastError;
}

```

## disassembly

```asm
0x18003a030  mov     rax, rsp
0x18003a033  mov     [rax+8], rbx
0x18003a037  mov     [rax+10h], rbp
0x18003a03b  mov     [rax+18h], rsi
0x18003a03f  push    rdi
0x18003a040  push    r14
0x18003a042  push    r15
0x18003a044  sub     rsp, 40h
0x18003a048  and     dword ptr [rax-24h], 0
0x18003a04c  xor     esi, esi
0x18003a04e  and     dword ptr [rax+20h], 0
0x18003a052  xor     ebp, ebp
0x18003a054  mov     [rax-20h], r8
0x18003a058  mov     r14d, edx
0x18003a05b  mov     [rax-28h], r9d
0x18003a05f  mov     r15, rcx
0x18003a062  test    rcx, rcx
0x18003a065  jnz     short loc_18003A07D
0x18003a067  lea     ebx, [rcx+57h]
0x18003a06a  mov     ecx, ebx; dwErrCode
0x18003a06c  call    cs:__imp_SetLastError
0x18003a073  nop     dword ptr [rax+rax+00h]
0x18003a078  jmp     loc_18003A1D4
0x18003a07d  lea     rax, [rsp+58h+var_28]
0x18003a082  mov     r9d, 1; dwFlags
0x18003a088  mov     r8, r15; hCryptProv
0x18003a08b  mov     [rsp+58h+pvPara], rax; pvPara
0x18003a090  mov     edx, 10001h; dwEncodingType
0x18003a095  lea     rcx, szStoreProvider; "PKCS7"
0x18003a09c  call    cs:__imp_CertOpenStore
0x18003a0a3  nop     dword ptr [rax+rax+00h]
0x18003a0a8  mov     rdi, rax
0x18003a0ab  test    rax, rax
0x18003a0ae  jnz     short loc_18003A0C3
0x18003a0b0  call    cs:__imp_GetLastError
0x18003a0b7  nop     dword ptr [rax+rax+00h]
0x18003a0bc  mov     ebx, eax
0x18003a0be  jmp     loc_18003A1D4
0x18003a0c3  xor     edx, edx
0x18003a0c5  jmp     short loc_18003A0CF
0x18003a0c7  inc     esi
0x18003a0c9  mov     rdx, rax; pPrevCertContext
0x18003a0cc  add     ebp, [rax+10h]
0x18003a0cf  mov     rcx, rdi; hCertStore
0x18003a0d2  call    cs:__imp_CertEnumCertificatesInStore
0x18003a0d9  nop     dword ptr [rax+rax+00h]
0x18003a0de  test    rax, rax
0x18003a0e1  jnz     short loc_18003A0C7
0x18003a0e3  call    cs:__imp_GetLastError
0x18003a0ea  nop     dword ptr [rax+rax+00h]
0x18003a0ef  mov     ebx, eax
0x18003a0f1  cmp     eax, 80092004h
0x18003a0f6  jnz     loc_18003A1C0
0x18003a0fc  lea     eax, ds:10h[rsi*8]
0x18003a103  mov     ecx, 40h ; '@'; uFlags
0x18003a108  add     eax, ebp
0x18003a10a  mov     rbp, [rsp+58h+arg_28]
0x18003a112  mov     edx, eax; uBytes
0x18003a114  mov     [rbp+0], eax
0x18003a117  call    cs:__imp_LocalAlloc
0x18003a11e  nop     dword ptr [rax+rax+00h]
0x18003a123  mov     rsi, rax
0x18003a126  test    rax, rax
0x18003a129  jnz     short loc_18003A13C
0x18003a12b  call    cs:__imp_GetLastError
0x18003a132  nop     dword ptr [rax+rax+00h]
0x18003a137  jmp     loc_18003A1BE
0x18003a13c  neg     r14d
0x18003a13f  sbb     eax, eax
0x18003a141  and     eax, 80000000h
0x18003a146  add     eax, 2
0x18003a149  mov     [rsi], eax
0x18003a14b  xor     ebx, ebx
0x18003a14d  mov     rdx, rbx; pPrevCertContext
0x18003a150  mov     rcx, rdi; hCertStore
0x18003a153  call    cs:__imp_CertEnumCertificatesInStore
0x18003a15a  nop     dword ptr [rax+rax+00h]
0x18003a15f  mov     rbx, rax
0x18003a162  test    rax, rax
0x18003a165  jz      short loc_18003A1A5
0x18003a167  mov     rcx, [rax+18h]; struct _CERT_INFO *
0x18003a16b  call    ?IsHydraClientCertficate@@YAHPEAU_CERT_INFO@@@Z; IsHydraClientCertficate(_CERT_INFO *)
0x18003a170  test    eax, eax
0x18003a172  jz      short loc_18003A14D
0x18003a174  mov     eax, [rbp+0]
0x18003a177  mov     r9, rsi; struct _Cert_Chain *
0x18003a17a  mov     [rsp+58h+var_30], eax; unsigned int
0x18003a17e  mov     r8, rbx; struct _CERT_CONTEXT *
0x18003a181  lea     rax, [rsp+58h+arg_18]
0x18003a186  mov     rdx, rdi; void *
0x18003a189  mov     rcx, r15; unsigned __int64
0x18003a18c  mov     [rsp+58h+pvPara], rax; unsigned int *
0x18003a191  call    ?ChainProprietyCert@@YAK_KPEAXPEBU_CERT_CONTEXT@@PEAU_Cert_Chain@@PEAKK@Z; ChainProprietyCert(unsigned __int64,void *,_CERT_CONTEXT const *,_Cert_Chain *,ulong *,ulong)
0x18003a196  mov     ebx, eax
0x18003a198  mov     rax, [rsp+58h+arg_20]
0x18003a1a0  mov     [rax], rsi
0x18003a1a3  jmp     short loc_18003A1C0
0x18003a1a5  call    cs:__imp_GetLastError
0x18003a1ac  nop     dword ptr [rax+rax+00h]
0x18003a1b1  cmp     eax, 80092004h
0x18003a1b6  mov     ebx, 57h ; 'W'
0x18003a1bb  cmovz   eax, ebx
0x18003a1be  mov     ebx, eax
0x18003a1c0  mov     edx, 1; dwFlags
0x18003a1c5  mov     rcx, rdi; hCertStore
0x18003a1c8  call    cs:__imp_CertCloseStore
0x18003a1cf  nop     dword ptr [rax+rax+00h]
0x18003a1d4  mov     rbp, [rsp+58h+arg_8]
0x18003a1d9  mov     eax, ebx
0x18003a1db  mov     rbx, [rsp+58h+arg_0]
0x18003a1e0  mov     rsi, [rsp+58h+arg_10]
0x18003a1e5  add     rsp, 40h
0x18003a1e9  pop     r15
0x18003a1eb  pop     r14
0x18003a1ed  pop     rdi
0x18003a1ee  retn
```
