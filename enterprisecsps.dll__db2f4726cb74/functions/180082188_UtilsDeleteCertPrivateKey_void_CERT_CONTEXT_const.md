# UtilsDeleteCertPrivateKey(void *,_CERT_CONTEXT const *)

- ea: `0x180082188`
- end: `0x180082464`
- name: `?UtilsDeleteCertPrivateKey@@YAJPEAXPEBU_CERT_CONTEXT@@@Z`
- size: `732`
- prototype: `__int64 __fastcall(HCERTSTORE hCertStore, PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180081dec`

## callees

- `0x180082188`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800823d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800823f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800823d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800823f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082439`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082448`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082439`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082448`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800821ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180082263`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800821ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180082263`
- `CRYPT32!CertFreeCertificateContext` at `0x1800823bf`
- `CRYPT32!CertFreeCertificateContext` at `0x1800823bf`
- `CRYPT32!CertFindCertificateInStore` at `0x1800822bf`
- `CRYPT32!CertFindCertificateInStore` at `0x1800822ef`
- `CRYPT32!CertFindCertificateInStore` at `0x1800822bf`
- `CRYPT32!CertFindCertificateInStore` at `0x1800822ef`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800821ce`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180082217`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180082239`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180082287`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800821ce`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180082217`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180082239`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180082287`
- `CRYPT32!CryptSetKeyIdentifierProperty` at `0x18008233d`
- `CRYPT32!CryptSetKeyIdentifierProperty` at `0x18008233d`
- `ncrypt!NCryptOpenStorageProvider` at `0x180082354`
- `ncrypt!NCryptOpenStorageProvider` at `0x180082354`
- `ncrypt!NCryptFreeObject` at `0x180082414`
- `ncrypt!NCryptFreeObject` at `0x180082429`
- `ncrypt!NCryptFreeObject` at `0x180082414`
- `ncrypt!NCryptFreeObject` at `0x180082429`
- `ncrypt!NCryptDeleteKey` at `0x180082397`
- `ncrypt!NCryptDeleteKey` at `0x180082397`
- `ncrypt!NCryptOpenKey` at `0x18008237f`
- `ncrypt!NCryptOpenKey` at `0x18008237f`

## pseudocode

```c
__int64 __fastcall UtilsDeleteCertPrivateKey(HCERTSTORE hCertStore, PCCERT_CONTEXT pCertContext)
{
  HLOCAL v2; // rdi
  int v5; // ebx
  HLOCAL v6; // rax
  HLOCAL v7; // rax
  const CERT_CONTEXT *pPrevCertContext; // rax
  const CERT_CONTEXT *CertificateInStore; // rbx
  SECURITY_STATUS v10; // eax
  signed int LastError; // eax
  signed int v12; // eax
  DWORD pvFindPara[4]; // [rsp+30h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+28h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+70h] [rbp+30h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+78h] [rbp+38h] BYREF

  v2 = 0;
  phProvider = 0;
  phKey = 0;
  pcbData = 0;
  *(_OWORD *)pvFindPara = 0;
  if ( !pCertContext )
  {
    v5 = -2147418113;
    goto LABEL_32;
  }
  if ( !CertGetCertificateContextProperty(pCertContext, 2u, 0, &pcbData) )
  {
    v5 = 0;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError == -2146885628 )
      goto LABEL_28;
    goto LABEL_26;
  }
  v6 = LocalAlloc(0x40u, pcbData);
  v2 = v6;
  if ( !v6 )
  {
LABEL_5:
    v5 = -2147024882;
    goto LABEL_28;
  }
  if ( !CertGetCertificateContextProperty(pCertContext, 2u, v6, &pcbData)
    || !CertGetCertificateContextProperty(pCertContext, 0x14u, 0, pvFindPara) )
  {
    goto LABEL_26;
  }
  if ( !pvFindPara[0] )
  {
    v5 = -2147418113;
    goto LABEL_28;
  }
  v7 = LocalAlloc(0, pvFindPara[0]);
  *(_QWORD *)&pvFindPara[2] = v7;
  if ( !v7 )
    goto LABEL_5;
  if ( !CertGetCertificateContextProperty(pCertContext, 0x14u, v7, pvFindPara) )
  {
LABEL_26:
    v12 = GetLastError();
    v5 = v12;
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_28;
  }
  pPrevCertContext = CertFindCertificateInStore(hCertStore, 1u, 0, 0xF0000u, pvFindPara, 0);
  if ( !pPrevCertContext )
  {
LABEL_22:
    v5 = 0;
LABEL_28:
    if ( phKey )
      NCryptFreeObject(phKey);
    goto LABEL_30;
  }
  CertificateInStore = CertFindCertificateInStore(hCertStore, 1u, 0, 0xF0000u, pvFindPara, pPrevCertContext);
  if ( CertificateInStore || GetLastError() != -2146885628 )
  {
    CertFreeCertificateContext(CertificateInStore);
    goto LABEL_22;
  }
  CryptSetKeyIdentifierProperty((const CRYPT_HASH_BLOB *)pvFindPara, 0, *((_DWORD *)v2 + 5) & 0x20 | 0x10, 0, 0, 0);
  v5 = NCryptOpenStorageProvider(&phProvider, *((LPCWSTR *)v2 + 1), 0);
  if ( v5 < 0 )
    goto LABEL_28;
  v10 = NCryptOpenKey(phProvider, &phKey, *(LPCWSTR *)v2, 0, *((_DWORD *)v2 + 5));
  v5 = v10;
  if ( v10 )
  {
    if ( v10 != -2146893802 )
      goto LABEL_28;
    goto LABEL_22;
  }
  v5 = NCryptDeleteKey(phKey, 0);
  if ( v5 < 0 )
    goto LABEL_28;
  phKey = 0;
LABEL_30:
  if ( phProvider )
    NCryptFreeObject(phProvider);
LABEL_32:
  LocalFree(*(HLOCAL *)&pvFindPara[2]);
  LocalFree(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180082188  mov     [rsp-18h+arg_0], rbx
0x18008218d  push    rbp
0x18008218e  push    rsi
0x18008218f  push    rdi
0x180082190  mov     rbp, rsp
0x180082193  sub     rsp, 40h
0x180082197  xor     edi, edi
0x180082199  xorps   xmm0, xmm0
0x18008219c  mov     [rbp+phProvider], rdi
0x1800821a0  mov     rbx, rdx
0x1800821a3  mov     [rbp+phKey], rdi
0x1800821a7  mov     rsi, rcx
0x1800821aa  mov     [rbp+pcbData], edi
0x1800821ad  movups  xmmword ptr [rbp+var_10], xmm0
0x1800821b1  test    rdx, rdx
0x1800821b4  jnz     short loc_1800821C0
0x1800821b6  mov     ebx, 8000FFFFh
0x1800821bb  jmp     loc_180082435
0x1800821c0  xor     r8d, r8d; pvData
0x1800821c3  lea     r9, [rbp+pcbData]; pcbData
0x1800821c7  mov     rcx, rbx; pCertContext
0x1800821ca  lea     edx, [r8+2]; dwPropId
0x1800821ce  call    cs:__imp_CertGetCertificateContextProperty
0x1800821d5  nop     dword ptr [rax+rax+00h]
0x1800821da  test    eax, eax
0x1800821dc  jz      loc_1800823CF
0x1800821e2  mov     edx, [rbp+pcbData]; uBytes
0x1800821e5  mov     ecx, 40h ; '@'; uFlags
0x1800821ea  call    cs:__imp_LocalAlloc
0x1800821f1  nop     dword ptr [rax+rax+00h]
0x1800821f6  mov     rdi, rax
0x1800821f9  test    rax, rax
0x1800821fc  jnz     short loc_180082208
0x1800821fe  mov     ebx, 8007000Eh
0x180082203  jmp     loc_18008240B
0x180082208  lea     r9, [rbp+pcbData]; pcbData
0x18008220c  mov     r8, rdi; pvData
0x18008220f  mov     edx, 2; dwPropId
0x180082214  mov     rcx, rbx; pCertContext
0x180082217  call    cs:__imp_CertGetCertificateContextProperty
0x18008221e  nop     dword ptr [rax+rax+00h]
0x180082223  test    eax, eax
0x180082225  jz      loc_1800823F0
0x18008222b  xor     r8d, r8d; pvData
0x18008222e  lea     r9, [rbp+var_10]; pcbData
0x180082232  mov     rcx, rbx; pCertContext
0x180082235  lea     edx, [r8+14h]; dwPropId
0x180082239  call    cs:__imp_CertGetCertificateContextProperty
0x180082240  nop     dword ptr [rax+rax+00h]
0x180082245  test    eax, eax
0x180082247  jz      loc_1800823F0
0x18008224d  mov     eax, [rbp+var_10]
0x180082250  test    eax, eax
0x180082252  jnz     short loc_18008225E
0x180082254  mov     ebx, 8000FFFFh
0x180082259  jmp     loc_18008240B
0x18008225e  mov     rdx, rax; uBytes
0x180082261  xor     ecx, ecx; uFlags
0x180082263  call    cs:__imp_LocalAlloc
0x18008226a  nop     dword ptr [rax+rax+00h]
0x18008226f  mov     qword ptr [rbp+var_10+8], rax
0x180082273  test    rax, rax
0x180082276  jz      short loc_1800821FE
0x180082278  lea     r9, [rbp+var_10]; pcbData
0x18008227c  mov     r8, rax; pvData
0x18008227f  mov     edx, 14h; dwPropId
0x180082284  mov     rcx, rbx; pCertContext
0x180082287  call    cs:__imp_CertGetCertificateContextProperty
0x18008228e  nop     dword ptr [rax+rax+00h]
0x180082293  test    eax, eax
0x180082295  jz      loc_1800823F0
0x18008229b  xor     r8d, r8d; dwFindFlags
0x18008229e  mov     [rsp+40h+pPrevCertContext], 0; pPrevCertContext
0x1800822a7  lea     rax, [rbp+var_10]
0x1800822ab  mov     ebx, 0F0000h
0x1800822b0  mov     r9d, ebx; dwFindType
0x1800822b3  mov     [rsp+40h+pvFindPara], rax; pvFindPara
0x1800822b8  mov     rcx, rsi; hCertStore
0x1800822bb  lea     edx, [r8+1]; dwCertEncodingType
0x1800822bf  call    cs:__imp_CertFindCertificateInStore
0x1800822c6  nop     dword ptr [rax+rax+00h]
0x1800822cb  test    rax, rax
0x1800822ce  jz      loc_1800823CB
0x1800822d4  mov     [rsp+40h+pPrevCertContext], rax; pPrevCertContext
0x1800822d9  xor     r8d, r8d; dwFindFlags
0x1800822dc  lea     rax, [rbp+var_10]
0x1800822e0  mov     r9d, ebx; dwFindType
0x1800822e3  mov     rcx, rsi; hCertStore
0x1800822e6  mov     [rsp+40h+pvFindPara], rax; pvFindPara
0x1800822eb  lea     edx, [r8+1]; dwCertEncodingType
0x1800822ef  call    cs:__imp_CertFindCertificateInStore
0x1800822f6  nop     dword ptr [rax+rax+00h]
0x1800822fb  mov     rbx, rax
0x1800822fe  test    rax, rax
0x180082301  jnz     loc_1800823BC
0x180082307  call    cs:__imp_GetLastError
0x18008230e  nop     dword ptr [rax+rax+00h]
0x180082313  cmp     eax, 80092004h
0x180082318  jnz     loc_1800823BC
0x18008231e  mov     r8d, [rdi+14h]
0x180082322  lea     rcx, [rbp+var_10]; pKeyIdentifier
0x180082326  and     r8d, 20h
0x18008232a  mov     [rsp+40h+pPrevCertContext], rbx; pvData
0x18008232f  or      r8d, 10h; dwFlags
0x180082333  mov     [rsp+40h+pvFindPara], rbx; pvReserved
0x180082338  xor     r9d, r9d; pwszComputerName
0x18008233b  xor     edx, edx; dwPropId
0x18008233d  call    cs:__imp_CryptSetKeyIdentifierProperty
0x180082344  nop     dword ptr [rax+rax+00h]
0x180082349  mov     rdx, [rdi+8]; pszProviderName
0x18008234d  lea     rcx, [rbp+phProvider]; phProvider
0x180082351  xor     r8d, r8d; dwFlags
0x180082354  call    cs:__imp_NCryptOpenStorageProvider
0x18008235b  nop     dword ptr [rax+rax+00h]
0x180082360  mov     ebx, eax
0x180082362  test    eax, eax
0x180082364  js      loc_18008240B
0x18008236a  mov     eax, [rdi+14h]
0x18008236d  lea     rdx, [rbp+phKey]; phKey
0x180082371  mov     r8, [rdi]; pszKeyName
0x180082374  xor     r9d, r9d; dwLegacyKeySpec
0x180082377  mov     rcx, [rbp+phProvider]; hProvider
0x18008237b  mov     dword ptr [rsp+40h+pvFindPara], eax; dwFlags
0x18008237f  call    cs:__imp_NCryptOpenKey
0x180082386  nop     dword ptr [rax+rax+00h]
0x18008238b  mov     ebx, eax
0x18008238d  test    eax, eax
0x18008238f  jnz     short loc_1800823B3
0x180082391  mov     rcx, [rbp+phKey]; hKey
0x180082395  xor     edx, edx; dwFlags
0x180082397  call    cs:__imp_NCryptDeleteKey
0x18008239e  nop     dword ptr [rax+rax+00h]
0x1800823a3  mov     ebx, eax
0x1800823a5  test    eax, eax
0x1800823a7  js      short loc_18008240B
0x1800823a9  mov     [rbp+phKey], 0
0x1800823b1  jmp     short loc_180082420
0x1800823b3  cmp     eax, 80090016h
0x1800823b8  jnz     short loc_18008240B
0x1800823ba  jmp     short loc_1800823CB
0x1800823bc  mov     rcx, rbx; pCertContext
0x1800823bf  call    cs:__imp_CertFreeCertificateContext
0x1800823c6  nop     dword ptr [rax+rax+00h]
0x1800823cb  xor     ebx, ebx
0x1800823cd  jmp     short loc_18008240B
0x1800823cf  xor     ebx, ebx
0x1800823d1  call    cs:__imp_GetLastError
0x1800823d8  nop     dword ptr [rax+rax+00h]
0x1800823dd  test    eax, eax
0x1800823df  jle     short loc_1800823E9
0x1800823e1  movzx   eax, ax
0x1800823e4  or      eax, 80070000h
0x1800823e9  cmp     eax, 80092004h
0x1800823ee  jz      short loc_18008240B
0x1800823f0  call    cs:__imp_GetLastError
0x1800823f7  nop     dword ptr [rax+rax+00h]
0x1800823fc  mov     ebx, eax
0x1800823fe  test    eax, eax
0x180082400  jle     short loc_18008240B
0x180082402  movzx   ebx, ax
0x180082405  or      ebx, 80070000h
0x18008240b  mov     rcx, [rbp+phKey]; hObject
0x18008240f  test    rcx, rcx
0x180082412  jz      short loc_180082420
0x180082414  call    cs:__imp_NCryptFreeObject
0x18008241b  nop     dword ptr [rax+rax+00h]
0x180082420  mov     rcx, [rbp+phProvider]; hObject
0x180082424  test    rcx, rcx
0x180082427  jz      short loc_180082435
0x180082429  call    cs:__imp_NCryptFreeObject
0x180082430  nop     dword ptr [rax+rax+00h]
0x180082435  mov     rcx, qword ptr [rbp+var_10+8]; hMem
0x180082439  call    cs:__imp_LocalFree
0x180082440  nop     dword ptr [rax+rax+00h]
0x180082445  mov     rcx, rdi; hMem
0x180082448  call    cs:__imp_LocalFree
0x18008244f  nop     dword ptr [rax+rax+00h]
0x180082454  mov     eax, ebx
0x180082456  mov     rbx, [rsp+40h+arg_0]
0x18008245b  add     rsp, 40h
0x18008245f  pop     rdi
0x180082460  pop     rsi
0x180082461  pop     rbp
0x180082462  retn
```
