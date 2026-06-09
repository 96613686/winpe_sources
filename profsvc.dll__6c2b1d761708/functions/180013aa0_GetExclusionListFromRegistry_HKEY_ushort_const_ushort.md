# GetExclusionListFromRegistry(HKEY__ *,ushort const *,ushort * *)

- ea: `0x180013aa0`
- end: `0x180013da8`
- name: `?GetExclusionListFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `776`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008fa0`

## callees

- `0x180005330`
- `0x18000d030`
- `0x18000e1a0`
- `0x1800130d0`
- `0x180013aa0`
- `0x1800146f0`
- `0x180014990`
- `0x180014aec`
- `0x18001a0f0`
- `0x18002cbb8`
- `0x180030ad0`
- `0x18004f6fc`
- `0x18004f870`
- `0x18004f8cc`
- `0x18004ff44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013b9d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013b9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013c3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013c3e`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180013c0a`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180013c0a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013be8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013be8`
- `USERENV!EnterCriticalPolicySection` at `0x180013acd`
- `USERENV!EnterCriticalPolicySection` at `0x180013acd`
- `USERENV!LeaveCriticalPolicySection` at `0x180013b52`
- `USERENV!LeaveCriticalPolicySection` at `0x180013b52`

## string_xrefs

- `0x180013b22`: `Failed to read "exclusion list" from policy setting. It may be empty`
- `0x180013b35`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetExclusionListFromRegistry(HKEY hKey, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  HKEY v6; // rbx
  unsigned int LocalSetting; // eax
  char v8; // dl
  HKEY v9; // rbx
  __int64 v10; // r9
  HKEY v11; // rdi
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r9
  int phkResult; // [rsp+20h] [rbp-60h]
  const char *lpSecurityAttributes; // [rsp+30h] [rbp-50h]
  _QWORD v23[3]; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v24[3]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  HKEY hKeyDest; // [rsp+C0h] [rbp+40h] BYREF
  HKEY v27; // [rsp+C8h] [rbp+48h] BYREF

  *a3 = 0;
  v6 = (HKEY)EnterCriticalPolicySection(0);
  hKeyDest = v6;
  if ( !v6 )
    GetLastError();
  v27 = 0;
  LocalSetting = Profile::GetLocalSetting(13, &v27, a2);
  if ( (int)(LocalSetting + 0x80000000) < 0 || (v8 = 1, LocalSetting == -2147024894) )
    v8 = 0;
  wil::details::in1diag3::Log_HrIfMsg(
    retaddr,
    (void *)0x366,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
    (const char *)LocalSetting,
    v8,
    (bool)"Failed to read \"exclusion list\" from policy setting. It may be empty",
    lpSecurityAttributes);
  if ( v6 && !LeaveCriticalPolicySection(v6) )
    GetLastError();
  v9 = 0;
  memset(v23, 0, sizeof(v23));
  hKeyDest = 0;
  if ( !RegOpenKeyExW(hKey, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", 0, 0x20019u, &hKeyDest)
    || (wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKeyDest,
          0),
        !RegCreateKeyExW(
           hKey,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &hKeyDest,
           0))
    && !RegCopyTreeW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\UserDefaults",
          hKeyDest) )
  {
    LOBYTE(v10) = 1;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
      v23,
      hKeyDest,
      L"ExcludeProfileDirs",
      v10);
    v9 = (HKEY)v23[0];
  }
  if ( hKeyDest )
    RegCloseKey(hKeyDest);
  v11 = v27;
  if ( !v27 )
  {
    if ( !v9 || !*(_WORD *)v9 )
    {
      ProfileTelemetry::BothPolicyAndUserExclusionListEmpty();
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v23);
      return 0;
    }
    hKeyDest = v9;
    ProfileTelemetry::PolicyListEmptyUseUserList<unsigned short const *>(&hKeyDest);
    v12 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(v23, a3);
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = 918;
LABEL_35:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)(unsigned int)v12,
        phkResult);
      goto LABEL_30;
    }
    goto LABEL_29;
  }
  if ( !v9 || !*(_WORD *)v9 )
  {
    hKeyDest = v27;
    ProfileTelemetry::UserListEmptyUsePolicyList<unsigned short *>(&hKeyDest);
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)v11 + v20) );
    v12 = _AllocStringWorker<CTLocalAllocPolicy>(v19, v18, v11);
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = 925;
      goto LABEL_35;
    }
    goto LABEL_29;
  }
  memset(v24, 0, sizeof(v24));
  v16 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
          v24,
          L"%s; %s",
          v9,
          v27);
  v13 = v16;
  if ( v16 >= 0 )
  {
    hKeyDest = (HKEY)v24[0];
    ProfileTelemetry::MergedPolicyAndUserList<unsigned short const *>(&hKeyDest);
    v16 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(v24, a3);
    v13 = v16;
    if ( v16 >= 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v24);
LABEL_29:
      v13 = 0;
      goto LABEL_30;
    }
    v17 = 935;
  }
  else
  {
    v17 = 931;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v17,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
    (const char *)(unsigned int)v16,
    phkResult);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v24);
LABEL_30:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v23);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
  return v13;
}

```

## disassembly

```asm
0x180013aa0  mov     [rsp-28h+arg_0], rbx
0x180013aa5  mov     [rsp-28h+arg_8], rsi
0x180013aaa  push    rbp
0x180013aab  push    rdi
0x180013aac  push    r12
0x180013aae  push    r14
0x180013ab0  push    r15
0x180013ab2  mov     rbp, rsp
0x180013ab5  sub     rsp, 80h
0x180013abc  mov     rsi, r8
0x180013abf  mov     rdi, rdx
0x180013ac2  mov     r14, rcx
0x180013ac5  xor     r15d, r15d
0x180013ac8  mov     [r8], r15
0x180013acb  xor     ecx, ecx; bMachine
0x180013acd  call    cs:__imp_EnterCriticalPolicySection
0x180013ad4  nop     dword ptr [rax+rax+00h]
0x180013ad9  mov     rbx, rax
0x180013adc  mov     [rbp+hKeyDest], rax
0x180013ae0  test    rax, rax
0x180013ae3  jnz     short loc_180013AF1
0x180013ae5  call    cs:__imp_GetLastError
0x180013aec  nop     dword ptr [rax+rax+00h]
0x180013af1  mov     [rbp+arg_18], r15
0x180013af5  mov     r8, rdi
0x180013af8  lea     rdx, [rbp+arg_18]
0x180013afc  mov     ecx, 0Dh
0x180013b01  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@PEAPEAGPEBGW4USERSTATE_SETTING_SOURCES@@PEAX@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,ushort * *,ushort const *,USERSTATE_SETTING_SOURCES,void *)
0x180013b06  mov     edx, 80000000h
0x180013b0b  lea     ecx, [rax+rdx]
0x180013b0e  test    edx, ecx
0x180013b10  jnz     short loc_180013B1B
0x180013b12  cmp     eax, 80070002h
0x180013b17  mov     dl, 1
0x180013b19  jnz     short loc_180013B1E
0x180013b1b  mov     dl, r15b
0x180013b1e  mov     rcx, [rbp+28h]; this
0x180013b22  lea     r8, aFailedToReadEx; "Failed to read \"exclusion list\" from "...
0x180013b29  mov     qword ptr [rsp+80h+samDesired], r8; bool
0x180013b2e  mov     byte ptr [rsp+80h+phkResult], dl; char
0x180013b32  mov     r9d, eax; char *
0x180013b35  lea     r12, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013b3c  mov     r8, r12; unsigned int
0x180013b3f  mov     edx, 366h; void *
0x180013b44  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180013b49  nop
0x180013b4a  test    rbx, rbx
0x180013b4d  jz      short loc_180013B6E
0x180013b4f  mov     rcx, rbx; hSection
0x180013b52  call    cs:__imp_LeaveCriticalPolicySection
0x180013b59  nop     dword ptr [rax+rax+00h]
0x180013b5e  test    eax, eax
0x180013b60  jnz     short loc_180013B6E
0x180013b62  call    cs:__imp_GetLastError
0x180013b69  nop     dword ptr [rax+rax+00h]
0x180013b6e  mov     rbx, r15
0x180013b71  mov     [rbp+var_30], rbx
0x180013b75  mov     [rbp+var_28], r15
0x180013b79  mov     [rbp+var_20], r15
0x180013b7d  mov     [rbp+hKeyDest], r15
0x180013b81  lea     rax, [rbp+hKeyDest]
0x180013b85  mov     [rsp+80h+phkResult], rax; phkResult
0x180013b8a  mov     r9d, 20019h; samDesired
0x180013b90  xor     r8d, r8d; ulOptions
0x180013b93  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x180013b9a  mov     rcx, r14; hKey
0x180013b9d  call    cs:__imp_RegOpenKeyExW
0x180013ba4  nop     dword ptr [rax+rax+00h]
0x180013ba9  test    eax, eax
0x180013bab  jz      short loc_180013C1A
0x180013bad  xor     edx, edx
0x180013baf  lea     rcx, [rbp+hKeyDest]
0x180013bb3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180013bb8  mov     [rsp+80h+lpdwDisposition], r15; lpdwDisposition
0x180013bbd  lea     rax, [rbp+hKeyDest]
0x180013bc1  mov     [rsp+80h+var_48], rax; phkResult
0x180013bc6  mov     [rsp+80h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180013bcb  mov     [rsp+80h+samDesired], 0F003Fh; samDesired
0x180013bd3  mov     dword ptr [rsp+80h+phkResult], r15d; int
0x180013bd8  xor     r9d, r9d; lpClass
0x180013bdb  xor     r8d, r8d; Reserved
0x180013bde  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x180013be5  mov     rcx, r14; hKey
0x180013be8  call    cs:__imp_RegCreateKeyExW
0x180013bef  nop     dword ptr [rax+rax+00h]
0x180013bf4  test    eax, eax
0x180013bf6  jnz     short loc_180013C35
0x180013bf8  mov     r8, [rbp+hKeyDest]; hKeyDest
0x180013bfc  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180013c03  mov     rcx, 0FFFFFFFF80000002h; hKeySrc
0x180013c0a  call    cs:__imp_RegCopyTreeW
0x180013c11  nop     dword ptr [rax+rax+00h]
0x180013c16  test    eax, eax
0x180013c18  jnz     short loc_180013C35
0x180013c1a  mov     r9b, 1
0x180013c1d  lea     r8, aExcludeprofile; "ExcludeProfileDirs"
0x180013c24  mov     rdx, [rbp+hKeyDest]
0x180013c28  lea     rcx, [rbp+var_30]
0x180013c2c  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x180013c31  mov     rbx, [rbp+var_30]
0x180013c35  mov     rcx, [rbp+hKeyDest]; hKey
0x180013c39  test    rcx, rcx
0x180013c3c  jz      short loc_180013C4A
0x180013c3e  call    cs:__imp_RegCloseKey
0x180013c45  nop     dword ptr [rax+rax+00h]
0x180013c4a  mov     rdi, [rbp+arg_18]
0x180013c4e  test    rdi, rdi
0x180013c51  jnz     short loc_180013CA1
0x180013c53  test    rbx, rbx
0x180013c56  jz      short loc_180013C8B
0x180013c58  cmp     [rbx], r15w
0x180013c5c  jz      short loc_180013C8B
0x180013c5e  mov     [rbp+hKeyDest], rbx
0x180013c62  lea     rcx, [rbp+hKeyDest]
0x180013c66  call    ??$PolicyListEmptyUseUserList@PEBG@ProfileTelemetry@@SAX$$QEAPEBG@Z; ProfileTelemetry::PolicyListEmptyUseUserList<ushort const *>(ushort const * &&)
0x180013c6b  mov     rdx, rsi
0x180013c6e  lea     rcx, [rbp+var_30]
0x180013c72  call    ?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)
0x180013c77  mov     ebx, eax
0x180013c79  test    eax, eax
0x180013c7b  jns     loc_180013D2E
0x180013c81  mov     edx, 396h
0x180013c86  jmp     loc_180013D96
0x180013c8b  call    ?BothPolicyAndUserExclusionListEmpty@ProfileTelemetry@@SAXXZ; ProfileTelemetry::BothPolicyAndUserExclusionListEmpty(void)
0x180013c90  lea     rcx, [rbp+var_30]
0x180013c94  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180013c99  nop
0x180013c9a  xor     eax, eax
0x180013c9c  jmp     loc_180013D46
0x180013ca1  test    rbx, rbx
0x180013ca4  jz      loc_180013D63
0x180013caa  cmp     [rbx], r15w
0x180013cae  jz      loc_180013D63
0x180013cb4  mov     [rbp+var_18], r15
0x180013cb8  mov     [rbp+var_10], r15
0x180013cbc  mov     [rbp+var_8], r15
0x180013cc0  mov     r9, rdi
0x180013cc3  mov     r8, rbx
0x180013cc6  lea     rdx, aSS; "%s; %s"
0x180013ccd  lea     rcx, [rbp+var_18]
0x180013cd1  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180013cd6  mov     ebx, eax
0x180013cd8  test    eax, eax
0x180013cda  jns     short loc_180013CFB
0x180013cdc  mov     edx, 3A3h; void *
0x180013ce1  mov     r8, r12; unsigned int
0x180013ce4  mov     r9d, eax; char *
0x180013ce7  mov     rcx, [rbp+28h]; this
0x180013ceb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013cf0  lea     rcx, [rbp+var_18]
0x180013cf4  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180013cf9  jmp     short loc_180013D31
0x180013cfb  mov     rax, [rbp+var_18]
0x180013cff  mov     [rbp+hKeyDest], rax
0x180013d03  lea     rcx, [rbp+hKeyDest]
0x180013d07  call    ??$MergedPolicyAndUserList@PEBG@ProfileTelemetry@@SAX$$QEAPEBG@Z; ProfileTelemetry::MergedPolicyAndUserList<ushort const *>(ushort const * &&)
0x180013d0c  mov     rdx, rsi
0x180013d0f  lea     rcx, [rbp+var_18]
0x180013d13  call    ?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)
0x180013d18  mov     ebx, eax
0x180013d1a  test    eax, eax
0x180013d1c  jns     short loc_180013D25
0x180013d1e  mov     edx, 3A7h
0x180013d23  jmp     short loc_180013CE1
0x180013d25  lea     rcx, [rbp+var_18]
0x180013d29  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180013d2e  mov     ebx, r15d
0x180013d31  lea     rcx, [rbp+var_30]
0x180013d35  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180013d3a  nop
0x180013d3b  lea     rcx, [rbp+arg_18]
0x180013d3f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180013d44  mov     eax, ebx
0x180013d46  lea     r11, [rsp+80h+var_s0]
0x180013d4e  mov     rbx, [r11+30h]
0x180013d52  mov     rsi, [r11+38h]
0x180013d56  mov     rsp, r11
0x180013d59  pop     r15
0x180013d5b  pop     r14
0x180013d5d  pop     r12
0x180013d5f  pop     rdi
0x180013d60  pop     rbp
0x180013d61  retn
0x180013d63  mov     [rbp+hKeyDest], rdi
0x180013d67  lea     rcx, [rbp+hKeyDest]
0x180013d6b  call    ??$UserListEmptyUsePolicyList@PEAG@ProfileTelemetry@@SAX$$QEAPEAG@Z; ProfileTelemetry::UserListEmptyUsePolicyList<ushort *>(ushort * &&)
0x180013d70  or      r9, 0FFFFFFFFFFFFFFFFh
0x180013d74  inc     r9
0x180013d77  cmp     [rdi+r9*2], r15w
0x180013d7c  jnz     short loc_180013D74
0x180013d7e  mov     qword ptr [rsp+80h+samDesired], rsi
0x180013d83  mov     r8, rdi
0x180013d86  call    ??$_AllocStringWorker@VCTLocalAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTLocalAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180013d8b  mov     ebx, eax
0x180013d8d  test    eax, eax
0x180013d8f  jns     short loc_180013D2E
0x180013d91  mov     edx, 39Dh; void *
0x180013d96  mov     r8, r12; unsigned int
0x180013d99  mov     r9d, eax; char *
0x180013d9c  mov     rcx, [rbp+28h]; this
0x180013da0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013da5  jmp     short loc_180013D31
```
