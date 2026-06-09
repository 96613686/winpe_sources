# CloudExperienceHostAPI::OobeUpdateSettingsManagerStaticsCore::get_ShouldSkip(uchar *)

- ea: `0x1800561b0`
- end: `0x180056365`
- name: `?get_ShouldSkip@OobeUpdateSettingsManagerStaticsCore@CloudExperienceHostAPI@@UEAAJPEAE@Z`
- size: `437`
- prototype: `__int64 __fastcall(CloudExperienceHostAPI::OobeUpdateSettingsManagerStaticsCore *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002b60`
- `0x180009760`
- `0x180009814`
- `0x18000a4f8`
- `0x18000b200`
- `0x180047d6c`
- `0x180055e38`
- `0x1800561b0`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800562a9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800562a9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800562f4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800562f4`

## string_xrefs

- `0x1800561d6`: `Software\Microsoft\Windows\CurrentVersion\DeviceAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CloudExperienceHostAPI::OobeUpdateSettingsManagerStaticsCore::get_ShouldSkip(
        CloudExperienceHostAPI::OobeUpdateSettingsManagerStaticsCore *this,
        unsigned __int8 *a2)
{
  HKEY v3; // rcx
  __int64 v4; // r9
  unsigned int v5; // ebx
  __int64 v7; // [rsp+30h] [rbp-D0h] BYREF
  LPCWCH lpString1; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+58h] [rbp-A8h]
  WCHAR String2[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v12[8]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v13; // [rsp+78h] [rbp-88h]
  wchar_t v14; // [rsp+88h] [rbp-78h]
  unsigned __int16 v15[8]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v16; // [rsp+A0h] [rbp-60h]
  __int128 v17; // [rsp+B0h] [rbp-50h]
  __int128 v18; // [rsp+C0h] [rbp-40h]
  __int128 v19; // [rsp+D0h] [rbp-30h]
  _OWORD v20[2]; // [rsp+E0h] [rbp-20h]

  *a2 = 1;
  *(_OWORD *)v15 = *(_OWORD *)L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess";
  v16 = *(_OWORD *)L"\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess";
  v17 = *(_OWORD *)L"ft\\Windows\\CurrentVersion\\DeviceAccess";
  v18 = *(_OWORD *)L"ws\\CurrentVersion\\DeviceAccess";
  v19 = *(_OWORD *)L"ntVersion\\DeviceAccess";
  v20[0] = *(_OWORD *)L"n\\DeviceAccess";
  *(_OWORD *)((char *)v20 + 14) = *(_OWORD *)L"eAccess";
  *(_OWORD *)v12 = *(_OWORD *)L"ActivePolicyCode";
  v13 = *(_OWORD *)L"licyCode";
  v14 = aActivepolicyco[16];
  lpString1 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpString1,
    0);
  if ( (int)SHRegAllocData(v3, v15, v12, v4, (void **)&lpString1) < 0
    || (wcscpy(String2, L"zh"), CompareStringOrdinal(lpString1, -1, String2, -1, 1) != 2) )
  {
LABEL_8:
    v5 = 0;
    goto LABEL_9;
  }
  v7 = 0;
  v10 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"CloudExperienceHostAPI.OobeSettingsManagerStatics",
    0x32u,
    0x31u);
  if ( (int)RoGetActivationFactory(v10, &GUID_1649561a_e904_44ec_9a0e_cc47736cf918, &v7) < 0 )
  {
    if ( !(unsigned __int8)AutoPilotUtils::AutoPilotGetOobeSettingsOverride(2) )
      *a2 = 0;
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v7);
    goto LABEL_8;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v7 + 48LL))(v7, a2);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v7);
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
  return v5;
}

```

## disassembly

```asm
0x1800561b0  mov     [rsp-8+arg_0], rbx
0x1800561b5  push    rbp
0x1800561b6  lea     rbp, [rsp-10h]
0x1800561bb  sub     rsp, 110h
0x1800561c2  mov     rax, cs:__security_cookie
0x1800561c9  xor     rax, rsp
0x1800561cc  mov     [rbp+10h+var_10], rax
0x1800561d0  mov     rbx, rdx
0x1800561d3  mov     byte ptr [rdx], 1
0x1800561d6  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800561dd  movaps  xmmword ptr [rbp+10h+var_80], xmm0
0x1800561e1  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_6+10h; "\\Microsoft\\Windows\\CurrentVersion\\D"...
0x1800561e8  movaps  [rbp+10h+var_70], xmm1
0x1800561ec  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_6+20h; "ft\\Windows\\CurrentVersion\\DeviceAcce"...
0x1800561f3  movaps  [rbp+10h+var_60], xmm0
0x1800561f7  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_6+30h; "ws\\CurrentVersion\\DeviceAccess"
0x1800561fe  movaps  [rbp+10h+var_50], xmm1
0x180056202  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_6+40h; "ntVersion\\DeviceAccess"
0x180056209  movaps  [rbp+10h+var_40], xmm0
0x18005620d  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_6+50h; "n\\DeviceAccess"
0x180056214  movaps  xmmword ptr [rbp+10h+var_30], xmm1
0x180056218  movups  xmm0, xmmword ptr cs:aSoftwareMicros_6+5Eh; "eAccess"
0x18005621f  movups  xmmword ptr [rbp+10h+var_30+0Eh], xmm0
0x180056223  movups  xmm1, xmmword ptr cs:aActivepolicyco; "ActivePolicyCode"
0x18005622a  movups  xmmword ptr [rsp+110h+var_A8], xmm1
0x18005622f  movups  xmm0, xmmword ptr cs:aActivepolicyco+10h; "licyCode"
0x180056236  movups  [rsp+110h+var_98], xmm0
0x18005623b  movzx   eax, word ptr cs:aActivepolicyco+20h; ""
0x180056242  mov     [rbp+10h+var_88], ax
0x180056246  mov     [rsp+110h+lpString1], 0
0x18005624f  xor     edx, edx
0x180056251  lea     rcx, [rsp+110h+lpString1]
0x180056256  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005625b  lea     rax, [rsp+110h+lpString1]
0x180056260  mov     qword ptr [rsp+110h+bIgnoreCase], rax; void **
0x180056265  lea     r8, [rsp+110h+var_A8]; unsigned __int16 *
0x18005626a  lea     rdx, [rbp+10h+var_80]; unsigned __int16 *
0x18005626e  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x180056273  test    eax, eax
0x180056275  js      loc_18005633A
0x18005627b  mov     eax, dword ptr cs:aZh; "zh"
0x180056281  mov     dword ptr [rsp+110h+String2], eax
0x180056285  movzx   eax, word ptr cs:aZh+4; ""
0x18005628c  mov     [rsp+110h+var_AC], ax
0x180056291  mov     [rsp+110h+bIgnoreCase], 1; bIgnoreCase
0x180056299  or      edx, 0FFFFFFFFh; cchCount1
0x18005629c  mov     r9d, edx; cchCount2
0x18005629f  lea     r8, [rsp+110h+String2]; lpString2
0x1800562a4  mov     rcx, [rsp+110h+lpString1]; lpString1
0x1800562a9  call    cs:__imp_CompareStringOrdinal
0x1800562af  cmp     eax, 2
0x1800562b2  jnz     loc_18005633A
0x1800562b8  mov     [rsp+110h+var_E0], 0
0x1800562c1  mov     [rsp+110h+var_B8], 0
0x1800562ca  lea     r9d, [rax+2Fh]; unsigned int
0x1800562ce  lea     r8d, [rax+30h]; unsigned int
0x1800562d2  lea     rdx, ?RuntimeClass_CloudExperienceHostAPI_OobeSettingsManagerStatics@@3QBGB; "CloudExperienceHostAPI.OobeSettingsMana"...
0x1800562d9  lea     rcx, [rsp+110h+hstringHeader]; hstringHeader
0x1800562de  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800562e3  lea     r8, [rsp+110h+var_E0]
0x1800562e8  lea     rdx, _GUID_1649561a_e904_44ec_9a0e_cc47736cf918
0x1800562ef  mov     rcx, [rsp+110h+var_B8]
0x1800562f4  call    cs:__imp_RoGetActivationFactory
0x1800562fa  test    eax, eax
0x1800562fc  js      short loc_180056320
0x1800562fe  mov     rcx, [rsp+110h+var_E0]
0x180056303  mov     rax, [rcx]
0x180056306  mov     rdx, rbx
0x180056309  mov     rax, [rax+30h]
0x18005630d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056312  mov     ebx, eax
0x180056314  lea     rcx, [rsp+110h+var_E0]
0x180056319  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005631e  jmp     short loc_18005633C
0x180056320  mov     ecx, 2
0x180056325  call    ?AutoPilotGetOobeSettingsOverride@AutoPilotUtils@@YAEW4AutoPilotOobeSetting@AutoPilot@Service@EnterpriseDeviceManagement@@@Z; AutoPilotUtils::AutoPilotGetOobeSettingsOverride(EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotOobeSetting)
0x18005632a  test    al, al
0x18005632c  jnz     short loc_180056330
0x18005632e  mov     [rbx], al
0x180056330  lea     rcx, [rsp+110h+var_E0]
0x180056335  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005633a  xor     ebx, ebx
0x18005633c  lea     rcx, [rsp+110h+lpString1]
0x180056341  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180056346  mov     eax, ebx
0x180056348  mov     rcx, [rbp+10h+var_10]
0x18005634c  xor     rcx, rsp; StackCookie
0x18005634f  call    __security_check_cookie
0x180056354  mov     rbx, [rsp+110h+arg_0]
0x18005635c  add     rsp, 110h
0x180056363  pop     rbp
0x180056364  retn
```
