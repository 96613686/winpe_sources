# FeatureTuningOneSettingsProvider::SetFlightIdFromJson(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &,std::unique_ptr<TuningFlightInfo,std::default_delete<TuningFlightInfo>> &)

- ea: `0x18008424c`
- end: `0x18008440e`
- name: `?SetFlightIdFromJson@FeatureTuningOneSettingsProvider@@CA?AV?$unique_ptr@UTuningFlightInfo@@U?$default_delete@UTuningFlightInfo@@@std@@@std@@AEBV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAV23@@Z`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180082d0c`

## callees

- `0x180003220`
- `0x180005898`
- `0x180010450`
- `0x1800109ac`
- `0x180015af4`
- `0x180016b30`
- `0x180019704`
- `0x180019890`
- `0x180068c1c`
- `0x18008424c`
- `0x180085d78`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084289`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084380`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084289`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084380`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800842d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800842d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall FeatureTuningOneSettingsProvider::SetFlightIdFromJson(_QWORD *a1, __int64 *a2, _QWORD *a3)
{
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  _DWORD *v12; // rdx
  _DWORD *v13; // rcx
  unsigned int v15; // eax
  int v16; // [rsp+20h] [rbp-60h] BYREF
  HSTRING string[2]; // [rsp+28h] [rbp-58h] BYREF
  _OWORD v18[2]; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v19[32]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  string[0] = 0;
  v5 = *a2;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a2 + 80LL);
  WindowsDeleteString(0);
  string[0] = 0;
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v19, off_1800BDDE0);
  v8 = v6(v5, *(_QWORD *)(v7 + 24), string);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featuretuning\\FeatureTuningOneSettingsProvider.h",
      (const char *)(unsigned int)v8,
      v16);
  if ( !string[0] )
  {
    v15 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featuretuning\\FeatureTuningOneSettingsProvider.h",
      (const char *)v15,
      v16);
  }
  WindowsGetStringRawBuffer(string[0], 0);
  v9 = std::wstring::wstring(v19);
  std::wstring::operator=(*a3 + 8LL, v9);
  std::wstring::_Tidy_deallocate(v19, v10);
  v18[0] = 0;
  v18[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v18[0]) = 0;
  v16 = 0;
  v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*a3 + 8LL);
  if ( !(unsigned __int8)FlightIdUtils::TryParseFlightId(v11, v18, &v16) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featuretuning\\FeatureTuningOneSettingsProvider.h",
      (const char *)0x80004005LL,
      v16);
  if ( (unsigned int)std::wstring::compare(v18, L"FT") )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featuretuning\\FeatureTuningOneSettingsProvider.h",
      (const char *)0x8000FFFFLL,
      v16);
  v12 = (_DWORD *)*a3;
  *v12 = v16;
  v13 = (_DWORD *)*a3;
  *a3 = 0;
  *a1 = v13;
  std::wstring::_Tidy_deallocate(v18, v12);
  WindowsDeleteString(string[0]);
  return a1;
}

```

## disassembly

```asm
0x18008424c  push    rbp
0x18008424e  push    rbx
0x18008424f  push    rsi
0x180084250  push    rdi
0x180084251  push    r14
0x180084253  mov     rbp, rsp
0x180084256  sub     rsp, 80h
0x18008425d  mov     rax, cs:__security_cookie
0x180084264  xor     rax, rsp
0x180084267  mov     [rbp+var_8], rax
0x18008426b  mov     rsi, r8
0x18008426e  mov     r14, rcx
0x180084271  mov     [rbp+string], rcx
0x180084275  mov     [rbp+string], 0
0x18008427d  mov     rdi, [rdx]
0x180084280  mov     rax, [rdi]
0x180084283  mov     rbx, [rax+50h]
0x180084287  xor     ecx, ecx; string
0x180084289  call    cs:__imp_WindowsDeleteString
0x18008428f  mov     [rbp+string], 0
0x180084297  lea     rdx, off_1800BDDE0; "__flightId"
0x18008429e  lea     rcx, [rbp+var_28]
0x1800842a2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800842a7  nop
0x1800842a8  lea     r8, [rbp+string]
0x1800842ac  mov     rdx, [rax+18h]
0x1800842b0  mov     rcx, rdi
0x1800842b3  mov     rax, rbx
0x1800842b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800842bb  mov     rcx, [rbp+28h]; this
0x1800842bf  test    eax, eax
0x1800842c1  js      loc_1800843BE
0x1800842c7  mov     rcx, [rbp+string]; string
0x1800842cb  test    rcx, rcx
0x1800842ce  jz      loc_1800843D3
0x1800842d4  xor     edx, edx; length
0x1800842d6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800842dc  mov     rdx, rax
0x1800842df  lea     rcx, [rbp+var_28]
0x1800842e3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800842e8  mov     rcx, [rsi]
0x1800842eb  add     rcx, 8
0x1800842ef  mov     rdx, rax
0x1800842f2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800842f7  lea     rcx, [rbp+var_28]
0x1800842fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180084300  xorps   xmm0, xmm0
0x180084303  movups  [rbp+var_48], xmm0
0x180084307  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18008430f  movdqu  [rbp+var_38], xmm1
0x180084314  xor     eax, eax
0x180084316  mov     word ptr [rbp+var_48], ax
0x18008431a  mov     [rbp+var_60], eax
0x18008431d  mov     rcx, [rsi]
0x180084320  add     rcx, 8
0x180084324  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180084329  lea     r8, [rbp+var_60]
0x18008432d  lea     rdx, [rbp+var_48]
0x180084331  mov     rcx, rax
0x180084334  call    ?TryParseFlightId@FlightIdUtils@@YA_NPEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAK@Z; FlightIdUtils::TryParseFlightId(ushort const *,std::wstring *,ulong *)
0x180084339  mov     rcx, [rbp+28h]; this
0x18008433d  test    al, al
0x18008433f  jz      loc_1800843F6
0x180084345  mov     rbx, [rbp+28h]
0x180084349  lea     rdx, aFt; "FT"
0x180084350  lea     rcx, [rbp+var_48]
0x180084354  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x180084359  test    eax, eax
0x18008435b  jnz     short loc_1800843A3
0x18008435d  mov     rdx, [rsi]
0x180084360  mov     ecx, [rbp+var_60]
0x180084363  mov     [rdx], ecx
0x180084365  mov     rcx, [rsi]
0x180084368  mov     qword ptr [rsi], 0
0x18008436f  mov     [r14], rcx
0x180084372  lea     rcx, [rbp+var_48]
0x180084376  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008437b  nop
0x18008437c  mov     rcx, [rbp+string]; string
0x180084380  call    cs:__imp_WindowsDeleteString
0x180084386  mov     rax, r14
0x180084389  mov     rcx, [rbp+var_8]
0x18008438d  xor     rcx, rsp; StackCookie
0x180084390  call    __security_check_cookie
0x180084395  add     rsp, 80h
0x18008439c  pop     r14
0x18008439e  pop     rdi
0x18008439f  pop     rsi
0x1800843a0  pop     rbx
0x1800843a1  pop     rbp
0x1800843a2  retn
0x1800843a3  mov     r9d, 8000FFFFh; char *
0x1800843a9  lea     r8, aOnecoreBaseFli_47; "onecore\\base\\flighting\\featuremanage"...
0x1800843b0  mov     edx, 10Dh; void *
0x1800843b5  mov     rcx, rbx; this
0x1800843b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800843be  mov     r9d, eax; char *
0x1800843c1  lea     r8, aOnecoreBaseFli_47; "onecore\\base\\flighting\\featuremanage"...
0x1800843c8  mov     edx, 101h; void *
0x1800843cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800843d3  mov     ecx, 80070057h
0x1800843d8  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800843dd  mov     r9d, eax; char *
0x1800843e0  mov     rcx, [rbp+28h]; this
0x1800843e4  lea     r8, aOnecoreBaseFli_47; "onecore\\base\\flighting\\featuremanage"...
0x1800843eb  mov     edx, 105h; void *
0x1800843f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800843f6  mov     r9d, 80004005h; char *
0x1800843fc  lea     r8, aOnecoreBaseFli_47; "onecore\\base\\flighting\\featuremanage"...
0x180084403  mov     edx, 10Ch; void *
0x180084408  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
