# BcpDecryptWithAesCcm(uchar *,unsigned __int64,uchar *,unsigned __int64,uchar *,unsigned __int64,uchar * *,unsigned __int64 *)

- ea: `0x1800f7500`
- end: `0x1800f77f5`
- name: `?BcpDecryptWithAesCcm@@YAJPEAE_K0101PEAPEAEPEA_K@Z`
- size: `757`
- prototype: `__int64 __fastcall(unsigned __int8 *, __int64, unsigned __int8 *, __int64, PUCHAR pbInput, unsigned __int64, unsigned __int8 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f65f4`

## callees

- `0x180038730`
- `0x18004c458`
- `0x18004c678`
- `0x1800a4530`
- `0x1800a45cc`
- `0x1800f7184`
- `0x1800f71d4`
- `0x1800f7494`
- `0x1800f74bc`
- `0x1800f7500`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x1800f759c`
- `bcrypt!BCryptSetProperty` at `0x1800f759c`
- `bcrypt!BCryptDecrypt` at `0x1800f775d`
- `bcrypt!BCryptDecrypt` at `0x1800f775d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800f7566`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800f7566`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800f7635`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800f7635`

## string_xrefs

- `0x1800f75af`: `onecore\base\ngscb\cornerstone\nkpcommonlib\crypto.cpp`
- `0x1800f75f2`: `onecore\base\ngscb\cornerstone\nkpcommonlib\crypto.cpp`
- `0x1800f764c`: `onecore\base\ngscb\cornerstone\nkpcommonlib\crypto.cpp`
- `0x1800f7710`: `onecore\base\ngscb\cornerstone\nkpcommonlib\crypto.cpp`
- `0x1800f7774`: `onecore\base\ngscb\cornerstone\nkpcommonlib\crypto.cpp`

## pseudocode

```c
__int64 __fastcall BcpDecryptWithAesCcm(
        unsigned __int8 *a1,
        __int64 a2,
        unsigned __int8 *a3,
        __int64 a4,
        PUCHAR pbInput,
        unsigned __int64 a6,
        unsigned __int8 **a7,
        unsigned __int64 *a8)
{
  NTSTATUS v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // ebx
  int v13; // eax
  __int64 v14; // rdx
  NTSTATUS v15; // eax
  int v16; // ecx
  unsigned __int64 cbOutput; // rdi
  unsigned __int8 *v18; // rbx
  NTSTATUS v19; // eax
  __int64 v20; // rcx
  int v21; // edi
  int dwFlags; // [rsp+20h] [rbp-D9h]
  int dwFlagsa; // [rsp+20h] [rbp-D9h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-A9h] BYREF
  ULONG cbInput[2]; // [rsp+58h] [rbp-A1h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-99h] BYREF
  ULONG pcbResult; // [rsp+68h] [rbp-91h] BYREF
  _BYTE v29[16]; // [rsp+70h] [rbp-89h] BYREF
  _DWORD pPaddingInfo[2]; // [rsp+80h] [rbp-79h] BYREF
  __int64 *v31; // [rsp+88h] [rbp-71h]
  int v32; // [rsp+90h] [rbp-69h]
  __int64 v33; // [rsp+98h] [rbp-61h]
  int v34; // [rsp+A0h] [rbp-59h]
  unsigned __int8 *v35; // [rsp+A8h] [rbp-51h]
  unsigned int v36; // [rsp+B0h] [rbp-49h] BYREF
  __int64 v37; // [rsp+B8h] [rbp-41h]
  __int64 v38; // [rsp+C0h] [rbp-39h]
  int v39; // [rsp+D0h] [rbp-29h]
  __int64 v40; // [rsp+E0h] [rbp-19h] BYREF
  int v41; // [rsp+E8h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+3Fh]

  BclStageOutput::BclStageOutput((BclStageOutput *)v29, 10);
  phAlgorithm = 0;
  v10 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
  if ( v10 < 0 )
  {
    v11 = 26;
LABEL_5:
    v12 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v11,
            (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\crypto.cpp",
            (const char *)(unsigned int)v10,
            dwFlags);
    goto LABEL_23;
  }
  v10 = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCCM", 0x20u, 0);
  if ( v10 < 0 )
  {
    v11 = 28;
    goto LABEL_5;
  }
  phKey = 0;
  cbInput[0] = 0;
  v13 = ULongLongToULong(0x20u, cbInput);
  v12 = v13;
  if ( v13 < 0 )
  {
    v14 = 31;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\crypto.cpp",
      (const char *)(unsigned int)v13,
      dwFlags);
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    goto LABEL_23;
  }
  phKey = 0;
  v15 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, a1, cbInput[0], 0);
  if ( v15 < 0 )
  {
    v12 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x21,
            (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\crypto.cpp",
            (const char *)(unsigned int)v15,
            dwFlags);
    goto LABEL_9;
  }
  v40 = 0;
  v41 = 0;
  memset_0(pPaddingInfo, 0, 0x58u);
  pPaddingInfo[0] = 88;
  pPaddingInfo[1] = 1;
  v31 = &v40;
  v32 = 12;
  v33 = 0;
  v34 = 0;
  v35 = a3;
  v13 = ULongLongToULong(0x10u, &v36);
  v12 = v13;
  if ( v13 < 0 )
  {
    v14 = (unsigned int)(v16 + 30);
    goto LABEL_8;
  }
  v37 = 0;
  v38 = 0;
  v39 = 0;
  cbInput[0] = 0;
  v13 = ULongLongToULong(a6, cbInput);
  v12 = v13;
  if ( v13 < 0 )
  {
    v14 = 54;
    goto LABEL_8;
  }
  cbOutput = cbInput[0];
  wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(cbInput, cbInput[0]);
  v18 = *(unsigned __int8 **)cbInput;
  if ( !*(_QWORD *)cbInput )
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\crypto.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
    goto LABEL_9;
  }
  pcbResult = 0;
  v19 = BCryptDecrypt(phKey, pbInput, cbOutput, pPaddingInfo, 0, 0, *(PUCHAR *)cbInput, cbOutput, &pcbResult, 0);
  if ( v19 >= 0 )
  {
    *a7 = v18;
    *a8 = cbOutput;
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    v12 = 0;
  }
  else
  {
    v21 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x3D,
            (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\crypto.cpp",
            (const char *)(unsigned int)v19,
            dwFlagsa);
    if ( v18 )
      wil::hlocal_secure_deleter::operator()<unsigned char>(v20, v18);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    v12 = v21;
  }
LABEL_23:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  BclStageOutput::~BclStageOutput((BclStageOutput *)v29);
  return v12;
}

```

## disassembly

```asm
0x1800f7500  mov     [rsp-8+arg_8], rbx
0x1800f7505  push    rbp
0x1800f7506  push    rsi
0x1800f7507  push    rdi
0x1800f7508  push    r12
0x1800f750a  push    r13
0x1800f750c  push    r14
0x1800f750e  push    r15
0x1800f7510  lea     rbp, [rsp-7]
0x1800f7515  sub     rsp, 100h
0x1800f751c  mov     rax, cs:__security_cookie
0x1800f7523  xor     rax, rsp
0x1800f7526  mov     [rbp+37h+var_40], rax
0x1800f752a  mov     rsi, r8
0x1800f752d  mov     rdi, rcx
0x1800f7530  mov     r12, [rbp+37h+pbInput]
0x1800f7534  mov     r14, [rbp+37h+arg_30]
0x1800f7538  mov     r15, [rbp+37h+arg_38]
0x1800f753c  mov     edx, 0Ah
0x1800f7541  lea     rcx, [rsp+130h+var_C0]
0x1800f7546  call    ??0BclStageOutput@@QEAA@W4BCL_STAGE_ID@@@Z; BclStageOutput::BclStageOutput(BCL_STAGE_ID)
0x1800f754b  nop
0x1800f754c  xor     r13d, r13d
0x1800f754f  mov     [rsp+130h+phAlgorithm], r13
0x1800f7554  xor     r9d, r9d; dwFlags
0x1800f7557  xor     r8d, r8d; pszImplementation
0x1800f755a  lea     rdx, aAes; "AES"
0x1800f7561  lea     rcx, [rsp+130h+phAlgorithm]; phAlgorithm
0x1800f7566  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800f756d  nop     dword ptr [rax+rax+00h]
0x1800f7572  test    eax, eax
0x1800f7574  jns     short loc_1800F757C
0x1800f7576  lea     edx, [r13+1Ah]
0x1800f757a  jmp     short loc_1800F75AF
0x1800f757c  mov     [rsp+130h+dwFlags], r13d; int
0x1800f7581  mov     ebx, 20h ; ' '
0x1800f7586  mov     r9d, ebx; cbInput
0x1800f7589  lea     r8, pbInput; "ChainingModeCCM"
0x1800f7590  lea     rdx, aChainingmode; "ChainingMode"
0x1800f7597  mov     rcx, [rsp+130h+phAlgorithm]; hObject
0x1800f759c  call    cs:__imp_BCryptSetProperty
0x1800f75a3  nop     dword ptr [rax+rax+00h]
0x1800f75a8  test    eax, eax
0x1800f75aa  jns     short loc_1800F75C9
0x1800f75ac  lea     edx, [rbx-4]; void *
0x1800f75af  lea     r8, aOnecoreBaseNgs_12; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f75b6  mov     r9d, eax; char *
0x1800f75b9  mov     rcx, [rbp+3Fh]; this
0x1800f75bd  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800f75c2  mov     ebx, eax
0x1800f75c4  jmp     loc_1800F77B6
0x1800f75c9  mov     [rsp+130h+phKey], r13
0x1800f75ce  mov     [rsp+130h+cbInput], r13d
0x1800f75d3  lea     rdx, [rsp+130h+cbInput]; unsigned int *
0x1800f75d8  mov     rcx, rbx; unsigned __int64
0x1800f75db  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800f75e0  mov     ebx, eax
0x1800f75e2  test    eax, eax
0x1800f75e4  jns     short loc_1800F760E
0x1800f75e6  mov     edx, 1Fh; void *
0x1800f75eb  mov     rcx, [rbp+3Fh]; this
0x1800f75ef  mov     r9d, eax; char *
0x1800f75f2  lea     r8, aOnecoreBaseNgs_12; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f75f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f75fe  nop
0x1800f75ff  lea     rcx, [rsp+130h+phKey]
0x1800f7604  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800f7609  jmp     loc_1800F77B6
0x1800f760e  mov     eax, [rsp+130h+cbInput]
0x1800f7612  mov     [rsp+130h+phKey], r13
0x1800f7617  mov     [rsp+130h+var_100], r13d; dwFlags
0x1800f761c  mov     [rsp+130h+cbSecret], eax; cbSecret
0x1800f7620  mov     qword ptr [rsp+130h+dwFlags], rdi; int
0x1800f7625  xor     r9d, r9d; cbKeyObject
0x1800f7628  xor     r8d, r8d; pbKeyObject
0x1800f762b  lea     rdx, [rsp+130h+phKey]; phKey
0x1800f7630  mov     rcx, [rsp+130h+phAlgorithm]; hAlgorithm
0x1800f7635  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800f763c  nop     dword ptr [rax+rax+00h]
0x1800f7641  test    eax, eax
0x1800f7643  jns     short loc_1800F7661
0x1800f7645  mov     rcx, [rbp+3Fh]; this
0x1800f7649  mov     r9d, eax; char *
0x1800f764c  lea     r8, aOnecoreBaseNgs_12; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f7653  mov     edx, 21h ; '!'; void *
0x1800f7658  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800f765d  mov     ebx, eax
0x1800f765f  jmp     short loc_1800F75FF
0x1800f7661  xor     eax, eax
0x1800f7663  mov     [rbp+37h+var_50], rax
0x1800f7667  mov     [rbp+37h+var_48], eax
0x1800f766a  lea     ebx, [rax+58h]
0x1800f766d  mov     r8d, ebx; Size
0x1800f7670  xor     edx, edx; Val
0x1800f7672  lea     rcx, [rbp+37h+pPaddingInfo]; void *
0x1800f7676  call    memset_0
0x1800f767b  mov     [rbp+37h+pPaddingInfo], ebx
0x1800f767e  mov     [rbp+37h+var_AC], 1
0x1800f7685  lea     rax, [rbp+37h+var_50]
0x1800f7689  mov     [rbp+37h+var_A8], rax
0x1800f768d  mov     [rbp+37h+var_A0], 0Ch
0x1800f7694  mov     [rbp+37h+var_98], r13
0x1800f7698  mov     [rbp+37h+var_90], r13d
0x1800f769c  mov     [rbp+37h+var_88], rsi
0x1800f76a0  lea     rdx, [rbp+37h+var_80]; unsigned int *
0x1800f76a4  lea     ecx, [rbx-48h]; unsigned __int64
0x1800f76a7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800f76ac  mov     ebx, eax
0x1800f76ae  test    eax, eax
0x1800f76b0  jns     short loc_1800F76BA
0x1800f76b2  lea     edx, [rcx+1Eh]
0x1800f76b5  jmp     loc_1800F75EB
0x1800f76ba  mov     [rbp+37h+var_78], r13
0x1800f76be  mov     [rbp+37h+var_70], r13
0x1800f76c2  mov     [rbp+37h+var_60], r13d
0x1800f76c6  mov     [rsp+130h+cbInput], r13d
0x1800f76cb  lea     rdx, [rsp+130h+cbInput]; unsigned int *
0x1800f76d0  mov     rcx, [rbp+37h+arg_28]; unsigned __int64
0x1800f76d4  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800f76d9  mov     ebx, eax
0x1800f76db  test    eax, eax
0x1800f76dd  jns     short loc_1800F76E9
0x1800f76df  mov     edx, 36h ; '6'
0x1800f76e4  jmp     loc_1800F75EB
0x1800f76e9  mov     edi, [rsp+130h+cbInput]
0x1800f76ed  mov     edx, edi
0x1800f76ef  lea     rcx, [rsp+130h+cbInput]
0x1800f76f4  call    ??$make_unique_hlocal_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure_nothrow<uchar [0]>(unsigned __int64)
0x1800f76f9  nop
0x1800f76fa  mov     rbx, qword ptr [rsp+130h+cbInput]
0x1800f76ff  test    rbx, rbx
0x1800f7702  jnz     short loc_1800F7727
0x1800f7704  mov     rcx, [rbp+3Fh]; this
0x1800f7708  mov     ebx, 8007000Eh
0x1800f770d  mov     r9d, ebx; char *
0x1800f7710  lea     r8, aOnecoreBaseNgs_12; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f7717  mov     edx, 39h ; '9'; void *
0x1800f771c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f7721  nop
0x1800f7722  jmp     loc_1800F75FF
0x1800f7727  mov     [rsp+130h+var_C8], r13d
0x1800f772c  mov     [rsp+130h+var_E8], r13d; dwFlags
0x1800f7731  lea     rax, [rsp+130h+var_C8]
0x1800f7736  mov     [rsp+130h+pcbResult], rax; pcbResult
0x1800f773b  mov     [rsp+130h+cbOutput], edi; cbOutput
0x1800f773f  mov     qword ptr [rsp+130h+var_100], rbx; pbOutput
0x1800f7744  mov     [rsp+130h+cbSecret], r13d; cbIV
0x1800f7749  mov     qword ptr [rsp+130h+dwFlags], r13; int
0x1800f774e  lea     r9, [rbp+37h+pPaddingInfo]; pPaddingInfo
0x1800f7752  mov     r8d, edi; cbInput
0x1800f7755  mov     rdx, r12; pbInput
0x1800f7758  mov     rcx, [rsp+130h+phKey]; hKey
0x1800f775d  call    cs:__imp_BCryptDecrypt
0x1800f7764  nop     dword ptr [rax+rax+00h]
0x1800f7769  test    eax, eax
0x1800f776b  jns     short loc_1800F77A3
0x1800f776d  mov     rcx, [rbp+3Fh]; this
0x1800f7771  mov     r9d, eax; char *
0x1800f7774  lea     r8, aOnecoreBaseNgs_12; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f777b  mov     edx, 3Dh ; '='; void *
0x1800f7780  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800f7785  mov     edi, eax
0x1800f7787  test    rbx, rbx
0x1800f778a  jz      short loc_1800F7795
0x1800f778c  mov     rdx, rbx
0x1800f778f  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
0x1800f7794  nop
0x1800f7795  lea     rcx, [rsp+130h+phKey]
0x1800f779a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800f779f  mov     ebx, edi
0x1800f77a1  jmp     short loc_1800F77B6
0x1800f77a3  mov     [r14], rbx
0x1800f77a6  mov     [r15], rdi
0x1800f77a9  lea     rcx, [rsp+130h+phKey]
0x1800f77ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800f77b3  mov     ebx, r13d
0x1800f77b6  lea     rcx, [rsp+130h+phAlgorithm]
0x1800f77bb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800f77c0  nop
0x1800f77c1  lea     rcx, [rsp+130h+var_C0]; this
0x1800f77c6  call    ??1BclStageOutput@@QEAA@XZ; BclStageOutput::~BclStageOutput(void)
0x1800f77cb  mov     eax, ebx
0x1800f77cd  mov     rcx, [rbp+37h+var_40]
0x1800f77d1  xor     rcx, rsp; StackCookie
0x1800f77d4  call    __security_check_cookie
0x1800f77d9  mov     rbx, [rsp+130h+arg_8]
0x1800f77e1  add     rsp, 100h
0x1800f77e8  pop     r15
0x1800f77ea  pop     r14
0x1800f77ec  pop     r13
0x1800f77ee  pop     r12
0x1800f77f0  pop     rdi
0x1800f77f1  pop     rsi
0x1800f77f2  pop     rbp
0x1800f77f3  retn
```
