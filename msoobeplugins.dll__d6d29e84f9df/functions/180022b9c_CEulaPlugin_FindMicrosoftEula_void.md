# CEulaPlugin::_FindMicrosoftEula(void)

- ea: `0x180022b9c`
- end: `0x180022ed9`
- name: `?_FindMicrosoftEula@CEulaPlugin@@AEAAJXZ`
- size: `829`
- prototype: `__int64 __fastcall(CEulaPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180022b64`

## callees

- `0x180003470`
- `0x180003ffc`
- `0x18000ac48`
- `0x18001e968`
- `0x18001e9a4`
- `0x18001f060`
- `0x1800203d0`
- `0x18002164c`
- `0x180021988`
- `0x180021b20`
- `0x180022b9c`
- `0x180022ee0`
- `0x1800b8834`
- `0x1800bbf60`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180022bda`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180022bda`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180022bf5`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180022bf5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022ccd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022ccd`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x180022c2c`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x180022c2c`
- `WINBRAND!GetInstalledEULAPath` at `0x180022e41`
- `WINBRAND!GetInstalledEULAPath` at `0x180022e41`
- `WINBRAND!EulaFreeBuffer` at `0x180022e90`
- `WINBRAND!EulaFreeBuffer` at `0x180022e90`

## string_xrefs

- `0x180022c58`: `shell\oobe\machine\plugins\eula\eulaplugin.cpp`
- `0x180022d86`: `CompositionEditionID`
- `0x180022e01`: `DIGITALPID4 structure was not found in the registry.`
- `0x180022e17`: `Failed to get DIGITALPID4 structure from registry with hr=0x%08X`
- `0x180022e25`: `Falling back to installed EULA.`
- `0x180022e52`: `Successfully retrieved installed EULA path [%s]`
- `0x180022e9b`: `Failed to get installed EULA file with hr=0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CEulaPlugin::_FindMicrosoftEula(LPVOID *this)
{
  LANGID ThreadUILanguage; // ax
  WCHAR *v3; // rsi
  unsigned int Error; // eax
  WCHAR *v5; // r14
  const char *v6; // rbx
  int ValueW; // eax
  __int64 v8; // rdx
  bool v9; // sf
  int BaseEulaType; // eax
  int MicrosoftEulaForEdition; // edi
  int v12; // ebx
  int InstalledEULAPath; // eax
  int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v16; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 **v18; // [rsp+50h] [rbp-B0h] BYREF
  void *v19; // [rsp+58h] [rbp-A8h] BYREF
  char v20; // [rsp+60h] [rbp-A0h]
  _BYTE pvData[280]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v22[432]; // [rsp+188h] [rbp+88h] BYREF
  unsigned __int16 v23[68]; // [rsp+4E8h] [rbp+3E8h] BYREF
  WCHAR geoName[8]; // [rsp+570h] [rbp+470h] BYREF
  unsigned __int16 v25[264]; // [rsp+580h] [rbp+480h] BYREF
  WCHAR LCData[264]; // [rsp+790h] [rbp+690h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+9D8h] [rbp+8D8h]

  CMicrosoftEulaData::Clear(this + 5);
  ThreadUILanguage = GetThreadUILanguage();
  if ( GetLocaleInfoW(ThreadUILanguage, 0x5Cu, LCData, 260) )
  {
    v3 = LCData;
  }
  else
  {
    v3 = 0;
    Error = ResultFromKnownLastError();
    UnattendLogW(0, L"Could not get language for EULA file with hr=0x%08X", Error);
  }
  if ( GetUserDefaultGeoName(geoName, 4) )
  {
    v5 = geoName;
  }
  else
  {
    v5 = 0;
    v6 = (const char *)(unsigned int)ResultFromKnownLastError();
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"shell\\oobe\\machine\\plugins\\eula\\eulaplugin.cpp",
      v6,
      pdwType);
    UnattendLogW(1, L"Could not get Region for EULA file with hr=0x%08X", (unsigned int)v6);
  }
  memset_0(pvData, 0, 0x4F8u);
  pcbData = 1272;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
             L"DigitalProductId4",
             8u,
             0,
             pvData,
             &pcbData);
  v9 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
    v9 = ValueW < 0;
  }
  if ( v9 )
  {
    if ( ValueW == -2147023728 )
      UnattendLogW(2, L"DIGITALPID4 structure was not found in the registry.");
    else
      UnattendLogW(1, L"Failed to get DIGITALPID4 structure from registry with hr=0x%08X", (unsigned int)ValueW);
  }
  else
  {
    LOBYTE(v8) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_EditionFallBackForEULAByOOBE>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_EditionFallBackForEULAByOOBE>::GetImpl'::`2'::impl,
      v8);
    v16 = 0;
    BaseEulaType = GetBaseEulaType(v23);
    MicrosoftEulaForEdition = BaseEulaType;
    if ( BaseEulaType < 0 )
    {
      UnattendLogW(1, L"Failed to get base EULA type with hr=0x%08X", (unsigned int)BaseEulaType);
    }
    else
    {
      MicrosoftEulaForEdition = CEulaPlugin::_FindMicrosoftEulaForEdition((CEulaPlugin *)this, v3, v5, v25, v22);
      if ( MicrosoftEulaForEdition >= 0 )
        return (unsigned int)MicrosoftEulaForEdition;
      v16 = 0;
      v18 = &v16;
      v19 = 0;
      v20 = 1;
      v12 = SHRegAllocData(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
              L"CompositionEditionID",
              2u,
              &v19,
              0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v18);
      if ( v12 >= 0 )
        MicrosoftEulaForEdition = CEulaPlugin::_FindMicrosoftEulaForEdition((CEulaPlugin *)this, v3, v5, v25, v16);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v16);
    }
    if ( MicrosoftEulaForEdition >= 0 )
      return (unsigned int)MicrosoftEulaForEdition;
  }
  UnattendLogW(0, L"Falling back to installed EULA.");
  v16 = 0;
  InstalledEULAPath = GetInstalledEULAPath(&v16);
  MicrosoftEulaForEdition = InstalledEULAPath;
  if ( InstalledEULAPath < 0 )
  {
    UnattendLogW(1, L"Failed to get installed EULA file with hr=0x%08X", (unsigned int)InstalledEULAPath);
  }
  else
  {
    UnattendLogW(0, L"Successfully retrieved installed EULA path [%s]", v16);
    MicrosoftEulaForEdition = CMicrosoftEulaData::Set((CMicrosoftEulaData *)(this + 5), 0, 0, 0, 0, v16, 1);
    EulaFreeBuffer(v16);
  }
  return (unsigned int)MicrosoftEulaForEdition;
}

```

## disassembly

```asm
0x180022b9c  mov     [rsp-8+arg_8], rbx
0x180022ba1  mov     [rsp-8+arg_10], rsi
0x180022ba6  push    rbp
0x180022ba7  push    rdi
0x180022ba8  push    r12
0x180022baa  push    r14
0x180022bac  push    r15
0x180022bae  lea     rbp, [rsp-8B0h]
0x180022bb6  sub     rsp, 9B0h
0x180022bbd  mov     rax, cs:__security_cookie
0x180022bc4  xor     rax, rsp
0x180022bc7  mov     [rbp+8D0h+var_30], rax
0x180022bce  mov     r15, rcx
0x180022bd1  add     rcx, 28h ; '('; this
0x180022bd5  call    ?Clear@CMicrosoftEulaData@@QEAAXXZ; CMicrosoftEulaData::Clear(void)
0x180022bda  call    cs:__imp_GetThreadUILanguage
0x180022be0  movzx   ecx, ax; Locale
0x180022be3  mov     r9d, 104h; cchData
0x180022be9  lea     r8, [rbp+8D0h+LCData]; lpLCData
0x180022bf0  mov     edx, 5Ch ; '\'; LCType
0x180022bf5  call    cs:__imp_GetLocaleInfoW
0x180022bfb  test    eax, eax
0x180022bfd  jz      short loc_180022C08
0x180022bff  lea     rsi, [rbp+8D0h+LCData]
0x180022c06  jmp     short loc_180022C20
0x180022c08  xor     esi, esi
0x180022c0a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180022c0f  mov     r8d, eax
0x180022c12  lea     rdx, aCouldNotGetLan; "Could not get language for EULA file wi"...
0x180022c19  xor     ecx, ecx
0x180022c1b  call    UnattendLogW
0x180022c20  mov     edx, 4; geoNameCount
0x180022c25  lea     rcx, [rbp+8D0h+geoName]; geoName
0x180022c2c  call    cs:__imp_GetUserDefaultGeoName
0x180022c32  mov     edi, 1
0x180022c37  test    eax, eax
0x180022c39  jz      short loc_180022C44
0x180022c3b  lea     r14, [rbp+8D0h+geoName]
0x180022c42  jmp     short loc_180022C7A
0x180022c44  xor     r14d, r14d
0x180022c47  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180022c4c  mov     ebx, eax
0x180022c4e  mov     rcx, [rbp+8D8h]; this
0x180022c55  mov     r9d, eax; char *
0x180022c58  lea     r8, aShellOobeMachi_17; "shell\\oobe\\machine\\plugins\\eula\\eu"...
0x180022c5f  mov     edx, 171h; void *
0x180022c64  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180022c69  mov     r8d, ebx
0x180022c6c  lea     rdx, aCouldNotGetReg; "Could not get Region for EULA file with"...
0x180022c73  mov     ecx, edi
0x180022c75  call    UnattendLogW
0x180022c7a  mov     ebx, 4F8h
0x180022c7f  mov     r8d, ebx; Size
0x180022c82  xor     edx, edx; Val
0x180022c84  lea     rcx, [rsp+9D0h+var_960]; void *
0x180022c89  call    memset_0
0x180022c8e  mov     [rsp+9D0h+var_988], ebx
0x180022c92  lea     rax, [rsp+9D0h+var_988]
0x180022c97  mov     [rsp+9D0h+pcbData], rax; pcbData
0x180022c9c  lea     rax, [rsp+9D0h+var_960]
0x180022ca1  mov     [rsp+9D0h+pvData], rax; pvData
0x180022ca6  mov     [rsp+9D0h+pdwType], 0; pdwType
0x180022caf  mov     r9d, 8; dwFlags
0x180022cb5  lea     r8, aDigitalproduct; "DigitalProductId4"
0x180022cbc  lea     rdx, aSoftwareMicros_38; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180022cc3  mov     rbx, 0FFFFFFFF80000002h
0x180022cca  mov     rcx, rbx; hkey
0x180022ccd  call    cs:__imp_RegGetValueW
0x180022cd3  test    eax, eax
0x180022cd5  jle     short loc_180022CE1
0x180022cd7  movzx   eax, ax
0x180022cda  or      eax, 80070000h
0x180022cdf  test    eax, eax
0x180022ce1  js      loc_180022DFA
0x180022ce7  mov     dl, dil
0x180022cea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EditionFallBackForEULAByOOBE@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EditionFallBackForEULAByOOBE@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EditionFallBackForEULAByOOBE> `wil::Feature<__WilFeatureTraits_Feature_EditionFallBackForEULAByOOBE>::GetImpl(void)'::`2'::impl
0x180022cf1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_EditionFallBackForEULAByOOBE@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EditionFallBackForEULAByOOBE>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180022cf6  mov     [rsp+9D0h+var_990], 0
0x180022cff  lea     r9, [rbp+8D0h+var_450]
0x180022d06  lea     r8, [rsp+9D0h+var_990]
0x180022d0b  lea     rcx, [rbp+8D0h+var_4E8]; unsigned __int16 *
0x180022d12  call    GetBaseEulaType
0x180022d17  mov     edi, eax
0x180022d19  test    eax, eax
0x180022d1b  js      loc_180022DDD
0x180022d21  lea     rax, [rbp+8D0h+var_848]
0x180022d28  mov     [rsp+9D0h+pdwType], rax; unsigned __int16 *
0x180022d2d  lea     r9, [rbp+8D0h+var_450]; unsigned __int16 *
0x180022d34  mov     r8, r14; unsigned __int16 *
0x180022d37  mov     rdx, rsi; unsigned __int16 *
0x180022d3a  mov     rcx, r15; this
0x180022d3d  call    ?_FindMicrosoftEulaForEdition@CEulaPlugin@@AEAAJPEBG000@Z; CEulaPlugin::_FindMicrosoftEulaForEdition(ushort const *,ushort const *,ushort const *,ushort const *)
0x180022d42  mov     edi, eax
0x180022d44  test    eax, eax
0x180022d46  jns     loc_180022EAC
0x180022d4c  mov     [rsp+9D0h+var_990], 0
0x180022d55  lea     rax, [rsp+9D0h+var_990]
0x180022d5a  mov     [rsp+9D0h+var_980], rax
0x180022d5f  mov     [rsp+9D0h+var_978], 0
0x180022d68  mov     [rsp+9D0h+var_970], 1
0x180022d6d  mov     [rsp+9D0h+pvData], 0; unsigned int *
0x180022d76  lea     rax, [rsp+9D0h+var_978]
0x180022d7b  mov     [rsp+9D0h+pdwType], rax; void **
0x180022d80  mov     r9d, 2; int
0x180022d86  lea     r8, aCompositionedi; "CompositionEditionID"
0x180022d8d  lea     rdx, aSoftwareMicros_38; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180022d94  mov     rcx, rbx; HKEY
0x180022d97  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x180022d9c  mov     ebx, eax
0x180022d9e  lea     rcx, [rsp+9D0h+var_980]
0x180022da3  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180022da8  shr     ebx, 1Fh
0x180022dab  xor     bl, 1
0x180022dae  jz      short loc_180022DD1
0x180022db0  mov     rax, [rsp+9D0h+var_990]
0x180022db5  mov     [rsp+9D0h+pdwType], rax; unsigned __int16 *
0x180022dba  lea     r9, [rbp+8D0h+var_450]; unsigned __int16 *
0x180022dc1  mov     r8, r14; unsigned __int16 *
0x180022dc4  mov     rdx, rsi; unsigned __int16 *
0x180022dc7  mov     rcx, r15; this
0x180022dca  call    ?_FindMicrosoftEulaForEdition@CEulaPlugin@@AEAAJPEBG000@Z; CEulaPlugin::_FindMicrosoftEulaForEdition(ushort const *,ushort const *,ushort const *,ushort const *)
0x180022dcf  mov     edi, eax
0x180022dd1  lea     rcx, [rsp+9D0h+var_990]
0x180022dd6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022ddb  jmp     short loc_180022DF1
0x180022ddd  mov     r8d, eax
0x180022de0  lea     rdx, aFailedToGetBas; "Failed to get base EULA type with hr=0x"...
0x180022de7  mov     ecx, 1
0x180022dec  call    UnattendLogW
0x180022df1  test    edi, edi
0x180022df3  js      short loc_180022E25
0x180022df5  jmp     loc_180022EAC
0x180022dfa  cmp     eax, 80070490h
0x180022dff  jnz     short loc_180022E14
0x180022e01  lea     rdx, aDigitalpid4Str; "DIGITALPID4 structure was not found in "...
0x180022e08  mov     ecx, 2
0x180022e0d  call    UnattendLogW
0x180022e12  jmp     short loc_180022E25
0x180022e14  mov     r8d, eax
0x180022e17  lea     rdx, aFailedToGetDig; "Failed to get DIGITALPID4 structure fro"...
0x180022e1e  mov     ecx, edi
0x180022e20  call    UnattendLogW
0x180022e25  lea     rdx, aFallingBackToI; "Falling back to installed EULA."
0x180022e2c  xor     ecx, ecx
0x180022e2e  call    UnattendLogW
0x180022e33  mov     [rsp+9D0h+var_990], 0
0x180022e3c  lea     rcx, [rsp+9D0h+var_990]
0x180022e41  call    cs:__imp_GetInstalledEULAPath
0x180022e47  mov     edi, eax
0x180022e49  test    eax, eax
0x180022e4b  js      short loc_180022E98
0x180022e4d  mov     r8, [rsp+9D0h+var_990]
0x180022e52  lea     rdx, aSuccessfullyRe; "Successfully retrieved installed EULA p"...
0x180022e59  xor     ecx, ecx
0x180022e5b  call    UnattendLogW
0x180022e60  mov     byte ptr [rsp+9D0h+pcbData], 1; bool
0x180022e65  mov     rax, [rsp+9D0h+var_990]
0x180022e6a  mov     [rsp+9D0h+pvData], rax; unsigned __int16 *
0x180022e6f  mov     [rsp+9D0h+pdwType], 0; unsigned __int16 *
0x180022e78  xor     r9d, r9d; unsigned __int16 *
0x180022e7b  xor     r8d, r8d; unsigned __int16 *
0x180022e7e  xor     edx, edx; unsigned __int16 *
0x180022e80  lea     rcx, [r15+28h]; this
0x180022e84  call    ?Set@CMicrosoftEulaData@@QEAAJPEBG0000_N@Z; CMicrosoftEulaData::Set(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,bool)
0x180022e89  mov     edi, eax
0x180022e8b  mov     rcx, [rsp+9D0h+var_990]
0x180022e90  call    cs:__imp_EulaFreeBuffer
0x180022e96  jmp     short loc_180022EAC
0x180022e98  mov     r8d, eax
0x180022e9b  lea     rdx, aFailedToGetIns; "Failed to get installed EULA file with "...
0x180022ea2  mov     ecx, 1
0x180022ea7  call    UnattendLogW
0x180022eac  mov     eax, edi
0x180022eae  mov     rcx, [rbp+8D0h+var_30]
0x180022eb5  xor     rcx, rsp; StackCookie
0x180022eb8  call    __security_check_cookie
0x180022ebd  lea     r11, [rsp+9D0h+var_20]
0x180022ec5  mov     rbx, [r11+38h]
0x180022ec9  mov     rsi, [r11+40h]
0x180022ecd  mov     rsp, r11
0x180022ed0  pop     r15
0x180022ed2  pop     r14
0x180022ed4  pop     r12
0x180022ed6  pop     rdi
0x180022ed7  pop     rbp
0x180022ed8  retn
```
