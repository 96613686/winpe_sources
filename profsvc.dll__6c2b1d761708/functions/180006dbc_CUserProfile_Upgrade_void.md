# CUserProfile::Upgrade(void)

- ea: `0x180006dbc`
- end: `0x180007178`
- name: `?Upgrade@CUserProfile@@IEAAJXZ`
- size: `956`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180030744`

## callees

- `0x180005dd0`
- `0x180006dbc`
- `0x180007180`
- `0x180007b58`
- `0x180007bc0`
- `0x180007c2c`
- `0x180007d40`
- `0x1800080d0`
- `0x180008154`
- `0x1800081b0`
- `0x1800081f0`
- `0x180008250`
- `0x1800087e8`
- `0x18000b060`
- `0x18000d030`
- `0x18000e1a0`
- `0x180013770`
- `0x180014b4c`
- `0x180014e90`
- `0x180026390`
- `0x180028f20`
- `0x180029d28`
- `0x180030ad0`
- `0x180031060`
- `0x18003bc70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006f3e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006f3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ed3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800070ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ed3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800070ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006f92`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006f92`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006e9c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006e9c`

## string_xrefs

- `0x180006e4e`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180006eb6`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180006fc4`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180007092`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfile::Upgrade(CUserProfile *this)
{
  int v2; // eax
  signed int v3; // ebx
  unsigned int v4; // eax
  LSTATUS ValueW; // eax
  LSTATUS v6; // eax
  const struct wil::FailureInfo *v7; // rdx
  __int64 v8; // rdx
  unsigned __int64 v9; // r9
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int pvData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+68h] [rbp-98h] BYREF
  char v21; // [rsp+70h] [rbp-90h]
  LPCWSTR lpSubKey[3]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v23[3]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int ProfileTypeFromState; // [rsp+A8h] [rbp-58h]
  int v25; // [rsp+ACh] [rbp-54h]
  void **v26; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v27[40]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v28[192]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v29[40]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v30[8]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v31[48]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(
    &v26,
    "CUserProfile_Upgrade");
  v26 = &ProfileTelemetry::CUserProfile_Upgrade::`vftable';
  ProfileTelemetry::CUserProfile_Upgrade::StartActivity((ProfileTelemetry::CUserProfile_Upgrade *)&v26);
  memset(lpSubKey, 0, sizeof(lpSubKey));
  v2 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s\\%s",
         *((_QWORD *)this + 6),
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon");
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8CD,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)v2,
      dwOptions);
LABEL_27:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
    ProfileTelemetry::CUserProfile_Upgrade::~CUserProfile_Upgrade((ProfileTelemetry::CUserProfile_Upgrade *)&v26);
    return (unsigned int)v3;
  }
  hKey = 0;
  v4 = RegCreateKeyExW(HKEY_USERS, lpSubKey[0], 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  if ( v4 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x8D9,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
           (const char *)v4,
           dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
    v26 = &ProfileTelemetry::CUserProfile_Upgrade::`vftable';
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v26);
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(&v26);
    return (unsigned int)v3;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hKey, 0, L"BuildNumber", 0x10u, 0, &pvData, &pcbData);
  v3 = ValueW;
  if ( ValueW > 0 )
    v3 = (unsigned __int16)ValueW | 0x80070000;
  if ( v3 == -2147024894 )
  {
    pcbData = g_dwBuildNumber;
    v6 = RegSetValueExW(hKey, L"BuildNumber", 0, 4u, (const BYTE *)&pcbData, 4u);
    v3 = v6;
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    if ( v3 < 0 )
    {
      v8 = 2273;
LABEL_14:
      v9 = (unsigned int)v3;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)v9,
        dwOptionsb);
LABEL_26:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_27;
    }
  }
  else
  {
    if ( v3 < 0 )
    {
      v8 = 2277;
      goto LABEL_14;
    }
    ProfileTelemetry::CUserProfile_Upgrade::BuildNumbers<unsigned long &,unsigned long &>(&v26, &pvData);
    if ( pvData < g_dwBuildNumber )
    {
      v10 = SHRegSetDWORD(hKey, 0, L"BuildNumber", g_dwBuildNumber);
      v3 = v10;
      if ( v10 < 0 )
      {
        v9 = (unsigned int)v10;
        v8 = 2285;
        goto LABEL_15;
      }
      v20 = 0;
      v21 = 0;
      v11 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v20, *((void **)this + 3));
      v3 = v11;
      if ( v11 >= 0 )
      {
        v23[2] = 0;
        v25 = 0;
        v23[0] = *((_QWORD *)this + 6);
        v23[1] = *((_QWORD *)this + 19);
        ProfileTypeFromState = GetProfileTypeFromState(*((_DWORD *)this + 3));
        v11 = SendNotification(16, v23, *((_DWORD *)this + 5), *((void **)this + 3));
        v3 = v11;
        if ( v11 >= 0 )
        {
          CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v20);
          goto LABEL_30;
        }
        v12 = 2297;
      }
      else
      {
        v12 = 2290;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v11,
        dwOptionsb);
      CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v20);
      goto LABEL_26;
    }
  }
LABEL_30:
  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)&v26, v7);
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpSubKey[0] )
    Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(lpSubKey[0]);
  v26 = &ProfileTelemetry::CUserProfile_Upgrade::`vftable';
  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v26);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v31);
  wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v30);
  wil::details::shared_buffer::reset((wil::details::shared_buffer *)v29);
  wil::details::StoredCallContextInfo::ClearMessage((wil::details::StoredCallContextInfo *)v28);
  _TlgActivityBase<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>,0,4>::~_TlgActivityBase<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>,0,4>(v27);
  return 0;
}

```

## disassembly

```asm
0x180006dbc  mov     [rsp-8+arg_8], rbx
0x180006dc1  mov     [rsp-8+arg_10], rsi
0x180006dc6  push    rbp
0x180006dc7  push    r12
0x180006dc9  push    r14
0x180006dcb  lea     rbp, [rsp-110h]
0x180006dd3  sub     rsp, 210h
0x180006dda  mov     rax, cs:__security_cookie
0x180006de1  xor     rax, rsp
0x180006de4  mov     [rbp+120h+var_20], rax
0x180006deb  mov     rsi, rcx
0x180006dee  lea     rdx, aCuserprofileUp; "CUserProfile_Upgrade"
0x180006df5  lea     rcx, [rbp+120h+var_170]
0x180006df9  call    ??0?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180006dfe  lea     r12, ??_7CUserProfile_Upgrade@ProfileTelemetry@@6B@; const ProfileTelemetry::CUserProfile_Upgrade::`vftable'
0x180006e05  mov     [rbp+120h+var_170], r12
0x180006e09  lea     rcx, [rbp+120h+var_170]; this
0x180006e0d  call    ?StartActivity@CUserProfile_Upgrade@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::CUserProfile_Upgrade::StartActivity(void)
0x180006e12  xor     r14d, r14d
0x180006e15  mov     [rsp+220h+lpSubKey], r14
0x180006e1a  mov     [rbp+120h+var_1A0], r14
0x180006e1e  mov     [rbp+120h+var_198], r14
0x180006e22  lea     r9, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x180006e29  mov     r8, [rsi+30h]
0x180006e2d  lea     rdx, aSS_0; "%s\\%s"
0x180006e34  lea     rcx, [rsp+220h+lpSubKey]
0x180006e39  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180006e3e  mov     ebx, eax
0x180006e40  test    eax, eax
0x180006e42  jns     short loc_180006E64
0x180006e44  mov     rcx, [rbp+128h]; this
0x180006e4b  mov     r9d, eax; char *
0x180006e4e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006e55  mov     edx, 8CDh; void *
0x180006e5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e5f  jmp     loc_1800070B9
0x180006e64  mov     [rsp+220h+hKey], r14
0x180006e69  mov     [rsp+220h+lpdwDisposition], r14; lpdwDisposition
0x180006e6e  lea     rax, [rsp+220h+hKey]
0x180006e73  mov     [rsp+220h+phkResult], rax; phkResult
0x180006e78  mov     [rsp+220h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180006e7d  mov     [rsp+220h+samDesired], 2001Fh; samDesired
0x180006e85  mov     [rsp+220h+dwOptions], r14d; unsigned int
0x180006e8a  xor     r9d, r9d; lpClass
0x180006e8d  xor     r8d, r8d; Reserved
0x180006e90  mov     rdx, [rsp+220h+lpSubKey]; lpSubKey
0x180006e95  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180006e9c  call    cs:__imp_RegCreateKeyExW
0x180006ea3  nop     dword ptr [rax+rax+00h]
0x180006ea8  test    eax, eax
0x180006eaa  jz      short loc_180006F04
0x180006eac  mov     rcx, [rbp+128h]; this
0x180006eb3  mov     r9d, eax; char *
0x180006eb6  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006ebd  mov     edx, 8D9h; void *
0x180006ec2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180006ec7  mov     ebx, eax
0x180006ec9  mov     rcx, [rsp+220h+hKey]; hKey
0x180006ece  test    rcx, rcx
0x180006ed1  jz      short loc_180006EDF
0x180006ed3  call    cs:__imp_RegCloseKey
0x180006eda  nop     dword ptr [rax+rax+00h]
0x180006edf  lea     rcx, [rsp+220h+lpSubKey]
0x180006ee4  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180006ee9  mov     [rbp+120h+var_170], r12
0x180006eed  lea     rcx, [rbp+120h+var_170]
0x180006ef1  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180006ef6  lea     rcx, [rbp+120h+var_170]
0x180006efa  call    ??1?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180006eff  jmp     loc_1800070CC
0x180006f04  mov     [rsp+220h+pvData], r14d
0x180006f09  mov     [rsp+220h+pcbData], 4
0x180006f11  lea     rax, [rsp+220h+pcbData]
0x180006f16  mov     [rsp+220h+lpSecurityAttributes], rax; pcbData
0x180006f1b  lea     rax, [rsp+220h+pvData]
0x180006f20  mov     qword ptr [rsp+220h+samDesired], rax; pvData
0x180006f25  mov     qword ptr [rsp+220h+dwOptions], r14; int
0x180006f2a  mov     r9d, 10h; dwFlags
0x180006f30  lea     r8, ValueName; "BuildNumber"
0x180006f37  xor     edx, edx; lpSubKey
0x180006f39  mov     rcx, [rsp+220h+hKey]; hkey
0x180006f3e  call    cs:__imp_RegGetValueW
0x180006f45  nop     dword ptr [rax+rax+00h]
0x180006f4a  mov     ebx, eax
0x180006f4c  test    eax, eax
0x180006f4e  jle     short loc_180006F59
0x180006f50  movzx   ebx, ax
0x180006f53  or      ebx, 80070000h
0x180006f59  cmp     ebx, 80070002h
0x180006f5f  jnz     short loc_180006FD5
0x180006f61  mov     eax, cs:?g_dwBuildNumber@@3KA; ulong g_dwBuildNumber
0x180006f67  mov     [rsp+220h+pcbData], eax
0x180006f6b  mov     [rsp+220h+samDesired], 4; cbData
0x180006f73  lea     rax, [rsp+220h+pcbData]
0x180006f78  mov     qword ptr [rsp+220h+dwOptions], rax; int
0x180006f7d  mov     r9d, 4; dwType
0x180006f83  xor     r8d, r8d; Reserved
0x180006f86  lea     rdx, ValueName; "BuildNumber"
0x180006f8d  mov     rcx, [rsp+220h+hKey]; hKey
0x180006f92  call    cs:__imp_RegSetValueExW
0x180006f99  nop     dword ptr [rax+rax+00h]
0x180006f9e  mov     ebx, eax
0x180006fa0  test    eax, eax
0x180006fa2  jle     short loc_180006FAD
0x180006fa4  movzx   ebx, ax
0x180006fa7  or      ebx, 80070000h
0x180006fad  test    ebx, ebx
0x180006faf  jns     loc_1800070DA
0x180006fb5  mov     edx, 8E1h; void *
0x180006fba  mov     r9d, ebx; char *
0x180006fbd  mov     rcx, [rbp+128h]; this
0x180006fc4  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006fcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006fd0  jmp     loc_1800070AF
0x180006fd5  test    ebx, ebx
0x180006fd7  jns     short loc_180006FE0
0x180006fd9  mov     edx, 8E5h
0x180006fde  jmp     short loc_180006FBA
0x180006fe0  lea     rdx, [rsp+220h+pvData]
0x180006fe5  lea     rcx, [rbp+120h+var_170]
0x180006fe9  call    ??$BuildNumbers@AEAKAEAK@CUserProfile_Upgrade@ProfileTelemetry@@QEAAXAEAK0@Z; ProfileTelemetry::CUserProfile_Upgrade::BuildNumbers<ulong &,ulong &>(ulong &,ulong &)
0x180006fee  mov     r9d, cs:?g_dwBuildNumber@@3KA; unsigned int
0x180006ff5  cmp     [rsp+220h+pvData], r9d
0x180006ffa  jnb     loc_1800070DA
0x180007000  lea     r8, ValueName; "BuildNumber"
0x180007007  xor     edx, edx; unsigned __int16 *
0x180007009  mov     rcx, [rsp+220h+hKey]; HKEY
0x18000700e  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180007013  mov     ebx, eax
0x180007015  test    eax, eax
0x180007017  jns     short loc_180007023
0x180007019  mov     r9d, eax
0x18000701c  mov     edx, 8EDh
0x180007021  jmp     short loc_180006FBD
0x180007023  mov     [rsp+220h+var_1B8], r14
0x180007028  mov     [rsp+220h+var_1B0], r14b
0x18000702d  mov     rdx, [rsi+18h]; void *
0x180007031  lea     rcx, [rsp+220h+var_1B8]; this
0x180007036  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x18000703b  mov     ebx, eax
0x18000703d  test    eax, eax
0x18000703f  jns     short loc_180007048
0x180007041  mov     edx, 8F2h
0x180007046  jmp     short loc_18000708F
0x180007048  mov     [rbp+120h+var_180], r14
0x18000704c  mov     [rbp+120h+var_174], r14d
0x180007050  mov     rax, [rsi+30h]
0x180007054  mov     [rbp+120h+var_190], rax
0x180007058  mov     rax, [rsi+98h]
0x18000705f  mov     [rbp+120h+var_188], rax
0x180007063  mov     ecx, [rsi+0Ch]; unsigned int
0x180007066  call    ?GetProfileTypeFromState@@YAKK@Z; GetProfileTypeFromState(ulong)
0x18000706b  mov     [rbp+120h+var_178], eax
0x18000706e  mov     r9, [rsi+18h]
0x180007072  mov     r8d, [rsi+14h]
0x180007076  lea     rdx, [rbp+120h+var_190]
0x18000707a  mov     ecx, 10h
0x18000707f  call    ?SendNotification@@YAJW4PROF_NOTIFY_EVENT_FLAGS@@PEAUPROF_NOTIFY_PARAM@@KPEAX@Z; SendNotification(PROF_NOTIFY_EVENT_FLAGS,PROF_NOTIFY_PARAM *,ulong,void *)
0x180007084  mov     ebx, eax
0x180007086  test    eax, eax
0x180007088  jns     short loc_1800070D0
0x18000708a  mov     edx, 8F9h; void *
0x18000708f  mov     r9d, eax; char *
0x180007092  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180007099  mov     rcx, [rbp+128h]; this
0x1800070a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070a5  lea     rcx, [rsp+220h+var_1B8]; this
0x1800070aa  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x1800070af  lea     rcx, [rsp+220h+hKey]
0x1800070b4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800070b9  lea     rcx, [rsp+220h+lpSubKey]
0x1800070be  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800070c3  lea     rcx, [rbp+120h+var_170]; this
0x1800070c7  call    ??1CUserProfile_Upgrade@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::CUserProfile_Upgrade::~CUserProfile_Upgrade(void)
0x1800070cc  mov     eax, ebx
0x1800070ce  jmp     short loc_18000714F
0x1800070d0  lea     rcx, [rsp+220h+var_1B8]; this
0x1800070d5  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x1800070da  lea     rcx, [rbp+120h+var_170]
0x1800070de  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800070e3  mov     rcx, [rsp+220h+hKey]; hKey
0x1800070e8  test    rcx, rcx
0x1800070eb  jz      short loc_1800070F9
0x1800070ed  call    cs:__imp_RegCloseKey
0x1800070f4  nop     dword ptr [rax+rax+00h]
0x1800070f9  cmp     [rsp+220h+lpSubKey], r14
0x1800070fe  jz      short loc_18000710A
0x180007100  mov     rcx, [rsp+220h+lpSubKey]
0x180007105  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18000710a  mov     [rbp+120h+var_170], r12
0x18000710e  lea     rcx, [rbp+120h+var_170]
0x180007112  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180007117  lea     rcx, [rbp+120h+var_50]; this
0x18000711e  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180007123  lea     rcx, [rbp+120h+var_58]
0x18000712a  call    ?reset@?$shared_object@V?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000712f  lea     rcx, [rbp+120h+var_80]; this
0x180007136  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x18000713b  lea     rcx, [rbp+120h+var_140]; this
0x18000713f  call    ?ClearMessage@StoredCallContextInfo@details@wil@@QEAAXXZ; wil::details::StoredCallContextInfo::ClearMessage(void)
0x180007144  lea     rcx, [rbp+120h+var_168]
0x180007148  call    ??1?$_TlgActivityBase@V?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0A@$03@@IEAA@XZ; _TlgActivityBase<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>,0,4>::~_TlgActivityBase<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>,0,4>(void)
0x18000714d  xor     eax, eax
0x18000714f  mov     rcx, [rbp+120h+var_20]
0x180007156  xor     rcx, rsp; StackCookie
0x180007159  call    __security_check_cookie
0x18000715e  lea     r11, [rsp+220h+var_10]
0x180007166  mov     rbx, [r11+28h]
0x18000716a  mov     rsi, [r11+30h]
0x18000716e  mov     rsp, r11
0x180007171  pop     r14
0x180007173  pop     r12
0x180007175  pop     rbp
0x180007176  retn
```
