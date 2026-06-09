# LSVerifyDecodeClientLicense

- ea: `0x18006464c`
- end: `0x1800648dd`
- name: `LSVerifyDecodeClientLicense`
- size: `657`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, int *, _QWORD *Base)`
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180010050`
- `0x180010b60`
- `0x1800168b0`
- `0x180018be0`
- `0x18001ce5c`

## callees

- `0x180002b98`
- `0x18006366c`
- `0x180063e5c`
- `0x180063ed0`
- `0x180063fa0`
- `0x1800644c0`
- `0x18006464c`

## import_xrefs

- `CRYPT32!CertEnumCertificatesInStore` at `0x180064708`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180064708`
- `CRYPT32!CertOpenStore` at `0x1800646ea`
- `CRYPT32!CertOpenStore` at `0x1800646ea`
- `CRYPT32!CertCloseStore` at `0x180064850`
- `CRYPT32!CertCloseStore` at `0x180064850`
- `KERNEL32!GetLastError` at `0x180064823`
- `KERNEL32!GetLastError` at `0x180064860`
- `KERNEL32!GetLastError` at `0x180064823`
- `KERNEL32!GetLastError` at `0x180064860`
- `KERNEL32!SetLastError` at `0x1800646bd`
- `KERNEL32!SetLastError` at `0x18006483c`
- `KERNEL32!SetLastError` at `0x1800646bd`
- `KERNEL32!SetLastError` at `0x18006483c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LSVerifyDecodeClientLicense(__int64 a1, int a2, __int64 a3, int a4, int *a5, _QWORD *Base)
{
  unsigned int v6; // ebx
  int *v7; // rsi
  const struct _CERT_CONTEXT *v8; // r14
  _QWORD *v9; // rbp
  unsigned __int8 *v10; // rax
  unsigned int v11; // r13d
  DWORD LastError; // edi
  HCERTSTORE v13; // r15
  PCCERT_CONTEXT v14; // rax
  unsigned int ClientLicenseVersion; // eax
  unsigned __int64 v16; // rcx
  unsigned int v17; // r12d
  unsigned __int64 v18; // rcx
  int i; // r14d
  _DWORD pvPara[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v22; // [rsp+38h] [rbp-40h]
  unsigned int v23; // [rsp+88h] [rbp+10h]
  unsigned __int8 *v24; // [rsp+90h] [rbp+18h]
  int v25; // [rsp+98h] [rbp+20h] BYREF

  v25 = a4;
  v6 = 0;
  v7 = a5;
  v8 = 0;
  v9 = Base;
  v23 = g_cbSecretKey;
  v10 = (unsigned __int8 *)g_pbSecretKey;
  v11 = *a5;
  *a5 = 0;
  pvPara[1] = 0;
  v22 = a1;
  v24 = v10;
  pvPara[0] = a2;
  if ( !g_hCertUtilCryptProv )
  {
    LastError = 87;
    SetLastError(0x57u);
LABEL_25:
    for ( i = *v7; i >= 0; LSFreeLicensedProduct(&v9[23 * (unsigned int)i--]) )
    {
      if ( !v9 )
        break;
    }
    goto LABEL_31;
  }
  v13 = CertOpenStore("PKCS7", 0x10001u, g_hCertUtilCryptProv, 1u, pvPara);
  if ( !v13 )
    goto LABEL_23;
  while ( 1 )
  {
    v14 = CertEnumCertificatesInStore(v13, v8);
    v8 = v14;
    if ( !v14 )
      break;
    ClientLicenseVersion = GetClientLicenseVersion(v14->pCertInfo->rgExtension, v14->pCertInfo->cExtension);
    v17 = ClientLicenseVersion;
    if ( ClientLicenseVersion == 131073 )
    {
      LastError = 59;
      goto LABEL_22;
    }
    if ( ClientLicenseVersion != -1 )
    {
      LastError = LSVerifyTlsCertificate(v16, v8, v13);
      if ( LastError )
        goto LABEL_22;
      if ( v9 && *v7 < v11 )
      {
        LastError = DecodeLicense20(v8->pCertInfo, v24, v23, (struct _LicensedProduct *)&v9[23 * (unsigned int)*v7]);
        if ( LastError )
          goto LABEL_22;
        if ( v17 == 327681 )
        {
          v18 = *(unsigned int *)(v9[23 * (unsigned int)*v7 + 7] + 4LL);
          if ( (*(_DWORD *)(v9[23 * (unsigned int)*v7 + 7] + 4LL) & 0x700000u) <= 0x500000
            && (v18 & 0xF0000) <= 0x20000
            && (v18 & 0x80000000) == 0LL )
          {
            v25 = 0;
            LastError = IsW2kLicenseIssuerNonEnforce(v18, v8, v13, &v25);
            if ( LastError )
              goto LABEL_22;
            if ( !v25 )
              *(_DWORD *)(v9[23 * (unsigned int)*v7 + 7] + 4LL) |= 0x8000u;
          }
        }
      }
      ++*v7;
    }
  }
  LastError = GetLastError();
  if ( LastError == -2146885628 )
  {
    LastError = 0;
    SetLastError(0);
  }
LABEL_22:
  if ( !CertCloseStore(v13, 1u) )
LABEL_23:
    LastError = GetLastError();
  if ( LastError )
    goto LABEL_25;
  if ( v9 )
    qsort_0(v9, (unsigned int)*v7, 0xB8u, SortLicensedProduct);
LABEL_31:
  if ( !*v7 || LastError )
    return 31;
  return v6;
}

```

## disassembly

```asm
0x18006464c  mov     r11, rsp
0x18006464f  mov     [r11+8], rbx
0x180064653  mov     [r11+20h], r9d
0x180064657  mov     [r11+18h], r8
0x18006465b  push    rbp
0x18006465c  push    rsi
0x18006465d  push    rdi
0x18006465e  push    r12
0x180064660  push    r13
0x180064662  push    r14
0x180064664  push    r15
0x180064666  sub     rsp, 40h
0x18006466a  mov     eax, cs:?g_cbSecretKey@@3KA; ulong g_cbSecretKey
0x180064670  xor     ebx, ebx
0x180064672  mov     rsi, [rsp+78h+arg_20]
0x18006467a  mov     r14d, ebx
0x18006467d  mov     rbp, [rsp+78h+Base]
0x180064685  mov     [rsp+78h+arg_8], eax
0x18006468c  mov     rax, cs:?g_pbSecretKey@@3PEAEEA; uchar * g_pbSecretKey
0x180064693  mov     r13d, [rsi]
0x180064696  mov     [rsi], ebx
0x180064698  mov     r8, cs:?g_hCertUtilCryptProv@@3_KA; hCryptProv
0x18006469f  mov     [rsp+78h+var_44], ebx
0x1800646a3  mov     [r11-40h], rcx
0x1800646a7  mov     [rsp+78h+arg_10], rax
0x1800646af  mov     [rsp+78h+var_48], edx
0x1800646b3  test    r8, r8
0x1800646b6  jnz     short loc_1800646CE
0x1800646b8  lea     edi, [rbx+57h]
0x1800646bb  mov     ecx, edi; dwErrCode
0x1800646bd  call    cs:__imp_SetLastError
0x1800646c4  nop     dword ptr [rax+rax+00h]
0x1800646c9  jmp     loc_180064872
0x1800646ce  lea     rax, [rsp+78h+var_48]
0x1800646d3  mov     edx, 10001h; dwEncodingType
0x1800646d8  mov     r9d, 1; dwFlags
0x1800646de  mov     [rsp+78h+pvPara], rax; pvPara
0x1800646e3  lea     rcx, szStoreProvider; "PKCS7"
0x1800646ea  call    cs:__imp_CertOpenStore
0x1800646f1  nop     dword ptr [rax+rax+00h]
0x1800646f6  mov     r15, rax
0x1800646f9  test    rax, rax
0x1800646fc  jz      loc_180064860
0x180064702  mov     rdx, r14; pPrevCertContext
0x180064705  mov     rcx, r15; hCertStore
0x180064708  call    cs:__imp_CertEnumCertificatesInStore
0x18006470f  nop     dword ptr [rax+rax+00h]
0x180064714  mov     r14, rax
0x180064717  test    rax, rax
0x18006471a  jz      loc_180064823
0x180064720  mov     rcx, [rax+18h]
0x180064724  mov     edx, [rcx+0C0h]; unsigned int
0x18006472a  mov     rcx, [rcx+0C8h]; struct _CERT_EXTENSION *
0x180064731  call    ?GetClientLicenseVersion@@YAKPEAU_CERT_EXTENSION@@K@Z; GetClientLicenseVersion(_CERT_EXTENSION *,ulong)
0x180064736  mov     r12d, eax
0x180064739  cmp     eax, 20001h
0x18006473e  jz      loc_18006481C
0x180064744  cmp     eax, 0FFFFFFFFh
0x180064747  jz      short loc_180064702
0x180064749  mov     r8, r15; void *
0x18006474c  mov     rdx, r14; struct _CERT_CONTEXT *
0x18006474f  call    ?LSVerifyTlsCertificate@@YAK_KPEBU_CERT_CONTEXT@@PEAX@Z; LSVerifyTlsCertificate(unsigned __int64,_CERT_CONTEXT const *,void *)
0x180064754  mov     edi, eax
0x180064756  test    eax, eax
0x180064758  jnz     loc_180064848
0x18006475e  test    rbp, rbp
0x180064761  jz      loc_180064815
0x180064767  cmp     [rsi], r13d
0x18006476a  jnb     loc_180064815
0x180064770  mov     eax, [rsi]
0x180064772  mov     r8d, [rsp+78h+arg_8]; unsigned int
0x18006477a  mov     rdx, [rsp+78h+arg_10]; unsigned __int8 *
0x180064782  mov     rcx, [r14+18h]; struct _CERT_INFO *
0x180064786  imul    r9, rax, 0B8h
0x18006478d  add     r9, rbp; struct _LicensedProduct *
0x180064790  call    ?DecodeLicense20@@YAKPEAU_CERT_INFO@@PEAEKPEAU_LicensedProduct@@@Z; DecodeLicense20(_CERT_INFO *,uchar *,ulong,_LicensedProduct *)
0x180064795  mov     edi, eax
0x180064797  test    eax, eax
0x180064799  jnz     loc_180064848
0x18006479f  cmp     r12d, 50001h
0x1800647a6  jnz     short loc_180064815
0x1800647a8  mov     eax, [rsi]
0x1800647aa  imul    rcx, rax, 0B8h
0x1800647b1  mov     rax, [rcx+rbp+38h]
0x1800647b6  mov     ecx, [rax+4]; unsigned __int64
0x1800647b9  mov     eax, ecx
0x1800647bb  and     eax, 700000h
0x1800647c0  cmp     eax, 500000h
0x1800647c5  ja      short loc_180064815
0x1800647c7  mov     eax, ecx
0x1800647c9  and     eax, 0F0000h
0x1800647ce  cmp     eax, 20000h
0x1800647d3  ja      short loc_180064815
0x1800647d5  test    ecx, ecx
0x1800647d7  js      short loc_180064815
0x1800647d9  lea     r9, [rsp+78h+arg_18]; int *
0x1800647e1  mov     [rsp+78h+arg_18], ebx
0x1800647e8  mov     r8, r15; void *
0x1800647eb  mov     rdx, r14; struct _CERT_CONTEXT *
0x1800647ee  call    ?IsW2kLicenseIssuerNonEnforce@@YAK_KPEBU_CERT_CONTEXT@@PEAXPEAH@Z; IsW2kLicenseIssuerNonEnforce(unsigned __int64,_CERT_CONTEXT const *,void *,int *)
0x1800647f3  mov     edi, eax
0x1800647f5  test    eax, eax
0x1800647f7  jnz     short loc_180064848
0x1800647f9  cmp     [rsp+78h+arg_18], ebx
0x180064800  jnz     short loc_180064815
0x180064802  mov     eax, [rsi]
0x180064804  imul    rcx, rax, 0B8h
0x18006480b  mov     rax, [rcx+rbp+38h]
0x180064810  bts     dword ptr [rax+4], 0Fh
0x180064815  inc     dword ptr [rsi]
0x180064817  jmp     loc_180064702
0x18006481c  mov     edi, 3Bh ; ';'
0x180064821  jmp     short loc_180064848
0x180064823  call    cs:__imp_GetLastError
0x18006482a  nop     dword ptr [rax+rax+00h]
0x18006482f  mov     edi, eax
0x180064831  cmp     eax, 80092004h
0x180064836  jnz     short loc_180064848
0x180064838  xor     ecx, ecx; dwErrCode
0x18006483a  mov     edi, ebx
0x18006483c  call    cs:__imp_SetLastError
0x180064843  nop     dword ptr [rax+rax+00h]
0x180064848  mov     edx, 1; dwFlags
0x18006484d  mov     rcx, r15; hCertStore
0x180064850  call    cs:__imp_CertCloseStore
0x180064857  nop     dword ptr [rax+rax+00h]
0x18006485c  test    eax, eax
0x18006485e  jnz     short loc_18006486E
0x180064860  call    cs:__imp_GetLastError
0x180064867  nop     dword ptr [rax+rax+00h]
0x18006486c  mov     edi, eax
0x18006486e  test    edi, edi
0x180064870  jz      short loc_180064899
0x180064872  mov     r14d, [rsi]
0x180064875  test    r14d, r14d
0x180064878  js      short loc_1800648B5
0x18006487a  test    rbp, rbp
0x18006487d  jz      short loc_1800648B5
0x18006487f  mov     eax, r14d
0x180064882  imul    rcx, rax, 0B8h
0x180064889  add     rcx, rbp
0x18006488c  call    LSFreeLicensedProduct
0x180064891  sub     r14d, 1
0x180064895  jns     short loc_18006487A
0x180064897  jmp     short loc_1800648B5
0x180064899  test    rbp, rbp
0x18006489c  jz      short loc_1800648B5
0x18006489e  mov     edx, [rsi]; NumOfElements
0x1800648a0  lea     r9, ?SortLicensedProduct@@YAHPEBX0@Z; CompareFunction
0x1800648a7  mov     r8d, 0B8h; SizeOfElements
0x1800648ad  mov     rcx, rbp; Base
0x1800648b0  call    qsort_0
0x1800648b5  cmp     [rsi], ebx
0x1800648b7  jz      short loc_1800648BD
0x1800648b9  test    edi, edi
0x1800648bb  jz      short loc_1800648C2
0x1800648bd  mov     ebx, 1Fh
0x1800648c2  mov     eax, ebx
0x1800648c4  mov     rbx, [rsp+78h+arg_0]
0x1800648cc  add     rsp, 40h
0x1800648d0  pop     r15
0x1800648d2  pop     r14
0x1800648d4  pop     r13
0x1800648d6  pop     r12
0x1800648d8  pop     rdi
0x1800648d9  pop     rsi
0x1800648da  pop     rbp
0x1800648db  retn
```
