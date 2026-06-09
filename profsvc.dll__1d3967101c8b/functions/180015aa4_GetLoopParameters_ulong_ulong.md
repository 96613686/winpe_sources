# GetLoopParameters(ulong *,ulong *)

- ea: `0x180015aa4`
- end: `0x180015ca9`
- name: `?GetLoopParameters@@YAJPEAK0@Z`
- size: `517`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002fc50`

## callees

- `0x1800053a0`
- `0x1800111a0`
- `0x180015aa4`
- `0x180015cb0`
- `0x180015d00`
- `0x18001613c`
- `0x1800164e0`
- `0x18002d2d8`
- `0x180030e58`
- `0x180030ebc`
- `0x18004448c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015ba3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015ba3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015b41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015b6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015bd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015c6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015b41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015b6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015bd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015c6a`

## string_xrefs

- `0x180015b24`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180015bb3`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180015c03`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180015c41`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall GetLoopParameters(unsigned int *a1, unsigned int *a2)
{
  __int64 v4; // rcx
  int UserProfileListRootKeyName; // eax
  unsigned int v6; // ebx
  HKEY v8; // rbx
  LPCWSTR v9; // rbx
  LSTATUS v10; // eax
  unsigned int v11; // edi
  unsigned int DWORD; // eax
  unsigned int v13; // eax
  unsigned int v14; // ecx
  int phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKey[4]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HKEY hKey; // [rsp+70h] [rbp+20h] BYREF
  char v20; // [rsp+78h] [rbp+28h] BYREF

  *a1 = 50;
  *a2 = 100;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::__private_GetVariant((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetImpl'::`2'::impl) == 1
    || wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::__private_GetVariant((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetImpl'::`2'::impl) == 2 )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetCachedVariantState(
      v4,
      &hKey);
    v14 = HIWORD(HIDWORD(hKey));
    *a1 = WORD2(hKey);
    *a2 = v14;
    return 0;
  }
  lpSubKey[0] = 0;
  lpSubKey[1] = (LPCWSTR)-1LL;
  lpSubKey[2] = (LPCWSTR)-1LL;
  hKey = 0;
  UserProfileListRootKeyName = GetUserProfileListRootKeyName((unsigned __int16 **)lpSubKey, 0);
  v6 = UserProfileListRootKeyName;
  if ( UserProfileListRootKeyName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)UserProfileListRootKeyName,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
    return v6;
  }
  v8 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v20);
    RegCloseKey(v8);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v20);
  }
  v9 = lpSubKey[0];
  hKey = 0;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey);
  v11 = v10;
  if ( v10 >= 0 )
  {
    DWORD = SHRegGetDWORD(hKey, 0, L"LoadIterations", a1);
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0x520,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)DWORD,
      1,
      0x80070002);
    v13 = SHRegGetDWORD(hKey, 0, L"LoadDelayMS", a2);
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0x521,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)v13,
      1,
      0x80070002);
    if ( hKey )
      RegCloseKey(hKey);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x51D,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)(unsigned int)v10,
    phkResulta);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v9 )
    Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v9);
  return v11;
}

```

## disassembly

```asm
0x180015aa4  mov     [rsp-18h+arg_10], rbx
0x180015aa9  mov     [rsp-18h+arg_18], rsi
0x180015aae  push    rbp
0x180015aaf  push    rdi
0x180015ab0  push    r14
0x180015ab2  mov     rbp, rsp
0x180015ab5  sub     rsp, 50h
0x180015ab9  mov     dword ptr [rcx], 32h ; '2'
0x180015abf  mov     rsi, rdx
0x180015ac2  mov     dword ptr [rdx], 64h ; 'd'
0x180015ac8  mov     r14, rcx
0x180015acb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetImpl(void)'::`2'::impl
0x180015ad2  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@details@wil@@QEAA?AW4Variant_Profile_Service_Retry_Load_Loop@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180015ad7  cmp     al, 1
0x180015ad9  jz      loc_180015C7B
0x180015adf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetImpl(void)'::`2'::impl
0x180015ae6  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@details@wil@@QEAA?AW4Variant_Profile_Service_Retry_Load_Loop@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180015aeb  cmp     al, 2
0x180015aed  jz      loc_180015C7B
0x180015af3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015af7  mov     [rbp+lpSubKey], 0
0x180015aff  xor     edx, edx; int *
0x180015b01  mov     [rbp+var_18], rax
0x180015b05  lea     rcx, [rbp+lpSubKey]; unsigned __int16 **
0x180015b09  mov     [rbp+var_10], rax
0x180015b0d  mov     [rbp+hKey], 0
0x180015b15  call    ?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z; GetUserProfileListRootKeyName(ushort * *,int *)
0x180015b1a  mov     ebx, eax
0x180015b1c  test    eax, eax
0x180015b1e  jns     short loc_180015B57
0x180015b20  mov     rcx, [rbp+18h]; this
0x180015b24  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180015b2b  mov     r9d, eax; char *
0x180015b2e  mov     edx, 51Ch; void *
0x180015b33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015b38  mov     rcx, [rbp+hKey]; hKey
0x180015b3c  test    rcx, rcx
0x180015b3f  jz      short loc_180015B47
0x180015b41  call    cs:__imp_RegCloseKey
0x180015b47  lea     rcx, [rbp+lpSubKey]
0x180015b4b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180015b50  mov     eax, ebx
0x180015b52  jmp     loc_180015C94
0x180015b57  mov     rbx, [rbp+hKey]
0x180015b5b  test    rbx, rbx
0x180015b5e  jz      short loc_180015B7B
0x180015b60  lea     rcx, [rbp+arg_8]; this
0x180015b64  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180015b69  mov     rcx, rbx; hKey
0x180015b6c  call    cs:__imp_RegCloseKey
0x180015b72  lea     rcx, [rbp+arg_8]; this
0x180015b76  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180015b7b  mov     rbx, [rbp+lpSubKey]
0x180015b7f  lea     rax, [rbp+hKey]
0x180015b83  mov     rdx, rbx; lpSubKey
0x180015b86  mov     [rbp+hKey], 0
0x180015b8e  mov     r9d, 20019h; samDesired
0x180015b94  mov     [rsp+50h+phkResult], rax; int
0x180015b99  xor     r8d, r8d; ulOptions
0x180015b9c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015ba3  call    cs:__imp_RegOpenKeyExW
0x180015ba9  mov     edi, eax
0x180015bab  test    eax, eax
0x180015bad  jns     short loc_180015BEA
0x180015baf  mov     rcx, [rbp+18h]; this
0x180015bb3  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180015bba  mov     r9d, eax; char *
0x180015bbd  mov     edx, 51Dh; void *
0x180015bc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015bc7  mov     rcx, [rbp+hKey]; hKey
0x180015bcb  test    rcx, rcx
0x180015bce  jz      short loc_180015BD6
0x180015bd0  call    cs:__imp_RegCloseKey
0x180015bd6  test    rbx, rbx
0x180015bd9  jz      short loc_180015BE3
0x180015bdb  mov     rcx, rbx
0x180015bde  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180015be3  mov     eax, edi
0x180015be5  jmp     loc_180015C94
0x180015bea  mov     rcx, [rbp+hKey]; HKEY
0x180015bee  lea     r8, aLoaditerations; "LoadIterations"
0x180015bf5  mov     r9, r14; unsigned int *
0x180015bf8  xor     edx, edx; unsigned __int16 *
0x180015bfa  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180015bff  mov     rcx, [rbp+18h]; this
0x180015c03  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180015c0a  mov     ebx, 80070002h
0x180015c0f  mov     r9d, eax; char *
0x180015c12  mov     [rsp+50h+var_28], ebx; unsigned int
0x180015c16  mov     edx, 520h; void *
0x180015c1b  mov     dword ptr [rsp+50h+phkResult], 1; int
0x180015c23  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180015c28  mov     rcx, [rbp+hKey]; HKEY
0x180015c2c  lea     r8, aLoaddelayms; "LoadDelayMS"
0x180015c33  mov     r9, rsi; unsigned int *
0x180015c36  xor     edx, edx; unsigned __int16 *
0x180015c38  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180015c3d  mov     rcx, [rbp+18h]; this
0x180015c41  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180015c48  mov     r9d, eax; char *
0x180015c4b  mov     [rsp+50h+var_28], ebx; unsigned int
0x180015c4f  mov     edx, 521h; void *
0x180015c54  mov     dword ptr [rsp+50h+phkResult], 1; int
0x180015c5c  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180015c61  mov     rcx, [rbp+hKey]; hKey
0x180015c65  test    rcx, rcx
0x180015c68  jz      short loc_180015C70
0x180015c6a  call    cs:__imp_RegCloseKey
0x180015c70  lea     rcx, [rbp+lpSubKey]
0x180015c74  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180015c79  jmp     short loc_180015C92
0x180015c7b  lea     rdx, [rbp+hKey]
0x180015c7f  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetCachedVariantState(void)
0x180015c84  mov     ecx, dword ptr [rbp+hKey+4]
0x180015c87  movzx   eax, cx
0x180015c8a  shr     ecx, 10h
0x180015c8d  mov     [r14], eax
0x180015c90  mov     [rsi], ecx
0x180015c92  xor     eax, eax
0x180015c94  lea     r11, [rsp+50h+var_s0]
0x180015c99  mov     rbx, [r11+30h]
0x180015c9d  mov     rsi, [r11+38h]
0x180015ca1  mov     rsp, r11
0x180015ca4  pop     r14
0x180015ca6  pop     rdi
0x180015ca7  pop     rbp
0x180015ca8  retn
```
