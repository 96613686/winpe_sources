# CloudExperienceHostAPI::SnapshotCapture::IsPackageAvailable(uchar *)

- ea: `0x180032d30`
- end: `0x180032dc2`
- name: `?IsPackageAvailable@SnapshotCapture@CloudExperienceHostAPI@@UEAAJPEAE@Z`
- size: `146`
- prototype: `__int64 __fastcall(CloudExperienceHostAPI::SnapshotCapture *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180009834`
- `0x180031b78`
- `0x180032d30`
- `0x1800333b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032d90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032d90`

## string_xrefs

- `0x180032d61`: `Software\Microsoft\Windows\CurrentVersion\Shell\Update\Packages\MicrosoftWindows.Client.AIX_cw5n1h2txyewy`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::SnapshotCapture::IsPackageAvailable(
        CloudExperienceHostAPI::SnapshotCapture *this,
        unsigned __int8 *a2)
{
  unsigned __int8 *v2; // rdi
  LSTATUS v3; // ebx
  __int64 *v5; // [rsp+30h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-20h] BYREF
  char v7; // [rsp+40h] [rbp-18h]
  __int64 v8; // [rsp+68h] [rbp+10h] BYREF

  v2 = a2;
  *a2 = 0;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_53188129>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_53188129>::GetImpl'::`2'::impl,
    a2);
  v8 = 0;
  v5 = &v8;
  phkResult = 0;
  v7 = 1;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell\\Update\\Packages\\MicrosoftWindows.Client.AIX_cw5n1h2txyewy",
         0,
         0x20019u,
         &phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v5);
  if ( !v3 )
    *v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v8);
  return 0;
}

```

## disassembly

```asm
0x180032d30  mov     [rsp+arg_0], rbx
0x180032d35  push    rdi
0x180032d36  sub     rsp, 50h
0x180032d3a  mov     rdi, rdx
0x180032d3d  mov     byte ptr [rdx], 0
0x180032d40  mov     dl, 1
0x180032d42  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53188129@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53188129@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53188129> `wil::Feature<__WilFeatureTraits_Feature_53188129>::GetImpl(void)'::`2'::impl
0x180032d49  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_53188129@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53188129>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180032d4e  lea     rax, [rsp+58h+arg_8]
0x180032d53  mov     [rsp+58h+arg_8], 0
0x180032d5c  mov     [rsp+58h+var_28], rax
0x180032d61  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180032d68  lea     rax, [rsp+58h+var_20]
0x180032d6d  mov     [rsp+58h+var_20], 0
0x180032d76  mov     r9d, 20019h; samDesired
0x180032d7c  mov     [rsp+58h+phkResult], rax; phkResult
0x180032d81  xor     r8d, r8d; ulOptions
0x180032d84  mov     [rsp+58h+var_18], 1
0x180032d89  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032d90  call    cs:__imp_RegOpenKeyExW
0x180032d96  lea     rcx, [rsp+58h+var_28]
0x180032d9b  mov     ebx, eax
0x180032d9d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180032da2  lea     rcx, [rsp+58h+arg_8]
0x180032da7  test    ebx, ebx
0x180032da9  jnz     short loc_180032DAE
0x180032dab  mov     byte ptr [rdi], 1
0x180032dae  xor     ebx, ebx
0x180032db0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180032db5  mov     eax, ebx
0x180032db7  mov     rbx, [rsp+58h+arg_0]
0x180032dbc  add     rsp, 50h
0x180032dc0  pop     rdi
0x180032dc1  retn
```
