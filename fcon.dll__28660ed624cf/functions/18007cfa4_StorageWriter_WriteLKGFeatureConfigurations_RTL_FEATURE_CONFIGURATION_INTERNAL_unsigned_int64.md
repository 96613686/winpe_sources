# StorageWriter::WriteLKGFeatureConfigurations(_RTL_FEATURE_CONFIGURATION_INTERNAL *,unsigned __int64)

- ea: `0x18007cfa4`
- end: `0x18007d1bd`
- name: `?WriteLKGFeatureConfigurations@StorageWriter@@SAJPEAU_RTL_FEATURE_CONFIGURATION_INTERNAL@@_K@Z`
- size: `537`
- prototype: `__int64 __fastcall(struct _RTL_FEATURE_CONFIGURATION_INTERNAL *, unsigned __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007dbf0`

## callees

- `0x180004100`
- `0x18000949c`
- `0x180016698`
- `0x180018a90`
- `0x18001e820`
- `0x180024098`
- `0x1800258d8`
- `0x18002b818`
- `0x18004dee0`
- `0x1800711a0`
- `0x1800777bc`
- `0x18007cfa4`
- `0x18007d388`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18007d17b`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18007d17b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d083`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d083`

## string_xrefs

- `0x18007d146`: `LKGConfiguration`
- `0x18007d00c`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18007d05b`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18007d0af`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18007d121`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`

## pseudocode

```c
__int64 __fastcall StorageWriter::WriteLKGFeatureConfigurations(
        struct _RTL_FEATURE_CONFIGURATION_INTERNAL *a1,
        unsigned __int64 a2)
{
  RegPersistedKey *v4; // rbx
  __int64 v5; // r8
  unsigned int v6; // r8d
  unsigned int v7; // r9d
  int v8; // eax
  unsigned int v9; // ebx
  _DWORD *v10; // rbx
  unsigned int v11; // edi
  int LKGFeatureConfigurationsBufferSize; // eax
  LPVOID v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r9
  unsigned __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // edi
  int v22; // eax
  LSTATUS v23; // eax
  struct _SECURITY_ATTRIBUTES *v25; // [rsp+20h] [rbp-30h]
  int v26; // [rsp+20h] [rbp-30h]
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  SIZE_T cb; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned int v30; // [rsp+80h] [rbp+30h] BYREF
  void *v31; // [rsp+88h] [rbp+38h] BYREF

  v30 = 0;
  hKey = 0;
  v4 = RegPersistedKeySingleton::KeyFeatureManagement();
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0,
    v5);
  v8 = RegPersistedKey::RegCreateKeyExW(v4, L"LastKnownGood", v6, v7, v25, &hKey, &v30);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = 0;
    v31 = 0;
    v11 = 0;
    if ( a2 && a1 )
    {
      cb = 0;
      LKGFeatureConfigurationsBufferSize = GetLKGFeatureConfigurationsBufferSize(a2, &cb);
      if ( LKGFeatureConfigurationsBufferSize < 0 )
      {
        v9 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x308,
               (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
               (const char *)(unsigned int)LKGFeatureConfigurationsBufferSize,
               v26);
LABEL_7:
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v31);
        goto LABEL_22;
      }
      v13 = CoTaskMemAlloc(cb);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v31,
        v13);
      v10 = v31;
      if ( !v31 )
      {
        v9 = -2147024882;
        v14 = 779;
        v15 = 2147942414LL;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
          (const char *)v15,
          v26);
        goto LABEL_7;
      }
      memset_0(v31, 0, cb);
      v16 = 0;
      *v10 = 20;
      do
      {
        if ( !(unsigned __int8)RtlpIsImmutableFeatureConfigurationPriority(*((_DWORD *)a1 + 4 * v16 + 1) & 0xF) )
        {
          v19 = 2LL * v11++;
          *(_OWORD *)&v10[2 * v19 + 1] = *(_OWORD *)((char *)a1 + 8 * v18);
        }
        v16 = v17 + 1;
      }
      while ( v16 < a2 );
    }
    cb = 0;
    v20 = GetLKGFeatureConfigurationsBufferSize(v11, &cb);
    v21 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x320,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
        (const char *)(unsigned int)v20,
        v26);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v31);
      v9 = v21;
      goto LABEL_22;
    }
    v22 = RegValet::SetValue::_Set(hKey, L"LKGConfiguration", 3u, v10, cb);
    v9 = v22;
    if ( v22 >= 0 )
    {
      v23 = RegFlushKey(hKey);
      v9 = v23;
      if ( v23 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v31);
        v9 = 0;
        goto LABEL_22;
      }
      v15 = (unsigned int)v23;
      v14 = 805;
    }
    else
    {
      v15 = (unsigned int)v22;
      v14 = 803;
    }
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2FE,
    (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
    (const char *)(unsigned int)v8,
    v26);
LABEL_22:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v9;
}

```

## disassembly

```asm
0x18007cfa4  mov     [rsp-18h+arg_0], rbx
0x18007cfa9  mov     [rsp-18h+arg_8], rsi
0x18007cfae  push    rbp
0x18007cfaf  push    rdi
0x18007cfb0  push    r14
0x18007cfb2  mov     rbp, rsp
0x18007cfb5  sub     rsp, 50h
0x18007cfb9  mov     rsi, rdx
0x18007cfbc  mov     [rbp+arg_10], 0
0x18007cfc3  mov     r14, rcx
0x18007cfc6  mov     [rbp+hKey], 0
0x18007cfce  call    ?KeyFeatureManagement@RegPersistedKeySingleton@@SAAEAVRegPersistedKey@@XZ; RegPersistedKeySingleton::KeyFeatureManagement(void)
0x18007cfd3  xor     edx, edx
0x18007cfd5  lea     rcx, [rbp+hKey]
0x18007cfd9  mov     rbx, rax
0x18007cfdc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18007cfe1  lea     rax, [rbp+arg_10]
0x18007cfe5  mov     rcx, rbx; this
0x18007cfe8  mov     [rsp+50h+var_20], rax; unsigned int *
0x18007cfed  lea     rdx, aLastknowngood; "LastKnownGood"
0x18007cff4  lea     rax, [rbp+hKey]
0x18007cff8  mov     [rsp+50h+var_28], rax; HKEY *
0x18007cffd  call    ?RegCreateKeyExW@RegPersistedKey@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAUHKEY__@@PEAK@Z; RegPersistedKey::RegCreateKeyExW(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18007d002  mov     ebx, eax
0x18007d004  test    eax, eax
0x18007d006  jns     short loc_18007D025
0x18007d008  mov     rcx, [rbp+18h]; this
0x18007d00c  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007d013  mov     r9d, eax; char *
0x18007d016  mov     edx, 2FEh; void *
0x18007d01b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d020  jmp     loc_18007D19F
0x18007d025  xor     ebx, ebx
0x18007d027  mov     [rbp+arg_18], 0
0x18007d02f  xor     edi, edi
0x18007d031  test    rsi, rsi
0x18007d034  jz      loc_18007D104
0x18007d03a  test    r14, r14
0x18007d03d  jz      loc_18007D104
0x18007d043  lea     rdx, [rbp+cb]
0x18007d047  mov     [rbp+cb], rbx
0x18007d04b  mov     rcx, rsi
0x18007d04e  call    GetLKGFeatureConfigurationsBufferSize
0x18007d053  test    eax, eax
0x18007d055  jns     short loc_18007D07F
0x18007d057  mov     rcx, [rbp+18h]; this
0x18007d05b  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007d062  mov     r9d, eax; char *
0x18007d065  mov     edx, 308h; void *
0x18007d06a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007d06f  mov     ebx, eax
0x18007d071  lea     rcx, [rbp+arg_18]
0x18007d075  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007d07a  jmp     loc_18007D19F
0x18007d07f  mov     rcx, [rbp+cb]; cb
0x18007d083  call    cs:__imp_CoTaskMemAlloc
0x18007d089  mov     rdx, rax
0x18007d08c  lea     rcx, [rbp+arg_18]
0x18007d090  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18007d095  mov     rbx, [rbp+arg_18]
0x18007d099  test    rbx, rbx
0x18007d09c  jnz     short loc_18007D0BD
0x18007d09e  mov     ebx, 8007000Eh
0x18007d0a3  mov     edx, 30Bh; void *
0x18007d0a8  mov     r9d, ebx; char *
0x18007d0ab  mov     rcx, [rbp+18h]; this
0x18007d0af  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007d0b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d0bb  jmp     short loc_18007D071
0x18007d0bd  mov     r8, [rbp+cb]; Size
0x18007d0c1  xor     edx, edx; Val
0x18007d0c3  mov     rcx, rbx; void *
0x18007d0c6  call    memset_0
0x18007d0cb  xor     edx, edx
0x18007d0cd  mov     dword ptr [rbx], 14h
0x18007d0d3  mov     r8, rdx
0x18007d0d6  add     r8, r8
0x18007d0d9  mov     ecx, [r14+r8*8+4]
0x18007d0de  and     ecx, 0Fh
0x18007d0e1  call    RtlpIsImmutableFeatureConfigurationPriority
0x18007d0e6  test    al, al
0x18007d0e8  jnz     short loc_18007D0FC
0x18007d0ea  movups  xmm0, xmmword ptr [r14+r8*8]
0x18007d0ef  mov     eax, edi
0x18007d0f1  add     rax, rax
0x18007d0f4  inc     edi
0x18007d0f6  movdqu  xmmword ptr [rbx+rax*8+4], xmm0
0x18007d0fc  inc     rdx
0x18007d0ff  cmp     rdx, rsi
0x18007d102  jb      short loc_18007D0D3
0x18007d104  mov     ecx, edi
0x18007d106  lea     rdx, [rbp+cb]
0x18007d10a  mov     [rbp+cb], 0
0x18007d112  call    GetLKGFeatureConfigurationsBufferSize
0x18007d117  mov     edi, eax
0x18007d119  test    eax, eax
0x18007d11b  jns     short loc_18007D142
0x18007d11d  mov     rcx, [rbp+18h]; this
0x18007d121  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007d128  mov     r9d, eax; char *
0x18007d12b  mov     edx, 320h; void *
0x18007d130  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d135  lea     rcx, [rbp+arg_18]
0x18007d139  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007d13e  mov     ebx, edi
0x18007d140  jmp     short loc_18007D19F
0x18007d142  mov     rax, [rbp+cb]
0x18007d146  lea     rdx, aLkgconfigurati; "LKGConfiguration"
0x18007d14d  mov     rcx, [rbp+hKey]; HKEY
0x18007d151  mov     r9, rbx; void *
0x18007d154  mov     r8d, 3; unsigned int
0x18007d15a  mov     [rsp+50h+var_30], rax; unsigned __int64
0x18007d15f  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18007d164  mov     ebx, eax
0x18007d166  test    eax, eax
0x18007d168  jns     short loc_18007D177
0x18007d16a  mov     r9d, eax
0x18007d16d  mov     edx, 323h
0x18007d172  jmp     loc_18007D0AB
0x18007d177  mov     rcx, [rbp+hKey]; hKey
0x18007d17b  call    cs:__imp_RegFlushKey
0x18007d181  mov     ebx, eax
0x18007d183  test    eax, eax
0x18007d185  jns     short loc_18007D194
0x18007d187  mov     r9d, eax
0x18007d18a  mov     edx, 325h
0x18007d18f  jmp     loc_18007D0AB
0x18007d194  lea     rcx, [rbp+arg_18]
0x18007d198  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007d19d  xor     ebx, ebx
0x18007d19f  lea     rcx, [rbp+hKey]
0x18007d1a3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007d1a8  mov     rsi, [rsp+50h+arg_8]
0x18007d1ad  mov     eax, ebx
0x18007d1af  mov     rbx, [rsp+50h+arg_0]
0x18007d1b4  add     rsp, 50h
0x18007d1b8  pop     r14
0x18007d1ba  pop     rdi
0x18007d1bb  pop     rbp
0x18007d1bc  retn
```
