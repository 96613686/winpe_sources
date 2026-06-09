# CUserProfile::CheckUserPrefrenceKey(HKEY__ *,int)

- ea: `0x180045494`
- end: `0x18004560e`
- name: `?CheckUserPrefrenceKey@CUserProfile@@IEAAJPEAUHKEY__@@H@Z`
- size: `378`
- prototype: `int(CUserProfile *__hidden this, HKEY, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180013838`

## callees

- `0x1800130d0`
- `0x180013770`
- `0x180030ad0`
- `0x180030af8`
- `0x18003164c`
- `0x180045494`
- `0x180049e10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045581`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045581`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180045504`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180045504`

## string_xrefs

- `0x180045536`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800455d1`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfile::CheckUserPrefrenceKey(CUserProfile *this, HKEY a2, int a3)
{
  _WORD *v5; // rax
  __int64 v6; // rcx
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  __int64 v10; // rcx
  int v11; // eax
  int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY v14; // [rsp+40h] [rbp+8h] BYREF

  v5 = (_WORD *)*((_QWORD *)this + 13);
  if ( v5 && *v5 )
  {
    if ( (*((_BYTE *)this + 12) & 1) != 0 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
      {
        McTemplateU0z_EtwEventWriteTransfer(v6, EVENT_PROFILE_USER_PREF_KEY_DELETE, *((_QWORD *)this + 10));
      }
      v7 = RegDeleteKeyExW(a2, L"Preference", 0, 0);
      v8 = v7;
      if ( (v7 & 0xFFFFFFFD) != 0 )
      {
        if ( v7 > 0 )
          v8 = (unsigned __int16)v7 | 0x80070000;
        if ( (v8 & 0x80000000) != 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x497,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)v8,
            phkResult);
        return v8;
      }
    }
    else
    {
      v14 = 0;
      if ( a3
        || (wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &v14,
              0),
            RegOpenKeyExW(a2, L"Preference", 0, 0x20019u, &v14)) )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
          && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
        {
          McTemplateU0z_EtwEventWriteTransfer(v10, EVENT_PROFILE_USER_PREF_SETUP, *((_QWORD *)this + 10));
        }
        v11 = SetupPreferenceKey(*((LPCWCH *)this + 6));
        v8 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4A5,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)(unsigned int)v11,
            phkResult);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v14);
          return v8;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v14);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180045494  mov     [rsp+arg_8], rbx
0x180045499  mov     [rsp+arg_10], rsi
0x18004549e  push    rdi
0x18004549f  sub     rsp, 30h
0x1800454a3  mov     rdi, rdx
0x1800454a6  mov     rbx, rcx
0x1800454a9  mov     rax, [rcx+68h]
0x1800454ad  xor     esi, esi
0x1800454af  test    rax, rax
0x1800454b2  jz      loc_1800455FB
0x1800454b8  cmp     [rax], si
0x1800454bb  jz      loc_1800455FB
0x1800454c1  test    byte ptr [rcx+0Ch], 1
0x1800454c5  jz      loc_18004554E
0x1800454cb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x1800454d2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x1800454d7  test    al, al
0x1800454d9  jz      short loc_1800454F4
0x1800454db  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, sil
0x1800454e2  jge     short loc_1800454F4
0x1800454e4  mov     r8, [rbx+50h]
0x1800454e8  lea     rdx, EVENT_PROFILE_USER_PREF_KEY_DELETE
0x1800454ef  call    McTemplateU0z_EtwEventWriteTransfer
0x1800454f4  xor     r9d, r9d; Reserved
0x1800454f7  xor     r8d, r8d; samDesired
0x1800454fa  lea     rdx, aPreference; "Preference"
0x180045501  mov     rcx, rdi; hKey
0x180045504  call    cs:__imp_RegDeleteKeyExW
0x18004550b  nop     dword ptr [rax+rax+00h]
0x180045510  mov     ebx, eax
0x180045512  test    eax, 0FFFFFFFDh
0x180045517  jz      loc_1800455FB
0x18004551d  test    eax, eax
0x18004551f  jle     short loc_18004552A
0x180045521  movzx   ebx, ax
0x180045524  or      ebx, 80070000h
0x18004552a  test    ebx, ebx
0x18004552c  jns     short loc_180045547
0x18004552e  mov     rcx, [rsp+38h]; this
0x180045533  mov     r9d, ebx; char *
0x180045536  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004553d  mov     edx, 497h; void *
0x180045542  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045547  mov     eax, ebx
0x180045549  jmp     loc_1800455FD
0x18004554e  mov     [rsp+38h+arg_0], rsi
0x180045553  test    r8d, r8d
0x180045556  jnz     short loc_180045591
0x180045558  xor     edx, edx
0x18004555a  lea     rcx, [rsp+38h+arg_0]
0x18004555f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180045564  lea     rax, [rsp+38h+arg_0]
0x180045569  mov     qword ptr [rsp+38h+phkResult], rax; int
0x18004556e  mov     r9d, 20019h; samDesired
0x180045574  xor     r8d, r8d; ulOptions
0x180045577  lea     rdx, aPreference; "Preference"
0x18004557e  mov     rcx, rdi; hKey
0x180045581  call    cs:__imp_RegOpenKeyExW
0x180045588  nop     dword ptr [rax+rax+00h]
0x18004558d  test    eax, eax
0x18004558f  jz      short loc_1800455F1
0x180045591  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180045598  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18004559d  test    al, al
0x18004559f  jz      short loc_1800455BA
0x1800455a1  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, sil
0x1800455a8  jge     short loc_1800455BA
0x1800455aa  mov     r8, [rbx+50h]
0x1800455ae  lea     rdx, EVENT_PROFILE_USER_PREF_SETUP
0x1800455b5  call    McTemplateU0z_EtwEventWriteTransfer
0x1800455ba  mov     rcx, [rbx+30h]; lpString1
0x1800455be  call    ?SetupPreferenceKey@@YAJPEBG@Z; SetupPreferenceKey(ushort const *)
0x1800455c3  mov     ebx, eax
0x1800455c5  test    eax, eax
0x1800455c7  jns     short loc_1800455F1
0x1800455c9  mov     rcx, [rsp+38h]; this
0x1800455ce  mov     r9d, eax; char *
0x1800455d1  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800455d8  mov     edx, 4A5h; void *
0x1800455dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800455e2  lea     rcx, [rsp+38h+arg_0]
0x1800455e7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800455ec  jmp     loc_180045547
0x1800455f1  lea     rcx, [rsp+38h+arg_0]
0x1800455f6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800455fb  xor     eax, eax
0x1800455fd  mov     rbx, [rsp+38h+arg_8]
0x180045602  mov     rsi, [rsp+38h+arg_10]
0x180045607  add     rsp, 30h
0x18004560b  pop     rdi
0x18004560c  retn
```
