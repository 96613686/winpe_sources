# ShouldEnrollAikCert(ushort const *,bool *)

- ea: `0x180016b24`
- end: `0x180016e54`
- name: `?ShouldEnrollAikCert@@YAJPEBGPEA_N@Z`
- size: `816`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800126e4`

## callees

- `0x180006330`
- `0x18000cc14`
- `0x18000cc34`
- `0x18000ebc0`
- `0x180010248`
- `0x1800166e8`
- `0x180016708`
- `0x180016740`
- `0x180016b24`
- `0x18001d748`
- `0x18001d954`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016cc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016d29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016d6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016dbe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016cc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016d29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016d6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016dbe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e23`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016d41`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016d41`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016cf1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016cf1`
- `CRYPT32!CertCreateCertificateContext` at `0x180016c87`
- `CRYPT32!CertCreateCertificateContext` at `0x180016c87`
- `ncrypt!NCryptSetProperty` at `0x180016de7`
- `ncrypt!NCryptSetProperty` at `0x180016de7`

## string_xrefs

- `0x180016b6f`: `onecore\ds\security\ngc\ngctask\dll\utilities.cpp`
- `0x180016be7`: `onecore\ds\security\ngc\ngctask\dll\utilities.cpp`
- `0x180016c31`: `onecore\ds\security\ngc\ngctask\dll\utilities.cpp`
- `0x180016c9d`: `onecore\ds\security\ngc\ngctask\dll\utilities.cpp`
- `0x180016cff`: `onecore\ds\security\ngc\ngctask\dll\utilities.cpp`
- `0x180016d95`: `onecore\ds\security\ngc\ngctask\dll\utilities.cpp`
- `0x180016df8`: `onecore\ds\security\ngc\ngctask\dll\utilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ShouldEnrollAikCert(NgcUtils *a1, bool *a2, unsigned __int64 *a3)
{
  int v4; // eax
  int NCryptBinaryBlob; // ebx
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // rcx
  struct _FILETIME *v8; // r8
  HLOCAL v9; // rcx
  HLOCAL v10; // rcx
  HLOCAL v11; // rcx
  PCCERT_CONTEXT CertificateContext; // rbx
  const char *v13; // r9
  HLOCAL v14; // rcx
  const char *v15; // r9
  HLOCAL v16; // rcx
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // rcx
  struct _FILETIME *v19; // r8
  HLOCAL v20; // rcx
  HLOCAL v21; // rcx
  SECURITY_STATUS v23; // eax
  HLOCAL v24; // rcx
  DWORD dwFlags; // [rsp+20h] [rbp-29h]
  bool v26; // [rsp+30h] [rbp-19h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-11h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+40h] [rbp-9h] BYREF
  int v29; // [rsp+48h] [rbp-1h]
  DWORD cbCertEncoded; // [rsp+4Ch] [rbp+3h] BYREF
  PCCERT_CONTEXT v31; // [rsp+50h] [rbp+7h] BYREF
  struct _FILETIME FileTime; // [rsp+58h] [rbp+Fh] BYREF
  HLOCAL *p_hMem; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int16 v34[4]; // [rsp+68h] [rbp+1Fh] BYREF
  char v35; // [rsp+70h] [rbp+27h]
  SYSTEMTIME SystemTime; // [rsp+78h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v29 = 0;
  *a2 = 0;
  hObject = 0;
  v4 = NgcUtils::OpenAikNCryptHandle(a1, (const unsigned __int16 *)&hObject, a3);
  NCryptBinaryBlob = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\utilities.cpp",
      (const char *)(unsigned int)v4,
      dwFlags);
LABEL_31:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    return (unsigned int)NCryptBinaryBlob;
  }
  cbCertEncoded = 0;
  hMem = 0;
  p_hMem = &hMem;
  *(_QWORD *)v34 = 0;
  v35 = 1;
  v29 = 1;
  NCryptBinaryBlob = NgcUtils::GetNCryptBinaryBlob(
                       hObject,
                       L"SmartCardKeyCertificate",
                       v34,
                       (unsigned __int8 **)&cbCertEncoded);
  v29 = 0;
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
  if ( NCryptBinaryBlob < 0 )
  {
    if ( NCryptBinaryBlob == -2146893807 )
    {
      v26 = 0;
      IsRegDwordEnabled(v7, v6, v8, &v26);
      if ( v26 )
      {
        NCryptBinaryBlob = -2147023636;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8C,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\utilities.cpp",
          (const char *)0x800704ECLL,
          dwFlags);
        v10 = hMem;
        hMem = 0;
        if ( v10 )
          LocalFree(v10);
      }
      else
      {
        *a2 = 1;
        v11 = hMem;
        hMem = 0;
        if ( v11 )
          LocalFree(v11);
        NCryptBinaryBlob = 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\utilities.cpp",
        (const char *)(unsigned int)NCryptBinaryBlob,
        dwFlags);
      v9 = hMem;
      hMem = 0;
      if ( v9 )
        LocalFree(v9);
    }
    goto LABEL_31;
  }
  CertificateContext = CertCreateCertificateContext(0x10001u, (const BYTE *)hMem, cbCertEncoded);
  v31 = CertificateContext;
  if ( !CertificateContext )
  {
    NCryptBinaryBlob = wil::details::in1diag3::Return_GetLastError(
                         retaddr,
                         (void *)0x98,
                         (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\utilities.cpp",
                         v13);
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v31);
    v14 = hMem;
    hMem = 0;
    if ( v14 )
      LocalFree(v14);
    goto LABEL_31;
  }
  FileTime = 0;
  *(_DWORD *)&SystemTime.wYear = 526309;
  *(_QWORD *)&SystemTime.wDayOfWeek = 1310725;
  *(_DWORD *)&SystemTime.wSecond = 0;
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    NCryptBinaryBlob = wil::details::in1diag3::Return_GetLastError(
                         retaddr,
                         (void *)0x9D,
                         (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\utilities.cpp",
                         v15);
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v31);
    v16 = hMem;
    hMem = 0;
    if ( v16 )
      LocalFree(v16);
    goto LABEL_31;
  }
  if ( CompareFileTime(&CertificateContext->pCertInfo->NotBefore, &FileTime) < 0 || *(_DWORD *)&g_reenrollAik )
  {
    v26 = 0;
    IsRegDwordEnabled(v18, v17, v19, &v26);
    if ( v26 )
    {
      NCryptBinaryBlob = -2147023636;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\utilities.cpp",
        (const char *)0x800704ECLL,
        dwFlags);
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v31);
      v21 = hMem;
      hMem = 0;
      if ( v21 )
        LocalFree(v21);
      goto LABEL_31;
    }
    v23 = NCryptSetProperty(hObject, L"SmartCardKeyCertificate", 0, 0, 0);
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAC,
        (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\utilities.cpp",
        (const char *)(unsigned int)v23);
    *a2 = 1;
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v31);
    v24 = hMem;
    hMem = 0;
    if ( v24 )
      LocalFree(v24);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v31);
    v20 = hMem;
    hMem = 0;
    if ( v20 )
      LocalFree(v20);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  return 0;
}

```

## disassembly

```asm
0x180016b24  mov     [rsp-8+arg_10], rbx
0x180016b29  push    rbp
0x180016b2a  push    rsi
0x180016b2b  push    rdi
0x180016b2c  lea     rbp, [rsp-47h]
0x180016b31  sub     rsp, 90h
0x180016b38  mov     rax, cs:__security_cookie
0x180016b3f  xor     rax, rsp
0x180016b42  mov     [rbp+57h+var_18], rax
0x180016b46  mov     rdi, rdx
0x180016b49  xor     esi, esi
0x180016b4b  mov     [rbp+57h+var_58], esi
0x180016b4e  mov     [rdx], sil
0x180016b51  mov     [rbp+57h+hObject], rsi
0x180016b55  mov     [rbp+57h+hObject], rsi
0x180016b59  lea     rdx, [rbp+57h+hObject]; unsigned __int16 *
0x180016b5d  call    ?OpenAikNCryptHandle@NgcUtils@@YAJPEBGPEA_K@Z; NgcUtils::OpenAikNCryptHandle(ushort const *,unsigned __int64 *)
0x180016b62  mov     ebx, eax
0x180016b64  test    eax, eax
0x180016b66  jns     short loc_180016B84
0x180016b68  mov     rcx, [rbp+5Fh]; this
0x180016b6c  mov     r9d, eax; char *
0x180016b6f  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180016b76  lea     edx, [rsi+7Ch]; void *
0x180016b79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b7e  nop
0x180016b7f  jmp     loc_180016DC5
0x180016b84  mov     [rbp+57h+cbCertEncoded], esi
0x180016b87  mov     [rbp+57h+hMem], rsi
0x180016b8b  lea     rax, [rbp+57h+hMem]
0x180016b8f  mov     [rbp+57h+var_40], rax
0x180016b93  mov     qword ptr [rbp+57h+var_38], rsi
0x180016b97  mov     [rbp+57h+var_30], 1
0x180016b9b  mov     [rbp+57h+var_58], 1
0x180016ba2  lea     r9, [rbp+57h+cbCertEncoded]; unsigned __int8 **
0x180016ba6  lea     r8, [rbp+57h+var_38]; unsigned __int16 *
0x180016baa  lea     rdx, pszProperty; "SmartCardKeyCertificate"
0x180016bb1  mov     rcx, [rbp+57h+hObject]; hObject
0x180016bb5  call    ?GetNCryptBinaryBlob@NgcUtils@@YAJ_KPEBGPEAPEAEPEAK@Z; NgcUtils::GetNCryptBinaryBlob(unsigned __int64,ushort const *,uchar * *,ulong *)
0x180016bba  mov     ebx, eax
0x180016bbc  mov     ecx, 1
0x180016bc1  and     ecx, 0FFFFFFFEh
0x180016bc4  mov     [rbp+57h+var_58], ecx
0x180016bc7  lea     rcx, [rbp+57h+var_40]
0x180016bcb  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180016bd0  test    ebx, ebx
0x180016bd2  jns     loc_180016C7A
0x180016bd8  cmp     ebx, 80090011h
0x180016bde  jz      short loc_180016C12
0x180016be0  mov     rcx, [rbp+5Fh]; this
0x180016be4  mov     r9d, ebx; char *
0x180016be7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180016bee  mov     edx, 88h; void *
0x180016bf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016bf8  nop
0x180016bf9  mov     rcx, [rbp+57h+hMem]; hMem
0x180016bfd  mov     [rbp+57h+hMem], rsi
0x180016c01  test    rcx, rcx
0x180016c04  jz      short loc_180016C0D
0x180016c06  call    cs:__imp_LocalFree
0x180016c0c  nop
0x180016c0d  jmp     loc_180016DC5
0x180016c12  mov     [rbp+57h+var_70], sil
0x180016c16  lea     r9, [rbp+57h+var_70]; bool *
0x180016c1a  call    ?IsRegDwordEnabled@@YAXPEBG0PEAU_FILETIME@@PEA_N@Z; IsRegDwordEnabled(ushort const *,ushort const *,_FILETIME *,bool *)
0x180016c1f  cmp     [rbp+57h+var_70], sil
0x180016c23  jz      short loc_180016C5C
0x180016c25  mov     rcx, [rbp+5Fh]; this
0x180016c29  mov     ebx, 800704ECh
0x180016c2e  mov     r9d, ebx; char *
0x180016c31  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180016c38  mov     edx, 8Ch; void *
0x180016c3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c42  nop
0x180016c43  mov     rcx, [rbp+57h+hMem]; hMem
0x180016c47  mov     [rbp+57h+hMem], rsi
0x180016c4b  test    rcx, rcx
0x180016c4e  jz      short loc_180016C57
0x180016c50  call    cs:__imp_LocalFree
0x180016c56  nop
0x180016c57  jmp     loc_180016DC5
0x180016c5c  mov     byte ptr [rdi], 1
0x180016c5f  mov     rcx, [rbp+57h+hMem]; hMem
0x180016c63  mov     [rbp+57h+hMem], rsi
0x180016c67  test    rcx, rcx
0x180016c6a  jz      short loc_180016C73
0x180016c6c  call    cs:__imp_LocalFree
0x180016c72  nop
0x180016c73  mov     ebx, esi
0x180016c75  jmp     loc_180016DC5
0x180016c7a  mov     r8d, [rbp+57h+cbCertEncoded]; cbCertEncoded
0x180016c7e  mov     rdx, [rbp+57h+hMem]; pbCertEncoded
0x180016c82  mov     ecx, 10001h; dwCertEncodingType
0x180016c87  call    cs:__imp_CertCreateCertificateContext
0x180016c8d  mov     rbx, rax
0x180016c90  mov     [rbp+57h+var_50], rax
0x180016c94  test    rax, rax
0x180016c97  jnz     short loc_180016CD3
0x180016c99  mov     rcx, [rbp+5Fh]; this
0x180016c9d  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180016ca4  mov     edx, 98h; void *
0x180016ca9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016cae  mov     ebx, eax
0x180016cb0  lea     rcx, [rbp+57h+var_50]
0x180016cb4  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180016cb9  nop
0x180016cba  mov     rcx, [rbp+57h+hMem]; hMem
0x180016cbe  mov     [rbp+57h+hMem], rsi
0x180016cc2  test    rcx, rcx
0x180016cc5  jz      short loc_180016CCE
0x180016cc7  call    cs:__imp_LocalFree
0x180016ccd  nop
0x180016cce  jmp     loc_180016DC5
0x180016cd3  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rsi
0x180016cd7  mov     dword ptr [rbp+57h+SystemTime.wYear], 807E5h
0x180016cde  mov     qword ptr [rbp+57h+SystemTime.wDayOfWeek], 140005h
0x180016ce6  mov     dword ptr [rbp+57h+SystemTime.wSecond], esi
0x180016ce9  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180016ced  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180016cf1  call    cs:__imp_SystemTimeToFileTime
0x180016cf7  test    eax, eax
0x180016cf9  jnz     short loc_180016D35
0x180016cfb  mov     rcx, [rbp+5Fh]; this
0x180016cff  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180016d06  mov     edx, 9Dh; void *
0x180016d0b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016d10  mov     ebx, eax
0x180016d12  lea     rcx, [rbp+57h+var_50]
0x180016d16  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180016d1b  nop
0x180016d1c  mov     rcx, [rbp+57h+hMem]; hMem
0x180016d20  mov     [rbp+57h+hMem], rsi
0x180016d24  test    rcx, rcx
0x180016d27  jz      short loc_180016D30
0x180016d29  call    cs:__imp_LocalFree
0x180016d2f  nop
0x180016d30  jmp     loc_180016DC5
0x180016d35  mov     rcx, [rbx+18h]
0x180016d39  add     rcx, 40h ; '@'; lpFileTime1
0x180016d3d  lea     rdx, [rbp+57h+FileTime]; lpFileTime2
0x180016d41  call    cs:__imp_CompareFileTime
0x180016d47  test    eax, eax
0x180016d49  js      short loc_180016D76
0x180016d4b  cmp     cs:?g_reenrollAik@@3KA, esi; ulong g_reenrollAik
0x180016d51  ja      short loc_180016D76
0x180016d53  lea     rcx, [rbp+57h+var_50]
0x180016d57  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180016d5c  nop
0x180016d5d  mov     rcx, [rbp+57h+hMem]; hMem
0x180016d61  mov     [rbp+57h+hMem], rsi
0x180016d65  test    rcx, rcx
0x180016d68  jz      short loc_180016D71
0x180016d6a  call    cs:__imp_LocalFree
0x180016d70  nop
0x180016d71  jmp     loc_180016E2A
0x180016d76  mov     [rbp+57h+var_70], sil
0x180016d7a  lea     r9, [rbp+57h+var_70]; bool *
0x180016d7e  call    ?IsRegDwordEnabled@@YAXPEBG0PEAU_FILETIME@@PEA_N@Z; IsRegDwordEnabled(ushort const *,ushort const *,_FILETIME *,bool *)
0x180016d83  cmp     [rbp+57h+var_70], sil
0x180016d87  jz      short loc_180016DD2
0x180016d89  mov     rcx, [rbp+5Fh]; this
0x180016d8d  mov     ebx, 800704ECh
0x180016d92  mov     r9d, ebx; char *
0x180016d95  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180016d9c  mov     edx, 0A3h; void *
0x180016da1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016da6  nop
0x180016da7  lea     rcx, [rbp+57h+var_50]
0x180016dab  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180016db0  nop
0x180016db1  mov     rcx, [rbp+57h+hMem]; hMem
0x180016db5  mov     [rbp+57h+hMem], rsi
0x180016db9  test    rcx, rcx
0x180016dbc  jz      short loc_180016DC5
0x180016dbe  call    cs:__imp_LocalFree
0x180016dc4  nop
0x180016dc5  lea     rcx, [rbp+57h+hObject]
0x180016dc9  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016dce  mov     eax, ebx
0x180016dd0  jmp     short loc_180016E35
0x180016dd2  mov     [rsp+0A0h+dwFlags], esi; int
0x180016dd6  xor     r9d, r9d; cbInput
0x180016dd9  xor     r8d, r8d; pbInput
0x180016ddc  lea     rdx, pszProperty; "SmartCardKeyCertificate"
0x180016de3  mov     rcx, [rbp+57h+hObject]; hObject
0x180016de7  call    cs:__imp_NCryptSetProperty
0x180016ded  mov     rcx, [rbp+5Fh]; this
0x180016df1  test    eax, eax
0x180016df3  jns     short loc_180016E09
0x180016df5  mov     r9d, eax; char *
0x180016df8  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180016dff  mov     edx, 0ACh; void *
0x180016e04  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016e09  mov     byte ptr [rdi], 1
0x180016e0c  lea     rcx, [rbp+57h+var_50]
0x180016e10  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180016e15  nop
0x180016e16  mov     rcx, [rbp+57h+hMem]; hMem
0x180016e1a  mov     [rbp+57h+hMem], rsi
0x180016e1e  test    rcx, rcx
0x180016e21  jz      short loc_180016E2A
0x180016e23  call    cs:__imp_LocalFree
0x180016e29  nop
0x180016e2a  lea     rcx, [rbp+57h+hObject]
0x180016e2e  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016e33  xor     eax, eax
0x180016e35  mov     rcx, [rbp+57h+var_18]
0x180016e39  xor     rcx, rsp; StackCookie
0x180016e3c  call    __security_check_cookie
0x180016e41  mov     rbx, [rsp+0A0h+arg_10]
0x180016e49  add     rsp, 90h
0x180016e50  pop     rdi
0x180016e51  pop     rsi
0x180016e52  pop     rbp
0x180016e53  retn
```
