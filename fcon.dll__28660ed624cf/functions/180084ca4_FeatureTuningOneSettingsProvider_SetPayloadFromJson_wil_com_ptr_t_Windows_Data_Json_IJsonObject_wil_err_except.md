# FeatureTuningOneSettingsProvider::SetPayloadFromJson(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &,std::unique_ptr<TuningFlightInfo,std::default_delete<TuningFlightInfo>> &)

- ea: `0x180084ca4`
- end: `0x180084ee1`
- name: `?SetPayloadFromJson@FeatureTuningOneSettingsProvider@@CA?AV?$unique_ptr@UTuningFlightInfo@@U?$default_delete@UTuningFlightInfo@@@std@@@std@@AEBV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAV23@@Z`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180082d0c`

## callees

- `0x180003220`
- `0x180010450`
- `0x1800107b0`
- `0x1800109ac`
- `0x180015af4`
- `0x180019704`
- `0x180019850`
- `0x180019890`
- `0x180081120`
- `0x180081434`
- `0x180084ca4`
- `0x180086dc8`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084d72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084e54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084d72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084e54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180084da4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180084da4`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall FeatureTuningOneSettingsProvider::SetPayloadFromJson(_QWORD *a1, __int64 *a2, _QWORD *a3)
{
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, int *); // rbx
  __int64 v7; // rax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  __int64 v13; // rax
  __int128 *v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v18[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING string[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v21; // [rsp+40h] [rbp-C0h] BYREF
  __m128i si128; // [rsp+50h] [rbp-B0h]
  _BYTE v23[16]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h]
  _BYTE v25[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v26[128]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  *(_QWORD *)v18 = 0;
  v5 = *a2;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)*a2 + 48LL);
  *(_QWORD *)v18 = 0;
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
         v25,
         &FeatureTuningOneSettingsProvider::c_FTunePayloadKey);
  v8 = v6(v5, *(_QWORD *)(v7 + 24), v18);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featuretuning\\FeatureTuningOneSettingsProvider.h",
      (const char *)(unsigned int)v8,
      v18[0]);
  v19 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v18 + 48LL))(*(_QWORD *)v18, &v19);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featuretuning\\FeatureTuningOneSettingsProvider.h",
      (const char *)(unsigned int)v9,
      v18[0]);
  if ( v19 != 5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11A,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featuretuning\\FeatureTuningOneSettingsProvider.h",
      (const char *)0x8000FFFFLL,
      v18[0]);
  string[0] = 0;
  v10 = *(_QWORD *)v18;
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v18 + 56LL);
  WindowsDeleteString(0);
  string[0] = 0;
  v12 = v11(v10, string);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featuretuning\\FeatureTuningOneSettingsProvider.h",
      (const char *)(unsigned int)v12,
      v18[0]);
  WindowsGetStringRawBuffer(string[0], 0);
  std::wstring::wstring(v23);
  std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v26);
  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
  std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
    v26,
    &v21,
    v13,
    v13 + 2 * v24);
  std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v26);
  v14 = (__int128 *)(*a3 + 40LL);
  if ( v14 != &v21 )
  {
    std::string::_Tidy_deallocate(*a3 + 40LL);
    *v14 = v21;
    v14[1] = (__int128)si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v21) = 0;
  }
  std::string::_Tidy_deallocate(&v21);
  v15 = *a3;
  *a3 = 0;
  *a1 = v15;
  std::wstring::_Tidy_deallocate(v23, v16);
  WindowsDeleteString(string[0]);
  string[0] = 0;
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(v18);
  return a1;
}

```

## disassembly

```asm
0x180084ca4  push    rbp
0x180084ca6  push    rbx
0x180084ca7  push    rsi
0x180084ca8  push    rdi
0x180084ca9  push    r14
0x180084cab  lea     rbp, [rsp-30h]
0x180084cb0  sub     rsp, 130h
0x180084cb7  mov     rax, cs:__security_cookie
0x180084cbe  xor     rax, rsp
0x180084cc1  mov     [rbp+50h+var_30], rax
0x180084cc5  mov     rsi, r8
0x180084cc8  mov     r14, rcx
0x180084ccb  mov     qword ptr [rsp+150h+var_130], rcx
0x180084cd0  mov     qword ptr [rsp+150h+var_130], 0
0x180084cd9  mov     rdi, [rdx]
0x180084cdc  mov     rax, [rdi]
0x180084cdf  mov     rbx, [rax+30h]
0x180084ce3  mov     qword ptr [rsp+150h+var_130], 0; int
0x180084cec  lea     rdx, ?c_FTunePayloadKey@FeatureTuningOneSettingsProvider@@0QEBGEB; ushort const * const FeatureTuningOneSettingsProvider::c_FTunePayloadKey
0x180084cf3  lea     rcx, [rbp+50h+var_D0]
0x180084cf7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180084cfc  nop
0x180084cfd  lea     r8, [rsp+150h+var_130]
0x180084d02  mov     rdx, [rax+18h]
0x180084d06  mov     rcx, rdi
0x180084d09  mov     rax, rbx
0x180084d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084d11  mov     rcx, [rbp+58h]; this
0x180084d15  test    eax, eax
0x180084d17  js      loc_180084E9F
0x180084d1d  mov     [rsp+150h+var_128], 0
0x180084d25  mov     rcx, qword ptr [rsp+150h+var_130]
0x180084d2a  mov     rax, [rcx]
0x180084d2d  lea     rdx, [rsp+150h+var_128]
0x180084d32  mov     rax, [rax+30h]
0x180084d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084d3b  mov     rcx, [rbp+58h]; this
0x180084d3f  test    eax, eax
0x180084d41  js      loc_180084EB4
0x180084d47  cmp     [rsp+150h+var_128], 5
0x180084d4c  setz    al
0x180084d4f  mov     rcx, [rbp+58h]; this
0x180084d53  test    al, al
0x180084d55  jz      loc_180084EC9
0x180084d5b  mov     [rsp+150h+string], 0
0x180084d64  mov     rdi, qword ptr [rsp+150h+var_130]
0x180084d69  mov     rax, [rdi]
0x180084d6c  mov     rbx, [rax+38h]
0x180084d70  xor     ecx, ecx; string
0x180084d72  call    cs:__imp_WindowsDeleteString
0x180084d78  mov     [rsp+150h+string], 0
0x180084d81  lea     rdx, [rsp+150h+string]
0x180084d86  mov     rcx, rdi
0x180084d89  mov     rax, rbx
0x180084d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084d91  mov     rcx, [rbp+58h]; this
0x180084d95  test    eax, eax
0x180084d97  js      loc_180084E8A
0x180084d9d  xor     edx, edx; length
0x180084d9f  mov     rcx, [rsp+150h+string]; string
0x180084da4  call    cs:__imp_WindowsGetStringRawBuffer
0x180084daa  mov     rdx, rax
0x180084dad  lea     rcx, [rsp+150h+var_F0]
0x180084db2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180084db7  nop
0x180084db8  lea     rcx, [rbp+50h+var_B0]
0x180084dbc  call    ??0?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180084dc1  nop
0x180084dc2  lea     rcx, [rsp+150h+var_F0]
0x180084dc7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180084dcc  mov     r8, rax
0x180084dcf  mov     rax, [rsp+150h+var_E0]
0x180084dd4  lea     r9, [r8+rax*2]
0x180084dd8  lea     rdx, [rsp+150h+var_110]
0x180084ddd  lea     rcx, [rbp+50h+var_B0]
0x180084de1  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x180084de6  nop
0x180084de7  lea     rcx, [rbp+50h+var_B0]
0x180084deb  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180084df0  mov     rbx, [rsi]
0x180084df3  add     rbx, 28h ; '('
0x180084df7  lea     rax, [rsp+150h+var_110]
0x180084dfc  cmp     rbx, rax
0x180084dff  jz      short loc_180084E2D
0x180084e01  mov     rcx, rbx
0x180084e04  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180084e09  movups  xmm0, [rsp+150h+var_110]
0x180084e0e  movups  xmmword ptr [rbx], xmm0
0x180084e11  movups  xmm1, [rsp+150h+var_100]
0x180084e16  movups  xmmword ptr [rbx+10h], xmm1
0x180084e1a  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180084e22  movdqu  [rsp+150h+var_100], xmm0
0x180084e28  mov     byte ptr [rsp+150h+var_110], 0
0x180084e2d  lea     rcx, [rsp+150h+var_110]
0x180084e32  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180084e37  mov     rcx, [rsi]
0x180084e3a  mov     qword ptr [rsi], 0
0x180084e41  mov     [r14], rcx
0x180084e44  lea     rcx, [rsp+150h+var_F0]
0x180084e49  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180084e4e  nop
0x180084e4f  mov     rcx, [rsp+150h+string]; string
0x180084e54  call    cs:__imp_WindowsDeleteString
0x180084e5a  mov     [rsp+150h+string], 0
0x180084e63  lea     rcx, [rsp+150h+var_130]
0x180084e68  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180084e6d  mov     rax, r14
0x180084e70  mov     rcx, [rbp+50h+var_30]
0x180084e74  xor     rcx, rsp; StackCookie
0x180084e77  call    __security_check_cookie
0x180084e7c  add     rsp, 130h
0x180084e83  pop     r14
0x180084e85  pop     rdi
0x180084e86  pop     rsi
0x180084e87  pop     rbx
0x180084e88  pop     rbp
0x180084e89  retn
0x180084e8a  mov     r9d, eax; char *
0x180084e8d  lea     r8, aOnecoreBaseFli_47; "onecore\\base\\flighting\\featuremanage"...
0x180084e94  mov     edx, 11Dh; void *
0x180084e99  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180084e9f  mov     r9d, eax; char *
0x180084ea2  lea     r8, aOnecoreBaseFli_47; "onecore\\base\\flighting\\featuremanage"...
0x180084ea9  mov     edx, 117h; void *
0x180084eae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180084eb4  mov     r9d, eax; char *
0x180084eb7  lea     r8, aOnecoreBaseFli_47; "onecore\\base\\flighting\\featuremanage"...
0x180084ebe  mov     edx, 119h; void *
0x180084ec3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180084ec9  mov     r9d, 8000FFFFh; char *
0x180084ecf  lea     r8, aOnecoreBaseFli_47; "onecore\\base\\flighting\\featuremanage"...
0x180084ed6  mov     edx, 11Ah; void *
0x180084edb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
