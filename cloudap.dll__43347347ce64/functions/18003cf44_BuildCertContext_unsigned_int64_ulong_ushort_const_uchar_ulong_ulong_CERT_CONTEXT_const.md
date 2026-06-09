# BuildCertContext(unsigned __int64,ulong,ushort const *,uchar *,ulong,ulong,_CERT_CONTEXT const * *)

- ea: `0x18003cf44`
- end: `0x18003d38a`
- name: `?BuildCertContext@@YAJ_KKPEBGPEAEKKPEAPEBU_CERT_CONTEXT@@@Z`
- size: `1094`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, int, const unsigned __int16 *, unsigned __int8 *, DWORD cbCertEncoded, unsigned int, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003f6a0`

## callees

- `0x18000a810`
- `0x18003cf44`
- `0x18003d390`
- `0x18003f9c0`
- `0x180042410`
- `0x18004317c`
- `0x18007e9d0`
- `0x18007ea68`
- `0x18007f990`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d2da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d2da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d34d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d34d`
- `CRYPT32!CertCreateCertificateContext` at `0x18003cfdd`
- `CRYPT32!CertCreateCertificateContext` at `0x18003cfdd`
- `CRYPT32!CertFreeCertificateContext` at `0x18003d2fd`
- `CRYPT32!CertFreeCertificateContext` at `0x18003d2fd`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18003d284`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18003d2c6`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18003d284`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18003d2c6`
- `ncrypt!NCryptGetProperty` at `0x18003d250`
- `ncrypt!NCryptGetProperty` at `0x18003d250`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x18003d019`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x18003d0d6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x18003d103`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x18003d1be`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x18003d019`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x18003d0d6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x18003d103`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x18003d1be`

## pseudocode

```c
__int64 __fastcall BuildCertContext(
        NCRYPT_HANDLE hObject,
        int a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        DWORD cbCertEncoded,
        unsigned int a6,
        const struct _CERT_CONTEXT **a7)
{
  DWORD *p_pdwDataLen; // rsi
  DWORD *p_pcbResult; // rdi
  const struct _CERT_CONTEXT *CertificateContext; // rax
  SECURITY_STATUS Property; // ebx
  DWORD LastError; // r14d
  unsigned __int64 v15; // rbx
  __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  DWORD *v20; // rax
  unsigned __int64 v21; // rbx
  __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  void *v24; // rsp
  void *v25; // rsp
  DWORD *v26; // rax
  const CERT_CONTEXT *v27; // rcx
  _BYTE v29[32]; // [rsp+0h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+30h] [rbp+0h] BYREF
  DWORD v31; // [rsp+34h] [rbp+4h] BYREF
  DWORD pcbResult; // [rsp+38h] [rbp+8h] BYREF
  __int128 pvData; // [rsp+40h] [rbp+10h] BYREF
  __int128 v34; // [rsp+50h] [rbp+20h]
  __int128 v35; // [rsp+60h] [rbp+30h]
  _BYTE v36[16]; // [rsp+70h] [rbp+40h] BYREF
  __int128 v37; // [rsp+80h] [rbp+50h]
  int v38; // [rsp+90h] [rbp+60h]
  _BYTE v39[16]; // [rsp+98h] [rbp+68h] BYREF
  __int128 v40; // [rsp+A8h] [rbp+78h]
  int v41; // [rsp+B8h] [rbp+88h]
  _QWORD v42[2]; // [rsp+C0h] [rbp+90h] BYREF
  int v43; // [rsp+D0h] [rbp+A0h]
  int v44; // [rsp+D4h] [rbp+A4h]
  BYTE pbOutput[528]; // [rsp+E0h] [rbp+B0h] BYREF

  pdwDataLen = 0;
  v31 = 0;
  *a7 = 0;
  v41 = 3;
  v38 = 3;
  p_pdwDataLen = 0;
  p_pcbResult = 0;
  pvData = 0;
  v34 = 0;
  v35 = 0;
  v40 = 0;
  v37 = 0;
  if ( !hObject || !a4 || !cbCertEncoded )
    goto LABEL_43;
  CertificateContext = CertCreateCertificateContext(0x10001u, a4, cbCertEncoded);
  *a7 = CertificateContext;
  if ( !CertificateContext )
  {
LABEL_5:
    Property = -1073741023;
    goto LABEL_44;
  }
  if ( (unsigned int)(a2 - 1) <= 0xFFFFFFFD )
  {
    LastError = 0;
    if ( !CryptGetProvParam(hObject, 6u, 0, &pdwDataLen, 0) )
      goto LABEL_5;
    v15 = pdwDataLen;
    if ( !pdwDataLen
      || pdwDataLen > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)pdwDataLen + g_ulAdditionalProbeSize + 8 < pdwDataLen
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_57;
    }
    v16 = v15 + 23;
    if ( v15 + 23 <= v15 + 8 )
      v16 = 0xFFFFFFFFFFFFFF0LL;
    v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
    v18 = alloca(v17);
    v19 = alloca(v17);
    p_pdwDataLen = &pdwDataLen;
    if ( v29 == (_BYTE *)-48LL || (pdwDataLen = 1801679955, (p_pdwDataLen = &pcbResult) == 0) )
    {
LABEL_57:
      if ( v15 + 8 >= v15 )
      {
        v20 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        p_pdwDataLen = v20;
        if ( v20 )
        {
          *v20 = 1885431112;
          p_pdwDataLen = v20 + 2;
        }
      }
    }
    if ( p_pdwDataLen )
    {
      if ( !CryptGetProvParam(hObject, 6u, (BYTE *)p_pdwDataLen, &pdwDataLen, 0) )
        goto LABEL_5;
      CUnicodeString::Set((CUnicodeString *)v39, (const char *)p_pdwDataLen);
      if ( !CryptGetProvParam(hObject, 4u, 0, &v31, 0) )
        goto LABEL_5;
      v21 = v31;
      if ( !v31
        || v31 > (unsigned __int64)g_ulMaxStackAllocSize
        || (unsigned __int64)v31 + g_ulAdditionalProbeSize + 8 < v31
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_58;
      }
      v22 = v21 + 23;
      if ( v21 + 23 <= v21 + 8 )
        v22 = 0xFFFFFFFFFFFFFF0LL;
      v23 = v22 & 0xFFFFFFFFFFFFFFF0uLL;
      v24 = alloca(v23);
      v25 = alloca(v23);
      p_pcbResult = &pdwDataLen;
      if ( v29 == (_BYTE *)-48LL || (pdwDataLen = 1801679955, (p_pcbResult = &pcbResult) == 0) )
      {
LABEL_58:
        if ( v21 + 8 >= v21 )
        {
          v26 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          p_pcbResult = v26;
          if ( v26 )
          {
            *v26 = 1885431112;
            p_pcbResult = v26 + 2;
          }
        }
      }
      if ( p_pcbResult )
      {
        if ( !CryptGetProvParam(hObject, 4u, (BYTE *)p_pcbResult, &v31, 0) )
          goto LABEL_5;
        Property = 0;
        CUnicodeString::Set((CUnicodeString *)v36, (const char *)p_pcbResult);
        *(_QWORD *)&pvData = CUnicodeString::Unicode((CUnicodeString *)v39);
        *((_QWORD *)&pvData + 1) = CUnicodeString::Unicode((CUnicodeString *)v36);
        LODWORD(v34) = 1;
        *(_QWORD *)((char *)&v34 + 4) = 1;
        *(_QWORD *)&v35 = 0;
        DWORD2(v35) = a2;
LABEL_40:
        if ( CertSetCertificateContextProperty(*a7, 2u, 0, &pvData) )
        {
          v27 = *a7;
          v42[0] = 24;
          v44 = 0;
          v42[1] = hObject;
          v43 = DWORD2(v35);
          if ( CertSetCertificateContextProperty(v27, 5u, 0, v42) )
            goto LABEL_46;
        }
        goto LABEL_5;
      }
    }
    Property = -1073741670;
    goto LABEL_44;
  }
  memset_0(pbOutput, 0, 0x20Au);
  pcbResult = 520;
  if ( !a3 )
  {
LABEL_43:
    Property = -1073741811;
    goto LABEL_44;
  }
  Property = NCryptGetProperty(hObject, L"Unique Name", pbOutput, 0x208u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    *((_QWORD *)&pvData + 1) = a3;
    *(_QWORD *)&pvData = pbOutput;
    LastError = 0;
    DWORD2(v35) = -1;
    goto LABEL_40;
  }
LABEL_44:
  LastError = GetLastError();
  Property = LogEventAndTranslateLastErrorToNtStatus(Property, 0x1000Cu, LastError);
  if ( *a7 )
  {
    CertFreeCertificateContext(*a7);
    *a7 = 0;
  }
LABEL_46:
  if ( p_pdwDataLen && *(p_pdwDataLen - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( p_pcbResult && *(p_pcbResult - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( LastError )
    SetLastError(LastError);
  CUnicodeString::~CUnicodeString((CUnicodeString *)v36);
  CUnicodeString::~CUnicodeString((CUnicodeString *)v39);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18003cf44  push    rbp
0x18003cf46  push    rbx
0x18003cf47  push    rsi
0x18003cf48  push    rdi
0x18003cf49  push    r12
0x18003cf4b  push    r13
0x18003cf4d  push    r14
0x18003cf4f  push    r15
0x18003cf51  sub     rsp, 308h
0x18003cf58  lea     rbp, [rsp+30h]
0x18003cf5d  mov     rax, cs:__security_cookie
0x18003cf64  xor     rax, rbp
0x18003cf67  mov     [rbp+310h+var_50], rax
0x18003cf6e  mov     r12, [rbp+310h+arg_30]
0x18003cf75  xor     ebx, ebx
0x18003cf77  mov     [rbp+310h+pdwDataLen], ebx
0x18003cf7a  xorps   xmm0, xmm0
0x18003cf7d  mov     [rbp+310h+var_30C], ebx
0x18003cf80  mov     r14, r8
0x18003cf83  mov     r8d, [rbp+310h+cbCertEncoded]; cbCertEncoded
0x18003cf8a  mov     r13d, edx
0x18003cf8d  mov     [r12], rbx
0x18003cf91  lea     eax, [rbx+3]
0x18003cf94  mov     [rbp+310h+var_288], eax
0x18003cf9a  mov     r15, rcx
0x18003cf9d  mov     [rbp+310h+var_2B0], eax
0x18003cfa0  mov     esi, ebx
0x18003cfa2  mov     edi, ebx
0x18003cfa4  movups  [rbp+310h+pvData], xmm0
0x18003cfa8  movups  [rbp+310h+var_2F0], xmm0
0x18003cfac  movups  [rbp+310h+var_2E0], xmm0
0x18003cfb0  movdqu  [rbp+310h+var_298], xmm0
0x18003cfb5  movdqu  [rbp+310h+var_2C0], xmm0
0x18003cfba  test    rcx, rcx
0x18003cfbd  jz      loc_18003D2D5
0x18003cfc3  test    r9, r9
0x18003cfc6  jz      loc_18003D2D5
0x18003cfcc  test    r8d, r8d
0x18003cfcf  jz      loc_18003D2D5
0x18003cfd5  mov     rdx, r9; pbCertEncoded
0x18003cfd8  mov     ecx, 10001h; dwCertEncodingType
0x18003cfdd  call    cs:__imp_CertCreateCertificateContext
0x18003cfe3  mov     [r12], rax
0x18003cfe7  test    rax, rax
0x18003cfea  jnz     short loc_18003CFF6
0x18003cfec  mov     ebx, 0C0000321h
0x18003cff1  jmp     loc_18003D2DA
0x18003cff6  lea     eax, [r13-1]
0x18003cffa  cmp     eax, 0FFFFFFFDh
0x18003cffd  ja      loc_18003D20B
0x18003d003  xor     r14d, r14d
0x18003d006  lea     r9, [rbp+310h+pdwDataLen]; pdwDataLen
0x18003d00a  xor     r8d, r8d; pbData
0x18003d00d  mov     [rsp+340h+dwFlags], r14d; dwFlags
0x18003d012  mov     rcx, r15; hProv
0x18003d015  lea     edx, [r14+6]; dwParam
0x18003d019  call    cs:__imp_CryptGetProvParam
0x18003d01f  test    eax, eax
0x18003d021  jz      short loc_18003CFEC
0x18003d023  mov     ebx, [rbp+310h+pdwDataLen]
0x18003d026  test    rbx, rbx
0x18003d029  jz      short loc_18003D08C
0x18003d02b  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18003d032  ja      short loc_18003D08C
0x18003d034  mov     rcx, cs:g_ulAdditionalProbeSize
0x18003d03b  add     rcx, 8
0x18003d03f  add     rcx, rbx
0x18003d042  cmp     rcx, rbx
0x18003d045  jb      short loc_18003D08C
0x18003d047  call    VerifyStackAvailable
0x18003d04c  test    eax, eax
0x18003d04e  jz      short loc_18003D08C
0x18003d050  lea     rax, [rbx+8]
0x18003d054  lea     rcx, [rax+0Fh]
0x18003d058  cmp     rcx, rax
0x18003d05b  ja      short loc_18003D067
0x18003d05d  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18003d067  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18003d06b  mov     rax, rcx
0x18003d06e  call    _alloca_probe
0x18003d073  sub     rsp, rcx
0x18003d076  lea     rsi, [rsp+340h+pdwDataLen]
0x18003d07b  test    rsi, rsi
0x18003d07e  jz      short loc_18003D08C
0x18003d080  mov     dword ptr [rsi], 6B637453h
0x18003d086  add     rsi, 8
0x18003d08a  jnz     short loc_18003D0B3
0x18003d08c  lea     rcx, [rbx+8]
0x18003d090  cmp     rcx, rbx
0x18003d093  jb      short loc_18003D0B3
0x18003d095  mov     rax, cs:g_pfnAllocate
0x18003d09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0a1  mov     rsi, rax
0x18003d0a4  test    rax, rax
0x18003d0a7  jz      short loc_18003D0B3
0x18003d0a9  mov     dword ptr [rax], 70616548h
0x18003d0af  add     rsi, 8
0x18003d0b3  test    rsi, rsi
0x18003d0b6  jnz     short loc_18003D0C2
0x18003d0b8  mov     ebx, 0C000009Ah
0x18003d0bd  jmp     loc_18003D2DA
0x18003d0c2  lea     r9, [rbp+310h+pdwDataLen]; pdwDataLen
0x18003d0c6  mov     [rsp+340h+dwFlags], r14d; dwFlags
0x18003d0cb  mov     r8, rsi; pbData
0x18003d0ce  mov     edx, 6; dwParam
0x18003d0d3  mov     rcx, r15; hProv
0x18003d0d6  call    cs:__imp_CryptGetProvParam
0x18003d0dc  test    eax, eax
0x18003d0de  jz      loc_18003CFEC
0x18003d0e4  mov     rdx, rsi; char *
0x18003d0e7  lea     rcx, [rbp+310h+var_2A8]; this
0x18003d0eb  call    ?Set@CUnicodeString@@QEAAPEBDPEBD@Z; CUnicodeString::Set(char const *)
0x18003d0f0  xor     r8d, r8d; pbData
0x18003d0f3  mov     [rsp+340h+dwFlags], r14d; dwFlags
0x18003d0f8  lea     r9, [rbp+310h+var_30C]; pdwDataLen
0x18003d0fc  mov     rcx, r15; hProv
0x18003d0ff  lea     edx, [r8+4]; dwParam
0x18003d103  call    cs:__imp_CryptGetProvParam
0x18003d109  test    eax, eax
0x18003d10b  jz      loc_18003CFEC
0x18003d111  mov     ebx, [rbp+310h+var_30C]
0x18003d114  test    rbx, rbx
0x18003d117  jz      short loc_18003D17A
0x18003d119  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18003d120  ja      short loc_18003D17A
0x18003d122  mov     rcx, cs:g_ulAdditionalProbeSize
0x18003d129  add     rcx, 8
0x18003d12d  add     rcx, rbx
0x18003d130  cmp     rcx, rbx
0x18003d133  jb      short loc_18003D17A
0x18003d135  call    VerifyStackAvailable
0x18003d13a  test    eax, eax
0x18003d13c  jz      short loc_18003D17A
0x18003d13e  lea     rax, [rbx+8]
0x18003d142  lea     rcx, [rax+0Fh]
0x18003d146  cmp     rcx, rax
0x18003d149  ja      short loc_18003D155
0x18003d14b  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18003d155  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18003d159  mov     rax, rcx
0x18003d15c  call    _alloca_probe
0x18003d161  sub     rsp, rcx
0x18003d164  lea     rdi, [rsp+340h+pdwDataLen]
0x18003d169  test    rdi, rdi
0x18003d16c  jz      short loc_18003D17A
0x18003d16e  mov     dword ptr [rdi], 6B637453h
0x18003d174  add     rdi, 8
0x18003d178  jnz     short loc_18003D1A1
0x18003d17a  lea     rcx, [rbx+8]
0x18003d17e  cmp     rcx, rbx
0x18003d181  jb      short loc_18003D1A1
0x18003d183  mov     rax, cs:g_pfnAllocate
0x18003d18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d18f  mov     rdi, rax
0x18003d192  test    rax, rax
0x18003d195  jz      short loc_18003D1A1
0x18003d197  mov     dword ptr [rax], 70616548h
0x18003d19d  add     rdi, 8
0x18003d1a1  test    rdi, rdi
0x18003d1a4  jz      loc_18003D0B8
0x18003d1aa  lea     r9, [rbp+310h+var_30C]; pdwDataLen
0x18003d1ae  mov     [rsp+340h+dwFlags], r14d; dwFlags
0x18003d1b3  mov     r8, rdi; pbData
0x18003d1b6  mov     edx, 4; dwParam
0x18003d1bb  mov     rcx, r15; hProv
0x18003d1be  call    cs:__imp_CryptGetProvParam
0x18003d1c4  test    eax, eax
0x18003d1c6  jz      loc_18003CFEC
0x18003d1cc  mov     rdx, rdi; char *
0x18003d1cf  lea     rcx, [rbp+310h+var_2D0]; this
0x18003d1d3  mov     ebx, r14d
0x18003d1d6  call    ?Set@CUnicodeString@@QEAAPEBDPEBD@Z; CUnicodeString::Set(char const *)
0x18003d1db  lea     rcx, [rbp+310h+var_2A8]; this
0x18003d1df  call    ?Unicode@CUnicodeString@@IEAAPEBGXZ; CUnicodeString::Unicode(void)
0x18003d1e4  lea     rcx, [rbp+310h+var_2D0]; this
0x18003d1e8  mov     qword ptr [rbp+310h+pvData], rax
0x18003d1ec  call    ?Unicode@CUnicodeString@@IEAAPEBGXZ; CUnicodeString::Unicode(void)
0x18003d1f1  mov     qword ptr [rbp+310h+pvData+8], rax
0x18003d1f5  mov     eax, 1
0x18003d1fa  mov     dword ptr [rbp+310h+var_2F0], eax
0x18003d1fd  mov     qword ptr [rbp+310h+var_2F0+4], rax
0x18003d201  mov     qword ptr [rbp+310h+var_2E0], r14
0x18003d205  mov     dword ptr [rbp+310h+var_2E0+8], r13d
0x18003d209  jmp     short loc_18003D275
0x18003d20b  xor     edx, edx; Val
0x18003d20d  lea     rcx, [rbp+310h+pbOutput]; void *
0x18003d214  mov     r8d, 20Ah; Size
0x18003d21a  call    memset_0
0x18003d21f  mov     r9d, 208h; cbOutput
0x18003d225  mov     [rbp+310h+pcbResult], r9d
0x18003d229  test    r14, r14
0x18003d22c  jz      loc_18003D2D5
0x18003d232  lea     rax, [rbp+310h+pcbResult]
0x18003d236  mov     [rsp+340h+var_318], ebx; dwFlags
0x18003d23a  lea     r8, [rbp+310h+pbOutput]; pbOutput
0x18003d241  mov     qword ptr [rsp+340h+dwFlags], rax; pcbResult
0x18003d246  lea     rdx, aUniqueName; "Unique Name"
0x18003d24d  mov     rcx, r15; hObject
0x18003d250  call    cs:__imp_NCryptGetProperty
0x18003d256  mov     ebx, eax
0x18003d258  test    eax, eax
0x18003d25a  js      short loc_18003D2DA
0x18003d25c  lea     rax, [rbp+310h+pbOutput]
0x18003d263  mov     qword ptr [rbp+310h+pvData+8], r14
0x18003d267  mov     qword ptr [rbp+310h+pvData], rax
0x18003d26b  xor     r14d, r14d
0x18003d26e  mov     dword ptr [rbp+310h+var_2E0+8], 0FFFFFFFFh
0x18003d275  mov     rcx, [r12]; pCertContext
0x18003d279  lea     r9, [rbp+310h+pvData]; pvData
0x18003d27d  xor     r8d, r8d; dwFlags
0x18003d280  lea     edx, [r8+2]; dwPropId
0x18003d284  call    cs:__imp_CertSetCertificateContextProperty
0x18003d28a  test    eax, eax
0x18003d28c  jz      loc_18003CFEC
0x18003d292  mov     eax, dword ptr [rbp+310h+var_2E0+8]
0x18003d295  lea     r9, [rbp+310h+var_280]; pvData
0x18003d29c  mov     rcx, [r12]; pCertContext
0x18003d2a0  xor     r8d, r8d; dwFlags
0x18003d2a3  mov     [rbp+310h+var_280], 18h
0x18003d2ae  mov     [rbp+310h+var_26C], r14d
0x18003d2b5  mov     [rbp+310h+var_278], r15
0x18003d2bc  lea     edx, [r8+5]; dwPropId
0x18003d2c0  mov     [rbp+310h+var_270], eax
0x18003d2c6  call    cs:__imp_CertSetCertificateContextProperty
0x18003d2cc  test    eax, eax
0x18003d2ce  jnz     short loc_18003D30B
0x18003d2d0  jmp     loc_18003CFEC
0x18003d2d5  mov     ebx, 0C000000Dh
0x18003d2da  call    cs:__imp_GetLastError
0x18003d2e0  mov     edx, 1000Ch; unsigned int
0x18003d2e5  mov     ecx, ebx; int
0x18003d2e7  mov     r8d, eax; unsigned int
0x18003d2ea  mov     r14d, eax
0x18003d2ed  call    ?LogEventAndTranslateLastErrorToNtStatus@@YAJJKK@Z; LogEventAndTranslateLastErrorToNtStatus(long,ulong,ulong)
0x18003d2f2  mov     rcx, [r12]; pCertContext
0x18003d2f6  mov     ebx, eax
0x18003d2f8  test    rcx, rcx
0x18003d2fb  jz      short loc_18003D30B
0x18003d2fd  call    cs:__imp_CertFreeCertificateContext
0x18003d303  mov     qword ptr [r12], 0
0x18003d30b  test    rsi, rsi
0x18003d30e  jz      short loc_18003D328
0x18003d310  lea     rcx, [rsi-8]
0x18003d314  cmp     dword ptr [rcx], 70616548h
0x18003d31a  jnz     short loc_18003D328
0x18003d31c  mov     rax, cs:g_pfnFree
0x18003d323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d328  test    rdi, rdi
0x18003d32b  jz      short loc_18003D345
0x18003d32d  lea     rcx, [rdi-8]
0x18003d331  cmp     dword ptr [rcx], 70616548h
0x18003d337  jnz     short loc_18003D345
0x18003d339  mov     rax, cs:g_pfnFree
0x18003d340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d345  test    r14d, r14d
0x18003d348  jz      short loc_18003D353
0x18003d34a  mov     ecx, r14d; dwErrCode
0x18003d34d  call    cs:__imp_SetLastError
0x18003d353  lea     rcx, [rbp+310h+var_2D0]; this
0x18003d357  call    ??1CUnicodeString@@QEAA@XZ; CUnicodeString::~CUnicodeString(void)
0x18003d35c  lea     rcx, [rbp+310h+var_2A8]; this
0x18003d360  call    ??1CUnicodeString@@QEAA@XZ; CUnicodeString::~CUnicodeString(void)
0x18003d365  mov     eax, ebx
0x18003d367  mov     rcx, [rbp+310h+var_50]
0x18003d36e  xor     rcx, rbp; StackCookie
0x18003d371  call    __security_check_cookie
0x18003d376  lea     rsp, [rbp+2D8h]
0x18003d37d  pop     r15
0x18003d37f  pop     r14
0x18003d381  pop     r13
0x18003d383  pop     r12
0x18003d385  pop     rdi
0x18003d386  pop     rsi
0x18003d387  pop     rbx
0x18003d388  pop     rbp
0x18003d389  retn
```
