# NgcUtils::OpenAikNCryptHandle(ushort const *,unsigned __int64 *)

- ea: `0x18001d954`
- end: `0x18001db10`
- name: `?OpenAikNCryptHandle@NgcUtils@@YAJPEBGPEA_K@Z`
- size: `444`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016850`
- `0x180016b24`

## callees

- `0x18000cc34`
- `0x180010310`
- `0x180014bcc`
- `0x180016708`
- `0x18001c724`
- `0x18001c928`
- `0x18001d85c`
- `0x18001d954`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x18001da57`
- `ncrypt!NCryptSetProperty` at `0x18001da57`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001d984`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001d984`
- `ncrypt!NCryptOpenKey` at `0x18001daac`
- `ncrypt!NCryptOpenKey` at `0x18001daac`

## string_xrefs

- `0x18001d997`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001da09`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001da6a`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001dabf`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcUtils::OpenAikNCryptHandle(NgcUtils *this, unsigned __int16 *a2, unsigned __int64 *a3)
{
  SECURITY_STATUS v5; // eax
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // r8
  int v8; // ebx
  unsigned __int16 **v9; // rdx
  int WindowsAikAlternateLocation; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r9
  SECURITY_STATUS v14; // eax
  SECURITY_STATUS v15; // eax
  NCRYPT_KEY_HANDLE v16; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-20h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-20h]
  DWORD dwFlagsb; // [rsp+20h] [rbp-20h]
  NCRYPT_PROV_HANDLE phProvider[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  PBYTE pbInput; // [rsp+70h] [rbp+30h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+78h] [rbp+38h] BYREF

  phProvider[0] = 0;
  v5 = NCryptOpenStorageProvider(phProvider, L"Microsoft Platform Crypto Provider", 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)v5,
      dwFlags);
    goto LABEL_17;
  }
  pbInput = 0;
  v8 = 0;
  if ( (int)StringCchLengthW((const unsigned __int16 *)this, 0xCu, (unsigned __int64 *)&pbInput) >= 0
    && NgcUtils::AreStringsEqual((const WCHAR *)this, L"Windows AIK", v7) )
  {
    pbInput = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pbInput,
      0);
    WindowsAikAlternateLocation = NgcUtils::GetWindowsAikAlternateLocation((unsigned __int16 ***)&pbInput, v9);
    v6 = WindowsAikAlternateLocation;
    if ( WindowsAikAlternateLocation < 0 )
    {
      v11 = (unsigned int)WindowsAikAlternateLocation;
      v12 = 56;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
        (const char *)v11,
        dwFlags);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&pbInput);
      goto LABEL_17;
    }
    if ( pbInput )
    {
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)&pbInput[2 * v13] );
      v14 = NCryptSetProperty(phProvider[0], L"PCP_ALTERNATE_KEY_STORAGE_LOCATION", pbInput, 2 * v13 + 2, 0);
      v6 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x187,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
          (const char *)(unsigned int)v14,
          dwFlagsa);
        v11 = v6;
        v12 = 61;
        goto LABEL_7;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&pbInput);
    v8 = 1;
  }
  phKey = 0;
  v15 = NCryptOpenKey(phProvider[0], &phKey, (LPCWSTR)this, 0, 32 * v8);
  v6 = v15;
  if ( v15 >= 0 )
  {
    v16 = phKey;
    phKey = 0;
    *(_QWORD *)a2 = v16;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)v15,
      dwFlagsb);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  }
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(phProvider);
  return v6;
}

```

## disassembly

```asm
0x18001d954  mov     [rsp-18h+arg_0], rbx
0x18001d959  mov     [rsp-18h+arg_8], rsi
0x18001d95e  push    rbp
0x18001d95f  push    rdi
0x18001d960  push    r14
0x18001d962  mov     rbp, rsp
0x18001d965  sub     rsp, 40h
0x18001d969  mov     rsi, rdx
0x18001d96c  mov     rdi, rcx
0x18001d96f  xor     r14d, r14d
0x18001d972  mov     [rbp+phProvider], r14
0x18001d976  xor     r8d, r8d; dwFlags
0x18001d979  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18001d980  lea     rcx, [rbp+phProvider]; phProvider
0x18001d984  call    cs:__imp_NCryptOpenStorageProvider
0x18001d98a  mov     ebx, eax
0x18001d98c  test    eax, eax
0x18001d98e  jns     short loc_18001D9AC
0x18001d990  mov     rcx, [rbp+18h]; this
0x18001d994  mov     r9d, eax; char *
0x18001d997  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d99e  lea     edx, [r14+2Fh]; void *
0x18001d9a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d9a7  jmp     loc_18001DAF2
0x18001d9ac  mov     [rbp+pbInput], r14
0x18001d9b0  lea     r8, [rbp+pbInput]; unsigned __int64 *
0x18001d9b4  mov     edx, 0Ch; unsigned __int64
0x18001d9b9  mov     rcx, rdi; unsigned __int16 *
0x18001d9bc  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001d9c1  mov     ebx, r14d
0x18001d9c4  test    eax, eax
0x18001d9c6  js      loc_18001DA93
0x18001d9cc  lea     rdx, aWindowsAik; "Windows AIK"
0x18001d9d3  mov     rcx, rdi; this
0x18001d9d6  call    ?AreStringsEqual@NgcUtils@@YA_NPEBG0@Z; NgcUtils::AreStringsEqual(ushort const *,ushort const *)
0x18001d9db  test    al, al
0x18001d9dd  jz      loc_18001DA93
0x18001d9e3  mov     [rbp+pbInput], r14
0x18001d9e7  xor     edx, edx
0x18001d9e9  lea     rcx, [rbp+pbInput]
0x18001d9ed  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001d9f2  lea     rcx, [rbp+pbInput]; this
0x18001d9f6  call    ?GetWindowsAikAlternateLocation@NgcUtils@@YAJPEAPEAG@Z; NgcUtils::GetWindowsAikAlternateLocation(ushort * *)
0x18001d9fb  mov     ebx, eax
0x18001d9fd  test    eax, eax
0x18001d9ff  jns     short loc_18001DA28
0x18001da01  mov     r9d, eax; char *
0x18001da04  mov     edx, 38h ; '8'; void *
0x18001da09  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001da10  mov     rcx, [rbp+18h]; this
0x18001da14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da19  nop
0x18001da1a  lea     rcx, [rbp+pbInput]
0x18001da1e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001da23  jmp     loc_18001DAF2
0x18001da28  mov     r8, [rbp+pbInput]; pbInput
0x18001da2c  test    r8, r8
0x18001da2f  jz      short loc_18001DA85
0x18001da31  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001da35  inc     r9
0x18001da38  cmp     [r8+r9*2], r14w
0x18001da3d  jnz     short loc_18001DA35
0x18001da3f  lea     r9d, ds:2[r9*2]; cbInput
0x18001da47  mov     [rsp+40h+dwFlags], r14d; int
0x18001da4c  lea     rdx, aPcpAlternateKe; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x18001da53  mov     rcx, [rbp+phProvider]; hObject
0x18001da57  call    cs:__imp_NCryptSetProperty
0x18001da5d  mov     ebx, eax
0x18001da5f  test    eax, eax
0x18001da61  jns     short loc_18001DA85
0x18001da63  mov     rcx, [rbp+18h]; this
0x18001da67  mov     r9d, eax; char *
0x18001da6a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001da71  mov     edx, 187h; void *
0x18001da76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da7b  mov     r9d, ebx
0x18001da7e  mov     edx, 3Dh ; '='
0x18001da83  jmp     short loc_18001DA09
0x18001da85  lea     rcx, [rbp+pbInput]
0x18001da89  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001da8e  mov     ebx, 1
0x18001da93  mov     [rbp+phKey], r14
0x18001da97  shl     ebx, 5
0x18001da9a  mov     [rsp+40h+dwFlags], ebx; int
0x18001da9e  xor     r9d, r9d; dwLegacyKeySpec
0x18001daa1  mov     r8, rdi; pszKeyName
0x18001daa4  lea     rdx, [rbp+phKey]; phKey
0x18001daa8  mov     rcx, [rbp+phProvider]; hProvider
0x18001daac  call    cs:__imp_NCryptOpenKey
0x18001dab2  mov     ebx, eax
0x18001dab4  test    eax, eax
0x18001dab6  jns     short loc_18001DADB
0x18001dab8  mov     rcx, [rbp+18h]; this
0x18001dabc  mov     r9d, eax; char *
0x18001dabf  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001dac6  mov     edx, 46h ; 'F'; void *
0x18001dacb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dad0  lea     rcx, [rbp+phKey]
0x18001dad4  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001dad9  jmp     short loc_18001DAF2
0x18001dadb  mov     rax, [rbp+phKey]
0x18001dadf  mov     [rbp+phKey], r14
0x18001dae3  mov     [rsi], rax
0x18001dae6  lea     rcx, [rbp+phKey]
0x18001daea  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001daef  mov     ebx, r14d
0x18001daf2  lea     rcx, [rbp+phProvider]
0x18001daf6  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001dafb  mov     eax, ebx
0x18001dafd  mov     rbx, [rsp+40h+arg_0]
0x18001db02  mov     rsi, [rsp+40h+arg_8]
0x18001db07  add     rsp, 40h
0x18001db0b  pop     r14
0x18001db0d  pop     rdi
0x18001db0e  pop     rbp
0x18001db0f  retn
```
