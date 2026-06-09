# SetNgcSelfSignedCertificate(unsigned __int64,ushort const *)

- ea: `0x180027f54`
- end: `0x180028357`
- name: `?SetNgcSelfSignedCertificate@@YAJ_KPEBG@Z`
- size: `1027`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180039c18`

## callees

- `0x180006150`
- `0x180006538`
- `0x180006560`
- `0x1800065c0`
- `0x180018790`
- `0x180027f54`
- `0x180028360`
- `0x180028f9c`
- `0x18002e850`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028099`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028320`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028099`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028320`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800280cc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800280cc`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800280db`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180028124`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800280db`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180028124`
- `ncrypt!NCryptSetProperty` at `0x1800282d4`
- `ncrypt!NCryptSetProperty` at `0x1800282d4`
- `CRYPT32!CertStrToNameW` at `0x180027fee`
- `CRYPT32!CertStrToNameW` at `0x180028070`
- `CRYPT32!CertStrToNameW` at `0x180027fee`
- `CRYPT32!CertStrToNameW` at `0x180028070`
- `CRYPT32!CryptEncodeObjectEx` at `0x180028186`
- `CRYPT32!CryptEncodeObjectEx` at `0x1800281f5`
- `CRYPT32!CryptEncodeObjectEx` at `0x180028186`
- `CRYPT32!CryptEncodeObjectEx` at `0x1800281f5`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x18002827e`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x18002827e`

## string_xrefs

- `0x180027ffc`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18002803d`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180028083`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180028203`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180028292`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x1800282e4`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
__int64 __fastcall SetNgcSelfSignedCertificate(NCRYPT_HANDLE hObject, const unsigned __int16 *a2)
{
  int v4; // eax
  unsigned int LastError; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  const char *v8; // r9
  HLOCAL v9; // rbx
  const char *v10; // r9
  __int64 v11; // rdx
  SECURITY_STATUS v12; // edi
  const char *v13; // r9
  PCCERT_CONTEXT v14; // rax
  const char *v15; // r9
  SECURITY_STATUS v16; // eax
  unsigned __int16 **pbEncoded; // [rsp+20h] [rbp-E0h]
  int pbEncodeda; // [rsp+20h] [rbp-E0h]
  int pbEncodedb; // [rsp+20h] [rbp-E0h]
  DWORD pcbEncoded; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR pszX500; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  PCCERT_CONTEXT v26; // [rsp+68h] [rbp-98h] BYREF
  const char *v27; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v28[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _CERT_EXTENSIONS pExtensions; // [rsp+88h] [rbp-78h] BYREF
  struct _CRYPTOAPI_BLOB pSubjectIssuerBlob; // [rsp+98h] [rbp-68h] BYREF
  const char *v31; // [rsp+B0h] [rbp-50h] BYREF
  int v32; // [rsp+B8h] [rbp-48h]
  DWORD v33; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD pvEncoded[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v35; // [rsp+D8h] [rbp-28h]
  DWORD v36; // [rsp+E0h] [rbp-20h] BYREF
  void *v37; // [rsp+E8h] [rbp-18h] BYREF
  struct _CRYPT_ALGORITHM_IDENTIFIER pSignatureAlgorithm; // [rsp+F0h] [rbp-10h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+108h] [rbp+8h] BYREF
  __int64 pvStructInfo; // [rsp+118h] [rbp+18h] BYREF
  int v41; // [rsp+120h] [rbp+20h]
  struct _SYSTEMTIME pStartTime; // [rsp+128h] [rbp+28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  pszX500 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszX500,
    0);
  v4 = NgcUtils::CombineSeparateStrings(
         (NgcUtils *)L"CN=",
         &LocaleName,
         a2,
         (const unsigned __int16 *)&pszX500,
         pbEncoded);
  LastError = v4;
  if ( v4 < 0 )
  {
    v6 = (unsigned int)v4;
    v7 = 480;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)v6,
      pbEncodeda);
    goto LABEL_34;
  }
  pcbEncoded = 0;
  if ( !CertStrToNameW(1u, pszX500, 0x2000003u, 0, 0, &pcbEncoded, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1EA,
                  (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
                  v8);
    goto LABEL_34;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, pcbEncoded);
  v9 = hMem;
  if ( !hMem )
  {
    LastError = -2147024882;
    v7 = 493;
    v6 = 2147942414LL;
    goto LABEL_7;
  }
  if ( !CertStrToNameW(1u, pszX500, 0x2000003u, 0, (BYTE *)hMem, &pcbEncoded, 0) )
  {
    v11 = 502;
LABEL_10:
    v12 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v11,
            (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
            v10);
LABEL_11:
    if ( v9 )
      LocalFree(v9);
    LastError = v12;
    goto LABEL_34;
  }
  *(&pSubjectIssuerBlob.cbData + 1) = 0;
  pSubjectIssuerBlob.pbData = (BYTE *)v9;
  pStartTime = 0;
  pSubjectIssuerBlob.cbData = pcbEncoded;
  SystemTime = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( !FileTimeToSystemTime(&SystemTimeAsFileTime, &SystemTime) )
  {
    v11 = 515;
    goto LABEL_10;
  }
  SystemTime.wYear += 30;
  if ( SystemTime.wMonth == 2 && SystemTime.wDay >= 0x1Cu )
    SystemTime.wDay = 28;
  *(_QWORD *)&SystemTimeAsFileTime -= 6000000000LL;
  if ( !FileTimeToSystemTime(&SystemTimeAsFileTime, &pStartTime) )
  {
    v11 = 527;
    goto LABEL_10;
  }
  pvStructInfo = 0;
  v41 = 0;
  memset_0(&v31, 0, 0x40u);
  v32 = 1;
  v31 = "2.5.29.19";
  if ( !CryptEncodeObjectEx(1u, (LPCSTR)0xF, &pvStructInfo, 0x8000u, 0, pvEncoded, &v33) )
  {
    v11 = 545;
    goto LABEL_10;
  }
  v25 = pvEncoded[0];
  v28[0] = 1;
  v27 = "1.3.6.1.4.1.311.20.2.2";
  v35 = 0;
  v28[1] = &v27;
  pvEncoded[1] = "2.5.29.37";
  if ( !CryptEncodeObjectEx(1u, (LPCSTR)0x24, v28, 0x8000u, 0, &v37, &v36) )
  {
    v12 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x233,
            (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
            v13);
LABEL_25:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v25);
    goto LABEL_11;
  }
  hMem = v37;
  *(_QWORD *)&pExtensions.cExtension = 2;
  pSignatureAlgorithm.pszObjId = "1.2.840.113549.1.1.11";
  pExtensions.rgExtension = (PCERT_EXTENSION)&v31;
  pSignatureAlgorithm.Parameters = 0;
  v14 = CertCreateSelfSignCertificate(
          hObject,
          &pSubjectIssuerBlob,
          2u,
          0,
          &pSignatureAlgorithm,
          &pStartTime,
          &SystemTime,
          &pExtensions);
  v26 = v14;
  if ( !v14 )
  {
    v12 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x247,
            (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
            v15);
LABEL_28:
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v26);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
    goto LABEL_25;
  }
  v16 = NCryptSetProperty(hObject, L"SmartCardKeyCertificate", v14->pbCertEncoded, v14->cbCertEncoded, 0);
  v12 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v16,
      pbEncodedb);
    goto LABEL_28;
  }
  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v26);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v25);
  if ( v9 )
    LocalFree(v9);
  LastError = 0;
LABEL_34:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszX500);
  return LastError;
}

```

## disassembly

```asm
0x180027f54  mov     [rsp-8+arg_10], rbx
0x180027f59  push    rbp
0x180027f5a  push    rsi
0x180027f5b  push    rdi
0x180027f5c  push    r14
0x180027f5e  push    r15
0x180027f60  lea     rbp, [rsp-40h]
0x180027f65  sub     rsp, 140h
0x180027f6c  mov     rax, cs:__security_cookie
0x180027f73  xor     rax, rsp
0x180027f76  mov     [rbp+60h+var_28], rax
0x180027f7a  mov     rbx, rdx
0x180027f7d  mov     rdi, rcx
0x180027f80  xor     esi, esi
0x180027f82  lea     rcx, [rsp+160h+pszX500]
0x180027f87  xor     edx, edx
0x180027f89  mov     [rsp+160h+pszX500], rsi
0x180027f8e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180027f93  lea     r9, [rsp+160h+pszX500]; unsigned __int16 *
0x180027f98  mov     r8, rbx; unsigned __int16 *
0x180027f9b  lea     rdx, LocaleName; unsigned __int16 *
0x180027fa2  lea     rcx, aCn; "CN="
0x180027fa9  call    ?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)
0x180027fae  mov     ebx, eax
0x180027fb0  test    eax, eax
0x180027fb2  jns     short loc_180027FBE
0x180027fb4  mov     r9d, eax
0x180027fb7  mov     edx, 1E0h
0x180027fbc  jmp     short loc_180028039
0x180027fbe  mov     rdx, [rsp+160h+pszX500]; pszX500
0x180027fc3  lea     rax, [rsp+160h+var_120]
0x180027fc8  xor     r9d, r9d; pvReserved
0x180027fcb  mov     [rsp+160h+ppszError], rsi; ppszError
0x180027fd0  mov     [rsp+160h+pcbEncoded], rax; pcbEncoded
0x180027fd5  mov     r15d, 2000003h
0x180027fdb  mov     r8d, r15d; dwStrType
0x180027fde  mov     [rsp+160h+var_120], esi
0x180027fe2  mov     [rsp+160h+pbEncoded], rsi; int
0x180027fe7  lea     r14d, [r9+1]
0x180027feb  mov     ecx, r14d; dwCertEncodingType
0x180027fee  call    cs:__imp_CertStrToNameW
0x180027ff4  test    eax, eax
0x180027ff6  jnz     short loc_180028014
0x180027ff8  mov     rcx, [rbp+68h]; this
0x180027ffc  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180028003  mov     edx, 1EAh; void *
0x180028008  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002800d  mov     ebx, eax
0x18002800f  jmp     loc_180028328
0x180028014  mov     edx, [rsp+160h+var_120]
0x180028018  lea     rcx, [rsp+160h+hMem]
0x18002801d  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180028022  mov     rbx, [rsp+160h+hMem]
0x180028027  test    rbx, rbx
0x18002802a  jnz     short loc_18002804E
0x18002802c  mov     ebx, 8007000Eh
0x180028031  mov     edx, 1EDh; void *
0x180028036  mov     r9d, ebx; char *
0x180028039  mov     rcx, [rbp+68h]; this
0x18002803d  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180028044  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028049  jmp     loc_180028328
0x18002804e  mov     rdx, [rsp+160h+pszX500]; pszX500
0x180028053  lea     rax, [rsp+160h+var_120]
0x180028058  mov     [rsp+160h+ppszError], rsi; ppszError
0x18002805d  xor     r9d, r9d; pvReserved
0x180028060  mov     [rsp+160h+pcbEncoded], rax; pcbEncoded
0x180028065  mov     r8d, r15d; dwStrType
0x180028068  mov     ecx, r14d; dwCertEncodingType
0x18002806b  mov     [rsp+160h+pbEncoded], rbx; pbEncoded
0x180028070  call    cs:__imp_CertStrToNameW
0x180028076  test    eax, eax
0x180028078  jnz     short loc_1800280A6
0x18002807a  mov     edx, 1F6h; void *
0x18002807f  mov     rcx, [rbp+68h]; this
0x180028083  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18002808a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002808f  mov     edi, eax
0x180028091  test    rbx, rbx
0x180028094  jz      short loc_18002809F
0x180028096  mov     rcx, rbx; hMem
0x180028099  call    cs:__imp_LocalFree
0x18002809f  mov     ebx, edi
0x1800280a1  jmp     loc_180028328
0x1800280a6  mov     eax, [rsp+160h+var_120]
0x1800280aa  lea     rcx, [rsp+160h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800280af  xorps   xmm0, xmm0
0x1800280b2  mov     dword ptr [rbp+60h+pSubjectIssuerBlob+4], esi
0x1800280b5  xorps   xmm1, xmm1
0x1800280b8  mov     [rbp+60h+pSubjectIssuerBlob.pbData], rbx
0x1800280bc  movups  xmmword ptr [rbp+60h+pStartTime.wYear], xmm0
0x1800280c0  mov     [rbp+60h+pSubjectIssuerBlob.cbData], eax
0x1800280c3  movups  xmmword ptr [rbp+60h+SystemTime.wYear], xmm1
0x1800280c7  mov     qword ptr [rsp+160h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x1800280cc  call    cs:__imp_GetSystemTimeAsFileTime
0x1800280d2  lea     rdx, [rbp+60h+SystemTime]; lpSystemTime
0x1800280d6  lea     rcx, [rsp+160h+SystemTimeAsFileTime]; lpFileTime
0x1800280db  call    cs:__imp_FileTimeToSystemTime
0x1800280e1  test    eax, eax
0x1800280e3  jnz     short loc_1800280EC
0x1800280e5  mov     edx, 203h
0x1800280ea  jmp     short loc_18002807F
0x1800280ec  add     [rbp+60h+SystemTime.wYear], 1Eh
0x1800280f1  mov     r15d, 2
0x1800280f7  cmp     [rbp+60h+SystemTime.wMonth], r15w
0x1800280fc  jnz     short loc_18002810C
0x1800280fe  lea     eax, [r15+1Ah]
0x180028102  cmp     [rbp+60h+SystemTime.wDay], ax
0x180028106  jb      short loc_18002810C
0x180028108  mov     [rbp+60h+SystemTime.wDay], ax
0x18002810c  mov     rax, 165A0BC00h
0x180028116  lea     rdx, [rbp+60h+pStartTime]; lpSystemTime
0x18002811a  sub     qword ptr [rsp+160h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002811f  lea     rcx, [rsp+160h+SystemTimeAsFileTime]; lpFileTime
0x180028124  call    cs:__imp_FileTimeToSystemTime
0x18002812a  test    eax, eax
0x18002812c  jnz     short loc_180028138
0x18002812e  mov     edx, 20Fh
0x180028133  jmp     loc_18002807F
0x180028138  xor     edx, edx; Val
0x18002813a  mov     [rbp+60h+pvStructInfo], rsi
0x18002813e  lea     rcx, [rbp+60h+var_B0]; void *
0x180028142  mov     [rbp+60h+var_40], esi
0x180028145  lea     r8d, [rdx+40h]; Size
0x180028149  call    memset_0
0x18002814e  lea     rax, a252919; "2.5.29.19"
0x180028155  mov     [rbp+60h+var_A8], r14d
0x180028159  mov     [rbp+60h+var_B0], rax
0x18002815d  lea     r8, [rbp+60h+pvStructInfo]; pvStructInfo
0x180028161  lea     rax, [rbp+60h+var_A0]
0x180028165  mov     r9d, 8000h; dwFlags
0x18002816b  mov     [rsp+160h+ppszError], rax; pcbEncoded
0x180028170  mov     edx, 0Fh; lpszStructType
0x180028175  lea     rax, [rbp+60h+pvEncoded]
0x180028179  mov     ecx, r14d; dwCertEncodingType
0x18002817c  mov     [rsp+160h+pcbEncoded], rax; pvEncoded
0x180028181  mov     [rsp+160h+pbEncoded], rsi; pEncodePara
0x180028186  call    cs:__imp_CryptEncodeObjectEx
0x18002818c  test    eax, eax
0x18002818e  jnz     short loc_18002819A
0x180028190  mov     edx, 221h
0x180028195  jmp     loc_18002807F
0x18002819a  mov     rax, [rbp+60h+pvEncoded]
0x18002819e  lea     r8, [rsp+160h+var_E8]; pvStructInfo
0x1800281a3  mov     [rsp+160h+var_100], rax
0x1800281a8  mov     r9d, 8000h; dwFlags
0x1800281ae  lea     rax, a1361413112022; "1.3.6.1.4.1.311.20.2.2"
0x1800281b5  mov     [rsp+160h+var_E8], r14
0x1800281ba  mov     [rsp+160h+var_F0], rax
0x1800281bf  mov     edx, 24h ; '$'; lpszStructType
0x1800281c4  lea     rax, [rsp+160h+var_F0]
0x1800281c9  mov     [rbp+60h+var_88], esi
0x1800281cc  mov     [rbp+60h+var_E0], rax
0x1800281d0  mov     ecx, r14d; dwCertEncodingType
0x1800281d3  lea     rax, a252937; "2.5.29.37"
0x1800281da  mov     [rbp+60h+var_90], rax
0x1800281de  lea     rax, [rbp+60h+var_80]
0x1800281e2  mov     [rsp+160h+ppszError], rax; pcbEncoded
0x1800281e7  lea     rax, [rbp+60h+var_78]
0x1800281eb  mov     [rsp+160h+pcbEncoded], rax; pvEncoded
0x1800281f0  mov     [rsp+160h+pbEncoded], rsi; pEncodePara
0x1800281f5  call    cs:__imp_CryptEncodeObjectEx
0x1800281fb  test    eax, eax
0x1800281fd  jnz     short loc_180028225
0x1800281ff  mov     rcx, [rbp+68h]; this
0x180028203  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18002820a  mov     edx, 233h; void *
0x18002820f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028214  mov     edi, eax
0x180028216  lea     rcx, [rsp+160h+var_100]; void *
0x18002821b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180028220  jmp     loc_180028091
0x180028225  mov     rax, [rbp+60h+var_78]
0x180028229  lea     rdx, [rbp+60h+pSubjectIssuerBlob]; pSubjectIssuerBlob
0x18002822d  mov     [rsp+160h+hMem], rax
0x180028232  xorps   xmm0, xmm0
0x180028235  lea     rax, a12840113549111; "1.2.840.113549.1.1.11"
0x18002823c  mov     qword ptr [rbp+60h+var_D8.cExtension], r15
0x180028240  mov     [rbp+60h+pSignatureAlgorithm.pszObjId], rax
0x180028244  xor     r9d, r9d; pKeyProvInfo
0x180028247  lea     rax, [rbp+60h+var_B0]
0x18002824b  mov     r8d, r15d; dwFlags
0x18002824e  mov     [rbp+60h+var_D8.rgExtension], rax
0x180028252  mov     rcx, rdi; hCryptProvOrNCryptKey
0x180028255  lea     rax, [rbp+60h+var_D8]
0x180028259  mov     [rsp+160h+pExtensions], rax; pExtensions
0x18002825e  lea     rax, [rbp+60h+SystemTime]
0x180028262  mov     [rsp+160h+ppszError], rax; pEndTime
0x180028267  lea     rax, [rbp+60h+pStartTime]
0x18002826b  mov     [rsp+160h+pcbEncoded], rax; pStartTime
0x180028270  lea     rax, [rbp+60h+pSignatureAlgorithm]
0x180028274  mov     [rsp+160h+pbEncoded], rax; pSignatureAlgorithm
0x180028279  movdqu  xmmword ptr [rbp+60h+pSignatureAlgorithm.Parameters.cbData], xmm0
0x18002827e  call    cs:__imp_CertCreateSelfSignCertificate
0x180028284  mov     [rsp+160h+var_F8], rax
0x180028289  test    rax, rax
0x18002828c  jnz     short loc_1800282BE
0x18002828e  mov     rcx, [rbp+68h]; this
0x180028292  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180028299  mov     edx, 247h; void *
0x18002829e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800282a3  mov     edi, eax
0x1800282a5  lea     rcx, [rsp+160h+var_F8]
0x1800282aa  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x1800282af  lea     rcx, [rsp+160h+hMem]; void *
0x1800282b4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800282b9  jmp     loc_180028216
0x1800282be  mov     r9d, [rax+10h]; cbInput
0x1800282c2  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x1800282c9  mov     r8, [rax+8]; pbInput
0x1800282cd  mov     rcx, rdi; hObject
0x1800282d0  mov     dword ptr [rsp+160h+pbEncoded], esi; int
0x1800282d4  call    cs:__imp_NCryptSetProperty
0x1800282da  mov     edi, eax
0x1800282dc  test    eax, eax
0x1800282de  jns     short loc_1800282FA
0x1800282e0  mov     rcx, [rbp+68h]; this
0x1800282e4  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800282eb  mov     r9d, eax; char *
0x1800282ee  mov     edx, 24Fh; void *
0x1800282f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800282f8  jmp     short loc_1800282A5
0x1800282fa  lea     rcx, [rsp+160h+var_F8]
0x1800282ff  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180028304  lea     rcx, [rsp+160h+hMem]; void *
0x180028309  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002830e  lea     rcx, [rsp+160h+var_100]; void *
0x180028313  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180028318  test    rbx, rbx
0x18002831b  jz      short loc_180028326
0x18002831d  mov     rcx, rbx; hMem
0x180028320  call    cs:__imp_LocalFree
0x180028326  mov     ebx, esi
0x180028328  lea     rcx, [rsp+160h+pszX500]; void *
0x18002832d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180028332  mov     eax, ebx
0x180028334  mov     rcx, [rbp+60h+var_28]
0x180028338  xor     rcx, rsp; StackCookie
0x18002833b  call    __security_check_cookie
0x180028340  mov     rbx, [rsp+160h+arg_10]
0x180028348  add     rsp, 140h
0x18002834f  pop     r15
0x180028351  pop     r14
0x180028353  pop     rdi
0x180028354  pop     rsi
0x180028355  pop     rbp
0x180028356  retn
```
