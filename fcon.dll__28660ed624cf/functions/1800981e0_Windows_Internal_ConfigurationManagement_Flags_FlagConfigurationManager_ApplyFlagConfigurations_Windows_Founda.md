# Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::ApplyFlagConfigurations(Windows::Foundation::Collections::IVectorView<Windows::Internal::ConfigurationManagement::Flags::IFlag *> *,Windows::Foundation::Collections::IVector<Windows::Internal::ConfigurationManagement::Flags::IFlag *> * *)

- ea: `0x1800981e0`
- end: `0x1800985b8`
- name: `?ApplyFlagConfigurations@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@UEAAJPEAU?$IVectorView@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@Collections@Foundation@5@PEAPEAU?$IVector@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@785@@Z`
- size: `984`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000796c`
- `0x18000949c`
- `0x180096bd4`
- `0x1800981e0`
- `0x180098ae0`
- `0x18009ab74`
- `0x1800b7010`

## string_xrefs

- `0x18009820c`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x180098236`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x180098261`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x1800982ab`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x1800982fe`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x18009836d`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x1800983c7`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x18009846f`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x1800984f5`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::ApplyFlagConfigurations(
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
  unsigned int i; // r14d
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 *); // rbx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, _QWORD *, __int64); // rbx
  __int64 v23; // r9
  int v24; // eax
  int v25; // edi
  int v26; // eax
  unsigned int v27; // ebx
  int ApplyOperationResultFromHr; // eax
  int v29; // eax
  unsigned int v30; // ebx
  __int64 v31; // rax
  int v32; // [rsp+20h] [rbp-58h]
  unsigned int v33; // [rsp+30h] [rbp-48h] BYREF
  __int64 v34; // [rsp+38h] [rbp-40h] BYREF
  __int64 v35; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v36[6]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v38; // [rsp+88h] [rbp+10h] BYREF
  unsigned int v39; // [rsp+98h] [rbp+20h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
      (const char *)0x80070057LL,
      v32);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
      (const char *)0x80070057LL,
      v32);
    return 2147942487LL;
  }
  v7 = Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::ValidateCallerPrivileges();
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x168,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
      (const char *)(unsigned int)v7,
      v32);
    return v8;
  }
  *a3 = 0;
  v34 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  v10 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::ConfigurationManagement::Flags::IFlag,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ConfigurationManagement::Flags::IFlag *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ConfigurationManagement::Flags::IFlag *>>>(
          v9,
          &v34);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16C,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
      (const char *)(unsigned int)v10,
      v32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    return v11;
  }
  v39 = 0;
  try
  {
    v12 = (*(__int64 (**)(void))(*(_QWORD *)a2 + 56LL))();
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x171,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
        (const char *)(unsigned int)v12,
        v32);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      return v13;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= v39 )
      {
        v31 = v34;
        v34 = 0;
        *a3 = v31;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
        return 0;
      }
      v35 = 0;
      v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a2 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
      v17 = v16(a2, i, &v35);
      v18 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x175,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
          (const char *)(unsigned int)v17,
          v32);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
        return v18;
      }
      v33 = 0;
      v19 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v35 + 56LL))(v35, &v33);
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x178,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
          (const char *)(unsigned int)v19,
          v32);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
        return v20;
      }
      v36[0] = 0;
      v21 = *(_QWORD *)(a1 + 40);
      v22 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD *, __int64))(*(_QWORD *)v21 + 96LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v36);
      LOBYTE(v23) = 1;
      v24 = v22(v21, v35, v36, v23);
      v25 = v24;
      v38 = 4;
      if ( v24 < 0 )
      {
        ApplyOperationResultFromHr = anonymous_namespace_::GetApplyOperationResultFromHr(
                                       *(_QWORD *)(a1 + 40),
                                       v33,
                                       (unsigned int)v24);
        v38 = ApplyOperationResultFromHr;
      }
      else
      {
        if ( !v36[0] )
          goto LABEL_32;
        v26 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v36[0] + 152LL))(v36[0], &v38);
        v27 = v26;
        if ( v26 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17F,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
            (const char *)(unsigned int)v26,
            v32);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v36);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
          return v27;
        }
        ApplyOperationResultFromHr = v38;
      }
      if ( !ApplyOperationResultFromHr && v36[0] )
      {
        v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 104LL))(v34);
        v30 = v29;
        if ( v29 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x188,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
            (const char *)(unsigned int)v29,
            v32);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v36);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
          return v30;
        }
        ApplyOperationResultFromHr = v38;
      }
      if ( v25 < 0 && ApplyOperationResultFromHr == 4 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v36);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
        return (unsigned int)v25;
      }
LABEL_32:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v36);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x19A,
                           (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\fla"
                                         "gconfigurationmanager.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x1800981e0  mov     [rsp+arg_0], rbx
0x1800981e5  push    rsi
0x1800981e6  push    rdi
0x1800981e7  push    r13
0x1800981e9  push    r14
0x1800981eb  push    r15
0x1800981ed  sub     rsp, 50h
0x1800981f1  mov     r15, r8
0x1800981f4  mov     rsi, rdx
0x1800981f7  mov     r13, rcx
0x1800981fa  test    rdx, rdx
0x1800981fd  jnz     short loc_180098224
0x1800981ff  mov     rcx, [rsp+78h]; this
0x180098204  mov     ebx, 80070057h
0x180098209  mov     r9d, ebx; char *
0x18009820c  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x180098213  mov     edx, 166h; void *
0x180098218  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009821d  mov     eax, ebx
0x18009821f  jmp     loc_1800985A2
0x180098224  test    r15, r15
0x180098227  jnz     short loc_18009824E
0x180098229  mov     rcx, [rsp+78h]; this
0x18009822e  mov     ebx, 80070057h
0x180098233  mov     r9d, ebx; char *
0x180098236  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x18009823d  mov     edx, 167h; void *
0x180098242  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098247  mov     eax, ebx
0x180098249  jmp     loc_1800985A2
0x18009824e  call    ?ValidateCallerPrivileges@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@CAJXZ; Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::ValidateCallerPrivileges(void)
0x180098253  mov     ebx, eax
0x180098255  test    eax, eax
0x180098257  jns     short loc_180098279
0x180098259  mov     rcx, [rsp+78h]; this
0x18009825e  mov     r9d, eax; char *
0x180098261  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x180098268  mov     edx, 168h; void *
0x18009826d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098272  mov     eax, ebx
0x180098274  jmp     loc_1800985A2
0x180098279  mov     qword ptr [r15], 0
0x180098280  mov     [rsp+78h+var_40], 0
0x180098289  lea     rcx, [rsp+78h+var_40]
0x18009828e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098293  lea     rdx, [rsp+78h+var_40]
0x180098298  call    ??$CreateExternalObjectVector@UIFlag@Flags@ConfigurationManagement@Internal@Windows@@V?$Vector@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@U?$DefaultVectorOptions@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@U?$DefaultVectorOptions@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::ConfigurationManagement::Flags::IFlag,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ConfigurationManagement::Flags::IFlag *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ConfigurationManagement::Flags::IFlag *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ConfigurationManagement::Flags::IFlag *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ConfigurationManagement::Flags::IFlag *>> * *)
0x18009829d  mov     ebx, eax
0x18009829f  test    eax, eax
0x1800982a1  jns     short loc_1800982CE
0x1800982a3  mov     rcx, [rsp+78h]; this
0x1800982a8  mov     r9d, eax; char *
0x1800982ab  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x1800982b2  mov     edx, 16Ch; void *
0x1800982b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800982bc  nop
0x1800982bd  lea     rcx, [rsp+78h+var_40]
0x1800982c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800982c7  mov     eax, ebx
0x1800982c9  jmp     loc_1800985A2
0x1800982ce  mov     [rsp+78h+arg_18], 0
0x1800982d9  mov     rax, [rsi]
0x1800982dc  lea     rdx, [rsp+78h+arg_18]
0x1800982e4  mov     rcx, rsi
0x1800982e7  mov     rax, [rax+38h]
0x1800982eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800982f0  mov     ebx, eax
0x1800982f2  test    eax, eax
0x1800982f4  jns     short loc_180098321
0x1800982f6  mov     rcx, [rsp+78h]; this
0x1800982fb  mov     r9d, eax; char *
0x1800982fe  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x180098305  mov     edx, 171h; void *
0x18009830a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009830f  nop
0x180098310  lea     rcx, [rsp+78h+var_40]
0x180098315  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009831a  mov     eax, ebx
0x18009831c  jmp     loc_1800985A2
0x180098321  xor     r14d, r14d
0x180098324  cmp     r14d, [rsp+78h+arg_18]
0x18009832c  jnb     loc_18009857C
0x180098332  mov     [rsp+78h+var_38], 0
0x18009833b  mov     rax, [rsi]
0x18009833e  mov     rbx, [rax+30h]
0x180098342  lea     rcx, [rsp+78h+var_38]
0x180098347  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009834c  lea     r8, [rsp+78h+var_38]
0x180098351  mov     edx, r14d
0x180098354  mov     rcx, rsi
0x180098357  mov     rax, rbx
0x18009835a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009835f  mov     ebx, eax
0x180098361  test    eax, eax
0x180098363  jns     short loc_18009839B
0x180098365  mov     rcx, [rsp+78h]; this
0x18009836a  mov     r9d, eax; char *
0x18009836d  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x180098374  mov     edx, 175h; void *
0x180098379  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009837e  nop
0x18009837f  lea     rcx, [rsp+78h+var_38]
0x180098384  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098389  nop
0x18009838a  lea     rcx, [rsp+78h+var_40]
0x18009838f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098394  mov     eax, ebx
0x180098396  jmp     loc_1800985A2
0x18009839b  mov     [rsp+78h+var_48], 0
0x1800983a3  mov     rcx, [rsp+78h+var_38]
0x1800983a8  mov     rax, [rcx]
0x1800983ab  lea     rdx, [rsp+78h+var_48]
0x1800983b0  mov     rax, [rax+38h]
0x1800983b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800983b9  mov     ebx, eax
0x1800983bb  test    eax, eax
0x1800983bd  jns     short loc_1800983F5
0x1800983bf  mov     rcx, [rsp+78h]; this
0x1800983c4  mov     r9d, eax; char *
0x1800983c7  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x1800983ce  mov     edx, 178h; void *
0x1800983d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800983d8  nop
0x1800983d9  lea     rcx, [rsp+78h+var_38]
0x1800983de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800983e3  nop
0x1800983e4  lea     rcx, [rsp+78h+var_40]
0x1800983e9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800983ee  mov     eax, ebx
0x1800983f0  jmp     loc_1800985A2
0x1800983f5  mov     [rsp+78h+var_30], 0
0x1800983fe  mov     rdi, [r13+28h]
0x180098402  mov     rax, [rdi]
0x180098405  mov     rbx, [rax+60h]
0x180098409  lea     rcx, [rsp+78h+var_30]
0x18009840e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098413  mov     r9b, 1
0x180098416  lea     r8, [rsp+78h+var_30]
0x18009841b  mov     rdx, [rsp+78h+var_38]
0x180098420  mov     rcx, rdi
0x180098423  mov     rax, rbx
0x180098426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009842b  mov     edi, eax
0x18009842d  mov     [rsp+78h+arg_8], 4
0x180098438  test    eax, eax
0x18009843a  js      short loc_1800984B1
0x18009843c  mov     rcx, [rsp+78h+var_30]
0x180098441  test    rcx, rcx
0x180098444  jz      loc_18009855F
0x18009844a  mov     rdx, [rcx]
0x18009844d  mov     rax, [rdx+98h]
0x180098454  lea     rdx, [rsp+78h+arg_8]
0x18009845c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098461  mov     ebx, eax
0x180098463  test    eax, eax
0x180098465  jns     short loc_1800984A8
0x180098467  mov     rcx, [rsp+78h]; this
0x18009846c  mov     r9d, eax; char *
0x18009846f  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x180098476  mov     edx, 17Fh; void *
0x18009847b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098480  nop
0x180098481  lea     rcx, [rsp+78h+var_30]
0x180098486  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009848b  nop
0x18009848c  lea     rcx, [rsp+78h+var_38]
0x180098491  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098496  nop
0x180098497  lea     rcx, [rsp+78h+var_40]
0x18009849c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800984a1  mov     eax, ebx
0x1800984a3  jmp     loc_1800985A2
0x1800984a8  mov     eax, [rsp+78h+arg_8]
0x1800984af  jmp     short loc_1800984C8
0x1800984b1  mov     r8d, edi
0x1800984b4  mov     edx, [rsp+78h+var_48]
0x1800984b8  mov     rcx, [r13+28h]
0x1800984bc  call    _anonymous_namespace___GetApplyOperationResultFromHr
0x1800984c1  mov     [rsp+78h+arg_8], eax
0x1800984c8  test    eax, eax
0x1800984ca  jnz     short loc_180098532
0x1800984cc  mov     rdx, [rsp+78h+var_30]
0x1800984d1  test    rdx, rdx
0x1800984d4  jz      short loc_180098532
0x1800984d6  mov     rcx, [rsp+78h+var_40]
0x1800984db  mov     rax, [rcx]
0x1800984de  mov     rax, [rax+68h]
0x1800984e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800984e7  mov     ebx, eax
0x1800984e9  test    eax, eax
0x1800984eb  jns     short loc_18009852B
0x1800984ed  mov     rcx, [rsp+78h]; this
0x1800984f2  mov     r9d, eax; char *
0x1800984f5  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x1800984fc  mov     edx, 188h; void *
0x180098501  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098506  nop
0x180098507  lea     rcx, [rsp+78h+var_30]
0x18009850c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098511  nop
0x180098512  lea     rcx, [rsp+78h+var_38]
0x180098517  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009851c  nop
0x18009851d  lea     rcx, [rsp+78h+var_40]
0x180098522  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098527  mov     eax, ebx
0x180098529  jmp     short loc_1800985A2
0x18009852b  mov     eax, [rsp+78h+arg_8]
0x180098532  test    edi, edi
0x180098534  jns     short loc_18009855F
0x180098536  cmp     eax, 4
0x180098539  jnz     short loc_18009855F
0x18009853b  lea     rcx, [rsp+78h+var_30]
0x180098540  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098545  nop
0x180098546  lea     rcx, [rsp+78h+var_38]
0x18009854b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098550  nop
0x180098551  lea     rcx, [rsp+78h+var_40]
0x180098556  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009855b  mov     eax, edi
0x18009855d  jmp     short loc_1800985A2
0x18009855f  lea     rcx, [rsp+78h+var_30]
0x180098564  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098569  nop
0x18009856a  lea     rcx, [rsp+78h+var_38]
0x18009856f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098574  inc     r14d
0x180098577  jmp     loc_180098324
0x18009857c  mov     rax, [rsp+78h+var_40]
0x180098581  mov     [rsp+78h+var_40], 0
0x18009858a  mov     [r15], rax
0x18009858d  lea     rcx, [rsp+78h+var_40]
0x180098592  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098597  xor     eax, eax
0x180098599  jmp     short loc_1800985A2
0x18009859b  mov     eax, [rsp+78h+arg_8]
0x1800985a2  mov     rbx, [rsp+78h+arg_0]
0x1800985aa  add     rsp, 50h
0x1800985ae  pop     r15
0x1800985b0  pop     r14
0x1800985b2  pop     r13
0x1800985b4  pop     rdi
0x1800985b5  pop     rsi
0x1800985b6  retn
```
