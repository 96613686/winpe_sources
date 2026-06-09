# CloudExperienceHostAPI::OobeKeyboardStaticsCore::GetInputLanguages(Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeInputLanguage *> * *)

- ea: `0x180048640`
- end: `0x180048874`
- name: `?GetInputLanguages@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@UEAAJPEAPEAU?$IVectorView@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@@Z`
- size: `564`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x18000b098`
- `0x18000d664`
- `0x1800117bc`
- `0x180012e2c`
- `0x180015524`
- `0x180035080`
- `0x1800359d8`
- `0x180038854`
- `0x180045d88`
- `0x180047398`
- `0x180047b68`
- `0x180048640`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004868b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004868b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048755`
- `WinLangdb!LanguagesDatabaseGetLeafLanguages` at `0x180048703`
- `WinLangdb!LanguagesDatabaseGetLeafLanguages` at `0x180048703`

## string_xrefs

- `0x180048721`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x18004879a`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180048813`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CloudExperienceHostAPI::OobeKeyboardStaticsCore::GetInputLanguages(RTL_SRWLOCK *a1, _QWORD *a2)
{
  PVOID Ptr; // rcx
  __int64 v6; // rcx
  int v7; // eax
  int LeafLanguages; // ebx
  __int64 v9; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // r15
  const WCHAR *v12; // rcx
  int v13; // eax
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  const char *v17; // r9
  int v18[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v19; // [rsp+28h] [rbp-30h] BYREF
  __int64 v20; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v22; // [rsp+60h] [rbp+8h]
  HSTRING string; // [rsp+68h] [rbp+10h] BYREF
  RTL_SRWLOCK *v24; // [rsp+70h] [rbp+18h] BYREF

  CloudExperienceHostCoreTelemetry::GlobalizationState<char const (&)[71]>("CloudExperienceHostAPI::OobeKeyboardStaticsCo"
                                                                           "re::GetInputLanguages");
  *a2 = 0;
  Ptr = a1[7].Ptr;
  if ( Ptr )
    return (*(__int64 (__fastcall **)(PVOID, _QWORD *))(*(_QWORD *)Ptr + 56LL))(Ptr, a2);
  AcquireSRWLockExclusive(a1 + 8);
  v24 = a1 + 8;
  if ( !a1[9].Ptr )
  {
    a1[9].Ptr = 0;
    v7 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<CloudExperienceHostAPI::IOobeInputLanguage,Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeInputLanguage *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeInputLanguage *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeInputLanguage *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeInputLanguage *>>>(
           v6,
           &a1[9]);
    LeafLanguages = v7;
    if ( v7 < 0 )
    {
      v9 = 143;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
        (const char *)(unsigned int)v7,
        v18[0]);
      goto LABEL_19;
    }
    CloudExperienceHostAPI::OobeKeyboardStaticsCore::s_inputLanguagesPopulating = (__int64)a1[9].Ptr;
    string = 0;
    *(_QWORD *)v18 = &string;
    v19 = 0;
    LOBYTE(v20) = 1;
    LeafLanguages = LanguagesDatabaseGetLeafLanguages(2, 0, 59, &v19);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(v18);
    if ( LeafLanguages < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x98,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
        (const char *)(unsigned int)LeafLanguages,
        v18[0]);
      Windows::Internal::String::~String(&string);
      CloudExperienceHostAPI::OobeKeyboardStaticsCore::s_inputLanguagesPopulating = 0;
LABEL_19:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v24);
      return (unsigned int)LeafLanguages;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    try
    {
      VectorFromDelimitedStringNonConst(v18, StringRawBuffer);
      v16 = *(_QWORD *)v18;
      v14 = *(_QWORD *)v18;
      v15 = v19;
      v11 = v19;
      while ( v14 != v11 )
      {
        v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
        v13 = CloudExperienceHostAPI::OobeKeyboardStaticsCore::AddLocaleToInputLanguages(v12);
        if ( v13 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x9F,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
            (const char *)(unsigned int)v13,
            v18[0]);
        v14 += 32;
        v15 = v19;
        v16 = *(_QWORD *)v18;
      }
      if ( v16 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v16, v15);
        std::_Deallocate<16>(*(_QWORD *)v18, (v20 - *(_QWORD *)v18) & 0xFFFFFFFFFFFFFFE0uLL);
      }
      Windows::Internal::String::~String(&string);
      CloudExperienceHostAPI::OobeKeyboardStaticsCore::s_inputLanguagesPopulating = 0;
    }
    catch ( ... )
    {
      v22 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0xA2,
              (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
              v17);
      Windows::Internal::String::~String(&string);
      CloudExperienceHostAPI::OobeKeyboardStaticsCore::s_inputLanguagesPopulating = 0;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v24);
      return v22;
    }
  }
  v7 = (*(__int64 (__fastcall **)(PVOID, _QWORD *))(*(_QWORD *)a1[9].Ptr + 64LL))(a1[9].Ptr, a2);
  LeafLanguages = v7;
  if ( v7 < 0 )
  {
    v9 = 164;
    goto LABEL_18;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v24);
  return 0;
}

```

## disassembly

```asm
0x180048640  mov     [rsp+arg_18], rbx
0x180048645  push    rsi
0x180048646  push    r14
0x180048648  push    r15
0x18004864a  sub     rsp, 40h
0x18004864e  mov     r14, rdx
0x180048651  mov     rsi, rcx
0x180048654  lea     rcx, aCloudexperienc_26; "CloudExperienceHostAPI::OobeKeyboardSta"...
0x18004865b  call    ??$GlobalizationState@AEAY0EH@$$CBD@CloudExperienceHostCoreTelemetry@@SAXAEAY0EH@$$CBD@Z; CloudExperienceHostCoreTelemetry::GlobalizationState<char const (&)[71]>(char const (&)[71])
0x180048660  mov     qword ptr [r14], 0
0x180048667  mov     rcx, [rsi+38h]
0x18004866b  test    rcx, rcx
0x18004866e  jz      short loc_180048684
0x180048670  mov     rax, [rcx]
0x180048673  mov     rdx, r14
0x180048676  mov     rax, [rax+38h]
0x18004867a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004867f  jmp     loc_180048865
0x180048684  lea     rbx, [rsi+40h]
0x180048688  mov     rcx, rbx; SRWLock
0x18004868b  call    cs:__imp_AcquireSRWLockExclusive
0x180048691  mov     [rsp+58h+arg_10], rbx
0x180048696  cmp     qword ptr [rsi+48h], 0
0x18004869b  jnz     loc_1800487F2
0x1800486a1  mov     qword ptr [rsi+48h], 0
0x1800486a9  lea     rdx, [rsi+48h]
0x1800486ad  call    ??$CreateExternalObjectVector@UIOobeInputLanguage@CloudExperienceHostAPI@@V?$Vector@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@U?$DefaultEqualityPredicate@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@@4567@U?$DefaultVectorOptions@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@@4567@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@U?$DefaultEqualityPredicate@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@@4567@U?$DefaultVectorOptions@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@@4567@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<CloudExperienceHostAPI::IOobeInputLanguage,Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeInputLanguage *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeInputLanguage *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeInputLanguage *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeInputLanguage *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeInputLanguage *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeInputLanguage *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeInputLanguage *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeInputLanguage *>> * *)
0x1800486b2  mov     ebx, eax
0x1800486b4  test    eax, eax
0x1800486b6  jns     short loc_1800486C2
0x1800486b8  mov     edx, 8Fh
0x1800486bd  jmp     loc_180048810
0x1800486c2  mov     rax, [rsi+48h]
0x1800486c6  mov     cs:?s_inputLanguagesPopulating@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@0PEAU?$IVector@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@EA, rax; Windows::Foundation::Collections::IVector<CloudExperienceHostAPI::IOobeInputLanguage *> * CloudExperienceHostAPI::OobeKeyboardStaticsCore::s_inputLanguagesPopulating
0x1800486cd  mov     [rsp+58h+arg_1], 1
0x1800486d2  mov     [rsp+58h+string], 0
0x1800486db  lea     rax, [rsp+58h+string]
0x1800486e0  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800486e5  mov     [rsp+58h+var_30], 0
0x1800486ee  mov     byte ptr [rsp+58h+var_28], 1
0x1800486f3  mov     r8d, 3Bh ; ';'
0x1800486f9  lea     r9, [rsp+58h+var_30]
0x1800486fe  xor     edx, edx
0x180048700  lea     ecx, [rdx+2]
0x180048703  call    cs:__imp_LanguagesDatabaseGetLeafLanguages
0x180048709  mov     ebx, eax
0x18004870b  lea     rcx, [rsp+58h+var_38]
0x180048710  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x180048715  test    ebx, ebx
0x180048717  jns     short loc_18004874E
0x180048719  mov     rcx, [rsp+58h]; this
0x18004871e  mov     r9d, ebx; char *
0x180048721  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180048728  mov     edx, 98h; void *
0x18004872d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048732  nop
0x180048733  lea     rcx, [rsp+58h+string]; this
0x180048738  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004873d  nop
0x18004873e  mov     cs:?s_inputLanguagesPopulating@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@0PEAU?$IVector@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@EA, 0; Windows::Foundation::Collections::IVector<CloudExperienceHostAPI::IOobeInputLanguage *> * CloudExperienceHostAPI::OobeKeyboardStaticsCore::s_inputLanguagesPopulating
0x180048749  jmp     loc_180048825
0x18004874e  xor     edx, edx; length
0x180048750  mov     rcx, [rsp+58h+string]; string
0x180048755  call    cs:__imp_WindowsGetStringRawBuffer
0x18004875b  mov     rdx, rax
0x18004875e  lea     rcx, [rsp+58h+var_38]
0x180048763  call    ?VectorFromDelimitedStringNonConst@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGG@Z; VectorFromDelimitedStringNonConst(ushort const *,ushort)
0x180048768  nop
0x180048769  mov     rcx, qword ptr [rsp+58h+var_38]
0x18004876e  mov     rbx, rcx
0x180048771  mov     rdx, [rsp+58h+var_30]
0x180048776  mov     r15, rdx
0x180048779  cmp     rbx, r15
0x18004877c  jz      short loc_1800487BB
0x18004877e  mov     rcx, rbx
0x180048781  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180048786  mov     rcx, rax; lpLocaleName
0x180048789  call    ?AddLocaleToInputLanguages@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@CAJPEBG@Z; CloudExperienceHostAPI::OobeKeyboardStaticsCore::AddLocaleToInputLanguages(ushort const *)
0x18004878e  test    eax, eax
0x180048790  jns     short loc_1800487AB
0x180048792  mov     rcx, [rsp+58h]; this
0x180048797  mov     r9d, eax; char *
0x18004879a  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800487a1  mov     edx, 9Fh; void *
0x1800487a6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800487ab  add     rbx, 20h ; ' '
0x1800487af  mov     rdx, [rsp+58h+var_30]
0x1800487b4  mov     rcx, qword ptr [rsp+58h+var_38]
0x1800487b9  jmp     short loc_180048779
0x1800487bb  test    rcx, rcx
0x1800487be  jz      short loc_1800487DC
0x1800487c0  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800487c5  mov     rcx, qword ptr [rsp+58h+var_38]
0x1800487ca  mov     rdx, [rsp+58h+var_28]
0x1800487cf  sub     rdx, rcx
0x1800487d2  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800487d6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800487db  nop
0x1800487dc  lea     rcx, [rsp+58h+string]; this
0x1800487e1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800487e6  nop
0x1800487e7  mov     cs:?s_inputLanguagesPopulating@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@0PEAU?$IVector@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@EA, 0; Windows::Foundation::Collections::IVector<CloudExperienceHostAPI::IOobeInputLanguage *> * CloudExperienceHostAPI::OobeKeyboardStaticsCore::s_inputLanguagesPopulating
0x1800487f2  mov     rcx, [rsi+48h]
0x1800487f6  mov     rax, [rcx]
0x1800487f9  mov     rdx, r14
0x1800487fc  mov     rax, [rax+40h]
0x180048800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048805  mov     ebx, eax
0x180048807  test    eax, eax
0x180048809  jns     short loc_180048859
0x18004880b  mov     edx, 0A4h; void *
0x180048810  mov     r9d, eax; char *
0x180048813  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004881a  mov     rcx, [rsp+58h]; this
0x18004881f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048824  nop
0x180048825  lea     rcx, [rsp+58h+arg_10]
0x18004882a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004882f  mov     eax, ebx
0x180048831  jmp     short loc_180048865
0x180048833  lea     rcx, [rsp+58h+string]; this
0x180048838  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004883d  nop
0x18004883e  mov     cs:?s_inputLanguagesPopulating@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@0PEAU?$IVector@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@EA, 0; Windows::Foundation::Collections::IVector<CloudExperienceHostAPI::IOobeInputLanguage *> * CloudExperienceHostAPI::OobeKeyboardStaticsCore::s_inputLanguagesPopulating
0x180048849  lea     rcx, [rsp+58h+arg_10]
0x18004884e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180048853  mov     eax, [rsp+60h]
0x180048857  jmp     short loc_180048865
0x180048859  lea     rcx, [rsp+58h+arg_10]
0x18004885e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180048863  xor     eax, eax
0x180048865  mov     rbx, [rsp+58h+arg_18]
0x18004886a  add     rsp, 40h
0x18004886e  pop     r15
0x180048870  pop     r14
0x180048872  pop     rsi
0x180048873  retn
```
