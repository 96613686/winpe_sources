# CreateUnfinalizedNgcKeyHandle(_NGC_IDP_ACCOUNT_INFO *,ushort const *,ushort const *,bool,unsigned __int64 *)

- ea: `0x18001b850`
- end: `0x18001b9ac`
- name: `?CreateUnfinalizedNgcKeyHandle@@YAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBG1_NPEA_K@Z`
- size: `348`
- prototype: `int(struct _NGC_IDP_ACCOUNT_INFO *, const unsigned __int16 *, const unsigned __int16 *, bool, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002abc0`

## callees

- `0x180006538`
- `0x1800167f8`
- `0x180018790`
- `0x18001b850`
- `0x18002ae30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b8ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b8ea`
- `ncrypt!NCryptFreeObject` at `0x18001b8fd`
- `ncrypt!NCryptFreeObject` at `0x18001b8fd`
- `ncrypt!NCryptCreatePersistedKey` at `0x18001b930`
- `ncrypt!NCryptCreatePersistedKey` at `0x18001b930`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001b883`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001b883`

## string_xrefs

- `0x18001b893`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18001b8cd`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18001b940`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
__int64 __fastcall CreateUnfinalizedNgcKeyHandle(
        struct _NGC_IDP_ACCOUNT_INFO *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int8 a4,
        unsigned __int64 *a5)
{
  int v6; // r14d
  SECURITY_STATUS v9; // eax
  unsigned int v10; // ebx
  int UserIdKeyName; // eax
  SECURITY_STATUS v12; // eax
  DWORD dwLegacyKeySpec; // [rsp+20h] [rbp-38h]
  DWORD dwLegacyKeySpeca; // [rsp+20h] [rbp-38h]
  NCRYPT_KEY_HANDLE phKey; // [rsp+30h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-20h] BYREF
  NCRYPT_PROV_HANDLE phProvider[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]

  v6 = a4;
  phProvider[0] = 0;
  v9 = NCryptOpenStorageProvider(phProvider, L"Microsoft Passport Key Storage Provider", 0);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v9,
      dwLegacyKeySpec);
LABEL_13:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(phProvider);
    return v10;
  }
  hMem = 0;
  UserIdKeyName = NgcGetUserIdKeyName(a1, a3, &hMem);
  v10 = UserIdKeyName;
  if ( UserIdKeyName >= 0 )
  {
    phKey = 0;
    v12 = NCryptCreatePersistedKey(phProvider[0], &phKey, a2, (LPCWSTR)hMem, 0, v6 << 7);
    v10 = v12;
    if ( v12 >= 0 )
    {
      if ( a5 )
      {
        *a5 = phKey;
        phKey = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
      v10 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
        (const char *)(unsigned int)v12,
        dwLegacyKeySpeca);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
    }
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC6,
    (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
    (const char *)(unsigned int)UserIdKeyName,
    dwLegacyKeySpec);
  if ( hMem )
    LocalFree(hMem);
  if ( phProvider[0] )
    NCryptFreeObject(phProvider[0]);
  return v10;
}

```

## disassembly

```asm
0x18001b850  push    rbp
0x18001b852  push    rbx
0x18001b853  push    rsi
0x18001b854  push    rdi
0x18001b855  push    r14
0x18001b857  push    r15
0x18001b859  mov     rbp, rsp
0x18001b85c  sub     rsp, 58h
0x18001b860  mov     rdi, r8
0x18001b863  movzx   r14d, r9b
0x18001b867  mov     r15, rdx
0x18001b86a  mov     [rbp+phProvider], 0
0x18001b872  mov     rsi, rcx
0x18001b875  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x18001b87c  xor     r8d, r8d; dwFlags
0x18001b87f  lea     rcx, [rbp+phProvider]; phProvider
0x18001b883  call    cs:__imp_NCryptOpenStorageProvider
0x18001b889  mov     ebx, eax
0x18001b88b  test    eax, eax
0x18001b88d  jns     short loc_18001B8AC
0x18001b88f  mov     rcx, [rbp+30h]; this
0x18001b893  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18001b89a  mov     r9d, eax; char *
0x18001b89d  mov     edx, 0C0h; void *
0x18001b8a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b8a7  jmp     loc_18001B994
0x18001b8ac  lea     r8, [rbp+hMem]
0x18001b8b0  mov     [rbp+hMem], 0
0x18001b8b8  mov     rdx, rdi
0x18001b8bb  mov     rcx, rsi
0x18001b8be  call    NgcGetUserIdKeyName
0x18001b8c3  mov     ebx, eax
0x18001b8c5  test    eax, eax
0x18001b8c7  jns     short loc_18001B908
0x18001b8c9  mov     rcx, [rbp+30h]; this
0x18001b8cd  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18001b8d4  mov     r9d, eax; char *
0x18001b8d7  mov     edx, 0C6h; void *
0x18001b8dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b8e1  mov     rcx, [rbp+hMem]; hMem
0x18001b8e5  test    rcx, rcx
0x18001b8e8  jz      short loc_18001B8F0
0x18001b8ea  call    cs:__imp_LocalFree
0x18001b8f0  mov     rcx, [rbp+phProvider]; hObject
0x18001b8f4  test    rcx, rcx
0x18001b8f7  jz      loc_18001B99D
0x18001b8fd  call    cs:__imp_NCryptFreeObject
0x18001b903  jmp     loc_18001B99D
0x18001b908  mov     r9, [rbp+hMem]; pszKeyName
0x18001b90c  lea     rdx, [rbp+phKey]; phKey
0x18001b910  mov     rcx, [rbp+phProvider]; hProvider
0x18001b914  mov     r8, r15; pszAlgId
0x18001b917  shl     r14d, 7
0x18001b91b  mov     [rsp+58h+dwFlags], r14d; dwFlags
0x18001b920  mov     [rsp+58h+dwLegacyKeySpec], 0; int
0x18001b928  mov     [rbp+phKey], 0
0x18001b930  call    cs:__imp_NCryptCreatePersistedKey
0x18001b936  mov     ebx, eax
0x18001b938  test    eax, eax
0x18001b93a  jns     short loc_18001B968
0x18001b93c  mov     rcx, [rbp+30h]; this
0x18001b940  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18001b947  mov     r9d, eax; char *
0x18001b94a  mov     edx, 0CFh; void *
0x18001b94f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b954  lea     rcx, [rbp+phKey]
0x18001b958  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001b95d  lea     rcx, [rbp+hMem]; void *
0x18001b961  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18001b966  jmp     short loc_18001B994
0x18001b968  mov     rcx, [rbp+arg_20]
0x18001b96c  test    rcx, rcx
0x18001b96f  jz      short loc_18001B980
0x18001b971  mov     rax, [rbp+phKey]
0x18001b975  mov     [rcx], rax
0x18001b978  mov     [rbp+phKey], 0
0x18001b980  lea     rcx, [rbp+phKey]
0x18001b984  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001b989  lea     rcx, [rbp+hMem]; void *
0x18001b98d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18001b992  xor     ebx, ebx
0x18001b994  lea     rcx, [rbp+phProvider]
0x18001b998  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001b99d  mov     eax, ebx
0x18001b99f  add     rsp, 58h
0x18001b9a3  pop     r15
0x18001b9a5  pop     r14
0x18001b9a7  pop     rdi
0x18001b9a8  pop     rsi
0x18001b9a9  pop     rbx
0x18001b9aa  pop     rbp
0x18001b9ab  retn
```
