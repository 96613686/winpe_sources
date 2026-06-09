# GetSoftwareTokenBindingAikBlob(_NGC_TB_AIK_KEY_TYPE,ushort const *,ushort const *,ushort const *,uchar * *,ulong *)

- ea: `0x180016328`
- end: `0x18001670f`
- name: `?GetSoftwareTokenBindingAikBlob@@YAJW4_NGC_TB_AIK_KEY_TYPE@@PEBG11PEAPEAEPEAK@Z`
- size: `999`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, __int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f464`

## callees

- `0x18000749c`
- `0x180007dc4`
- `0x18000b0fc`
- `0x18000dad8`
- `0x18000db5c`
- `0x18001070c`
- `0x180010730`
- `0x180011e48`
- `0x180013e3c`
- `0x180014918`
- `0x180016328`
- `0x1800169e0`

## import_xrefs

- `ncrypt!NCryptFinalizeKey` at `0x1800165da`
- `ncrypt!NCryptFinalizeKey` at `0x1800165da`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800164d8`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800164d8`
- `ncrypt!NCryptFreeObject` at `0x1800163bc`
- `ncrypt!NCryptFreeObject` at `0x18001643d`
- `ncrypt!NCryptFreeObject` at `0x180016490`
- `ncrypt!NCryptFreeObject` at `0x1800163bc`
- `ncrypt!NCryptFreeObject` at `0x18001643d`
- `ncrypt!NCryptFreeObject` at `0x180016490`
- `ncrypt!NCryptOpenKey` at `0x18001646d`
- `ncrypt!NCryptOpenKey` at `0x18001646d`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800163e2`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800163e2`

## string_xrefs

- `0x18001637c`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x1800163f5`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x1800164eb`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180016547`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x18001659f`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x1800165ed`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x18001667b`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`

## pseudocode

```c
__int64 __fastcall GetSoftwareTokenBindingAikBlob(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _DWORD *a6)
{
  int TokenBindingAikNameInternal; // eax
  unsigned int v11; // ebx
  SECURITY_STATUS v13; // eax
  NCRYPT_HANDLE v14; // rbx
  DWORD v15; // eax
  SECURITY_STATUS v16; // eax
  unsigned int v17; // r9d
  int v18; // eax
  int v19; // eax
  SECURITY_STATUS v20; // eax
  __int64 v21; // rcx
  int dwFlags; // [rsp+20h] [rbp-50h]
  int dwFlagsa; // [rsp+20h] [rbp-50h]
  unsigned int *v24; // [rsp+28h] [rbp-48h]
  unsigned __int8 *v25; // [rsp+30h] [rbp-40h] BYREF
  NCRYPT_HANDLE phKey; // [rsp+38h] [rbp-38h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR pszKeyName; // [rsp+48h] [rbp-28h] BYREF
  __int64 v29; // [rsp+50h] [rbp-20h] BYREF
  __int64 *v30; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v31[2]; // [rsp+60h] [rbp-10h] BYREF
  char v32; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  pszKeyName = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszKeyName,
    0);
  TokenBindingAikNameInternal = GetTokenBindingAikNameInternal(a1, a2, a3, a4);
  v11 = TokenBindingAikNameInternal;
  if ( TokenBindingAikNameInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)TokenBindingAikNameInternal,
      (int)&pszKeyName);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
    return v11;
  }
  hObject = 0;
  v13 = NCryptOpenStorageProvider(&hObject, L"Microsoft Software Key Storage Provider", 0);
  v11 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x236,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)v13,
      (int)&pszKeyName);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
    return v11;
  }
  phKey = 0;
  if ( NCryptOpenKey(hObject, &phKey, pszKeyName, 0, 0x40u) < 0 )
  {
    v14 = phKey;
    if ( phKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v25);
      NCryptFreeObject(v14);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v25);
    }
    phKey = 0;
    v15 = 131200;
    if ( a1 != 2 )
      v15 = 128;
    v16 = NCryptCreatePersistedKey(hObject, &phKey, L"RSA", pszKeyName, 0, v15);
    v11 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x249,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
        (const char *)(unsigned int)v16,
        dwFlags);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
      return v11;
    }
    if ( a1 == 2 )
    {
      v18 = NgcUtils::SetNCryptDwordProperty(
              (NgcUtils *)phKey,
              (unsigned __int64)L"Key Usage",
              (const unsigned __int16 *)0x10,
              v17);
      v11 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x252,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
          (const char *)(unsigned int)v18,
          dwFlags);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
        return v11;
      }
    }
    v19 = NgcUtils::SetNCryptDwordProperty(
            (NgcUtils *)phKey,
            (unsigned __int64)L"Length",
            (const unsigned __int16 *)0x800,
            v17);
    v11 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x259,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
        (const char *)(unsigned int)v19,
        dwFlags);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
      return v11;
    }
    v20 = NCryptFinalizeKey(phKey, 0x40u);
    v11 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25D,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
        (const char *)(unsigned int)v20,
        dwFlags);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
      return v11;
    }
  }
  LODWORD(v25) = 0;
  v29 = 0;
  v30 = &v29;
  *(_QWORD *)v31 = 0;
  v32 = 1;
  v11 = NgcUtils::ExportNCryptKey(phKey, L"PUBLICBLOB", 0, (unsigned int)v31, &v25, v24);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v30);
  if ( (v11 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x268,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)v11,
      dwFlagsa);
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v29, 0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
    return v11;
  }
  v21 = v29;
  v29 = 0;
  *a5 = v21;
  *a6 = (_DWORD)v25;
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v29, 0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
  return 0;
}

```

## disassembly

```asm
0x180016328  push    rbp
0x18001632a  push    rbx
0x18001632b  push    rsi
0x18001632c  push    rdi
0x18001632d  push    r14
0x18001632f  mov     rbp, rsp
0x180016332  sub     rsp, 70h
0x180016336  mov     rbx, r9
0x180016339  mov     rdi, r8
0x18001633c  mov     rsi, rdx
0x18001633f  mov     r14d, ecx
0x180016342  mov     [rbp+pszKeyName], 0
0x18001634a  xor     edx, edx
0x18001634c  lea     rcx, [rbp+pszKeyName]
0x180016350  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180016355  lea     rax, [rbp+pszKeyName]
0x180016359  mov     qword ptr [rsp+70h+dwFlags], rax; int
0x18001635e  mov     r9, rbx
0x180016361  mov     r8, rdi
0x180016364  mov     rdx, rsi
0x180016367  mov     ecx, r14d
0x18001636a  call    ?GetTokenBindingAikNameInternal@@YAJW4_NGC_TB_AIK_KEY_TYPE@@PEBG11PEAPEAG@Z; GetTokenBindingAikNameInternal(_NGC_TB_AIK_KEY_TYPE,ushort const *,ushort const *,ushort const *,ushort * *)
0x18001636f  mov     ebx, eax
0x180016371  test    eax, eax
0x180016373  jns     short loc_18001639F
0x180016375  mov     rcx, [rbp+28h]; this
0x180016379  mov     r9d, eax; char *
0x18001637c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016383  mov     edx, 22Fh; void *
0x180016388  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001638d  nop
0x18001638e  lea     rcx, [rbp+pszKeyName]
0x180016392  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016397  nop
0x180016398  mov     eax, ebx
0x18001639a  jmp     loc_180016704
0x18001639f  mov     [rbp+hObject], 0
0x1800163a7  mov     rbx, [rbp+hObject]
0x1800163ab  test    rbx, rbx
0x1800163ae  jz      short loc_1800163CC
0x1800163b0  lea     rcx, [rbp+var_40]; this
0x1800163b4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800163b9  mov     rcx, rbx; hObject
0x1800163bc  call    cs:__imp_NCryptFreeObject
0x1800163c2  lea     rcx, [rbp+var_40]; this
0x1800163c6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800163cb  nop
0x1800163cc  mov     [rbp+hObject], 0
0x1800163d4  xor     r8d, r8d; dwFlags
0x1800163d7  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x1800163de  lea     rcx, [rbp+hObject]; phProvider
0x1800163e2  call    cs:__imp_NCryptOpenStorageProvider
0x1800163e8  mov     ebx, eax
0x1800163ea  test    eax, eax
0x1800163ec  jns     short loc_180016420
0x1800163ee  mov     rcx, [rbp+28h]; this
0x1800163f2  mov     r9d, eax; char *
0x1800163f5  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800163fc  mov     edx, 236h; void *
0x180016401  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016406  nop
0x180016407  lea     rcx, [rbp+hObject]
0x18001640b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016410  nop
0x180016411  lea     rcx, [rbp+pszKeyName]
0x180016415  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001641a  nop
0x18001641b  jmp     loc_180016398
0x180016420  mov     [rbp+phKey], 0
0x180016428  mov     rbx, [rbp+phKey]
0x18001642c  test    rbx, rbx
0x18001642f  jz      short loc_18001644D
0x180016431  lea     rcx, [rbp+var_40]; this
0x180016435  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001643a  mov     rcx, rbx; hObject
0x18001643d  call    cs:__imp_NCryptFreeObject
0x180016443  lea     rcx, [rbp+var_40]; this
0x180016447  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001644c  nop
0x18001644d  mov     [rbp+phKey], 0
0x180016455  mov     edi, 40h ; '@'
0x18001645a  mov     [rsp+70h+dwFlags], edi; dwFlags
0x18001645e  xor     r9d, r9d; dwLegacyKeySpec
0x180016461  mov     r8, [rbp+pszKeyName]; pszKeyName
0x180016465  lea     rdx, [rbp+phKey]; phKey
0x180016469  mov     rcx, [rbp+hObject]; hProvider
0x18001646d  call    cs:__imp_NCryptOpenKey
0x180016473  test    eax, eax
0x180016475  jns     loc_180016622
0x18001647b  mov     rbx, [rbp+phKey]
0x18001647f  test    rbx, rbx
0x180016482  jz      short loc_1800164A0
0x180016484  lea     rcx, [rbp+var_40]; this
0x180016488  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001648d  mov     rcx, rbx; hObject
0x180016490  call    cs:__imp_NCryptFreeObject
0x180016496  lea     rcx, [rbp+var_40]; this
0x18001649a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001649f  nop
0x1800164a0  mov     [rbp+phKey], 0
0x1800164a8  mov     eax, 20080h
0x1800164ad  mov     ecx, 80h
0x1800164b2  cmp     r14d, 2
0x1800164b6  cmovnz  eax, ecx
0x1800164b9  mov     dword ptr [rsp+70h+var_48], eax; dwFlags
0x1800164bd  mov     [rsp+70h+dwFlags], 0; int
0x1800164c5  mov     r9, [rbp+pszKeyName]; pszKeyName
0x1800164c9  lea     r8, pszAlgId; "RSA"
0x1800164d0  lea     rdx, [rbp+phKey]; phKey
0x1800164d4  mov     rcx, [rbp+hObject]; hProvider
0x1800164d8  call    cs:__imp_NCryptCreatePersistedKey
0x1800164de  mov     ebx, eax
0x1800164e0  test    eax, eax
0x1800164e2  jns     short loc_180016520
0x1800164e4  mov     rcx, [rbp+28h]; this
0x1800164e8  mov     r9d, eax; char *
0x1800164eb  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800164f2  mov     edx, 249h; void *
0x1800164f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800164fc  nop
0x1800164fd  lea     rcx, [rbp+phKey]
0x180016501  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016506  nop
0x180016507  lea     rcx, [rbp+hObject]
0x18001650b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016510  nop
0x180016511  lea     rcx, [rbp+pszKeyName]
0x180016515  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001651a  nop
0x18001651b  jmp     loc_180016398
0x180016520  cmp     r14d, 2
0x180016524  jnz     short loc_18001657C
0x180016526  lea     r8d, [r14+0Eh]; unsigned __int16 *
0x18001652a  lea     rdx, aKeyUsage; "Key Usage"
0x180016531  mov     rcx, [rbp+phKey]; this
0x180016535  call    ?SetNCryptDwordProperty@NgcUtils@@YAJ_KPEBGK@Z; NgcUtils::SetNCryptDwordProperty(unsigned __int64,ushort const *,ulong)
0x18001653a  mov     ebx, eax
0x18001653c  test    eax, eax
0x18001653e  jns     short loc_18001657C
0x180016540  mov     rcx, [rbp+28h]; this
0x180016544  mov     r9d, eax; char *
0x180016547  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001654e  mov     edx, 252h; void *
0x180016553  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016558  nop
0x180016559  lea     rcx, [rbp+phKey]
0x18001655d  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016562  nop
0x180016563  lea     rcx, [rbp+hObject]
0x180016567  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001656c  nop
0x18001656d  lea     rcx, [rbp+pszKeyName]
0x180016571  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016576  nop
0x180016577  jmp     loc_180016398
0x18001657c  mov     r8d, 800h; unsigned __int16 *
0x180016582  lea     rdx, aLength; "Length"
0x180016589  mov     rcx, [rbp+phKey]; this
0x18001658d  call    ?SetNCryptDwordProperty@NgcUtils@@YAJ_KPEBGK@Z; NgcUtils::SetNCryptDwordProperty(unsigned __int64,ushort const *,ulong)
0x180016592  mov     ebx, eax
0x180016594  test    eax, eax
0x180016596  jns     short loc_1800165D4
0x180016598  mov     rcx, [rbp+28h]; this
0x18001659c  mov     r9d, eax; char *
0x18001659f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800165a6  mov     edx, 259h; void *
0x1800165ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800165b0  nop
0x1800165b1  lea     rcx, [rbp+phKey]
0x1800165b5  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800165ba  nop
0x1800165bb  lea     rcx, [rbp+hObject]
0x1800165bf  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800165c4  nop
0x1800165c5  lea     rcx, [rbp+pszKeyName]
0x1800165c9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800165ce  nop
0x1800165cf  jmp     loc_180016398
0x1800165d4  mov     edx, edi; dwFlags
0x1800165d6  mov     rcx, [rbp+phKey]; hKey
0x1800165da  call    cs:__imp_NCryptFinalizeKey
0x1800165e0  mov     ebx, eax
0x1800165e2  test    eax, eax
0x1800165e4  jns     short loc_180016622
0x1800165e6  mov     rcx, [rbp+28h]; this
0x1800165ea  mov     r9d, eax; char *
0x1800165ed  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800165f4  mov     edx, 25Dh; void *
0x1800165f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800165fe  nop
0x1800165ff  lea     rcx, [rbp+phKey]
0x180016603  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016608  nop
0x180016609  lea     rcx, [rbp+hObject]
0x18001660d  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016612  nop
0x180016613  lea     rcx, [rbp+pszKeyName]
0x180016617  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001661c  nop
0x18001661d  jmp     loc_180016398
0x180016622  mov     dword ptr [rbp+var_40], 0
0x180016629  mov     [rbp+var_20], 0
0x180016631  lea     rax, [rbp+var_20]
0x180016635  mov     [rbp+var_18], rax
0x180016639  mov     qword ptr [rbp+var_10], 0
0x180016641  mov     [rbp+var_8], 1
0x180016645  lea     rax, [rbp+var_40]
0x180016649  mov     qword ptr [rsp+70h+dwFlags], rax; int
0x18001664e  lea     r9, [rbp+var_10]; unsigned int
0x180016652  xor     r8d, r8d; dwFlags
0x180016655  lea     rdx, aPublicblob; "PUBLICBLOB"
0x18001665c  mov     rcx, [rbp+phKey]; hKey
0x180016660  call    ?ExportNCryptKey@NgcUtils@@YAJ_KPEBGKPEAPEAEPEAK@Z; NgcUtils::ExportNCryptKey(unsigned __int64,ushort const *,ulong,uchar * *,ulong *)
0x180016665  mov     ebx, eax
0x180016667  lea     rcx, [rbp+var_18]
0x18001666b  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180016670  test    ebx, ebx
0x180016672  jns     short loc_1800166BC
0x180016674  mov     rcx, [rbp+28h]; this
0x180016678  mov     r9d, ebx; char *
0x18001667b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016682  mov     edx, 268h; void *
0x180016687  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001668c  nop
0x18001668d  xor     edx, edx
0x18001668f  lea     rcx, [rbp+var_20]
0x180016693  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180016698  nop
0x180016699  lea     rcx, [rbp+phKey]
0x18001669d  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800166a2  nop
0x1800166a3  lea     rcx, [rbp+hObject]
0x1800166a7  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800166ac  nop
0x1800166ad  lea     rcx, [rbp+pszKeyName]
0x1800166b1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800166b6  nop
0x1800166b7  jmp     loc_180016398
0x1800166bc  mov     rcx, [rbp+var_20]
0x1800166c0  mov     [rbp+var_20], 0
0x1800166c8  mov     rax, [rbp+arg_20]
0x1800166cc  mov     [rax], rcx
0x1800166cf  mov     rcx, [rbp+arg_28]
0x1800166d3  mov     eax, dword ptr [rbp+var_40]
0x1800166d6  mov     [rcx], eax
0x1800166d8  xor     edx, edx
0x1800166da  lea     rcx, [rbp+var_20]
0x1800166de  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x1800166e3  nop
0x1800166e4  lea     rcx, [rbp+phKey]
0x1800166e8  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800166ed  nop
0x1800166ee  lea     rcx, [rbp+hObject]
0x1800166f2  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800166f7  nop
0x1800166f8  lea     rcx, [rbp+pszKeyName]
0x1800166fc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016701  nop
0x180016702  xor     eax, eax
0x180016704  add     rsp, 70h
0x180016708  pop     r14
0x18001670a  pop     rdi
0x18001670b  pop     rsi
0x18001670c  pop     rbx
0x18001670d  pop     rbp
0x18001670e  retn
```
