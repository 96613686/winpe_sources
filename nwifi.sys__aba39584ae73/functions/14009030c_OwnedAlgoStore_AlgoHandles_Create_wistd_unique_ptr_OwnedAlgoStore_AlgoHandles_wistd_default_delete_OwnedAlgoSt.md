# OwnedAlgoStore::AlgoHandles::Create(wistd::unique_ptr<OwnedAlgoStore::AlgoHandles,wistd::default_delete<OwnedAlgoStore::AlgoHandles>> &)

- ea: `0x14009030c`
- end: `0x140090688`
- name: `?Create@AlgoHandles@OwnedAlgoStore@@SAJAEAV?$unique_ptr@UAlgoHandles@OwnedAlgoStore@@U?$default_delete@UAlgoHandles@OwnedAlgoStore@@@wistd@@@wistd@@@Z`
- size: `892`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14008f6ec`

## callees

- `0x14000599c`
- `0x140023150`
- `0x1400902d0`
- `0x14009030c`

## import_xrefs

- `ksecdd!BCryptSetProperty` at `0x1400903ce`
- `ksecdd!BCryptSetProperty` at `0x140090438`
- `ksecdd!BCryptSetProperty` at `0x1400903ce`
- `ksecdd!BCryptSetProperty` at `0x140090438`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140090388`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140090401`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140090470`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400904b0`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400904f6`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140090536`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140090576`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400905b6`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400905f6`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140090636`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140090388`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140090401`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140090470`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400904b0`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400904f6`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140090536`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140090576`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400905b6`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400905f6`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140090636`

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
0x14009030c  mov     [rsp-28h+arg_0], rbx
0x140090311  mov     [rsp-28h+arg_10], rsi
0x140090316  push    rbp
0x140090317  push    rdi
0x140090318  push    r12
0x14009031a  push    r14
0x14009031c  push    r15
0x14009031e  mov     rbp, rsp
0x140090321  sub     rsp, 50h
0x140090325  mov     rsi, rcx
0x140090328  xor     r15d, r15d
0x14009032b  lea     ecx, [r15+50h]; unsigned __int64
0x14009032f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140090334  mov     rbx, rax
0x140090337  test    rax, rax
0x14009033a  jz      loc_140090669
0x140090340  mov     [rax], r15
0x140090343  lea     r12d, [r15+1]
0x140090347  mov     [rax+8], r15
0x14009034b  lea     rdx, pszAlgId; "AES"
0x140090352  mov     [rax+10h], r15
0x140090356  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14009035a  mov     [rax+18h], r15
0x14009035e  mov     r9d, r12d; dwFlags
0x140090361  mov     [rax+20h], r15
0x140090365  xor     r8d, r8d; pszImplementation
0x140090368  mov     [rax+28h], r15
0x14009036c  mov     [rax+30h], r15
0x140090370  mov     [rax+38h], r15
0x140090374  mov     [rax+40h], r15
0x140090378  mov     [rax+48h], r15
0x14009037c  mov     [rbp+var_20], rax
0x140090380  mov     [rbp+phAlgorithm], r15
0x140090384  mov     [rbp+var_10], r12b
0x140090388  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14009038f  nop     dword ptr [rax+rax+00h]
0x140090394  lea     rcx, [rbp+var_20]
0x140090398  mov     edi, eax
0x14009039a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14009039f  test    edi, edi
0x1400903a1  jns     short loc_1400903B2
0x1400903a3  mov     rcx, rbx; this
0x1400903a6  call    ??_GAlgoHandles@OwnedAlgoStore@@QEAAPEAXI@Z; OwnedAlgoStore::AlgoHandles::`scalar deleting destructor'(uint)
0x1400903ab  mov     eax, edi
0x1400903ad  jmp     loc_14009066E
0x1400903b2  mov     rcx, [rbx]; hObject
0x1400903b5  lea     r8, pbInput; "ChainingModeECB"
0x1400903bc  mov     r9d, 20h ; ' '; cbInput
0x1400903c2  mov     [rsp+50h+dwFlags], r15d; dwFlags
0x1400903c7  lea     rdx, aChainingmode; "ChainingMode"
0x1400903ce  call    cs:__imp_BCryptSetProperty
0x1400903d5  nop     dword ptr [rax+rax+00h]
0x1400903da  mov     edi, eax
0x1400903dc  test    eax, eax
0x1400903de  js      short loc_1400903A3
0x1400903e0  lea     r14, [rbx+8]
0x1400903e4  mov     [rbp+phAlgorithm], r15
0x1400903e8  mov     r9d, r12d; dwFlags
0x1400903eb  mov     [rbp+var_20], r14
0x1400903ef  xor     r8d, r8d; pszImplementation
0x1400903f2  mov     [rbp+var_10], r12b
0x1400903f6  lea     rdx, pszAlgId; "AES"
0x1400903fd  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140090401  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140090408  nop     dword ptr [rax+rax+00h]
0x14009040d  lea     rcx, [rbp+var_20]
0x140090411  mov     edi, eax
0x140090413  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x140090418  test    edi, edi
0x14009041a  js      short loc_1400903A3
0x14009041c  mov     rcx, [r14]; hObject
0x14009041f  lea     r8, aChainingmodecc; "ChainingModeCCM"
0x140090426  mov     r9d, 20h ; ' '; cbInput
0x14009042c  mov     [rsp+50h+dwFlags], r15d; dwFlags
0x140090431  lea     rdx, aChainingmode; "ChainingMode"
0x140090438  call    cs:__imp_BCryptSetProperty
0x14009043f  nop     dword ptr [rax+rax+00h]
0x140090444  test    eax, eax
0x140090446  jns     short loc_14009044F
0x140090448  mov     edi, eax
0x14009044a  jmp     loc_1400903A3
0x14009044f  lea     rax, [rbx+10h]
0x140090453  mov     [rbp+phAlgorithm], r15
0x140090457  mov     r9d, r12d; dwFlags
0x14009045a  mov     [rbp+var_20], rax
0x14009045e  xor     r8d, r8d; pszImplementation
0x140090461  mov     [rbp+var_10], r12b
0x140090465  lea     rdx, aSha256; "SHA256"
0x14009046c  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140090470  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140090477  nop     dword ptr [rax+rax+00h]
0x14009047c  lea     rcx, [rbp+var_20]
0x140090480  mov     edi, eax
0x140090482  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x140090487  test    edi, edi
0x140090489  js      loc_1400903A3
0x14009048f  lea     rax, [rbx+18h]
0x140090493  mov     [rbp+phAlgorithm], r15
0x140090497  mov     r9d, r12d; dwFlags
0x14009049a  mov     [rbp+var_20], rax
0x14009049e  xor     r8d, r8d; pszImplementation
0x1400904a1  mov     [rbp+var_10], r12b
0x1400904a5  lea     rdx, aSha384; "SHA384"
0x1400904ac  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1400904b0  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400904b7  nop     dword ptr [rax+rax+00h]
0x1400904bc  lea     rcx, [rbp+var_20]
0x1400904c0  mov     edi, eax
0x1400904c2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x1400904c7  test    edi, edi
0x1400904c9  js      loc_1400903A3
0x1400904cf  lea     rax, [rbx+20h]
0x1400904d3  mov     [rbp+phAlgorithm], r15
0x1400904d7  mov     r14d, 9
0x1400904dd  mov     [rbp+var_20], rax
0x1400904e1  mov     r9d, r14d; dwFlags
0x1400904e4  mov     [rbp+var_10], r12b
0x1400904e8  xor     r8d, r8d; pszImplementation
0x1400904eb  lea     rdx, aMd5; "MD5"
0x1400904f2  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1400904f6  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400904fd  nop     dword ptr [rax+rax+00h]
0x140090502  lea     rcx, [rbp+var_20]
0x140090506  mov     edi, eax
0x140090508  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14009050d  test    edi, edi
0x14009050f  js      loc_1400903A3
0x140090515  lea     rax, [rbx+28h]
0x140090519  mov     [rbp+phAlgorithm], r15
0x14009051d  mov     r9d, r14d; dwFlags
0x140090520  mov     [rbp+var_20], rax
0x140090524  xor     r8d, r8d; pszImplementation
0x140090527  mov     [rbp+var_10], r12b
0x14009052b  lea     rdx, aSha1; "SHA1"
0x140090532  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140090536  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14009053d  nop     dword ptr [rax+rax+00h]
0x140090542  lea     rcx, [rbp+var_20]
0x140090546  mov     edi, eax
0x140090548  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14009054d  test    edi, edi
0x14009054f  js      loc_1400903A3
0x140090555  lea     rax, [rbx+30h]
0x140090559  mov     [rbp+phAlgorithm], r15
0x14009055d  mov     r9d, r14d; dwFlags
0x140090560  mov     [rbp+var_20], rax
0x140090564  xor     r8d, r8d; pszImplementation
0x140090567  mov     [rbp+var_10], r12b
0x14009056b  lea     rdx, aSha256; "SHA256"
0x140090572  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140090576  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14009057d  nop     dword ptr [rax+rax+00h]
0x140090582  lea     rcx, [rbp+var_20]
0x140090586  mov     edi, eax
0x140090588  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14009058d  test    edi, edi
0x14009058f  js      loc_1400903A3
0x140090595  lea     rax, [rbx+38h]
0x140090599  mov     [rbp+phAlgorithm], r15
0x14009059d  mov     r9d, r14d; dwFlags
0x1400905a0  mov     [rbp+var_20], rax
0x1400905a4  xor     r8d, r8d; pszImplementation
0x1400905a7  mov     [rbp+var_10], r12b
0x1400905ab  lea     rdx, aSha384; "SHA384"
0x1400905b2  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1400905b6  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400905bd  nop     dword ptr [rax+rax+00h]
0x1400905c2  lea     rcx, [rbp+var_20]
0x1400905c6  mov     edi, eax
0x1400905c8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x1400905cd  test    edi, edi
0x1400905cf  js      loc_1400903A3
0x1400905d5  lea     rax, [rbx+40h]
0x1400905d9  mov     [rbp+phAlgorithm], r15
0x1400905dd  mov     r9d, r12d; dwFlags
0x1400905e0  mov     [rbp+var_20], rax
0x1400905e4  xor     r8d, r8d; pszImplementation
0x1400905e7  mov     [rbp+var_10], r12b
0x1400905eb  lea     rdx, aAesCmac; "AES-CMAC"
0x1400905f2  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1400905f6  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400905fd  nop     dword ptr [rax+rax+00h]
0x140090602  lea     rcx, [rbp+var_20]
0x140090606  mov     edi, eax
0x140090608  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14009060d  test    edi, edi
0x14009060f  js      loc_1400903A3
0x140090615  lea     rax, [rbx+48h]
0x140090619  mov     [rbp+phAlgorithm], r15
0x14009061d  mov     r9d, r12d; dwFlags
0x140090620  mov     [rbp+var_20], rax
0x140090624  xor     r8d, r8d; pszImplementation
0x140090627  mov     [rbp+var_10], r12b
0x14009062b  lea     rdx, aRc4; "RC4"
0x140090632  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140090636  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14009063d  nop     dword ptr [rax+rax+00h]
0x140090642  lea     rcx, [rbp+var_20]
0x140090646  mov     edi, eax
0x140090648  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x14009064d  test    edi, edi
0x14009064f  js      loc_1400903A3
0x140090655  mov     rcx, [rsi]; this
0x140090658  mov     [rsi], rbx
0x14009065b  test    rcx, rcx
0x14009065e  jz      short loc_140090665
0x140090660  call    ??_GAlgoHandles@OwnedAlgoStore@@QEAAPEAXI@Z; OwnedAlgoStore::AlgoHandles::`scalar deleting destructor'(uint)
0x140090665  xor     eax, eax
0x140090667  jmp     short loc_14009066E
0x140090669  mov     eax, 0C0000017h
0x14009066e  lea     r11, [rsp+50h+var_s0]
0x140090673  mov     rbx, [r11+30h]
0x140090677  mov     rsi, [r11+40h]
0x14009067b  mov     rsp, r11
0x14009067e  pop     r15
0x140090680  pop     r14
0x140090682  pop     r12
0x140090684  pop     rdi
0x140090685  pop     rbp
0x140090686  retn
```
