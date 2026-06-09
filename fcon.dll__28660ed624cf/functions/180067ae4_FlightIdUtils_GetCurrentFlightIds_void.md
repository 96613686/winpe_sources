# FlightIdUtils::GetCurrentFlightIds(void)

- ea: `0x180067ae4`
- end: `0x180067c48`
- name: `?GetCurrentFlightIds@FlightIdUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180067888`

## callees

- `0x180003220`
- `0x1800107b0`
- `0x1800109ac`
- `0x1800120a0`
- `0x180015a74`
- `0x180015b6c`
- `0x180019890`
- `0x18001c070`
- `0x180067ae4`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180067b2e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180067b2e`

## string_xrefs

- `0x180067b3f`: `onecore\base\flighting\common\inc\FlightIdUtility.h`
- `0x180067b80`: `onecore\base\flighting\common\inc\FlightIdUtility.h`
- `0x180067bc4`: `onecore\base\flighting\common\inc\FlightIdUtility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall FlightIdUtils::GetCurrentFlightIds(__int64 a1)
{
  HRESULT v2; // eax
  __int64 v3; // rax
  int v4; // eax
  int v5; // eax
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  int ppv; // [rsp+20h] [rbp-60h]
  int v11; // [rsp+30h] [rbp-50h] BYREF
  __int64 v12; // [rsp+38h] [rbp-48h] BYREF
  LPVOID v13; // [rsp+40h] [rbp-40h] BYREF
  __int64 v14; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v15[32]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v14 = a1;
  v13 = 0;
  v2 = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, &v13);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
      (const char *)(unsigned int)v2,
      ppv);
  v12 = 0;
  v3 = *(_QWORD *)v13;
  v12 = 0;
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(v3 + 32))(v13, &v12);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
      (const char *)(unsigned int)v4,
      ppv);
  v14 = 0;
  v11 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *, int *))(*(_QWORD *)v12 + 32LL))(v12, &v14, &v11);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
      (const char *)(unsigned int)v5,
      ppv);
  std::wstring::wstring(v15);
  if ( v11 )
  {
    v6 = std::_WChar_traits<unsigned short>::length(v14);
    std::wstring::_Assign<unsigned short>(v15, v7, v6);
  }
  std::wstring::wstring(a1, v15);
  std::wstring::_Tidy_deallocate(v15, v8);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v12);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v13);
  return a1;
}

```

## disassembly

```asm
0x180067ae4  mov     [rsp-8+arg_8], rbx
0x180067ae9  push    rbp
0x180067aea  mov     rbp, rsp
0x180067aed  sub     rsp, 80h
0x180067af4  mov     rax, cs:__security_cookie
0x180067afb  xor     rax, rsp
0x180067afe  mov     [rbp+var_8], rax
0x180067b02  mov     rbx, rcx
0x180067b05  mov     [rbp+var_38], rcx
0x180067b09  mov     [rbp+var_40], 0
0x180067b11  lea     rax, [rbp+var_40]
0x180067b15  mov     qword ptr [rsp+80h+ppv], rax; int
0x180067b1a  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x180067b21  xor     edx, edx; pUnkOuter
0x180067b23  lea     r8d, [rdx+1]; dwClsContext
0x180067b27  lea     rcx, CLSID_FlightClientAPI; rclsid
0x180067b2e  call    cs:__imp_CoCreateInstance
0x180067b34  mov     rcx, [rbp+8]; this
0x180067b38  test    eax, eax
0x180067b3a  jns     short loc_180067B51
0x180067b3c  mov     r9d, eax; char *
0x180067b3f  lea     r8, aOnecoreBaseFli_46; "onecore\\base\\flighting\\common\\inc\\"...
0x180067b46  mov     edx, 7Fh; void *
0x180067b4b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067b51  mov     [rbp+var_48], 0
0x180067b59  mov     rcx, [rbp+var_40]
0x180067b5d  mov     rax, [rcx]
0x180067b60  mov     [rbp+var_48], 0
0x180067b68  lea     rdx, [rbp+var_48]
0x180067b6c  mov     rax, [rax+20h]
0x180067b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b75  mov     rcx, [rbp+8]; this
0x180067b79  test    eax, eax
0x180067b7b  jns     short loc_180067B92
0x180067b7d  mov     r9d, eax; char *
0x180067b80  lea     r8, aOnecoreBaseFli_46; "onecore\\base\\flighting\\common\\inc\\"...
0x180067b87  mov     edx, 82h; void *
0x180067b8c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067b92  mov     [rbp+var_38], 0
0x180067b9a  mov     [rbp+var_50], 0
0x180067ba1  mov     rcx, [rbp+var_48]
0x180067ba5  mov     rax, [rcx]
0x180067ba8  lea     r8, [rbp+var_50]
0x180067bac  lea     rdx, [rbp+var_38]
0x180067bb0  mov     rax, [rax+20h]
0x180067bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067bb9  mov     rcx, [rbp+8]; this
0x180067bbd  test    eax, eax
0x180067bbf  jns     short loc_180067BD6
0x180067bc1  mov     r9d, eax; char *
0x180067bc4  lea     r8, aOnecoreBaseFli_46; "onecore\\base\\flighting\\common\\inc\\"...
0x180067bcb  mov     edx, 86h; void *
0x180067bd0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067bd6  lea     rcx, [rbp+var_28]
0x180067bda  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180067bdf  nop
0x180067be0  cmp     [rbp+var_50], 0
0x180067be4  jbe     short loc_180067BFE
0x180067be6  mov     rcx, [rbp+var_38]
0x180067bea  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180067bef  mov     r8, rax
0x180067bf2  mov     rdx, rcx
0x180067bf5  lea     rcx, [rbp+var_28]
0x180067bf9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180067bfe  lea     rdx, [rbp+var_28]
0x180067c02  mov     rcx, rbx
0x180067c05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180067c0a  nop
0x180067c0b  lea     rcx, [rbp+var_28]
0x180067c0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180067c14  nop
0x180067c15  lea     rcx, [rbp+var_48]
0x180067c19  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180067c1e  nop
0x180067c1f  lea     rcx, [rbp+var_40]
0x180067c23  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180067c28  mov     rax, rbx
0x180067c2b  mov     rcx, [rbp+var_8]
0x180067c2f  xor     rcx, rsp; StackCookie
0x180067c32  call    __security_check_cookie
0x180067c37  mov     rbx, [rsp+80h+arg_8]
0x180067c3f  add     rsp, 80h
0x180067c46  pop     rbp
0x180067c47  retn
```
