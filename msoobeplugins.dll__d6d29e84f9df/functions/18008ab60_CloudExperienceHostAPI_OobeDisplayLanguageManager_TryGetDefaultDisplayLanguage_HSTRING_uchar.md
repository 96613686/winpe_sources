# CloudExperienceHostAPI::OobeDisplayLanguageManager::TryGetDefaultDisplayLanguage(HSTRING__ * *,uchar *)

- ea: `0x18008ab60`
- end: `0x18008acfd`
- name: `?TryGetDefaultDisplayLanguage@OobeDisplayLanguageManager@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@PEAE@Z`
- size: `413`
- prototype: `int(CloudExperienceHostAPI::OobeDisplayLanguageManager *__hidden this, HSTRING *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003470`
- `0x180008544`
- `0x18001ad08`
- `0x1800230b0`
- `0x180042068`
- `0x18005cf54`
- `0x1800883a4`
- `0x180088494`
- `0x180088950`
- `0x18008ab60`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18008ac7d`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18008ac7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008aca2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008aca2`

## string_xrefs

- `0x18008abcf`: `CloudExperienceHostAPI.OobeXmlAdapter`
- `0x18008abfb`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`
- `0x18008acb3`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CloudExperienceHostAPI::OobeDisplayLanguageManager::TryGetDefaultDisplayLanguage(
        CloudExperienceHostAPI::OobeDisplayLanguageManager *this,
        HSTRING *a2,
        unsigned __int8 *a3)
{
  __int64 v6; // rbx
  int v7; // eax
  __int64 (__fastcall *v8)(__int64, HSTRING, int *, _BYTE *); // rdi
  HSTRING *v9; // rax
  HRESULT String; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rdx
  int v15; // [rsp+20h] [rbp-E0h]
  _BYTE v16[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h]
  WCHAR LCData[88]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  CloudExperienceHostCoreTelemetry::GlobalizationState<char const (&)[67]>("CloudExperienceHostAPI::OobeDisplayLanguageMa"
                                                                           "nager::TryGetDefaultDisplayLanguage");
  *a2 = 0;
  *a3 = 0;
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(
    &v18,
    (char *)this + 56);
  v6 = v18;
  if ( !v18 )
  {
    v18 = 0;
    v20 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"CloudExperienceHostAPI.OobeXmlAdapter",
      0x26u,
      0x25u);
    v7 = Windows::Foundation::ActivateInstance<CloudExperienceHostAPI::IOobeXmlAdapter>(v20, &v18);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x164,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
        (const char *)(unsigned int)v7,
        v15);
    v6 = v18;
    if ( !v18 )
      goto LABEL_15;
  }
  v16[0] = 0;
  v17 = 0;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING, int *, _BYTE *))(*(_QWORD *)v6 + 64LL);
  v9 = Windows::Internal::StringReference::StringReference((HSTRING *)&hstringHeader, L"defaults/language");
  String = v8(v6, *v9, &v17, v16);
  v11 = String;
  if ( String >= 0 )
  {
    if ( v16[0] && GetLocaleInfoW((unsigned __int16)v17, 0x5Cu, LCData, 85) > 0 )
    {
      v13 = -1;
      do
        ++v13;
      while ( LCData[v13] );
      String = WindowsCreateString(LCData, v13, a2);
      v11 = String;
      if ( String < 0 )
      {
        v12 = 368;
        goto LABEL_13;
      }
      *a3 = 1;
    }
LABEL_15:
    v11 = 0;
    goto LABEL_16;
  }
  v12 = 363;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
    (const char *)(unsigned int)String,
    v15);
LABEL_16:
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v18);
  return v11;
}

```

## disassembly

```asm
0x18008ab60  mov     [rsp-8+arg_18], rbx
0x18008ab65  push    rbp
0x18008ab66  push    rsi
0x18008ab67  push    rdi
0x18008ab68  push    r14
0x18008ab6a  push    r15
0x18008ab6c  lea     rbp, [rsp-20h]
0x18008ab71  sub     rsp, 120h
0x18008ab78  mov     rax, cs:__security_cookie
0x18008ab7f  xor     rax, rsp
0x18008ab82  mov     [rbp+40h+var_30], rax
0x18008ab86  mov     rsi, r8
0x18008ab89  mov     r14, rdx
0x18008ab8c  mov     rbx, rcx
0x18008ab8f  lea     rcx, aCloudexperienc_4; "CloudExperienceHostAPI::OobeDisplayLang"...
0x18008ab96  call    ??$GlobalizationState@AEAY0ED@$$CBD@CloudExperienceHostCoreTelemetry@@SAXAEAY0ED@$$CBD@Z; CloudExperienceHostCoreTelemetry::GlobalizationState<char const (&)[67]>(char const (&)[67])
0x18008ab9b  xor     r15d, r15d
0x18008ab9e  mov     [r14], r15
0x18008aba1  mov     [rsi], r15b
0x18008aba4  lea     rdx, [rbx+38h]
0x18008aba8  lea     rcx, [rsp+140h+var_108]
0x18008abad  call    ??0?$com_ptr_t@UIOobeXmlAdapter@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy> const &)
0x18008abb2  nop
0x18008abb3  mov     rbx, [rsp+140h+var_108]
0x18008abb8  test    rbx, rbx
0x18008abbb  jnz     short loc_18008AC1B
0x18008abbd  mov     [rsp+140h+var_108], r15
0x18008abc2  mov     [rsp+140h+var_E8], r15
0x18008abc7  lea     r9d, [r15+25h]; unsigned int
0x18008abcb  lea     r8d, [r15+26h]; unsigned int
0x18008abcf  lea     rdx, ?RuntimeClass_CloudExperienceHostAPI_OobeXmlAdapter@@3QBGB; "CloudExperienceHostAPI.OobeXmlAdapter"
0x18008abd6  lea     rcx, [rsp+140h+hstringHeader]; hstringHeader
0x18008abdb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008abe0  nop
0x18008abe1  lea     rdx, [rsp+140h+var_108]
0x18008abe6  mov     rcx, [rsp+140h+var_E8]
0x18008abeb  call    ??$ActivateInstance@UIOobeXmlAdapter@CloudExperienceHostAPI@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIOobeXmlAdapter@CloudExperienceHostAPI@@@Z; Windows::Foundation::ActivateInstance<CloudExperienceHostAPI::IOobeXmlAdapter>(HSTRING__ *,CloudExperienceHostAPI::IOobeXmlAdapter * *)
0x18008abf0  mov     rcx, [rbp+48h]; this
0x18008abf4  test    eax, eax
0x18008abf6  jns     short loc_18008AC0D
0x18008abf8  mov     r9d, eax; char *
0x18008abfb  lea     r8, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x18008ac02  mov     edx, 164h; void *
0x18008ac07  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008ac0c  nop
0x18008ac0d  mov     rbx, [rsp+140h+var_108]
0x18008ac12  test    rbx, rbx
0x18008ac15  jz      loc_18008ACCB
0x18008ac1b  mov     [rsp+140h+var_110], r15b
0x18008ac20  mov     [rsp+140h+var_10C], r15d
0x18008ac25  mov     rax, [rbx]
0x18008ac28  mov     rdi, [rax+40h]
0x18008ac2c  lea     rdx, aDefaultsLangua; "defaults/language"
0x18008ac33  lea     rcx, [rsp+140h+hstringHeader]; string
0x18008ac38  call    ??$?0$0BC@@StringReference@Internal@Windows@@QEAA@AEAY0BC@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[18])
0x18008ac3d  lea     r9, [rsp+140h+var_110]
0x18008ac42  lea     r8, [rsp+140h+var_10C]
0x18008ac47  mov     rdx, [rax]
0x18008ac4a  mov     rcx, rbx
0x18008ac4d  mov     rax, rdi
0x18008ac50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ac55  mov     ebx, eax
0x18008ac57  test    eax, eax
0x18008ac59  jns     short loc_18008AC62
0x18008ac5b  mov     edx, 16Bh
0x18008ac60  jmp     short loc_18008ACB3
0x18008ac62  cmp     [rsp+140h+var_110], r15b
0x18008ac67  jz      short loc_18008ACCB
0x18008ac69  movzx   ecx, word ptr [rsp+140h+var_10C]; Locale
0x18008ac6e  mov     r9d, 55h ; 'U'; cchData
0x18008ac74  lea     r8, [rsp+140h+LCData]; lpLCData
0x18008ac79  lea     edx, [r9+7]; LCType
0x18008ac7d  call    cs:__imp_GetLocaleInfoW
0x18008ac83  test    eax, eax
0x18008ac85  jle     short loc_18008ACCB
0x18008ac87  lea     rax, [rsp+140h+LCData]
0x18008ac8c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008ac90  inc     rdx; length
0x18008ac93  cmp     [rax+rdx*2], r15w
0x18008ac98  jnz     short loc_18008AC90
0x18008ac9a  mov     r8, r14; string
0x18008ac9d  lea     rcx, [rsp+140h+LCData]; sourceString
0x18008aca2  call    cs:__imp_WindowsCreateString
0x18008aca8  mov     ebx, eax
0x18008acaa  test    eax, eax
0x18008acac  jns     short loc_18008ACC8
0x18008acae  mov     edx, 170h; void *
0x18008acb3  lea     r8, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x18008acba  mov     r9d, eax; char *
0x18008acbd  mov     rcx, [rbp+48h]; this
0x18008acc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008acc6  jmp     short loc_18008ACCE
0x18008acc8  mov     byte ptr [rsi], 1
0x18008accb  mov     ebx, r15d
0x18008acce  lea     rcx, [rsp+140h+var_108]
0x18008acd3  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18008acd8  mov     eax, ebx
0x18008acda  mov     rcx, [rbp+40h+var_30]
0x18008acde  xor     rcx, rsp; StackCookie
0x18008ace1  call    __security_check_cookie
0x18008ace6  mov     rbx, [rsp+140h+arg_18]
0x18008acee  add     rsp, 120h
0x18008acf5  pop     r15
0x18008acf7  pop     r14
0x18008acf9  pop     rdi
0x18008acfa  pop     rsi
0x18008acfb  pop     rbp
0x18008acfc  retn
```
