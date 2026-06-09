# CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForDefaultInputLanguage(Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeKeyboard *> * *)

- ea: `0x180091910`
- end: `0x180091c31`
- name: `?GetKeyboardsForDefaultInputLanguage@OobeKeyboardStatics@CloudExperienceHostAPI@@UEAAJPEAPEAU?$IVectorView@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@@Z`
- size: `801`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003470`
- `0x180003ffc`
- `0x180008524`
- `0x180008544`
- `0x18001ad08`
- `0x1800230b0`
- `0x180042068`
- `0x18005cf54`
- `0x1800883a4`
- `0x180088494`
- `0x180088950`
- `0x180091910`
- `0x180091d1c`
- `0x180092ce0`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180091957`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180091957`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180091ae9`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180091ae9`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18009196e`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18009196e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091a23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091bef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091a23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091bef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091a8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091b26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091b5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091a8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091b26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091b5f`

## string_xrefs

- `0x1800919c5`: `CloudExperienceHostAPI.OobeXmlAdapter`
- `0x18009197f`: `shell\oobe\machine\plugins\adapters\winrt\oobekeyboard.cpp`
- `0x1800919a2`: `shell\oobe\machine\plugins\adapters\winrt\oobekeyboard.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForDefaultInputLanguage(
        __int64 a1,
        _QWORD *a2)
{
  LANGID ThreadUILanguage; // ax
  const char *v5; // r9
  __int64 v7; // rbx
  int v8; // eax
  __int64 (__fastcall *v9)(__int64, HSTRING, HSTRING *, _BYTE *); // rdi
  HSTRING *v10; // rax
  int v11; // eax
  WCHAR *v12; // rax
  int v13; // eax
  unsigned int LastError; // ebx
  const char *v15; // r9
  WCHAR *StringRawBuffer; // rax
  int KeyboardsForLocaleByName; // eax
  wil::details::in1diag3 *v18; // rcx
  __int64 v19; // rdx
  WCHAR *v20; // rax
  int v21; // eax
  __int64 v22; // rax
  int v23; // [rsp+20h] [rbp-E0h]
  _BYTE v24[8]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h]
  WCHAR v31[88]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR LCData[88]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  CloudExperienceHostCoreTelemetry::GlobalizationState<char const (&)[67]>("CloudExperienceHostAPI::OobeKeyboardStatics::"
                                                                           "GetKeyboardsForDefaultInputLanguage");
  *a2 = 0;
  ThreadUILanguage = GetThreadUILanguage();
  if ( !GetLocaleInfoW(ThreadUILanguage, 0x5Cu, LCData, 85) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x7B,
             (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
             v5);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(
    &v28,
    a1 + 72);
  v7 = v28;
  if ( !v28 )
  {
    v28 = 0;
    v30 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"CloudExperienceHostAPI.OobeXmlAdapter",
      0x26u,
      0x25u);
    v8 = Windows::Foundation::ActivateInstance<CloudExperienceHostAPI::IOobeXmlAdapter>(v30, &v28);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
        (const char *)(unsigned int)v8,
        v23);
    v7 = v28;
  }
  string = 0;
  if ( v7 )
  {
    v24[0] = 0;
    v9 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *, _BYTE *))(*(_QWORD *)v7 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v10 = Windows::Internal::StringReference::StringReference((HSTRING *)&hstringHeader, L"defaults/keyboard");
    v11 = v9(v7, *v10, &string, v24);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
        (const char *)(unsigned int)v11,
        v23);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PairedLocaleInputMethods>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PairedLocaleInputMethods>::GetImpl'::`2'::impl) )
  {
    memset_0(v31, 0, 0xAAu);
    if ( !GetLocaleInfoEx(0, 0x5Cu, v31, 85) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x8E,
                    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
                    v15);
      goto LABEL_26;
    }
    v27 = 0;
    v26 = 0;
    StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
    KeyboardsForLocaleByName = CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForLocaleByName(
                                 v31,
                                 StringRawBuffer,
                                 &v26);
    v18 = retaddr;
    if ( KeyboardsForLocaleByName >= 0 )
    {
      KeyboardsForLocaleByName = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 56LL))(v26, &v27);
      v18 = retaddr;
      if ( KeyboardsForLocaleByName >= 0 )
      {
        if ( v27 )
        {
          v22 = v26;
          v26 = 0;
          *a2 = v22;
LABEL_24:
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v26);
          goto LABEL_25;
        }
LABEL_18:
        v20 = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
        v21 = CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForLocaleByName(LCData, v20, a2);
        LastError = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9A,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
            (const char *)(unsigned int)v21,
            v23);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v26);
          goto LABEL_26;
        }
        goto LABEL_24;
      }
      v19 = 148;
    }
    else
    {
      v19 = 147;
    }
    wil::details::in1diag3::_Log_Hr(
      v18,
      (void *)v19,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
      (const char *)(unsigned int)KeyboardsForLocaleByName,
      v23);
    goto LABEL_18;
  }
  v12 = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
  v13 = CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForLocaleByName(LCData, v12, a2);
  LastError = v13;
  if ( v13 >= 0 )
  {
LABEL_25:
    LastError = 0;
    goto LABEL_26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9F,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
    (const char *)(unsigned int)v13,
    v23);
LABEL_26:
  WindowsDeleteString(string);
  string = 0;
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v28);
  return LastError;
}

```

## disassembly

```asm
0x180091910  mov     [rsp-8+arg_10], rbx
0x180091915  mov     [rsp-8+arg_18], rsi
0x18009191a  push    rbp
0x18009191b  push    rdi
0x18009191c  push    r14
0x18009191e  lea     rbp, [rsp-0F0h]
0x180091926  sub     rsp, 1F0h
0x18009192d  mov     rax, cs:__security_cookie
0x180091934  xor     rax, rsp
0x180091937  mov     [rbp+100h+var_20], rax
0x18009193e  mov     r14, rdx
0x180091941  mov     rbx, rcx
0x180091944  lea     rcx, aCloudexperienc_14; "CloudExperienceHostAPI::OobeKeyboardSta"...
0x18009194b  call    ??$GlobalizationState@AEAY0ED@$$CBD@CloudExperienceHostCoreTelemetry@@SAXAEAY0ED@$$CBD@Z; CloudExperienceHostCoreTelemetry::GlobalizationState<char const (&)[67]>(char const (&)[67])
0x180091950  mov     qword ptr [r14], 0
0x180091957  call    cs:__imp_GetThreadUILanguage
0x18009195d  movzx   ecx, ax; Locale
0x180091960  mov     r9d, 55h ; 'U'; cchData
0x180091966  lea     r8, [rbp+100h+LCData]; lpLCData
0x18009196a  lea     edx, [r9+7]; LCType
0x18009196e  call    cs:__imp_GetLocaleInfoW
0x180091974  test    eax, eax
0x180091976  jnz     short loc_180091993
0x180091978  mov     rcx, [rbp+108h]; this
0x18009197f  lea     r8, aShellOobeMachi_22; "shell\\oobe\\machine\\plugins\\adapters"...
0x180091986  lea     edx, [rax+7Bh]; void *
0x180091989  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009198e  jmp     loc_180091C0A
0x180091993  lea     rdx, [rbx+48h]
0x180091997  lea     rcx, [rsp+200h+var_1B0]
0x18009199c  call    ??0?$com_ptr_t@UIOobeXmlAdapter@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy> const &)
0x1800919a1  nop
0x1800919a2  lea     rsi, aShellOobeMachi_22; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800919a9  mov     rbx, [rsp+200h+var_1B0]
0x1800919ae  test    rbx, rbx
0x1800919b1  jnz     short loc_180091A07
0x1800919b3  mov     [rsp+200h+var_1B0], rbx
0x1800919b8  mov     [rsp+200h+var_190], rbx
0x1800919bd  lea     r9d, [rbx+25h]; unsigned int
0x1800919c1  lea     r8d, [rbx+26h]; unsigned int
0x1800919c5  lea     rdx, ?RuntimeClass_CloudExperienceHostAPI_OobeXmlAdapter@@3QBGB; "CloudExperienceHostAPI.OobeXmlAdapter"
0x1800919cc  lea     rcx, [rsp+200h+hstringHeader]; hstringHeader
0x1800919d1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800919d6  nop
0x1800919d7  lea     rdx, [rsp+200h+var_1B0]
0x1800919dc  mov     rcx, [rsp+200h+var_190]
0x1800919e1  call    ??$ActivateInstance@UIOobeXmlAdapter@CloudExperienceHostAPI@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIOobeXmlAdapter@CloudExperienceHostAPI@@@Z; Windows::Foundation::ActivateInstance<CloudExperienceHostAPI::IOobeXmlAdapter>(HSTRING__ *,CloudExperienceHostAPI::IOobeXmlAdapter * *)
0x1800919e6  mov     rcx, [rbp+108h]; this
0x1800919ed  test    eax, eax
0x1800919ef  jns     short loc_180091A02
0x1800919f1  mov     r9d, eax; char *
0x1800919f4  mov     r8, rsi; unsigned int
0x1800919f7  mov     edx, 81h; void *
0x1800919fc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180091a01  nop
0x180091a02  mov     rbx, [rsp+200h+var_1B0]
0x180091a07  mov     [rsp+200h+string], 0
0x180091a10  test    rbx, rbx
0x180091a13  jz      short loc_180091A76
0x180091a15  mov     [rsp+200h+var_1D0], 0
0x180091a1a  mov     rax, [rbx]
0x180091a1d  mov     rdi, [rax+38h]
0x180091a21  xor     ecx, ecx; string
0x180091a23  call    cs:__imp_WindowsDeleteString
0x180091a29  mov     [rsp+200h+string], 0
0x180091a32  lea     rdx, aDefaultsKeyboa; "defaults/keyboard"
0x180091a39  lea     rcx, [rsp+200h+hstringHeader]; string
0x180091a3e  call    ??$?0$0BC@@StringReference@Internal@Windows@@QEAA@AEAY0BC@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[18])
0x180091a43  lea     r9, [rsp+200h+var_1D0]
0x180091a48  lea     r8, [rsp+200h+string]
0x180091a4d  mov     rdx, [rax]
0x180091a50  mov     rcx, rbx
0x180091a53  mov     rax, rdi
0x180091a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091a5b  mov     rcx, [rbp+108h]; this
0x180091a62  test    eax, eax
0x180091a64  jns     short loc_180091A76
0x180091a66  mov     r9d, eax; char *
0x180091a69  mov     r8, rsi; unsigned int
0x180091a6c  mov     edx, 87h; void *
0x180091a71  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180091a76  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PairedLocaleInputMethods@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PairedLocaleInputMethods@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PairedLocaleInputMethods> `wil::Feature<__WilFeatureTraits_Feature_PairedLocaleInputMethods>::GetImpl(void)'::`2'::impl
0x180091a7d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PairedLocaleInputMethods@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PairedLocaleInputMethods>::__private_IsEnabled(void)
0x180091a82  test    al, al
0x180091a84  jnz     short loc_180091AC8
0x180091a86  xor     edx, edx; length
0x180091a88  mov     rcx, [rsp+200h+string]; string
0x180091a8d  call    cs:__imp_WindowsGetStringRawBuffer
0x180091a93  mov     r8, r14
0x180091a96  mov     rdx, rax
0x180091a99  lea     rcx, [rbp+100h+LCData]; unsigned __int16 *
0x180091a9d  call    ?GetKeyboardsForLocaleByName@OobeKeyboardStatics@CloudExperienceHostAPI@@CAJPEBG0PEAPEAU?$IVectorView@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@@Z; CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForLocaleByName(ushort const *,ushort const *,Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeKeyboard *> * *)
0x180091aa2  mov     ebx, eax
0x180091aa4  test    eax, eax
0x180091aa6  jns     loc_180091BE8
0x180091aac  mov     rcx, [rbp+108h]; this
0x180091ab3  mov     r9d, eax; char *
0x180091ab6  mov     r8, rsi; unsigned int
0x180091ab9  mov     edx, 9Fh; void *
0x180091abe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091ac3  jmp     loc_180091BEA
0x180091ac8  xor     edx, edx; Val
0x180091aca  mov     r8d, 0AAh; Size
0x180091ad0  lea     rcx, [rbp+100h+var_180]; void *
0x180091ad4  call    memset_0
0x180091ad9  mov     r9d, 55h ; 'U'; cchData
0x180091adf  lea     r8, [rbp+100h+var_180]; lpLCData
0x180091ae3  lea     edx, [r9+7]; LCType
0x180091ae7  xor     ecx, ecx; lpLocaleName
0x180091ae9  call    cs:__imp_GetLocaleInfoEx
0x180091aef  test    eax, eax
0x180091af1  jnz     short loc_180091B0E
0x180091af3  mov     rcx, [rbp+108h]; this
0x180091afa  mov     r8, rsi; unsigned int
0x180091afd  mov     edx, 8Eh; void *
0x180091b02  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180091b07  mov     ebx, eax
0x180091b09  jmp     loc_180091BEA
0x180091b0e  mov     [rsp+200h+var_1B8], 0
0x180091b16  mov     [rsp+200h+var_1C0], 0
0x180091b1f  xor     edx, edx; length
0x180091b21  mov     rcx, [rsp+200h+string]; string
0x180091b26  call    cs:__imp_WindowsGetStringRawBuffer
0x180091b2c  lea     r8, [rsp+200h+var_1C0]
0x180091b31  mov     rdx, rax
0x180091b34  lea     rcx, [rbp+100h+var_180]; unsigned __int16 *
0x180091b38  call    ?GetKeyboardsForLocaleByName@OobeKeyboardStatics@CloudExperienceHostAPI@@CAJPEBG0PEAPEAU?$IVectorView@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@@Z; CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForLocaleByName(ushort const *,ushort const *,Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeKeyboard *> * *)
0x180091b3d  mov     rcx, [rbp+108h]; this
0x180091b44  test    eax, eax
0x180091b46  jns     short loc_180091B9E
0x180091b48  mov     edx, 93h; void *
0x180091b4d  mov     r8, rsi; unsigned int
0x180091b50  mov     r9d, eax; char *
0x180091b53  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180091b58  xor     edx, edx; length
0x180091b5a  mov     rcx, [rsp+200h+string]; string
0x180091b5f  call    cs:__imp_WindowsGetStringRawBuffer
0x180091b65  mov     r8, r14
0x180091b68  mov     rdx, rax
0x180091b6b  lea     rcx, [rbp+100h+LCData]; unsigned __int16 *
0x180091b6f  call    ?GetKeyboardsForLocaleByName@OobeKeyboardStatics@CloudExperienceHostAPI@@CAJPEBG0PEAPEAU?$IVectorView@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@@Z; CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForLocaleByName(ushort const *,ushort const *,Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeKeyboard *> * *)
0x180091b74  mov     ebx, eax
0x180091b76  test    eax, eax
0x180091b78  jns     short loc_180091BDE
0x180091b7a  mov     rcx, [rbp+108h]; this
0x180091b81  mov     r9d, eax; char *
0x180091b84  mov     r8, rsi; unsigned int
0x180091b87  mov     edx, 9Ah; void *
0x180091b8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091b91  nop
0x180091b92  lea     rcx, [rsp+200h+var_1C0]
0x180091b97  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180091b9c  jmp     short loc_180091BEA
0x180091b9e  mov     rcx, [rsp+200h+var_1C0]
0x180091ba3  mov     rax, [rcx]
0x180091ba6  lea     rdx, [rsp+200h+var_1B8]
0x180091bab  mov     rax, [rax+38h]
0x180091baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091bb4  mov     rcx, [rbp+108h]
0x180091bbb  test    eax, eax
0x180091bbd  jns     short loc_180091BC6
0x180091bbf  mov     edx, 94h
0x180091bc4  jmp     short loc_180091B4D
0x180091bc6  cmp     [rsp+200h+var_1B8], 0
0x180091bcb  jbe     short loc_180091B58
0x180091bcd  mov     rax, [rsp+200h+var_1C0]
0x180091bd2  mov     [rsp+200h+var_1C0], 0
0x180091bdb  mov     [r14], rax
0x180091bde  lea     rcx, [rsp+200h+var_1C0]
0x180091be3  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180091be8  xor     ebx, ebx
0x180091bea  mov     rcx, [rsp+200h+string]; string
0x180091bef  call    cs:__imp_WindowsDeleteString
0x180091bf5  mov     [rsp+200h+string], 0
0x180091bfe  lea     rcx, [rsp+200h+var_1B0]
0x180091c03  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180091c08  mov     eax, ebx
0x180091c0a  mov     rcx, [rbp+100h+var_20]
0x180091c11  xor     rcx, rsp; StackCookie
0x180091c14  call    __security_check_cookie
0x180091c19  lea     r11, [rsp+200h+var_10]
0x180091c21  mov     rbx, [r11+30h]
0x180091c25  mov     rsi, [r11+38h]
0x180091c29  mov     rsp, r11
0x180091c2c  pop     r14
0x180091c2e  pop     rdi
0x180091c2f  pop     rbp
0x180091c30  retn
```
