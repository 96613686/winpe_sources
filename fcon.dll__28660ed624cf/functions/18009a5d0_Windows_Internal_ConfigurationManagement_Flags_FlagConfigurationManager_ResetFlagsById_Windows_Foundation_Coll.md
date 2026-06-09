# Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::ResetFlagsById(Windows::Foundation::Collections::IVectorView<uint> *,Windows::Foundation::Collections::IVector<Windows::Internal::ConfigurationManagement::Flags::IFlag *> * *)

- ea: `0x18009a5d0`
- end: `0x18009a8ea`
- name: `?ResetFlagsById@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@UEAAJPEAU?$IVectorView@I@Collections@Foundation@5@PEAPEAU?$IVector@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@785@@Z`
- size: `794`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000796c`
- `0x18000949c`
- `0x180096bd4`
- `0x18009a5d0`
- `0x18009ab74`
- `0x1800b7010`

## string_xrefs

- `0x18009a5fd`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x18009a628`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x18009a656`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x18009a699`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x18009a6e8`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x18009a745`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x18009a7d7`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x18009a879`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::ResetFlagsById(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 result; // rax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  const char *v14; // r9
  unsigned int i; // r15d
  int v16; // eax
  unsigned int v17; // ebx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, _QWORD *); // rbx
  int v20; // ebx
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // eax
  int v24; // eax
  unsigned int v25; // ebx
  __int64 v26; // rax
  int v27; // [rsp+20h] [rbp-48h] BYREF
  __int64 v28; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v29[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v31; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v32; // [rsp+88h] [rbp+20h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B5,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
      (const char *)0x80070057LL,
      v27);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
      (const char *)0x80070057LL,
      v27);
    return 2147942487LL;
  }
  v7 = Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::ValidateCallerPrivileges();
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B7,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
      (const char *)(unsigned int)v7,
      v27);
    return v8;
  }
  *a3 = 0;
  v28 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  v10 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::ConfigurationManagement::Flags::IFlag,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ConfigurationManagement::Flags::IFlag *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ConfigurationManagement::Flags::IFlag *>>>(
          v9,
          &v28);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
      (const char *)(unsigned int)v10,
      v27);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    return v11;
  }
  v32 = 0;
  try
  {
    v12 = (*(__int64 (**)(void))(*(_QWORD *)a2 + 56LL))();
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BE,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
        (const char *)(unsigned int)v12,
        v27);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      return v13;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= v32 )
      {
        v26 = v28;
        v28 = 0;
        *a3 = v26;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
        return 0;
      }
      v27 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)a2 + 48LL))(a2, i, &v27);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C2,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
          (const char *)(unsigned int)v16,
          v27);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
        return v17;
      }
      v29[0] = 0;
      v18 = *(_QWORD *)(a1 + 40);
      v19 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v18 + 104LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
      v20 = v19(v18, (unsigned int)v27, v29);
      v31 = 4;
      if ( v20 < 0 )
      {
        if ( v20 == -2147024809 )
        {
          v23 = 2;
        }
        else
        {
          v23 = 1;
          if ( v20 != -2147023728 )
            v23 = 4;
        }
        v31 = v23;
        if ( v23 == 4 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
          return (unsigned int)v20;
        }
      }
      else
      {
        if ( !v29[0] )
          goto LABEL_32;
        v21 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v29[0] + 152LL))(v29[0], &v31);
        v22 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1C9,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
            (const char *)(unsigned int)v21,
            v27);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
          return v22;
        }
        v23 = v31;
      }
      if ( !v23 )
      {
        if ( v29[0] )
        {
          v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 104LL))(v28);
          v25 = v24;
          if ( v24 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1D7,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
              (const char *)(unsigned int)v24,
              v27);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
            return v25;
          }
        }
      }
LABEL_32:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1DF,
                           (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\fla"
                                         "gconfigurationmanager.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x18009a5d0  mov     [rsp+arg_0], rbx
0x18009a5d5  push    rdi
0x18009a5d6  push    r12
0x18009a5d8  push    r13
0x18009a5da  push    r14
0x18009a5dc  push    r15
0x18009a5de  sub     rsp, 40h
0x18009a5e2  mov     r12, r8
0x18009a5e5  mov     r14, rdx
0x18009a5e8  mov     r13, rcx
0x18009a5eb  xor     edi, edi
0x18009a5ed  test    rdx, rdx
0x18009a5f0  jnz     short loc_18009A618
0x18009a5f2  mov     rcx, [rsp+68h]; this
0x18009a5f7  mov     r9d, 80070057h; char *
0x18009a5fd  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x18009a604  mov     edx, 1B5h; void *
0x18009a609  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a60e  mov     eax, 80070057h
0x18009a613  jmp     loc_18009A8D6
0x18009a618  test    r12, r12
0x18009a61b  jnz     short loc_18009A643
0x18009a61d  mov     rcx, [rsp+68h]; this
0x18009a622  mov     r9d, 80070057h; char *
0x18009a628  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x18009a62f  mov     edx, 1B6h; void *
0x18009a634  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a639  mov     eax, 80070057h
0x18009a63e  jmp     loc_18009A8D6
0x18009a643  call    ?ValidateCallerPrivileges@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@CAJXZ; Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::ValidateCallerPrivileges(void)
0x18009a648  mov     ebx, eax
0x18009a64a  test    eax, eax
0x18009a64c  jns     short loc_18009A66E
0x18009a64e  mov     rcx, [rsp+68h]; this
0x18009a653  mov     r9d, eax; char *
0x18009a656  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x18009a65d  mov     edx, 1B7h; void *
0x18009a662  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a667  mov     eax, ebx
0x18009a669  jmp     loc_18009A8D6
0x18009a66e  mov     [r12], rdi
0x18009a672  mov     [rsp+68h+var_40], rdi
0x18009a677  lea     rcx, [rsp+68h+var_40]
0x18009a67c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a681  lea     rdx, [rsp+68h+var_40]
0x18009a686  call    ??$CreateExternalObjectVector@UIFlag@Flags@ConfigurationManagement@Internal@Windows@@V?$Vector@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@U?$DefaultVectorOptions@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@U?$DefaultVectorOptions@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::ConfigurationManagement::Flags::IFlag,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ConfigurationManagement::Flags::IFlag *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ConfigurationManagement::Flags::IFlag *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ConfigurationManagement::Flags::IFlag *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ConfigurationManagement::Flags::IFlag *>> * *)
0x18009a68b  mov     ebx, eax
0x18009a68d  test    eax, eax
0x18009a68f  jns     short loc_18009A6BC
0x18009a691  mov     rcx, [rsp+68h]; this
0x18009a696  mov     r9d, eax; char *
0x18009a699  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x18009a6a0  mov     edx, 1BBh; void *
0x18009a6a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a6aa  nop
0x18009a6ab  lea     rcx, [rsp+68h+var_40]
0x18009a6b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a6b5  mov     eax, ebx
0x18009a6b7  jmp     loc_18009A8D6
0x18009a6bc  mov     [rsp+68h+arg_18], edi
0x18009a6c3  mov     rax, [r14]
0x18009a6c6  lea     rdx, [rsp+68h+arg_18]
0x18009a6ce  mov     rcx, r14
0x18009a6d1  mov     rax, [rax+38h]
0x18009a6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a6da  mov     ebx, eax
0x18009a6dc  test    eax, eax
0x18009a6de  jns     short loc_18009A70B
0x18009a6e0  mov     rcx, [rsp+68h]; this
0x18009a6e5  mov     r9d, eax; char *
0x18009a6e8  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x18009a6ef  mov     edx, 1BEh; void *
0x18009a6f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a6f9  nop
0x18009a6fa  lea     rcx, [rsp+68h+var_40]
0x18009a6ff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a704  mov     eax, ebx
0x18009a706  jmp     loc_18009A8D6
0x18009a70b  mov     r15d, edi
0x18009a70e  cmp     r15d, [rsp+68h+arg_18]
0x18009a716  jnb     loc_18009A8B6
0x18009a71c  mov     [rsp+68h+var_48], edi; int
0x18009a720  mov     rax, [r14]
0x18009a723  lea     r8, [rsp+68h+var_48]
0x18009a728  mov     edx, r15d
0x18009a72b  mov     rcx, r14
0x18009a72e  mov     rax, [rax+30h]
0x18009a732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a737  mov     ebx, eax
0x18009a739  test    eax, eax
0x18009a73b  jns     short loc_18009A768
0x18009a73d  mov     rcx, [rsp+68h]; this
0x18009a742  mov     r9d, eax; char *
0x18009a745  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x18009a74c  mov     edx, 1C2h; void *
0x18009a751  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a756  nop
0x18009a757  lea     rcx, [rsp+68h+var_40]
0x18009a75c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a761  mov     eax, ebx
0x18009a763  jmp     loc_18009A8D6
0x18009a768  mov     [rsp+68h+var_38], rdi
0x18009a76d  mov     rdi, [r13+28h]
0x18009a771  mov     rax, [rdi]
0x18009a774  mov     rbx, [rax+68h]
0x18009a778  lea     rcx, [rsp+68h+var_38]
0x18009a77d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a782  lea     r8, [rsp+68h+var_38]
0x18009a787  mov     edx, [rsp+68h+var_48]
0x18009a78b  mov     rcx, rdi
0x18009a78e  mov     rax, rbx
0x18009a791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a796  mov     ebx, eax
0x18009a798  mov     ecx, 4
0x18009a79d  mov     [rsp+68h+arg_8], ecx
0x18009a7a1  xor     edi, edi
0x18009a7a3  test    eax, eax
0x18009a7a5  js      short loc_18009A80B
0x18009a7a7  mov     rcx, [rsp+68h+var_38]
0x18009a7ac  test    rcx, rcx
0x18009a7af  jz      loc_18009A8A4
0x18009a7b5  mov     rax, [rcx]
0x18009a7b8  lea     rdx, [rsp+68h+arg_8]
0x18009a7bd  mov     rax, [rax+98h]
0x18009a7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a7c9  mov     ebx, eax
0x18009a7cb  test    eax, eax
0x18009a7cd  jns     short loc_18009A805
0x18009a7cf  mov     rcx, [rsp+68h]; this
0x18009a7d4  mov     r9d, eax; char *
0x18009a7d7  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x18009a7de  mov     edx, 1C9h; void *
0x18009a7e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a7e8  nop
0x18009a7e9  lea     rcx, [rsp+68h+var_38]
0x18009a7ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a7f3  nop
0x18009a7f4  lea     rcx, [rsp+68h+var_40]
0x18009a7f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a7fe  mov     eax, ebx
0x18009a800  jmp     loc_18009A8D6
0x18009a805  mov     eax, [rsp+68h+arg_8]
0x18009a809  jmp     short loc_18009A84C
0x18009a80b  cmp     ebx, 80070057h
0x18009a811  jz      short loc_18009A823
0x18009a813  mov     eax, 1
0x18009a818  cmp     ebx, 80070490h
0x18009a81e  cmovnz  eax, ecx
0x18009a821  jmp     short loc_18009A828
0x18009a823  mov     eax, 2
0x18009a828  mov     [rsp+68h+arg_8], eax
0x18009a82c  cmp     eax, ecx
0x18009a82e  jnz     short loc_18009A84C
0x18009a830  lea     rcx, [rsp+68h+var_38]
0x18009a835  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a83a  nop
0x18009a83b  lea     rcx, [rsp+68h+var_40]
0x18009a840  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a845  mov     eax, ebx
0x18009a847  jmp     loc_18009A8D6
0x18009a84c  test    eax, eax
0x18009a84e  jnz     short loc_18009A8A4
0x18009a850  mov     rdx, [rsp+68h+var_38]
0x18009a855  test    rdx, rdx
0x18009a858  jz      short loc_18009A8A4
0x18009a85a  mov     rcx, [rsp+68h+var_40]
0x18009a85f  mov     rax, [rcx]
0x18009a862  mov     rax, [rax+68h]
0x18009a866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a86b  mov     ebx, eax
0x18009a86d  test    eax, eax
0x18009a86f  jns     short loc_18009A8A4
0x18009a871  mov     rcx, [rsp+68h]; this
0x18009a876  mov     r9d, eax; char *
0x18009a879  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x18009a880  mov     edx, 1D7h; void *
0x18009a885  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a88a  nop
0x18009a88b  lea     rcx, [rsp+68h+var_38]
0x18009a890  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a895  nop
0x18009a896  lea     rcx, [rsp+68h+var_40]
0x18009a89b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a8a0  mov     eax, ebx
0x18009a8a2  jmp     short loc_18009A8D6
0x18009a8a4  lea     rcx, [rsp+68h+var_38]
0x18009a8a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a8ae  inc     r15d
0x18009a8b1  jmp     loc_18009A70E
0x18009a8b6  mov     rax, [rsp+68h+var_40]
0x18009a8bb  mov     [rsp+68h+var_40], rdi
0x18009a8c0  mov     [r12], rax
0x18009a8c4  lea     rcx, [rsp+68h+var_40]
0x18009a8c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a8ce  xor     eax, eax
0x18009a8d0  jmp     short loc_18009A8D6
0x18009a8d2  mov     eax, [rsp+68h+arg_8]
0x18009a8d6  mov     rbx, [rsp+68h+arg_0]
0x18009a8db  add     rsp, 40h
0x18009a8df  pop     r15
0x18009a8e1  pop     r14
0x18009a8e3  pop     r13
0x18009a8e5  pop     r12
0x18009a8e7  pop     rdi
0x18009a8e8  retn
```
