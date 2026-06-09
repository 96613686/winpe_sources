# NtlmQueryPolicyChangeCallback(void *)

- ea: `0x180047f50`
- end: `0x180048048`
- name: `?NtlmQueryPolicyChangeCallback@@YAKPEAX@Z`
- size: `248`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180048a10`
- `0x180049da8`
- `0x18005a58c`

## callees

- `0x18002049c`
- `0x18002e6a0`
- `0x18002ee7c`
- `0x180047f50`
- `0x1800486ac`
- `0x180066870`
- `0x180068cd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047f5b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047f5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004803b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004803b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047f9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047f9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NtlmQueryPolicyChangeCallback(void *a1)
{
  unsigned int v1; // eax
  NtlmHelper::Blocking::PolicyEngine *v2; // rcx
  _QWORD v4[3]; // [rsp+30h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp+18h] BYREF

  AcquireSRWLockExclusive(&stru_180089C78);
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\NTLM\\Parameters",
         0,
         0x20019u,
         &phkResult);
  if ( v1 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5c1f7330bd6c32ac7f45bfafe678c964_Traceguids, v1);
  v4[0] = L"LogEnhancedAuditEvents";
  v4[1] = 22;
  NtlmDoEnhancedAuditing = (unsigned int)NtlmHelper::RegistryReader::ReadDword(&phkResult, v4, 1) != 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_NtlmBlockingPolicy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NTLMless_NtlmBlockingPolicy>::GetImpl'::`2'::impl) )
    NtlmHelper::Blocking::PolicyEngine::UpdatePolicy(v2, (struct NtlmHelper::RegistryReader *)&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  ReleaseSRWLockExclusive(&stru_180089C78);
  return 0;
}

```

## disassembly

```asm
0x180047f50  sub     rsp, 48h
0x180047f54  lea     rcx, stru_180089C78; SRWLock
0x180047f5b  call    cs:__imp_AcquireSRWLockExclusive
0x180047f61  mov     [rsp+48h+arg_9], 1
0x180047f66  mov     [rsp+48h+arg_10], 0
0x180047f6f  xor     edx, edx
0x180047f71  lea     rcx, [rsp+48h+arg_10]
0x180047f76  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180047f7b  lea     rax, [rsp+48h+arg_10]
0x180047f80  mov     [rsp+48h+phkResult], rax; phkResult
0x180047f85  mov     r9d, 20019h; samDesired
0x180047f8b  xor     r8d, r8d; ulOptions
0x180047f8e  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180047f95  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180047f9c  call    cs:__imp_RegOpenKeyExW
0x180047fa2  test    eax, eax
0x180047fa4  jz      short loc_180047FDB
0x180047fa6  lea     rdx, WPP_GLOBAL_Control
0x180047fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180047fb4  cmp     rcx, rdx
0x180047fb7  jz      short loc_180047FDB
0x180047fb9  test    dword ptr [rcx+1Ch], 100h
0x180047fc0  jz      short loc_180047FDB
0x180047fc2  mov     edx, 0Ah
0x180047fc7  mov     r9d, eax
0x180047fca  lea     r8, WPP_5c1f7330bd6c32ac7f45bfafe678c964_Traceguids
0x180047fd1  mov     rcx, [rcx+10h]
0x180047fd5  call    WPP_SF_d
0x180047fda  nop
0x180047fdb  lea     rax, aLogenhancedaud; "LogEnhancedAuditEvents"
0x180047fe2  mov     [rsp+48h+var_18], rax
0x180047fe7  mov     [rsp+48h+var_10], 16h
0x180047ff0  mov     r8d, 1
0x180047ff6  lea     rdx, [rsp+48h+var_18]
0x180047ffb  lea     rcx, [rsp+48h+arg_10]
0x180048000  call    ?ReadDword@RegistryReader@NtlmHelper@@QEBAKV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@K@Z; NtlmHelper::RegistryReader::ReadDword(utl::basic_string_view<ushort,utl::char_traits<ushort>>,ulong)
0x180048005  test    eax, eax
0x180048007  setnz   cs:NtlmDoEnhancedAuditing
0x18004800e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NTLMless_NtlmBlockingPolicy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless_NtlmBlockingPolicy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_NtlmBlockingPolicy> `wil::Feature<__WilFeatureTraits_Feature_NTLMless_NtlmBlockingPolicy>::GetImpl(void)'::`2'::impl
0x180048015  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless_NtlmBlockingPolicy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_NtlmBlockingPolicy>::__private_IsEnabled(void)
0x18004801a  test    al, al
0x18004801c  jz      short loc_180048029
0x18004801e  lea     rdx, [rsp+48h+arg_10]; struct NtlmHelper::RegistryReader *
0x180048023  call    ?UpdatePolicy@PolicyEngine@Blocking@NtlmHelper@@QEAAXAEAVRegistryReader@3@@Z; NtlmHelper::Blocking::PolicyEngine::UpdatePolicy(NtlmHelper::RegistryReader &)
0x180048028  nop
0x180048029  lea     rcx, [rsp+48h+arg_10]
0x18004802e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180048033  nop
0x180048034  lea     rcx, stru_180089C78; SRWLock
0x18004803b  call    cs:__imp_ReleaseSRWLockExclusive
0x180048041  xor     eax, eax
0x180048043  add     rsp, 48h
0x180048047  retn
```
