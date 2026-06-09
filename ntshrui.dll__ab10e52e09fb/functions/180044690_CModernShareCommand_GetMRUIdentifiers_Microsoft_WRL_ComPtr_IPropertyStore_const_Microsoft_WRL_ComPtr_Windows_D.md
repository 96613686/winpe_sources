# CModernShareCommand::GetMRUIdentifiers(Microsoft::WRL::ComPtr<IPropertyStore> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x180044690`
- end: `0x180044cae`
- name: `?GetMRUIdentifiers@CModernShareCommand@@QEAAJAEBV?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@34@@Z`
- size: `1566`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004fa00`

## callees

- `0x180008900`
- `0x18001bfd8`
- `0x18001d18c`
- `0x18001efc4`
- `0x180020b7c`
- `0x180020f6c`
- `0x180020fb8`
- `0x1800214cc`
- `0x1800222cc`
- `0x1800223bc`
- `0x1800232c4`
- `0x1800254e0`
- `0x18002e7b0`
- `0x180035d9c`
- `0x1800388f4`
- `0x18003a7a8`
- `0x18003c138`
- `0x180044690`
- `0x1800513f4`
- `0x180051598`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004499d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044a34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004499d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044a34`
- `USER32!GetAncestor` at `0x18004476b`
- `USER32!GetAncestor` at `0x18004476b`

## string_xrefs

- `0x180044740`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x1800447e0`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180044846`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004497c`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180044bf7`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CModernShareCommand::GetMRUIdentifiers(__int64 a1, struct IPropertyStore **a2, __int64 *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HWND Ancestor; // r14
  __int64 v9; // rsi
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HWND, GUID *, __int64); // rbx
  int v12; // eax
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rdx
  _QWORD *v15; // rax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  HWND v23; // r9
  unsigned __int64 v24; // rcx
  __int64 v25; // r8
  unsigned __int64 i; // rdx
  __int16 v27; // r10
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rsi
  __int64 (__fastcall *v32)(__int64, __int64, __int64); // rdi
  __int64 v33; // rbx
  int v35; // [rsp+20h] [rbp-49h]
  __int64 v36; // [rsp+30h] [rbp-39h] BYREF
  __int64 v37; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v38[8]; // [rsp+40h] [rbp-29h] BYREF
  HWND hwnd; // [rsp+48h] [rbp-21h] BYREF
  __int64 v40; // [rsp+50h] [rbp-19h] BYREF
  HWND v41; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER string; // [rsp+60h] [rbp-9h] BYREF
  __int64 v43; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  wil::PropertyStoreHelper::PropertyStoreHelper((wil::PropertyStoreHelper *)v38, *a2);
  *(_OWORD *)&string.Reserved.Reserved1 = PKEY_Home_DriveType;
  *(_DWORD *)&string.Reserved.Reserved2[16] = 10;
  v5 = AddStringMRUIdentifiersToJSON(v38, L"driveType", &string, a3);
  v6 = v5;
  if ( v5 >= 0 )
  {
    *(_OWORD *)&string.Reserved.Reserved1 = PKEY_Home_UserOneDriveCid;
    *(_DWORD *)&string.Reserved.Reserved2[16] = 18;
    v5 = AddStringMRUIdentifiersToJSON(v38, L"CID", &string, a3);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = 2569;
      goto LABEL_5;
    }
    hwnd = 0;
    GetWindowFromSite(*(IUnknown **)(a1 + 40), &hwnd);
    Ancestor = GetAncestor(hwnd, 2u);
    v9 = a1 + 168;
    if ( !*(_QWORD *)(a1 + 168) )
    {
      v10 = *(_QWORD *)(a1 + 176);
      v11 = *(__int64 (__fastcall **)(__int64, HWND, GUID *, __int64))(*(_QWORD *)v10 + 24LL);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v9);
      v5 = v11(v10, Ancestor, &GUID_a5caee9b_8708_49d1_8d36_67d25a8da00c, v9);
      v6 = v5;
      if ( v5 < 0 )
      {
        v7 = 2575;
        goto LABEL_5;
      }
    }
    v37 = 0;
    v12 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
            &v37,
            L"%llx",
            (unsigned int)Ancestor);
    v6 = v12;
    if ( v12 < 0 )
    {
      v13 = 2579;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
        (const char *)(unsigned int)v12,
        v35);
LABEL_12:
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v37);
      goto LABEL_65;
    }
    v12 = AddStringToJSON(L"HWND", v37, a3);
    v6 = v12;
    if ( v12 < 0 )
    {
      v13 = 2580;
      goto LABEL_11;
    }
    v36 = 0;
    v15 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                      (HSTRING *)&string,
                      (const unsigned __int16 (*)[29])v14);
    v16 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(*v15, &v36);
    v6 = v16;
    if ( v16 < 0 )
    {
      v17 = 2584;
      goto LABEL_17;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56859762>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56859762>::GetImpl'::`2'::impl) )
    {
      *(GUID *)&string.Reserved.Reserved1 = PKEY_ItemNameDisplayWithoutExtension.fmtid;
      *(_DWORD *)&string.Reserved.Reserved2[16] = PKEY_ItemNameDisplayWithoutExtension.pid;
      v16 = AddStringMRUIdentifiersToJSON(v38, L"itemName", &string, &v36);
      v6 = v16;
      if ( v16 < 0 )
      {
        v17 = 2587;
        goto LABEL_17;
      }
    }
    else
    {
      *(_OWORD *)&string.Reserved.Reserved1 = PKEY_Home_FullName;
      *(_DWORD *)&string.Reserved.Reserved2[16] = 8;
      v16 = AddStringMRUIdentifiersToJSON(v38, L"itemName", &string, &v36);
      v6 = v16;
      if ( v16 < 0 )
      {
        v17 = 2591;
        goto LABEL_17;
      }
    }
    v16 = AddBooleanToJSON(v19, v18, &v36);
    v6 = v16;
    if ( v16 < 0 )
    {
      v17 = 2593;
      goto LABEL_17;
    }
    *(_OWORD *)&string.Reserved.Reserved1 = PKEY_Home_ListId;
    *(_DWORD *)&string.Reserved.Reserved2[16] = 11;
    v16 = AddStringMRUIdentifiersToJSON(v38, L"listId", &string, &v36);
    v6 = v16;
    if ( v16 < 0 )
    {
      v17 = 2594;
      goto LABEL_17;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FE_SharedBackend>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FE_SharedBackend>::GetImpl'::`2'::impl) )
    {
      hwnd = 0;
      v20 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&hwnd);
      *(_OWORD *)&string.Reserved.Reserved1 = PKEY_Home_ListItemUniqueId;
      *(_DWORD *)&string.Reserved.Reserved2[16] = 13;
      v21 = wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(v38, &string, v20);
      v6 = v21;
      if ( v21 < 0 )
      {
        v22 = 2601;
        goto LABEL_31;
      }
      v23 = hwnd;
      v24 = -1;
      do
        ++v24;
      while ( *((_WORD *)hwnd + v24) );
      v25 = 0;
      for ( i = 0; i < v24; ++i )
      {
        v27 = *((_WORD *)v23 + i);
        if ( v27 == 45 )
          ++v25;
        else
          *((_WORD *)v23 + i - v25) = v27;
      }
      *((_WORD *)v23 + v24 - v25) = 0;
      v41 = hwnd;
      v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&string, &v41);
      v21 = AddStringToJSON(L"SpoUniqueId", *(_QWORD *)(v28 + 24), &v36);
      v6 = v21;
      if ( v21 < 0 )
      {
        v22 = 2603;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
          (const char *)(unsigned int)v21,
          v35);
        if ( hwnd )
          CoTaskMemFree(hwnd);
        goto LABEL_18;
      }
      if ( hwnd )
        CoTaskMemFree(hwnd);
    }
    else
    {
      *(_OWORD *)&string.Reserved.Reserved1 = PKEY_Home_ListItemId;
      *(_DWORD *)&string.Reserved.Reserved2[16] = 12;
      v16 = AddStringMRUIdentifiersToJSON(v38, L"listItemId", &string, &v36);
      v6 = v16;
      if ( v16 < 0 )
      {
        v17 = 2607;
        goto LABEL_17;
      }
    }
    *(_OWORD *)&string.Reserved.Reserved1 = PKEY_Home_SiteUrl;
    *(_DWORD *)&string.Reserved.Reserved2[16] = 15;
    v16 = AddStringMRUIdentifiersToJSON(v38, L"siteUrl", &string, &v36);
    v6 = v16;
    if ( v16 >= 0 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56859762>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56859762>::GetImpl'::`2'::impl) )
      {
        *(GUID *)&string.Reserved.Reserved1 = PKEY_ContentUri.fmtid;
        *(_DWORD *)&string.Reserved.Reserved2[16] = PKEY_ContentUri.pid;
        v16 = AddStringMRUIdentifiersToJSON(v38, L"webUrl", &string, &v36);
        v6 = v16;
        if ( v16 < 0 )
        {
          v17 = 2612;
          goto LABEL_17;
        }
      }
      else
      {
        *(_OWORD *)&string.Reserved.Reserved1 = PKEY_Home_WebUrl;
        *(_DWORD *)&string.Reserved.Reserved2[16] = 9;
        v16 = AddStringMRUIdentifiersToJSON(v38, L"webUrl", &string, &v36);
        v6 = v16;
        if ( v16 < 0 )
        {
          v17 = 2616;
          goto LABEL_17;
        }
      }
      *(_OWORD *)&string.Reserved.Reserved1 = PKEY_Home_ListItemUniqueId;
      *(_DWORD *)&string.Reserved.Reserved2[16] = 13;
      v16 = AddStringMRUIdentifiersToJSON(v38, L"listItemUniqueId", &string, &v36);
      v6 = v16;
      if ( v16 >= 0 )
      {
        *(_OWORD *)&string.Reserved.Reserved1 = PKEY_Home_SiteId;
        *(_DWORD *)&string.Reserved.Reserved2[16] = 14;
        v16 = AddStringMRUIdentifiersToJSON(v38, L"siteId", &string, &v36);
        v6 = v16;
        if ( v16 >= 0 )
        {
          *(_OWORD *)&string.Reserved.Reserved1 = PKEY_Home_WebId;
          *(_DWORD *)&string.Reserved.Reserved2[16] = 16;
          v16 = AddStringMRUIdentifiersToJSON(v38, L"webId", &string, &v36);
          v6 = v16;
          if ( v16 >= 0 )
          {
            v40 = 0;
            v29 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
                    &v36,
                    &v40);
            v6 = v29;
            if ( v29 >= 0 )
            {
              v31 = *a3;
              v32 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)*a3 + 56LL);
              v33 = v40;
              v43 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&string, L"itemInfo", 9u, 8u);
              v29 = v32(v31, v43, v33);
              v6 = v29;
              if ( v29 >= 0 )
              {
                Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v40);
                Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v36);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v37);
                v6 = 0;
                goto LABEL_65;
              }
              v30 = 2624;
            }
            else
            {
              v30 = 2623;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v30,
              (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
              (const char *)(unsigned int)v29,
              v35);
            Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v40);
            goto LABEL_18;
          }
          v17 = 2620;
        }
        else
        {
          v17 = 2619;
        }
      }
      else
      {
        v17 = 2618;
      }
      goto LABEL_17;
    }
    v17 = 2609;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v16,
      v35);
LABEL_18:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v36);
    goto LABEL_12;
  }
  v7 = 2568;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
    (const char *)(unsigned int)v5,
    v35);
LABEL_65:
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v38);
  return v6;
}

```

## disassembly

```asm
0x180044690  push    rbp
0x180044692  push    rbx
0x180044693  push    rsi
0x180044694  push    rdi
0x180044695  push    r12
0x180044697  push    r14
0x180044699  push    r15
0x18004469b  lea     rbp, [rsp-27h]
0x1800446a0  sub     rsp, 90h
0x1800446a7  mov     rax, cs:__security_cookie
0x1800446ae  xor     rax, rsp
0x1800446b1  mov     [rbp+57h+var_40], rax
0x1800446b5  mov     r15, r8
0x1800446b8  mov     rdi, rcx
0x1800446bb  mov     rdx, [rdx]; struct IPropertyStore *
0x1800446be  lea     rcx, [rbp+57h+var_80]; this
0x1800446c2  call    ??0PropertyStoreHelper@wil@@QEAA@PEAUIPropertyStore@@@Z; wil::PropertyStoreHelper::PropertyStoreHelper(IPropertyStore *)
0x1800446c7  nop
0x1800446c8  movups  xmm0, cs:PKEY_Home_DriveType
0x1800446cf  movaps  xmmword ptr [rbp+57h+string], xmm0
0x1800446d3  mov     eax, cs:dword_18007E7A8
0x1800446d9  mov     [rbp+57h+var_50], eax
0x1800446dc  mov     r9, r15
0x1800446df  lea     r8, [rbp+57h+string]
0x1800446e3  lea     rdx, aDrivetype; "driveType"
0x1800446ea  lea     rcx, [rbp+57h+var_80]
0x1800446ee  call    ?AddStringMRUIdentifiersToJSON@@YAJAEBVPropertyStoreHelper@wil@@PEAGU_tagpropertykey@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; AddStringMRUIdentifiersToJSON(wil::PropertyStoreHelper const &,ushort *,_tagpropertykey,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800446f3  mov     ebx, eax
0x1800446f5  xor     r12d, r12d
0x1800446f8  test    eax, eax
0x1800446fa  jns     short loc_180044703
0x1800446fc  mov     edx, 0A08h
0x180044701  jmp     short loc_180044739
0x180044703  movups  xmm0, cs:PKEY_Home_UserOneDriveCid
0x18004470a  movaps  xmmword ptr [rbp+57h+string], xmm0
0x18004470e  mov     eax, cs:dword_18007E868
0x180044714  mov     [rbp+57h+var_50], eax
0x180044717  mov     r9, r15
0x18004471a  lea     r8, [rbp+57h+string]
0x18004471e  lea     rdx, aCid; "CID"
0x180044725  lea     rcx, [rbp+57h+var_80]
0x180044729  call    ?AddStringMRUIdentifiersToJSON@@YAJAEBVPropertyStoreHelper@wil@@PEAGU_tagpropertykey@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; AddStringMRUIdentifiersToJSON(wil::PropertyStoreHelper const &,ushort *,_tagpropertykey,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18004472e  mov     ebx, eax
0x180044730  test    eax, eax
0x180044732  jns     short loc_180044751
0x180044734  mov     edx, 0A09h; void *
0x180044739  mov     rcx, [rbp+5Fh]; this
0x18004473d  mov     r9d, eax; char *
0x180044740  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180044747  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004474c  jmp     loc_180044C85
0x180044751  mov     [rbp+57h+hwnd], r12
0x180044755  lea     rdx, [rbp+57h+hwnd]; phwnd
0x180044759  mov     rcx, [rdi+28h]; punk
0x18004475d  call    ?GetWindowFromSite@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; GetWindowFromSite(IUnknown *,HWND__ * *)
0x180044762  mov     edx, 2; gaFlags
0x180044767  mov     rcx, [rbp+57h+hwnd]; hwnd
0x18004476b  call    cs:__imp_GetAncestor
0x180044771  mov     r14, rax
0x180044774  lea     rsi, [rdi+0A8h]
0x18004477b  cmp     [rsi], r12
0x18004477e  jnz     short loc_1800447BE
0x180044780  mov     rdi, [rdi+0B0h]
0x180044787  mov     rdx, [rdi]
0x18004478a  mov     rbx, [rdx+18h]
0x18004478e  mov     rcx, rsi
0x180044791  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180044796  mov     r9, rsi
0x180044799  lea     r8, _GUID_a5caee9b_8708_49d1_8d36_67d25a8da00c
0x1800447a0  mov     rdx, r14
0x1800447a3  mov     rcx, rdi
0x1800447a6  mov     rax, rbx
0x1800447a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447ae  mov     ebx, eax
0x1800447b0  test    eax, eax
0x1800447b2  jns     short loc_1800447BE
0x1800447b4  mov     edx, 0A0Fh
0x1800447b9  jmp     loc_180044739
0x1800447be  mov     [rbp+57h+var_88], r12
0x1800447c2  mov     r8d, r14d
0x1800447c5  lea     rdx, aLlx; "%llx"
0x1800447cc  lea     rcx, [rbp+57h+var_88]
0x1800447d0  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &,ushort const *,...)
0x1800447d5  mov     ebx, eax
0x1800447d7  test    eax, eax
0x1800447d9  jns     short loc_180044802
0x1800447db  mov     edx, 0A13h; void *
0x1800447e0  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x1800447e7  mov     r9d, eax; char *
0x1800447ea  mov     rcx, [rbp+5Fh]; this
0x1800447ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800447f3  nop
0x1800447f4  lea     rcx, [rbp+57h+var_88]
0x1800447f8  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800447fd  jmp     loc_180044C85
0x180044802  mov     r8, r15
0x180044805  mov     rdx, [rbp+57h+var_88]
0x180044809  lea     rcx, aHwnd; "HWND"
0x180044810  call    ?AddStringToJSON@@YAJPEAGPEAUHSTRING__@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; AddStringToJSON(ushort *,HSTRING__ *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180044815  mov     ebx, eax
0x180044817  test    eax, eax
0x180044819  jns     short loc_180044822
0x18004481b  mov     edx, 0A14h
0x180044820  jmp     short loc_1800447E0
0x180044822  mov     [rbp+57h+var_90], r12
0x180044826  lea     rcx, [rbp+57h+string]; string
0x18004482a  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x18004482f  lea     rdx, [rbp+57h+var_90]
0x180044833  mov     rcx, [rax]
0x180044836  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18004483b  mov     ebx, eax
0x18004483d  test    eax, eax
0x18004483f  jns     short loc_180044865
0x180044841  mov     edx, 0A18h; void *
0x180044846  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004484d  mov     r9d, eax; char *
0x180044850  mov     rcx, [rbp+5Fh]; this
0x180044854  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044859  nop
0x18004485a  lea     rcx, [rbp+57h+var_90]
0x18004485e  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180044863  jmp     short loc_1800447F4
0x180044865  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56859762@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56859762@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56859762> `wil::Feature<__WilFeatureTraits_Feature_56859762>::GetImpl(void)'::`2'::impl
0x18004486c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56859762@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56859762>::__private_IsEnabled(wil::ReportingKind)
0x180044871  lea     r9, [rbp+57h+var_90]
0x180044875  lea     r8, [rbp+57h+string]
0x180044879  lea     rdx, aItemname; "itemName"
0x180044880  lea     rcx, [rbp+57h+var_80]
0x180044884  test    al, al
0x180044886  jz      short loc_1800448AE
0x180044888  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplayWithoutExtension.fmtid.Data1
0x18004488f  movaps  xmmword ptr [rbp+57h+string], xmm0
0x180044893  mov     eax, cs:PKEY_ItemNameDisplayWithoutExtension.pid
0x180044899  mov     [rbp+57h+var_50], eax
0x18004489c  call    ?AddStringMRUIdentifiersToJSON@@YAJAEBVPropertyStoreHelper@wil@@PEAGU_tagpropertykey@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; AddStringMRUIdentifiersToJSON(wil::PropertyStoreHelper const &,ushort *,_tagpropertykey,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800448a1  mov     ebx, eax
0x1800448a3  test    eax, eax
0x1800448a5  jns     short loc_1800448D7
0x1800448a7  mov     edx, 0A1Bh
0x1800448ac  jmp     short loc_180044846
0x1800448ae  movups  xmm0, cs:PKEY_Home_FullName
0x1800448b5  movaps  xmmword ptr [rbp+57h+string], xmm0
0x1800448b9  mov     eax, cs:dword_18007E7C0
0x1800448bf  mov     [rbp+57h+var_50], eax
0x1800448c2  call    ?AddStringMRUIdentifiersToJSON@@YAJAEBVPropertyStoreHelper@wil@@PEAGU_tagpropertykey@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; AddStringMRUIdentifiersToJSON(wil::PropertyStoreHelper const &,ushort *,_tagpropertykey,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800448c7  mov     ebx, eax
0x1800448c9  test    eax, eax
0x1800448cb  jns     short loc_1800448D7
0x1800448cd  mov     edx, 0A1Fh
0x1800448d2  jmp     loc_180044846
0x1800448d7  lea     r8, [rbp+57h+var_90]
0x1800448db  call    ?AddBooleanToJSON@@YAJPEAG_NAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; AddBooleanToJSON(ushort *,bool,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800448e0  mov     ebx, eax
0x1800448e2  test    eax, eax
0x1800448e4  jns     short loc_1800448F0
0x1800448e6  mov     edx, 0A21h
0x1800448eb  jmp     loc_180044846
0x1800448f0  movups  xmm0, cs:PKEY_Home_ListId
0x1800448f7  movaps  xmmword ptr [rbp+57h+string], xmm0
0x1800448fb  mov     eax, cs:dword_18007E7F0
0x180044901  mov     [rbp+57h+var_50], eax
0x180044904  lea     r9, [rbp+57h+var_90]
0x180044908  lea     r8, [rbp+57h+string]
0x18004490c  lea     rdx, aListid; "listId"
0x180044913  lea     rcx, [rbp+57h+var_80]
0x180044917  call    ?AddStringMRUIdentifiersToJSON@@YAJAEBVPropertyStoreHelper@wil@@PEAGU_tagpropertykey@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; AddStringMRUIdentifiersToJSON(wil::PropertyStoreHelper const &,ushort *,_tagpropertykey,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18004491c  mov     ebx, eax
0x18004491e  test    eax, eax
0x180044920  jns     short loc_18004492C
0x180044922  mov     edx, 0A22h
0x180044927  jmp     loc_180044846
0x18004492c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FE_SharedBackend@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FE_SharedBackend@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FE_SharedBackend> `wil::Feature<__WilFeatureTraits_Feature_FE_SharedBackend>::GetImpl(void)'::`2'::impl
0x180044933  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FE_SharedBackend@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FE_SharedBackend>::__private_IsEnabled(void)
0x180044938  test    al, al
0x18004493a  jz      loc_180044A76
0x180044940  mov     [rbp+57h+hwnd], r12
0x180044944  lea     rcx, [rbp+57h+hwnd]
0x180044948  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18004494d  movups  xmm0, cs:PKEY_Home_ListItemUniqueId
0x180044954  movaps  xmmword ptr [rbp+57h+string], xmm0
0x180044958  mov     ecx, cs:dword_18007E820
0x18004495e  mov     [rbp+57h+var_50], ecx
0x180044961  mov     r8, rax
0x180044964  lea     rdx, [rbp+57h+string]
0x180044968  lea     rcx, [rbp+57h+var_80]
0x18004496c  call    ??$GetString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180044971  mov     ebx, eax
0x180044973  test    eax, eax
0x180044975  jns     short loc_1800449A8
0x180044977  mov     edx, 0A29h; void *
0x18004497c  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180044983  mov     r9d, eax; char *
0x180044986  mov     rcx, [rbp+5Fh]; this
0x18004498a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004498f  nop
0x180044990  mov     rcx, [rbp+57h+hwnd]; pv
0x180044994  test    rcx, rcx
0x180044997  jz      loc_18004485A
0x18004499d  call    cs:__imp_CoTaskMemFree
0x1800449a3  jmp     loc_18004485A
0x1800449a8  mov     r9, [rbp+57h+hwnd]
0x1800449ac  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800449b0  inc     rcx
0x1800449b3  cmp     [r9+rcx*2], r12w
0x1800449b8  jnz     short loc_1800449B0
0x1800449ba  mov     r8, r12
0x1800449bd  mov     rdx, r12
0x1800449c0  test    rcx, rcx
0x1800449c3  jz      short loc_1800449E9
0x1800449c5  movzx   r10d, word ptr [r9+rdx*2]
0x1800449ca  cmp     r10w, 2Dh ; '-'
0x1800449cf  jz      short loc_1800449DE
0x1800449d1  mov     rax, rdx
0x1800449d4  sub     rax, r8
0x1800449d7  mov     [r9+rax*2], r10w
0x1800449dc  jmp     short loc_1800449E1
0x1800449de  inc     r8
0x1800449e1  inc     rdx
0x1800449e4  cmp     rdx, rcx
0x1800449e7  jb      short loc_1800449C5
0x1800449e9  sub     rcx, r8
0x1800449ec  mov     [r9+rcx*2], r12w
0x1800449f1  mov     rax, [rbp+57h+hwnd]
0x1800449f5  mov     [rbp+57h+var_68], rax
0x1800449f9  lea     rdx, [rbp+57h+var_68]
0x1800449fd  lea     rcx, [rbp+57h+string]
0x180044a01  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180044a06  nop
0x180044a07  lea     r8, [rbp+57h+var_90]
0x180044a0b  mov     rdx, [rax+18h]
0x180044a0f  lea     rcx, aSpouniqueid; "SpoUniqueId"
0x180044a16  call    ?AddStringToJSON@@YAJPEAGPEAUHSTRING__@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; AddStringToJSON(ushort *,HSTRING__ *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180044a1b  mov     ebx, eax
0x180044a1d  test    eax, eax
0x180044a1f  jns     short loc_180044A2B
0x180044a21  mov     edx, 0A2Bh
0x180044a26  jmp     loc_18004497C
0x180044a2b  mov     rcx, [rbp+57h+hwnd]; pv
0x180044a2f  test    rcx, rcx
0x180044a32  jz      short loc_180044A3A
0x180044a34  call    cs:__imp_CoTaskMemFree
0x180044a3a  movups  xmm0, cs:PKEY_Home_SiteUrl
0x180044a41  movaps  xmmword ptr [rbp+57h+string], xmm0
0x180044a45  mov     eax, cs:dword_18007E850
0x180044a4b  mov     [rbp+57h+var_50], eax
0x180044a4e  lea     r9, [rbp+57h+var_90]
0x180044a52  lea     r8, [rbp+57h+string]
0x180044a56  lea     rdx, aSiteurl; "siteUrl"
0x180044a5d  lea     rcx, [rbp+57h+var_80]
0x180044a61  call    ?AddStringMRUIdentifiersToJSON@@YAJAEBVPropertyStoreHelper@wil@@PEAGU_tagpropertykey@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; AddStringMRUIdentifiersToJSON(wil::PropertyStoreHelper const &,ushort *,_tagpropertykey,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180044a66  mov     ebx, eax
0x180044a68  test    eax, eax
0x180044a6a  jns     short loc_180044AB2
0x180044a6c  mov     edx, 0A31h
0x180044a71  jmp     loc_180044846
0x180044a76  movups  xmm0, cs:PKEY_Home_ListItemId
0x180044a7d  movaps  xmmword ptr [rbp+57h+string], xmm0
0x180044a81  mov     eax, cs:dword_18007E808
0x180044a87  mov     [rbp+57h+var_50], eax
0x180044a8a  lea     r9, [rbp+57h+var_90]
0x180044a8e  lea     r8, [rbp+57h+string]
0x180044a92  lea     rdx, aListitemid; "listItemId"
0x180044a99  lea     rcx, [rbp+57h+var_80]
0x180044a9d  call    ?AddStringMRUIdentifiersToJSON@@YAJAEBVPropertyStoreHelper@wil@@PEAGU_tagpropertykey@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; AddStringMRUIdentifiersToJSON(wil::PropertyStoreHelper const &,ushort *,_tagpropertykey,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180044aa2  mov     ebx, eax
0x180044aa4  test    eax, eax
0x180044aa6  jns     short loc_180044A3A
0x180044aa8  mov     edx, 0A2Fh
0x180044aad  jmp     loc_180044846
0x180044ab2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56859762@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56859762@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56859762> `wil::Feature<__WilFeatureTraits_Feature_56859762>::GetImpl(void)'::`2'::impl
0x180044ab9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56859762@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56859762>::__private_IsEnabled(wil::ReportingKind)
0x180044abe  lea     r9, [rbp+57h+var_90]
0x180044ac2  lea     r8, [rbp+57h+string]
0x180044ac6  lea     rdx, aWeburl; "webUrl"
0x180044acd  lea     rcx, [rbp+57h+var_80]
0x180044ad1  test    al, al
0x180044ad3  jz      short loc_180044AFE
0x180044ad5  movups  xmm0, xmmword ptr cs:PKEY_ContentUri.fmtid.Data1
0x180044adc  movaps  xmmword ptr [rbp+57h+string], xmm0
0x180044ae0  mov     eax, cs:PKEY_ContentUri.pid
0x180044ae6  mov     [rbp+57h+var_50], eax
0x180044ae9  call    ?AddStringMRUIdentifiersToJSON@@YAJAEBVPropertyStoreHelper@wil@@PEAGU_tagpropertykey@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; AddStringMRUIdentifiersToJSON(wil::PropertyStoreHelper const &,ushort *,_tagpropertykey,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180044aee  mov     ebx, eax
0x180044af0  test    eax, eax
0x180044af2  jns     short loc_180044B27
0x180044af4  mov     edx, 0A34h
0x180044af9  jmp     loc_180044846
0x180044afe  movups  xmm0, cs:PKEY_Home_WebUrl
0x180044b05  movaps  xmmword ptr [rbp+57h+string], xmm0
0x180044b09  mov     eax, cs:dword_18007E898
0x180044b0f  mov     [rbp+57h+var_50], eax
0x180044b12  call    ?AddStringMRUIdentifiersToJSON@@YAJAEBVPropertyStoreHelper@wil@@PEAGU_tagpropertykey@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; AddStringMRUIdentifiersToJSON(wil::PropertyStoreHelper const &,ushort *,_tagpropertykey,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180044b17  mov     ebx, eax
0x180044b19  test    eax, eax
0x180044b1b  jns     short loc_180044B27
0x180044b1d  mov     edx, 0A38h
0x180044b22  jmp     loc_180044846
0x180044b27  movups  xmm0, cs:PKEY_Home_ListItemUniqueId
0x180044b2e  movaps  xmmword ptr [rbp+57h+string], xmm0
0x180044b32  mov     eax, cs:dword_18007E820
  ... truncated ...
```
