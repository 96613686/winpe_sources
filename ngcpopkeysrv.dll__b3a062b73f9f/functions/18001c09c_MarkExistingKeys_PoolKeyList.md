# MarkExistingKeys(PoolKeyList &)

- ea: `0x18001c09c`
- end: `0x18001c1dc`
- name: `?MarkExistingKeys@@YAJAEAVPoolKeyList@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(struct PoolKeyList *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b7fc`

## callees

- `0x18000b0fc`
- `0x180011e48`
- `0x180019898`
- `0x18001b05c`
- `0x18001c09c`
- `0x18001c708`

## import_xrefs

- `ncrypt!NCryptEnumKeys` at `0x18001c132`
- `ncrypt!NCryptEnumKeys` at `0x18001c132`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001c0c5`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001c0c5`

## string_xrefs

- `0x18001c0d5`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001c17e`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 __fastcall MarkExistingKeys(struct PoolKeyList *this)
{
  SECURITY_STATUS v2; // eax
  unsigned int v3; // ebx
  SECURITY_STATUS v5; // eax
  bool v6; // r8
  NCryptKeyName *v7; // rbx
  DWORD dwFlags; // [rsp+20h] [rbp-20h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-20h]
  void **v10; // [rsp+30h] [rbp-10h] BYREF
  NCryptKeyName *v11; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+68h] [rbp+28h] BYREF
  NCryptKeyName *ppKeyName; // [rsp+70h] [rbp+30h] BYREF
  PVOID ppEnumState; // [rsp+78h] [rbp+38h] BYREF

  phProvider = 0;
  v2 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  v3 = v2;
  if ( v2 >= 0 )
  {
    ppEnumState = 0;
    while ( 1 )
    {
      v10 = &Microsoft::WRL::Wrappers::HandleT<NCryptBufferHandleTraits>::`vftable';
      v11 = 0;
      ppKeyName = 0;
      v5 = NCryptEnumKeys(phProvider, 0, &ppKeyName, &ppEnumState, 0);
      v3 = v5;
      if ( v5 == -2146893782 )
        break;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x73A,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
          (const char *)(unsigned int)v5,
          dwFlagsa);
        v10 = &Microsoft::WRL::Wrappers::HandleT<NCryptBufferHandleTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<NCryptBufferHandleTraits>::Close(&v10);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NCryptFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NCryptFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppEnumState);
        goto LABEL_3;
      }
      v7 = ppKeyName;
      if ( ppKeyName != v11 )
      {
        Microsoft::WRL::Wrappers::HandleT<NCryptBufferHandleTraits>::Close(&v10);
        v11 = v7;
        v7 = ppKeyName;
      }
      PoolKeyList::SetKeyExistsFlag(this, v7->pszName, v6);
      v10 = &Microsoft::WRL::Wrappers::HandleT<NCryptBufferHandleTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<NCryptBufferHandleTraits>::Close(&v10);
    }
    v10 = &Microsoft::WRL::Wrappers::HandleT<NCryptBufferHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<NCryptBufferHandleTraits>::Close(&v10);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NCryptFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NCryptFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppEnumState);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x729,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v2,
      dwFlags);
LABEL_3:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    return v3;
  }
}

```

## disassembly

```asm
0x18001c09c  mov     [rsp-18h+arg_0], rbx
0x18001c0a1  push    rbp
0x18001c0a2  push    rdi
0x18001c0a3  push    r14
0x18001c0a5  mov     rbp, rsp
0x18001c0a8  sub     rsp, 40h
0x18001c0ac  mov     rdi, rcx
0x18001c0af  mov     [rbp+phProvider], 0
0x18001c0b7  lea     rcx, [rbp+phProvider]; phProvider
0x18001c0bb  xor     r8d, r8d; dwFlags
0x18001c0be  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18001c0c5  call    cs:__imp_NCryptOpenStorageProvider
0x18001c0cb  mov     ebx, eax
0x18001c0cd  test    eax, eax
0x18001c0cf  jns     short loc_18001C0F9
0x18001c0d1  mov     rcx, [rbp+18h]; this
0x18001c0d5  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c0dc  mov     r9d, eax; char *
0x18001c0df  mov     edx, 729h; void *
0x18001c0e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c0e9  lea     rcx, [rbp+phProvider]
0x18001c0ed  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001c0f2  mov     eax, ebx
0x18001c0f4  jmp     loc_18001C1CE
0x18001c0f9  mov     [rbp+ppEnumState], 0
0x18001c101  lea     r14, ??_7?$HandleT@UNCryptBufferHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<NCryptBufferHandleTraits>::`vftable'
0x18001c108  mov     rcx, [rbp+phProvider]; hProvider
0x18001c10c  lea     r9, [rbp+ppEnumState]; ppEnumState
0x18001c110  lea     r8, [rbp+ppKeyName]; ppKeyName
0x18001c114  mov     [rbp+var_10], r14
0x18001c118  xor     edx, edx; pszScope
0x18001c11a  mov     [rbp+var_8], 0
0x18001c122  mov     [rbp+ppKeyName], 0
0x18001c12a  mov     [rsp+40h+dwFlags], 0; int
0x18001c132  call    cs:__imp_NCryptEnumKeys
0x18001c138  mov     ebx, eax
0x18001c13a  cmp     eax, 8009002Ah
0x18001c13f  jz      short loc_18001C1AD
0x18001c141  test    eax, eax
0x18001c143  js      short loc_18001C17A
0x18001c145  mov     rbx, [rbp+ppKeyName]
0x18001c149  cmp     rbx, [rbp+var_8]
0x18001c14d  jz      short loc_18001C160
0x18001c14f  lea     rcx, [rbp+var_10]
0x18001c153  call    ?Close@?$HandleT@UNCryptBufferHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<NCryptBufferHandleTraits>::Close(void)
0x18001c158  mov     [rbp+var_8], rbx
0x18001c15c  mov     rbx, [rbp+ppKeyName]
0x18001c160  mov     rdx, [rbx]; unsigned __int16 *
0x18001c163  mov     rcx, rdi; this
0x18001c166  call    ?SetKeyExistsFlag@PoolKeyList@@QEAAPEBU_KeyEntry@@PEBG_N@Z; PoolKeyList::SetKeyExistsFlag(ushort const *,bool)
0x18001c16b  lea     rcx, [rbp+var_10]
0x18001c16f  mov     [rbp+var_10], r14
0x18001c173  call    ?Close@?$HandleT@UNCryptBufferHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<NCryptBufferHandleTraits>::Close(void)
0x18001c178  jmp     short loc_18001C108
0x18001c17a  mov     rcx, [rbp+18h]; this
0x18001c17e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c185  mov     r9d, ebx; char *
0x18001c188  mov     edx, 73Ah; void *
0x18001c18d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c192  lea     rcx, [rbp+var_10]
0x18001c196  mov     [rbp+var_10], r14
0x18001c19a  call    ?Close@?$HandleT@UNCryptBufferHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<NCryptBufferHandleTraits>::Close(void)
0x18001c19f  lea     rcx, [rbp+ppEnumState]
0x18001c1a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NCryptFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NCryptFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c1a8  jmp     loc_18001C0E9
0x18001c1ad  lea     rcx, [rbp+var_10]
0x18001c1b1  mov     [rbp+var_10], r14
0x18001c1b5  call    ?Close@?$HandleT@UNCryptBufferHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<NCryptBufferHandleTraits>::Close(void)
0x18001c1ba  lea     rcx, [rbp+ppEnumState]
0x18001c1be  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NCryptFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NCryptFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c1c3  lea     rcx, [rbp+phProvider]
0x18001c1c7  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001c1cc  xor     eax, eax
0x18001c1ce  mov     rbx, [rsp+40h+arg_0]
0x18001c1d3  add     rsp, 40h
0x18001c1d7  pop     r14
0x18001c1d9  pop     rdi
0x18001c1da  pop     rbp
0x18001c1db  retn
```
