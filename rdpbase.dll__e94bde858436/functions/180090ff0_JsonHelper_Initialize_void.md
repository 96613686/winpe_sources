# JsonHelper::Initialize(void)

- ea: `0x180090ff0`
- end: `0x180091268`
- name: `?Initialize@JsonHelper@@UEAAJXZ`
- size: `632`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800711c8`
- `0x180071a60`
- `0x180078c20`
- `0x18008fc3c`
- `0x18008fd2c`
- `0x180090034`
- `0x180090ff0`
- `0x180091270`
- `0x1800923bc`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800911e8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800911e8`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180091013`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180091013`

## string_xrefs

- `0x180091128`: `ActivateInstance: JsonObject`
- `0x1800911a0`: `GetActivationFactory(JsonObject) failed!`
- `0x18009121d`: `GetActivationFactory: JsonValue`
- `0x1800910cc`: `Windows.Data.Json.JsonObject`
- `0x180091146`: `Windows.Data.Json.JsonObject`
- `0x1800911bb`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
__int64 __fastcall JsonHelper::Initialize(JsonHelper *this)
{
  int ActivationFactory; // ebx
  __int64 v3; // rdx
  __int64 v4; // r8
  int ActivityIdPrefix; // eax
  int v6; // edx
  const char *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // r8
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  __int64 v17; // [rsp+48h] [rbp-20h]

  ActivationFactory = RoInitialize(0);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::GetImpl'::`2'::impl) )
  {
    if ( ActivationFactory == -2147417850 )
      goto LABEL_15;
    if ( ActivationFactory < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v3, v4);
        v6 = 17;
LABEL_8:
        v7 = "Windows::Foundation::Initialize failed!";
LABEL_30:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v6,
          (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
          ActivityIdPrefix,
          (__int64)v7,
          ActivationFactory);
        return (unsigned int)ActivationFactory;
      }
      return (unsigned int)ActivationFactory;
    }
LABEL_14:
    *((_BYTE *)this + 64) = 1;
LABEL_15:
    v17 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    ActivationFactory = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
                          v17,
                          (char *)this + 40);
    if ( ActivationFactory >= 0 )
    {
      v17 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonObject",
        0x1Du,
        0x1Cu);
      ActivationFactory = ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
                            v17,
                            (char *)this + 48);
      if ( ActivationFactory >= 0 )
      {
        v17 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Data.Json.JsonValue",
          0x1Cu,
          0x1Bu);
        v12 = v17;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease((char *)this + 56);
        ActivationFactory = RoGetActivationFactory(v12, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, (char *)this + 56);
        if ( ActivationFactory < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v13, v14);
          v6 = 21;
          v7 = "GetActivationFactory: JsonValue";
          goto LABEL_30;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v10, v11);
        v6 = 20;
        v7 = "GetActivationFactory(JsonObject) failed!";
        goto LABEL_30;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v8, v9);
      v6 = 19;
      v7 = "ActivateInstance: JsonObject";
      goto LABEL_30;
    }
    return (unsigned int)ActivationFactory;
  }
  if ( ActivationFactory >= 0 )
    goto LABEL_14;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v3, v4);
    v6 = 18;
    goto LABEL_8;
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180090ff0  mov     [rsp+arg_8], rbx
0x180090ff5  mov     [rsp+arg_10], rsi
0x180090ffa  push    rdi
0x180090ffb  sub     rsp, 60h
0x180090fff  mov     rax, cs:__security_cookie
0x180091006  xor     rax, rsp
0x180091009  mov     [rsp+68h+var_18], rax
0x18009100e  mov     rsi, rcx
0x180091011  xor     ecx, ecx
0x180091013  call    cs:__imp_RoInitialize
0x180091019  mov     ebx, eax
0x18009101b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA> `wil::Feature<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::GetImpl(void)'::`2'::impl
0x180091022  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::__private_IsEnabled(void)
0x180091027  test    al, al
0x180091029  jz      short loc_18009107C
0x18009102b  cmp     ebx, 80010106h
0x180091031  jz      loc_1800910BB
0x180091037  test    ebx, ebx
0x180091039  jns     short loc_1800910B7
0x18009103b  mov     rcx, cs:WPP_GLOBAL_Control
0x180091042  lea     rax, WPP_GLOBAL_Control
0x180091049  cmp     rcx, rax
0x18009104c  jz      loc_180091247
0x180091052  test    byte ptr [rcx+1Ch], 8
0x180091056  jz      loc_180091247
0x18009105c  cmp     byte ptr [rcx+19h], 2
0x180091060  jb      loc_180091247
0x180091066  call    RdpX_GetActivityIdPrefix
0x18009106b  mov     edx, 11h
0x180091070  lea     rcx, aWindowsFoundat; "Windows::Foundation::Initialize failed!"
0x180091077  jmp     loc_180091224
0x18009107c  test    ebx, ebx
0x18009107e  jns     short loc_1800910B7
0x180091080  mov     rcx, cs:WPP_GLOBAL_Control
0x180091087  lea     rax, WPP_GLOBAL_Control
0x18009108e  cmp     rcx, rax
0x180091091  jz      loc_180091247
0x180091097  test    byte ptr [rcx+1Ch], 8
0x18009109b  jz      loc_180091247
0x1800910a1  cmp     byte ptr [rcx+19h], 2
0x1800910a5  jb      loc_180091247
0x1800910ab  call    RdpX_GetActivityIdPrefix
0x1800910b0  mov     edx, 12h
0x1800910b5  jmp     short loc_180091070
0x1800910b7  mov     byte ptr [rsi+40h], 1
0x1800910bb  mov     edi, 1Ch
0x1800910c0  mov     [rsp+68h+var_20], 0
0x1800910c9  mov     r9d, edi; unsigned int
0x1800910cc  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800910d3  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x1800910d8  lea     r8d, [rdi+1]; unsigned int
0x1800910dc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800910e1  mov     rcx, [rsp+68h+var_20]
0x1800910e6  lea     rdx, [rsi+28h]
0x1800910ea  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1800910ef  mov     ebx, eax
0x1800910f1  test    eax, eax
0x1800910f3  jns     short loc_180091134
0x1800910f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800910fc  lea     rax, WPP_GLOBAL_Control
0x180091103  cmp     rcx, rax
0x180091106  jz      loc_180091247
0x18009110c  test    byte ptr [rcx+1Ch], 8
0x180091110  jz      loc_180091247
0x180091116  cmp     byte ptr [rcx+19h], 2
0x18009111a  jb      loc_180091247
0x180091120  call    RdpX_GetActivityIdPrefix
0x180091125  lea     edx, [rdi-9]
0x180091128  lea     rcx, aActivateinstan; "ActivateInstance: JsonObject"
0x18009112f  jmp     loc_180091224
0x180091134  mov     r9d, edi; unsigned int
0x180091137  mov     [rsp+68h+var_20], 0
0x180091140  mov     r8d, 1Dh; unsigned int
0x180091146  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18009114d  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x180091152  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180091157  mov     rcx, [rsp+68h+var_20]
0x18009115c  lea     rdx, [rsi+30h]
0x180091160  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x180091165  mov     ebx, eax
0x180091167  test    eax, eax
0x180091169  jns     short loc_1800911A9
0x18009116b  mov     rcx, cs:WPP_GLOBAL_Control
0x180091172  lea     rax, WPP_GLOBAL_Control
0x180091179  cmp     rcx, rax
0x18009117c  jz      loc_180091247
0x180091182  test    byte ptr [rcx+1Ch], 8
0x180091186  jz      loc_180091247
0x18009118c  cmp     byte ptr [rcx+19h], 2
0x180091190  jb      loc_180091247
0x180091196  call    RdpX_GetActivityIdPrefix
0x18009119b  mov     edx, 14h
0x1800911a0  lea     rcx, aGetactivationf_0; "GetActivationFactory(JsonObject) failed"...
0x1800911a7  jmp     short loc_180091224
0x1800911a9  mov     r9d, 1Bh; unsigned int
0x1800911af  mov     [rsp+68h+var_20], 0
0x1800911b8  mov     r8d, edi; unsigned int
0x1800911bb  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800911c2  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x1800911c7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800911cc  mov     rdi, [rsp+68h+var_20]
0x1800911d1  lea     rcx, [rsi+38h]
0x1800911d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800911da  lea     r8, [rsi+38h]
0x1800911de  mov     rcx, rdi
0x1800911e1  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800911e8  call    cs:__imp_RoGetActivationFactory
0x1800911ee  mov     ebx, eax
0x1800911f0  test    eax, eax
0x1800911f2  jns     short loc_180091247
0x1800911f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800911fb  lea     rax, WPP_GLOBAL_Control
0x180091202  cmp     rcx, rax
0x180091205  jz      short loc_180091247
0x180091207  test    byte ptr [rcx+1Ch], 8
0x18009120b  jz      short loc_180091247
0x18009120d  cmp     byte ptr [rcx+19h], 2
0x180091211  jb      short loc_180091247
0x180091213  call    RdpX_GetActivityIdPrefix
0x180091218  mov     edx, 15h
0x18009121d  lea     rcx, aGetactivationf_1; "GetActivationFactory: JsonValue"
0x180091224  mov     [rsp+68h+var_40], ebx
0x180091228  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18009122f  mov     [rsp+68h+var_48], rcx
0x180091234  mov     r9d, eax
0x180091237  mov     rcx, cs:WPP_GLOBAL_Control
0x18009123e  mov     rcx, [rcx+10h]
0x180091242  call    WPP_SF_DsD
0x180091247  mov     eax, ebx
0x180091249  mov     rcx, [rsp+68h+var_18]
0x18009124e  xor     rcx, rsp; StackCookie
0x180091251  call    __security_check_cookie
0x180091256  lea     r11, [rsp+68h+var_8]
0x18009125b  mov     rbx, [r11+18h]
0x18009125f  mov     rsi, [r11+20h]
0x180091263  mov     rsp, r11
0x180091266  pop     rdi
0x180091267  retn
```
