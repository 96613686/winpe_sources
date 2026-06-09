# BuildCertContext(unsigned __int64,ulong,ushort const *,uchar *,ulong,ulong,_CERT_CONTEXT const * *)

- ea: `0x18001ffb0`
- end: `0x1800204c0`
- name: `?BuildCertContext@@YAJ_KKPEBGPEAEKKPEAPEBU_CERT_CONTEXT@@@Z`
- size: `1296`
- prototype: `__int64 __usercall@<rax>(NCRYPT_HANDLE hObject@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned __int8 *@<r9>, unsigned int, unsigned int, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001fc10`

## callees

- `0x180007e80`
- `0x18001ffb0`
- `0x180070680`
- `0x18007108c`
- `0x1800d637c`
- `0x1800d842c`
- `0x1800d84c4`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800203ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800203ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020379`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020414`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002043f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020467`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020495`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020414`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002043f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020467`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020495`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180020426`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002047c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180020426`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002047c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800203fe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180020451`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800203fe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180020451`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020318`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020363`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020318`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020363`
- `CRYPT32!CertCreateCertificateContext` at `0x18002004e`
- `CRYPT32!CertCreateCertificateContext` at `0x18002004e`
- `CRYPT32!CertFreeCertificateContext` at `0x18002039b`
- `CRYPT32!CertFreeCertificateContext` at `0x18002039b`
- `ncrypt!NCryptGetProperty` at `0x1800202e2`
- `ncrypt!NCryptGetProperty` at `0x1800202e2`
- `CRYPTSP!CryptGetProvParam` at `0x180020086`
- `CRYPTSP!CryptGetProvParam` at `0x180020150`
- `CRYPTSP!CryptGetProvParam` at `0x180020183`
- `CRYPTSP!CryptGetProvParam` at `0x180020246`
- `CRYPTSP!CryptGetProvParam` at `0x180020086`
- `CRYPTSP!CryptGetProvParam` at `0x180020150`
- `CRYPTSP!CryptGetProvParam` at `0x180020183`
- `CRYPTSP!CryptGetProvParam` at `0x180020246`

## pseudocode

```c
__int64 __fastcall BuildCertContext(
        NCRYPT_HANDLE hObject,
        int a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        DWORD cbCertEncoded,
        DWORD a6,
        const struct _CERT_CONTEXT **a7)
{
  DWORD *p_pdwDataLen; // r14
  DWORD *p_pcbResult; // rdi
  const struct _CERT_CONTEXT *CertificateContext; // rax
  SECURITY_STATUS Property; // ebx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  DWORD *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  unsigned __int64 v27; // rbx
  unsigned __int64 v28; // rcx
  __int64 v29; // rcx
  unsigned __int64 v30; // rcx
  void *v31; // rsp
  void *v32; // rsp
  DWORD *v33; // rax
  DWORD LastError; // esi
  const CERT_CONTEXT *v35; // rcx
  CHAR *v36; // rdi
  int v37; // eax
  CHAR *v38; // rdi
  int v39; // eax
  CHAR *v40; // rdi
  int v41; // eax
  CHAR *v42; // rdi
  int v43; // eax
  _BYTE v45[32]; // [rsp+0h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+30h] [rbp+0h] BYREF
  DWORD v47; // [rsp+34h] [rbp+4h] BYREF
  DWORD pcbResult; // [rsp+38h] [rbp+8h] BYREF
  __int128 pvData; // [rsp+40h] [rbp+10h] BYREF
  __int128 v50; // [rsp+50h] [rbp+20h]
  __int128 v51; // [rsp+60h] [rbp+30h]
  _BYTE v52[16]; // [rsp+70h] [rbp+40h] BYREF
  LPCSTR lpString[2]; // [rsp+80h] [rbp+50h]
  int v54; // [rsp+90h] [rbp+60h]
  _BYTE v55[16]; // [rsp+98h] [rbp+68h] BYREF
  LPCSTR v56[2]; // [rsp+A8h] [rbp+78h]
  int v57; // [rsp+B8h] [rbp+88h]
  _QWORD v58[2]; // [rsp+C0h] [rbp+90h] BYREF
  int v59; // [rsp+D0h] [rbp+A0h]
  int v60; // [rsp+D4h] [rbp+A4h]
  BYTE pbOutput[528]; // [rsp+E0h] [rbp+B0h] BYREF

  v57 = 3;
  v54 = 3;
  *a7 = 0;
  pdwDataLen = 0;
  p_pdwDataLen = 0;
  v47 = 0;
  p_pcbResult = 0;
  pvData = 0;
  v50 = 0;
  v51 = 0;
  *(_OWORD *)v56 = 0;
  *(_OWORD *)lpString = 0;
  if ( !hObject || !a4 || !cbCertEncoded )
    goto LABEL_49;
  CertificateContext = CertCreateCertificateContext(0x10001u, a4, cbCertEncoded);
  *a7 = CertificateContext;
  if ( !CertificateContext )
  {
    Property = -1073741023;
    goto LABEL_50;
  }
  if ( (unsigned int)(a2 - 1) > 0xFFFFFFFD )
  {
    memset_0(pbOutput, 0, 0x20Au);
    pcbResult = 520;
    if ( a3 )
    {
      Property = NCryptGetProperty(hObject, L"Unique Name", pbOutput, 0x208u, &pcbResult, 0);
      if ( Property < 0 )
        goto LABEL_50;
      *((_QWORD *)&pvData + 1) = a3;
      *(_QWORD *)&pvData = pbOutput;
      DWORD2(v51) = -1;
      goto LABEL_45;
    }
LABEL_49:
    Property = -1073741811;
    goto LABEL_50;
  }
  if ( !CryptGetProvParam(hObject, 6u, 0, &pdwDataLen, 0) )
  {
    Property = -1073741023;
    goto LABEL_50;
  }
  v17 = pdwDataLen;
  if ( !pdwDataLen )
    goto LABEL_71;
  if ( pdwDataLen > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_71;
  v18 = pdwDataLen + g_ulAdditionalProbeSize + 8;
  if ( v18 < pdwDataLen || !(unsigned int)VerifyStackAvailable(v18, v14, v15, v16) )
    goto LABEL_71;
  v19 = v17 + 23;
  if ( v17 + 23 <= v17 + 8 )
    v19 = 0xFFFFFFFFFFFFFF0LL;
  v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
  v21 = alloca(v20);
  v22 = alloca(v20);
  p_pdwDataLen = &pdwDataLen;
  if ( v45 == (_BYTE *)-48LL || (pdwDataLen = 1801679955, (p_pdwDataLen = &pcbResult) == 0) )
  {
LABEL_71:
    if ( v17 + 8 >= v17 )
    {
      v23 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_pdwDataLen = v23;
      if ( v23 )
      {
        *v23 = 1885431112;
        p_pdwDataLen = v23 + 2;
      }
    }
  }
  if ( !p_pdwDataLen )
  {
    Property = -1073741670;
    goto LABEL_50;
  }
  if ( !CryptGetProvParam(hObject, 6u, (BYTE *)p_pdwDataLen, &pdwDataLen, 0) )
  {
    Property = -1073741023;
    goto LABEL_50;
  }
  CUnicodeString::Set((CUnicodeString *)v55, (const char *)p_pdwDataLen);
  if ( !CryptGetProvParam(hObject, 4u, 0, &v47, 0) )
  {
    Property = -1073741023;
    goto LABEL_50;
  }
  v27 = v47;
  if ( !v47 )
    goto LABEL_72;
  if ( v47 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_72;
  v28 = v47 + g_ulAdditionalProbeSize + 8;
  if ( v28 < v47 || !(unsigned int)VerifyStackAvailable(v28, v24, v25, v26) )
    goto LABEL_72;
  v29 = v27 + 23;
  if ( v27 + 23 <= v27 + 8 )
    v29 = 0xFFFFFFFFFFFFFF0LL;
  v30 = v29 & 0xFFFFFFFFFFFFFFF0uLL;
  v31 = alloca(v30);
  v32 = alloca(v30);
  p_pcbResult = &pdwDataLen;
  if ( v45 == (_BYTE *)-48LL || (pdwDataLen = 1801679955, (p_pcbResult = &pcbResult) == 0) )
  {
LABEL_72:
    if ( v27 + 8 >= v27 )
    {
      v33 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_pcbResult = v33;
      if ( v33 )
      {
        *v33 = 1885431112;
        p_pcbResult = v33 + 2;
      }
    }
  }
  if ( !p_pcbResult )
  {
    Property = -1073741670;
    goto LABEL_50;
  }
  if ( !CryptGetProvParam(hObject, 4u, (BYTE *)p_pcbResult, &v47, 0) )
  {
    Property = -1073741023;
    goto LABEL_50;
  }
  Property = 0;
  CUnicodeString::Set((CUnicodeString *)v52, (const char *)p_pcbResult);
  *(_QWORD *)&pvData = CUnicodeString::Unicode((CUnicodeString *)v55);
  *((_QWORD *)&pvData + 1) = CUnicodeString::Unicode((CUnicodeString *)v52);
  LODWORD(v50) = 1;
  *(_QWORD *)((char *)&v50 + 4) = 1;
  *(_QWORD *)&v51 = 0;
  DWORD2(v51) = a2;
LABEL_45:
  if ( CertSetCertificateContextProperty(*a7, 2u, 0, &pvData) )
  {
    LastError = 0;
    v35 = *a7;
    v60 = 0;
    v58[0] = 24;
    v58[1] = hObject;
    v59 = DWORD2(v51);
    if ( CertSetCertificateContextProperty(v35, 5u, a6, v58) )
      goto LABEL_52;
    Property = -1073741023;
  }
  else
  {
    Property = -1073741023;
  }
LABEL_50:
  LastError = GetLastError();
  Property = LogEventAndTranslateLastErrorToNtStatus(Property, 0x1000Cu, LastError);
  if ( *a7 )
  {
    CertFreeCertificateContext(*a7);
    *a7 = 0;
  }
LABEL_52:
  if ( p_pdwDataLen && *(p_pdwDataLen - 2) == 1885431112 )
    ((void (__fastcall *)(DWORD *))g_pfnFree)(p_pdwDataLen - 2);
  if ( p_pcbResult && *(p_pcbResult - 2) == 1885431112 )
    ((void (__fastcall *)(DWORD *))g_pfnFree)(p_pcbResult - 2);
  if ( LastError )
    SetLastError(LastError);
  v36 = (CHAR *)lpString[0];
  if ( lpString[0] )
  {
    v37 = lstrlenA(lpString[0]);
    memset_0(v36, 0, v37);
    LocalFree(v36);
  }
  v38 = (CHAR *)lpString[1];
  if ( lpString[1] )
  {
    v39 = lstrlenW((LPCWSTR)lpString[1]);
    memset_0(v38, 0, 2LL * v39);
    LocalFree(v38);
  }
  v40 = (CHAR *)v56[0];
  if ( v56[0] )
  {
    v41 = lstrlenA(v56[0]);
    memset_0(v40, 0, v41);
    LocalFree(v40);
  }
  v42 = (CHAR *)v56[1];
  if ( v56[1] )
  {
    v43 = lstrlenW((LPCWSTR)v56[1]);
    memset_0(v42, 0, 2LL * v43);
    LocalFree(v42);
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18001ffb0  push    rbp
0x18001ffb2  push    rbx
0x18001ffb3  push    rsi
0x18001ffb4  push    rdi
0x18001ffb5  push    r12
0x18001ffb7  push    r13
0x18001ffb9  push    r14
0x18001ffbb  push    r15
0x18001ffbd  sub     rsp, 308h
0x18001ffc4  lea     rbp, [rsp+30h]
0x18001ffc9  mov     rax, cs:__security_cookie
0x18001ffd0  xor     rax, rbp
0x18001ffd3  mov     [rbp+310h+var_50], rax
0x18001ffda  mov     r12, [rbp+310h+arg_30]
0x18001ffe1  xor     ebx, ebx
0x18001ffe3  mov     [rbp+310h+var_288], 3
0x18001ffed  xorps   xmm0, xmm0
0x18001fff0  mov     [rbp+310h+var_2B0], 3
0x18001fff7  mov     r13, r8
0x18001fffa  mov     r8d, [rbp+310h+cbCertEncoded]; cbCertEncoded
0x180020001  mov     esi, edx
0x180020003  mov     [r12], rbx
0x180020007  mov     r15, rcx
0x18002000a  mov     [rbp+310h+pdwDataLen], ebx
0x18002000d  mov     r14d, ebx
0x180020010  mov     [rbp+310h+var_30C], ebx
0x180020013  mov     edi, ebx
0x180020015  movups  [rbp+310h+pvData], xmm0
0x180020019  movups  [rbp+310h+var_2F0], xmm0
0x18002001d  movups  [rbp+310h+var_2E0], xmm0
0x180020021  movdqu  xmmword ptr [rbp+310h+var_298], xmm0
0x180020026  movdqu  xmmword ptr [rbp+310h+lpString], xmm0
0x18002002b  test    rcx, rcx
0x18002002e  jz      loc_180020374
0x180020034  test    r9, r9
0x180020037  jz      loc_180020374
0x18002003d  test    r8d, r8d
0x180020040  jz      loc_180020374
0x180020046  mov     rdx, r9; pbCertEncoded
0x180020049  mov     ecx, 10001h; dwCertEncodingType
0x18002004e  call    cs:__imp_CertCreateCertificateContext
0x180020054  mov     [r12], rax
0x180020058  test    rax, rax
0x18002005b  jnz     short loc_180020067
0x18002005d  mov     ebx, 0C0000321h
0x180020062  jmp     loc_180020379
0x180020067  lea     eax, [rsi-1]
0x18002006a  cmp     eax, 0FFFFFFFDh
0x18002006d  ja      loc_18002029A
0x180020073  lea     r9, [rbp+310h+pdwDataLen]; pdwDataLen
0x180020077  mov     [rsp+340h+dwFlags], ebx; dwFlags
0x18002007b  xor     r8d, r8d; pbData
0x18002007e  mov     edx, 6; dwParam
0x180020083  mov     rcx, r15; hProv
0x180020086  call    cs:__imp_CryptGetProvParam
0x18002008c  test    eax, eax
0x18002008e  jnz     short loc_18002009A
0x180020090  mov     ebx, 0C0000321h
0x180020095  jmp     loc_180020379
0x18002009a  mov     ebx, [rbp+310h+pdwDataLen]
0x18002009d  mov     r13, 0FFFFFFFFFFFFFF0h
0x1800200a7  test    rbx, rbx
0x1800200aa  jz      short loc_180020107
0x1800200ac  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800200b3  ja      short loc_180020107
0x1800200b5  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800200bc  add     rcx, 8
0x1800200c0  add     rcx, rbx
0x1800200c3  cmp     rcx, rbx
0x1800200c6  jb      short loc_180020107
0x1800200c8  call    VerifyStackAvailable
0x1800200cd  test    eax, eax
0x1800200cf  jz      short loc_180020107
0x1800200d1  lea     rax, [rbx+8]
0x1800200d5  lea     rcx, [rax+0Fh]
0x1800200d9  cmp     rcx, rax
0x1800200dc  ja      short loc_1800200E1
0x1800200de  mov     rcx, r13
0x1800200e1  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800200e5  mov     rax, rcx
0x1800200e8  call    _alloca_probe
0x1800200ed  sub     rsp, rcx
0x1800200f0  lea     r14, [rsp+340h+pdwDataLen]
0x1800200f5  test    r14, r14
0x1800200f8  jz      short loc_180020107
0x1800200fa  mov     dword ptr [r14], 6B637453h
0x180020101  add     r14, 8
0x180020105  jnz     short loc_18002012E
0x180020107  lea     rcx, [rbx+8]
0x18002010b  cmp     rcx, rbx
0x18002010e  jb      short loc_18002012E
0x180020110  mov     rax, cs:g_pfnAllocate
0x180020117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002011c  mov     r14, rax
0x18002011f  test    rax, rax
0x180020122  jz      short loc_18002012E
0x180020124  mov     dword ptr [rax], 70616548h
0x18002012a  add     r14, 8
0x18002012e  test    r14, r14
0x180020131  jnz     short loc_18002013D
0x180020133  mov     ebx, 0C000009Ah
0x180020138  jmp     loc_180020379
0x18002013d  lea     r9, [rbp+310h+pdwDataLen]; pdwDataLen
0x180020141  mov     [rsp+340h+dwFlags], edi; dwFlags
0x180020145  mov     r8, r14; pbData
0x180020148  mov     edx, 6; dwParam
0x18002014d  mov     rcx, r15; hProv
0x180020150  call    cs:__imp_CryptGetProvParam
0x180020156  test    eax, eax
0x180020158  jnz     short loc_180020164
0x18002015a  mov     ebx, 0C0000321h
0x18002015f  jmp     loc_180020379
0x180020164  mov     rdx, r14; char *
0x180020167  lea     rcx, [rbp+310h+var_2A8]; this
0x18002016b  call    ?Set@CUnicodeString@@QEAAPEBDPEBD@Z; CUnicodeString::Set(char const *)
0x180020170  lea     r9, [rbp+310h+var_30C]; pdwDataLen
0x180020174  mov     [rsp+340h+dwFlags], edi; dwFlags
0x180020178  xor     r8d, r8d; pbData
0x18002017b  mov     edx, 4; dwParam
0x180020180  mov     rcx, r15; hProv
0x180020183  call    cs:__imp_CryptGetProvParam
0x180020189  test    eax, eax
0x18002018b  jnz     short loc_180020197
0x18002018d  mov     ebx, 0C0000321h
0x180020192  jmp     loc_180020379
0x180020197  mov     ebx, [rbp+310h+var_30C]
0x18002019a  test    rbx, rbx
0x18002019d  jz      short loc_1800201F9
0x18002019f  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800201a6  ja      short loc_1800201F9
0x1800201a8  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800201af  add     rcx, 8
0x1800201b3  add     rcx, rbx
0x1800201b6  cmp     rcx, rbx
0x1800201b9  jb      short loc_1800201F9
0x1800201bb  call    VerifyStackAvailable
0x1800201c0  test    eax, eax
0x1800201c2  jz      short loc_1800201F9
0x1800201c4  lea     rax, [rbx+8]
0x1800201c8  lea     rcx, [rax+0Fh]
0x1800201cc  cmp     rcx, rax
0x1800201cf  ja      short loc_1800201D4
0x1800201d1  mov     rcx, r13
0x1800201d4  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800201d8  mov     rax, rcx
0x1800201db  call    _alloca_probe
0x1800201e0  sub     rsp, rcx
0x1800201e3  lea     rdi, [rsp+340h+pdwDataLen]
0x1800201e8  test    rdi, rdi
0x1800201eb  jz      short loc_1800201F9
0x1800201ed  mov     dword ptr [rdi], 6B637453h
0x1800201f3  add     rdi, 8
0x1800201f7  jnz     short loc_180020220
0x1800201f9  lea     rcx, [rbx+8]
0x1800201fd  cmp     rcx, rbx
0x180020200  jb      short loc_180020220
0x180020202  mov     rax, cs:g_pfnAllocate
0x180020209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002020e  mov     rdi, rax
0x180020211  test    rax, rax
0x180020214  jz      short loc_180020220
0x180020216  mov     dword ptr [rax], 70616548h
0x18002021c  add     rdi, 8
0x180020220  test    rdi, rdi
0x180020223  jnz     short loc_18002022F
0x180020225  mov     ebx, 0C000009Ah
0x18002022a  jmp     loc_180020379
0x18002022f  lea     r9, [rbp+310h+var_30C]; pdwDataLen
0x180020233  mov     [rsp+340h+dwFlags], 0; dwFlags
0x18002023b  mov     r8, rdi; pbData
0x18002023e  mov     edx, 4; dwParam
0x180020243  mov     rcx, r15; hProv
0x180020246  call    cs:__imp_CryptGetProvParam
0x18002024c  test    eax, eax
0x18002024e  jnz     short loc_18002025A
0x180020250  mov     ebx, 0C0000321h
0x180020255  jmp     loc_180020379
0x18002025a  mov     rdx, rdi; char *
0x18002025d  lea     rcx, [rbp+310h+var_2D0]; this
0x180020261  xor     ebx, ebx
0x180020263  call    ?Set@CUnicodeString@@QEAAPEBDPEBD@Z; CUnicodeString::Set(char const *)
0x180020268  lea     rcx, [rbp+310h+var_2A8]; this
0x18002026c  call    ?Unicode@CUnicodeString@@IEAAPEBGXZ; CUnicodeString::Unicode(void)
0x180020271  lea     rcx, [rbp+310h+var_2D0]; this
0x180020275  mov     qword ptr [rbp+310h+pvData], rax
0x180020279  call    ?Unicode@CUnicodeString@@IEAAPEBGXZ; CUnicodeString::Unicode(void)
0x18002027e  mov     qword ptr [rbp+310h+pvData+8], rax
0x180020282  mov     dword ptr [rbp+310h+var_2F0], 1
0x180020289  mov     qword ptr [rbp+310h+var_2F0+4], 1
0x180020291  mov     qword ptr [rbp+310h+var_2E0], rbx
0x180020295  mov     dword ptr [rbp+310h+var_2E0+8], esi
0x180020298  jmp     short loc_180020308
0x18002029a  xor     edx, edx; Val
0x18002029c  lea     rcx, [rbp+310h+pbOutput]; void *
0x1800202a3  mov     r8d, 20Ah; Size
0x1800202a9  call    memset_0
0x1800202ae  mov     [rbp+310h+pcbResult], 208h
0x1800202b5  test    r13, r13
0x1800202b8  jz      loc_180020374
0x1800202be  lea     rax, [rbp+310h+pcbResult]
0x1800202c2  mov     [rsp+340h+var_318], ebx; dwFlags
0x1800202c6  mov     r9d, 208h; cbOutput
0x1800202cc  mov     qword ptr [rsp+340h+dwFlags], rax; pcbResult
0x1800202d1  lea     r8, [rbp+310h+pbOutput]; pbOutput
0x1800202d8  mov     rcx, r15; hObject
0x1800202db  lea     rdx, aUniqueName; "Unique Name"
0x1800202e2  call    cs:__imp_NCryptGetProperty
0x1800202e8  mov     ebx, eax
0x1800202ea  test    eax, eax
0x1800202ec  js      loc_180020379
0x1800202f2  lea     rax, [rbp+310h+pbOutput]
0x1800202f9  mov     qword ptr [rbp+310h+pvData+8], r13
0x1800202fd  mov     qword ptr [rbp+310h+pvData], rax
0x180020301  mov     dword ptr [rbp+310h+var_2E0+8], 0FFFFFFFFh
0x180020308  mov     rcx, [r12]; pCertContext
0x18002030c  lea     r9, [rbp+310h+pvData]; pvData
0x180020310  xor     r8d, r8d; dwFlags
0x180020313  mov     edx, 2; dwPropId
0x180020318  call    cs:__imp_CertSetCertificateContextProperty
0x18002031e  test    eax, eax
0x180020320  jnz     short loc_180020329
0x180020322  mov     ebx, 0C0000321h
0x180020327  jmp     short loc_180020379
0x180020329  mov     eax, dword ptr [rbp+310h+var_2E0+8]
0x18002032c  lea     r9, [rbp+310h+var_280]; pvData
0x180020333  mov     r8d, [rbp+310h+arg_28]; dwFlags
0x18002033a  xor     esi, esi
0x18002033c  mov     rcx, [r12]; pCertContext
0x180020340  mov     edx, 5; dwPropId
0x180020345  mov     [rbp+310h+var_26C], esi
0x18002034b  mov     [rbp+310h+var_280], 18h
0x180020356  mov     [rbp+310h+var_278], r15
0x18002035d  mov     [rbp+310h+var_270], eax
0x180020363  call    cs:__imp_CertSetCertificateContextProperty
0x180020369  test    eax, eax
0x18002036b  jnz     short loc_1800203A9
0x18002036d  mov     ebx, 0C0000321h
0x180020372  jmp     short loc_180020379
0x180020374  mov     ebx, 0C000000Dh
0x180020379  call    cs:__imp_GetLastError
0x18002037f  mov     edx, 1000Ch; unsigned int
0x180020384  mov     ecx, ebx; int
0x180020386  mov     r8d, eax; unsigned int
0x180020389  mov     esi, eax
0x18002038b  call    ?LogEventAndTranslateLastErrorToNtStatus@@YAJJKK@Z; LogEventAndTranslateLastErrorToNtStatus(long,ulong,ulong)
0x180020390  mov     rcx, [r12]; pCertContext
0x180020394  mov     ebx, eax
0x180020396  test    rcx, rcx
0x180020399  jz      short loc_1800203A9
0x18002039b  call    cs:__imp_CertFreeCertificateContext
0x1800203a1  mov     qword ptr [r12], 0
0x1800203a9  test    r14, r14
0x1800203ac  jz      short loc_1800203C8
0x1800203ae  cmp     dword ptr [r14-8], 70616548h
0x1800203b6  lea     rcx, [r14-8]
0x1800203ba  jnz     short loc_1800203C8
0x1800203bc  mov     rax, cs:g_pfnFree
0x1800203c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203c8  test    rdi, rdi
0x1800203cb  jz      short loc_1800203E6
0x1800203cd  cmp     dword ptr [rdi-8], 70616548h
0x1800203d4  lea     rcx, [rdi-8]
0x1800203d8  jnz     short loc_1800203E6
0x1800203da  mov     rax, cs:g_pfnFree
0x1800203e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203e6  test    esi, esi
0x1800203e8  jz      short loc_1800203F2
0x1800203ea  mov     ecx, esi; dwErrCode
0x1800203ec  call    cs:__imp_SetLastError
0x1800203f2  mov     rdi, [rbp+310h+lpString]
0x1800203f6  test    rdi, rdi
0x1800203f9  jz      short loc_18002041A
0x1800203fb  mov     rcx, rdi; lpString
0x1800203fe  call    cs:__imp_lstrlenA
0x180020404  movsxd  r8, eax; Size
0x180020407  xor     edx, edx; Val
0x180020409  mov     rcx, rdi; void *
0x18002040c  call    memset_0
0x180020411  mov     rcx, rdi; hMem
0x180020414  call    cs:__imp_LocalFree
0x18002041a  mov     rdi, [rbp+310h+lpString+8]
0x18002041e  test    rdi, rdi
0x180020421  jz      short loc_180020445
0x180020423  mov     rcx, rdi; lpString
0x180020426  call    cs:__imp_lstrlenW
0x18002042c  movsxd  r8, eax
0x18002042f  xor     edx, edx; Val
0x180020431  add     r8, r8; Size
0x180020434  mov     rcx, rdi; void *
0x180020437  call    memset_0
0x18002043c  mov     rcx, rdi; hMem
0x18002043f  call    cs:__imp_LocalFree
0x180020445  mov     rdi, [rbp+310h+var_298]
0x180020449  test    rdi, rdi
0x18002044c  jz      short loc_18002046D
0x18002044e  mov     rcx, rdi; lpString
0x180020451  call    cs:__imp_lstrlenA
0x180020457  movsxd  r8, eax; Size
0x18002045a  xor     edx, edx; Val
0x18002045c  mov     rcx, rdi; void *
  ... truncated ...
```
