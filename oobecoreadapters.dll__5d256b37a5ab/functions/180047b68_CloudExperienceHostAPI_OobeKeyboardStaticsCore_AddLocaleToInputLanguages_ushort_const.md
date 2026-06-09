# CloudExperienceHostAPI::OobeKeyboardStaticsCore::AddLocaleToInputLanguages(ushort const *)

- ea: `0x180047b68`
- end: `0x180047d32`
- name: `?AddLocaleToInputLanguages@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@CAJPEBG@Z`
- size: `458`
- prototype: `__int64 __fastcall(LPCWSTR lpLocaleName)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180048640`

## callees

- `0x1800076b4`
- `0x1800076d4`
- `0x180009760`
- `0x180009814`
- `0x180016c24`
- `0x1800464b8`
- `0x180047b68`
- `0x180049740`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180047c16`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180047c85`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180047c16`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180047c85`

## string_xrefs

- `0x180047b91`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180047c27`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180047c61`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180047c93`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180047cd0`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CloudExperienceHostAPI::OobeKeyboardStaticsCore::AddLocaleToInputLanguages(LPCWSTR lpLocaleName)
{
  unsigned int LastError; // ebx
  bool v3; // bl
  int LocaleInfo; // eax
  const char *v6; // r9
  int v7; // esi
  LPWSTR v8; // rbx
  const char *v9; // r9
  int v10; // eax
  __int64 v11; // rdx
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+20h]
  void *v14; // [rsp+58h] [rbp+30h] BYREF
  LPWSTR lpLCData; // [rsp+60h] [rbp+38h] BYREF
  LPWSTR v16; // [rsp+68h] [rbp+40h] BYREF

  if ( CloudExperienceHostAPI::OobeKeyboardStaticsCore::s_inputLanguagesPopulating )
  {
    LODWORD(lpLCData) = 0;
    LOBYTE(v14) = 0;
    v16 = 0;
    v3 = (int)CloudExperienceHostAPI::OobeKeyboardStaticsCore::TryGetInputProfilesForLanguage(lpLocaleName, &v16, &v14) >= 0
      && (_BYTE)v14
      && (*(int (__fastcall **)(LPWSTR, LPWSTR *))(*(_QWORD *)v16 + 56LL))(v16, &lpLCData) >= 0
      && (_DWORD)lpLCData;
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v16);
    if ( !v3 )
      return 0;
    LocaleInfo = GetLocaleInfoEx(lpLocaleName, 2u, 0, 0);
    v7 = LocaleInfo;
    if ( !LocaleInfo )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xE4,
               (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
               v6);
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpLCData,
      0,
      LocaleInfo,
      v6);
    v8 = lpLCData;
    if ( lpLCData )
    {
      if ( GetLocaleInfoEx(lpLocaleName, 2u, lpLCData, v7) )
      {
        v16 = v8;
        v14 = 0;
        v10 = Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostAPI::OobeInputLanguageCore,CloudExperienceHostAPI::IOobeInputLanguage,unsigned short const * &,unsigned short *>(&v14);
        LastError = v10;
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)CloudExperienceHostAPI::OobeKeyboardStaticsCore::s_inputLanguagesPopulating
                                                           + 104LL))(
                  CloudExperienceHostAPI::OobeKeyboardStaticsCore::s_inputLanguagesPopulating,
                  v14);
          LastError = v10;
          if ( v10 >= 0 )
          {
            wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v14);
            LastError = 0;
            goto LABEL_23;
          }
          v11 = 237;
        }
        else
        {
          v11 = 236;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
          (const char *)(unsigned int)v10,
          v12);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v14);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xE8,
                      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
                      v9);
      }
    }
    else
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
        (const char *)0x8007000ELL,
        v12);
    }
LABEL_23:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpLCData);
    return LastError;
  }
  LastError = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xDC,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
    (const char *)0x8000FFFFLL,
    v12);
  return LastError;
}

```

## disassembly

```asm
0x180047b68  mov     [rsp-20h+arg_0], rcx
0x180047b6d  push    rbp
0x180047b6e  push    rbx
0x180047b6f  push    rsi
0x180047b70  push    rdi
0x180047b71  mov     rbp, rsp
0x180047b74  sub     rsp, 28h
0x180047b78  mov     rdi, rcx
0x180047b7b  cmp     cs:?s_inputLanguagesPopulating@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@0PEAU?$IVector@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@EA, 0; Windows::Foundation::Collections::IVector<CloudExperienceHostAPI::IOobeInputLanguage *> * CloudExperienceHostAPI::OobeKeyboardStaticsCore::s_inputLanguagesPopulating
0x180047b83  jnz     short loc_180047BA7
0x180047b85  mov     rcx, [rbp+20h]; this
0x180047b89  mov     ebx, 8000FFFFh
0x180047b8e  mov     r9d, ebx; char *
0x180047b91  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180047b98  mov     edx, 0DCh; void *
0x180047b9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047ba2  jmp     loc_180047D27
0x180047ba7  mov     dword ptr [rbp+lpLCData], 0
0x180047bae  mov     byte ptr [rbp+arg_8], 0
0x180047bb2  mov     [rbp+arg_18], 0
0x180047bba  lea     r8, [rbp+arg_8]
0x180047bbe  lea     rdx, [rbp+arg_18]
0x180047bc2  call    ?TryGetInputProfilesForLanguage@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@CAJPEBGPEAPEAU?$IVectorView@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@Collections@Foundation@Windows@@PEA_N@Z; CloudExperienceHostAPI::OobeKeyboardStaticsCore::TryGetInputProfilesForLanguage(ushort const *,Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *> * *,bool *)
0x180047bc7  test    eax, eax
0x180047bc9  js      short loc_180047BF3
0x180047bcb  cmp     byte ptr [rbp+arg_8], 0
0x180047bcf  jz      short loc_180047BF3
0x180047bd1  mov     rcx, [rbp+arg_18]
0x180047bd5  mov     rax, [rcx]
0x180047bd8  lea     rdx, [rbp+lpLCData]
0x180047bdc  mov     rax, [rax+38h]
0x180047be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047be5  test    eax, eax
0x180047be7  js      short loc_180047BF3
0x180047be9  cmp     dword ptr [rbp+lpLCData], 0
0x180047bed  jbe     short loc_180047BF3
0x180047bef  mov     bl, 1
0x180047bf1  jmp     short loc_180047BF5
0x180047bf3  xor     bl, bl
0x180047bf5  lea     rcx, [rbp+arg_18]
0x180047bf9  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180047bfe  test    bl, bl
0x180047c00  jnz     short loc_180047C09
0x180047c02  xor     eax, eax
0x180047c04  jmp     loc_180047D29
0x180047c09  xor     r9d, r9d; cchData
0x180047c0c  xor     r8d, r8d; lpLCData
0x180047c0f  lea     edx, [r9+2]; LCType
0x180047c13  mov     rcx, rdi; lpLocaleName
0x180047c16  call    cs:__imp_GetLocaleInfoEx
0x180047c1c  movsxd  rsi, eax
0x180047c1f  test    eax, eax
0x180047c21  jnz     short loc_180047C3D
0x180047c23  mov     rcx, [rbp+20h]; this
0x180047c27  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180047c2e  mov     edx, 0E4h; void *
0x180047c33  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180047c38  jmp     loc_180047D29
0x180047c3d  mov     r8, rsi
0x180047c40  xor     edx, edx
0x180047c42  lea     rcx, [rbp+lpLCData]
0x180047c46  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180047c4b  nop
0x180047c4c  mov     rbx, [rbp+lpLCData]
0x180047c50  test    rbx, rbx
0x180047c53  jnz     short loc_180047C77
0x180047c55  mov     rcx, [rbp+20h]; this
0x180047c59  mov     ebx, 8007000Eh
0x180047c5e  mov     r9d, ebx; char *
0x180047c61  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180047c68  mov     edx, 0E7h; void *
0x180047c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047c72  jmp     loc_180047D1E
0x180047c77  mov     r9d, esi; cchData
0x180047c7a  mov     r8, rbx; lpLCData
0x180047c7d  mov     edx, 2; LCType
0x180047c82  mov     rcx, rdi; lpLocaleName
0x180047c85  call    cs:__imp_GetLocaleInfoEx
0x180047c8b  test    eax, eax
0x180047c8d  jnz     short loc_180047CA8
0x180047c8f  mov     rcx, [rbp+20h]; this
0x180047c93  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180047c9a  mov     edx, 0E8h; void *
0x180047c9f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180047ca4  mov     ebx, eax
0x180047ca6  jmp     short loc_180047D1E
0x180047ca8  mov     [rbp+arg_18], rbx
0x180047cac  mov     [rbp+arg_8], 0
0x180047cb4  lea     r8, [rbp+arg_18]
0x180047cb8  lea     rdx, [rbp+arg_0]
0x180047cbc  lea     rcx, [rbp+arg_8]; void **
0x180047cc0  call    ??$MakeAndInitialize@VOobeInputLanguageCore@CloudExperienceHostAPI@@UIOobeInputLanguage@2@AEAPEBGPEAG@Details@WRL@Microsoft@@YAJPEAPEAUIOobeInputLanguage@CloudExperienceHostAPI@@AEAPEBG$$QEAPEAG@Z; Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostAPI::OobeInputLanguageCore,CloudExperienceHostAPI::IOobeInputLanguage,ushort const * &,ushort *>(CloudExperienceHostAPI::IOobeInputLanguage * *,ushort const * &,ushort * &&)
0x180047cc5  mov     ebx, eax
0x180047cc7  test    eax, eax
0x180047cc9  jns     short loc_180047CEF
0x180047ccb  mov     edx, 0ECh; void *
0x180047cd0  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180047cd7  mov     r9d, eax; char *
0x180047cda  mov     rcx, [rbp+20h]; this
0x180047cde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047ce3  nop
0x180047ce4  lea     rcx, [rbp+arg_8]
0x180047ce8  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180047ced  jmp     short loc_180047D1E
0x180047cef  mov     rcx, cs:?s_inputLanguagesPopulating@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@0PEAU?$IVector@PEAUIOobeInputLanguage@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@EA; Windows::Foundation::Collections::IVector<CloudExperienceHostAPI::IOobeInputLanguage *> * CloudExperienceHostAPI::OobeKeyboardStaticsCore::s_inputLanguagesPopulating
0x180047cf6  mov     rax, [rcx]
0x180047cf9  mov     rdx, [rbp+arg_8]
0x180047cfd  mov     rax, [rax+68h]
0x180047d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d06  mov     ebx, eax
0x180047d08  test    eax, eax
0x180047d0a  jns     short loc_180047D13
0x180047d0c  mov     edx, 0EDh
0x180047d11  jmp     short loc_180047CD0
0x180047d13  lea     rcx, [rbp+arg_8]
0x180047d17  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180047d1c  xor     ebx, ebx
0x180047d1e  lea     rcx, [rbp+lpLCData]
0x180047d22  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180047d27  mov     eax, ebx
0x180047d29  add     rsp, 28h
0x180047d2d  pop     rdi
0x180047d2e  pop     rsi
0x180047d2f  pop     rbx
0x180047d30  pop     rbp
0x180047d31  retn
```
