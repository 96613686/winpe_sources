# NtlmHelper::Blocking::PolicyEngine::UpdatePolicy(NtlmHelper::RegistryReader &)

- ea: `0x180068cd8`
- end: `0x180068eba`
- name: `?UpdatePolicy@PolicyEngine@Blocking@NtlmHelper@@QEAAXAEAVRegistryReader@3@@Z`
- size: `482`
- prototype: `void __fastcall(NtlmHelper::Blocking::PolicyEngine *__hidden this, struct NtlmHelper::RegistryReader *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180047f50`

## callees

- `0x18002e2f8`
- `0x18002ffb0`
- `0x18004e4c4`
- `0x1800668e0`
- `0x180067090`
- `0x180068cd8`
- `0x180068ec0`
- `0x180068efc`
- `0x180068f38`
- `0x180068f74`
- `0x18006adb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068e3c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068e3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068e8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068e8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NtlmHelper::Blocking::PolicyEngine::UpdatePolicy(
        NtlmHelper::Blocking::PolicyEngine *this,
        struct NtlmHelper::RegistryReader *a2)
{
  unsigned __int8 IsEnabled; // al
  unsigned __int8 v4; // al
  unsigned __int8 v5; // al
  unsigned __int8 v6; // al
  __int64 *v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rdi
  const struct std::nothrow_t *v10; // rdx
  void *v11; // rcx
  const wchar_t *v12; // [rsp+20h] [rbp-20h] BYREF
  __int64 v13; // [rsp+28h] [rbp-18h]
  _BYTE v14[16]; // [rsp+30h] [rbp-10h] BYREF
  struct NtlmHelper::RegistryReader *v15; // [rsp+50h] [rbp+10h] BYREF

  v15 = a2;
  v12 = L"BlockDomainAccountSSO";
  v13 = 21;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_BlockDomainUserSSONtlm>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NTLMless_BlockDomainUserSSONtlm>::GetImpl'::`2'::impl);
  g_ntlmPolicyEngine = lambda_63e3a7b7ae56bddb12dc9bc2c321eec4_::operator()(&v15, &v12, 2 * (unsigned int)IsEnabled);
  v12 = L"BlockDomainControllerAuth";
  v13 = 25;
  v4 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_BlockDomainControllerNtlm>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NTLMless_BlockDomainControllerNtlm>::GetImpl'::`2'::impl);
  LODWORD(qword_180089AA4) = lambda_63e3a7b7ae56bddb12dc9bc2c321eec4_::operator()(&v15, &v12, 2 * (unsigned int)v4);
  v12 = L"EnforceMachineBinding";
  v13 = 21;
  HIDWORD(qword_180089AA4) = lambda_63e3a7b7ae56bddb12dc9bc2c321eec4_::operator()(&v15, &v12, 0);
  v12 = L"BlockHardcodedCalls";
  v13 = 19;
  v5 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_BlockHardcodedNtlm>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NTLMless_BlockHardcodedNtlm>::GetImpl'::`2'::impl);
  dword_180089AAC = lambda_63e3a7b7ae56bddb12dc9bc2c321eec4_::operator()(&v15, &v12, 2 * (unsigned int)v5);
  v12 = L"BlockAll";
  v13 = 8;
  v6 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_BlockAllOfNtlm>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NTLMless_BlockAllOfNtlm>::GetImpl'::`2'::impl);
  dword_180089AB0 = lambda_63e3a7b7ae56bddb12dc9bc2c321eec4_::operator()(&v15, &v12, 2 * (unsigned int)v6);
  v12 = L"EnhancedMachineBlockingAllowList";
  v13 = 32;
  v7 = (__int64 *)NtlmHelper::RegistryReader::ReadMultiString(a2, v14, &v12);
  v8 = *v7;
  *v7 = 0;
  v9 = v7[1];
  v13 = v9;
  AcquireSRWLockExclusive(&stru_180089AE0);
  v12 = 0;
  v11 = (void *)qword_180089AB8;
  qword_180089AB8 = v8;
  if ( v11 )
    operator delete(v11, v10);
  qword_180089AC0 = v9;
  utl::vector<NtlmHelper::Blocking::SpnPolicy::SpnEntry,utl::allocator<NtlmHelper::Blocking::SpnPolicy::SpnEntry>>::_EraseTail(
    &qword_180089AC8,
    qword_180089AC8);
  NtlmHelper::Blocking::SpnPolicy::ParseMultiSz((NtlmHelper::Blocking::SpnPolicy *)&qword_180089AB8);
  ReleaseSRWLockExclusive(&stru_180089AE0);
  utl::unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>::~unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>(&v12);
  utl::unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>::~unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>(v14);
}

```

## disassembly

```asm
0x180068cd8  mov     [rsp-8+arg_8], rbx
0x180068cdd  mov     [rsp-8+arg_10], rdi
0x180068ce2  mov     [rsp-8+arg_0], rcx
0x180068ce7  push    rbp
0x180068ce8  mov     rbp, rsp
0x180068ceb  sub     rsp, 40h
0x180068cef  mov     rbx, rdx
0x180068cf2  mov     [rbp+arg_0], rdx
0x180068cf6  lea     rax, aBlockdomainacc; "BlockDomainAccountSSO"
0x180068cfd  mov     [rbp+var_20], rax
0x180068d01  mov     edi, 15h
0x180068d06  mov     [rbp+var_18], rdi
0x180068d0a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NTLMless_BlockDomainUserSSONtlm@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless_BlockDomainUserSSONtlm@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_BlockDomainUserSSONtlm> `wil::Feature<__WilFeatureTraits_Feature_NTLMless_BlockDomainUserSSONtlm>::GetImpl(void)'::`2'::impl
0x180068d11  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless_BlockDomainUserSSONtlm@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_BlockDomainUserSSONtlm>::__private_IsEnabled(void)
0x180068d16  movzx   r8d, al
0x180068d1a  add     r8d, r8d
0x180068d1d  lea     rdx, [rbp+var_20]
0x180068d21  lea     rcx, [rbp+arg_0]
0x180068d25  call    _lambda_63e3a7b7ae56bddb12dc9bc2c321eec4___operator__
0x180068d2a  mov     cs:?g_ntlmPolicyEngine@@3VPolicyEngine@Blocking@NtlmHelper@@A, eax; NtlmHelper::Blocking::PolicyEngine g_ntlmPolicyEngine
0x180068d30  lea     rax, aBlockdomaincon; "BlockDomainControllerAuth"
0x180068d37  mov     [rbp+var_20], rax
0x180068d3b  mov     [rbp+var_18], 19h
0x180068d43  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NTLMless_BlockDomainControllerNtlm@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless_BlockDomainControllerNtlm@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_BlockDomainControllerNtlm> `wil::Feature<__WilFeatureTraits_Feature_NTLMless_BlockDomainControllerNtlm>::GetImpl(void)'::`2'::impl
0x180068d4a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless_BlockDomainControllerNtlm@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_BlockDomainControllerNtlm>::__private_IsEnabled(void)
0x180068d4f  movzx   r8d, al
0x180068d53  add     r8d, r8d
0x180068d56  lea     rdx, [rbp+var_20]
0x180068d5a  lea     rcx, [rbp+arg_0]
0x180068d5e  call    _lambda_63e3a7b7ae56bddb12dc9bc2c321eec4___operator__
0x180068d63  mov     dword ptr cs:qword_180089AA4, eax
0x180068d69  lea     rax, aEnforcemachine; "EnforceMachineBinding"
0x180068d70  mov     [rbp+var_20], rax
0x180068d74  mov     [rbp+var_18], rdi
0x180068d78  xor     r8d, r8d
0x180068d7b  lea     rdx, [rbp+var_20]
0x180068d7f  lea     rcx, [rbp+arg_0]
0x180068d83  call    _lambda_63e3a7b7ae56bddb12dc9bc2c321eec4___operator__
0x180068d88  mov     dword ptr cs:qword_180089AA4+4, eax
0x180068d8e  lea     rax, aBlockhardcoded; "BlockHardcodedCalls"
0x180068d95  mov     [rbp+var_20], rax
0x180068d99  mov     [rbp+var_18], 13h
0x180068da1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NTLMless_BlockHardcodedNtlm@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless_BlockHardcodedNtlm@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_BlockHardcodedNtlm> `wil::Feature<__WilFeatureTraits_Feature_NTLMless_BlockHardcodedNtlm>::GetImpl(void)'::`2'::impl
0x180068da8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless_BlockHardcodedNtlm@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_BlockHardcodedNtlm>::__private_IsEnabled(void)
0x180068dad  movzx   r8d, al
0x180068db1  add     r8d, r8d
0x180068db4  lea     rdx, [rbp+var_20]
0x180068db8  lea     rcx, [rbp+arg_0]
0x180068dbc  call    _lambda_63e3a7b7ae56bddb12dc9bc2c321eec4___operator__
0x180068dc1  mov     cs:dword_180089AAC, eax
0x180068dc7  lea     rax, aBlockall; "BlockAll"
0x180068dce  mov     [rbp+var_20], rax
0x180068dd2  mov     [rbp+var_18], 8
0x180068dda  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NTLMless_BlockAllOfNtlm@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless_BlockAllOfNtlm@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_BlockAllOfNtlm> `wil::Feature<__WilFeatureTraits_Feature_NTLMless_BlockAllOfNtlm>::GetImpl(void)'::`2'::impl
0x180068de1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless_BlockAllOfNtlm@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_BlockAllOfNtlm>::__private_IsEnabled(void)
0x180068de6  movzx   r8d, al
0x180068dea  add     r8d, r8d
0x180068ded  lea     rdx, [rbp+var_20]
0x180068df1  lea     rcx, [rbp+arg_0]
0x180068df5  call    _lambda_63e3a7b7ae56bddb12dc9bc2c321eec4___operator__
0x180068dfa  mov     cs:dword_180089AB0, eax
0x180068e00  lea     rax, aEnhancedmachin; "EnhancedMachineBlockingAllowList"
0x180068e07  mov     [rbp+var_20], rax
0x180068e0b  mov     [rbp+var_18], 20h ; ' '
0x180068e13  lea     r8, [rbp+var_20]
0x180068e17  lea     rdx, [rbp+var_10]
0x180068e1b  mov     rcx, rbx
0x180068e1e  call    ?ReadMultiString@RegistryReader@NtlmHelper@@QEAA?AU?$pair@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@_K@utl@@V?$basic_string_view@GU?$char_traits@G@utl@@@4@@Z; NtlmHelper::RegistryReader::ReadMultiString(utl::basic_string_view<ushort,utl::char_traits<ushort>>)
0x180068e23  mov     rbx, [rax]
0x180068e26  mov     qword ptr [rax], 0
0x180068e2d  mov     rdi, [rax+8]
0x180068e31  mov     [rbp+var_18], rdi
0x180068e35  lea     rcx, stru_180089AE0; SRWLock
0x180068e3c  call    cs:__imp_AcquireSRWLockExclusive
0x180068e42  mov     [rbp+var_20], 0
0x180068e4a  mov     rcx, cs:qword_180089AB8; void *
0x180068e51  mov     cs:qword_180089AB8, rbx
0x180068e58  test    rcx, rcx
0x180068e5b  jz      short loc_180068E62
0x180068e5d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068e62  mov     cs:qword_180089AC0, rdi
0x180068e69  mov     rdx, cs:qword_180089AC8
0x180068e70  lea     rcx, qword_180089AC8
0x180068e77  call    ?_EraseTail@?$vector@USpnEntry@SpnPolicy@Blocking@NtlmHelper@@V?$allocator@USpnEntry@SpnPolicy@Blocking@NtlmHelper@@@utl@@@utl@@AEAAXPEAUSpnEntry@SpnPolicy@Blocking@NtlmHelper@@@Z; utl::vector<NtlmHelper::Blocking::SpnPolicy::SpnEntry,utl::allocator<NtlmHelper::Blocking::SpnPolicy::SpnEntry>>::_EraseTail(NtlmHelper::Blocking::SpnPolicy::SpnEntry *)
0x180068e7c  lea     rcx, qword_180089AB8; this
0x180068e83  call    ?ParseMultiSz@SpnPolicy@Blocking@NtlmHelper@@AEAAXXZ; NtlmHelper::Blocking::SpnPolicy::ParseMultiSz(void)
0x180068e88  lea     rcx, stru_180089AE0; SRWLock
0x180068e8f  call    cs:__imp_ReleaseSRWLockExclusive
0x180068e95  nop
0x180068e96  lea     rcx, [rbp+var_20]
0x180068e9a  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>>::~unique_ptr<ushort [0],utl::default_delete<ushort [0]>>(void)
0x180068e9f  nop
0x180068ea0  lea     rcx, [rbp+var_10]
0x180068ea4  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>>::~unique_ptr<ushort [0],utl::default_delete<ushort [0]>>(void)
0x180068ea9  nop
0x180068eaa  mov     rbx, [rsp+40h+arg_8]
0x180068eaf  mov     rdi, [rsp+40h+arg_10]
0x180068eb4  add     rsp, 40h
0x180068eb8  pop     rbp
0x180068eb9  retn
```
