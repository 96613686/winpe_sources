# RdlsSecretsDBCache::ExtractIssuerAndResetInMemoryCerts(_RdlsCertData *)

- ea: `0x180082740`
- end: `0x1800828cb`
- name: `?ExtractIssuerAndResetInMemoryCerts@RdlsSecretsDBCache@@IEAAKPEAU_RdlsCertData@@@Z`
- size: `395`
- prototype: `unsigned int __fastcall(RdlsSecretsDBCache *__hidden this, struct _RdlsCertData *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180082acc`

## callees

- `0x180022910`
- `0x180082740`

## import_xrefs

- `CRYPT32!CertNameToStrW` at `0x1800827ba`
- `CRYPT32!CertNameToStrW` at `0x18008280f`
- `CRYPT32!CertNameToStrW` at `0x1800827ba`
- `CRYPT32!CertNameToStrW` at `0x18008280f`
- `CRYPT32!CertCreateCertificateContext` at `0x180082785`
- `CRYPT32!CertCreateCertificateContext` at `0x180082785`
- `CRYPT32!CertFreeCertificateContext` at `0x180082876`
- `CRYPT32!CertFreeCertificateContext` at `0x180082876`
- `KERNEL32!LocalAlloc` at `0x1800827dc`
- `KERNEL32!LocalAlloc` at `0x1800827dc`
- `KERNEL32!LocalFree` at `0x18008283f`
- `KERNEL32!LocalFree` at `0x180082858`
- `KERNEL32!LocalFree` at `0x18008283f`
- `KERNEL32!LocalFree` at `0x180082858`

## pseudocode

```c
__int64 __fastcall RdlsSecretsDBCache::ExtractIssuerAndResetInMemoryCerts(
        RdlsSecretsDBCache *this,
        struct _RdlsCertData *a2)
{
  unsigned int v2; // ebx
  const CERT_CONTEXT *v5; // rdi
  const BYTE *v7; // rdx
  PCCERT_CONTEXT CertificateContext; // rax
  DWORD v9; // eax
  DWORD csz; // r14d
  WCHAR *v11; // rax
  WCHAR *v12; // r15
  void *v13; // rcx
  void *v14; // rcx
  struct _EVENT_DESCRIPTOR v15; // [rsp+30h] [rbp-28h] BYREF

  v2 = 0;
  v5 = 0;
  if ( !a2 )
    return 87;
  v7 = (const BYTE *)*((_QWORD *)a2 + 5);
  if ( !v7 )
  {
LABEL_9:
    if ( *((_QWORD *)a2 + 3) && *((_QWORD *)a2 + 5) )
    {
      v13 = (void *)*((_QWORD *)this + 4);
      if ( v13 )
        LocalFree(v13);
      v14 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 4) = 0;
      if ( v14 )
        LocalFree(v14);
      *((_QWORD *)this + 6) = 0;
      *((_DWORD *)this + 6) = 0;
      *((_DWORD *)this + 10) = 0;
    }
    if ( !v5 )
      return v2;
    goto LABEL_17;
  }
  CertificateContext = CertCreateCertificateContext(1u, v7, *((_DWORD *)a2 + 8));
  v5 = CertificateContext;
  if ( CertificateContext )
  {
    v9 = CertNameToStrW(1u, &CertificateContext->pCertInfo->Subject, 0x8000003u, 0, 0);
    csz = v9;
    if ( v9 )
    {
      v11 = (WCHAR *)LocalAlloc(0x40u, 2LL * (v9 + 1));
      v12 = v11;
      if ( v11 )
      {
        CertNameToStrW(1u, &v5->pCertInfo->Subject, 0x8000003u, v11, csz);
        *((_QWORD *)a2 + 1) = v12;
        *((_DWORD *)a2 + 1) = 2 * csz + 2;
        goto LABEL_9;
      }
      v2 = 14;
      v15 = (struct _EVENT_DESCRIPTOR)TLS_E_STORELSCERTIFICATE;
      TLSLogEvent(&v15, 0xC001001B, 14);
    }
    else
    {
      v2 = 13;
    }
LABEL_17:
    CertFreeCertificateContext(v5);
    return v2;
  }
  return 13;
}

```

## disassembly

```asm
0x180082740  mov     [rsp+arg_0], rbx
0x180082745  mov     [rsp+arg_10], rbp
0x18008274a  mov     [rsp+arg_18], rsi
0x18008274f  push    rdi
0x180082750  push    r14
0x180082752  push    r15
0x180082754  sub     rsp, 40h
0x180082758  xor     ebx, ebx
0x18008275a  mov     rbp, rdx
0x18008275d  mov     rsi, rcx
0x180082760  mov     edi, ebx
0x180082762  test    rdx, rdx
0x180082765  jnz     short loc_18008276F
0x180082767  lea     eax, [rdx+57h]
0x18008276a  jmp     loc_180082884
0x18008276f  mov     rdx, [rdx+28h]; pbCertEncoded
0x180082773  test    rdx, rdx
0x180082776  jz      loc_18008282A
0x18008277c  mov     r8d, [rbp+20h]; cbCertEncoded
0x180082780  mov     ecx, 1; dwCertEncodingType
0x180082785  call    cs:__imp_CertCreateCertificateContext
0x18008278c  nop     dword ptr [rax+rax+00h]
0x180082791  mov     rdi, rax
0x180082794  test    rax, rax
0x180082797  jnz     short loc_1800827A1
0x180082799  lea     ebx, [rax+0Dh]
0x18008279c  jmp     loc_180082882
0x1800827a1  mov     rdx, [rax+18h]
0x1800827a5  xor     r9d, r9d; psz
0x1800827a8  add     rdx, 50h ; 'P'; pName
0x1800827ac  mov     [rsp+58h+csz], ebx; csz
0x1800827b0  mov     r8d, 8000003h; dwStrType
0x1800827b6  lea     ecx, [r9+1]; dwCertEncodingType
0x1800827ba  call    cs:__imp_CertNameToStrW
0x1800827c1  nop     dword ptr [rax+rax+00h]
0x1800827c6  mov     r14d, eax
0x1800827c9  test    eax, eax
0x1800827cb  jz      loc_1800828C4
0x1800827d1  lea     edx, [rax+1]
0x1800827d4  mov     ecx, 40h ; '@'; uFlags
0x1800827d9  add     rdx, rdx; uBytes
0x1800827dc  call    cs:__imp_LocalAlloc
0x1800827e3  nop     dword ptr [rax+rax+00h]
0x1800827e8  mov     r15, rax
0x1800827eb  test    rax, rax
0x1800827ee  jz      loc_18008289E
0x1800827f4  mov     rdx, [rdi+18h]
0x1800827f8  mov     r9, rax; psz
0x1800827fb  add     rdx, 50h ; 'P'; pName
0x1800827ff  mov     [rsp+58h+csz], r14d; csz
0x180082804  mov     ecx, 1; dwCertEncodingType
0x180082809  mov     r8d, 8000003h; dwStrType
0x18008280f  call    cs:__imp_CertNameToStrW
0x180082816  nop     dword ptr [rax+rax+00h]
0x18008281b  lea     eax, ds:2[r14*2]
0x180082823  mov     [rbp+8], r15
0x180082827  mov     [rbp+4], eax
0x18008282a  cmp     [rbp+18h], rbx
0x18008282e  jz      short loc_18008286E
0x180082830  cmp     [rbp+28h], rbx
0x180082834  jz      short loc_18008286E
0x180082836  mov     rcx, [rsi+20h]; hMem
0x18008283a  test    rcx, rcx
0x18008283d  jz      short loc_18008284B
0x18008283f  call    cs:__imp_LocalFree
0x180082846  nop     dword ptr [rax+rax+00h]
0x18008284b  mov     rcx, [rsi+30h]; hMem
0x18008284f  mov     [rsi+20h], rbx
0x180082853  test    rcx, rcx
0x180082856  jz      short loc_180082864
0x180082858  call    cs:__imp_LocalFree
0x18008285f  nop     dword ptr [rax+rax+00h]
0x180082864  mov     [rsi+30h], rbx
0x180082868  mov     [rsi+18h], ebx
0x18008286b  mov     [rsi+28h], ebx
0x18008286e  test    rdi, rdi
0x180082871  jz      short loc_180082882
0x180082873  mov     rcx, rdi; pCertContext
0x180082876  call    cs:__imp_CertFreeCertificateContext
0x18008287d  nop     dword ptr [rax+rax+00h]
0x180082882  mov     eax, ebx
0x180082884  mov     rbx, [rsp+58h+arg_0]
0x180082889  mov     rbp, [rsp+58h+arg_10]
0x18008288e  mov     rsi, [rsp+58h+arg_18]
0x180082893  add     rsp, 40h
0x180082897  pop     r15
0x180082899  pop     r14
0x18008289b  pop     rdi
0x18008289c  retn
0x18008289e  movups  xmm0, cs:TLS_E_STORELSCERTIFICATE
0x1800828a5  mov     ebx, 0Eh
0x1800828aa  lea     rcx, [rsp+58h+var_28]; struct _EVENT_DESCRIPTOR
0x1800828af  mov     r8d, ebx
0x1800828b2  mov     edx, 0C001001Bh; unsigned int
0x1800828b7  movdqu  xmmword ptr [rsp+58h+var_28.Id], xmm0
0x1800828bd  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x1800828c2  jmp     short loc_180082873
0x1800828c4  mov     ebx, 0Dh
0x1800828c9  jmp     short loc_180082873
```
