# GetAik(PregenKeyType,_NGC_IDP_ACCOUNT_INFO *,ushort const *,bool,unsigned __int64 *,DelayRetryAction *,ushort * *)

- ea: `0x180015bf0`
- end: `0x180015e8b`
- name: `?GetAik@@YAJW4PregenKeyType@@PEAU_NGC_IDP_ACCOUNT_INFO@@PEBG_NPEA_KPEAW4DelayRetryAction@@PEAPEAG@Z`
- size: `667`
- prototype: `__int64 __fastcall(unsigned int, NgcUtils **, NgcUtils *, char, NCRYPT_HANDLE *, __int64, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015644`
- `0x180015e94`
- `0x18001608c`
- `0x180016718`
- `0x180016dc0`
- `0x180017070`

## callees

- `0x18000749c`
- `0x180007dc4`
- `0x18000b0fc`
- `0x18000db5c`
- `0x180010730`
- `0x180011e48`
- `0x180015410`
- `0x180015bf0`
- `0x180016f58`
- `0x1800177f4`
- `0x180022ef4`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x180015d51`
- `ncrypt!NCryptFreeObject` at `0x180015dae`
- `ncrypt!NCryptFreeObject` at `0x180015d51`
- `ncrypt!NCryptFreeObject` at `0x180015dae`

## string_xrefs

- `0x180015c55`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180015cb8`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180015de3`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetAik(
        unsigned int a1,
        NgcUtils **a2,
        NgcUtils *a3,
        char a4,
        NCRYPT_HANDLE *a5,
        __int64 a6,
        unsigned __int16 **a7)
{
  const unsigned __int16 *v10; // rdx
  NgcUtils *v11; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v13; // ebx
  int PopRegLocationForKeyMapping; // eax
  HKEY v16; // rbx
  int v17; // eax
  int v18; // edi
  NCRYPT_HANDLE v19; // rdi
  NCRYPT_HANDLE v20; // rdi
  unsigned __int16 *v21; // rax
  NCRYPT_HANDLE v22; // rcx
  unsigned __int16 **v23; // [rsp+20h] [rbp-50h]
  int v24; // [rsp+20h] [rbp-50h]
  unsigned __int16 **v25; // [rsp+20h] [rbp-50h]
  NCRYPT_HANDLE hObject; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int16 *v27; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int16 *v28; // [rsp+40h] [rbp-30h] BYREF
  HKEY lpSubKey; // [rsp+48h] [rbp-28h] BYREF
  NgcUtils *v30[4]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  char v32; // [rsp+98h] [rbp+28h] BYREF

  v30[2] = 0;
  v30[0] = *a2;
  v30[1] = a2[1];
  v28 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v28,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v11,
                                        v10,
                                        L"AIK",
                                        (const unsigned __int16 *)&v28,
                                        v23);
  v13 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      v24);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return v13;
  }
  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  PopRegLocationForKeyMapping = GetPopRegLocationForKeyMapping(
                                  v30,
                                  a3,
                                  v28,
                                  L"PerDeviceAik",
                                  (unsigned __int16 **)&lpSubKey);
  v13 = PopRegLocationForKeyMapping;
  if ( PopRegLocationForKeyMapping < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)PopRegLocationForKeyMapping,
      (int)v25);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return v13;
  }
  v27 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v27,
    0);
  hObject = 0;
  v16 = lpSubKey;
  v17 = OpenAikBasedOnRegistryLocation(lpSubKey, &hObject, &v27);
  v18 = v17;
  if ( !a4 && (unsigned int)(v17 + 2147024894) <= 1 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v27,
      0);
    v19 = hObject;
    if ( hObject )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v32);
      NCryptFreeObject(v19);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v32);
    }
    hObject = 0;
    v25 = &v27;
    v18 = AddAikBasedOnRegistryLocation(a1, v16, &hObject, a6);
    if ( v18 == -2147024816 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v27,
        0);
      v20 = hObject;
      if ( hObject )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v32);
        NCryptFreeObject(v20);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v32);
      }
      hObject = 0;
      v18 = OpenAikBasedOnRegistryLocation(v16, &hObject, &v27);
    }
  }
  if ( v18 >= 0 )
  {
    if ( a7 )
    {
      v21 = v27;
      v27 = 0;
      *a7 = v21;
    }
    v22 = hObject;
    hObject = 0;
    *a5 = v22;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)v18,
      (int)v25);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return (unsigned int)v18;
  }
}

```

## disassembly

```asm
0x180015bf0  mov     [rsp-18h+arg_0], rbx
0x180015bf5  mov     [rsp-18h+arg_10], rsi
0x180015bfa  push    rbp
0x180015bfb  push    rdi
0x180015bfc  push    r14
0x180015bfe  mov     rbp, rsp
0x180015c01  sub     rsp, 70h
0x180015c05  mov     sil, r9b
0x180015c08  mov     rdi, r8
0x180015c0b  mov     r14d, ecx
0x180015c0e  mov     [rbp+var_10], 0
0x180015c16  mov     rax, [rdx]
0x180015c19  mov     [rbp+var_20], rax
0x180015c1d  mov     rax, [rdx+8]
0x180015c21  mov     [rbp+var_18], rax
0x180015c25  mov     [rbp+var_30], 0
0x180015c2d  xor     edx, edx
0x180015c2f  lea     rcx, [rbp+var_30]
0x180015c33  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015c38  lea     r9, [rbp+var_30]; unsigned __int16 *
0x180015c3c  lea     r8, aAik_0; "AIK"
0x180015c43  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180015c48  mov     ebx, eax
0x180015c4a  test    eax, eax
0x180015c4c  jns     short loc_180015C78
0x180015c4e  mov     rcx, [rbp+18h]; this
0x180015c52  mov     r9d, eax; char *
0x180015c55  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180015c5c  mov     edx, 75h ; 'u'; void *
0x180015c61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015c66  nop
0x180015c67  lea     rcx, [rbp+var_30]
0x180015c6b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015c70  nop
0x180015c71  mov     eax, ebx
0x180015c73  jmp     loc_180015E76
0x180015c78  mov     [rbp+lpSubKey], 0
0x180015c80  xor     edx, edx
0x180015c82  lea     rcx, [rbp+lpSubKey]
0x180015c86  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015c8b  lea     rax, [rbp+lpSubKey]
0x180015c8f  mov     [rsp+70h+var_50], rax; int
0x180015c94  lea     r9, aPerdeviceaik; "PerDeviceAik"
0x180015c9b  mov     r8, [rbp+var_30]; unsigned __int16 *
0x180015c9f  mov     rdx, rdi; unsigned __int16 *
0x180015ca2  lea     rcx, [rbp+var_20]; struct _NGC_IDP_ACCOUNT_INFO *
0x180015ca6  call    ?GetPopRegLocationForKeyMapping@@YAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBG11PEAPEAG@Z; GetPopRegLocationForKeyMapping(_NGC_IDP_ACCOUNT_INFO *,ushort const *,ushort const *,ushort const *,ushort * *)
0x180015cab  mov     ebx, eax
0x180015cad  test    eax, eax
0x180015caf  jns     short loc_180015CE0
0x180015cb1  mov     rcx, [rbp+18h]; this
0x180015cb5  mov     r9d, eax; char *
0x180015cb8  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180015cbf  mov     edx, 7Fh; void *
0x180015cc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015cc9  nop
0x180015cca  lea     rcx, [rbp+lpSubKey]
0x180015cce  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015cd3  nop
0x180015cd4  lea     rcx, [rbp+var_30]
0x180015cd8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015cdd  nop
0x180015cde  jmp     short loc_180015C71
0x180015ce0  mov     [rbp+hObject], 0
0x180015ce8  mov     [rbp+var_38], 0
0x180015cf0  xor     edx, edx
0x180015cf2  lea     rcx, [rbp+var_38]
0x180015cf6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015cfb  mov     [rbp+hObject], 0
0x180015d03  lea     r8, [rbp+var_38]; unsigned __int16 **
0x180015d07  lea     rdx, [rbp+hObject]; unsigned __int64 *
0x180015d0b  mov     rbx, [rbp+lpSubKey]
0x180015d0f  mov     rcx, rbx; lpSubKey
0x180015d12  call    ?OpenAikBasedOnRegistryLocation@@YAJPEBGPEA_KPEAPEAG@Z; OpenAikBasedOnRegistryLocation(ushort const *,unsigned __int64 *,ushort * *)
0x180015d17  mov     edi, eax
0x180015d19  test    sil, sil
0x180015d1c  jnz     loc_180015DD8
0x180015d22  lea     ecx, [rax+7FF8FFFEh]
0x180015d28  cmp     ecx, 1
0x180015d2b  ja      loc_180015DD8
0x180015d31  xor     edx, edx
0x180015d33  lea     rcx, [rbp+var_38]
0x180015d37  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015d3c  mov     rdi, [rbp+hObject]
0x180015d40  test    rdi, rdi
0x180015d43  jz      short loc_180015D61
0x180015d45  lea     rcx, [rbp+arg_8]; this
0x180015d49  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180015d4e  mov     rcx, rdi; hObject
0x180015d51  call    cs:__imp_NCryptFreeObject
0x180015d57  lea     rcx, [rbp+arg_8]; this
0x180015d5b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180015d60  nop
0x180015d61  mov     [rbp+hObject], 0
0x180015d69  lea     rax, [rbp+var_38]
0x180015d6d  mov     [rsp+70h+var_50], rax; int
0x180015d72  mov     r9, [rbp+arg_28]
0x180015d76  lea     r8, [rbp+hObject]
0x180015d7a  mov     rdx, rbx
0x180015d7d  mov     ecx, r14d
0x180015d80  call    ?AddAikBasedOnRegistryLocation@@YAJW4PregenKeyType@@PEBGPEA_KPEAW4DelayRetryAction@@PEAPEAG@Z; AddAikBasedOnRegistryLocation(PregenKeyType,ushort const *,unsigned __int64 *,DelayRetryAction *,ushort * *)
0x180015d85  mov     edi, eax
0x180015d87  cmp     eax, 80070050h
0x180015d8c  jnz     short loc_180015DD8
0x180015d8e  xor     edx, edx
0x180015d90  lea     rcx, [rbp+var_38]
0x180015d94  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015d99  mov     rdi, [rbp+hObject]
0x180015d9d  test    rdi, rdi
0x180015da0  jz      short loc_180015DBE
0x180015da2  lea     rcx, [rbp+arg_8]; this
0x180015da6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180015dab  mov     rcx, rdi; hObject
0x180015dae  call    cs:__imp_NCryptFreeObject
0x180015db4  lea     rcx, [rbp+arg_8]; this
0x180015db8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180015dbd  nop
0x180015dbe  mov     [rbp+hObject], 0
0x180015dc6  lea     r8, [rbp+var_38]; unsigned __int16 **
0x180015dca  lea     rdx, [rbp+hObject]; unsigned __int64 *
0x180015dce  mov     rcx, rbx; lpSubKey
0x180015dd1  call    ?OpenAikBasedOnRegistryLocation@@YAJPEBGPEA_KPEAPEAG@Z; OpenAikBasedOnRegistryLocation(ushort const *,unsigned __int64 *,ushort * *)
0x180015dd6  mov     edi, eax
0x180015dd8  test    edi, edi
0x180015dda  jns     short loc_180015E21
0x180015ddc  mov     rcx, [rbp+18h]; this
0x180015de0  mov     r9d, edi; char *
0x180015de3  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180015dea  mov     edx, 9Dh; void *
0x180015def  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015df4  nop
0x180015df5  lea     rcx, [rbp+var_38]
0x180015df9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015dfe  nop
0x180015dff  lea     rcx, [rbp+hObject]
0x180015e03  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180015e08  nop
0x180015e09  lea     rcx, [rbp+lpSubKey]
0x180015e0d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015e12  nop
0x180015e13  lea     rcx, [rbp+var_30]
0x180015e17  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015e1c  nop
0x180015e1d  mov     eax, edi
0x180015e1f  jmp     short loc_180015E76
0x180015e21  mov     rcx, [rbp+arg_30]
0x180015e25  test    rcx, rcx
0x180015e28  jz      short loc_180015E39
0x180015e2a  mov     rax, [rbp+var_38]
0x180015e2e  mov     [rbp+var_38], 0
0x180015e36  mov     [rcx], rax
0x180015e39  mov     rcx, [rbp+hObject]
0x180015e3d  mov     [rbp+hObject], 0
0x180015e45  mov     rax, [rbp+arg_20]
0x180015e49  mov     [rax], rcx
0x180015e4c  lea     rcx, [rbp+var_38]
0x180015e50  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015e55  nop
0x180015e56  lea     rcx, [rbp+hObject]
0x180015e5a  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180015e5f  nop
0x180015e60  lea     rcx, [rbp+lpSubKey]
0x180015e64  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015e69  nop
0x180015e6a  lea     rcx, [rbp+var_30]
0x180015e6e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015e73  nop
0x180015e74  xor     eax, eax
0x180015e76  lea     r11, [rsp+70h+var_s0]
0x180015e7b  mov     rbx, [r11+20h]
0x180015e7f  mov     rsi, [r11+30h]
0x180015e83  mov     rsp, r11
0x180015e86  pop     r14
0x180015e88  pop     rdi
0x180015e89  pop     rbp
0x180015e8a  retn
```
