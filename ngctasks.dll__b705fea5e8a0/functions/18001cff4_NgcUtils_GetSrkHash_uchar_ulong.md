# NgcUtils::GetSrkHash(uchar * *,ulong *)

- ea: `0x18001cff4`
- end: `0x18001d5f8`
- name: `?GetSrkHash@NgcUtils@@YAJPEAPEAEPEAK@Z`
- size: `1540`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800106ac`
- `0x180014490`

## callees

- `0x18000cc14`
- `0x18000cc34`
- `0x180010248`
- `0x180016708`
- `0x180017440`
- `0x18001cfc4`
- `0x18001cff4`
- `0x18001d600`
- `0x18001d624`
- `0x18001d748`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d1b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d250`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d264`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d2a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d2b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d2f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d30c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d3a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d3b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d3cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d48e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d4a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d4b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d4ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d4e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d4fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d511`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d539`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d57b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d58f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d5a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d5cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d1b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d250`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d264`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d2a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d2b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d2f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d30c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d3a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d3b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d3cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d48e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d4a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d4b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d4ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d4e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d4fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d511`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d539`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d57b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d58f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d5a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d5cb`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001d211`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001d364`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001d211`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001d364`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001d02f`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001d0d9`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001d02f`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001d0d9`
- `ncrypt!NCryptImportKey` at `0x18001d134`
- `ncrypt!NCryptImportKey` at `0x18001d134`
- `bcrypt!BCryptHash` at `0x18001d46e`
- `bcrypt!BCryptHash` at `0x18001d46e`

## string_xrefs

- `0x18001d042`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x18001d0b1`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x18001d0ec`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x18001d147`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x18001d194`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x18001d230`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x18001d285`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x18001d2d9`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x18001d383`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x18001d55c`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetSrkHash(NgcUtils *this, unsigned __int8 **a2, unsigned int *a3)
{
  SECURITY_STATUS v5; // eax
  int NCryptBinaryBlob; // ebx
  SECURITY_STATUS v7; // eax
  SECURITY_STATUS v8; // eax
  struct _CERT_PUBLIC_KEY_INFO **v9; // r8
  HLOCAL v10; // rcx
  BOOL v11; // ebx
  const char *v12; // r9
  HLOCAL v13; // rcx
  HLOCAL v14; // rcx
  HLOCAL v15; // rcx
  HLOCAL v16; // rcx
  HLOCAL v17; // rcx
  HLOCAL v18; // rcx
  BOOL v19; // ebx
  const char *v20; // r9
  HLOCAL v21; // rcx
  HLOCAL v22; // rcx
  HLOCAL v23; // rcx
  int *v24; // rbx
  int v25; // ecx
  _QWORD *v26; // rsi
  unsigned int v27; // r10d
  char v28; // r8
  bool v29; // zf
  unsigned __int8 *v30; // rdi
  int v31; // eax
  void *v32; // rdx
  unsigned int v33; // r8d
  HLOCAL v34; // rcx
  HLOCAL v35; // rcx
  HLOCAL v36; // rcx
  HLOCAL v37; // rcx
  HLOCAL v38; // rcx
  HLOCAL v39; // rcx
  PBYTE v40; // rcx
  HLOCAL v42; // rcx
  HLOCAL v43; // rcx
  HLOCAL v44; // rcx
  PBYTE v45; // rcx
  int phKey; // [rsp+20h] [rbp-59h]
  int phKeya; // [rsp+20h] [rbp-59h]
  int phKeyb; // [rsp+20h] [rbp-59h]
  int phKeyc; // [rsp+20h] [rbp-59h]
  int phKeyd; // [rsp+20h] [rbp-59h]
  PBYTE pbData; // [rsp+40h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-31h] BYREF
  HLOCAL v53; // [rsp+50h] [rbp-29h] BYREF
  int v54; // [rsp+58h] [rbp-21h]
  NCRYPT_PROV_HANDLE hProvider; // [rsp+60h] [rbp-19h] BYREF
  NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey; // [rsp+68h] [rbp-11h] BYREF
  HLOCAL v57; // [rsp+70h] [rbp-9h] BYREF
  void **p_pbData; // [rsp+78h] [rbp-1h] BYREF
  PCERT_PUBLIC_KEY_INFO pvStructInfo; // [rsp+80h] [rbp+7h] BYREF
  char v60; // [rsp+88h] [rbp+Fh]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+90h] [rbp+17h] BYREF
  DWORD v62[14]; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  unsigned __int8 *cbData; // [rsp+F0h] [rbp+77h] BYREF
  DWORD pcbStructInfo; // [rsp+F8h] [rbp+7Fh] BYREF

  v54 = 0;
  phProvider = 0;
  v5 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  NCryptBinaryBlob = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x131,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)(unsigned int)v5,
      phKey);
LABEL_75:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    return (unsigned int)NCryptBinaryBlob;
  }
  LODWORD(cbData) = 0;
  pbData = 0;
  p_pbData = (void **)&pbData;
  pvStructInfo = 0;
  v60 = 1;
  v54 = 1;
  NCryptBinaryBlob = NgcUtils::GetNCryptBinaryBlob(
                       phProvider,
                       L"PCP_SRKPUB",
                       (unsigned __int16 *)&pvStructInfo,
                       &cbData);
  v54 = 0;
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_pbData);
  if ( NCryptBinaryBlob < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)(unsigned int)NCryptBinaryBlob,
      phKey);
    goto LABEL_73;
  }
  hProvider = 0;
  v7 = NCryptOpenStorageProvider(&hProvider, L"Microsoft Software Key Storage Provider", 0);
  NCryptBinaryBlob = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)(unsigned int)v7,
      phKey);
LABEL_72:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hProvider);
LABEL_73:
    v45 = pbData;
    v29 = pbData == 0;
    pbData = 0;
    if ( !v29 )
      LocalFree(v45);
    goto LABEL_75;
  }
  hCryptProvOrNCryptKey = 0;
  v8 = NCryptImportKey(hProvider, 0, L"PUBLICBLOB", 0, &hCryptProvOrNCryptKey, pbData, (DWORD)cbData, 0);
  NCryptBinaryBlob = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)(unsigned int)v8,
      phKeya);
LABEL_71:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hCryptProvOrNCryptKey);
    goto LABEL_72;
  }
  hMem = 0;
  p_pbData = &hMem;
  pvStructInfo = 0;
  v60 = 1;
  NCryptBinaryBlob = NgcUtils::ExportPublicKeyInfo(hCryptProvOrNCryptKey, &pvStructInfo, v9);
  wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_pbData);
  if ( NCryptBinaryBlob < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14F,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)(unsigned int)NCryptBinaryBlob,
      phKeya);
    v10 = hMem;
    hMem = 0;
    if ( v10 )
      LocalFree(v10);
    goto LABEL_71;
  }
  pcbStructInfo = 0;
  v53 = 0;
  p_pbData = &v53;
  pvStructInfo = 0;
  v60 = 1;
  v54 = 2;
  v11 = CryptDecodeObjectEx(
          1u,
          (LPCSTR)0x22,
          *((const BYTE **)hMem + 4),
          *((_DWORD *)hMem + 6),
          0x8000u,
          0,
          &pvStructInfo,
          &pcbStructInfo);
  v54 = 0;
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_pbData);
  if ( !v11 )
  {
    NCryptBinaryBlob = wil::details::in1diag3::Return_GetLastError(
                         retaddr,
                         (void *)0x15C,
                         (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
                         v12);
    v13 = v53;
    v53 = 0;
    if ( v13 )
      LocalFree(v13);
    v14 = hMem;
    hMem = 0;
    if ( v14 )
      LocalFree(v14);
    goto LABEL_71;
  }
  if ( !*(_DWORD *)v53 )
  {
    NCryptBinaryBlob = -2147024883;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15F,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)0x8007000DLL,
      phKeyb);
    v15 = v53;
    v53 = 0;
    if ( v15 )
      LocalFree(v15);
    v16 = hMem;
    hMem = 0;
    if ( v16 )
      LocalFree(v16);
    goto LABEL_71;
  }
  if ( !**((_DWORD **)v53 + 1) )
  {
    NCryptBinaryBlob = -2147024883;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)0x8007000DLL,
      phKeyb);
    v17 = v53;
    v53 = 0;
    if ( v17 )
      LocalFree(v17);
    v18 = hMem;
    hMem = 0;
    if ( v18 )
      LocalFree(v18);
    goto LABEL_71;
  }
  v62[0] = 0;
  v57 = 0;
  p_pbData = &v57;
  pvStructInfo = 0;
  v60 = 1;
  v54 = 4;
  v19 = CryptDecodeObjectEx(
          1u,
          (LPCSTR)0x1C,
          *(const BYTE **)(*((_QWORD *)v53 + 1) + 8LL),
          **((_DWORD **)v53 + 1),
          0x8000u,
          0,
          &pvStructInfo,
          v62);
  v54 = 0;
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_pbData);
  if ( !v19 )
  {
    NCryptBinaryBlob = wil::details::in1diag3::Return_GetLastError(
                         retaddr,
                         (void *)0x16C,
                         (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
                         v20);
    v21 = v57;
    v57 = 0;
    if ( v21 )
      LocalFree(v21);
    v22 = v53;
    v53 = 0;
    if ( v22 )
      LocalFree(v22);
    v23 = hMem;
    hMem = 0;
    if ( v23 )
      LocalFree(v23);
    goto LABEL_71;
  }
  v24 = (int *)v57;
  v25 = *(_DWORD *)v57;
  v26 = (char *)v57 + 8;
  if ( (*(_DWORD *)v57 & 0xFFFFFFFE) != 0 )
  {
    v27 = 0;
    do
    {
      v28 = *(_BYTE *)(v27 + *v26);
      *(_BYTE *)(v27 + *v26) = *(_BYTE *)(v25 + ~v27 + *v26);
      *(_BYTE *)(v25 + ~v27++ + *v26) = v28;
      v25 = *v24;
    }
    while ( v27 < (unsigned int)*v24 >> 1 );
  }
  if ( v25 )
  {
    do
    {
      if ( *(_BYTE *)*v26 )
        break;
      ++*v26;
      v29 = (*v24)-- == 1;
    }
    while ( !v29 );
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&cbData, 0x14u);
  v30 = cbData;
  if ( !cbData )
  {
    NCryptBinaryBlob = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x183,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)0x8007000ELL,
      phKeyc);
    v42 = v57;
    v57 = 0;
    if ( v42 )
      LocalFree(v42);
    v43 = v53;
    v53 = 0;
    if ( v43 )
      LocalFree(v43);
    v44 = hMem;
    hMem = 0;
    if ( v44 )
      LocalFree(v44);
    goto LABEL_71;
  }
  phKeyd = *v24;
  v31 = BCryptHash(49, 0, 0, *v26);
  if ( v31 < 0 )
  {
    NCryptBinaryBlob = wil::details::in1diag3::Return_NtStatus(
                         retaddr,
                         v32,
                         v33,
                         (const char *)(unsigned int)v31,
                         phKeyd);
    if ( v30 )
      LocalFree(v30);
    v34 = v57;
    v57 = 0;
    if ( v34 )
      LocalFree(v34);
    v35 = v53;
    v53 = 0;
    if ( v35 )
      LocalFree(v35);
    v36 = hMem;
    hMem = 0;
    if ( v36 )
      LocalFree(v36);
    goto LABEL_71;
  }
  *(_QWORD *)this = v30;
  *(_DWORD *)a2 = 20;
  v37 = v57;
  v57 = 0;
  if ( v37 )
    LocalFree(v37);
  v38 = v53;
  v53 = 0;
  if ( v38 )
    LocalFree(v38);
  v39 = hMem;
  hMem = 0;
  if ( v39 )
    LocalFree(v39);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hCryptProvOrNCryptKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hProvider);
  v40 = pbData;
  pbData = 0;
  if ( v40 )
    LocalFree(v40);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  return 0;
}

```

## disassembly

```asm
0x18001cff4  mov     [rsp-8+arg_0], rbx
0x18001cff9  push    rbp
0x18001cffa  push    rsi
0x18001cffb  push    rdi
0x18001cffc  push    r12
0x18001cffe  push    r13
0x18001d000  push    r14
0x18001d002  push    r15
0x18001d004  lea     rbp, [rsp-27h]
0x18001d009  sub     rsp, 0A0h
0x18001d010  mov     r14, rdx
0x18001d013  mov     r15, rcx
0x18001d016  xor     r12d, r12d
0x18001d019  mov     [rbp+57h+var_78], r12d
0x18001d01d  mov     [rbp+57h+phProvider], r12
0x18001d021  xor     r8d, r8d; dwFlags
0x18001d024  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18001d02b  lea     rcx, [rbp+57h+phProvider]; phProvider
0x18001d02f  call    cs:__imp_NCryptOpenStorageProvider
0x18001d035  mov     ebx, eax
0x18001d037  test    eax, eax
0x18001d039  jns     short loc_18001D058
0x18001d03b  mov     rcx, [rbp+5Fh]; this
0x18001d03f  mov     r9d, eax; char *
0x18001d042  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d049  mov     edx, 131h; void *
0x18001d04e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d053  jmp     loc_18001D5D2
0x18001d058  mov     dword ptr [rbp+57h+arg_10], r12d
0x18001d05c  mov     [rbp+57h+var_90], r12
0x18001d060  lea     rax, [rbp+57h+var_90]
0x18001d064  mov     [rbp+57h+var_58], rax
0x18001d068  mov     [rbp+57h+pvStructInfo], r12
0x18001d06c  mov     r13d, 1
0x18001d072  mov     [rbp+57h+var_48], r13b
0x18001d076  mov     [rbp+57h+var_78], r13d
0x18001d07a  lea     r9, [rbp+57h+arg_10]; unsigned __int8 **
0x18001d07e  lea     r8, [rbp+57h+pvStructInfo]; unsigned __int16 *
0x18001d082  lea     rdx, aPcpSrkpub; "PCP_SRKPUB"
0x18001d089  mov     rcx, [rbp+57h+phProvider]; hObject
0x18001d08d  call    ?GetNCryptBinaryBlob@NgcUtils@@YAJ_KPEBGPEAPEAEPEAK@Z; NgcUtils::GetNCryptBinaryBlob(unsigned __int64,ushort const *,uchar * *,ulong *)
0x18001d092  mov     ebx, eax
0x18001d094  mov     edi, r13d
0x18001d097  and     edi, 0FFFFFFFEh
0x18001d09a  mov     [rbp+57h+var_78], edi
0x18001d09d  lea     rcx, [rbp+57h+var_58]
0x18001d0a1  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001d0a6  test    ebx, ebx
0x18001d0a8  jns     short loc_18001D0C7
0x18001d0aa  mov     rcx, [rbp+5Fh]; this
0x18001d0ae  mov     r9d, ebx; char *
0x18001d0b1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d0b8  mov     edx, 139h; void *
0x18001d0bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d0c2  jmp     loc_18001D5BE
0x18001d0c7  mov     [rbp+57h+hProvider], r12
0x18001d0cb  xor     r8d, r8d; dwFlags
0x18001d0ce  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x18001d0d5  lea     rcx, [rbp+57h+hProvider]; phProvider
0x18001d0d9  call    cs:__imp_NCryptOpenStorageProvider
0x18001d0df  mov     ebx, eax
0x18001d0e1  test    eax, eax
0x18001d0e3  jns     short loc_18001D102
0x18001d0e5  mov     rcx, [rbp+5Fh]; this
0x18001d0e9  mov     r9d, eax; char *
0x18001d0ec  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d0f3  mov     edx, 13Fh; void *
0x18001d0f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d0fd  jmp     loc_18001D5B4
0x18001d102  mov     eax, dword ptr [rbp+57h+arg_10]
0x18001d105  mov     rdx, [rbp+57h+var_90]
0x18001d109  mov     [rbp+57h+hCryptProvOrNCryptKey], r12
0x18001d10d  mov     [rsp+0D0h+dwFlags], r12d; dwFlags
0x18001d112  mov     [rsp+0D0h+cbData], eax; cbData
0x18001d116  mov     [rsp+0D0h+pbData], rdx; pbData
0x18001d11b  lea     rax, [rbp+57h+hCryptProvOrNCryptKey]
0x18001d11f  mov     [rsp+0D0h+phKey], rax; int
0x18001d124  xor     r9d, r9d; pParameterList
0x18001d127  lea     r8, pszBlobType; "PUBLICBLOB"
0x18001d12e  xor     edx, edx; hImportKey
0x18001d130  mov     rcx, [rbp+57h+hProvider]; hProvider
0x18001d134  call    cs:__imp_NCryptImportKey
0x18001d13a  mov     ebx, eax
0x18001d13c  test    eax, eax
0x18001d13e  jns     short loc_18001D15D
0x18001d140  mov     rcx, [rbp+5Fh]; this
0x18001d144  mov     r9d, eax; char *
0x18001d147  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d14e  mov     edx, 14Ah; void *
0x18001d153  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d158  jmp     loc_18001D5AA
0x18001d15d  mov     [rbp+57h+hMem], r12
0x18001d161  lea     rax, [rbp+57h+hMem]
0x18001d165  mov     [rbp+57h+var_58], rax
0x18001d169  mov     [rbp+57h+pvStructInfo], r12
0x18001d16d  mov     [rbp+57h+var_48], r13b
0x18001d171  lea     rdx, [rbp+57h+pvStructInfo]; unsigned __int64
0x18001d175  mov     rcx, [rbp+57h+hCryptProvOrNCryptKey]; hCryptProvOrNCryptKey
0x18001d179  call    ?ExportPublicKeyInfo@NgcUtils@@YAJ_KPEAPEAU_CERT_PUBLIC_KEY_INFO@@@Z; NgcUtils::ExportPublicKeyInfo(unsigned __int64,_CERT_PUBLIC_KEY_INFO * *)
0x18001d17e  mov     ebx, eax
0x18001d180  lea     rcx, [rbp+57h+var_58]
0x18001d184  call    ??1?$out_param_t@V?$unique_ptr@U_CERT_PUBLIC_KEY_INFO@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001d189  test    ebx, ebx
0x18001d18b  jns     short loc_18001D1BF
0x18001d18d  mov     rcx, [rbp+5Fh]; this
0x18001d191  mov     r9d, ebx; char *
0x18001d194  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d19b  mov     edx, 14Fh; void *
0x18001d1a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d1a5  nop
0x18001d1a6  mov     rcx, [rbp+57h+hMem]; hMem
0x18001d1aa  mov     [rbp+57h+hMem], r12
0x18001d1ae  test    rcx, rcx
0x18001d1b1  jz      short loc_18001D1BA
0x18001d1b3  call    cs:__imp_LocalFree
0x18001d1b9  nop
0x18001d1ba  jmp     loc_18001D5AA
0x18001d1bf  mov     [rbp+57h+pcbStructInfo], r12d
0x18001d1c3  mov     [rbp+57h+var_80], r12
0x18001d1c7  lea     rax, [rbp+57h+var_80]
0x18001d1cb  mov     [rbp+57h+var_58], rax
0x18001d1cf  mov     [rbp+57h+pvStructInfo], r12
0x18001d1d3  mov     [rbp+57h+var_48], r13b
0x18001d1d7  or      edi, 2
0x18001d1da  mov     [rbp+57h+var_78], edi
0x18001d1dd  lea     rax, [rbp+57h+pcbStructInfo]
0x18001d1e1  mov     qword ptr [rsp+0D0h+dwFlags], rax; pcbStructInfo
0x18001d1e6  lea     rax, [rbp+57h+pvStructInfo]
0x18001d1ea  mov     qword ptr [rsp+0D0h+cbData], rax; pvStructInfo
0x18001d1ef  mov     [rsp+0D0h+pbData], r12; pDecodePara
0x18001d1f4  mov     esi, 8000h
0x18001d1f9  mov     dword ptr [rsp+0D0h+phKey], esi; int
0x18001d1fd  mov     r8, [rbp+57h+hMem]
0x18001d201  mov     r9d, [r8+18h]; cbEncoded
0x18001d205  mov     r8, [r8+20h]; pbEncoded
0x18001d209  mov     edx, 22h ; '"'; lpszStructType
0x18001d20e  mov     ecx, r13d; dwCertEncodingType
0x18001d211  call    cs:__imp_CryptDecodeObjectEx
0x18001d217  mov     ebx, eax
0x18001d219  and     edi, 0FFFFFFFDh
0x18001d21c  mov     [rbp+57h+var_78], edi
0x18001d21f  lea     rcx, [rbp+57h+var_58]
0x18001d223  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001d228  test    ebx, ebx
0x18001d22a  jnz     short loc_18001D270
0x18001d22c  mov     rcx, [rbp+5Fh]; this
0x18001d230  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d237  mov     edx, 15Ch; void *
0x18001d23c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d241  mov     ebx, eax
0x18001d243  mov     rcx, [rbp+57h+var_80]; hMem
0x18001d247  mov     [rbp+57h+var_80], r12
0x18001d24b  test    rcx, rcx
0x18001d24e  jz      short loc_18001D257
0x18001d250  call    cs:__imp_LocalFree
0x18001d256  nop
0x18001d257  mov     rcx, [rbp+57h+hMem]; hMem
0x18001d25b  mov     [rbp+57h+hMem], r12
0x18001d25f  test    rcx, rcx
0x18001d262  jz      short loc_18001D26B
0x18001d264  call    cs:__imp_LocalFree
0x18001d26a  nop
0x18001d26b  jmp     loc_18001D5AA
0x18001d270  mov     r8, [rbp+57h+var_80]
0x18001d274  cmp     [r8], r13d
0x18001d277  jnb     short loc_18001D2C4
0x18001d279  mov     rcx, [rbp+5Fh]; this
0x18001d27d  mov     ebx, 8007000Dh
0x18001d282  mov     r9d, ebx; char *
0x18001d285  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d28c  mov     edx, 15Fh; void *
0x18001d291  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d296  nop
0x18001d297  mov     rcx, [rbp+57h+var_80]; hMem
0x18001d29b  mov     [rbp+57h+var_80], r12
0x18001d29f  test    rcx, rcx
0x18001d2a2  jz      short loc_18001D2AB
0x18001d2a4  call    cs:__imp_LocalFree
0x18001d2aa  nop
0x18001d2ab  mov     rcx, [rbp+57h+hMem]; hMem
0x18001d2af  mov     [rbp+57h+hMem], r12
0x18001d2b3  test    rcx, rcx
0x18001d2b6  jz      short loc_18001D2BF
0x18001d2b8  call    cs:__imp_LocalFree
0x18001d2be  nop
0x18001d2bf  jmp     loc_18001D5AA
0x18001d2c4  mov     rax, [r8+8]
0x18001d2c8  cmp     [rax], r12d
0x18001d2cb  jnz     short loc_18001D318
0x18001d2cd  mov     rcx, [rbp+5Fh]; this
0x18001d2d1  mov     ebx, 8007000Dh
0x18001d2d6  mov     r9d, ebx; char *
0x18001d2d9  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d2e0  mov     edx, 160h; void *
0x18001d2e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d2ea  nop
0x18001d2eb  mov     rcx, [rbp+57h+var_80]; hMem
0x18001d2ef  mov     [rbp+57h+var_80], r12
0x18001d2f3  test    rcx, rcx
0x18001d2f6  jz      short loc_18001D2FF
0x18001d2f8  call    cs:__imp_LocalFree
0x18001d2fe  nop
0x18001d2ff  mov     rcx, [rbp+57h+hMem]; hMem
0x18001d303  mov     [rbp+57h+hMem], r12
0x18001d307  test    rcx, rcx
0x18001d30a  jz      short loc_18001D313
0x18001d30c  call    cs:__imp_LocalFree
0x18001d312  nop
0x18001d313  jmp     loc_18001D5AA
0x18001d318  mov     [rbp+57h+var_38], r12d
0x18001d31c  mov     [rbp+57h+var_60], r12
0x18001d320  lea     rax, [rbp+57h+var_60]
0x18001d324  mov     [rbp+57h+var_58], rax
0x18001d328  mov     [rbp+57h+pvStructInfo], r12
0x18001d32c  mov     [rbp+57h+var_48], r13b
0x18001d330  or      edi, 4
0x18001d333  mov     [rbp+57h+var_78], edi
0x18001d336  mov     r8, [r8+8]
0x18001d33a  lea     rax, [rbp+57h+var_38]
0x18001d33e  mov     qword ptr [rsp+0D0h+dwFlags], rax; pcbStructInfo
0x18001d343  lea     rax, [rbp+57h+pvStructInfo]
0x18001d347  mov     qword ptr [rsp+0D0h+cbData], rax; pvStructInfo
0x18001d34c  mov     [rsp+0D0h+pbData], r12; pDecodePara
0x18001d351  mov     dword ptr [rsp+0D0h+phKey], esi; int
0x18001d355  mov     r9d, [r8]; cbEncoded
0x18001d358  mov     r8, [r8+8]; pbEncoded
0x18001d35c  mov     edx, 1Ch; lpszStructType
0x18001d361  mov     ecx, r13d; dwCertEncodingType
0x18001d364  call    cs:__imp_CryptDecodeObjectEx
0x18001d36a  mov     ebx, eax
0x18001d36c  and     edi, 0FFFFFFFBh
0x18001d36f  mov     [rbp+57h+var_78], edi
0x18001d372  lea     rcx, [rbp+57h+var_58]
0x18001d376  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001d37b  test    ebx, ebx
0x18001d37d  jnz     short loc_18001D3D7
0x18001d37f  mov     rcx, [rbp+5Fh]; this
0x18001d383  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d38a  mov     edx, 16Ch; void *
0x18001d38f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d394  mov     ebx, eax
0x18001d396  mov     rcx, [rbp+57h+var_60]; hMem
0x18001d39a  mov     [rbp+57h+var_60], r12
0x18001d39e  test    rcx, rcx
0x18001d3a1  jz      short loc_18001D3AA
0x18001d3a3  call    cs:__imp_LocalFree
0x18001d3a9  nop
0x18001d3aa  mov     rcx, [rbp+57h+var_80]; hMem
0x18001d3ae  mov     [rbp+57h+var_80], r12
0x18001d3b2  test    rcx, rcx
0x18001d3b5  jz      short loc_18001D3BE
0x18001d3b7  call    cs:__imp_LocalFree
0x18001d3bd  nop
0x18001d3be  mov     rcx, [rbp+57h+hMem]; hMem
0x18001d3c2  mov     [rbp+57h+hMem], r12
0x18001d3c6  test    rcx, rcx
0x18001d3c9  jz      short loc_18001D3D2
0x18001d3cb  call    cs:__imp_LocalFree
0x18001d3d1  nop
0x18001d3d2  jmp     loc_18001D5AA
0x18001d3d7  mov     rbx, [rbp+57h+var_60]
0x18001d3db  mov     ecx, [rbx]
0x18001d3dd  lea     rsi, [rbx+8]
0x18001d3e1  test    ecx, 0FFFFFFFEh
0x18001d3e7  jbe     short loc_18001D41C
0x18001d3e9  mov     r10d, r12d
0x18001d3ec  mov     r9, [rsi]
0x18001d3ef  mov     edx, r10d
0x18001d3f2  mov     r8b, [rdx+r9]
0x18001d3f6  mov     eax, r10d
0x18001d3f9  not     eax
0x18001d3fb  add     eax, ecx
0x18001d3fd  mov     ecx, eax
0x18001d3ff  mov     al, [rax+r9]
0x18001d403  mov     [rdx+r9], al
0x18001d407  mov     rax, [rsi]
0x18001d40a  mov     [rcx+rax], r8b
0x18001d40e  add     r10d, r13d
0x18001d411  mov     ecx, [rbx]
0x18001d413  mov     eax, ecx
0x18001d415  shr     eax, 1
0x18001d417  cmp     r10d, eax
0x18001d41a  jb      short loc_18001D3EC
0x18001d41c  test    ecx, ecx
0x18001d41e  jz      short loc_18001D433
0x18001d420  mov     rax, [rsi]
0x18001d423  cmp     [rax], r12b
0x18001d426  jnz     short loc_18001D433
0x18001d428  inc     rax
0x18001d42b  mov     [rsi], rax
0x18001d42e  add     dword ptr [rbx], 0FFFFFFFFh
0x18001d431  jnz     short loc_18001D420
0x18001d433  mov     r13d, 14h
0x18001d439  mov     edx, r13d
0x18001d43c  lea     rcx, [rbp+57h+arg_10]
0x18001d440  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18001d445  nop
0x18001d446  mov     rdi, [rbp+57h+arg_10]
0x18001d44a  test    rdi, rdi
0x18001d44d  jz      loc_18001D550
  ... truncated ...
```
