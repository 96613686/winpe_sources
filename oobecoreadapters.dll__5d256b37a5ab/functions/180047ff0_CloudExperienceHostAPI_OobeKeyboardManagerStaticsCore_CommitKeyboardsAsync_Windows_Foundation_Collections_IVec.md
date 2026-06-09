# CloudExperienceHostAPI::OobeKeyboardManagerStaticsCore::CommitKeyboardsAsync(Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeKeyboard *> *,Windows::Foundation::IAsyncAction * *)

- ea: `0x180047ff0`
- end: `0x18004835a`
- name: `?CommitKeyboardsAsync@OobeKeyboardManagerStaticsCore@CloudExperienceHostAPI@@UEAAJPEAU?$IVectorView@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@PEAPEAUIAsyncAction@56@@Z`
- size: `874`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180009760`
- `0x18000b098`
- `0x18000b7f8`
- `0x18000b9b8`
- `0x18000bc70`
- `0x1800459bc`
- `0x1800460d0`
- `0x1800468c4`
- `0x18004699c`
- `0x180046e48`
- `0x180047110`
- `0x180047ff0`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004818f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800481e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004818f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800481e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800481d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800481d0`

## string_xrefs

- `0x180048082`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x1800480b2`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x1800481b9`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180048223`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180048259`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x18004827c`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180048314`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180048028`: `CloudExperienceHostAPI::OobeKeyboardManagerStaticsCore::CommitKeyboardsAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CloudExperienceHostAPI::OobeKeyboardManagerStaticsCore::CommitKeyboardsAsync(
        __int64 a1,
        unsigned __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // rcx
  CloudExperienceHostCoreTelemetry *v7; // rcx
  __int64 v8; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // ebx
  int v13; // eax
  unsigned int v14; // r15d
  __int64 v15; // r14
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rax
  int v30; // r8d
  int v31; // r9d
  int v32; // [rsp+20h] [rbp-60h]
  int v33; // [rsp+20h] [rbp-60h]
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-50h] BYREF
  __int64 *v35; // [rsp+38h] [rbp-48h] BYREF
  __int64 v36; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+48h] [rbp-38h] BYREF
  __int64 v38; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v39[12]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v40; // [rsp+68h] [rbp-18h] BYREF
  _BYTE v41[16]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  __int64 v43; // [rsp+C0h] [rbp+40h] BYREF
  char v44; // [rsp+D0h] [rbp+50h] BYREF
  unsigned int v45; // [rsp+D8h] [rbp+58h] BYREF

  v43 = a1;
  if ( CloudExperienceHostCoreTelemetry::IsEnabled(a1, a2) )
  {
    wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(
      v6,
      _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_);
    CloudExperienceHostCoreTelemetry::GlobalizationState_(
      v7,
      "CloudExperienceHostAPI::OobeKeyboardManagerStaticsCore::CommitKeyboardsAsync");
  }
  *a3 = 0;
  v8 = *(_QWORD *)(a1 + 56);
  if ( v8 )
    return (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD *))(*(_QWORD *)v8 + 56LL))(v8, a2, a3);
  v45 = 0;
  v10 = (*(__int64 (__fastcall **)(unsigned __int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v45);
  v12 = v10;
  if ( v10 >= 0 )
  {
    v38 = 0;
    v13 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>>>(
            v11,
            &v38);
    v12 = v13;
    if ( v13 >= 0 )
    {
      v14 = 0;
      v15 = v38;
      while ( v14 < v45 )
      {
        v16 = *(_QWORD *)a2;
        v35 = 0;
        v17 = (*(__int64 (__fastcall **)(unsigned __int64, _QWORD, __int64 **))(v16 + 48))(a2, v14, &v35);
        v12 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15B,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
            (const char *)(unsigned int)v17,
            v32);
          goto LABEL_27;
        }
        v44 = 0;
        v34 = 0;
        v18 = *v35;
        v34 = 0;
        v19 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, char *))(v18 + 64))(v35, &v34, &v44);
        v12 = v19;
        if ( v19 < 0 )
        {
          v27 = (unsigned int)v19;
          v28 = 351;
          goto LABEL_24;
        }
        if ( !v44 )
        {
          v12 = -2147418113;
          v27 = 2147549183LL;
          v28 = 352;
LABEL_24:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v28,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
            (const char *)v27,
            v32);
          goto LABEL_25;
        }
        v36 = 0;
        v20 = (**v34)(v34, &GUID_29fc1d95_e12c_43d9_98a5_de79a87ea36b, &v36);
        v12 = v20;
        if ( v20 < 0 )
        {
          v26 = 355;
LABEL_21:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v26,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
            (const char *)(unsigned int)v20,
            v32);
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v36);
LABEL_25:
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v34);
LABEL_27:
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v35);
          goto LABEL_33;
        }
        v20 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 104LL))(v15, v36);
        v12 = v20;
        if ( v20 < 0 )
        {
          v26 = 357;
          goto LABEL_21;
        }
        string = 0;
        v21 = v36;
        v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 192LL);
        WindowsDeleteString(0);
        string = 0;
        v23 = v22(v21, &string);
        if ( v23 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x168,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
            (const char *)(unsigned int)v23,
            v32);
        *(_QWORD *)v39 = WindowsGetStringRawBuffer(string, 0);
        CloudExperienceHostCoreTelemetry::CoreEvent2<char const (&)[77],unsigned short const (&)[43],unsigned short const *>(
          v25,
          v24,
          v39);
        WindowsDeleteString(string);
        string = 0;
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v36);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v34);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v35);
        ++v14;
      }
      wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>(
        &v43,
        v43 + 64);
      v40 = v15;
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
      wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>(
        v41,
        &v43);
      *(_DWORD *)v39 = 3;
      *(_QWORD *)&v39[4] = 128;
      v29 = Windows::Internal::MakeOpLambda<0,Windows::Internal::CNoResult,_lambda_db4142dd390035ea5bdc0c00158a31ab_,>(&v40);
      v12 = Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostAPI::CommitKeyboardsAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
              (_DWORD)a3,
              (unsigned int)v39,
              v30,
              v31,
              v29);
      _lambda_db4142dd390035ea5bdc0c00158a31ab_::~_lambda_db4142dd390035ea5bdc0c00158a31ab_((_lambda_db4142dd390035ea5bdc0c00158a31ab_ *)&v40);
      if ( v12 >= 0 )
      {
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v43);
        v12 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A6,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
          (const char *)(unsigned int)v12,
          v33);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v43);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x157,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
        (const char *)(unsigned int)v13,
        v32);
    }
LABEL_33:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v38);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
      (const char *)(unsigned int)v10,
      v32);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180047ff0  mov     [rsp-38h+arg_0], rcx
0x180047ff5  push    rbp
0x180047ff6  push    rbx
0x180047ff7  push    rdi
0x180047ff8  push    r12
0x180047ffa  push    r13
0x180047ffc  push    r14
0x180047ffe  push    r15
0x180048000  mov     rbp, rsp
0x180048003  sub     rsp, 80h
0x18004800a  mov     r13, r8
0x18004800d  mov     r12, rdx
0x180048010  mov     rdi, rcx
0x180048013  call    ?IsEnabled@CloudExperienceHostCoreTelemetry@@SA_NE_K@Z; CloudExperienceHostCoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x180048018  test    al, al
0x18004801a  jz      short loc_180048034
0x18004801c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5eb5719585a1dfff1c0403c1b5c6f80a_@@CA@XZ; _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_(void)
0x180048023  call    ?get@?$static_lazy@VCloudExperienceHostCoreTelemetry@@@details@wil@@QEAAPEAVCloudExperienceHostCoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(void (*)(void))
0x180048028  lea     rdx, aCloudexperienc_9; "CloudExperienceHostAPI::OobeKeyboardMan"...
0x18004802f  call    ?GlobalizationState_@CloudExperienceHostCoreTelemetry@@QEAAXPEBD@Z; CloudExperienceHostCoreTelemetry::GlobalizationState_(char const *)
0x180048034  mov     qword ptr [r13+0], 0
0x18004803c  mov     rcx, [rdi+38h]
0x180048040  xor     edi, edi
0x180048042  test    rcx, rcx
0x180048045  jz      short loc_18004805E
0x180048047  mov     rax, [rcx]
0x18004804a  mov     r8, r13
0x18004804d  mov     rdx, r12
0x180048050  mov     rax, [rax+38h]
0x180048054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048059  jmp     loc_180048347
0x18004805e  mov     [rbp+arg_18], edi
0x180048061  mov     rax, [r12]
0x180048065  lea     rdx, [rbp+arg_18]
0x180048069  mov     rcx, r12
0x18004806c  mov     rax, [rax+38h]
0x180048070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048075  mov     ebx, eax
0x180048077  test    eax, eax
0x180048079  jns     short loc_180048098
0x18004807b  mov     rcx, [rbp+38h]; this
0x18004807f  mov     r9d, eax; char *
0x180048082  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180048089  mov     edx, 153h; void *
0x18004808e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048093  jmp     loc_180048345
0x180048098  mov     [rbp+var_30], rdi
0x18004809c  lea     rdx, [rbp+var_30]
0x1800480a0  call    ??$CreateExternalObjectVector@VCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@V?$Vector@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@U?$DefaultEqualityPredicate@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4896@U?$DefaultVectorOptions@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4896@@4Collections@Foundation@6@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@U?$DefaultEqualityPredicate@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4896@U?$DefaultVectorOptions@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4896@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>> * *)
0x1800480a5  mov     ebx, eax
0x1800480a7  test    eax, eax
0x1800480a9  jns     short loc_1800480C8
0x1800480ab  mov     rcx, [rbp+38h]; this
0x1800480af  mov     r9d, eax; char *
0x1800480b2  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800480b9  mov     edx, 157h; void *
0x1800480be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800480c3  jmp     loc_18004833C
0x1800480c8  mov     r15d, edi
0x1800480cb  mov     r14, [rbp+var_30]
0x1800480cf  cmp     r15d, [rbp+arg_18]
0x1800480d3  jnb     loc_18004829C
0x1800480d9  mov     rax, [r12]
0x1800480dd  mov     [rbp+var_48], rdi
0x1800480e1  lea     r8, [rbp+var_48]
0x1800480e5  mov     edx, r15d
0x1800480e8  mov     rcx, r12
0x1800480eb  mov     rax, [rax+30h]
0x1800480ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480f4  mov     ebx, eax
0x1800480f6  test    eax, eax
0x1800480f8  js      loc_180048275
0x1800480fe  mov     [rbp+arg_10], dil
0x180048102  mov     [rbp+var_50], rdi
0x180048106  mov     rcx, [rbp+var_48]
0x18004810a  mov     rax, [rcx]
0x18004810d  mov     [rbp+var_50], rdi
0x180048111  lea     r8, [rbp+arg_10]
0x180048115  lea     rdx, [rbp+var_50]
0x180048119  mov     rax, [rax+40h]
0x18004811d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048122  mov     ebx, eax
0x180048124  test    eax, eax
0x180048126  js      loc_180048251
0x18004812c  cmp     [rbp+arg_10], dil
0x180048130  jz      loc_180048242
0x180048136  mov     [rbp+var_40], rdi
0x18004813a  mov     rcx, [rbp+var_50]
0x18004813e  mov     rax, [rcx]
0x180048141  lea     r8, [rbp+var_40]
0x180048145  lea     rdx, _GUID_29fc1d95_e12c_43d9_98a5_de79a87ea36b
0x18004814c  mov     rax, [rax]
0x18004814f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048154  mov     ebx, eax
0x180048156  test    eax, eax
0x180048158  js      loc_18004821E
0x18004815e  mov     rax, [r14]
0x180048161  mov     rdx, [rbp+var_40]
0x180048165  mov     rcx, r14
0x180048168  mov     rax, [rax+68h]
0x18004816c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048171  mov     ebx, eax
0x180048173  test    eax, eax
0x180048175  js      loc_180048217
0x18004817b  mov     [rbp+string], rdi
0x18004817f  mov     rdi, [rbp+var_40]
0x180048183  mov     rax, [rdi]
0x180048186  mov     rbx, [rax+0C0h]
0x18004818d  xor     ecx, ecx; string
0x18004818f  call    cs:__imp_WindowsDeleteString
0x180048195  mov     [rbp+string], 0
0x18004819d  lea     rdx, [rbp+string]
0x1800481a1  mov     rcx, rdi
0x1800481a4  mov     rax, rbx
0x1800481a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481ac  mov     rcx, [rbp+38h]; this
0x1800481b0  xor     edi, edi
0x1800481b2  test    eax, eax
0x1800481b4  jns     short loc_1800481CA
0x1800481b6  mov     r9d, eax; char *
0x1800481b9  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800481c0  mov     edx, 168h; void *
0x1800481c5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800481ca  xor     edx, edx; length
0x1800481cc  mov     rcx, [rbp+string]; string
0x1800481d0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800481d6  mov     [rbp+var_28], rax
0x1800481da  lea     r8, [rbp+var_28]
0x1800481de  call    ??$CoreEvent2@AEAY0EN@$$CBDAEAY0CL@$$CBGPEBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0EN@$$CBDAEAY0CL@$$CBG$$QEAPEBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent2<char const (&)[77],ushort const (&)[43],ushort const *>(char const (&)[77],ushort const (&)[43],ushort const * &&)
0x1800481e3  nop
0x1800481e4  mov     rcx, [rbp+string]; string
0x1800481e8  call    cs:__imp_WindowsDeleteString
0x1800481ee  mov     [rbp+string], rdi
0x1800481f2  lea     rcx, [rbp+var_40]
0x1800481f6  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800481fb  nop
0x1800481fc  lea     rcx, [rbp+var_50]
0x180048200  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180048205  nop
0x180048206  lea     rcx, [rbp+var_48]
0x18004820a  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004820f  inc     r15d
0x180048212  jmp     loc_1800480CF
0x180048217  mov     edx, 165h
0x18004821c  jmp     short loc_180048223
0x18004821e  mov     edx, 163h; void *
0x180048223  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004822a  mov     r9d, eax; char *
0x18004822d  mov     rcx, [rbp+38h]; this
0x180048231  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048236  nop
0x180048237  lea     rcx, [rbp+var_40]
0x18004823b  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180048240  jmp     short loc_18004826A
0x180048242  mov     ebx, 8000FFFFh
0x180048247  mov     r9d, ebx
0x18004824a  mov     edx, 160h
0x18004824f  jmp     short loc_180048259
0x180048251  mov     r9d, eax; char *
0x180048254  mov     edx, 15Fh; void *
0x180048259  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180048260  mov     rcx, [rbp+38h]; this
0x180048264  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048269  nop
0x18004826a  lea     rcx, [rbp+var_50]
0x18004826e  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180048273  jmp     short loc_18004828E
0x180048275  mov     rcx, [rbp+38h]; this
0x180048279  mov     r9d, eax; char *
0x18004827c  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180048283  mov     edx, 15Bh; void *
0x180048288  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004828d  nop
0x18004828e  lea     rcx, [rbp+var_48]
0x180048292  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180048297  jmp     loc_18004833C
0x18004829c  mov     rdx, [rbp+arg_0]
0x1800482a0  add     rdx, 40h ; '@'
0x1800482a4  lea     rcx, [rbp+arg_0]
0x1800482a8  call    ??0?$com_ptr_t@UICoreKeyboardInputProfileManager@Core@Text@Internal@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>(wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy> const &)
0x1800482ad  nop
0x1800482ae  mov     [rbp+var_18], r14
0x1800482b2  test    r14, r14
0x1800482b5  jz      short loc_1800482C7
0x1800482b7  mov     rax, [r14]
0x1800482ba  mov     rcx, r14
0x1800482bd  mov     rax, [rax+8]
0x1800482c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482c6  nop
0x1800482c7  lea     rdx, [rbp+arg_0]
0x1800482cb  lea     rcx, [rbp+var_10]
0x1800482cf  call    ??0?$com_ptr_t@UICoreKeyboardInputProfileManager@Core@Text@Internal@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>(wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy> const &)
0x1800482d4  nop
0x1800482d5  mov     dword ptr [rbp+var_28], 3
0x1800482dc  mov     [rbp+var_28+4], 80h
0x1800482e4  lea     rcx, [rbp+var_18]
0x1800482e8  call    ??$MakeOpLambda@$0A@VCNoResult@Internal@Windows@@V_lambda_db4142dd390035ea5bdc0c00158a31ab_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@VCNoResult@Internal@Windows@@@01@$$QEAV_lambda_db4142dd390035ea5bdc0c00158a31ab_@@@Z; Windows::Internal::MakeOpLambda<0,Windows::Internal::CNoResult,_lambda_db4142dd390035ea5bdc0c00158a31ab_,>(_lambda_db4142dd390035ea5bdc0c00158a31ab_ &&)
0x1800482ed  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800482f2  lea     rdx, [rbp+var_28]
0x1800482f6  mov     rcx, r13
0x1800482f9  call    ??$MakeAsyncHelper@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@UINilDelegate@Internal@3@VCNoResult@63@VComTaskPoolHandler@63@U?$AsyncCausalityOptions@$1?CommitKeyboardsAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAUIAsyncAction@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@VCNoResult@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::CommitKeyboardsAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncAction * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CNoResult> *)
0x1800482fe  mov     ebx, eax
0x180048300  lea     rcx, [rbp+var_18]; this
0x180048304  call    ??1_lambda_db4142dd390035ea5bdc0c00158a31ab_@@QEAA@XZ; _lambda_db4142dd390035ea5bdc0c00158a31ab_::~_lambda_db4142dd390035ea5bdc0c00158a31ab_(void)
0x180048309  test    ebx, ebx
0x18004830b  jns     short loc_180048331
0x18004830d  mov     rcx, [rbp+38h]; this
0x180048311  mov     r9d, ebx; char *
0x180048314  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004831b  mov     edx, 1A6h; void *
0x180048320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048325  nop
0x180048326  lea     rcx, [rbp+arg_0]
0x18004832a  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004832f  jmp     short loc_18004833C
0x180048331  lea     rcx, [rbp+arg_0]
0x180048335  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004833a  mov     ebx, edi
0x18004833c  lea     rcx, [rbp+var_30]
0x180048340  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180048345  mov     eax, ebx
0x180048347  add     rsp, 80h
0x18004834e  pop     r15
0x180048350  pop     r14
0x180048352  pop     r13
0x180048354  pop     r12
0x180048356  pop     rdi
0x180048357  pop     rbx
0x180048358  pop     rbp
0x180048359  retn
```
