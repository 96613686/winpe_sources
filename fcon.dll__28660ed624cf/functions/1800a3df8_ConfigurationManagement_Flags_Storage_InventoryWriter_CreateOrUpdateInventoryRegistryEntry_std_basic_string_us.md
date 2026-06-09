# ConfigurationManagement::Flags::Storage::InventoryWriter::CreateOrUpdateInventoryRegistryEntry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ConfigurationManagement::Flags::Storage::InventoryWriterEntry const &)

- ea: `0x1800a3df8`
- end: `0x1800a42a5`
- name: `?CreateOrUpdateInventoryRegistryEntry@InventoryWriter@Storage@Flags@ConfigurationManagement@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVInventoryWriterEntry@234@@Z`
- size: `1197`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callers

- `0x18008a644`

## callees

- `0x180003220`
- `0x18000949c`
- `0x180016698`
- `0x180019704`
- `0x180019890`
- `0x18001e820`
- `0x1800294cc`
- `0x1800a0640`
- `0x1800a3ccc`
- `0x1800a3d6c`
- `0x1800a3df8`
- `0x1800a42ac`
- `0x1800a479c`
- `0x1800a4940`
- `0x1800a4980`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a3ee6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a3ee6`

## string_xrefs

- `0x1800a3e4d`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\inventorywriter.cpp`
- `0x1800a3f0a`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\inventorywriter.cpp`
- `0x1800a3f53`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\inventorywriter.cpp`
- `0x1800a3faa`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\inventorywriter.cpp`
- `0x1800a4018`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\inventorywriter.cpp`
- `0x1800a408d`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\inventorywriter.cpp`
- `0x1800a40e2`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\inventorywriter.cpp`
- `0x1800a4136`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\inventorywriter.cpp`
- `0x1800a418a`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\inventorywriter.cpp`
- `0x1800a4232`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\inventorywriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall ConfigurationManagement::Flags::Storage::InventoryWriter::CreateOrUpdateInventoryRegistryEntry(
        __int64 a1,
        __int64 a2)
{
  unsigned int v4; // edx
  FeatureInventory *v5; // rcx
  __int64 v7; // r8
  __int64 v8; // r8
  const WCHAR *v9; // rax
  LSTATUS v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  int v16; // eax
  unsigned int v17; // ebx
  __int64 v18; // rdx
  int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // rdx
  int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // rdx
  int v25; // eax
  unsigned int v26; // ebx
  __int64 v27; // rdx
  int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rdx
  int v31; // eax
  unsigned int v32; // ebx
  __int64 v33; // rdx
  _QWORD **v34; // rdi
  _QWORD *i; // rbx
  __int64 v36; // rdx
  __int64 Key; // rax
  __int64 v38; // rax
  int v39; // esi
  __int64 v40; // rdx
  __int64 v41; // rdx
  DWORD dwOptions; // [rsp+20h] [rbp-98h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-98h]
  HKEY phkResult; // [rsp+50h] [rbp-68h] BYREF
  __int64 v45; // [rsp+58h] [rbp-60h] BYREF
  _BYTE v46[32]; // [rsp+60h] [rbp-58h] BYREF
  _BYTE v47[32]; // [rsp+80h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter>::GetImpl'::`2'::impl) )
    return 2147500037LL;
  v5 = (FeatureInventory *)*(unsigned int *)(a2 + 32);
  if ( (_DWORD)v5 )
  {
    v45 = *(_QWORD *)FeatureInventory::GetFeatureConfigurationInfo(v5, v4);
    LOBYTE(v7) = *(_BYTE *)(a2 + 240);
    anonymous_namespace_::BuildInventoryRegistryPath(v46, a1, v7, *(unsigned int *)(a2 + 36));
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0,
      v8);
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
    v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0, 0, 0x2000Eu, 0, &phkResult, 0);
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    if ( (v11 & 0x80000000) == 0 )
    {
      v13 = anonymous_namespace_::DeleteAllSubkeys(&phkResult);
      v14 = v13;
      if ( v13 >= 0 )
      {
        if ( *(_QWORD *)(a2 + 192) && (v16 = anonymous_namespace_::WriteMetadata(&phkResult), v17 = v16, v16 < 0) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x99,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\inventorywriter.cpp",
            (const char *)(unsigned int)v16,
            dwOptionsa);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
          std::wstring::_Tidy_deallocate(v46, v18);
          return v17;
        }
        else
        {
          v19 = anonymous_namespace_::WriteRegistryDword(&phkResult, L"ChangeTime");
          v20 = v19;
          if ( v19 >= 0 )
          {
            v22 = anonymous_namespace_::WriteRegistryDword(&phkResult, L"DefaultState");
            v23 = v22;
            if ( v22 >= 0 )
            {
              v25 = anonymous_namespace_::WriteRegistryDword(&phkResult, L"DefaultVariant");
              v26 = v25;
              if ( v25 >= 0 )
              {
                v28 = anonymous_namespace_::WriteRegistryDword(&phkResult, L"VariantPayload");
                v29 = v28;
                if ( v28 >= 0 )
                {
                  v31 = anonymous_namespace_::WriteRegistryDword(&phkResult, L"VariantPayloadKind");
                  v32 = v31;
                  if ( v31 >= 0 )
                  {
                    v34 = *(_QWORD ***)(a2 + 120);
                    for ( i = *v34; ; i = (_QWORD *)*i )
                    {
                      if ( i == v34 )
                      {
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
                        std::wstring::_Tidy_deallocate(v46, v36);
                        return 0;
                      }
                      v45 = 0;
                      Key = ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::GetKey(i + 2, v47);
                      v38 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Key);
                      v39 = anonymous_namespace_::CreateOrOpenSubkey(&phkResult, v38, &v45);
                      std::wstring::_Tidy_deallocate(v47, v40);
                      if ( v39 < 0 )
                        break;
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v45);
                    }
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xB0,
                      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\inventorywriter.cpp",
                      (const char *)(unsigned int)v39,
                      dwOptionsa);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v45);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
                    std::wstring::_Tidy_deallocate(v46, v41);
                    return (unsigned int)v39;
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xA8,
                      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\inventorywriter.cpp",
                      (const char *)(unsigned int)v31,
                      dwOptionsa);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
                    std::wstring::_Tidy_deallocate(v46, v33);
                    return v32;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xA5,
                    (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\inventorywriter.cpp",
                    (const char *)(unsigned int)v28,
                    dwOptionsa);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
                  std::wstring::_Tidy_deallocate(v46, v30);
                  return v29;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xA3,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\inventorywriter.cpp",
                  (const char *)(unsigned int)v25,
                  dwOptionsa);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
                std::wstring::_Tidy_deallocate(v46, v27);
                return v26;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xA1,
                (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\inventorywriter.cpp",
                (const char *)(unsigned int)v22,
                dwOptionsa);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
              std::wstring::_Tidy_deallocate(v46, v24);
              return v23;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9E,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\inventorywriter.cpp",
              (const char *)(unsigned int)v19,
              dwOptionsa);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
            std::wstring::_Tidy_deallocate(v46, v21);
            return v20;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x95,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\inventorywriter.cpp",
          (const char *)(unsigned int)v13,
          dwOptionsa);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        std::wstring::_Tidy_deallocate(v46, v15);
        return v14;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\inventorywriter.cpp",
        (const char *)v11,
        dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      std::wstring::_Tidy_deallocate(v46, v12);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\inventorywriter.cpp",
      (const char *)0x80070057LL,
      dwOptions);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800a3df8  mov     [rsp+arg_10], rbx
0x1800a3dfd  mov     [rsp+arg_18], rsi
0x1800a3e02  push    rdi
0x1800a3e03  sub     rsp, 0B0h
0x1800a3e0a  mov     rax, cs:__security_cookie
0x1800a3e11  xor     rax, rsp
0x1800a3e14  mov     [rsp+0B8h+var_18], rax
0x1800a3e1c  mov     rdi, rdx
0x1800a3e1f  mov     rbx, rcx
0x1800a3e22  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter>::GetImpl(void)'::`2'::impl
0x1800a3e29  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter>::__private_IsEnabled(void)
0x1800a3e2e  test    al, al
0x1800a3e30  jz      loc_1800A427A
0x1800a3e36  mov     ecx, [rdi+20h]; this
0x1800a3e39  test    ecx, ecx
0x1800a3e3b  jnz     short loc_1800A3E65
0x1800a3e3d  mov     rcx, [rsp+0B8h]; this
0x1800a3e45  mov     ebx, 80070057h
0x1800a3e4a  mov     r9d, ebx; char *
0x1800a3e4d  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\featuremanage"...
0x1800a3e54  mov     edx, 84h; void *
0x1800a3e59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3e5e  mov     eax, ebx
0x1800a3e60  jmp     loc_1800A427F
0x1800a3e65  call    ?GetFeatureConfigurationInfo@FeatureInventory@@YAAEAU_FEATURE_CONFIGURATION_INFO@FeatureStaging@@I@Z; FeatureInventory::GetFeatureConfigurationInfo(uint)
0x1800a3e6a  mov     rax, [rax]
0x1800a3e6d  mov     [rsp+0B8h+var_60], rax
0x1800a3e72  mov     r9d, [rdi+24h]
0x1800a3e76  mov     r8b, [rdi+0F0h]
0x1800a3e7d  mov     rdx, rbx
0x1800a3e80  lea     rcx, [rsp+0B8h+var_58]
0x1800a3e85  call    _anonymous_namespace___BuildInventoryRegistryPath
0x1800a3e8a  nop
0x1800a3e8b  mov     [rsp+0B8h+var_68], 0
0x1800a3e94  xor     edx, edx
0x1800a3e96  lea     rcx, [rsp+0B8h+var_68]
0x1800a3e9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a3ea0  lea     rcx, [rsp+0B8h+var_58]
0x1800a3ea5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a3eaa  mov     rdx, rax; lpSubKey
0x1800a3ead  mov     [rsp+0B8h+lpdwDisposition], 0; lpdwDisposition
0x1800a3eb6  lea     rax, [rsp+0B8h+var_68]
0x1800a3ebb  mov     [rsp+0B8h+phkResult], rax; phkResult
0x1800a3ec0  mov     [rsp+0B8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a3ec9  mov     [rsp+0B8h+samDesired], 2000Eh; samDesired
0x1800a3ed1  mov     [rsp+0B8h+dwOptions], 0; int
0x1800a3ed9  xor     r9d, r9d; lpClass
0x1800a3edc  xor     r8d, r8d; Reserved
0x1800a3edf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a3ee6  call    cs:__imp_RegCreateKeyExW
0x1800a3eec  mov     ebx, eax
0x1800a3eee  test    eax, eax
0x1800a3ef0  jle     short loc_1800A3EFB
0x1800a3ef2  movzx   ebx, ax
0x1800a3ef5  or      ebx, 80070000h
0x1800a3efb  test    ebx, ebx
0x1800a3efd  jns     short loc_1800A3F38
0x1800a3eff  mov     rcx, [rsp+0B8h]; this
0x1800a3f07  mov     r9d, ebx; char *
0x1800a3f0a  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\featuremanage"...
0x1800a3f11  mov     edx, 91h; void *
0x1800a3f16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3f1b  nop
0x1800a3f1c  lea     rcx, [rsp+0B8h+var_68]
0x1800a3f21  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a3f26  nop
0x1800a3f27  lea     rcx, [rsp+0B8h+var_58]
0x1800a3f2c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3f31  mov     eax, ebx
0x1800a3f33  jmp     loc_1800A427F
0x1800a3f38  lea     rcx, [rsp+0B8h+var_68]
0x1800a3f3d  call    _anonymous_namespace___DeleteAllSubkeys
0x1800a3f42  mov     ebx, eax
0x1800a3f44  test    eax, eax
0x1800a3f46  jns     short loc_1800A3F81
0x1800a3f48  mov     rcx, [rsp+0B8h]; this
0x1800a3f50  mov     r9d, eax; char *
0x1800a3f53  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\featuremanage"...
0x1800a3f5a  mov     edx, 95h; void *
0x1800a3f5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3f64  nop
0x1800a3f65  lea     rcx, [rsp+0B8h+var_68]
0x1800a3f6a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a3f6f  nop
0x1800a3f70  lea     rcx, [rsp+0B8h+var_58]
0x1800a3f75  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3f7a  mov     eax, ebx
0x1800a3f7c  jmp     loc_1800A427F
0x1800a3f81  lea     rdx, [rdi+0B0h]
0x1800a3f88  cmp     qword ptr [rdx+10h], 0
0x1800a3f8d  jz      short loc_1800A3FD8
0x1800a3f8f  lea     rcx, [rsp+0B8h+var_68]
0x1800a3f94  call    _anonymous_namespace___WriteMetadata
0x1800a3f99  mov     ebx, eax
0x1800a3f9b  test    eax, eax
0x1800a3f9d  jns     short loc_1800A3FD8
0x1800a3f9f  mov     rcx, [rsp+0B8h]; this
0x1800a3fa7  mov     r9d, eax; char *
0x1800a3faa  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\featuremanage"...
0x1800a3fb1  mov     edx, 99h; void *
0x1800a3fb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3fbb  nop
0x1800a3fbc  lea     rcx, [rsp+0B8h+var_68]
0x1800a3fc1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a3fc6  nop
0x1800a3fc7  lea     rcx, [rsp+0B8h+var_58]
0x1800a3fcc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3fd1  mov     eax, ebx
0x1800a3fd3  jmp     loc_1800A427F
0x1800a3fd8  mov     r8, [rdi+48h]
0x1800a3fdc  mov     rax, r8
0x1800a3fdf  shr     rax, 20h
0x1800a3fe3  mov     ebx, dword ptr [rsp+0B8h+var_60+4]
0x1800a3fe7  test    al, al
0x1800a3fe9  jnz     short loc_1800A3FF6
0x1800a3feb  mov     r8d, ebx
0x1800a3fee  shr     r8d, 9
0x1800a3ff2  and     r8d, 3
0x1800a3ff6  lea     rdx, aChangetime; "ChangeTime"
0x1800a3ffd  lea     rcx, [rsp+0B8h+var_68]
0x1800a4002  call    _anonymous_namespace___WriteRegistryDword
0x1800a4007  mov     esi, eax
0x1800a4009  test    eax, eax
0x1800a400b  jns     short loc_1800A4046
0x1800a400d  mov     rcx, [rsp+0B8h]; this
0x1800a4015  mov     r9d, eax; char *
0x1800a4018  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\featuremanage"...
0x1800a401f  mov     edx, 9Eh; void *
0x1800a4024  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4029  nop
0x1800a402a  lea     rcx, [rsp+0B8h+var_68]
0x1800a402f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a4034  nop
0x1800a4035  lea     rcx, [rsp+0B8h+var_58]
0x1800a403a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a403f  mov     eax, esi
0x1800a4041  jmp     loc_1800A427F
0x1800a4046  shr     ebx, 7
0x1800a4049  and     ebx, 3
0x1800a404c  jz      short loc_1800A4065
0x1800a404e  sub     ebx, 1
0x1800a4051  jz      short loc_1800A4065
0x1800a4053  sub     ebx, 1
0x1800a4056  jz      short loc_1800A405D
0x1800a4058  cmp     ebx, 1
0x1800a405b  jnz     short loc_1800A4065
0x1800a405d  mov     r8d, 2
0x1800a4063  jmp     short loc_1800A406B
0x1800a4065  mov     r8d, 1
0x1800a406b  lea     rdx, aDefaultstate; "DefaultState"
0x1800a4072  lea     rcx, [rsp+0B8h+var_68]
0x1800a4077  call    _anonymous_namespace___WriteRegistryDword
0x1800a407c  mov     ebx, eax
0x1800a407e  test    eax, eax
0x1800a4080  jns     short loc_1800A40BB
0x1800a4082  mov     rcx, [rsp+0B8h]; this
0x1800a408a  mov     r9d, eax; char *
0x1800a408d  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\featuremanage"...
0x1800a4094  mov     edx, 0A1h; void *
0x1800a4099  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a409e  nop
0x1800a409f  lea     rcx, [rsp+0B8h+var_68]
0x1800a40a4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a40a9  nop
0x1800a40aa  lea     rcx, [rsp+0B8h+var_58]
0x1800a40af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a40b4  mov     eax, ebx
0x1800a40b6  jmp     loc_1800A427F
0x1800a40bb  movzx   r8d, byte ptr [rdi+38h]
0x1800a40c0  lea     rdx, aDefaultvariant; "DefaultVariant"
0x1800a40c7  lea     rcx, [rsp+0B8h+var_68]
0x1800a40cc  call    _anonymous_namespace___WriteRegistryDword
0x1800a40d1  mov     ebx, eax
0x1800a40d3  test    eax, eax
0x1800a40d5  jns     short loc_1800A4110
0x1800a40d7  mov     rcx, [rsp+0B8h]; this
0x1800a40df  mov     r9d, eax; char *
0x1800a40e2  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\featuremanage"...
0x1800a40e9  mov     edx, 0A3h; void *
0x1800a40ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a40f3  nop
0x1800a40f4  lea     rcx, [rsp+0B8h+var_68]
0x1800a40f9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a40fe  nop
0x1800a40ff  lea     rcx, [rsp+0B8h+var_58]
0x1800a4104  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a4109  mov     eax, ebx
0x1800a410b  jmp     loc_1800A427F
0x1800a4110  mov     r8d, [rdi+3Ch]
0x1800a4114  lea     rdx, aVariantpayload; "VariantPayload"
0x1800a411b  lea     rcx, [rsp+0B8h+var_68]
0x1800a4120  call    _anonymous_namespace___WriteRegistryDword
0x1800a4125  mov     ebx, eax
0x1800a4127  test    eax, eax
0x1800a4129  jns     short loc_1800A4164
0x1800a412b  mov     rcx, [rsp+0B8h]; this
0x1800a4133  mov     r9d, eax; char *
0x1800a4136  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\featuremanage"...
0x1800a413d  mov     edx, 0A5h; void *
0x1800a4142  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4147  nop
0x1800a4148  lea     rcx, [rsp+0B8h+var_68]
0x1800a414d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a4152  nop
0x1800a4153  lea     rcx, [rsp+0B8h+var_58]
0x1800a4158  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a415d  mov     eax, ebx
0x1800a415f  jmp     loc_1800A427F
0x1800a4164  mov     r8d, [rdi+40h]
0x1800a4168  lea     rdx, aVariantpayload_0; "VariantPayloadKind"
0x1800a416f  lea     rcx, [rsp+0B8h+var_68]
0x1800a4174  call    _anonymous_namespace___WriteRegistryDword
0x1800a4179  mov     ebx, eax
0x1800a417b  test    eax, eax
0x1800a417d  jns     short loc_1800A41B8
0x1800a417f  mov     rcx, [rsp+0B8h]; this
0x1800a4187  mov     r9d, eax; char *
0x1800a418a  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\featuremanage"...
0x1800a4191  mov     edx, 0A8h; void *
0x1800a4196  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a419b  nop
0x1800a419c  lea     rcx, [rsp+0B8h+var_68]
0x1800a41a1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a41a6  nop
0x1800a41a7  lea     rcx, [rsp+0B8h+var_58]
0x1800a41ac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a41b1  mov     eax, ebx
0x1800a41b3  jmp     loc_1800A427F
0x1800a41b8  mov     rdi, [rdi+78h]
0x1800a41bc  mov     rbx, [rdi]
0x1800a41bf  cmp     rbx, rdi
0x1800a41c2  jnz     short loc_1800A41E0
0x1800a41c4  lea     rcx, [rsp+0B8h+var_68]
0x1800a41c9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a41ce  nop
0x1800a41cf  lea     rcx, [rsp+0B8h+var_58]
0x1800a41d4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a41d9  xor     eax, eax
0x1800a41db  jmp     loc_1800A427F
0x1800a41e0  mov     [rsp+0B8h+var_60], 0
0x1800a41e9  lea     rcx, [rbx+10h]
0x1800a41ed  lea     rdx, [rsp+0B8h+var_38]
0x1800a41f5  call    ?GetKey@FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::GetKey(void)
0x1800a41fa  mov     rcx, rax
0x1800a41fd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a4202  lea     r8, [rsp+0B8h+var_60]
0x1800a4207  mov     rdx, rax
0x1800a420a  lea     rcx, [rsp+0B8h+var_68]
0x1800a420f  call    _anonymous_namespace___CreateOrOpenSubkey
0x1800a4214  mov     esi, eax
0x1800a4216  lea     rcx, [rsp+0B8h+var_38]
0x1800a421e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a4223  test    esi, esi
0x1800a4225  jns     short loc_1800A4268
0x1800a4227  mov     rcx, [rsp+0B8h]; this
0x1800a422f  mov     r9d, esi; char *
0x1800a4232  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\featuremanage"...
0x1800a4239  mov     edx, 0B0h; void *
0x1800a423e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4243  nop
0x1800a4244  lea     rcx, [rsp+0B8h+var_60]
0x1800a4249  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a424e  nop
0x1800a424f  lea     rcx, [rsp+0B8h+var_68]
0x1800a4254  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a4259  nop
0x1800a425a  lea     rcx, [rsp+0B8h+var_58]
0x1800a425f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a4264  mov     eax, esi
0x1800a4266  jmp     short loc_1800A427F
0x1800a4268  lea     rcx, [rsp+0B8h+var_60]
0x1800a426d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a4272  mov     rbx, [rbx]
0x1800a4275  jmp     loc_1800A41BF
0x1800a427a  mov     eax, 80004005h
0x1800a427f  mov     rcx, [rsp+0B8h+var_18]
0x1800a4287  xor     rcx, rsp; StackCookie
0x1800a428a  call    __security_check_cookie
0x1800a428f  lea     r11, [rsp+0B8h+var_8]
0x1800a4297  mov     rbx, [r11+20h]
0x1800a429b  mov     rsi, [r11+28h]
0x1800a429f  mov     rsp, r11
0x1800a42a2  pop     rdi
0x1800a42a3  retn
```
