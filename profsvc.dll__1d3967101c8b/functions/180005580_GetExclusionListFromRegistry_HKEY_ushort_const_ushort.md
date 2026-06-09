# GetExclusionListFromRegistry(HKEY__ *,ushort const *,ushort * *)

- ea: `0x180005580`
- end: `0x18000585b`
- name: `?GetExclusionListFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `731`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b540`

## callees

- `0x1800053a0`
- `0x1800053cc`
- `0x180005430`
- `0x180005580`
- `0x180006b10`
- `0x180007978`
- `0x180010f30`
- `0x1800111a0`
- `0x180016250`
- `0x18001f060`
- `0x18002aab0`
- `0x18002d2d8`
- `0x18004c6e8`
- `0x18004c854`
- `0x18004c8ac`
- `0x18004cc54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005630`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005665`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005665`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800056f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800056f4`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800056c6`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800056c6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800056aa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800056aa`
- `USERENV!EnterCriticalPolicySection` at `0x1800055ad`
- `USERENV!EnterCriticalPolicySection` at `0x1800055ad`
- `USERENV!LeaveCriticalPolicySection` at `0x180005626`
- `USERENV!LeaveCriticalPolicySection` at `0x180005626`

## string_xrefs

- `0x1800055f6`: `Failed to read "exclusion list" from policy setting. It may be empty`
- `0x180005609`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetExclusionListFromRegistry(HKEY hKey, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  HKEY v6; // rbx
  unsigned int LocalSetting; // eax
  char v8; // dl
  HKEY v9; // rbx
  HKEY v10; // rdi
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r9
  int phkResult; // [rsp+20h] [rbp-60h]
  const char *lpSecurityAttributes; // [rsp+30h] [rbp-50h]
  _QWORD v22[3]; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v23[3]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  HKEY hKeyDest; // [rsp+C0h] [rbp+40h] BYREF
  HKEY v26; // [rsp+C8h] [rbp+48h] BYREF

  *a3 = 0;
  v6 = (HKEY)EnterCriticalPolicySection(0);
  hKeyDest = v6;
  if ( !v6 )
    GetLastError();
  v26 = 0;
  LocalSetting = Profile::GetLocalSetting(13, &v26, a2);
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
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
      (__int64)v23,
      hKeyDest,
      L"ExcludeProfileDirs",
      1);
    v9 = (HKEY)v23[0];
  }
  if ( hKeyDest )
    RegCloseKey(hKeyDest);
  v10 = v26;
  if ( v26 )
  {
    if ( !v9 || !*(_WORD *)v9 )
    {
      hKeyDest = v26;
      ProfileTelemetry::UserListEmptyUsePolicyList<unsigned short *>((__int64 *)&hKeyDest);
      v19 = -1;
      do
        ++v19;
      while ( *((_WORD *)v10 + v19) );
      v11 = _AllocStringWorker<CTLocalAllocPolicy>(v18, v17, v10);
      v12 = v11;
      if ( v11 < 0 )
      {
        v13 = 925;
        goto LABEL_37;
      }
      goto LABEL_31;
    }
    memset(v22, 0, sizeof(v22));
    v15 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
            v22,
            L"%s; %s",
            v9,
            v26);
    v12 = v15;
    if ( v15 >= 0 )
    {
      hKeyDest = (HKEY)v22[0];
      ProfileTelemetry::MergedPolicyAndUserList<unsigned short const *>(&hKeyDest);
      v15 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(
              (__int64)v22,
              a3);
      v12 = v15;
      if ( v15 >= 0 )
      {
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v22);
LABEL_31:
        v12 = 0;
        goto LABEL_32;
      }
      v16 = 935;
    }
    else
    {
      v16 = 931;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)(unsigned int)v15,
      phkResult);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v22);
LABEL_32:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v23);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v26);
    return v12;
  }
  if ( v9 && *(_WORD *)v9 )
  {
    hKeyDest = v9;
    ProfileTelemetry::PolicyListEmptyUseUserList<unsigned short const *>((__int64 *)&hKeyDest);
    v11 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(
            (__int64)v23,
            a3);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = 918;
LABEL_37:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)(unsigned int)v11,
        phkResult);
      goto LABEL_32;
    }
    goto LABEL_31;
  }
  ProfileTelemetry::BothPolicyAndUserExclusionListEmpty();
  if ( v9 )
    Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v9);
  return 0;
}

```

## disassembly

```asm
0x180005580  mov     [rsp-28h+arg_0], rbx
0x180005585  mov     [rsp-28h+arg_8], rsi
0x18000558a  push    rbp
0x18000558b  push    rdi
0x18000558c  push    r12
0x18000558e  push    r14
0x180005590  push    r15
0x180005592  mov     rbp, rsp
0x180005595  sub     rsp, 80h
0x18000559c  mov     rsi, r8
0x18000559f  mov     rdi, rdx
0x1800055a2  mov     r14, rcx
0x1800055a5  xor     r15d, r15d
0x1800055a8  mov     [r8], r15
0x1800055ab  xor     ecx, ecx; bMachine
0x1800055ad  call    cs:__imp_EnterCriticalPolicySection
0x1800055b3  mov     rbx, rax
0x1800055b6  mov     [rbp+hKeyDest], rax
0x1800055ba  test    rax, rax
0x1800055bd  jnz     short loc_1800055C5
0x1800055bf  call    cs:__imp_GetLastError
0x1800055c5  mov     [rbp+arg_18], r15
0x1800055c9  mov     r8, rdi
0x1800055cc  lea     rdx, [rbp+arg_18]
0x1800055d0  mov     ecx, 0Dh
0x1800055d5  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@PEAPEAGPEBGW4USERSTATE_SETTING_SOURCES@@PEAX@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,ushort * *,ushort const *,USERSTATE_SETTING_SOURCES,void *)
0x1800055da  mov     edx, 80000000h
0x1800055df  lea     ecx, [rax+rdx]
0x1800055e2  test    edx, ecx
0x1800055e4  jnz     short loc_1800055EF
0x1800055e6  cmp     eax, 80070002h
0x1800055eb  mov     dl, 1
0x1800055ed  jnz     short loc_1800055F2
0x1800055ef  mov     dl, r15b
0x1800055f2  mov     rcx, [rbp+28h]; this
0x1800055f6  lea     r8, aFailedToReadEx; "Failed to read \"exclusion list\" from "...
0x1800055fd  mov     qword ptr [rsp+80h+samDesired], r8; bool
0x180005602  mov     byte ptr [rsp+80h+phkResult], dl; char
0x180005606  mov     r9d, eax; char *
0x180005609  lea     r12, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180005610  mov     r8, r12; unsigned int
0x180005613  mov     edx, 366h; void *
0x180005618  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18000561d  nop
0x18000561e  test    rbx, rbx
0x180005621  jz      short loc_180005636
0x180005623  mov     rcx, rbx; hSection
0x180005626  call    cs:__imp_LeaveCriticalPolicySection
0x18000562c  test    eax, eax
0x18000562e  jnz     short loc_180005636
0x180005630  call    cs:__imp_GetLastError
0x180005636  mov     rbx, r15
0x180005639  mov     [rbp+var_18], rbx
0x18000563d  mov     [rbp+var_10], r15
0x180005641  mov     [rbp+var_8], r15
0x180005645  mov     [rbp+hKeyDest], r15
0x180005649  lea     rax, [rbp+hKeyDest]
0x18000564d  mov     [rsp+80h+phkResult], rax; phkResult
0x180005652  mov     r9d, 20019h; samDesired
0x180005658  xor     r8d, r8d; ulOptions
0x18000565b  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x180005662  mov     rcx, r14; hKey
0x180005665  call    cs:__imp_RegOpenKeyExW
0x18000566b  test    eax, eax
0x18000566d  jz      short loc_1800056D0
0x18000566f  xor     edx, edx
0x180005671  lea     rcx, [rbp+hKeyDest]
0x180005675  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000567a  mov     [rsp+80h+lpdwDisposition], r15; lpdwDisposition
0x18000567f  lea     rax, [rbp+hKeyDest]
0x180005683  mov     [rsp+80h+var_48], rax; phkResult
0x180005688  mov     [rsp+80h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18000568d  mov     [rsp+80h+samDesired], 0F003Fh; samDesired
0x180005695  mov     dword ptr [rsp+80h+phkResult], r15d; int
0x18000569a  xor     r9d, r9d; lpClass
0x18000569d  xor     r8d, r8d; Reserved
0x1800056a0  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800056a7  mov     rcx, r14; hKey
0x1800056aa  call    cs:__imp_RegCreateKeyExW
0x1800056b0  test    eax, eax
0x1800056b2  jnz     short loc_1800056EB
0x1800056b4  mov     r8, [rbp+hKeyDest]; hKeyDest
0x1800056b8  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800056bf  mov     rcx, 0FFFFFFFF80000002h; hKeySrc
0x1800056c6  call    cs:__imp_RegCopyTreeW
0x1800056cc  test    eax, eax
0x1800056ce  jnz     short loc_1800056EB
0x1800056d0  mov     r9b, 1
0x1800056d3  lea     r8, aExcludeprofile; "ExcludeProfileDirs"
0x1800056da  mov     rdx, [rbp+hKeyDest]
0x1800056de  lea     rcx, [rbp+var_18]
0x1800056e2  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x1800056e7  mov     rbx, [rbp+var_18]
0x1800056eb  mov     rcx, [rbp+hKeyDest]; hKey
0x1800056ef  test    rcx, rcx
0x1800056f2  jz      short loc_1800056FA
0x1800056f4  call    cs:__imp_RegCloseKey
0x1800056fa  mov     rdi, [rbp+arg_18]
0x1800056fe  test    rdi, rdi
0x180005701  jnz     short loc_180005755
0x180005703  test    rbx, rbx
0x180005706  jz      short loc_18000573B
0x180005708  cmp     [rbx], r15w
0x18000570c  jz      short loc_18000573B
0x18000570e  mov     [rbp+hKeyDest], rbx
0x180005712  lea     rcx, [rbp+hKeyDest]
0x180005716  call    ??$PolicyListEmptyUseUserList@PEBG@ProfileTelemetry@@SAX$$QEAPEBG@Z; ProfileTelemetry::PolicyListEmptyUseUserList<ushort const *>(ushort const * &&)
0x18000571b  mov     rdx, rsi
0x18000571e  lea     rcx, [rbp+var_18]
0x180005722  call    ?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)
0x180005727  mov     ebx, eax
0x180005729  test    eax, eax
0x18000572b  jns     loc_1800057E2
0x180005731  mov     edx, 396h
0x180005736  jmp     loc_180005849
0x18000573b  call    ?BothPolicyAndUserExclusionListEmpty@ProfileTelemetry@@SAXXZ; ProfileTelemetry::BothPolicyAndUserExclusionListEmpty(void)
0x180005740  test    rbx, rbx
0x180005743  jz      short loc_18000574E
0x180005745  mov     rcx, rbx
0x180005748  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18000574d  nop
0x18000574e  xor     eax, eax
0x180005750  jmp     loc_1800057FA
0x180005755  test    rbx, rbx
0x180005758  jz      loc_180005816
0x18000575e  cmp     [rbx], r15w
0x180005762  jz      loc_180005816
0x180005768  mov     [rbp+var_30], r15
0x18000576c  mov     [rbp+var_28], r15
0x180005770  mov     [rbp+var_20], r15
0x180005774  mov     r9, rdi
0x180005777  mov     r8, rbx
0x18000577a  lea     rdx, aSS; "%s; %s"
0x180005781  lea     rcx, [rbp+var_30]
0x180005785  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000578a  mov     ebx, eax
0x18000578c  test    eax, eax
0x18000578e  jns     short loc_1800057AF
0x180005790  mov     edx, 3A3h; void *
0x180005795  mov     r8, r12; unsigned int
0x180005798  mov     r9d, eax; char *
0x18000579b  mov     rcx, [rbp+28h]; this
0x18000579f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057a4  lea     rcx, [rbp+var_30]
0x1800057a8  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800057ad  jmp     short loc_1800057E5
0x1800057af  mov     rax, [rbp+var_30]
0x1800057b3  mov     [rbp+hKeyDest], rax
0x1800057b7  lea     rcx, [rbp+hKeyDest]
0x1800057bb  call    ??$MergedPolicyAndUserList@PEBG@ProfileTelemetry@@SAX$$QEAPEBG@Z; ProfileTelemetry::MergedPolicyAndUserList<ushort const *>(ushort const * &&)
0x1800057c0  mov     rdx, rsi
0x1800057c3  lea     rcx, [rbp+var_30]
0x1800057c7  call    ?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)
0x1800057cc  mov     ebx, eax
0x1800057ce  test    eax, eax
0x1800057d0  jns     short loc_1800057D9
0x1800057d2  mov     edx, 3A7h
0x1800057d7  jmp     short loc_180005795
0x1800057d9  lea     rcx, [rbp+var_30]
0x1800057dd  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800057e2  mov     ebx, r15d
0x1800057e5  lea     rcx, [rbp+var_18]
0x1800057e9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800057ee  nop
0x1800057ef  lea     rcx, [rbp+arg_18]
0x1800057f3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800057f8  mov     eax, ebx
0x1800057fa  lea     r11, [rsp+80h+var_s0]
0x180005802  mov     rbx, [r11+30h]
0x180005806  mov     rsi, [r11+38h]
0x18000580a  mov     rsp, r11
0x18000580d  pop     r15
0x18000580f  pop     r14
0x180005811  pop     r12
0x180005813  pop     rdi
0x180005814  pop     rbp
0x180005815  retn
0x180005816  mov     [rbp+hKeyDest], rdi
0x18000581a  lea     rcx, [rbp+hKeyDest]
0x18000581e  call    ??$UserListEmptyUsePolicyList@PEAG@ProfileTelemetry@@SAX$$QEAPEAG@Z; ProfileTelemetry::UserListEmptyUsePolicyList<ushort *>(ushort * &&)
0x180005823  or      r9, 0FFFFFFFFFFFFFFFFh
0x180005827  inc     r9
0x18000582a  cmp     [rdi+r9*2], r15w
0x18000582f  jnz     short loc_180005827
0x180005831  mov     qword ptr [rsp+80h+samDesired], rsi
0x180005836  mov     r8, rdi
0x180005839  call    ??$_AllocStringWorker@VCTLocalAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTLocalAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18000583e  mov     ebx, eax
0x180005840  test    eax, eax
0x180005842  jns     short loc_1800057E2
0x180005844  mov     edx, 39Dh; void *
0x180005849  mov     r8, r12; unsigned int
0x18000584c  mov     r9d, eax; char *
0x18000584f  mov     rcx, [rbp+28h]; this
0x180005853  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005858  jmp     short loc_1800057E5
```
