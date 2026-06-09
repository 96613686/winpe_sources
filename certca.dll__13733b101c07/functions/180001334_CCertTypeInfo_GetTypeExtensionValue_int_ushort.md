# CCertTypeInfo::_GetTypeExtensionValue(int,ushort * *)

- ea: `0x180001334`
- end: `0x1800016d4`
- name: `?_GetTypeExtensionValue@CCertTypeInfo@@IEAAJHPEAPEAG@Z`
- size: `928`
- prototype: `__int64 __fastcall(CCertTypeInfo *this, __int64, BYTE **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800025a0`

## callees

- `0x180001334`
- `0x180002ef0`
- `0x180004c30`
- `0x180005944`
- `0x180008400`
- `0x180012450`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001533`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001533`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001698`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800016a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001698`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800016a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000151e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800015a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000151e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800015a4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001511`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001597`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001511`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001597`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800013c2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800013f8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001425`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001452`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001482`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800013c2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800013f8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001425`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001452`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001482`
- `CRYPT32!CryptEncodeObject` at `0x180001628`
- `CRYPT32!CryptEncodeObject` at `0x18000167f`
- `CRYPT32!CryptEncodeObject` at `0x180001628`
- `CRYPT32!CryptEncodeObject` at `0x18000167f`

## string_xrefs

- `0x18000143d`: `msPKI-Template-Schema-Version`
- `0x18000139f`: `msPKI-Template-Minor-Revision`
- `0x1800013a6`: `msPKI-Cert-Template-OID`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_GetTypeExtensionValue(CCertTypeInfo *this, __int64 a2, BYTE **a3)
{
  HLOCAL v4; // rcx
  BYTE *v7; // r15
  __int64 v8; // rdi
  int v9; // eax
  DWORD Property; // ebx
  const WCHAR *v11; // r8
  __int64 v12; // rax
  unsigned int v13; // eax
  int v14; // r12d
  CHAR *v15; // rax
  CHAR *v16; // r14
  const WCHAR *v17; // r8
  __int128 *p_pvStructInfo; // r8
  const CHAR *v19; // rdi
  const CHAR *v20; // rdx
  const char *v21; // rcx
  __int128 *v22; // r8
  __int128 v23; // [rsp+40h] [rbp-30h] BYREF
  __int64 v24; // [rsp+50h] [rbp-20h]
  __int128 pvStructInfo; // [rsp+58h] [rbp-18h] BYREF
  __int64 v26; // [rsp+68h] [rbp-8h]
  DWORD pcbEncoded; // [rsp+B8h] [rbp+48h] BYREF
  HLOCAL hMem; // [rsp+C0h] [rbp+50h] BYREF

  v26 = 0;
  v24 = 0;
  v4 = 0;
  hMem = 0;
  pcbEncoded = 0;
  pvStructInfo = 0;
  v23 = 0;
  if ( !a3 )
    return 2147500035LL;
  v7 = 0;
  if ( *((_DWORD *)this + 22) < 2u )
  {
    v16 = 0;
    v26 = *((_QWORD *)this + 1);
    Property = 0;
    LODWORD(pvStructInfo) = 12;
    DWORD2(pvStructInfo) = 0;
    goto LABEL_35;
  }
  v8 = -1;
  if ( CompareStringW(0x7Fu, 1u, L"msPKI-Cert-Template-OID", -1, L"msPKI-Template-Minor-Revision", -1) == 2 )
  {
    v9 = *((_DWORD *)this + 16);
LABEL_6:
    LODWORD(hMem) = v9;
    Property = 0;
    goto LABEL_16;
  }
  if ( CompareStringW(0x7Fu, 1u, L"msPKI-Cert-Template-OID", -1, L"msPKI-RA-Signature", -1) == 2 )
  {
    v9 = *((_DWORD *)this + 21);
    goto LABEL_6;
  }
  if ( CompareStringW(0x7Fu, 1u, L"msPKI-Cert-Template-OID", -1, L"msPKI-Minimal-Key-Size", -1) == 2 )
  {
    v9 = *((_DWORD *)this + 20);
    goto LABEL_6;
  }
  if ( CompareStringW(0x7Fu, 1u, L"msPKI-Cert-Template-OID", -1, L"msPKI-Template-Schema-Version", -1) == 2 )
  {
    v9 = *((_DWORD *)this + 22);
    goto LABEL_6;
  }
  if ( CompareStringW(0x7Fu, 1u, L"msPKI-Cert-Template-OID", -1, L"revision", -1) == 2 )
  {
    v9 = *((_DWORD *)this + 36);
    goto LABEL_6;
  }
  Property = CCertTypeInfo::GetProperty(this, L"msPKI-Cert-Template-OID", (unsigned __int16 ***)&hMem);
  if ( !Property )
  {
LABEL_16:
    if ( !hMem || (v11 = *(const WCHAR **)hMem) == 0 )
    {
      Property = -2147024809;
      goto LABEL_49;
    }
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    if ( (unsigned __int64)(v12 + 1) > 0x10000 )
    {
      Property = -2147024362;
      CSPrintErrorLineFile(0x16550328u, -2147024362);
      goto LABEL_49;
    }
    v13 = WideCharToMultiByte(0, 0, v11, v12 + 1, 0, 0, 0, 0);
    v14 = v13;
    if ( !v13 )
    {
      Property = GetLastError();
      goto LABEL_49;
    }
    v15 = (CHAR *)LocalAlloc(0x40u, v13);
    v16 = v15;
    if ( !v15 )
    {
      Property = -2147024882;
      goto LABEL_49;
    }
    v17 = *(const WCHAR **)hMem;
    do
      ++v8;
    while ( v17[v8] );
    if ( (unsigned __int64)(v8 + 1) > 0x10000 )
    {
      Property = -2147024362;
      CSPrintErrorLineFile(0x16700328u, -2147024362);
      goto LABEL_48;
    }
    if ( !WideCharToMultiByte(0, 0, v17, v8 + 1, v15, v14, 0, 0) )
    {
      Property = GetLastError();
      goto LABEL_48;
    }
    v4 = hMem;
    DWORD2(v23) = *((_DWORD *)this + 36);
    LODWORD(v24) = *((_DWORD *)this + 16);
    *(_QWORD *)&v23 = v16;
    HIDWORD(v23) = 1;
LABEL_35:
    p_pvStructInfo = &v23;
    if ( !v4 )
      p_pvStructInfo = &pvStructInfo;
    v19 = "1.3.6.1.4.1.311.21.7";
    v20 = "1.3.6.1.4.1.311.21.7";
    if ( !v4 )
      v20 = (const CHAR *)24;
    if ( !CryptEncodeObject(1u, v20, p_pvStructInfo, 0, &pcbEncoded) )
      goto LABEL_40;
    v7 = (BYTE *)CertAllocStringByteLen(v21, pcbEncoded);
    if ( v7 )
    {
      v22 = &v23;
      if ( !hMem )
      {
        v19 = (const CHAR *)24;
        v22 = &pvStructInfo;
      }
      if ( !CryptEncodeObject(1u, v19, v22, v7, &pcbEncoded) )
      {
LABEL_40:
        Property = myHLastError();
        goto LABEL_47;
      }
      *a3 = v7;
      v7 = 0;
    }
    else
    {
      Property = -2147024882;
    }
LABEL_47:
    if ( !v16 )
      goto LABEL_49;
LABEL_48:
    LocalFree(v16);
  }
LABEL_49:
  if ( hMem )
    LocalFree(hMem);
  if ( v7 )
    CertFreeString((unsigned __int16 *)v7);
  return Property;
}

```

## disassembly

```asm
0x180001334  mov     [rsp-38h+arg_0], rbx
0x180001339  mov     [rsp-38h+pcbEncoded], edx
0x18000133d  push    rbp
0x18000133e  push    rsi
0x18000133f  push    rdi
0x180001340  push    r12
0x180001342  push    r13
0x180001344  push    r14
0x180001346  push    r15
0x180001348  mov     rbp, rsp
0x18000134b  sub     rsp, 70h
0x18000134f  xor     r12d, r12d
0x180001352  xor     eax, eax
0x180001354  mov     [rbp+var_8], rax
0x180001358  mov     rsi, rcx
0x18000135b  mov     [rbp+var_20], rax
0x18000135f  mov     ecx, r12d
0x180001362  mov     [rbp+hMem], rcx
0x180001366  xorps   xmm0, xmm0
0x180001369  mov     [rbp+pcbEncoded], r12d
0x18000136d  xorps   xmm1, xmm1
0x180001370  mov     r13, r8
0x180001373  movups  [rbp+pvStructInfo], xmm0
0x180001377  movups  [rbp+var_30], xmm1
0x18000137b  test    r8, r8
0x18000137e  jnz     short loc_18000138A
0x180001380  mov     eax, 80004003h
0x180001385  jmp     loc_1800016BC
0x18000138a  mov     ebx, 2
0x18000138f  mov     r15, r12
0x180001392  cmp     [rsi+58h], ebx
0x180001395  jb      loc_1800015DB
0x18000139b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000139f  lea     rax, aMspkiTemplateM; "msPKI-Template-Minor-Revision"
0x1800013a6  lea     r14, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x1800013ad  mov     [rsp+70h+cchCount2], edi; cchCount2
0x1800013b1  mov     r9d, edi; cchCount1
0x1800013b4  mov     [rsp+70h+lpString2], rax; lpString2
0x1800013b9  mov     r8, r14; lpString1
0x1800013bc  lea     edx, [rbx-1]; dwCmpFlags
0x1800013bf  lea     ecx, [rbx+7Dh]; Locale
0x1800013c2  call    cs:__imp_CompareStringW
0x1800013c8  cmp     eax, ebx
0x1800013ca  jnz     short loc_1800013DA
0x1800013cc  mov     eax, [rsi+40h]
0x1800013cf  mov     dword ptr [rbp+hMem], eax
0x1800013d2  mov     ebx, r12d
0x1800013d5  jmp     loc_1800014B0
0x1800013da  mov     edx, 1; dwCmpFlags
0x1800013df  mov     [rsp+70h+cchCount2], edi; cchCount2
0x1800013e3  lea     rax, aMspkiRaSignatu; "msPKI-RA-Signature"
0x1800013ea  mov     r9d, edi; cchCount1
0x1800013ed  mov     r8, r14; lpString1
0x1800013f0  mov     [rsp+70h+lpString2], rax; lpString2
0x1800013f5  lea     ecx, [rdx+7Eh]; Locale
0x1800013f8  call    cs:__imp_CompareStringW
0x1800013fe  cmp     eax, ebx
0x180001400  jnz     short loc_180001407
0x180001402  mov     eax, [rsi+54h]
0x180001405  jmp     short loc_1800013CF
0x180001407  mov     edx, 1; dwCmpFlags
0x18000140c  mov     [rsp+70h+cchCount2], edi; cchCount2
0x180001410  lea     rax, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180001417  mov     r9d, edi; cchCount1
0x18000141a  mov     r8, r14; lpString1
0x18000141d  mov     [rsp+70h+lpString2], rax; lpString2
0x180001422  lea     ecx, [rdx+7Eh]; Locale
0x180001425  call    cs:__imp_CompareStringW
0x18000142b  cmp     eax, ebx
0x18000142d  jnz     short loc_180001434
0x18000142f  mov     eax, [rsi+50h]
0x180001432  jmp     short loc_1800013CF
0x180001434  mov     edx, 1; dwCmpFlags
0x180001439  mov     [rsp+70h+cchCount2], edi; cchCount2
0x18000143d  lea     rax, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180001444  mov     r9d, edi; cchCount1
0x180001447  mov     r8, r14; lpString1
0x18000144a  mov     [rsp+70h+lpString2], rax; lpString2
0x18000144f  lea     ecx, [rdx+7Eh]; Locale
0x180001452  call    cs:__imp_CompareStringW
0x180001458  cmp     eax, ebx
0x18000145a  jnz     short loc_180001464
0x18000145c  mov     eax, [rsi+58h]
0x18000145f  jmp     loc_1800013CF
0x180001464  mov     edx, 1; dwCmpFlags
0x180001469  mov     [rsp+70h+cchCount2], edi; cchCount2
0x18000146d  lea     rax, aRevision_0; "revision"
0x180001474  mov     r9d, edi; cchCount1
0x180001477  mov     r8, r14; lpString1
0x18000147a  mov     [rsp+70h+lpString2], rax; lpString2
0x18000147f  lea     ecx, [rdx+7Eh]; Locale
0x180001482  call    cs:__imp_CompareStringW
0x180001488  cmp     eax, ebx
0x18000148a  jnz     short loc_180001497
0x18000148c  mov     eax, [rsi+90h]
0x180001492  jmp     loc_1800013CF
0x180001497  lea     r8, [rbp+hMem]; unsigned __int16 ***
0x18000149b  mov     rdx, r14; unsigned __int16 *
0x18000149e  mov     rcx, rsi; this
0x1800014a1  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x1800014a6  mov     ebx, eax
0x1800014a8  test    eax, eax
0x1800014aa  jnz     loc_18000169E
0x1800014b0  mov     rcx, [rbp+hMem]
0x1800014b4  test    rcx, rcx
0x1800014b7  jz      loc_1800015D1
0x1800014bd  mov     r8, [rcx]; lpWideCharStr
0x1800014c0  test    r8, r8
0x1800014c3  jz      loc_1800015D1
0x1800014c9  mov     rax, rdi
0x1800014cc  inc     rax
0x1800014cf  cmp     [r8+rax*2], r12w
0x1800014d4  jnz     short loc_1800014CC
0x1800014d6  lea     r9, [rax+1]; cchWideChar
0x1800014da  cmp     r9, 10000h
0x1800014e1  jbe     short loc_1800014F9
0x1800014e3  mov     edx, 80070216h; int
0x1800014e8  mov     ecx, 16550328h; unsigned int
0x1800014ed  mov     ebx, edx
0x1800014ef  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800014f4  jmp     loc_18000169E
0x1800014f9  mov     [rsp+70h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x1800014fe  xor     edx, edx; dwFlags
0x180001500  mov     [rsp+70h+lpDefaultChar], r12; lpDefaultChar
0x180001505  xor     ecx, ecx; CodePage
0x180001507  mov     [rsp+70h+cchCount2], r12d; cbMultiByte
0x18000150c  mov     [rsp+70h+lpString2], r12; lpMultiByteStr
0x180001511  call    cs:__imp_WideCharToMultiByte
0x180001517  mov     r12d, eax
0x18000151a  test    eax, eax
0x18000151c  jnz     short loc_18000152B
0x18000151e  call    cs:__imp_GetLastError
0x180001524  mov     ebx, eax
0x180001526  jmp     loc_18000169E
0x18000152b  mov     rdx, r12; uBytes
0x18000152e  mov     ecx, 40h ; '@'; uFlags
0x180001533  call    cs:__imp_LocalAlloc
0x180001539  xor     ecx, ecx; CodePage
0x18000153b  mov     r14, rax
0x18000153e  test    rax, rax
0x180001541  jnz     short loc_18000154D
0x180001543  mov     ebx, 8007000Eh
0x180001548  jmp     loc_18000169E
0x18000154d  mov     rax, [rbp+hMem]
0x180001551  mov     r8, [rax]; lpWideCharStr
0x180001554  inc     rdi
0x180001557  cmp     [r8+rdi*2], cx
0x18000155c  jnz     short loc_180001554
0x18000155e  lea     r9, [rdi+1]; cchWideChar
0x180001562  cmp     r9, 10000h
0x180001569  jbe     short loc_180001581
0x18000156b  mov     edx, 80070216h; int
0x180001570  mov     ecx, 16700328h; unsigned int
0x180001575  mov     ebx, edx
0x180001577  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000157c  jmp     loc_180001695
0x180001581  mov     [rsp+70h+lpUsedDefaultChar], rcx; lpUsedDefaultChar
0x180001586  xor     edx, edx; dwFlags
0x180001588  mov     [rsp+70h+lpDefaultChar], rcx; lpDefaultChar
0x18000158d  mov     [rsp+70h+cchCount2], r12d; cbMultiByte
0x180001592  mov     [rsp+70h+lpString2], r14; lpMultiByteStr
0x180001597  call    cs:__imp_WideCharToMultiByte
0x18000159d  xor     r12d, r12d
0x1800015a0  test    eax, eax
0x1800015a2  jnz     short loc_1800015B1
0x1800015a4  call    cs:__imp_GetLastError
0x1800015aa  mov     ebx, eax
0x1800015ac  jmp     loc_180001695
0x1800015b1  mov     eax, [rsi+90h]
0x1800015b7  mov     rcx, [rbp+hMem]
0x1800015bb  mov     dword ptr [rbp+var_30+8], eax
0x1800015be  mov     eax, [rsi+40h]
0x1800015c1  mov     dword ptr [rbp+var_20], eax
0x1800015c4  mov     qword ptr [rbp+var_30], r14
0x1800015c8  mov     dword ptr [rbp+var_30+0Ch], 1
0x1800015cf  jmp     short loc_1800015F4
0x1800015d1  mov     ebx, 80070057h
0x1800015d6  jmp     loc_18000169E
0x1800015db  mov     rax, [rsi+8]
0x1800015df  mov     r14, r12
0x1800015e2  mov     [rbp+var_8], rax
0x1800015e6  mov     ebx, r12d
0x1800015e9  mov     dword ptr [rbp+pvStructInfo], 0Ch
0x1800015f0  mov     dword ptr [rbp+pvStructInfo+8], r12d
0x1800015f4  test    rcx, rcx
0x1800015f7  lea     rax, [rbp+pvStructInfo]
0x1800015fb  lea     r8, [rbp+var_30]
0x1800015ff  cmovz   r8, rax; pvStructInfo
0x180001603  lea     rdi, a136141311217_0; "1.3.6.1.4.1.311.21.7"
0x18000160a  mov     eax, 18h
0x18000160f  mov     rdx, rdi
0x180001612  cmovz   rdx, rax; lpszStructType
0x180001616  xor     r9d, r9d; pbEncoded
0x180001619  lea     rax, [rbp+pcbEncoded]
0x18000161d  mov     [rsp+70h+lpString2], rax; pcbEncoded
0x180001622  lea     esi, [r9+1]
0x180001626  mov     ecx, esi; dwCertEncodingType
0x180001628  call    cs:__imp_CryptEncodeObject
0x18000162e  test    eax, eax
0x180001630  jnz     short loc_18000163B
0x180001632  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180001637  mov     ebx, eax
0x180001639  jmp     short loc_180001690
0x18000163b  mov     edx, [rbp+pcbEncoded]; unsigned int
0x18000163e  call    ?CertAllocStringByteLen@@YAPEAGPEBDI@Z; CertAllocStringByteLen(char const *,uint)
0x180001643  mov     r15, rax
0x180001646  test    rax, rax
0x180001649  jnz     short loc_180001652
0x18000164b  mov     ebx, 8007000Eh
0x180001650  jmp     short loc_180001690
0x180001652  mov     rax, [rbp+hMem]
0x180001656  lea     rdx, [rbp+pvStructInfo]
0x18000165a  test    rax, rax
0x18000165d  lea     r8, [rbp+var_30]
0x180001661  mov     eax, 18h
0x180001666  mov     r9, r15; pbEncoded
0x180001669  cmovz   rdi, rax
0x18000166d  cmovz   r8, rdx; pvStructInfo
0x180001671  lea     rax, [rbp+pcbEncoded]
0x180001675  mov     rdx, rdi; lpszStructType
0x180001678  mov     ecx, esi; dwCertEncodingType
0x18000167a  mov     [rsp+70h+lpString2], rax; pcbEncoded
0x18000167f  call    cs:__imp_CryptEncodeObject
0x180001685  test    eax, eax
0x180001687  jz      short loc_180001632
0x180001689  mov     [r13+0], r15
0x18000168d  mov     r15, r12
0x180001690  test    r14, r14
0x180001693  jz      short loc_18000169E
0x180001695  mov     rcx, r14; hMem
0x180001698  call    cs:__imp_LocalFree
0x18000169e  mov     rcx, [rbp+hMem]; hMem
0x1800016a2  test    rcx, rcx
0x1800016a5  jz      short loc_1800016AD
0x1800016a7  call    cs:__imp_LocalFree
0x1800016ad  test    r15, r15
0x1800016b0  jz      short loc_1800016BA
0x1800016b2  mov     rcx, r15; unsigned __int16 *
0x1800016b5  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x1800016ba  mov     eax, ebx
0x1800016bc  mov     rbx, [rsp+70h+arg_0]
0x1800016c4  add     rsp, 70h
0x1800016c8  pop     r15
0x1800016ca  pop     r14
0x1800016cc  pop     r13
0x1800016ce  pop     r12
0x1800016d0  pop     rdi
0x1800016d1  pop     rsi
0x1800016d2  pop     rbp
0x1800016d3  retn
```
