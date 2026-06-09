# GetLoopParameters(ulong *,ulong *)

- ea: `0x18001984c`
- end: `0x180019a53`
- name: `?GetLoopParameters@@YAJPEAK0@Z`
- size: `519`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ef18`

## callees

- `0x18000e1a0`
- `0x180013770`
- `0x18001984c`
- `0x180019a5c`
- `0x180019ab0`
- `0x180019f74`
- `0x180022440`
- `0x180030ad0`
- `0x180032894`
- `0x180032900`
- `0x1800463cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019950`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019950`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019916`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019983`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019916`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019983`

## string_xrefs

- `0x1800198df`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180019966`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800199b8`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800199f6`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall GetLoopParameters(unsigned int *a1, unsigned int *a2)
{
  __int64 v4; // rcx
  int UserProfileListRootKeyName; // eax
  unsigned int v6; // ebx
  HKEY v7; // rbx
  LSTATUS v8; // eax
  unsigned int DWORD; // eax
  unsigned int v11; // eax
  unsigned int v12; // ecx
  int phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-20h] BYREF
  __int64 v16; // [rsp+38h] [rbp-18h]
  __int64 v17; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HKEY hKey; // [rsp+70h] [rbp+20h] BYREF
  char v20; // [rsp+78h] [rbp+28h] BYREF

  *a1 = 50;
  *a2 = 100;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetImpl'::`2'::impl) == 1
    || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetImpl'::`2'::impl) == 2 )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetCachedVariantState(
      v4,
      &hKey);
    v12 = HIWORD(HIDWORD(hKey));
    *a1 = WORD2(hKey);
    *a2 = v12;
  }
  else
  {
    lpSubKey = 0;
    v16 = 0;
    v17 = 0;
    hKey = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
    v16 = -1;
    v17 = -1;
    UserProfileListRootKeyName = GetUserProfileListRootKeyName((unsigned __int16 **)&lpSubKey, 0);
    v6 = UserProfileListRootKeyName;
    if ( UserProfileListRootKeyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51C,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)UserProfileListRootKeyName,
        phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_10:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
      return v6;
    }
    v7 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v20);
      RegCloseKey(v7);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v20);
    }
    hKey = 0;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51D,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v8,
        phkResulta);
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_10;
    }
    DWORD = SHRegGetDWORD(hKey, 0, L"LoadIterations", a1);
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0x520,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)DWORD,
      1,
      0x80070002);
    v11 = SHRegGetDWORD(hKey, 0, L"LoadDelayMS", a2);
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0x521,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)v11,
      1,
      0x80070002);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  }
  return 0;
}

```

## disassembly

```asm
0x18001984c  mov     [rsp-18h+arg_10], rbx
0x180019851  push    rbp
0x180019852  push    rsi
0x180019853  push    rdi
0x180019854  mov     rbp, rsp
0x180019857  sub     rsp, 50h
0x18001985b  mov     dword ptr [rcx], 32h ; '2'
0x180019861  mov     rdi, rdx
0x180019864  mov     dword ptr [rdx], 64h ; 'd'
0x18001986a  mov     rsi, rcx
0x18001986d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetImpl(void)'::`2'::impl
0x180019874  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@details@wil@@QEAA?AW4Variant_Profile_Service_Retry_Load_Loop@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180019879  cmp     al, 1
0x18001987b  jz      loc_180019A2A
0x180019881  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetImpl(void)'::`2'::impl
0x180019888  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@details@wil@@QEAA?AW4Variant_Profile_Service_Retry_Load_Loop@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::__private_GetVariant(wil::VariantReportingKind,bool)
0x18001988d  cmp     al, 2
0x18001988f  jz      loc_180019A2A
0x180019895  lea     rcx, [rbp+lpSubKey]
0x180019899  mov     [rbp+lpSubKey], 0
0x1800198a1  mov     [rbp+var_18], 0
0x1800198a9  mov     [rbp+var_10], 0
0x1800198b1  mov     [rbp+hKey], 0
0x1800198b9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800198be  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800198c2  lea     rcx, [rbp+lpSubKey]; unsigned __int16 **
0x1800198c6  xor     edx, edx; int *
0x1800198c8  mov     [rbp+var_18], rax
0x1800198cc  mov     [rbp+var_10], rax
0x1800198d0  call    ?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z; GetUserProfileListRootKeyName(ushort * *,int *)
0x1800198d5  mov     ebx, eax
0x1800198d7  test    eax, eax
0x1800198d9  jns     short loc_180019901
0x1800198db  mov     rcx, [rbp+18h]; this
0x1800198df  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800198e6  mov     r9d, eax; char *
0x1800198e9  mov     edx, 51Ch; void *
0x1800198ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800198f3  lea     rcx, [rbp+hKey]
0x1800198f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800198fc  jmp     loc_18001998F
0x180019901  mov     rbx, [rbp+hKey]
0x180019905  test    rbx, rbx
0x180019908  jz      short loc_18001992B
0x18001990a  lea     rcx, [rbp+arg_8]; this
0x18001990e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180019913  mov     rcx, rbx; hKey
0x180019916  call    cs:__imp_RegCloseKey
0x18001991d  nop     dword ptr [rax+rax+00h]
0x180019922  lea     rcx, [rbp+arg_8]; this
0x180019926  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001992b  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001992f  lea     rax, [rbp+hKey]
0x180019933  mov     r9d, 20019h; samDesired
0x180019939  mov     [rsp+50h+phkResult], rax; int
0x18001993e  xor     r8d, r8d; ulOptions
0x180019941  mov     [rbp+hKey], 0
0x180019949  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019950  call    cs:__imp_RegOpenKeyExW
0x180019957  nop     dword ptr [rax+rax+00h]
0x18001995c  mov     ebx, eax
0x18001995e  test    eax, eax
0x180019960  jns     short loc_18001999F
0x180019962  mov     rcx, [rbp+18h]; this
0x180019966  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001996d  mov     r9d, eax; char *
0x180019970  mov     edx, 51Dh; void *
0x180019975  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001997a  mov     rcx, [rbp+hKey]; hKey
0x18001997e  test    rcx, rcx
0x180019981  jz      short loc_18001998F
0x180019983  call    cs:__imp_RegCloseKey
0x18001998a  nop     dword ptr [rax+rax+00h]
0x18001998f  lea     rcx, [rbp+lpSubKey]
0x180019993  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180019998  mov     eax, ebx
0x18001999a  jmp     loc_180019A42
0x18001999f  mov     rcx, [rbp+hKey]; HKEY
0x1800199a3  lea     r8, aLoaditerations; "LoadIterations"
0x1800199aa  mov     r9, rsi; unsigned int *
0x1800199ad  xor     edx, edx; unsigned __int16 *
0x1800199af  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800199b4  mov     rcx, [rbp+18h]; this
0x1800199b8  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800199bf  mov     ebx, 80070002h
0x1800199c4  mov     r9d, eax; char *
0x1800199c7  mov     [rsp+50h+var_28], ebx; unsigned int
0x1800199cb  mov     edx, 520h; void *
0x1800199d0  mov     dword ptr [rsp+50h+phkResult], 1; int
0x1800199d8  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x1800199dd  mov     rcx, [rbp+hKey]; HKEY
0x1800199e1  lea     r8, aLoaddelayms; "LoadDelayMS"
0x1800199e8  mov     r9, rdi; unsigned int *
0x1800199eb  xor     edx, edx; unsigned __int16 *
0x1800199ed  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800199f2  mov     rcx, [rbp+18h]; this
0x1800199f6  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800199fd  mov     r9d, eax; char *
0x180019a00  mov     [rsp+50h+var_28], ebx; unsigned int
0x180019a04  mov     edx, 521h; void *
0x180019a09  mov     dword ptr [rsp+50h+phkResult], 1; int
0x180019a11  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180019a16  lea     rcx, [rbp+hKey]
0x180019a1a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180019a1f  lea     rcx, [rbp+lpSubKey]
0x180019a23  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180019a28  jmp     short loc_180019A40
0x180019a2a  lea     rdx, [rbp+hKey]
0x180019a2e  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetCachedVariantState(void)
0x180019a33  mov     ecx, dword ptr [rbp+hKey+4]
0x180019a36  movzx   eax, cx
0x180019a39  shr     ecx, 10h
0x180019a3c  mov     [rsi], eax
0x180019a3e  mov     [rdi], ecx
0x180019a40  xor     eax, eax
0x180019a42  mov     rbx, [rsp+50h+arg_10]
0x180019a4a  add     rsp, 50h
0x180019a4e  pop     rdi
0x180019a4f  pop     rsi
0x180019a50  pop     rbp
0x180019a51  retn
```
