# CUserProfile::CheckUserPrefrenceKey(HKEY__ *,int)

- ea: `0x1800439c0`
- end: `0x180043b39`
- name: `?CheckUserPrefrenceKey@CUserProfile@@IEAAJPEAUHKEY__@@H@Z`
- size: `377`
- prototype: `__int64 __fastcall(CUserProfile *this, HKEY, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001ea8c`

## callees

- `0x18001f060`
- `0x18002c324`
- `0x18002d2d8`
- `0x18002d7c0`
- `0x1800439c0`
- `0x180047cbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043aa3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043aa3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180043a2c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180043a2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043b0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043b21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043b0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043b21`

## string_xrefs

- `0x180043a58`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180043aed`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

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
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v5 = (_WORD *)*((_QWORD *)this + 13);
  if ( v5 && *v5 )
  {
    if ( (*((_BYTE *)this + 12) & 1) != 0 )
    {
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
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
      hKey = 0;
      if ( a3
        || (wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &hKey,
              0),
            RegOpenKeyExW(a2, L"Preference", 0, 0x20019u, &hKey)) )
      {
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
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
          if ( hKey )
            RegCloseKey(hKey);
          return v8;
        }
      }
      if ( hKey )
        RegCloseKey(hKey);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800439c0  mov     [rsp+arg_8], rbx
0x1800439c5  mov     [rsp+arg_10], rsi
0x1800439ca  push    rdi
0x1800439cb  sub     rsp, 30h
0x1800439cf  mov     rdi, rdx
0x1800439d2  mov     rbx, rcx
0x1800439d5  mov     rax, [rcx+68h]
0x1800439d9  xor     esi, esi
0x1800439db  test    rax, rax
0x1800439de  jz      loc_180043B27
0x1800439e4  cmp     [rax], si
0x1800439e7  jz      loc_180043B27
0x1800439ed  test    byte ptr [rcx+0Ch], 1
0x1800439f1  jz      short loc_180043A70
0x1800439f3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x1800439fa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x1800439ff  test    al, al
0x180043a01  jz      short loc_180043A1C
0x180043a03  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, sil
0x180043a0a  jge     short loc_180043A1C
0x180043a0c  mov     r8, [rbx+50h]
0x180043a10  lea     rdx, EVENT_PROFILE_USER_PREF_KEY_DELETE
0x180043a17  call    McTemplateU0z_EtwEventWriteTransfer
0x180043a1c  xor     r9d, r9d; Reserved
0x180043a1f  xor     r8d, r8d; samDesired
0x180043a22  lea     rdx, aPreference; "Preference"
0x180043a29  mov     rcx, rdi; hKey
0x180043a2c  call    cs:__imp_RegDeleteKeyExW
0x180043a32  mov     ebx, eax
0x180043a34  test    eax, 0FFFFFFFDh
0x180043a39  jz      loc_180043B27
0x180043a3f  test    eax, eax
0x180043a41  jle     short loc_180043A4C
0x180043a43  movzx   ebx, ax
0x180043a46  or      ebx, 80070000h
0x180043a4c  test    ebx, ebx
0x180043a4e  jns     short loc_180043A69
0x180043a50  mov     rcx, [rsp+38h]; this
0x180043a55  mov     r9d, ebx; char *
0x180043a58  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180043a5f  mov     edx, 497h; void *
0x180043a64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043a69  mov     eax, ebx
0x180043a6b  jmp     loc_180043B29
0x180043a70  mov     [rsp+38h+hKey], rsi
0x180043a75  test    r8d, r8d
0x180043a78  jnz     short loc_180043AAD
0x180043a7a  xor     edx, edx
0x180043a7c  lea     rcx, [rsp+38h+hKey]
0x180043a81  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180043a86  lea     rax, [rsp+38h+hKey]
0x180043a8b  mov     qword ptr [rsp+38h+phkResult], rax; int
0x180043a90  mov     r9d, 20019h; samDesired
0x180043a96  xor     r8d, r8d; ulOptions
0x180043a99  lea     rdx, aPreference; "Preference"
0x180043aa0  mov     rcx, rdi; hKey
0x180043aa3  call    cs:__imp_RegOpenKeyExW
0x180043aa9  test    eax, eax
0x180043aab  jz      short loc_180043B17
0x180043aad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180043ab4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180043ab9  test    al, al
0x180043abb  jz      short loc_180043AD6
0x180043abd  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, sil
0x180043ac4  jge     short loc_180043AD6
0x180043ac6  mov     r8, [rbx+50h]
0x180043aca  lea     rdx, EVENT_PROFILE_USER_PREF_SETUP
0x180043ad1  call    McTemplateU0z_EtwEventWriteTransfer
0x180043ad6  mov     rcx, [rbx+30h]; lpString1
0x180043ada  call    ?SetupPreferenceKey@@YAJPEBG@Z; SetupPreferenceKey(ushort const *)
0x180043adf  mov     ebx, eax
0x180043ae1  test    eax, eax
0x180043ae3  jns     short loc_180043B17
0x180043ae5  mov     rcx, [rsp+38h]; this
0x180043aea  mov     r9d, eax; char *
0x180043aed  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180043af4  mov     edx, 4A5h; void *
0x180043af9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043afe  mov     rcx, [rsp+38h+hKey]; hKey
0x180043b03  test    rcx, rcx
0x180043b06  jz      loc_180043A69
0x180043b0c  call    cs:__imp_RegCloseKey
0x180043b12  jmp     loc_180043A69
0x180043b17  mov     rcx, [rsp+38h+hKey]; hKey
0x180043b1c  test    rcx, rcx
0x180043b1f  jz      short loc_180043B27
0x180043b21  call    cs:__imp_RegCloseKey
0x180043b27  xor     eax, eax
0x180043b29  mov     rbx, [rsp+38h+arg_8]
0x180043b2e  mov     rsi, [rsp+38h+arg_10]
0x180043b33  add     rsp, 30h
0x180043b37  pop     rdi
0x180043b38  retn
```
