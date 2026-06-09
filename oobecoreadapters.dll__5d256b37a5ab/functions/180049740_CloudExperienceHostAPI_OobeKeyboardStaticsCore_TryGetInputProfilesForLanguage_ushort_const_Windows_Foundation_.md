# CloudExperienceHostAPI::OobeKeyboardStaticsCore::TryGetInputProfilesForLanguage(ushort const *,Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *> * *,bool *)

- ea: `0x180049740`
- end: `0x180049959`
- name: `?TryGetInputProfilesForLanguage@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@CAJPEBGPEAPEAU?$IVectorView@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@Collections@Foundation@Windows@@PEA_N@Z`
- size: `537`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180047b68`
- `0x180048a5c`

## callees

- `0x180002b60`
- `0x1800076d4`
- `0x180009100`
- `0x180009760`
- `0x18000a4f8`
- `0x180049740`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800497bc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180049877`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800497bc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180049877`

## string_xrefs

- `0x1800497cf`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180049826`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x18004988a`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x1800498d0`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CloudExperienceHostAPI::OobeKeyboardStaticsCore::TryGetInputProfilesForLanguage(
        __int64 a1,
        _QWORD *a2,
        _BYTE *a3)
{
  __int64 result; // rax
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // rbx
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // [rsp+20h] [rbp-50h] BYREF
  __int64 v16; // [rsp+28h] [rbp-48h] BYREF
  __int64 *v17; // [rsp+30h] [rbp-40h] BYREF
  __int64 v18; // [rsp+38h] [rbp-38h] BYREF
  __int64 v19; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v21; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v19 = a1;
  *a2 = 0;
  *a3 = 0;
  result = -1;
  do
    ++result;
  while ( *(_WORD *)(a1 + 2 * result) );
  if ( result )
  {
    v18 = 0;
    v21 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Globalization.Language",
      0x1Fu,
      0x1Eu);
    ActivationFactory = RoGetActivationFactory(v21, &GUID_9b0252ac_0c27_44f8_b792_9793fb66c63e, &v18);
    v7 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v15 = 0;
      v8 = v18;
      v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 48LL);
      v15 = 0;
      v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v19);
      v11 = v9(v8, *(_QWORD *)(v10 + 24), &v15);
      v7 = v11;
      if ( v11 >= 0 )
      {
        v17 = 0;
        v21 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.UI.Internal.Text.Core.CoreKeyboardInputProfileManager",
          0x3Eu,
          0x3Du);
        v12 = RoGetActivationFactory(v21, &GUID_d0380bbe_201e_4a70_8eff_bb52f7996cae, &v17);
        v7 = v12;
        if ( v12 >= 0 )
        {
          v16 = 0;
          v13 = *v17;
          v16 = 0;
          v14 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v13 + 48))(v17, &v16);
          v7 = v14;
          if ( v14 >= 0 )
          {
            if ( (*(int (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v16 + 136LL))(v16, v15, a2) >= 0 )
              *a3 = 1;
            wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v16);
            wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v17);
            wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v15);
            v7 = 0;
            goto LABEL_17;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x10D,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
            (const char *)(unsigned int)v14,
            v15);
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v16);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x10A,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
            (const char *)(unsigned int)v12,
            v15);
        }
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v17);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x107,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
          (const char *)(unsigned int)v11,
          v15);
      }
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v15);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v15);
    }
LABEL_17:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v18);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180049740  mov     [rsp-28h+arg_18], rbx
0x180049745  push    rbp
0x180049746  push    rsi
0x180049747  push    rdi
0x180049748  push    r14
0x18004974a  push    r15
0x18004974c  mov     rbp, rsp
0x18004974f  sub     rsp, 70h
0x180049753  mov     rax, cs:__security_cookie
0x18004975a  xor     rax, rsp
0x18004975d  mov     [rbp+var_8], rax
0x180049761  mov     rsi, r8
0x180049764  mov     r14, rdx
0x180049767  mov     [rbp+var_30], rcx
0x18004976b  xor     r15d, r15d
0x18004976e  mov     [rdx], r15
0x180049771  mov     [r8], r15b
0x180049774  or      rax, 0FFFFFFFFFFFFFFFFh
0x180049778  inc     rax
0x18004977b  cmp     [rcx+rax*2], r15w
0x180049780  jnz     short loc_180049778
0x180049782  test    rax, rax
0x180049785  jz      loc_180049939
0x18004978b  mov     [rbp+var_38], r15
0x18004978f  mov     [rbp+var_10], r15
0x180049793  mov     r9d, 1Eh; unsigned int
0x180049799  lea     r8d, [r9+1]; unsigned int
0x18004979d  lea     rdx, ?RuntimeClass_Windows_Globalization_Language@@3QBGB; "Windows.Globalization.Language"
0x1800497a4  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800497a8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800497ad  lea     r8, [rbp+var_38]
0x1800497b1  lea     rdx, _GUID_9b0252ac_0c27_44f8_b792_9793fb66c63e
0x1800497b8  mov     rcx, [rbp+var_10]
0x1800497bc  call    cs:__imp_RoGetActivationFactory
0x1800497c2  mov     ebx, eax
0x1800497c4  test    eax, eax
0x1800497c6  jns     short loc_1800497E5
0x1800497c8  mov     rcx, [rbp+28h]; this
0x1800497cc  mov     r9d, eax; char *
0x1800497cf  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800497d6  mov     edx, 104h; void *
0x1800497db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800497e0  jmp     loc_18004992E
0x1800497e5  mov     [rbp+var_50], r15
0x1800497e9  mov     rdi, [rbp+var_38]
0x1800497ed  mov     rax, [rdi]
0x1800497f0  mov     rbx, [rax+30h]
0x1800497f4  mov     [rbp+var_50], r15
0x1800497f8  lea     rdx, [rbp+var_30]
0x1800497fc  lea     rcx, [rbp+hstringHeader]
0x180049800  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180049805  nop
0x180049806  lea     r8, [rbp+var_50]
0x18004980a  mov     rdx, [rax+18h]
0x18004980e  mov     rcx, rdi
0x180049811  mov     rax, rbx
0x180049814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049819  mov     ebx, eax
0x18004981b  test    eax, eax
0x18004981d  jns     short loc_180049846
0x18004981f  mov     rcx, [rbp+28h]; this
0x180049823  mov     r9d, eax; char *
0x180049826  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004982d  mov     edx, 107h; void *
0x180049832  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049837  nop
0x180049838  lea     rcx, [rbp+var_50]
0x18004983c  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180049841  jmp     loc_18004992E
0x180049846  mov     [rbp+var_40], r15
0x18004984a  mov     [rbp+var_10], r15
0x18004984e  mov     r9d, 3Dh ; '='; unsigned int
0x180049854  lea     r8d, [r9+1]; unsigned int
0x180049858  lea     rdx, ?RuntimeClass_Windows_UI_Internal_Text_Core_CoreKeyboardInputProfileManager@@3QBGB; "Windows.UI.Internal.Text.Core.CoreKeybo"...
0x18004985f  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180049863  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180049868  lea     r8, [rbp+var_40]
0x18004986c  lea     rdx, _GUID_d0380bbe_201e_4a70_8eff_bb52f7996cae
0x180049873  mov     rcx, [rbp+var_10]
0x180049877  call    cs:__imp_RoGetActivationFactory
0x18004987d  mov     ebx, eax
0x18004987f  test    eax, eax
0x180049881  jns     short loc_1800498A7
0x180049883  mov     rcx, [rbp+28h]; this
0x180049887  mov     r9d, eax; char *
0x18004988a  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180049891  mov     edx, 10Ah; void *
0x180049896  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004989b  nop
0x18004989c  lea     rcx, [rbp+var_40]
0x1800498a0  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800498a5  jmp     short loc_180049838
0x1800498a7  mov     [rbp+var_48], r15
0x1800498ab  mov     rcx, [rbp+var_40]
0x1800498af  mov     rax, [rcx]
0x1800498b2  mov     [rbp+var_48], r15
0x1800498b6  lea     rdx, [rbp+var_48]
0x1800498ba  mov     rax, [rax+30h]
0x1800498be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498c3  mov     ebx, eax
0x1800498c5  test    eax, eax
0x1800498c7  jns     short loc_1800498ED
0x1800498c9  mov     rcx, [rbp+28h]; this
0x1800498cd  mov     r9d, eax; char *
0x1800498d0  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800498d7  mov     edx, 10Dh; void *
0x1800498dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800498e1  nop
0x1800498e2  lea     rcx, [rbp+var_48]
0x1800498e6  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800498eb  jmp     short loc_18004989C
0x1800498ed  mov     rcx, [rbp+var_48]
0x1800498f1  mov     rax, [rcx]
0x1800498f4  mov     r8, r14
0x1800498f7  mov     rdx, [rbp+var_50]
0x1800498fb  mov     rax, [rax+88h]
0x180049902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049907  test    eax, eax
0x180049909  js      short loc_18004990E
0x18004990b  mov     byte ptr [rsi], 1
0x18004990e  lea     rcx, [rbp+var_48]
0x180049912  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180049917  nop
0x180049918  lea     rcx, [rbp+var_40]
0x18004991c  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180049921  nop
0x180049922  lea     rcx, [rbp+var_50]
0x180049926  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004992b  mov     ebx, r15d
0x18004992e  lea     rcx, [rbp+var_38]
0x180049932  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180049937  mov     eax, ebx
0x180049939  mov     rcx, [rbp+var_8]
0x18004993d  xor     rcx, rsp; StackCookie
0x180049940  call    __security_check_cookie
0x180049945  mov     rbx, [rsp+70h+arg_18]
0x18004994d  add     rsp, 70h
0x180049951  pop     r15
0x180049953  pop     r14
0x180049955  pop     rdi
0x180049956  pop     rsi
0x180049957  pop     rbp
0x180049958  retn
```
