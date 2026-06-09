# CRetailDemoPlugin::ExecuteFinalMandatoryTasks(void)

- ea: `0x18004d450`
- end: `0x18004d66b`
- name: `?ExecuteFinalMandatoryTasks@CRetailDemoPlugin@@UEAAJXZ`
- size: `539`
- prototype: `__int64 __fastcall(CRetailDemoPlugin *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800022c8`
- `0x180003470`
- `0x180007bbc`
- `0x180008544`
- `0x18001bf7c`
- `0x18001de58`
- `0x18001e9a4`
- `0x180023574`
- `0x18004d450`
- `0x18004e990`
- `0x1800b8834`
- `0x1800bf2ac`
- `0x1800bf630`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004d542`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004d542`
- `api-ms-win-core-localization-l1-2-2!GetSystemDefaultLocaleName` at `0x18004d4eb`
- `api-ms-win-core-localization-l1-2-2!GetSystemDefaultLocaleName` at `0x18004d4eb`

## string_xrefs

- `0x18004d5e3`: `Failed to configure retail demo service to autostart. [hr=0x%08X]`
- `0x18004d640`: `Failed to create retaildemo folder delete scheduled task hr=0x%08X`
- `0x18004d5aa`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRetailDemoPlugin::ExecuteFinalMandatoryTasks(struct IOOBERunnableTask **this)
{
  int v2; // edi
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  const struct _tlgProvider_t *v7; // rax
  int v8; // r8d
  int v9; // r9d
  struct IOOBERunnableTask *v10; // rdx
  int v11; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  LPCWCH lpString2; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR LocaleName[88]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  if ( !(*((unsigned int (__fastcall **)(char *))this[3] + 3))((char *)this + 24) )
  {
    v14 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    v2 = ConfigureRetailDemoInternal_CreateInstance(0, &GUID_0e64bb19_ed60_458d_a97f_e65843ad2bc2, &v14);
    if ( v2 < 0
      || (v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v14 + 24LL))(
                 v14,
                 *((_DWORD *)this + 3) & 2,
                 0,
                 0),
          v2 < 0) )
    {
      UnattendLogW(1, L"Failed to configure retail demo service to autostart. [hr=0x%08X]", (unsigned int)v2);
    }
    else if ( GetSystemDefaultLocaleName(LocaleName, 85) )
    {
      lpString2 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &lpString2,
        0);
      if ( CBasePlugin::_GetGlobalSettingString((CBasePlugin *)this, L"LOCALE", (unsigned __int16 **)&lpString2) >= 0
        && CompareStringOrdinal(LocaleName, -1, lpString2, -1, 1) != 2 )
      {
        v3 = SHRegSetString(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\RetailInfo",
               L"Language",
               lpString2);
        v4 = v3;
        if ( v3 < 0 )
        {
          v5 = 115;
LABEL_11:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v5,
            (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
            (const char *)(unsigned int)v3,
            bIgnoreCase);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString2);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
          return v4;
        }
        v3 = SHRegSetString(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\RetailInfo",
               L"original_Language",
               lpString2);
        v4 = v3;
        if ( v3 < 0 )
        {
          v5 = 116;
          goto LABEL_11;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString2);
    }
    v7 = OOBELogging::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      LODWORD(lpString2) = v2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (_DWORD)v7,
        (unsigned int)&dword_1800FF9DC,
        v8,
        v9,
        (__int64)&lpString2);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  }
  v10 = this[4];
  if ( v10 )
  {
    v11 = CBasePlugin::_WaitForTaskToComplete((CBasePlugin *)this, v10);
    if ( v11 < 0 )
      UnattendLogW(1, L"Failed to create retaildemo folder delete scheduled task hr=0x%08X", (unsigned int)v11);
  }
  return 0;
}

```

## disassembly

```asm
0x18004d450  push    rbp
0x18004d452  push    rbx
0x18004d453  push    rsi
0x18004d454  push    rdi
0x18004d455  lea     rbp, [rsp-8]
0x18004d45a  sub     rsp, 108h
0x18004d461  mov     rax, cs:__security_cookie
0x18004d468  xor     rax, rsp
0x18004d46b  mov     [rbp+20h+var_30], rax
0x18004d46f  mov     rsi, rcx
0x18004d472  add     rcx, 18h
0x18004d476  mov     rax, [rcx]
0x18004d479  mov     rax, [rax+18h]
0x18004d47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d482  test    eax, eax
0x18004d484  jnz     loc_18004D628
0x18004d48a  mov     [rsp+120h+var_E8], 0
0x18004d493  lea     rcx, [rsp+120h+var_E8]
0x18004d498  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d49d  lea     r8, [rsp+120h+var_E8]
0x18004d4a2  lea     rdx, _GUID_0e64bb19_ed60_458d_a97f_e65843ad2bc2
0x18004d4a9  xor     ecx, ecx
0x18004d4ab  call    ConfigureRetailDemoInternal_CreateInstance
0x18004d4b0  mov     edi, eax
0x18004d4b2  test    eax, eax
0x18004d4b4  js      loc_18004D5E0
0x18004d4ba  mov     rcx, [rsp+120h+var_E8]
0x18004d4bf  mov     rax, [rcx]
0x18004d4c2  mov     edx, [rsi+0Ch]
0x18004d4c5  and     edx, 2
0x18004d4c8  xor     r9d, r9d
0x18004d4cb  xor     r8d, r8d
0x18004d4ce  mov     rax, [rax+18h]
0x18004d4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4d7  mov     edi, eax
0x18004d4d9  test    eax, eax
0x18004d4db  js      loc_18004D5E0
0x18004d4e1  mov     edx, 55h ; 'U'; cchLocaleName
0x18004d4e6  lea     rcx, [rsp+120h+LocaleName]; lpLocaleName
0x18004d4eb  call    cs:__imp_GetSystemDefaultLocaleName
0x18004d4f1  test    eax, eax
0x18004d4f3  jz      loc_18004D5F4
0x18004d4f9  mov     [rsp+120h+lpString2], 0
0x18004d502  xor     edx, edx
0x18004d504  lea     rcx, [rsp+120h+lpString2]
0x18004d509  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004d50e  lea     r8, [rsp+120h+lpString2]; unsigned __int16 **
0x18004d513  lea     rdx, aLocale_0; "LOCALE"
0x18004d51a  mov     rcx, rsi; this
0x18004d51d  call    ?_GetGlobalSettingString@CBasePlugin@@IEAAJPEBGPEAPEAG@Z; CBasePlugin::_GetGlobalSettingString(ushort const *,ushort * *)
0x18004d522  test    eax, eax
0x18004d524  js      loc_18004D5D4
0x18004d52a  mov     [rsp+120h+bIgnoreCase], 1; int
0x18004d532  or      edx, 0FFFFFFFFh; cchCount1
0x18004d535  mov     r9d, edx; cchCount2
0x18004d538  mov     r8, [rsp+120h+lpString2]; lpString2
0x18004d53d  lea     rcx, [rsp+120h+LocaleName]; lpString1
0x18004d542  call    cs:__imp_CompareStringOrdinal
0x18004d548  cmp     eax, 2
0x18004d54b  jz      loc_18004D5D4
0x18004d551  mov     r9, [rsp+120h+lpString2]; unsigned __int16 *
0x18004d556  lea     r8, aLanguage; "Language"
0x18004d55d  lea     rdx, ?c_retailDemoKeyRetailInfo@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004d564  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18004d56b  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18004d570  mov     ebx, eax
0x18004d572  test    eax, eax
0x18004d574  jns     short loc_18004D57D
0x18004d576  mov     edx, 73h ; 's'
0x18004d57b  jmp     short loc_18004D5A7
0x18004d57d  mov     r9, [rsp+120h+lpString2]; unsigned __int16 *
0x18004d582  lea     r8, aOriginalLangua; "original_Language"
0x18004d589  lea     rdx, ?c_retailDemoKeyRetailInfo@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004d590  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18004d597  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18004d59c  mov     ebx, eax
0x18004d59e  test    eax, eax
0x18004d5a0  jns     short loc_18004D5D4
0x18004d5a2  mov     edx, 74h ; 't'; void *
0x18004d5a7  mov     r9d, eax; char *
0x18004d5aa  lea     r8, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004d5b1  mov     rcx, [rbp+28h]; this
0x18004d5b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d5ba  nop
0x18004d5bb  lea     rcx, [rsp+120h+lpString2]
0x18004d5c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004d5c5  nop
0x18004d5c6  lea     rcx, [rsp+120h+var_E8]
0x18004d5cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d5d0  mov     eax, ebx
0x18004d5d2  jmp     short loc_18004D653
0x18004d5d4  lea     rcx, [rsp+120h+lpString2]
0x18004d5d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004d5de  jmp     short loc_18004D5F4
0x18004d5e0  mov     r8d, edi
0x18004d5e3  lea     rdx, aFailedToConfig; "Failed to configure retail demo service"...
0x18004d5ea  mov     ecx, 1
0x18004d5ef  call    UnattendLogW
0x18004d5f4  call    ?Provider@OOBELogging@@SAPEBU_tlgProvider_t@@XZ; OOBELogging::Provider(void)
0x18004d5f9  mov     ecx, [rax]
0x18004d5fb  cmp     ecx, 5
0x18004d5fe  jbe     short loc_18004D61E
0x18004d600  mov     dword ptr [rsp+120h+lpString2], edi
0x18004d604  lea     rcx, [rsp+120h+lpString2]
0x18004d609  mov     qword ptr [rsp+120h+bIgnoreCase], rcx
0x18004d60e  lea     rdx, dword_1800FF9DC
0x18004d615  mov     rcx, rax
0x18004d618  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004d61d  nop
0x18004d61e  lea     rcx, [rsp+120h+var_E8]
0x18004d623  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d628  mov     rdx, [rsi+20h]; struct IOOBERunnableTask *
0x18004d62c  test    rdx, rdx
0x18004d62f  jz      short loc_18004D651
0x18004d631  mov     rcx, rsi; this
0x18004d634  call    ?_WaitForTaskToComplete@CBasePlugin@@IEAAJPEAUIOOBERunnableTask@@@Z; CBasePlugin::_WaitForTaskToComplete(IOOBERunnableTask *)
0x18004d639  test    eax, eax
0x18004d63b  jns     short loc_18004D651
0x18004d63d  mov     r8d, eax
0x18004d640  lea     rdx, aFailedToCreate_5; "Failed to create retaildemo folder dele"...
0x18004d647  mov     ecx, 1
0x18004d64c  call    UnattendLogW
0x18004d651  xor     eax, eax
0x18004d653  mov     rcx, [rbp+20h+var_30]
0x18004d657  xor     rcx, rsp; StackCookie
0x18004d65a  call    __security_check_cookie
0x18004d65f  add     rsp, 108h
0x18004d666  pop     rdi
0x18004d667  pop     rsi
0x18004d668  pop     rbx
0x18004d669  pop     rbp
0x18004d66a  retn
```
