# AutoPilotUtils::AutoPilotTryGetStringPolicy(ushort const * const &)

- ea: `0x180032054`
- end: `0x180032209`
- name: `?AutoPilotTryGetStringPolicy@AutoPilotUtils@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBQEBG@Z`
- size: `437`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180032dd0`
- `0x180038a00`
- `0x18004b690`

## callees

- `0x180009760`
- `0x1800117bc`
- `0x180011db0`
- `0x180015544`
- `0x180031468`
- `0x180031508`
- `0x180032054`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003217e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003217e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800320c4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800320c4`

## string_xrefs

- `0x180032086`: `EnterpriseDeviceManagement.Service.AutoPilot.AutoPilotUtilStatics`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall AutoPilotUtils::AutoPilotTryGetStringPolicy(_QWORD *a1, __int64 *a2)
{
  _QWORD *v3; // rsi
  __int64 v4; // rcx
  int ActivationFactory; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, __int64, _QWORD **); // rdi
  _QWORD *v10; // rcx
  int v11; // eax
  _QWORD *v12; // rdi
  __int64 (__fastcall *v13)(_QWORD *, __int64); // rbx
  __int64 v14; // rax
  int v15; // eax
  const char *v16; // r9
  __int64 v18; // [rsp+28h] [rbp-30h] BYREF
  __int64 v19; // [rsp+30h] [rbp-28h] BYREF
  HSTRING string[4]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  _QWORD *v24; // [rsp+70h] [rbp+18h] BYREF
  __int64 v25; // [rsp+78h] [rbp+20h] BYREF

  try
  {
    v3 = a1;
    *a1 = 0;
    v25 = 0;
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &v19,
      L"EnterpriseDeviceManagement.Service.AutoPilot.AutoPilotUtilStatics",
      65);
    v4 = v25;
    v25 = 0;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    ActivationFactory = RoGetActivationFactory(v19, &GUID_b7e853b5_72ab_46cc_9056_2ead33d1a74d, &v25);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecoreuap\\internal\\admin\\inc\\AutopilotUtilsPublic.h",
        (const char *)(unsigned int)ActivationFactory,
        1);
    v24 = 0;
    v6 = *a2;
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(v6 + 2 * v7) );
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &v18,
      v6,
      v7);
    v8 = v25;
    v9 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v25 + 56LL);
    v10 = v24;
    v24 = 0;
    if ( v10 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v10 + 16LL))(v10, *v10);
    v11 = v9(v8, v18, &v24);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"onecoreuap\\internal\\admin\\inc\\AutopilotUtilsPublic.h",
        (const char *)(unsigned int)v11,
        1);
    wil::wait_for_completion<HSTRING__ *,wil::details::MapToSmartType<HSTRING__ *,void>::HStringWithRelease>(
      string,
      v24);
    WindowsDeleteString(string[0]);
    v12 = v24;
    v13 = *(__int64 (__fastcall **)(_QWORD *, __int64))(*v24 + 64LL);
    v14 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(v3);
    v15 = v13(v12, v14);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecoreuap\\internal\\admin\\inc\\AutopilotUtilsPublic.h",
        (const char *)(unsigned int)v15,
        3);
    Windows::Internal::String::~String((Windows::Internal::String *)&v18);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
    Windows::Internal::String::~String((Windows::Internal::String *)&v19);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v25);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\internal\\admin\\inc\\AutopilotUtilsPublic.h",
      v16);
    return a1;
  }
  return v3;
}

```

## disassembly

```asm
0x180032054  mov     rax, rsp
0x180032057  mov     [rax+10h], rbx
0x18003205b  mov     [rax+8], rcx
0x18003205f  push    rsi
0x180032060  push    rdi
0x180032061  push    r14
0x180032063  sub     rsp, 40h
0x180032067  mov     rbx, rdx
0x18003206a  mov     rsi, rcx
0x18003206d  xor     r14d, r14d
0x180032070  mov     [rax-38h], r14d
0x180032074  mov     [rcx], r14
0x180032077  mov     dword ptr [rax-38h], 1
0x18003207e  mov     [rax+20h], r14
0x180032082  lea     r8d, [r14+41h]
0x180032086  lea     rdx, ?RuntimeClass_EnterpriseDeviceManagement_Service_AutoPilot_AutoPilotUtilStatics@@3QBGB; "EnterpriseDeviceManagement.Service.Auto"...
0x18003208d  lea     rcx, [rax-28h]
0x180032091  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180032096  nop
0x180032097  mov     rcx, [rsp+58h+arg_18]
0x18003209c  mov     [rsp+58h+arg_18], r14
0x1800320a1  test    rcx, rcx
0x1800320a4  jz      short loc_1800320B3
0x1800320a6  mov     rax, [rcx]
0x1800320a9  mov     rax, [rax+10h]
0x1800320ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800320b2  nop
0x1800320b3  lea     r8, [rsp+58h+arg_18]
0x1800320b8  lea     rdx, _GUID_b7e853b5_72ab_46cc_9056_2ead33d1a74d
0x1800320bf  mov     rcx, [rsp+58h+var_28]
0x1800320c4  call    cs:__imp_RoGetActivationFactory
0x1800320ca  mov     rcx, [rsp+58h]; this
0x1800320cf  test    eax, eax
0x1800320d1  jns     short loc_1800320E7
0x1800320d3  mov     r9d, eax; char *
0x1800320d6  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\admin\\inc\\Autop"...
0x1800320dd  mov     edx, 39h ; '9'; void *
0x1800320e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800320e7  mov     [rsp+58h+arg_10], r14
0x1800320ec  mov     rdx, [rbx]
0x1800320ef  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800320f3  inc     r8
0x1800320f6  cmp     [rdx+r8*2], r14w
0x1800320fb  jnz     short loc_1800320F3
0x1800320fd  lea     rcx, [rsp+58h+var_30]
0x180032102  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180032107  nop
0x180032108  mov     rbx, [rsp+58h+arg_18]
0x18003210d  mov     rax, [rbx]
0x180032110  mov     rdi, [rax+38h]
0x180032114  mov     rcx, [rsp+58h+arg_10]
0x180032119  mov     [rsp+58h+arg_10], r14
0x18003211e  test    rcx, rcx
0x180032121  jz      short loc_180032130
0x180032123  mov     rdx, [rcx]
0x180032126  mov     rax, [rdx+10h]
0x18003212a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003212f  nop
0x180032130  lea     r8, [rsp+58h+arg_10]
0x180032135  mov     rdx, [rsp+58h+var_30]
0x18003213a  mov     rcx, rbx
0x18003213d  mov     rax, rdi
0x180032140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032145  mov     rcx, [rsp+58h]; this
0x18003214a  test    eax, eax
0x18003214c  jns     short loc_180032162
0x18003214e  mov     r9d, eax; char *
0x180032151  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\admin\\inc\\Autop"...
0x180032158  mov     edx, 3Eh ; '>'; void *
0x18003215d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032162  mov     rdx, [rsp+58h+arg_10]
0x180032167  lea     rcx, [rsp+58h+string]
0x18003216c  call    ??$wait_for_completion@PEAUHSTRING__@@VHStringWithRelease@?$MapToSmartType@PEAUHSTRING__@@X@details@wil@@@wil@@YA?AVHStringWithRelease@?$MapToSmartType@PEAUHSTRING__@@X@details@0@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<HSTRING__ *,wil::details::MapToSmartType<HSTRING__ *,void>::HStringWithRelease>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS)
0x180032171  mov     [rsp+58h+var_38], 3; int
0x180032179  mov     rcx, [rsp+58h+string]; string
0x18003217e  call    cs:__imp_WindowsDeleteString
0x180032184  mov     rdi, [rsp+58h+arg_10]
0x180032189  mov     rax, [rdi]
0x18003218c  mov     rbx, [rax+40h]
0x180032190  mov     rcx, rsi
0x180032193  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHSTRING__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(void)
0x180032198  mov     rdx, rax
0x18003219b  mov     rcx, rdi
0x18003219e  mov     rax, rbx
0x1800321a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800321a6  mov     rcx, [rsp+58h]; this
0x1800321ab  test    eax, eax
0x1800321ad  jns     short loc_1800321C4
0x1800321af  mov     r9d, eax; char *
0x1800321b2  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\admin\\inc\\Autop"...
0x1800321b9  mov     edx, 40h ; '@'; void *
0x1800321be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800321c4  lea     rcx, [rsp+58h+var_30]; this
0x1800321c9  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800321ce  nop
0x1800321cf  lea     rcx, [rsp+58h+arg_10]
0x1800321d4  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800321d9  nop
0x1800321da  lea     rcx, [rsp+58h+var_28]; this
0x1800321df  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800321e4  nop
0x1800321e5  lea     rcx, [rsp+58h+arg_18]
0x1800321ea  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800321ef  nop
0x1800321f0  jmp     short loc_1800321F7
0x1800321f2  mov     rsi, [rsp+58h+arg_0]
0x1800321f7  mov     rax, rsi
0x1800321fa  mov     rbx, [rsp+58h+arg_8]
0x1800321ff  add     rsp, 40h
0x180032203  pop     r14
0x180032205  pop     rdi
0x180032206  pop     rsi
0x180032207  retn
```
