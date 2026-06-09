# TreatmentsProvider::GetStagedVersion(void)

- ea: `0x18005f070`
- end: `0x18005f140`
- name: `?GetStagedVersion@TreatmentsProvider@@UEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800107b0`
- `0x180015af4`
- `0x18005e2f8`
- `0x18005f070`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f0b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f100`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f0b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f100`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005f0de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005f0de`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TreatmentsProvider::GetStagedVersion(__int64 a1, __int64 a2)
{
  _QWORD *v3; // rcx
  __int64 v4; // rdi
  int (__fastcall *v5)(__int64, HSTRING *); // rbx
  HSTRING string; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+50h] [rbp+18h] BYREF

  v3 = (_QWORD *)(a1 + 8);
  if ( !*v3 )
    goto LABEL_5;
  string = 0;
  wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsPayload,wil::err_exception_policy>::query<Windows::Internal::Flighting::OneSettings::IOneSettingsPayload2>(
    v3,
    &v8);
  v4 = v8;
  v5 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v8 + 56LL);
  WindowsDeleteString(string);
  string = 0;
  if ( v5(v4, &string) < 0 )
  {
    wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v8);
    WindowsDeleteString(string);
LABEL_5:
    std::wstring::wstring(a2);
    return a2;
  }
  WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(a2);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v8);
  WindowsDeleteString(string);
  return a2;
}

```

## disassembly

```asm
0x18005f070  mov     rax, rsp
0x18005f073  mov     [rax+10h], rbx
0x18005f077  mov     [rax+20h], rsi
0x18005f07b  push    rdi
0x18005f07c  sub     rsp, 30h
0x18005f080  mov     rsi, rdx
0x18005f083  add     rcx, 8
0x18005f087  cmp     qword ptr [rcx], 0
0x18005f08b  jz      loc_18005F11E
0x18005f091  mov     qword ptr [rax+8], 0
0x18005f099  lea     rdx, [rax+18h]
0x18005f09d  call    ??$query@UIOneSettingsPayload2@OneSettings@Flighting@Internal@Windows@@@?$com_ptr_t@UIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIOneSettingsPayload2@OneSettings@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsPayload,wil::err_exception_policy>::query<Windows::Internal::Flighting::OneSettings::IOneSettingsPayload2>(void)
0x18005f0a2  nop
0x18005f0a3  mov     rdi, [rsp+38h+arg_10]
0x18005f0a8  mov     rax, [rdi]
0x18005f0ab  mov     rbx, [rax+38h]
0x18005f0af  mov     rcx, [rsp+38h+string]; string
0x18005f0b4  call    cs:__imp_WindowsDeleteString
0x18005f0ba  mov     [rsp+38h+string], 0
0x18005f0c3  lea     rdx, [rsp+38h+string]
0x18005f0c8  mov     rcx, rdi
0x18005f0cb  mov     rax, rbx
0x18005f0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f0d3  test    eax, eax
0x18005f0d5  js      short loc_18005F108
0x18005f0d7  xor     edx, edx; length
0x18005f0d9  mov     rcx, [rsp+38h+string]; string
0x18005f0de  call    cs:__imp_WindowsGetStringRawBuffer
0x18005f0e4  mov     rdx, rax
0x18005f0e7  mov     rcx, rsi
0x18005f0ea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005f0ef  nop
0x18005f0f0  lea     rcx, [rsp+38h+arg_10]
0x18005f0f5  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x18005f0fa  nop
0x18005f0fb  mov     rcx, [rsp+38h+string]; string
0x18005f100  call    cs:__imp_WindowsDeleteString
0x18005f106  jmp     short loc_18005F12D
0x18005f108  lea     rcx, [rsp+38h+arg_10]
0x18005f10d  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x18005f112  nop
0x18005f113  mov     rcx, [rsp+38h+string]; string
0x18005f118  call    cs:__imp_WindowsDeleteString
0x18005f11e  lea     rdx, ?cDigitsLut@?1??GetDigitsLut@internal@rapidjson@@YAPEBDXZ@4QBDB+0C8h; ""
0x18005f125  mov     rcx, rsi
0x18005f128  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005f12d  mov     rax, rsi
0x18005f130  mov     rbx, [rsp+38h+arg_8]
0x18005f135  mov     rsi, [rsp+38h+arg_18]
0x18005f13a  add     rsp, 30h
0x18005f13e  pop     rdi
0x18005f13f  retn
```
