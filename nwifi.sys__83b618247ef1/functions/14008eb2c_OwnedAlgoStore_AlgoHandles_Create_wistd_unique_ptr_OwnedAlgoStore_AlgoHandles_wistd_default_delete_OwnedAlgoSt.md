# OwnedAlgoStore::AlgoHandles::Create(wistd::unique_ptr<OwnedAlgoStore::AlgoHandles,wistd::default_delete<OwnedAlgoStore::AlgoHandles>> &)

- ea: `0x14008eb2c`
- end: `0x14008eea8`
- name: `?Create@AlgoHandles@OwnedAlgoStore@@SAJAEAV?$unique_ptr@UAlgoHandles@OwnedAlgoStore@@U?$default_delete@UAlgoHandles@OwnedAlgoStore@@@wistd@@@wistd@@@Z`
- size: `892`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14008debc`

## callees

- `0x14000599c`
- `0x140023150`
- `0x14008eaf0`
- `0x14008eb2c`

## import_xrefs

- `ksecdd!BCryptSetProperty` at `0x14008ebee`
- `ksecdd!BCryptSetProperty` at `0x14008ec58`
- `ksecdd!BCryptSetProperty` at `0x14008ebee`
- `ksecdd!BCryptSetProperty` at `0x14008ec58`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008eba8`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ec21`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ec90`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ecd0`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ed16`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ed56`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ed96`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008edd6`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ee16`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ee56`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008eba8`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ec21`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ec90`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ecd0`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ed16`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ed56`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ed96`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008edd6`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ee16`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14008ee56`

## pseudocode

```c
__int64 __fastcall OwnedAlgoStore::AlgoHandles::Create(
        OwnedAlgoStore::AlgoHandles **a1,
        const struct std::nothrow_t *a2)
{
  BCRYPT_HANDLE *v3; // rax
  BCRYPT_HANDLE *v4; // rbx
  NTSTATUS v5; // edi
  unsigned int v6; // edx
  NTSTATUS v8; // eax
  OwnedAlgoStore::AlgoHandles *v9; // rcx
  BCRYPT_HANDLE *v10; // [rsp+30h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+38h] [rbp-18h] BYREF
  char v12; // [rsp+40h] [rbp-10h]

  v3 = (BCRYPT_HANDLE *)operator new(0x50u, a2);
  v4 = v3;
  if ( !v3 )
    return 3221225495LL;
  *v3 = 0;
  v3[1] = 0;
  v3[2] = 0;
  v3[3] = 0;
  v3[4] = 0;
  v3[5] = 0;
  v3[6] = 0;
  v3[7] = 0;
  v3[8] = 0;
  v3[9] = 0;
  v10 = v3;
  phAlgorithm = 0;
  v12 = 1;
  v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 1u);
  __1__out_param_t_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___details_wil__QEAA_XZ(&v10);
  if ( v5 < 0 )
    goto LABEL_3;
  v5 = BCryptSetProperty(*v4, L"ChainingMode", (PUCHAR)L"ChainingModeECB", 0x20u, 0);
  if ( v5 < 0 )
    goto LABEL_3;
  phAlgorithm = 0;
  v10 = v4 + 1;
  v12 = 1;
  v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 1u);
  __1__out_param_t_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___details_wil__QEAA_XZ(&v10);
  if ( v5 < 0 )
    goto LABEL_3;
  v8 = BCryptSetProperty(v4[1], L"ChainingMode", (PUCHAR)L"ChainingModeCCM", 0x20u, 0);
  if ( v8 < 0 )
  {
    v5 = v8;
LABEL_3:
    OwnedAlgoStore::AlgoHandles::`scalar deleting destructor'((OwnedAlgoStore::AlgoHandles *)v4, v6);
    return (unsigned int)v5;
  }
  phAlgorithm = 0;
  v10 = v4 + 2;
  v12 = 1;
  v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 1u);
  __1__out_param_t_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___details_wil__QEAA_XZ(&v10);
  if ( v5 < 0 )
    goto LABEL_3;
  phAlgorithm = 0;
  v10 = v4 + 3;
  v12 = 1;
  v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA384", 0, 1u);
  __1__out_param_t_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___details_wil__QEAA_XZ(&v10);
  if ( v5 < 0 )
    goto LABEL_3;
  phAlgorithm = 0;
  v10 = v4 + 4;
  v12 = 1;
  v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"MD5", 0, 9u);
  __1__out_param_t_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___details_wil__QEAA_XZ(&v10);
  if ( v5 < 0 )
    goto LABEL_3;
  phAlgorithm = 0;
  v10 = v4 + 5;
  v12 = 1;
  v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", 0, 9u);
  __1__out_param_t_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___details_wil__QEAA_XZ(&v10);
  if ( v5 < 0 )
    goto LABEL_3;
  phAlgorithm = 0;
  v10 = v4 + 6;
  v12 = 1;
  v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 9u);
  __1__out_param_t_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___details_wil__QEAA_XZ(&v10);
  if ( v5 < 0 )
    goto LABEL_3;
  phAlgorithm = 0;
  v10 = v4 + 7;
  v12 = 1;
  v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA384", 0, 9u);
  __1__out_param_t_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___details_wil__QEAA_XZ(&v10);
  if ( v5 < 0 )
    goto LABEL_3;
  phAlgorithm = 0;
  v10 = v4 + 8;
  v12 = 1;
  v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES-CMAC", 0, 1u);
  __1__out_param_t_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___details_wil__QEAA_XZ(&v10);
  if ( v5 < 0 )
    goto LABEL_3;
  phAlgorithm = 0;
  v10 = v4 + 9;
  v12 = 1;
  v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RC4", 0, 1u);
  __1__out_param_t_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___details_wil__QEAA_XZ(&v10);
  if ( v5 < 0 )
    goto LABEL_3;
  v9 = *a1;
  *a1 = (OwnedAlgoStore::AlgoHandles *)v4;
  if ( v9 )
    OwnedAlgoStore::AlgoHandles::`scalar deleting destructor'(v9, v6);
  return 0;
}

```

## disassembly

```asm
0x14008eb2c  mov     [rsp-28h+arg_0], rbx
0x14008eb31  mov     [rsp-28h+arg_10], rsi
0x14008eb36  push    rbp
0x14008eb37  push    rdi
0x14008eb38  push    r12
0x14008eb3a  push    r14
0x14008eb3c  push    r15
0x14008eb3e  mov     rbp, rsp
0x14008eb41  sub     rsp, 50h
0x14008eb45  mov     rsi, rcx
0x14008eb48  xor     r15d, r15d
0x14008eb4b  lea     ecx, [r15+50h]; unsigned __int64
0x14008eb4f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14008eb54  mov     rbx, rax
0x14008eb57  test    rax, rax
0x14008eb5a  jz      loc_14008EE89
0x14008eb60  mov     [rax], r15
0x14008eb63  lea     r12d, [r15+1]
0x14008eb67  mov     [rax+8], r15
0x14008eb6b  lea     rdx, pszAlgId; "AES"
0x14008eb72  mov     [rax+10h], r15
0x14008eb76  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14008eb7a  mov     [rax+18h], r15
0x14008eb7e  mov     r9d, r12d; dwFlags
0x14008eb81  mov     [rax+20h], r15
0x14008eb85  xor     r8d, r8d; pszImplementation
0x14008eb88  mov     [rax+28h], r15
0x14008eb8c  mov     [rax+30h], r15
0x14008eb90  mov     [rax+38h], r15
0x14008eb94  mov     [rax+40h], r15
0x14008eb98  mov     [rax+48h], r15
0x14008eb9c  mov     [rbp+var_20], rax
0x14008eba0  mov     [rbp+phAlgorithm], r15
0x14008eba4  mov     [rbp+var_10], r12b
0x14008eba8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14008ebaf  nop     dword ptr [rax+rax+00h]
0x14008ebb4  lea     rcx, [rbp+var_20]
0x14008ebb8  mov     edi, eax
0x14008ebba  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14008ebbf  test    edi, edi
0x14008ebc1  jns     short loc_14008EBD2
0x14008ebc3  mov     rcx, rbx; this
0x14008ebc6  call    ??_GAlgoHandles@OwnedAlgoStore@@QEAAPEAXI@Z; OwnedAlgoStore::AlgoHandles::`scalar deleting destructor'(uint)
0x14008ebcb  mov     eax, edi
0x14008ebcd  jmp     loc_14008EE8E
0x14008ebd2  mov     rcx, [rbx]; hObject
0x14008ebd5  lea     r8, pbInput; "ChainingModeECB"
0x14008ebdc  mov     r9d, 20h ; ' '; cbInput
0x14008ebe2  mov     [rsp+50h+dwFlags], r15d; dwFlags
0x14008ebe7  lea     rdx, aChainingmode; "ChainingMode"
0x14008ebee  call    cs:__imp_BCryptSetProperty
0x14008ebf5  nop     dword ptr [rax+rax+00h]
0x14008ebfa  mov     edi, eax
0x14008ebfc  test    eax, eax
0x14008ebfe  js      short loc_14008EBC3
0x14008ec00  lea     r14, [rbx+8]
0x14008ec04  mov     [rbp+phAlgorithm], r15
0x14008ec08  mov     r9d, r12d; dwFlags
0x14008ec0b  mov     [rbp+var_20], r14
0x14008ec0f  xor     r8d, r8d; pszImplementation
0x14008ec12  mov     [rbp+var_10], r12b
0x14008ec16  lea     rdx, pszAlgId; "AES"
0x14008ec1d  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14008ec21  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14008ec28  nop     dword ptr [rax+rax+00h]
0x14008ec2d  lea     rcx, [rbp+var_20]
0x14008ec31  mov     edi, eax
0x14008ec33  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14008ec38  test    edi, edi
0x14008ec3a  js      short loc_14008EBC3
0x14008ec3c  mov     rcx, [r14]; hObject
0x14008ec3f  lea     r8, aChainingmodecc; "ChainingModeCCM"
0x14008ec46  mov     r9d, 20h ; ' '; cbInput
0x14008ec4c  mov     [rsp+50h+dwFlags], r15d; dwFlags
0x14008ec51  lea     rdx, aChainingmode; "ChainingMode"
0x14008ec58  call    cs:__imp_BCryptSetProperty
0x14008ec5f  nop     dword ptr [rax+rax+00h]
0x14008ec64  test    eax, eax
0x14008ec66  jns     short loc_14008EC6F
0x14008ec68  mov     edi, eax
0x14008ec6a  jmp     loc_14008EBC3
0x14008ec6f  lea     rax, [rbx+10h]
0x14008ec73  mov     [rbp+phAlgorithm], r15
0x14008ec77  mov     r9d, r12d; dwFlags
0x14008ec7a  mov     [rbp+var_20], rax
0x14008ec7e  xor     r8d, r8d; pszImplementation
0x14008ec81  mov     [rbp+var_10], r12b
0x14008ec85  lea     rdx, aSha256; "SHA256"
0x14008ec8c  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14008ec90  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14008ec97  nop     dword ptr [rax+rax+00h]
0x14008ec9c  lea     rcx, [rbp+var_20]
0x14008eca0  mov     edi, eax
0x14008eca2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14008eca7  test    edi, edi
0x14008eca9  js      loc_14008EBC3
0x14008ecaf  lea     rax, [rbx+18h]
0x14008ecb3  mov     [rbp+phAlgorithm], r15
0x14008ecb7  mov     r9d, r12d; dwFlags
0x14008ecba  mov     [rbp+var_20], rax
0x14008ecbe  xor     r8d, r8d; pszImplementation
0x14008ecc1  mov     [rbp+var_10], r12b
0x14008ecc5  lea     rdx, aSha384; "SHA384"
0x14008eccc  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14008ecd0  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14008ecd7  nop     dword ptr [rax+rax+00h]
0x14008ecdc  lea     rcx, [rbp+var_20]
0x14008ece0  mov     edi, eax
0x14008ece2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14008ece7  test    edi, edi
0x14008ece9  js      loc_14008EBC3
0x14008ecef  lea     rax, [rbx+20h]
0x14008ecf3  mov     [rbp+phAlgorithm], r15
0x14008ecf7  mov     r14d, 9
0x14008ecfd  mov     [rbp+var_20], rax
0x14008ed01  mov     r9d, r14d; dwFlags
0x14008ed04  mov     [rbp+var_10], r12b
0x14008ed08  xor     r8d, r8d; pszImplementation
0x14008ed0b  lea     rdx, aMd5; "MD5"
0x14008ed12  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14008ed16  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14008ed1d  nop     dword ptr [rax+rax+00h]
0x14008ed22  lea     rcx, [rbp+var_20]
0x14008ed26  mov     edi, eax
0x14008ed28  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14008ed2d  test    edi, edi
0x14008ed2f  js      loc_14008EBC3
0x14008ed35  lea     rax, [rbx+28h]
0x14008ed39  mov     [rbp+phAlgorithm], r15
0x14008ed3d  mov     r9d, r14d; dwFlags
0x14008ed40  mov     [rbp+var_20], rax
0x14008ed44  xor     r8d, r8d; pszImplementation
0x14008ed47  mov     [rbp+var_10], r12b
0x14008ed4b  lea     rdx, aSha1; "SHA1"
0x14008ed52  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14008ed56  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14008ed5d  nop     dword ptr [rax+rax+00h]
0x14008ed62  lea     rcx, [rbp+var_20]
0x14008ed66  mov     edi, eax
0x14008ed68  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14008ed6d  test    edi, edi
0x14008ed6f  js      loc_14008EBC3
0x14008ed75  lea     rax, [rbx+30h]
0x14008ed79  mov     [rbp+phAlgorithm], r15
0x14008ed7d  mov     r9d, r14d; dwFlags
0x14008ed80  mov     [rbp+var_20], rax
0x14008ed84  xor     r8d, r8d; pszImplementation
0x14008ed87  mov     [rbp+var_10], r12b
0x14008ed8b  lea     rdx, aSha256; "SHA256"
0x14008ed92  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14008ed96  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14008ed9d  nop     dword ptr [rax+rax+00h]
0x14008eda2  lea     rcx, [rbp+var_20]
0x14008eda6  mov     edi, eax
0x14008eda8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14008edad  test    edi, edi
0x14008edaf  js      loc_14008EBC3
0x14008edb5  lea     rax, [rbx+38h]
0x14008edb9  mov     [rbp+phAlgorithm], r15
0x14008edbd  mov     r9d, r14d; dwFlags
0x14008edc0  mov     [rbp+var_20], rax
0x14008edc4  xor     r8d, r8d; pszImplementation
0x14008edc7  mov     [rbp+var_10], r12b
0x14008edcb  lea     rdx, aSha384; "SHA384"
0x14008edd2  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14008edd6  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14008eddd  nop     dword ptr [rax+rax+00h]
0x14008ede2  lea     rcx, [rbp+var_20]
0x14008ede6  mov     edi, eax
0x14008ede8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14008eded  test    edi, edi
0x14008edef  js      loc_14008EBC3
0x14008edf5  lea     rax, [rbx+40h]
0x14008edf9  mov     [rbp+phAlgorithm], r15
0x14008edfd  mov     r9d, r12d; dwFlags
0x14008ee00  mov     [rbp+var_20], rax
0x14008ee04  xor     r8d, r8d; pszImplementation
0x14008ee07  mov     [rbp+var_10], r12b
0x14008ee0b  lea     rdx, aAesCmac; "AES-CMAC"
0x14008ee12  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14008ee16  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14008ee1d  nop     dword ptr [rax+rax+00h]
0x14008ee22  lea     rcx, [rbp+var_20]
0x14008ee26  mov     edi, eax
0x14008ee28  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14008ee2d  test    edi, edi
0x14008ee2f  js      loc_14008EBC3
0x14008ee35  lea     rax, [rbx+48h]
0x14008ee39  mov     [rbp+phAlgorithm], r15
0x14008ee3d  mov     r9d, r12d; dwFlags
0x14008ee40  mov     [rbp+var_20], rax
0x14008ee44  xor     r8d, r8d; pszImplementation
0x14008ee47  mov     [rbp+var_10], r12b
0x14008ee4b  lea     rdx, aRc4; "RC4"
0x14008ee52  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14008ee56  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14008ee5d  nop     dword ptr [rax+rax+00h]
0x14008ee62  lea     rcx, [rbp+var_20]
0x14008ee66  mov     edi, eax
0x14008ee68  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14008ee6d  test    edi, edi
0x14008ee6f  js      loc_14008EBC3
0x14008ee75  mov     rcx, [rsi]; this
0x14008ee78  mov     [rsi], rbx
0x14008ee7b  test    rcx, rcx
0x14008ee7e  jz      short loc_14008EE85
0x14008ee80  call    ??_GAlgoHandles@OwnedAlgoStore@@QEAAPEAXI@Z; OwnedAlgoStore::AlgoHandles::`scalar deleting destructor'(uint)
0x14008ee85  xor     eax, eax
0x14008ee87  jmp     short loc_14008EE8E
0x14008ee89  mov     eax, 0C0000017h
0x14008ee8e  lea     r11, [rsp+50h+var_s0]
0x14008ee93  mov     rbx, [r11+30h]
0x14008ee97  mov     rsi, [r11+40h]
0x14008ee9b  mov     rsp, r11
0x14008ee9e  pop     r15
0x14008eea0  pop     r14
0x14008eea2  pop     r12
0x14008eea4  pop     rdi
0x14008eea5  pop     rbp
0x14008eea6  retn
```
