# CloudExperienceHostAPI::OobeKeyboardStaticsCore::GetKeyboardsForLocaleByName(ushort const *,Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeKeyboard *> * *)

- ea: `0x180048a5c`
- end: `0x180048ce5`
- name: `?GetKeyboardsForLocaleByName@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@CAJPEBGPEAPEAU?$IVectorView@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@@Z`
- size: `649`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180048880`
- `0x180048960`

## callees

- `0x1800076d4`
- `0x180009760`
- `0x180045f2c`
- `0x18004657c`
- `0x18004737c`
- `0x180048a5c`
- `0x180049740`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048b81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048bfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048b81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048bfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048bb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048bb2`

## string_xrefs

- `0x180048aaf`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180048b11`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180048c25`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180048c4b`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180048c74`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CloudExperienceHostAPI::OobeKeyboardStaticsCore::GetKeyboardsForLocaleByName(__int64 a1, _QWORD *a2)
{
  int InputProfilesForLanguage; // eax
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // r14d
  __int64 v12; // rbx
  __int64 v13; // rax
  int v14; // eax
  int v15; // edi
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rdi
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v22; // [rsp+20h] [rbp-30h] BYREF
  __int64 v23; // [rsp+28h] [rbp-28h] BYREF
  __int64 *v24; // [rsp+30h] [rbp-20h] BYREF
  __int64 v25; // [rsp+38h] [rbp-18h] BYREF
  PCWSTR v26[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  HSTRING string; // [rsp+98h] [rbp+48h] BYREF
  unsigned int v29; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v30; // [rsp+A8h] [rbp+58h] BYREF

  *a2 = 0;
  LOBYTE(string) = 0;
  v24 = 0;
  InputProfilesForLanguage = CloudExperienceHostAPI::OobeKeyboardStaticsCore::TryGetInputProfilesForLanguage(
                               a1,
                               &v24,
                               &string);
  v4 = InputProfilesForLanguage;
  if ( InputProfilesForLanguage < 0 )
  {
    v5 = (unsigned int)InputProfilesForLanguage;
    v6 = 191;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
      (const char *)v5,
      v22);
    goto LABEL_31;
  }
  if ( !(_BYTE)string )
  {
    v6 = 193;
LABEL_5:
    v4 = -2147418113;
    v5 = 2147549183LL;
    goto LABEL_6;
  }
  v29 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v24 + 56))(v24, &v29);
  v4 = v7;
  if ( v7 < 0 )
  {
    v5 = (unsigned int)v7;
    v6 = 196;
    goto LABEL_6;
  }
  if ( !v29 )
  {
    v6 = 197;
    goto LABEL_5;
  }
  v22 = 0;
  v9 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<CloudExperienceHostAPI::IOobeKeyboard,Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeKeyboard *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeKeyboard *>>>(
         v8,
         &v22);
  v4 = v9;
  if ( v9 >= 0 )
  {
    v11 = 0;
    v12 = v22;
    while ( v11 < v29 )
    {
      v30 = 0;
      v13 = *v24;
      v30 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v13 + 48))(v24, v11, &v30);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCD,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
          (const char *)(unsigned int)v14,
          v22);
        goto LABEL_27;
      }
      string = 0;
      v16 = v30;
      v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 128LL);
      WindowsDeleteString(0);
      string = 0;
      v18 = v17(v16, &string);
      v15 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD0,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
          (const char *)(unsigned int)v18,
          v22);
        goto LABEL_25;
      }
      v25 = v30;
      v26[0] = WindowsGetStringRawBuffer(string, 0);
      v23 = 0;
      v15 = Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostAPI::OobeKeyboardCore,CloudExperienceHostAPI::OobeKeyboardCore,unsigned short const (&)[1],unsigned short const *,Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfile *>(
              &v23,
              v19,
              v26,
              &v25);
      if ( v15 < 0 )
      {
        v20 = 211;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
          (const char *)(unsigned int)v15,
          v22);
        wil::com_ptr_t<CloudExperienceHostAPI::OobeKeyboardCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeKeyboardCore,wil::err_exception_policy>(&v23);
LABEL_25:
        WindowsDeleteString(string);
        string = 0;
LABEL_27:
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v30);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v22);
        v4 = v15;
        goto LABEL_31;
      }
      v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 104LL))(v12, v23);
      if ( v15 < 0 )
      {
        v20 = 212;
        goto LABEL_23;
      }
      wil::com_ptr_t<CloudExperienceHostAPI::OobeKeyboardCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeKeyboardCore,wil::err_exception_policy>(&v23);
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v30);
      ++v11;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v12 + 64LL))(v12, a2);
    v4 = v9;
    if ( v9 >= 0 )
    {
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v22);
      v4 = 0;
      goto LABEL_31;
    }
    v10 = 214;
  }
  else
  {
    v10 = 200;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
    (const char *)(unsigned int)v9,
    v22);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v22);
LABEL_31:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
  return v4;
}

```

## disassembly

```asm
0x180048a5c  push    rbp
0x180048a5e  push    rbx
0x180048a5f  push    rsi
0x180048a60  push    rdi
0x180048a61  push    r12
0x180048a63  push    r14
0x180048a65  push    r15
0x180048a67  mov     rbp, rsp
0x180048a6a  sub     rsp, 50h
0x180048a6e  mov     r15, rdx
0x180048a71  xor     r12d, r12d
0x180048a74  mov     [rdx], r12
0x180048a77  mov     byte ptr [rbp+string], r12b
0x180048a7b  mov     [rbp+var_20], r12
0x180048a7f  lea     r8, [rbp+string]
0x180048a83  lea     rdx, [rbp+var_20]
0x180048a87  call    ?TryGetInputProfilesForLanguage@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@CAJPEBGPEAPEAU?$IVectorView@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@Collections@Foundation@Windows@@PEA_N@Z; CloudExperienceHostAPI::OobeKeyboardStaticsCore::TryGetInputProfilesForLanguage(ushort const *,Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *> * *,bool *)
0x180048a8c  mov     ebx, eax
0x180048a8e  test    eax, eax
0x180048a90  jns     short loc_180048A9C
0x180048a92  mov     r9d, eax
0x180048a95  mov     edx, 0BFh
0x180048a9a  jmp     short loc_180048AAF
0x180048a9c  cmp     byte ptr [rbp+string], r12b
0x180048aa0  jnz     short loc_180048AC4
0x180048aa2  mov     edx, 0C1h; void *
0x180048aa7  mov     ebx, 8000FFFFh
0x180048aac  mov     r9d, ebx; char *
0x180048aaf  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180048ab6  mov     rcx, [rbp+38h]; this
0x180048aba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048abf  jmp     loc_180048CCB
0x180048ac4  mov     [rbp+arg_10], r12d
0x180048ac8  mov     rcx, [rbp+var_20]
0x180048acc  mov     rax, [rcx]
0x180048acf  lea     rdx, [rbp+arg_10]
0x180048ad3  mov     rax, [rax+38h]
0x180048ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048adc  mov     ebx, eax
0x180048ade  test    eax, eax
0x180048ae0  jns     short loc_180048AEC
0x180048ae2  mov     r9d, eax
0x180048ae5  mov     edx, 0C4h
0x180048aea  jmp     short loc_180048AAF
0x180048aec  cmp     [rbp+arg_10], r12d
0x180048af0  jnz     short loc_180048AF9
0x180048af2  mov     edx, 0C5h
0x180048af7  jmp     short loc_180048AA7
0x180048af9  mov     [rbp+var_30], r12
0x180048afd  lea     rdx, [rbp+var_30]
0x180048b01  call    ??$CreateExternalObjectVector@UIOobeKeyboard@CloudExperienceHostAPI@@V?$Vector@PEAUIOobeKeyboard@CloudExperienceHostAPI@@U?$DefaultEqualityPredicate@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@4567@U?$DefaultVectorOptions@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@4567@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIOobeKeyboard@CloudExperienceHostAPI@@U?$DefaultEqualityPredicate@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@4567@U?$DefaultVectorOptions@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@4567@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<CloudExperienceHostAPI::IOobeKeyboard,Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeKeyboard *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeKeyboard *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeKeyboard *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeKeyboard *>> * *)
0x180048b06  mov     ebx, eax
0x180048b08  test    eax, eax
0x180048b0a  jns     short loc_180048B33
0x180048b0c  mov     edx, 0C8h; void *
0x180048b11  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180048b18  mov     r9d, eax; char *
0x180048b1b  mov     rcx, [rbp+38h]; this
0x180048b1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048b24  nop
0x180048b25  lea     rcx, [rbp+var_30]
0x180048b29  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180048b2e  jmp     loc_180048CCB
0x180048b33  mov     r14d, r12d
0x180048b36  mov     rbx, [rbp+var_30]
0x180048b3a  cmp     r14d, [rbp+arg_10]
0x180048b3e  jnb     loc_180048C9D
0x180048b44  mov     [rbp+arg_18], r12
0x180048b48  mov     rcx, [rbp+var_20]
0x180048b4c  mov     rax, [rcx]
0x180048b4f  mov     [rbp+arg_18], r12
0x180048b53  lea     r8, [rbp+arg_18]
0x180048b57  mov     edx, r14d
0x180048b5a  mov     rax, [rax+30h]
0x180048b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b63  mov     edi, eax
0x180048b65  test    eax, eax
0x180048b67  js      loc_180048C6D
0x180048b6d  mov     [rbp+string], r12
0x180048b71  mov     rsi, [rbp+arg_18]
0x180048b75  mov     rax, [rsi]
0x180048b78  mov     rdi, [rax+80h]
0x180048b7f  xor     ecx, ecx; string
0x180048b81  call    cs:__imp_WindowsDeleteString
0x180048b87  mov     [rbp+string], r12
0x180048b8b  lea     rdx, [rbp+string]
0x180048b8f  mov     rcx, rsi
0x180048b92  mov     rax, rdi
0x180048b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b9a  mov     edi, eax
0x180048b9c  test    eax, eax
0x180048b9e  js      loc_180048C44
0x180048ba4  mov     rax, [rbp+arg_18]
0x180048ba8  mov     [rbp+var_18], rax
0x180048bac  xor     edx, edx; length
0x180048bae  mov     rcx, [rbp+string]; string
0x180048bb2  call    cs:__imp_WindowsGetStringRawBuffer
0x180048bb8  mov     [rbp+var_10], rax
0x180048bbc  mov     [rbp+var_28], r12
0x180048bc0  lea     r9, [rbp+var_18]
0x180048bc4  lea     r8, [rbp+var_10]
0x180048bc8  lea     rcx, [rbp+var_28]
0x180048bcc  call    ??$MakeAndInitialize@VOobeKeyboardCore@CloudExperienceHostAPI@@V12@AEAY00$$CBGPEBGPEAUICoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@Details@WRL@Microsoft@@YAJPEAPEAVOobeKeyboardCore@CloudExperienceHostAPI@@AEAY00$$CBG$$QEAPEBG$$QEAPEAUICoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostAPI::OobeKeyboardCore,CloudExperienceHostAPI::OobeKeyboardCore,ushort const (&)[1],ushort const *,Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfile *>(CloudExperienceHostAPI::OobeKeyboardCore * *,ushort const (&)[1],ushort const * &&,Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfile * &&)
0x180048bd1  mov     edi, eax
0x180048bd3  test    eax, eax
0x180048bd5  js      short loc_180048C20
0x180048bd7  mov     rax, [rbx]
0x180048bda  mov     rdx, [rbp+var_28]
0x180048bde  mov     rcx, rbx
0x180048be1  mov     rax, [rax+68h]
0x180048be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bea  mov     edi, eax
0x180048bec  test    eax, eax
0x180048bee  js      short loc_180048C19
0x180048bf0  lea     rcx, [rbp+var_28]
0x180048bf4  call    ??1?$com_ptr_t@VOobeKeyboardCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::OobeKeyboardCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeKeyboardCore,wil::err_exception_policy>(void)
0x180048bf9  nop
0x180048bfa  mov     rcx, [rbp+string]; string
0x180048bfe  call    cs:__imp_WindowsDeleteString
0x180048c04  mov     [rbp+string], r12
0x180048c08  lea     rcx, [rbp+arg_18]
0x180048c0c  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180048c11  inc     r14d
0x180048c14  jmp     loc_180048B3A
0x180048c19  mov     edx, 0D4h
0x180048c1e  jmp     short loc_180048C25
0x180048c20  mov     edx, 0D3h; void *
0x180048c25  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180048c2c  mov     r9d, edi; char *
0x180048c2f  mov     rcx, [rbp+38h]; this
0x180048c33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048c38  nop
0x180048c39  lea     rcx, [rbp+var_28]
0x180048c3d  call    ??1?$com_ptr_t@VOobeKeyboardCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::OobeKeyboardCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeKeyboardCore,wil::err_exception_policy>(void)
0x180048c42  jmp     short loc_180048C5D
0x180048c44  mov     rcx, [rbp+38h]; this
0x180048c48  mov     r9d, edi; char *
0x180048c4b  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180048c52  mov     edx, 0D0h; void *
0x180048c57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048c5c  nop
0x180048c5d  mov     rcx, [rbp+string]; string
0x180048c61  call    cs:__imp_WindowsDeleteString
0x180048c67  mov     [rbp+string], r12
0x180048c6b  jmp     short loc_180048C86
0x180048c6d  mov     rcx, [rbp+38h]; this
0x180048c71  mov     r9d, edi; char *
0x180048c74  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180048c7b  mov     edx, 0CDh; void *
0x180048c80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048c85  nop
0x180048c86  lea     rcx, [rbp+arg_18]
0x180048c8a  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180048c8f  nop
0x180048c90  lea     rcx, [rbp+var_30]
0x180048c94  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180048c99  mov     ebx, edi
0x180048c9b  jmp     short loc_180048CCB
0x180048c9d  mov     rax, [rbx]
0x180048ca0  mov     rdx, r15
0x180048ca3  mov     rcx, rbx
0x180048ca6  mov     rax, [rax+40h]
0x180048caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048caf  mov     ebx, eax
0x180048cb1  test    eax, eax
0x180048cb3  jns     short loc_180048CBF
0x180048cb5  mov     edx, 0D6h
0x180048cba  jmp     loc_180048B11
0x180048cbf  lea     rcx, [rbp+var_30]
0x180048cc3  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180048cc8  mov     ebx, r12d
0x180048ccb  lea     rcx, [rbp+var_20]
0x180048ccf  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180048cd4  mov     eax, ebx
0x180048cd6  add     rsp, 50h
0x180048cda  pop     r15
0x180048cdc  pop     r14
0x180048cde  pop     r12
0x180048ce0  pop     rdi
0x180048ce1  pop     rsi
0x180048ce2  pop     rbx
0x180048ce3  pop     rbp
0x180048ce4  retn
```
