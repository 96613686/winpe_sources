# SkipPackagedEncoderHMFT

- ea: `0x1801478c8`
- end: `0x180147ac7`
- name: `SkipPackagedEncoderHMFT`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180145550`

## callees

- `0x1800255b0`
- `0x180038bf0`
- `0x18003eef4`
- `0x1801200d0`
- `0x180128588`
- `0x180144e00`
- `0x1801478c8`
- `0x180147ad0`
- `0x180147b48`
- `0x180147b84`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180147942`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18014799a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180147a79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180147942`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18014799a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180147a79`

## string_xrefs

- `0x180147a5a`: `Microsoft.AV1EncoderVideoExtension_8wekyb3d8bbwe`
- `0x18014797b`: `Microsoft.HEVCVideoExtension_8wekyb3d8bbwe`
- `0x180147923`: `Microsoft.AVCEncoderVideoExtension_8wekyb3d8bbwe`

## pseudocode

```c
char __fastcall SkipPackagedEncoderHMFT(_QWORD *a1, __int64 a2)
{
  char v2; // bl
  bool v3; // zf
  __int64 v5; // rcx
  __int64 v6; // rdx
  CallStackScopeTrace v8; // [rsp+20h] [rbp-30h] BYREF
  INT32 result; // [rsp+24h] [rbp-2Ch] BYREF
  Microsoft::WRL::Wrappers::HStringReference v10; // [rsp+28h] [rbp-28h] BYREF

  v2 = 0;
  v3 = *a1 == *(_QWORD *)&MFT_CATEGORY_VIDEO_ENCODER.Data1;
  result = 0;
  if ( !v3 || a1[1] != *(_QWORD *)MFT_CATEGORY_VIDEO_ENCODER.Data4 )
    return v2;
  v10.hstr_ = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v10,
    L"Microsoft.AVCEncoderVideoExtension_8wekyb3d8bbwe",
    0x31u,
    0x30u);
  if ( WindowsCompareStringOrdinal(*(HSTRING *)a2, v10.hstr_, &result) >= 0 && !result )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AVCEnc_CodecPack>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AVCEnc_CodecPack>::GetImpl'::`2'::impl) )
    {
      v5 = 0;
      goto LABEL_22;
    }
    return 1;
  }
  v10.hstr_ = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v10,
    L"Microsoft.HEVCVideoExtension_8wekyb3d8bbwe",
    0x2Bu,
    0x2Au);
  if ( WindowsCompareStringOrdinal(*(HSTRING *)a2, v10.hstr_, &result) >= 0 && !result )
  {
    if ( (*(_BYTE *)(a2 + 64) & 4) == 0 )
      return v2;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HEVCEnc_CodecPack>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HEVCEnc_CodecPack>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)CheckForDX12EncSupport(1) )
        return v2;
      CallStackScopeTrace::CallStackScopeTrace(&v8, "SkipPackagedEncoderHMFT", 2310);
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 0x10u )
      {
        v6 = 51;
        goto LABEL_16;
      }
    }
    else
    {
      CallStackScopeTrace::CallStackScopeTrace(&v8, "SkipPackagedEncoderHMFT", 2305);
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 0x10u )
      {
        v6 = 50;
LABEL_16:
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_aba25f5d0023316200c116552e7e9732_Traceguids);
      }
    }
    v2 = 1;
    CallStackScopeTrace::~CallStackScopeTrace(&v8);
    return v2;
  }
  v10.hstr_ = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v10,
    L"Microsoft.AV1EncoderVideoExtension_8wekyb3d8bbwe",
    0x31u,
    0x30u);
  if ( WindowsCompareStringOrdinal(*(HSTRING *)a2, v10.hstr_, &result) < 0 || result )
    return v2;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AV1Enc_CodecPack>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AV1Enc_CodecPack>::GetImpl'::`2'::impl) )
    return 1;
  v5 = 2;
LABEL_22:
  if ( !(unsigned __int8)CheckForDX12EncSupport(v5) )
    return 1;
  return v2;
}

```

## disassembly

```asm
0x1801478c8  mov     [rsp-8+arg_0], rbx
0x1801478cd  mov     [rsp-8+arg_10], rdi
0x1801478d2  push    rbp
0x1801478d3  mov     rbp, rsp
0x1801478d6  sub     rsp, 50h
0x1801478da  mov     rax, cs:__security_cookie
0x1801478e1  xor     rax, rsp
0x1801478e4  mov     [rbp+var_8], rax
0x1801478e8  mov     rax, [rcx]
0x1801478eb  xor     bl, bl
0x1801478ed  cmp     rax, qword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x1801478f4  mov     rdi, rdx
0x1801478f7  mov     [rbp+result], 0
0x1801478fe  jnz     loc_180147AA9
0x180147904  mov     rax, [rcx+8]
0x180147908  cmp     rax, qword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data4
0x18014790f  jnz     loc_180147AA9
0x180147915  mov     r9d, 30h ; '0'; unsigned int
0x18014791b  mov     [rbp+var_28.hstr_], 0
0x180147923  lea     rdx, aMicrosoftAvcen; "Microsoft.AVCEncoderVideoExtension_8wek"...
0x18014792a  lea     rcx, [rbp+var_28]; this
0x18014792e  lea     r8d, [r9+1]; unsigned int
0x180147932  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180147937  mov     rdx, [rbp+var_28.hstr_]; string2
0x18014793b  lea     r8, [rbp+result]; result
0x18014793f  mov     rcx, [rdi]; string1
0x180147942  call    cs:__imp_WindowsCompareStringOrdinal
0x180147948  test    eax, eax
0x18014794a  js      short loc_18014796D
0x18014794c  cmp     [rbp+result], 0
0x180147950  jnz     short loc_18014796D
0x180147952  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AVCEnc_CodecPack@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AVCEnc_CodecPack@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AVCEnc_CodecPack> `wil::Feature<__WilFeatureTraits_Feature_AVCEnc_CodecPack>::GetImpl(void)'::`2'::impl
0x180147959  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AVCEnc_CodecPack@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AVCEnc_CodecPack>::__private_IsEnabled(void)
0x18014795e  test    al, al
0x180147960  jz      loc_180147AA7
0x180147966  xor     ecx, ecx
0x180147968  jmp     loc_180147A9E
0x18014796d  mov     r9d, 2Ah ; '*'; unsigned int
0x180147973  mov     [rbp+var_28.hstr_], 0
0x18014797b  lea     rdx, aMicrosoftHevcv_1; "Microsoft.HEVCVideoExtension_8wekyb3d8b"...
0x180147982  lea     rcx, [rbp+var_28]; this
0x180147986  lea     r8d, [r9+1]; unsigned int
0x18014798a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18014798f  mov     rdx, [rbp+var_28.hstr_]; string2
0x180147993  lea     r8, [rbp+result]; result
0x180147997  mov     rcx, [rdi]; string1
0x18014799a  call    cs:__imp_WindowsCompareStringOrdinal
0x1801479a0  test    eax, eax
0x1801479a2  js      loc_180147A4C
0x1801479a8  cmp     [rbp+result], 0
0x1801479ac  jnz     loc_180147A4C
0x1801479b2  test    byte ptr [rdi+40h], 4
0x1801479b6  jz      loc_180147AA9
0x1801479bc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HEVCEnc_CodecPack@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HEVCEnc_CodecPack@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HEVCEnc_CodecPack> `wil::Feature<__WilFeatureTraits_Feature_HEVCEnc_CodecPack>::GetImpl(void)'::`2'::impl
0x1801479c3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HEVCEnc_CodecPack@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HEVCEnc_CodecPack>::__private_IsEnabled(void)
0x1801479c8  test    al, al
0x1801479ca  jnz     short loc_1801479F2
0x1801479cc  mov     r8d, 901h; int
0x1801479d2  lea     rdx, aSkippackageden; "SkipPackagedEncoderHMFT"
0x1801479d9  lea     rcx, [rbp+var_30]; this
0x1801479dd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801479e2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x1801479e9  jb      short loc_180147A3F
0x1801479eb  mov     edx, 32h ; '2'
0x1801479f0  jmp     short loc_180147A28
0x1801479f2  mov     ecx, 1
0x1801479f7  call    CheckForDX12EncSupport
0x1801479fc  test    al, al
0x1801479fe  jnz     loc_180147AA9
0x180147a04  mov     r8d, 906h; int
0x180147a0a  lea     rdx, aSkippackageden; "SkipPackagedEncoderHMFT"
0x180147a11  lea     rcx, [rbp+var_30]; this
0x180147a15  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180147a1a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x180147a21  jb      short loc_180147A3F
0x180147a23  mov     edx, 33h ; '3'
0x180147a28  mov     rcx, cs:WPP_GLOBAL_Control
0x180147a2f  lea     r8, WPP_aba25f5d0023316200c116552e7e9732_Traceguids
0x180147a36  mov     rcx, [rcx+10h]
0x180147a3a  call    WPP_SF_
0x180147a3f  lea     rcx, [rbp+var_30]; this
0x180147a43  mov     bl, 1
0x180147a45  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180147a4a  jmp     short loc_180147AA9
0x180147a4c  mov     r9d, 30h ; '0'; unsigned int
0x180147a52  mov     [rbp+var_28.hstr_], 0
0x180147a5a  lea     rdx, aMicrosoftAv1en; "Microsoft.AV1EncoderVideoExtension_8wek"...
0x180147a61  lea     rcx, [rbp+var_28]; this
0x180147a65  lea     r8d, [r9+1]; unsigned int
0x180147a69  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180147a6e  mov     rdx, [rbp+var_28.hstr_]; string2
0x180147a72  lea     r8, [rbp+result]; result
0x180147a76  mov     rcx, [rdi]; string1
0x180147a79  call    cs:__imp_WindowsCompareStringOrdinal
0x180147a7f  test    eax, eax
0x180147a81  js      short loc_180147AA9
0x180147a83  cmp     [rbp+result], 0
0x180147a87  jnz     short loc_180147AA9
0x180147a89  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AV1Enc_CodecPack@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AV1Enc_CodecPack@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AV1Enc_CodecPack> `wil::Feature<__WilFeatureTraits_Feature_AV1Enc_CodecPack>::GetImpl(void)'::`2'::impl
0x180147a90  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AV1Enc_CodecPack@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AV1Enc_CodecPack>::__private_IsEnabled(void)
0x180147a95  test    al, al
0x180147a97  jz      short loc_180147AA7
0x180147a99  mov     ecx, 2
0x180147a9e  call    CheckForDX12EncSupport
0x180147aa3  test    al, al
0x180147aa5  jnz     short loc_180147AA9
0x180147aa7  mov     bl, 1
0x180147aa9  mov     al, bl
0x180147aab  mov     rcx, [rbp+var_8]
0x180147aaf  xor     rcx, rsp; StackCookie
0x180147ab2  call    __security_check_cookie
0x180147ab7  mov     rbx, [rsp+50h+arg_0]
0x180147abc  mov     rdi, [rsp+50h+arg_10]
0x180147ac1  add     rsp, 50h
0x180147ac5  pop     rbp
0x180147ac6  retn
```
