# CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForLocaleByName(ushort const *,ushort const *,Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeKeyboard *> * *)

- ea: `0x180091d1c`
- end: `0x180092258`
- name: `?GetKeyboardsForLocaleByName@OobeKeyboardStatics@CloudExperienceHostAPI@@CAJPEBG0PEAPEAU?$IVectorView@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@@Z`
- size: `1340`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `25`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180091910`
- `0x180091c40`

## callees

- `0x180003470`
- `0x180008544`
- `0x18001ad08`
- `0x1800230b0`
- `0x18003e430`
- `0x18003e4d4`
- `0x180048340`
- `0x180048384`
- `0x180048d38`
- `0x180048d88`
- `0x180048e18`
- `0x1800491b4`
- `0x18004941c`
- `0x18004a1b4`
- `0x18004a7d4`
- `0x18004b8b0`
- `0x18004b8f4`
- `0x18004b940`
- `0x1800628a8`
- `0x18008f040`
- `0x18008f3b8`
- `0x18008ff08`
- `0x18009124c`
- `0x180091d1c`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x180091f04`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x180091f04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091d53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091e02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091e36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091f57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091ff2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180092028`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180092038`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009207a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009211b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009217c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800921f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180092215`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009222f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091d53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091e02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091e36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091f57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091ff2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180092028`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180092038`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009207a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009211b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009217c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800921f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180092215`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009222f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091dc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091e79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800920ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091dc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091e79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800920ba`

## string_xrefs

- `0x180091d9e`: `shell\oobe\machine\plugins\adapters\winrt\oobekeyboard.cpp`
- `0x180091e5f`: `shell\oobe\machine\plugins\adapters\winrt\oobekeyboard.cpp`
- `0x180091f9a`: `shell\oobe\machine\plugins\adapters\winrt\oobekeyboard.cpp`
- `0x180092136`: `shell\oobe\machine\plugins\adapters\winrt\oobekeyboard.cpp`
- `0x180092165`: `shell\oobe\machine\plugins\adapters\winrt\oobekeyboard.cpp`
- `0x1800921c0`: `shell\oobe\machine\plugins\adapters\winrt\oobekeyboard.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForLocaleByName(
        unsigned __int16 *a1,
        _WORD *a2,
        _QWORD *a3)
{
  const unsigned __int16 (*v6)[1]; // rdx
  HSTRING v7; // rbx
  int CompatibleInputMethodsForLanguage; // eax
  unsigned int v9; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // rax
  int InputMethodDescription; // eax
  PCWSTR v13; // rdx
  unsigned __int16 *v14; // rbx
  unsigned __int16 *v15; // rsi
  unsigned __int16 *i; // rdi
  __int64 v17; // rax
  const unsigned __int16 *v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  char v22; // r8
  int v23; // eax
  const char *v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rbx
  HSTRING v27; // rdi
  const unsigned __int16 *v28; // rax
  int v29; // eax
  int v30; // esi
  __int64 v31; // rdx
  HSTRING v33; // [rsp+20h] [rbp-D8h] BYREF
  HSTRING v34; // [rsp+28h] [rbp-D0h] BYREF
  HSTRING v35; // [rsp+30h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C0h] BYREF
  _QWORD v37[3]; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+58h] [rbp-A0h] BYREF
  PCWSTR v39; // [rsp+60h] [rbp-98h] BYREF
  HSTRING v40[4]; // [rsp+68h] [rbp-90h] BYREF
  HSTRING v41[4]; // [rsp+88h] [rbp-70h] BYREF
  _BYTE v42[16]; // [rsp+A8h] [rbp-50h] BYREF
  __int64 v43; // [rsp+B8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  *a3 = 0;
  WindowsDeleteString(0);
  string = 0;
  v7 = *Windows::Internal::StringReference::StringReference(v41, v6);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v40, a1);
  CompatibleInputMethodsForLanguage = GetCompatibleInputMethodsForLanguage(v40[0], v7, &string);
  v9 = CompatibleInputMethodsForLanguage;
  if ( CompatibleInputMethodsForLanguage < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xED,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
      (const char *)(unsigned int)CompatibleInputMethodsForLanguage,
      (int)v33);
LABEL_34:
    WindowsDeleteString(string);
    return v9;
  }
  std::vector<std::unique_ptr<ProvPackageInfo>>::vector<std::unique_ptr<ProvPackageInfo>>(v37);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  try
  {
    v11 = VectorFromDelimitedString(v42, StringRawBuffer);
    std::vector<std::wstring>::operator=(v37, v11);
    std::vector<std::wstring>::_Tidy(v42);
    v34 = 0;
    WindowsDeleteString(0);
    v33 = 0;
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v40, a1);
    if ( (int)GetDefaultInputMethodForLanguage(v40[0], &v33) >= 0 )
    {
      WindowsDeleteString(v34);
      v34 = 0;
      InputMethodDescription = GetInputMethodDescription(v33, &v34);
      if ( InputMethodDescription >= 0 )
      {
        v13 = WindowsGetStringRawBuffer(v33, 0);
        std::wstring::wstring(v41, v13);
        std::vector<std::wstring>::emplace<std::wstring>(v37, &v38, v37[0], v41);
        std::wstring::_Tidy_deallocate(v41);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF9,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
          (const char *)(unsigned int)InputMethodDescription,
          (int)v33);
      }
    }
    if ( a2 && *a2 )
    {
      std::wstring::wstring(v41, a2);
      v14 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
      v15 = &v14[(__int64)v41[2]];
      for ( i = v14; v14 != v15; ++v14 )
        *i++ = toupper(*v14);
      v17 = std::wstring::wstring(v40, v41);
      CloudExperienceHostAPI::OobeKeyboardStatics::GetCompatibleIdForPromotion(v42, v37, v17);
      v35 = 0;
      if ( v43 )
      {
        WindowsDeleteString(0);
        v35 = 0;
        v18 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42);
        Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v40, v18);
        v19 = GetInputMethodDescription(v40[0], &v35);
        if ( v19 >= 0 )
        {
          v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42);
          std::wstring::wstring(v40, v20);
          std::vector<std::wstring>::emplace<std::wstring>(v37, &v38, v37[0], v40);
          std::wstring::_Tidy_deallocate(v40);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x10E,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
            (const char *)(unsigned int)v19,
            (int)v33);
        }
      }
      WindowsDeleteString(v35);
      v35 = 0;
      std::wstring::_Tidy_deallocate(v42);
      std::wstring::_Tidy_deallocate(v41);
    }
    RemoveDuplicates<std::vector<std::wstring>>(v37);
    WindowsDeleteString(v34);
    v34 = 0;
    WindowsDeleteString(v33);
    v34 = 0;
    v23 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<CloudExperienceHostAPI::IOobeKeyboard,Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeKeyboard *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeKeyboard *>>>(
            v21,
            &v34,
            v22);
  }
  catch ( ... )
  {
    LODWORD(v33) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x115,
                     (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
                     v24);
    std::vector<std::wstring>::_Tidy(v37);
    WindowsDeleteString(string);
    return (unsigned int)v33;
  }
  v9 = v23;
  if ( v23 >= 0 )
  {
    v26 = v37[0];
    v27 = v34;
    while ( v26 != v37[1] )
    {
      v33 = 0;
      WindowsDeleteString(0);
      v33 = 0;
      v28 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v40, v28);
      v29 = GetInputMethodDescription(v40[0], &v33);
      v30 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11D,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
          (const char *)(unsigned int)v29,
          (int)v33);
        goto LABEL_30;
      }
      v39 = WindowsGetStringRawBuffer(v33, 0);
      v38 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
      v35 = 0;
      v30 = Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostAPI::OobeKeyboard,CloudExperienceHostAPI::OobeKeyboard,unsigned short const *,unsigned short const *>(
              &v35,
              &v38,
              &v39);
      if ( v30 < 0 )
      {
        v31 = 288;
LABEL_28:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
          (const char *)(unsigned int)v30,
          (int)v33);
        wil::com_ptr_t<CloudExperienceHostAPI::OobeKeyboard,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeKeyboard,wil::err_exception_policy>(&v35);
LABEL_30:
        WindowsDeleteString(v33);
        v33 = 0;
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v34);
        std::vector<std::wstring>::_Tidy(v37);
        v9 = v30;
        goto LABEL_34;
      }
      v30 = (*(__int64 (__fastcall **)(HSTRING, HSTRING))(*(_QWORD *)v27 + 104LL))(v27, v35);
      if ( v30 < 0 )
      {
        v31 = 289;
        goto LABEL_28;
      }
      wil::com_ptr_t<CloudExperienceHostAPI::OobeKeyboard,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeKeyboard,wil::err_exception_policy>(&v35);
      WindowsDeleteString(v33);
      v26 += 32;
    }
    v23 = (*(__int64 (__fastcall **)(HSTRING, _QWORD *))(*(_QWORD *)v27 + 64LL))(v27, a3);
    v9 = v23;
    if ( v23 >= 0 )
    {
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v34);
      std::vector<std::wstring>::_Tidy(v37);
      WindowsDeleteString(string);
      return 0;
    }
    v25 = 292;
  }
  else
  {
    v25 = 280;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v25,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
    (const char *)(unsigned int)v23,
    (int)v33);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v34);
  std::vector<std::wstring>::_Tidy(v37);
  goto LABEL_34;
}

```

## disassembly

```asm
0x180091d1c  push    rbx
0x180091d1e  push    rsi
0x180091d1f  push    rdi
0x180091d20  push    r14
0x180091d22  push    r15
0x180091d24  sub     rsp, 0D0h
0x180091d2b  mov     rax, cs:__security_cookie
0x180091d32  xor     rax, rsp
0x180091d35  mov     [rsp+0F8h+var_30], rax
0x180091d3d  mov     r14, r8
0x180091d40  mov     rdi, rdx
0x180091d43  mov     rsi, rcx
0x180091d46  xor     r15d, r15d
0x180091d49  mov     [r8], r15
0x180091d4c  mov     [rsp+0F8h+string], r15
0x180091d51  xor     ecx, ecx; string
0x180091d53  call    cs:__imp_WindowsDeleteString
0x180091d59  mov     [rsp+0F8h+string], r15
0x180091d5e  lea     rcx, [rsp+0F8h+var_70]; string
0x180091d66  call    ??$?0$00@StringReference@Internal@Windows@@QEAA@AEAY00$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[1])
0x180091d6b  mov     rbx, [rax]
0x180091d6e  mov     rdx, rsi; unsigned __int16 *
0x180091d71  lea     rcx, [rsp+0F8h+var_90]; this
0x180091d76  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180091d7b  lea     r8, [rsp+0F8h+string]
0x180091d80  mov     rdx, rbx
0x180091d83  mov     rcx, [rsp+0F8h+var_90]
0x180091d88  call    GetCompatibleInputMethodsForLanguage
0x180091d8d  mov     ebx, eax
0x180091d8f  test    eax, eax
0x180091d91  jns     short loc_180091DB4
0x180091d93  mov     rcx, [rsp+0F8h]; this
0x180091d9b  mov     r9d, eax; char *
0x180091d9e  lea     r8, aShellOobeMachi_22; "shell\\oobe\\machine\\plugins\\adapters"...
0x180091da5  mov     edx, 0EDh; void *
0x180091daa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091daf  jmp     loc_1800921EB
0x180091db4  lea     rcx, [rsp+0F8h+var_B8]
0x180091db9  call    ??0?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ProvPackageInfo>>::vector<std::unique_ptr<ProvPackageInfo>>(void)
0x180091dbe  nop
0x180091dbf  xor     edx, edx; length
0x180091dc1  mov     rcx, [rsp+0F8h+string]; string
0x180091dc6  call    cs:__imp_WindowsGetStringRawBuffer
0x180091dcc  mov     rdx, rax
0x180091dcf  lea     rcx, [rsp+0F8h+var_50]
0x180091dd7  call    ?VectorFromDelimitedString@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGG@Z; VectorFromDelimitedString(ushort const *,ushort)
0x180091ddc  mov     rdx, rax
0x180091ddf  lea     rcx, [rsp+0F8h+var_B8]
0x180091de4  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> &&)
0x180091de9  lea     rcx, [rsp+0F8h+var_50]
0x180091df1  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180091df6  mov     [rsp+0F8h+var_D8], r15
0x180091dfb  mov     [rsp+0F8h+var_D0], r15
0x180091e00  xor     ecx, ecx; string
0x180091e02  call    cs:__imp_WindowsDeleteString
0x180091e08  mov     [rsp+0F8h+var_D8], r15; int
0x180091e0d  mov     rdx, rsi; unsigned __int16 *
0x180091e10  lea     rcx, [rsp+0F8h+var_90]; this
0x180091e15  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180091e1a  lea     rdx, [rsp+0F8h+var_D8]
0x180091e1f  mov     rcx, [rsp+0F8h+var_90]
0x180091e24  call    GetDefaultInputMethodForLanguage
0x180091e29  test    eax, eax
0x180091e2b  js      loc_180091EBA
0x180091e31  mov     rcx, [rsp+0F8h+var_D0]; string
0x180091e36  call    cs:__imp_WindowsDeleteString
0x180091e3c  mov     [rsp+0F8h+var_D0], r15
0x180091e41  lea     rdx, [rsp+0F8h+var_D0]
0x180091e46  mov     rcx, [rsp+0F8h+var_D8]
0x180091e4b  call    GetInputMethodDescription
0x180091e50  mov     rcx, [rsp+0F8h]; this
0x180091e58  test    eax, eax
0x180091e5a  jns     short loc_180091E72
0x180091e5c  mov     r9d, eax; char *
0x180091e5f  lea     r8, aShellOobeMachi_22; "shell\\oobe\\machine\\plugins\\adapters"...
0x180091e66  mov     edx, 0F9h; void *
0x180091e6b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180091e70  jmp     short loc_180091EBA
0x180091e72  xor     edx, edx; length
0x180091e74  mov     rcx, [rsp+0F8h+var_D8]; string
0x180091e79  call    cs:__imp_WindowsGetStringRawBuffer
0x180091e7f  mov     rdx, rax
0x180091e82  lea     rcx, [rsp+0F8h+var_70]
0x180091e8a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180091e8f  nop
0x180091e90  lea     r9, [rsp+0F8h+var_70]
0x180091e98  mov     r8, [rsp+0F8h+var_B8]
0x180091e9d  lea     rdx, [rsp+0F8h+var_A0]
0x180091ea2  lea     rcx, [rsp+0F8h+var_B8]
0x180091ea7  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::vector<std::wstring>::emplace<std::wstring>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring &&)
0x180091eac  nop
0x180091ead  lea     rcx, [rsp+0F8h+var_70]
0x180091eb5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180091eba  test    rdi, rdi
0x180091ebd  jz      loc_180092018
0x180091ec3  cmp     [rdi], r15w
0x180091ec7  jz      loc_180092018
0x180091ecd  mov     rdx, rdi
0x180091ed0  lea     rcx, [rsp+0F8h+var_70]
0x180091ed8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180091edd  lea     rcx, [rsp+0F8h+var_70]
0x180091ee5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180091eea  mov     rbx, rax
0x180091eed  mov     rcx, [rsp+0F8h+var_60]
0x180091ef5  lea     rsi, [rax+rcx*2]
0x180091ef9  mov     rdi, rax
0x180091efc  cmp     rax, rsi
0x180091eff  jz      short loc_180091F1A
0x180091f01  movzx   ecx, word ptr [rbx]; C
0x180091f04  call    cs:__imp_toupper
0x180091f0a  mov     [rdi], ax
0x180091f0d  lea     rdi, [rdi+2]
0x180091f11  add     rbx, 2
0x180091f15  cmp     rbx, rsi
0x180091f18  jnz     short loc_180091F01
0x180091f1a  lea     rdx, [rsp+0F8h+var_70]
0x180091f22  lea     rcx, [rsp+0F8h+var_90]
0x180091f27  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180091f2c  mov     r8, rax
0x180091f2f  lea     rdx, [rsp+0F8h+var_B8]
0x180091f34  lea     rcx, [rsp+0F8h+var_50]
0x180091f3c  call    ?GetCompatibleIdForPromotion@OobeKeyboardStatics@CloudExperienceHostAPI@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@V34@@Z; CloudExperienceHostAPI::OobeKeyboardStatics::GetCompatibleIdForPromotion(std::vector<std::wstring> const &,std::wstring)
0x180091f41  nop
0x180091f42  mov     [rsp+0F8h+var_C8], r15
0x180091f47  cmp     [rsp+0F8h+var_40], r15
0x180091f4f  jz      loc_180091FED
0x180091f55  xor     ecx, ecx; string
0x180091f57  call    cs:__imp_WindowsDeleteString
0x180091f5d  mov     [rsp+0F8h+var_C8], r15
0x180091f62  lea     rcx, [rsp+0F8h+var_50]
0x180091f6a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180091f6f  mov     rdx, rax; unsigned __int16 *
0x180091f72  lea     rcx, [rsp+0F8h+var_90]; this
0x180091f77  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180091f7c  lea     rdx, [rsp+0F8h+var_C8]
0x180091f81  mov     rcx, [rsp+0F8h+var_90]
0x180091f86  call    GetInputMethodDescription
0x180091f8b  mov     rcx, [rsp+0F8h]; this
0x180091f93  test    eax, eax
0x180091f95  jns     short loc_180091FAD
0x180091f97  mov     r9d, eax; char *
0x180091f9a  lea     r8, aShellOobeMachi_22; "shell\\oobe\\machine\\plugins\\adapters"...
0x180091fa1  mov     edx, 10Eh; void *
0x180091fa6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180091fab  jmp     short loc_180091FED
0x180091fad  lea     rcx, [rsp+0F8h+var_50]
0x180091fb5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180091fba  mov     rdx, rax
0x180091fbd  lea     rcx, [rsp+0F8h+var_90]
0x180091fc2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180091fc7  nop
0x180091fc8  lea     r9, [rsp+0F8h+var_90]
0x180091fcd  mov     r8, [rsp+0F8h+var_B8]
0x180091fd2  lea     rdx, [rsp+0F8h+var_A0]
0x180091fd7  lea     rcx, [rsp+0F8h+var_B8]
0x180091fdc  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::vector<std::wstring>::emplace<std::wstring>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring &&)
0x180091fe1  nop
0x180091fe2  lea     rcx, [rsp+0F8h+var_90]
0x180091fe7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180091fec  nop
0x180091fed  mov     rcx, [rsp+0F8h+var_C8]; string
0x180091ff2  call    cs:__imp_WindowsDeleteString
0x180091ff8  mov     [rsp+0F8h+var_C8], r15
0x180091ffd  lea     rcx, [rsp+0F8h+var_50]
0x180092005  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009200a  nop
0x18009200b  lea     rcx, [rsp+0F8h+var_70]
0x180092013  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180092018  lea     rcx, [rsp+0F8h+var_B8]
0x18009201d  call    ??$RemoveDuplicates@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; RemoveDuplicates<std::vector<std::wstring>>(std::vector<std::wstring> &)
0x180092022  nop
0x180092023  mov     rcx, [rsp+0F8h+var_D0]; string
0x180092028  call    cs:__imp_WindowsDeleteString
0x18009202e  mov     [rsp+0F8h+var_D0], r15
0x180092033  mov     rcx, [rsp+0F8h+var_D8]; string
0x180092038  call    cs:__imp_WindowsDeleteString
0x18009203e  nop
0x18009203f  mov     [rsp+0F8h+var_D0], r15
0x180092044  lea     rdx, [rsp+0F8h+var_D0]
0x180092049  call    ??$CreateExternalObjectVector@UIOobeKeyboard@CloudExperienceHostAPI@@V?$Vector@PEAUIOobeKeyboard@CloudExperienceHostAPI@@U?$DefaultEqualityPredicate@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@4567@U?$DefaultVectorOptions@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@4567@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIOobeKeyboard@CloudExperienceHostAPI@@U?$DefaultEqualityPredicate@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@4567@U?$DefaultVectorOptions@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@4567@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<CloudExperienceHostAPI::IOobeKeyboard,Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeKeyboard *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeKeyboard *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeKeyboard *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeKeyboard *>> * *)
0x18009204e  mov     ebx, eax
0x180092050  test    eax, eax
0x180092052  jns     short loc_18009205E
0x180092054  mov     edx, 118h
0x180092059  jmp     loc_1800921BD
0x18009205e  mov     rbx, [rsp+0F8h+var_B8]
0x180092063  mov     rdi, [rsp+0F8h+var_D0]
0x180092068  cmp     rbx, [rsp+0F8h+var_B0]
0x18009206d  jz      loc_1800921A0
0x180092073  mov     [rsp+0F8h+var_D8], r15
0x180092078  xor     ecx, ecx; string
0x18009207a  call    cs:__imp_WindowsDeleteString
0x180092080  mov     [rsp+0F8h+var_D8], r15; int
0x180092085  mov     rcx, rbx
0x180092088  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009208d  mov     rdx, rax; unsigned __int16 *
0x180092090  lea     rcx, [rsp+0F8h+var_90]; this
0x180092095  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18009209a  lea     rdx, [rsp+0F8h+var_D8]
0x18009209f  mov     rcx, [rsp+0F8h+var_90]
0x1800920a4  call    GetInputMethodDescription
0x1800920a9  mov     esi, eax
0x1800920ab  test    eax, eax
0x1800920ad  js      loc_18009215A
0x1800920b3  xor     edx, edx; length
0x1800920b5  mov     rcx, [rsp+0F8h+var_D8]; string
0x1800920ba  call    cs:__imp_WindowsGetStringRawBuffer
0x1800920c0  mov     [rsp+0F8h+var_98], rax
0x1800920c5  mov     rcx, rbx
0x1800920c8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800920cd  mov     [rsp+0F8h+var_A0], rax
0x1800920d2  mov     [rsp+0F8h+var_C8], r15
0x1800920d7  lea     r8, [rsp+0F8h+var_98]
0x1800920dc  lea     rdx, [rsp+0F8h+var_A0]
0x1800920e1  lea     rcx, [rsp+0F8h+var_C8]
0x1800920e6  call    ??$MakeAndInitialize@VOobeKeyboard@CloudExperienceHostAPI@@V12@PEBGPEBG@Details@WRL@Microsoft@@YAJPEAPEAVOobeKeyboard@CloudExperienceHostAPI@@$$QEAPEBG1@Z; Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostAPI::OobeKeyboard,CloudExperienceHostAPI::OobeKeyboard,ushort const *,ushort const *>(CloudExperienceHostAPI::OobeKeyboard * *,ushort const * &&,ushort const * &&)
0x1800920eb  mov     esi, eax
0x1800920ed  test    eax, eax
0x1800920ef  js      short loc_180092131
0x1800920f1  mov     rax, [rdi]
0x1800920f4  mov     rdx, [rsp+0F8h+var_C8]
0x1800920f9  mov     rcx, rdi
0x1800920fc  mov     rax, [rax+68h]
0x180092100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092105  mov     esi, eax
0x180092107  test    eax, eax
0x180092109  js      short loc_18009212A
0x18009210b  lea     rcx, [rsp+0F8h+var_C8]
0x180092110  call    ??1?$com_ptr_t@VOobeKeyboard@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::OobeKeyboard,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeKeyboard,wil::err_exception_policy>(void)
0x180092115  nop
0x180092116  mov     rcx, [rsp+0F8h+var_D8]; string
0x18009211b  call    cs:__imp_WindowsDeleteString
0x180092121  add     rbx, 20h ; ' '
0x180092125  jmp     loc_180092068
0x18009212a  mov     edx, 121h
0x18009212f  jmp     short loc_180092136
0x180092131  mov     edx, 120h; void *
0x180092136  lea     r8, aShellOobeMachi_22; "shell\\oobe\\machine\\plugins\\adapters"...
0x18009213d  mov     r9d, esi; char *
0x180092140  mov     rcx, [rsp+0F8h]; this
0x180092148  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009214d  nop
0x18009214e  lea     rcx, [rsp+0F8h+var_C8]
0x180092153  call    ??1?$com_ptr_t@VOobeKeyboard@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::OobeKeyboard,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeKeyboard,wil::err_exception_policy>(void)
0x180092158  jmp     short loc_180092177
0x18009215a  mov     rcx, [rsp+0F8h]; this
0x180092162  mov     r9d, esi; char *
0x180092165  lea     r8, aShellOobeMachi_22; "shell\\oobe\\machine\\plugins\\adapters"...
0x18009216c  mov     edx, 11Dh; void *
0x180092171  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092176  nop
0x180092177  mov     rcx, [rsp+0F8h+var_D8]; string
0x18009217c  call    cs:__imp_WindowsDeleteString
0x180092182  mov     [rsp+0F8h+var_D8], r15
0x180092187  lea     rcx, [rsp+0F8h+var_D0]
0x18009218c  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180092191  nop
0x180092192  lea     rcx, [rsp+0F8h+var_B8]
0x180092197  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18009219c  mov     ebx, esi
0x18009219e  jmp     short loc_1800921EB
0x1800921a0  mov     rax, [rdi]
0x1800921a3  mov     rdx, r14
0x1800921a6  mov     rcx, rdi
0x1800921a9  mov     rax, [rax+40h]
0x1800921ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800921b2  mov     ebx, eax
0x1800921b4  test    eax, eax
0x1800921b6  jns     short loc_1800921FA
0x1800921b8  mov     edx, 124h; void *
0x1800921bd  mov     r9d, eax; char *
0x1800921c0  lea     r8, aShellOobeMachi_22; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800921c7  mov     rcx, [rsp+0F8h]; this
0x1800921cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800921d4  nop
0x1800921d5  lea     rcx, [rsp+0F8h+var_D0]
0x1800921da  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800921df  nop
0x1800921e0  lea     rcx, [rsp+0F8h+var_B8]
0x1800921e5  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800921ea  nop
0x1800921eb  mov     rcx, [rsp+0F8h+string]; string
0x1800921f0  call    cs:__imp_WindowsDeleteString
0x1800921f6  mov     eax, ebx
0x1800921f8  jmp     short loc_180092239
0x1800921fa  lea     rcx, [rsp+0F8h+var_D0]
0x1800921ff  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180092204  nop
0x180092205  lea     rcx, [rsp+0F8h+var_B8]
0x18009220a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18009220f  nop
0x180092210  mov     rcx, [rsp+0F8h+string]; string
0x180092215  call    cs:__imp_WindowsDeleteString
0x18009221b  xor     eax, eax
0x18009221d  jmp     short loc_180092239
0x18009221f  lea     rcx, [rsp+0F8h+var_B8]
0x180092224  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180092229  nop
0x18009222a  mov     rcx, [rsp+0F8h+string]; string
0x18009222f  call    cs:__imp_WindowsDeleteString
  ... truncated ...
```
