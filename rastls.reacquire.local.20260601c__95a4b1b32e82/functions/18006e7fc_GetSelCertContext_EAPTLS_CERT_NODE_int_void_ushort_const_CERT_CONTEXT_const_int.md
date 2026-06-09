# GetSelCertContext(_EAPTLS_CERT_NODE *,int,void * *,ushort const *,_CERT_CONTEXT const * *,int)

- ea: `0x18006e7fc`
- end: `0x18006e945`
- name: `?GetSelCertContext@@YAKPEAU_EAPTLS_CERT_NODE@@HPEAPEAXPEBGPEAPEBU_CERT_CONTEXT@@H@Z`
- size: `329`
- prototype: `unsigned int(struct _EAPTLS_CERT_NODE *, int, void **, const unsigned __int16 *, const struct _CERT_CONTEXT **, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18006aae8`
- `0x18006bad8`
- `0x1800716f8`

## callees

- `0x18005db88`
- `0x18006e7fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e8e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e8e4`
- `CRYPT32!CertCloseStore` at `0x18006e926`
- `CRYPT32!CertCloseStore` at `0x18006e926`
- `CRYPT32!CertFindCertificateInStore` at `0x18006e8d0`
- `CRYPT32!CertFindCertificateInStore` at `0x18006e8d0`
- `CRYPT32!CertFreeCertificateContext` at `0x18006e906`
- `CRYPT32!CertFreeCertificateContext` at `0x18006e906`
- `CRYPT32!CertOpenStore` at `0x18006e847`
- `CRYPT32!CertOpenStore` at `0x18006e847`

## pseudocode

```c
__int64 __fastcall GetSelCertContext(
        struct _EAPTLS_CERT_NODE *a1,
        __int64 a2,
        void **a3,
        const unsigned __int16 *pvPara,
        const struct _CERT_CONTEXT **a5,
        int a6)
{
  HCERTSTORE v8; // rax
  DWORD v9; // ebx
  DWORD LastError; // eax
  PCCERT_CONTEXT CertificateInStore; // rdi
  __int128 pvFindPara; // [rsp+30h] [rbp-18h] BYREF

  pvFindPara = 0;
  if ( !a1 )
  {
    v9 = 1168;
LABEL_11:
    if ( *a3 )
      CertCloseStore(*a3, 1u);
    return v9;
  }
  v8 = CertOpenStore((LPCSTR)0xA, 0, 0, a6 != 0 ? 163840 : 98304, pvPara);
  *a3 = v8;
  if ( !v8 )
  {
    v9 = -2143158256;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      LastError = GetLastError();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 191, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, LastError);
    }
    goto LABEL_11;
  }
  v9 = 0;
  LODWORD(pvFindPara) = *((_DWORD *)a1 + 2);
  *((_QWORD *)&pvFindPara + 1) = (char *)a1 + 12;
  CertificateInStore = CertFindCertificateInStore(v8, 0, 0, 0x10000u, &pvFindPara, 0);
  if ( !CertificateInStore )
    v9 = GetLastError();
  *a5 = CertificateInStore;
  if ( v9 )
  {
    if ( CertificateInStore )
      CertFreeCertificateContext(CertificateInStore);
    goto LABEL_11;
  }
  return v9;
}

```

## disassembly

```asm
0x18006e7fc  mov     [rsp+arg_0], rbx
0x18006e801  mov     [rsp+arg_8], rsi
0x18006e806  push    rdi
0x18006e807  sub     rsp, 40h
0x18006e80b  xorps   xmm0, xmm0
0x18006e80e  mov     rax, r9
0x18006e811  mov     rsi, r8
0x18006e814  mov     rdi, rcx
0x18006e817  movups  [rsp+48h+pvFindPara], xmm0
0x18006e81c  test    rcx, rcx
0x18006e81f  jz      loc_18006E914
0x18006e825  neg     [rsp+48h+arg_28]
0x18006e829  mov     [rsp+48h+pvPara], rax; pvPara
0x18006e82e  sbb     r9d, r9d
0x18006e831  xor     edx, edx; dwEncodingType
0x18006e833  and     r9d, 10000h
0x18006e83a  xor     r8d, r8d; hCryptProv
0x18006e83d  add     r9d, 18000h; dwFlags
0x18006e844  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18006e847  call    cs:__imp_CertOpenStore
0x18006e84e  nop     dword ptr [rax+rax+00h]
0x18006e853  mov     [rsi], rax
0x18006e856  mov     rcx, rax; hCertStore
0x18006e859  test    rax, rax
0x18006e85c  jnz     short loc_18006E8A4
0x18006e85e  mov     ebx, 80420010h
0x18006e863  lea     rax, WPP_GLOBAL_Control
0x18006e86a  cmp     cs:WPP_GLOBAL_Control, rax
0x18006e871  jz      loc_18006E919
0x18006e877  call    cs:__imp_GetLastError
0x18006e87e  nop     dword ptr [rax+rax+00h]
0x18006e883  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e88a  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006e891  mov     edx, 0BFh
0x18006e896  mov     r9d, eax
0x18006e899  mov     rcx, [rcx+10h]
0x18006e89d  call    WPP_SF_Dd
0x18006e8a2  jmp     short loc_18006E919
0x18006e8a4  mov     eax, [rdi+8]
0x18006e8a7  xor     ebx, ebx
0x18006e8a9  mov     dword ptr [rsp+48h+pvFindPara], eax
0x18006e8ad  mov     r9d, 10000h; dwFindType
0x18006e8b3  lea     rax, [rdi+0Ch]
0x18006e8b7  mov     [rsp+48h+pPrevCertContext], rbx; pPrevCertContext
0x18006e8bc  mov     qword ptr [rsp+48h+pvFindPara+8], rax
0x18006e8c1  xor     r8d, r8d; dwFindFlags
0x18006e8c4  lea     rax, [rsp+48h+pvFindPara]
0x18006e8c9  xor     edx, edx; dwCertEncodingType
0x18006e8cb  mov     [rsp+48h+pvPara], rax; pvFindPara
0x18006e8d0  call    cs:__imp_CertFindCertificateInStore
0x18006e8d7  nop     dword ptr [rax+rax+00h]
0x18006e8dc  mov     rdi, rax
0x18006e8df  test    rax, rax
0x18006e8e2  jnz     short loc_18006E8F2
0x18006e8e4  call    cs:__imp_GetLastError
0x18006e8eb  nop     dword ptr [rax+rax+00h]
0x18006e8f0  mov     ebx, eax
0x18006e8f2  mov     rcx, [rsp+48h+arg_20]
0x18006e8f7  mov     [rcx], rdi
0x18006e8fa  test    ebx, ebx
0x18006e8fc  jz      short loc_18006E932
0x18006e8fe  test    rdi, rdi
0x18006e901  jz      short loc_18006E919
0x18006e903  mov     rcx, rdi; pCertContext
0x18006e906  call    cs:__imp_CertFreeCertificateContext
0x18006e90d  nop     dword ptr [rax+rax+00h]
0x18006e912  jmp     short loc_18006E919
0x18006e914  mov     ebx, 490h
0x18006e919  mov     rcx, [rsi]; hCertStore
0x18006e91c  test    rcx, rcx
0x18006e91f  jz      short loc_18006E932
0x18006e921  mov     edx, 1; dwFlags
0x18006e926  call    cs:__imp_CertCloseStore
0x18006e92d  nop     dword ptr [rax+rax+00h]
0x18006e932  mov     rsi, [rsp+48h+arg_8]
0x18006e937  mov     eax, ebx
0x18006e939  mov     rbx, [rsp+48h+arg_0]
0x18006e93e  add     rsp, 40h
0x18006e942  pop     rdi
0x18006e943  retn
```
