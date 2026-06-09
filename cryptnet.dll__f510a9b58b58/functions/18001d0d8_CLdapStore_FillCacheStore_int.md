# CLdapStore::FillCacheStore(int)

- ea: `0x18001d0d8`
- end: `0x18001d224`
- name: `?FillCacheStore@CLdapStore@@AEAAHH@Z`
- size: `332`
- prototype: `__int64 __fastcall(CLdapStore *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d5d0`
- `0x18001d698`

## callees

- `0x180011134`
- `0x180012ec0`
- `0x1800185a0`
- `0x18001d0d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d202`
- `CRYPT32!I_CertUpdateStore` at `0x18001d1c8`
- `CRYPT32!I_CertUpdateStore` at `0x18001d1c8`
- `CRYPT32!CertDeleteCTLFromStore` at `0x18001d14a`
- `CRYPT32!CertDeleteCTLFromStore` at `0x18001d14a`
- `CRYPT32!CertCloseStore` at `0x18001d1d6`
- `CRYPT32!CertCloseStore` at `0x18001d1d6`
- `CRYPT32!CertDeleteCRLFromStore` at `0x18001d128`
- `CRYPT32!CertDeleteCRLFromStore` at `0x18001d128`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18001d10d`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18001d10d`
- `CRYPT32!CertGetCRLFromStore` at `0x18001d13a`
- `CRYPT32!CertGetCRLFromStore` at `0x18001d13a`
- `CRYPT32!CertEnumCTLsInStore` at `0x18001d155`
- `CRYPT32!CertEnumCTLsInStore` at `0x18001d155`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18001d118`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18001d118`

## pseudocode

```c
__int64 __fastcall CLdapStore::FillCacheStore(CLdapStore *this, int a2)
{
  void *v3; // rbx
  const CERT_CONTEXT *v4; // rax
  const CRL_CONTEXT *CRLFromStore; // rax
  const CTL_CONTEXT *v6; // rax
  unsigned int updated; // ebx
  __int64 v9[2]; // [rsp+30h] [rbp-30h] BYREF
  int v10; // [rsp+40h] [rbp-20h] BYREF
  __int64 v11; // [rsp+48h] [rbp-18h]
  int v12; // [rsp+50h] [rbp-10h]
  int v13; // [rsp+54h] [rbp-Ch]
  DWORD pdwFlags; // [rsp+88h] [rbp+28h] BYREF
  HCERTSTORE hCertStore; // [rsp+90h] [rbp+30h] BYREF

  *(_OWORD *)v9 = 0;
  if ( a2 == 1 )
  {
    v3 = (void *)*((_QWORD *)this + 13);
    pdwFlags = 0;
    while ( 1 )
    {
      v4 = CertEnumCertificatesInStore(v3, 0);
      if ( !v4 )
        break;
      CertDeleteCertificateFromStore(v4);
    }
    while ( 1 )
    {
      CRLFromStore = CertGetCRLFromStore(v3, 0, 0, &pdwFlags);
      if ( !CRLFromStore )
        break;
      CertDeleteCRLFromStore(CRLFromStore);
    }
    while ( 1 )
    {
      v6 = CertEnumCTLsInStore(v3, 0);
      if ( !v6 )
        break;
      CertDeleteCTLFromStore(v6);
    }
  }
  if ( (unsigned int)LdapSendReceiveUrlRequest(*((LDAP **)this + 12), (__int64)v9, 0) )
  {
    hCertStore = 0;
    updated = CreateObjectContext(1, v9, 8462, 0, &hCertStore);
    if ( updated )
    {
      updated = I_CertUpdateStore(*((_QWORD *)this + 13), hCertStore, 0, 0);
      CertCloseStore(hCertStore, 0);
    }
    v10 = v9[0];
    v12 = v9[0];
    v13 = 0;
    v11 = v9[1];
    CCryptBlobArray::FreeArray((CCryptBlobArray *)&v10, 1);
  }
  else
  {
    return GetLastError() == -2146885628;
  }
  return updated;
}

```

## disassembly

```asm
0x18001d0d8  mov     [rsp-18h+arg_0], rbx
0x18001d0dd  push    rbp
0x18001d0de  push    rdi
0x18001d0df  push    r14
0x18001d0e1  mov     rbp, rsp
0x18001d0e4  sub     rsp, 60h
0x18001d0e8  mov     r14d, 1
0x18001d0ee  xorps   xmm0, xmm0
0x18001d0f1  mov     rdi, rcx
0x18001d0f4  movups  xmmword ptr [rbp+var_30], xmm0
0x18001d0f8  cmp     edx, r14d
0x18001d0fb  jnz     short loc_18001D160
0x18001d0fd  mov     rbx, [rcx+68h]
0x18001d101  mov     [rbp+pdwFlags], 0
0x18001d108  jmp     short loc_18001D113
0x18001d10a  mov     rcx, rax; pCertContext
0x18001d10d  call    cs:__imp_CertDeleteCertificateFromStore
0x18001d113  xor     edx, edx; pPrevCertContext
0x18001d115  mov     rcx, rbx; hCertStore
0x18001d118  call    cs:__imp_CertEnumCertificatesInStore
0x18001d11e  test    rax, rax
0x18001d121  jnz     short loc_18001D10A
0x18001d123  jmp     short loc_18001D12E
0x18001d125  mov     rcx, rax; pCrlContext
0x18001d128  call    cs:__imp_CertDeleteCRLFromStore
0x18001d12e  lea     r9, [rbp+pdwFlags]; pdwFlags
0x18001d132  xor     r8d, r8d; pPrevCrlContext
0x18001d135  xor     edx, edx; pIssuerContext
0x18001d137  mov     rcx, rbx; hCertStore
0x18001d13a  call    cs:__imp_CertGetCRLFromStore
0x18001d140  test    rax, rax
0x18001d143  jnz     short loc_18001D125
0x18001d145  jmp     short loc_18001D150
0x18001d147  mov     rcx, rax; pCtlContext
0x18001d14a  call    cs:__imp_CertDeleteCTLFromStore
0x18001d150  xor     edx, edx; pPrevCtlContext
0x18001d152  mov     rcx, rbx; hCertStore
0x18001d155  call    cs:__imp_CertEnumCTLsInStore
0x18001d15b  test    rax, rax
0x18001d15e  jnz     short loc_18001D147
0x18001d160  mov     rcx, [rdi+60h]; ld
0x18001d164  lea     rax, [rbp+var_30]
0x18001d168  lea     rdx, [rdi+28h]
0x18001d16c  mov     [rsp+60h+var_38], 0; __int64
0x18001d175  mov     r9d, 3A98h
0x18001d17b  mov     [rsp+60h+var_40], rax; __int64
0x18001d180  xor     r8d, r8d
0x18001d183  call    LdapSendReceiveUrlRequest
0x18001d188  mov     ebx, eax
0x18001d18a  test    eax, eax
0x18001d18c  jz      short loc_18001D202
0x18001d18e  lea     rax, [rbp+hCertStore]
0x18001d192  mov     [rbp+hCertStore], 0
0x18001d19a  xor     r9d, r9d
0x18001d19d  mov     [rsp+60h+var_40], rax
0x18001d1a2  mov     r8d, 210Eh
0x18001d1a8  lea     rdx, [rbp+var_30]
0x18001d1ac  mov     ecx, r14d
0x18001d1af  call    CreateObjectContext
0x18001d1b4  mov     ebx, eax
0x18001d1b6  test    eax, eax
0x18001d1b8  jz      short loc_18001D1DC
0x18001d1ba  mov     rdx, [rbp+hCertStore]
0x18001d1be  xor     r9d, r9d
0x18001d1c1  mov     rcx, [rdi+68h]
0x18001d1c5  xor     r8d, r8d
0x18001d1c8  call    cs:__imp_I_CertUpdateStore
0x18001d1ce  mov     rcx, [rbp+hCertStore]; hCertStore
0x18001d1d2  xor     edx, edx; dwFlags
0x18001d1d4  mov     ebx, eax
0x18001d1d6  call    cs:__imp_CertCloseStore
0x18001d1dc  mov     ecx, dword ptr [rbp+var_30]
0x18001d1df  mov     edx, r14d; int
0x18001d1e2  mov     rax, [rbp+var_30+8]
0x18001d1e6  mov     [rbp+var_20], ecx
0x18001d1e9  mov     [rbp+var_10], ecx
0x18001d1ec  lea     rcx, [rbp+var_20]; this
0x18001d1f0  mov     [rbp+var_C], 0
0x18001d1f7  mov     [rbp+var_18], rax
0x18001d1fb  call    ?FreeArray@CCryptBlobArray@@QEAAXH@Z; CCryptBlobArray::FreeArray(int)
0x18001d200  jmp     short loc_18001D211
0x18001d202  call    cs:__imp_GetLastError
0x18001d208  cmp     eax, 80092004h
0x18001d20d  cmovz   ebx, r14d
0x18001d211  mov     eax, ebx
0x18001d213  mov     rbx, [rsp+60h+arg_0]
0x18001d21b  add     rsp, 60h
0x18001d21f  pop     r14
0x18001d221  pop     rdi
0x18001d222  pop     rbp
0x18001d223  retn
```
