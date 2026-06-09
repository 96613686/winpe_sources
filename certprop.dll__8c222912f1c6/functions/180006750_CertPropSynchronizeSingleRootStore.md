# CertPropSynchronizeSingleRootStore

- ea: `0x180006750`
- end: `0x180006a30`
- name: `CertPropSynchronizeSingleRootStore`
- size: `736`
- prototype: `DWORD __fastcall(__int64, HANDLE *, unsigned int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800061c0`

## callees

- `0x180004600`
- `0x180006750`
- `0x180017a9c`
- `0x180018b58`
- `0x1800214a8`
- `0x180021848`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069b1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800067dd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800067dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006844`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006933`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006933`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800069fa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800069fa`
- `CRYPT32!CertCloseStore` at `0x1800069f4`
- `CRYPT32!CertCloseStore` at `0x1800069f4`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000685e`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000685e`
- `CRYPT32!CertFreeCertificateContext` at `0x1800069e4`
- `CRYPT32!CertFreeCertificateContext` at `0x1800069e4`
- `CRYPT32!CertOpenStore` at `0x180006831`
- `CRYPT32!CertOpenStore` at `0x180006831`

## pseudocode

```c
DWORD __fastcall CertPropSynchronizeSingleRootStore(__int64 a1, HANDLE *a2, unsigned int a3, int a4)
{
  int v4; // esi
  HANDLE *v5; // r15
  const CERT_CONTEXT *v9; // rbp
  void *v10; // rdi
  int LastError; // ebx
  const CERT_CONTEXT *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD *v15; // rbp
  unsigned int v16; // edi
  __int64 v17; // rdx
  HANDLE *v18; // r13
  BOOL v19; // eax
  __int64 v20; // rcx
  void *v21; // r13
  LPVOID lpMem; // [rsp+38h] [rbp-70h] BYREF
  unsigned __int64 v23; // [rsp+40h] [rbp-68h]
  HCERTSTORE v24; // [rsp+48h] [rbp-60h]
  PCCERT_CONTEXT pCertContext; // [rsp+50h] [rbp-58h]
  _QWORD pvPara[3]; // [rsp+58h] [rbp-50h] BYREF
  int v27; // [rsp+B0h] [rbp+8h] BYREF
  int v28; // [rsp+B4h] [rbp+Ch]
  unsigned int v29; // [rsp+C0h] [rbp+18h]

  v29 = a3;
  v28 = HIDWORD(a1);
  v4 = g_RootsCleanupOption;
  v5 = (HANDLE *)g_pSessionList;
  lpMem = 0;
  v27 = 0;
  WppTraceIndent(a1, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids, WPP_pszIndent);
  }
  if ( !v4 )
    return 0;
  if ( !SetThreadToken(0, a2[52]) )
    return GetLastError();
  pvPara[1] = L"SmartCardRootCtrl";
  pvPara[0] = -2147483647;
  v9 = 0;
  v24 = CertOpenStore((LPCSTR)0xD, 0, 0, 0xC0011000, pvPara);
  v10 = v24;
  if ( v24 )
  {
    LastError = 0;
    while ( 1 )
    {
      while ( 1 )
      {
LABEL_12:
        v12 = CertEnumCertificatesInStore(v10, v9);
        pCertContext = v12;
        v9 = v12;
        if ( !v12 )
        {
LABEL_36:
          CertCloseStore(v10, 0);
          goto LABEL_37;
        }
        if ( a4 != 1 || v4 != 1 )
          break;
        LastError = CertPropDeleteRootCertFromStore(v12, a2[52]);
        if ( LastError )
          goto LABEL_35;
        v9 = 0;
      }
      LastError = RootInfoGet(v14, v13, v12, &lpMem, (unsigned int *)&v27);
      if ( LastError )
      {
LABEL_35:
        CertFreeCertificateContext(v9);
        if ( !v10 )
          goto LABEL_37;
        goto LABEL_36;
      }
      v29 = 0;
      v23 = (unsigned int)v27 / 0x18uLL;
      if ( !v23 )
        goto LABEL_32;
      v15 = lpMem;
      v16 = 0;
      LODWORD(v17) = 0;
      do
      {
        v18 = v5;
        if ( !v5 )
          goto LABEL_27;
        while ( (HANDLE)v15[3 * v16 + 2] != v18[74] )
        {
          v18 = (HANDLE *)*v18;
          if ( !v18 )
            goto LABEL_27;
        }
        v19 = EqualSid(v18[75], a2[75]);
        v17 = v29;
        if ( !v19 || v4 == 1 && v18 == a2 )
        {
LABEL_27:
          v20 = 3LL * v16;
          v17 = (unsigned int)(v17 + 1);
          *(_OWORD *)&v15[v20] = 0;
          v29 = v17;
          v15[v20 + 2] = 0;
        }
        ++v16;
      }
      while ( v16 < v23 );
      v10 = v24;
      v9 = pCertContext;
      if ( !(_DWORD)v17 )
        goto LABEL_32;
      if ( (unsigned int)v17 == v23 )
        break;
      v21 = lpMem;
      RootInfoSet(v23, v17, pCertContext, (BYTE *)lpMem, v27);
LABEL_33:
      HeapFree(g_hHeap, 0, v21);
      lpMem = 0;
    }
    CertPropDeleteRootCertFromStore(pCertContext, a2[52]);
    v9 = 0;
LABEL_32:
    v21 = lpMem;
    goto LABEL_33;
  }
  LastError = GetLastError();
  if ( !LastError )
    goto LABEL_12;
LABEL_37:
  RevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x180006750  mov     rax, rsp
0x180006753  mov     [rax+18h], r8d
0x180006757  mov     [rax+8], rcx
0x18000675b  push    rbx
0x18000675c  push    rsi
0x18000675d  push    r12
0x18000675f  push    r13
0x180006761  push    r14
0x180006763  push    r15
0x180006765  sub     rsp, 78h
0x180006769  mov     esi, cs:g_RootsCleanupOption
0x18000676f  xor     r13d, r13d
0x180006772  mov     r15, cs:g_pSessionList
0x180006779  mov     r14, rdx
0x18000677c  mov     edx, 2
0x180006781  mov     [rax-70h], r13
0x180006785  mov     [rax+8], r13d
0x180006789  mov     r12d, r9d
0x18000678c  call    WppTraceIndent
0x180006791  mov     rcx, cs:WPP_GLOBAL_Control
0x180006798  lea     rax, WPP_GLOBAL_Control
0x18000679f  cmp     rcx, rax
0x1800067a2  jz      short loc_1800067CC
0x1800067a4  test    byte ptr [rcx+1Ch], 1
0x1800067a8  jz      short loc_1800067CC
0x1800067aa  cmp     byte ptr [rcx+19h], 4
0x1800067ae  jb      short loc_1800067CC
0x1800067b0  mov     r9, cs:WPP_pszIndent
0x1800067b7  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x1800067be  mov     rcx, [rcx+10h]
0x1800067c2  mov     edx, 12h
0x1800067c7  call    WPP_SF_s
0x1800067cc  test    esi, esi
0x1800067ce  jz      loc_180006A1E
0x1800067d4  mov     rdx, [r14+1A0h]; Token
0x1800067db  xor     ecx, ecx; Thread
0x1800067dd  call    cs:__imp_SetThreadToken
0x1800067e3  test    eax, eax
0x1800067e5  jnz     short loc_1800067F2
0x1800067e7  call    cs:__imp_GetLastError
0x1800067ed  jmp     loc_180006A21
0x1800067f2  lea     rax, aSmartcardrootc_0; "SmartCardRootCtrl"
0x1800067f9  mov     [rsp+0A8h+arg_8], rbp
0x180006801  mov     [rsp+0A8h+var_48], rax
0x180006806  mov     r9d, 0C0011000h; dwFlags
0x18000680c  lea     rax, [rsp+0A8h+var_50]
0x180006811  mov     [rsp+0A8h+var_38], rdi
0x180006816  xor     r8d, r8d; hCryptProv
0x180006819  mov     [rsp+0A8h+pvPara], rax; pvPara
0x18000681e  xor     edx, edx; dwEncodingType
0x180006820  mov     [rsp+0A8h+var_50], 0FFFFFFFF80000001h
0x180006829  mov     ecx, 0Dh; lpszStoreProvider
0x18000682e  mov     rbp, r13
0x180006831  call    cs:__imp_CertOpenStore
0x180006837  mov     [rsp+0A8h+var_60], rax
0x18000683c  mov     rdi, rax
0x18000683f  test    rax, rax
0x180006842  jnz     short loc_180006855
0x180006844  call    cs:__imp_GetLastError
0x18000684a  mov     ebx, eax
0x18000684c  test    eax, eax
0x18000684e  jz      short loc_180006858
0x180006850  jmp     loc_1800069FA
0x180006855  mov     ebx, r13d
0x180006858  mov     rdx, rbp; pPrevCertContext
0x18000685b  mov     rcx, rdi; hCertStore
0x18000685e  call    cs:__imp_CertEnumCertificatesInStore
0x180006864  mov     [rsp+0A8h+pCertContext], rax
0x180006869  mov     rbp, rax
0x18000686c  test    rax, rax
0x18000686f  jz      loc_1800069EF
0x180006875  cmp     r12d, 1
0x180006879  jnz     short loc_18000689E
0x18000687b  cmp     esi, r12d
0x18000687e  jnz     short loc_18000689E
0x180006880  mov     rdx, [r14+1A0h]; Token
0x180006887  mov     rcx, rax; pCertContext
0x18000688a  call    CertPropDeleteRootCertFromStore
0x18000688f  mov     ebx, eax
0x180006891  test    eax, eax
0x180006893  jnz     loc_1800069E1
0x180006899  mov     rbp, r13
0x18000689c  jmp     short loc_180006858
0x18000689e  lea     rax, [rsp+0A8h+arg_0]
0x1800068a6  mov     r8, rbp
0x1800068a9  lea     r9, [rsp+0A8h+lpMem]
0x1800068ae  mov     [rsp+0A8h+pvPara], rax
0x1800068b3  call    RootInfoGet
0x1800068b8  mov     ebx, eax
0x1800068ba  test    eax, eax
0x1800068bc  jnz     loc_1800069E1
0x1800068c2  mov     ecx, [rsp+0A8h+arg_0]
0x1800068c9  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800068d3  mul     rcx
0x1800068d6  mov     [rsp+0A8h+arg_10], r13d
0x1800068de  mov     rcx, rdx
0x1800068e1  shr     rcx, 4
0x1800068e5  mov     [rsp+0A8h+var_68], rcx
0x1800068ea  test    rcx, rcx
0x1800068ed  jz      loc_1800069A0
0x1800068f3  mov     rbp, [rsp+0A8h+lpMem]
0x1800068f8  mov     edi, r13d
0x1800068fb  mov     edx, r13d
0x1800068fe  mov     r13, r15
0x180006901  test    r15, r15
0x180006904  jz      short loc_18000694E
0x180006906  mov     eax, edi
0x180006908  lea     rcx, [rax+rax*2]
0x18000690c  mov     rax, [rbp+rcx*8+10h]
0x180006911  cmp     rax, [r13+250h]
0x180006918  jz      short loc_180006925
0x18000691a  mov     r13, [r13+0]
0x18000691e  test    r13, r13
0x180006921  jnz     short loc_18000690C
0x180006923  jmp     short loc_18000694E
0x180006925  mov     rdx, [r14+258h]; pSid2
0x18000692c  mov     rcx, [r13+258h]; pSid1
0x180006933  call    cs:__imp_EqualSid
0x180006939  mov     edx, [rsp+0A8h+arg_10]
0x180006940  test    eax, eax
0x180006942  jz      short loc_18000694E
0x180006944  cmp     esi, 1
0x180006947  jnz     short loc_18000696C
0x180006949  cmp     r13, r14
0x18000694c  jnz     short loc_18000696C
0x18000694e  mov     eax, edi
0x180006950  xorps   xmm0, xmm0
0x180006953  lea     rcx, [rax+rax*2]
0x180006957  xor     eax, eax
0x180006959  inc     edx
0x18000695b  movups  xmmword ptr [rbp+rcx*8+0], xmm0
0x180006960  mov     [rsp+0A8h+arg_10], edx
0x180006967  mov     [rbp+rcx*8+10h], rax
0x18000696c  mov     rcx, [rsp+0A8h+var_68]
0x180006971  inc     edi
0x180006973  mov     eax, edi
0x180006975  cmp     rax, rcx
0x180006978  jb      short loc_1800068FE
0x18000697a  mov     rdi, [rsp+0A8h+var_60]
0x18000697f  mov     rbp, [rsp+0A8h+pCertContext]
0x180006984  test    edx, edx
0x180006986  jz      short loc_1800069A0
0x180006988  mov     eax, edx
0x18000698a  cmp     rax, rcx
0x18000698d  jnz     short loc_1800069C4
0x18000698f  mov     rdx, [r14+1A0h]; Token
0x180006996  mov     rcx, rbp; pCertContext
0x180006999  call    CertPropDeleteRootCertFromStore
0x18000699e  xor     ebp, ebp
0x1800069a0  mov     r13, [rsp+0A8h+lpMem]
0x1800069a5  mov     rcx, cs:g_hHeap; hHeap
0x1800069ac  mov     r8, r13; lpMem
0x1800069af  xor     edx, edx; dwFlags
0x1800069b1  call    cs:__imp_HeapFree
0x1800069b7  xor     r13d, r13d
0x1800069ba  mov     [rsp+0A8h+lpMem], r13
0x1800069bf  jmp     loc_180006858
0x1800069c4  mov     eax, [rsp+0A8h+arg_0]
0x1800069cb  mov     r8, rbp
0x1800069ce  mov     r13, [rsp+0A8h+lpMem]
0x1800069d3  mov     r9, r13
0x1800069d6  mov     dword ptr [rsp+0A8h+pvPara], eax
0x1800069da  call    RootInfoSet
0x1800069df  jmp     short loc_1800069A5
0x1800069e1  mov     rcx, rbp; pCertContext
0x1800069e4  call    cs:__imp_CertFreeCertificateContext
0x1800069ea  test    rdi, rdi
0x1800069ed  jz      short loc_1800069FA
0x1800069ef  xor     edx, edx; dwFlags
0x1800069f1  mov     rcx, rdi; hCertStore
0x1800069f4  call    cs:__imp_CertCloseStore
0x1800069fa  call    cs:__imp_RevertToSelf
0x180006a00  mov     rdi, [rsp+0A8h+var_38]
0x180006a05  mov     eax, ebx
0x180006a07  mov     rbp, [rsp+0A8h+arg_8]
0x180006a0f  add     rsp, 78h
0x180006a13  pop     r15
0x180006a15  pop     r14
0x180006a17  pop     r13
0x180006a19  pop     r12
0x180006a1b  pop     rsi
0x180006a1c  pop     rbx
0x180006a1d  retn
0x180006a1e  mov     eax, r13d
0x180006a21  add     rsp, 78h
0x180006a25  pop     r15
0x180006a27  pop     r14
0x180006a29  pop     r13
0x180006a2b  pop     r12
0x180006a2d  pop     rsi
0x180006a2e  pop     rbx
0x180006a2f  retn
```
