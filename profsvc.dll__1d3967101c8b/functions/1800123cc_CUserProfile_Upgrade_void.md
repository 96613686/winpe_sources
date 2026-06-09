# CUserProfile::Upgrade(void)

- ea: `0x1800123cc`
- end: `0x180012743`
- name: `?Upgrade@CUserProfile@@IEAAJXZ`
- size: `887`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002bf94`

## callees

- `0x180008200`
- `0x18000a320`
- `0x18000a37c`
- `0x18000a4a0`
- `0x18000a9e0`
- `0x18000aa5c`
- `0x18000aab8`
- `0x18000adc0`
- `0x180010f30`
- `0x1800111a0`
- `0x1800123cc`
- `0x18001274c`
- `0x1800128b0`
- `0x180013c1c`
- `0x180013c48`
- `0x18001fb70`
- `0x180023a80`
- `0x18002d2d8`
- `0x18002e648`
- `0x18003a730`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800126e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800126e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800126d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800126d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012523`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012523`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800124d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012692`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800126ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800124d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012692`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800126ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012571`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012571`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800124a3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800124a3`

## string_xrefs

- `0x180012455`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800124b7`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001259d`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001266b`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

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
  HANDLE ProcessHeap; // rax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int pvData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  char v22; // [rsp+70h] [rbp-90h]
  LPCWSTR lpSubKey[3]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v24[3]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int ProfileTypeFromState; // [rsp+A8h] [rbp-58h]
  int v26; // [rsp+ACh] [rbp-54h]
  void **v27; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v28[272]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v29[8]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v30[48]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(
    &v27,
    "CUserProfile_Upgrade");
  v27 = &ProfileTelemetry::CUserProfile_Upgrade::`vftable';
  ProfileTelemetry::CUserProfile_Upgrade::StartActivity((ProfileTelemetry::CUserProfile_Upgrade *)&v27);
  memset(lpSubKey, 0, sizeof(lpSubKey));
  v2 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s\\%s",
         *((_QWORD *)this + 6),
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon");
  v3 = v2;
  if ( v2 >= 0 )
  {
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
LABEL_35:
      v27 = &ProfileTelemetry::CUserProfile_Upgrade::`vftable';
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v27);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v30);
      wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v29);
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(v28);
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
        goto LABEL_26;
      }
    }
    else
    {
      if ( v3 < 0 )
      {
        v8 = 2277;
        goto LABEL_14;
      }
      ProfileTelemetry::CUserProfile_Upgrade::BuildNumbers<unsigned long &,unsigned long &>(&v27, &pvData);
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
        v21 = 0;
        v22 = 0;
        v11 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v21, *((void **)this + 3));
        v3 = v11;
        if ( v11 >= 0 )
        {
          v24[2] = 0;
          v26 = 0;
          v24[0] = *((_QWORD *)this + 6);
          v24[1] = *((_QWORD *)this + 19);
          ProfileTypeFromState = GetProfileTypeFromState(*((_DWORD *)this + 3));
          v11 = SendNotification(16, v24, *((_DWORD *)this + 5), *((void **)this + 3));
          v3 = v11;
          if ( v11 >= 0 )
          {
            CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v21);
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
        CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v21);
LABEL_26:
        if ( hKey )
          RegCloseKey(hKey);
        goto LABEL_28;
      }
    }
LABEL_30:
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)&v27, v7);
    if ( hKey )
      RegCloseKey(hKey);
    if ( lpSubKey[0] )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)lpSubKey[0]);
    }
    v3 = 0;
    goto LABEL_35;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8CD,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)(unsigned int)v2,
    dwOptions);
LABEL_28:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
  ProfileTelemetry::CUserProfile_Upgrade::~CUserProfile_Upgrade((ProfileTelemetry::CUserProfile_Upgrade *)&v27);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800123cc  push    rbp
0x1800123ce  push    rbx
0x1800123cf  push    rdi
0x1800123d0  push    r14
0x1800123d2  lea     rbp, [rsp-118h]
0x1800123da  sub     rsp, 218h
0x1800123e1  mov     rax, cs:__security_cookie
0x1800123e8  xor     rax, rsp
0x1800123eb  mov     [rbp+130h+var_30], rax
0x1800123f2  mov     rdi, rcx
0x1800123f5  lea     rdx, aCuserprofileUp; "CUserProfile_Upgrade"
0x1800123fc  lea     rcx, [rbp+130h+var_180]
0x180012400  call    ??0?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180012405  lea     rax, ??_7CUserProfile_Upgrade@ProfileTelemetry@@6B@; const ProfileTelemetry::CUserProfile_Upgrade::`vftable'
0x18001240c  mov     [rbp+130h+var_180], rax
0x180012410  lea     rcx, [rbp+130h+var_180]; this
0x180012414  call    ?StartActivity@CUserProfile_Upgrade@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::CUserProfile_Upgrade::StartActivity(void)
0x180012419  xor     r14d, r14d
0x18001241c  mov     [rsp+230h+lpSubKey], r14
0x180012421  mov     [rbp+130h+var_1B0], r14
0x180012425  mov     [rbp+130h+var_1A8], r14
0x180012429  lea     r9, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x180012430  mov     r8, [rdi+30h]
0x180012434  lea     rdx, aSS_0; "%s\\%s"
0x18001243b  lea     rcx, [rsp+230h+lpSubKey]
0x180012440  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180012445  mov     ebx, eax
0x180012447  test    eax, eax
0x180012449  jns     short loc_18001246B
0x18001244b  mov     rcx, [rbp+138h]; this
0x180012452  mov     r9d, eax; char *
0x180012455  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001245c  mov     edx, 8CDh; void *
0x180012461  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012466  jmp     loc_180012698
0x18001246b  mov     [rsp+230h+hKey], r14
0x180012470  mov     [rsp+230h+lpdwDisposition], r14; lpdwDisposition
0x180012475  lea     rax, [rsp+230h+hKey]
0x18001247a  mov     [rsp+230h+phkResult], rax; phkResult
0x18001247f  mov     [rsp+230h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180012484  mov     [rsp+230h+samDesired], 2001Fh; samDesired
0x18001248c  mov     [rsp+230h+dwOptions], r14d; unsigned int
0x180012491  xor     r9d, r9d; lpClass
0x180012494  xor     r8d, r8d; Reserved
0x180012497  mov     rdx, [rsp+230h+lpSubKey]; lpSubKey
0x18001249c  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800124a3  call    cs:__imp_RegCreateKeyExW
0x1800124a9  test    eax, eax
0x1800124ab  jz      short loc_1800124E9
0x1800124ad  mov     rcx, [rbp+138h]; this
0x1800124b4  mov     r9d, eax; char *
0x1800124b7  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800124be  mov     edx, 8D9h; void *
0x1800124c3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800124c8  mov     ebx, eax
0x1800124ca  mov     rcx, [rsp+230h+hKey]; hKey
0x1800124cf  test    rcx, rcx
0x1800124d2  jz      short loc_1800124DA
0x1800124d4  call    cs:__imp_RegCloseKey
0x1800124da  lea     rcx, [rsp+230h+lpSubKey]
0x1800124df  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800124e4  jmp     loc_1800126F0
0x1800124e9  mov     [rsp+230h+pvData], r14d
0x1800124ee  mov     [rsp+230h+pcbData], 4
0x1800124f6  lea     rax, [rsp+230h+pcbData]
0x1800124fb  mov     [rsp+230h+lpSecurityAttributes], rax; pcbData
0x180012500  lea     rax, [rsp+230h+pvData]
0x180012505  mov     qword ptr [rsp+230h+samDesired], rax; pvData
0x18001250a  mov     qword ptr [rsp+230h+dwOptions], r14; int
0x18001250f  mov     r9d, 10h; dwFlags
0x180012515  lea     r8, aBuildnumber; "BuildNumber"
0x18001251c  xor     edx, edx; lpSubKey
0x18001251e  mov     rcx, [rsp+230h+hKey]; hkey
0x180012523  call    cs:__imp_RegGetValueW
0x180012529  mov     ebx, eax
0x18001252b  test    eax, eax
0x18001252d  jle     short loc_180012538
0x18001252f  movzx   ebx, ax
0x180012532  or      ebx, 80070000h
0x180012538  cmp     ebx, 80070002h
0x18001253e  jnz     short loc_1800125AE
0x180012540  mov     eax, cs:?g_dwBuildNumber@@3KA; ulong g_dwBuildNumber
0x180012546  mov     [rsp+230h+pcbData], eax
0x18001254a  mov     [rsp+230h+samDesired], 4; cbData
0x180012552  lea     rax, [rsp+230h+pcbData]
0x180012557  mov     qword ptr [rsp+230h+dwOptions], rax; int
0x18001255c  mov     r9d, 4; dwType
0x180012562  xor     r8d, r8d; Reserved
0x180012565  lea     rdx, aBuildnumber; "BuildNumber"
0x18001256c  mov     rcx, [rsp+230h+hKey]; hKey
0x180012571  call    cs:__imp_RegSetValueExW
0x180012577  mov     ebx, eax
0x180012579  test    eax, eax
0x18001257b  jle     short loc_180012586
0x18001257d  movzx   ebx, ax
0x180012580  or      ebx, 80070000h
0x180012586  test    ebx, ebx
0x180012588  jns     loc_1800126B7
0x18001258e  mov     edx, 8E1h; void *
0x180012593  mov     r9d, ebx; char *
0x180012596  mov     rcx, [rbp+138h]; this
0x18001259d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800125a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800125a9  jmp     loc_180012688
0x1800125ae  test    ebx, ebx
0x1800125b0  jns     short loc_1800125B9
0x1800125b2  mov     edx, 8E5h
0x1800125b7  jmp     short loc_180012593
0x1800125b9  lea     rdx, [rsp+230h+pvData]
0x1800125be  lea     rcx, [rbp+130h+var_180]
0x1800125c2  call    ??$BuildNumbers@AEAKAEAK@CUserProfile_Upgrade@ProfileTelemetry@@QEAAXAEAK0@Z; ProfileTelemetry::CUserProfile_Upgrade::BuildNumbers<ulong &,ulong &>(ulong &,ulong &)
0x1800125c7  mov     r9d, cs:?g_dwBuildNumber@@3KA; unsigned int
0x1800125ce  cmp     [rsp+230h+pvData], r9d
0x1800125d3  jnb     loc_1800126B7
0x1800125d9  lea     r8, aBuildnumber; "BuildNumber"
0x1800125e0  xor     edx, edx; unsigned __int16 *
0x1800125e2  mov     rcx, [rsp+230h+hKey]; HKEY
0x1800125e7  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800125ec  mov     ebx, eax
0x1800125ee  test    eax, eax
0x1800125f0  jns     short loc_1800125FC
0x1800125f2  mov     r9d, eax
0x1800125f5  mov     edx, 8EDh
0x1800125fa  jmp     short loc_180012596
0x1800125fc  mov     [rsp+230h+var_1C8], r14
0x180012601  mov     [rsp+230h+var_1C0], r14b
0x180012606  mov     rdx, [rdi+18h]; void *
0x18001260a  lea     rcx, [rsp+230h+var_1C8]; this
0x18001260f  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x180012614  mov     ebx, eax
0x180012616  test    eax, eax
0x180012618  jns     short loc_180012621
0x18001261a  mov     edx, 8F2h
0x18001261f  jmp     short loc_180012668
0x180012621  mov     [rbp+130h+var_190], r14
0x180012625  mov     [rbp+130h+var_184], r14d
0x180012629  mov     rax, [rdi+30h]
0x18001262d  mov     [rbp+130h+var_1A0], rax
0x180012631  mov     rax, [rdi+98h]
0x180012638  mov     [rbp+130h+var_198], rax
0x18001263c  mov     ecx, [rdi+0Ch]; unsigned int
0x18001263f  call    ?GetProfileTypeFromState@@YAKK@Z; GetProfileTypeFromState(ulong)
0x180012644  mov     [rbp+130h+var_188], eax
0x180012647  mov     r9, [rdi+18h]
0x18001264b  mov     r8d, [rdi+14h]
0x18001264f  lea     rdx, [rbp+130h+var_1A0]
0x180012653  mov     ecx, 10h
0x180012658  call    ?SendNotification@@YAJW4PROF_NOTIFY_EVENT_FLAGS@@PEAUPROF_NOTIFY_PARAM@@KPEAX@Z; SendNotification(PROF_NOTIFY_EVENT_FLAGS,PROF_NOTIFY_PARAM *,ulong,void *)
0x18001265d  mov     ebx, eax
0x18001265f  test    eax, eax
0x180012661  jns     short loc_1800126AD
0x180012663  mov     edx, 8F9h; void *
0x180012668  mov     r9d, eax; char *
0x18001266b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180012672  mov     rcx, [rbp+138h]; this
0x180012679  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001267e  lea     rcx, [rsp+230h+var_1C8]; this
0x180012683  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180012688  mov     rcx, [rsp+230h+hKey]; hKey
0x18001268d  test    rcx, rcx
0x180012690  jz      short loc_180012698
0x180012692  call    cs:__imp_RegCloseKey
0x180012698  lea     rcx, [rsp+230h+lpSubKey]
0x18001269d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800126a2  lea     rcx, [rbp+130h+var_180]; this
0x1800126a6  call    ??1CUserProfile_Upgrade@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::CUserProfile_Upgrade::~CUserProfile_Upgrade(void)
0x1800126ab  jmp     short loc_180012725
0x1800126ad  lea     rcx, [rsp+230h+var_1C8]; this
0x1800126b2  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x1800126b7  lea     rcx, [rbp+130h+var_180]
0x1800126bb  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800126c0  mov     rcx, [rsp+230h+hKey]; hKey
0x1800126c5  test    rcx, rcx
0x1800126c8  jz      short loc_1800126D0
0x1800126ca  call    cs:__imp_RegCloseKey
0x1800126d0  cmp     [rsp+230h+lpSubKey], r14
0x1800126d5  jz      short loc_1800126ED
0x1800126d7  call    cs:__imp_GetProcessHeap
0x1800126dd  mov     rcx, rax; hHeap
0x1800126e0  mov     r8, [rsp+230h+lpSubKey]; lpMem
0x1800126e5  xor     edx, edx; dwFlags
0x1800126e7  call    cs:__imp_HeapFree
0x1800126ed  mov     ebx, r14d
0x1800126f0  lea     rax, ??_7CUserProfile_Upgrade@ProfileTelemetry@@6B@; const ProfileTelemetry::CUserProfile_Upgrade::`vftable'
0x1800126f7  mov     [rbp+130h+var_180], rax
0x1800126fb  lea     rcx, [rbp+130h+var_180]
0x1800126ff  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180012704  lea     rcx, [rbp+130h+var_60]; this
0x18001270b  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180012710  lea     rcx, [rbp+130h+var_68]
0x180012717  call    ?reset@?$shared_object@V?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001271c  lea     rcx, [rbp+130h+var_178]
0x180012720  call    ??1?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180012725  mov     eax, ebx
0x180012727  mov     rcx, [rbp+130h+var_30]
0x18001272e  xor     rcx, rsp; StackCookie
0x180012731  call    __security_check_cookie
0x180012736  add     rsp, 218h
0x18001273d  pop     r14
0x18001273f  pop     rdi
0x180012740  pop     rbx
0x180012741  pop     rbp
0x180012742  retn
```
