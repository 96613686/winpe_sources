# AEUpdateCertificateStore(ldap *,ushort *,ushort *,ushort *)

- ea: `0x180006b10`
- end: `0x180006d51`
- name: `?AEUpdateCertificateStore@@YAJPEAUldap@@PEAG11@Z`
- size: `577`
- prototype: `__int64 __fastcall(struct ldap *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180003d10`

## callees

- `0x1800027e0`
- `0x180006b10`
- `0x1800070e4`
- `0x18000740c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c39`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006b8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006b8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d18`
- `CRYPT32!CertOpenStore` at `0x180006bd9`
- `CRYPT32!CertOpenStore` at `0x180006c2b`
- `CRYPT32!CertOpenStore` at `0x180006bd9`
- `CRYPT32!CertOpenStore` at `0x180006c2b`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180006c80`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180006cc9`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180006c80`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180006cc9`
- `CRYPT32!CertFreeCertificateContext` at `0x180006c5f`
- `CRYPT32!CertFreeCertificateContext` at `0x180006ca9`
- `CRYPT32!CertFreeCertificateContext` at `0x180006c5f`
- `CRYPT32!CertFreeCertificateContext` at `0x180006ca9`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180006c74`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180006c74`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180006cbd`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180006cbd`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180006cb4`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180006cb4`
- `CRYPT32!CertCloseStore` at `0x180006d28`
- `CRYPT32!CertCloseStore` at `0x180006d38`
- `CRYPT32!CertCloseStore` at `0x180006d28`
- `CRYPT32!CertCloseStore` at `0x180006d38`

## pseudocode

```c
__int64 __fastcall AEUpdateCertificateStore(
        struct ldap *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  HCERTSTORE v8; // rbp
  HCERTSTORE v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // r15
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // r14
  unsigned int v15; // ebx
  signed int LastError; // eax
  const CERT_CONTEXT *i; // rdx
  const CERT_CONTEXT *CertificateInOtherStore; // rax
  const CERT_CONTEXT *v19; // rdi
  const CERT_CONTEXT *v20; // rdx
  void *v21; // rcx
  const CERT_CONTEXT *v22; // rax
  const CERT_CONTEXT *v23; // rax
  const CERT_CONTEXT *v24; // rax
  const CERT_CONTEXT *v25; // rdi
  __int128 v27; // [rsp+50h] [rbp-58h] BYREF

  v8 = 0;
  v9 = 0;
  v27 = 0;
  if ( !a1 || !a2 || !a3 || !a4 )
  {
    v14 = 0;
    v15 = -2147024809;
    goto LABEL_34;
  }
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( a4[v11] );
  do
    ++v10;
  while ( a2[v10] );
  v12 = v11 + v10 + 1;
  v13 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v12);
  v14 = v13;
  if ( !v13 )
  {
    v15 = -2147024882;
    goto LABEL_34;
  }
  v15 = StringCchPrintfW(v13, v12, a4, a2);
  if ( v15 )
  {
LABEL_34:
    AELogAutoEnrollmentEvent(2, 1, v15, 1073741825, 1, 0, 2);
    if ( !v14 )
      goto LABEL_36;
    goto LABEL_35;
  }
  v9 = CertOpenStore((LPCSTR)0xD, 0, 0, 0x90000u, a3);
  if ( v9 )
  {
    *(_QWORD *)&v27 = a1;
    *((_QWORD *)&v27 + 1) = v14;
    v8 = CertOpenStore((LPCSTR)0x10, 0, 0, 0x58000u, &v27);
    if ( v8 )
    {
      for ( i = 0; ; i = v19 )
      {
        v19 = CertEnumCertificatesInStore(v8, i);
        v20 = v19;
        v21 = v9;
        if ( !v19 )
          break;
        CertificateInOtherStore = FindCertificateInOtherStore(v9, v19);
        if ( CertificateInOtherStore )
          CertFreeCertificateContext(CertificateInOtherStore);
        else
          CertAddCertificateContextToStore(v9, v19, 4u, 0);
      }
      while ( 1 )
      {
        v24 = CertEnumCertificatesInStore(v21, v20);
        v25 = v24;
        if ( !v24 )
          break;
        v22 = FindCertificateInOtherStore(v8, v24);
        if ( v22 )
        {
          CertFreeCertificateContext(v22);
        }
        else
        {
          v23 = CertDuplicateCertificateContext(v25);
          CertDeleteCertificateFromStore(v23);
        }
        v20 = v25;
        v21 = v9;
      }
      goto LABEL_35;
    }
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError == 2 )
    {
      v15 = 0;
      goto LABEL_35;
    }
  }
  else
  {
    LastError = GetLastError();
    v15 = LastError;
  }
  if ( LastError > 0 )
    v15 = (unsigned __int16)LastError | 0x80070000;
  if ( v15 )
    goto LABEL_34;
LABEL_35:
  LocalFree(v14);
LABEL_36:
  if ( v8 )
    CertCloseStore(v8, 0);
  if ( v9 )
    CertCloseStore(v9, 0);
  return v15;
}

```

## disassembly

```asm
0x180006b10  push    rbx
0x180006b12  push    rbp
0x180006b13  push    rsi
0x180006b14  push    rdi
0x180006b15  push    r12
0x180006b17  push    r13
0x180006b19  push    r14
0x180006b1b  push    r15
0x180006b1d  sub     rsp, 68h
0x180006b21  xor     r15d, r15d
0x180006b24  xorps   xmm0, xmm0
0x180006b27  mov     rbx, r9
0x180006b2a  mov     r12, r8
0x180006b2d  mov     rdi, rdx
0x180006b30  mov     r13, rcx
0x180006b33  mov     ebp, r15d
0x180006b36  mov     esi, r15d
0x180006b39  movups  [rsp+0A8h+var_58], xmm0
0x180006b3e  test    rcx, rcx
0x180006b41  jz      loc_180006CD9
0x180006b47  test    rdx, rdx
0x180006b4a  jz      loc_180006CD9
0x180006b50  test    r8, r8
0x180006b53  jz      loc_180006CD9
0x180006b59  test    rbx, rbx
0x180006b5c  jz      loc_180006CD9
0x180006b62  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006b66  mov     rcx, rax
0x180006b69  inc     rcx
0x180006b6c  cmp     [r9+rcx*2], r15w
0x180006b71  jnz     short loc_180006B69
0x180006b73  inc     rax
0x180006b76  cmp     [rdx+rax*2], r15w
0x180006b7b  jnz     short loc_180006B73
0x180006b7d  lea     r15, [rax+1]
0x180006b81  add     r15, rcx
0x180006b84  mov     ecx, 40h ; '@'; uFlags
0x180006b89  lea     rdx, [r15+r15]; uBytes
0x180006b8d  call    cs:__imp_LocalAlloc
0x180006b93  mov     r14, rax
0x180006b96  test    rax, rax
0x180006b99  jnz     short loc_180006BA8
0x180006b9b  mov     ebx, 8007000Eh
0x180006ba0  xor     r15d, r15d
0x180006ba3  jmp     loc_180006CE1
0x180006ba8  mov     r9, rdi
0x180006bab  mov     r8, rbx; unsigned __int16 *
0x180006bae  mov     rdx, r15; unsigned __int64
0x180006bb1  mov     rcx, r14; unsigned __int16 *
0x180006bb4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006bb9  xor     r15d, r15d
0x180006bbc  mov     ebx, eax
0x180006bbe  test    eax, eax
0x180006bc0  jnz     loc_180006CE1
0x180006bc6  mov     r9d, 90000h; dwFlags
0x180006bcc  mov     [rsp+0A8h+pvPara], r12; pvPara
0x180006bd1  xor     r8d, r8d; hCryptProv
0x180006bd4  lea     ecx, [rax+0Dh]; lpszStoreProvider
0x180006bd7  xor     edx, edx; dwEncodingType
0x180006bd9  call    cs:__imp_CertOpenStore
0x180006bdf  mov     rsi, rax
0x180006be2  test    rax, rax
0x180006be5  jnz     short loc_180006C09
0x180006be7  call    cs:__imp_GetLastError
0x180006bed  mov     ebx, eax
0x180006bef  test    eax, eax
0x180006bf1  jle     short loc_180006BFC
0x180006bf3  movzx   ebx, ax
0x180006bf6  or      ebx, 80070000h
0x180006bfc  test    ebx, ebx
0x180006bfe  jz      loc_180006D15
0x180006c04  jmp     loc_180006CE1
0x180006c09  xor     edx, edx; dwEncodingType
0x180006c0b  mov     qword ptr [rsp+0A8h+var_58], r13
0x180006c10  lea     rax, [rsp+0A8h+var_58]
0x180006c15  mov     qword ptr [rsp+0A8h+var_58+8], r14
0x180006c1a  mov     r9d, 58000h; dwFlags
0x180006c20  mov     [rsp+0A8h+pvPara], rax; pvPara
0x180006c25  xor     r8d, r8d; hCryptProv
0x180006c28  lea     ecx, [rdx+10h]; lpszStoreProvider
0x180006c2b  call    cs:__imp_CertOpenStore
0x180006c31  mov     rbp, rax
0x180006c34  test    rax, rax
0x180006c37  jnz     short loc_180006C4E
0x180006c39  call    cs:__imp_GetLastError
0x180006c3f  mov     ebx, eax
0x180006c41  cmp     eax, 2
0x180006c44  jnz     short loc_180006BEF
0x180006c46  mov     ebx, r15d
0x180006c49  jmp     loc_180006D15
0x180006c4e  xor     edx, edx
0x180006c50  jmp     short loc_180006C7D
0x180006c52  call    ?FindCertificateInOtherStore@@YAPEBU_CERT_CONTEXT@@PEAXPEBU1@@Z; FindCertificateInOtherStore(void *,_CERT_CONTEXT const *)
0x180006c57  test    rax, rax
0x180006c5a  jz      short loc_180006C67
0x180006c5c  mov     rcx, rax; pCertContext
0x180006c5f  call    cs:__imp_CertFreeCertificateContext
0x180006c65  jmp     short loc_180006C7A
0x180006c67  xor     r9d, r9d; ppStoreContext
0x180006c6a  mov     rdx, rdi; pCertContext
0x180006c6d  mov     rcx, rsi; hCertStore
0x180006c70  lea     r8d, [r9+4]; dwAddDisposition
0x180006c74  call    cs:__imp_CertAddCertificateContextToStore
0x180006c7a  mov     rdx, rdi; pPrevCertContext
0x180006c7d  mov     rcx, rbp; hCertStore
0x180006c80  call    cs:__imp_CertEnumCertificatesInStore
0x180006c86  mov     rdi, rax
0x180006c89  mov     rdx, rax; pCertContext
0x180006c8c  mov     rcx, rsi; hCertStore
0x180006c8f  test    rax, rax
0x180006c92  jnz     short loc_180006C52
0x180006c94  jmp     short loc_180006CC9
0x180006c96  mov     rdx, rdi; pCertContext
0x180006c99  mov     rcx, rbp; hCertStore
0x180006c9c  call    ?FindCertificateInOtherStore@@YAPEBU_CERT_CONTEXT@@PEAXPEBU1@@Z; FindCertificateInOtherStore(void *,_CERT_CONTEXT const *)
0x180006ca1  test    rax, rax
0x180006ca4  jz      short loc_180006CB1
0x180006ca6  mov     rcx, rax; pCertContext
0x180006ca9  call    cs:__imp_CertFreeCertificateContext
0x180006caf  jmp     short loc_180006CC3
0x180006cb1  mov     rcx, rdi; pCertContext
0x180006cb4  call    cs:__imp_CertDuplicateCertificateContext
0x180006cba  mov     rcx, rax; pCertContext
0x180006cbd  call    cs:__imp_CertDeleteCertificateFromStore
0x180006cc3  mov     rdx, rdi; pPrevCertContext
0x180006cc6  mov     rcx, rsi; hCertStore
0x180006cc9  call    cs:__imp_CertEnumCertificatesInStore
0x180006ccf  mov     rdi, rax
0x180006cd2  test    rax, rax
0x180006cd5  jnz     short loc_180006C96
0x180006cd7  jmp     short loc_180006D15
0x180006cd9  mov     r14, r15
0x180006cdc  mov     ebx, 80070057h
0x180006ce1  mov     [rsp+0A8h+var_68], r14
0x180006ce6  mov     edi, 2
0x180006ceb  mov     [rsp+0A8h+var_70], r12
0x180006cf0  mov     r9d, 40000001h
0x180006cf6  mov     [rsp+0A8h+var_78], edi
0x180006cfa  mov     r8d, ebx
0x180006cfd  mov     [rsp+0A8h+var_80], r15
0x180006d02  mov     ecx, edi
0x180006d04  lea     edx, [rdi-1]
0x180006d07  mov     dword ptr [rsp+0A8h+pvPara], edx
0x180006d0b  call    AELogAutoEnrollmentEvent
0x180006d10  test    r14, r14
0x180006d13  jz      short loc_180006D1E
0x180006d15  mov     rcx, r14; hMem
0x180006d18  call    cs:__imp_LocalFree
0x180006d1e  test    rbp, rbp
0x180006d21  jz      short loc_180006D2E
0x180006d23  xor     edx, edx; dwFlags
0x180006d25  mov     rcx, rbp; hCertStore
0x180006d28  call    cs:__imp_CertCloseStore
0x180006d2e  test    rsi, rsi
0x180006d31  jz      short loc_180006D3E
0x180006d33  xor     edx, edx; dwFlags
0x180006d35  mov     rcx, rsi; hCertStore
0x180006d38  call    cs:__imp_CertCloseStore
0x180006d3e  mov     eax, ebx
0x180006d40  add     rsp, 68h
0x180006d44  pop     r15
0x180006d46  pop     r14
0x180006d48  pop     r13
0x180006d4a  pop     r12
0x180006d4c  pop     rdi
0x180006d4d  pop     rsi
0x180006d4e  pop     rbp
0x180006d4f  pop     rbx
0x180006d50  retn
```
