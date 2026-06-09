# GetTokenBindingAikName(_NGC_TB_AIK_KEY_TYPE,ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180016718`
- end: `0x1800169d7`
- name: `?GetTokenBindingAikName@@YAJW4_NGC_TB_AIK_KEY_TYPE@@PEBG11PEAPEAG@Z`
- size: `703`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, LPCWSTR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ff24`

## callees

- `0x18000749c`
- `0x180007dc4`
- `0x18000b0fc`
- `0x18000db5c`
- `0x180010730`
- `0x180011e48`
- `0x180015bf0`
- `0x180016718`
- `0x1800169e0`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x180016896`
- `ncrypt!NCryptFreeObject` at `0x18001691b`
- `ncrypt!NCryptFreeObject` at `0x180016896`
- `ncrypt!NCryptFreeObject` at `0x18001691b`
- `ncrypt!NCryptOpenKey` at `0x180016949`
- `ncrypt!NCryptOpenKey` at `0x180016949`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800168bc`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800168bc`

## string_xrefs

- `0x1800167bd`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180016807`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180016856`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x1800168cf`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x18001695c`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetTokenBindingAikName(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        LPCWSTR *a5)
{
  __int64 v9; // r9
  int Aik; // eax
  unsigned int v11; // ebx
  LPCWSTR v12; // rbx
  int TokenBindingAikNameInternal; // eax
  SECURITY_STATUS v15; // eax
  SECURITY_STATUS v16; // eax
  unsigned int v17; // edi
  int dwFlags; // [rsp+20h] [rbp-60h]
  int dwFlagsa; // [rsp+20h] [rbp-60h]
  int dwFlagsb; // [rsp+20h] [rbp-60h]
  LPCWSTR pszKeyName; // [rsp+40h] [rbp-40h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+48h] [rbp-38h] BYREF
  NCRYPT_HANDLE phKey; // [rsp+50h] [rbp-30h] BYREF
  int v24[2]; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v25[3]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  pszKeyName = 0;
  if ( (a1 & 0xFFFFFFFD) != 0 )
  {
    if ( a1 != 1 )
    {
      v11 = -2146893785;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32E,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
        (const char *)0x80090027LL,
        dwFlags);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
      return v11;
    }
    *(_QWORD *)v24 = 0;
    v25[2] = 0;
    v25[0] = a2;
    v25[1] = a3;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszKeyName,
      0);
    *(_QWORD *)v24 = 0;
    LOBYTE(v9) = a1;
    Aik = GetAik((unsigned int)(a1 + 4), v25, a4, v9);
    v11 = Aik;
    if ( Aik < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32A,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
        (const char *)(unsigned int)Aik,
        (int)v24);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(v24);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
      return v11;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(v24);
    v12 = pszKeyName;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszKeyName,
      0);
    TokenBindingAikNameInternal = GetTokenBindingAikNameInternal(a1, a2, a3, a4, (unsigned __int16 **)&pszKeyName);
    v11 = TokenBindingAikNameInternal;
    if ( TokenBindingAikNameInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x306,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
        (const char *)(unsigned int)TokenBindingAikNameInternal,
        dwFlagsa);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
      return v11;
    }
    hObject = 0;
    v15 = NCryptOpenStorageProvider(&hObject, L"Microsoft Software Key Storage Provider", 0);
    v11 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30D,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
        (const char *)(unsigned int)v15,
        dwFlagsa);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
      return v11;
    }
    v12 = pszKeyName;
    phKey = 0;
    v16 = NCryptOpenKey(hObject, &phKey, pszKeyName, 0, 0x40u);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x316,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
        (const char *)(unsigned int)v16,
        dwFlagsb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
      return v17;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  }
  pszKeyName = 0;
  *a5 = v12;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
  return 0;
}

```

## disassembly

```asm
0x180016718  mov     [rsp-18h+arg_8], rbx
0x18001671d  mov     [rsp-18h+arg_10], rsi
0x180016722  push    rbp
0x180016723  push    rdi
0x180016724  push    r14
0x180016726  mov     rbp, rsp
0x180016729  sub     rsp, 80h
0x180016730  mov     rdi, r9
0x180016733  mov     rsi, r8
0x180016736  mov     r14, rdx
0x180016739  mov     ebx, ecx
0x18001673b  mov     [rbp+pszKeyName], 0
0x180016743  test    ecx, 0FFFFFFFDh
0x180016749  jz      loc_180016825
0x18001674f  cmp     ecx, 1
0x180016752  jnz     loc_1800167FB
0x180016758  mov     qword ptr [rbp+var_28], 0
0x180016760  mov     [rbp+var_8], 0
0x180016768  mov     [rbp+var_18], rdx
0x18001676c  mov     [rbp+var_10], r8
0x180016770  xor     edx, edx
0x180016772  lea     rcx, [rbp+pszKeyName]
0x180016776  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001677b  mov     qword ptr [rbp+var_28], 0
0x180016783  lea     rax, [rbp+pszKeyName]
0x180016787  mov     [rsp+80h+var_50], rax
0x18001678c  lea     rax, [rbp+arg_0]
0x180016790  mov     [rsp+80h+var_58], rax
0x180016795  lea     rax, [rbp+var_28]
0x180016799  mov     qword ptr [rsp+80h+dwFlags], rax; int
0x18001679e  mov     r9b, bl
0x1800167a1  mov     r8, rdi
0x1800167a4  lea     rdx, [rbp+var_18]
0x1800167a8  lea     ecx, [rbx+4]
0x1800167ab  call    ?GetAik@@YAJW4PregenKeyType@@PEAU_NGC_IDP_ACCOUNT_INFO@@PEBG_NPEA_KPEAW4DelayRetryAction@@PEAPEAG@Z; GetAik(PregenKeyType,_NGC_IDP_ACCOUNT_INFO *,ushort const *,bool,unsigned __int64 *,DelayRetryAction *,ushort * *)
0x1800167b0  mov     ebx, eax
0x1800167b2  test    eax, eax
0x1800167b4  jns     short loc_1800167E8
0x1800167b6  mov     rcx, [rbp+18h]; this
0x1800167ba  mov     r9d, eax; char *
0x1800167bd  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800167c4  mov     edx, 32Ah; void *
0x1800167c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800167ce  nop
0x1800167cf  lea     rcx, [rbp+var_28]
0x1800167d3  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800167d8  nop
0x1800167d9  lea     rcx, [rbp+pszKeyName]
0x1800167dd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800167e2  nop
0x1800167e3  jmp     loc_180016872
0x1800167e8  lea     rcx, [rbp+var_28]
0x1800167ec  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800167f1  nop
0x1800167f2  mov     rbx, [rbp+pszKeyName]
0x1800167f6  jmp     loc_1800169A4
0x1800167fb  mov     rcx, [rbp+18h]; this
0x1800167ff  mov     ebx, 80090027h
0x180016804  mov     r9d, ebx; char *
0x180016807  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001680e  mov     edx, 32Eh; void *
0x180016813  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016818  nop
0x180016819  lea     rcx, [rbp+pszKeyName]
0x18001681d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016822  nop
0x180016823  jmp     short loc_180016872
0x180016825  xor     edx, edx
0x180016827  lea     rcx, [rbp+pszKeyName]
0x18001682b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180016830  lea     rax, [rbp+pszKeyName]
0x180016834  mov     qword ptr [rsp+80h+dwFlags], rax; int
0x180016839  mov     r9, rdi
0x18001683c  mov     r8, rsi
0x18001683f  mov     rdx, r14
0x180016842  mov     ecx, ebx
0x180016844  call    ?GetTokenBindingAikNameInternal@@YAJW4_NGC_TB_AIK_KEY_TYPE@@PEBG11PEAPEAG@Z; GetTokenBindingAikNameInternal(_NGC_TB_AIK_KEY_TYPE,ushort const *,ushort const *,ushort const *,ushort * *)
0x180016849  mov     ebx, eax
0x18001684b  test    eax, eax
0x18001684d  jns     short loc_180016879
0x18001684f  mov     rcx, [rbp+18h]; this
0x180016853  mov     r9d, eax; char *
0x180016856  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001685d  mov     edx, 306h; void *
0x180016862  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016867  nop
0x180016868  lea     rcx, [rbp+pszKeyName]
0x18001686c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016871  nop
0x180016872  mov     eax, ebx
0x180016874  jmp     loc_1800169BF
0x180016879  mov     [rbp+hObject], 0
0x180016881  mov     rbx, [rbp+hObject]
0x180016885  test    rbx, rbx
0x180016888  jz      short loc_1800168A6
0x18001688a  lea     rcx, [rbp+var_20]; this
0x18001688e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180016893  mov     rcx, rbx; hObject
0x180016896  call    cs:__imp_NCryptFreeObject
0x18001689c  lea     rcx, [rbp+var_20]; this
0x1800168a0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800168a5  nop
0x1800168a6  mov     [rbp+hObject], 0
0x1800168ae  xor     r8d, r8d; dwFlags
0x1800168b1  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x1800168b8  lea     rcx, [rbp+hObject]; phProvider
0x1800168bc  call    cs:__imp_NCryptOpenStorageProvider
0x1800168c2  mov     ebx, eax
0x1800168c4  test    eax, eax
0x1800168c6  jns     short loc_1800168FA
0x1800168c8  mov     rcx, [rbp+18h]; this
0x1800168cc  mov     r9d, eax; char *
0x1800168cf  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800168d6  mov     edx, 30Dh; void *
0x1800168db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800168e0  nop
0x1800168e1  lea     rcx, [rbp+hObject]
0x1800168e5  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800168ea  nop
0x1800168eb  lea     rcx, [rbp+pszKeyName]
0x1800168ef  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800168f4  nop
0x1800168f5  jmp     loc_180016872
0x1800168fa  mov     [rbp+phKey], 0
0x180016902  mov     rbx, [rbp+pszKeyName]
0x180016906  mov     rdi, [rbp+phKey]
0x18001690a  test    rdi, rdi
0x18001690d  jz      short loc_18001692B
0x18001690f  lea     rcx, [rbp+var_20]; this
0x180016913  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180016918  mov     rcx, rdi; hObject
0x18001691b  call    cs:__imp_NCryptFreeObject
0x180016921  lea     rcx, [rbp+var_20]; this
0x180016925  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001692a  nop
0x18001692b  mov     [rbp+phKey], 0
0x180016933  mov     [rsp+80h+dwFlags], 40h ; '@'; int
0x18001693b  xor     r9d, r9d; dwLegacyKeySpec
0x18001693e  mov     r8, rbx; pszKeyName
0x180016941  lea     rdx, [rbp+phKey]; phKey
0x180016945  mov     rcx, [rbp+hObject]; hProvider
0x180016949  call    cs:__imp_NCryptOpenKey
0x18001694f  mov     edi, eax
0x180016951  test    eax, eax
0x180016953  jns     short loc_180016990
0x180016955  mov     rcx, [rbp+18h]; this
0x180016959  mov     r9d, eax; char *
0x18001695c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016963  mov     edx, 316h; void *
0x180016968  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001696d  nop
0x18001696e  lea     rcx, [rbp+phKey]
0x180016972  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016977  nop
0x180016978  lea     rcx, [rbp+hObject]
0x18001697c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016981  nop
0x180016982  lea     rcx, [rbp+pszKeyName]
0x180016986  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001698b  nop
0x18001698c  mov     eax, edi
0x18001698e  jmp     short loc_1800169BF
0x180016990  lea     rcx, [rbp+phKey]
0x180016994  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016999  nop
0x18001699a  lea     rcx, [rbp+hObject]
0x18001699e  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800169a3  nop
0x1800169a4  mov     [rbp+pszKeyName], 0
0x1800169ac  mov     rax, [rbp+arg_20]
0x1800169b0  mov     [rax], rbx
0x1800169b3  lea     rcx, [rbp+pszKeyName]
0x1800169b7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800169bc  nop
0x1800169bd  xor     eax, eax
0x1800169bf  lea     r11, [rsp+80h+var_s0]
0x1800169c7  mov     rbx, [r11+28h]
0x1800169cb  mov     rsi, [r11+30h]
0x1800169cf  mov     rsp, r11
0x1800169d2  pop     r14
0x1800169d4  pop     rdi
0x1800169d5  pop     rbp
0x1800169d6  retn
```
