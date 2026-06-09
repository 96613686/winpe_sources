# Windows::Internal::ApplicationModel::WindowManagement::IsWindowManagerIDKEnabledForSKU(void)

- ea: `0x1800035b0`
- end: `0x180003758`
- name: `?IsWindowManagerIDKEnabledForSKU@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ`
- size: `424`
- prototype: `bool __fastcall(Windows::Internal::ApplicationModel::WindowManagement *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x1800034f0`

## callees

- `0x1800035b0`
- `0x180003760`
- `0x180003c90`
- `0x180004630`
- `0x18002b980`
- `0x18002b9ec`
- `0x180038324`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000364e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800036c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000364e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800036c8`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800035c8`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800035c8`

## string_xrefs

- `0x1800036ab`: `System\CurrentControlSet\Services\MinShell`
- `0x180003631`: `System\CurrentControlSet\Services\CoreUI`

## pseudocode

```c
char __fastcall Windows::Internal::ApplicationModel::WindowManagement::IsWindowManagerIDKEnabledForSKU(
        Windows::Internal::ApplicationModel::WindowManagement *this)
{
  __int64 v1; // r8
  unsigned int v2; // r9d
  Windows::Internal::ApplicationModel::WindowManagement *v3; // rcx
  char v4; // dl
  bool v5; // al
  int v6; // eax
  char v7; // bl
  __int64 v8; // r8
  __int64 v9; // r9
  int v11; // [rsp+50h] [rbp+8h] BYREF
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+18h] BYREF

  v11 = 17;
  RtlGetDeviceFamilyInfoEnum(0, &v11, 0);
  v3 = (Windows::Internal::ApplicationModel::WindowManagement *)(unsigned int)tls_index;
  v4 = 4;
  if ( __TSS0__1__IsIDKOnXboxEnabled_WindowManagement_ApplicationModel_Internal_Windows__YA_NXZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
  {
    Init_thread_header(&__TSS0__1__IsIDKOnXboxEnabled_WindowManagement_ApplicationModel_Internal_Windows__YA_NXZ_4HA);
    if ( __TSS0__1__IsIDKOnXboxEnabled_WindowManagement_ApplicationModel_Internal_Windows__YA_NXZ_4HA == -1 )
    {
      pvData = 0;
      pcbData = 4;
      v5 = !RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Services\\CoreUI",
              L"IDKOnXbox",
              0xFFFFu,
              0,
              &pvData,
              &pcbData)
        && pvData == 1;
      `Windows::Internal::ApplicationModel::WindowManagement::IsIDKOnXboxEnabled'::`2'::result = v5;
      Init_thread_footer(&__TSS0__1__IsIDKOnXboxEnabled_WindowManagement_ApplicationModel_Internal_Windows__YA_NXZ_4HA);
    }
  }
  v6 = v11;
  v7 = `Windows::Internal::ApplicationModel::WindowManagement::IsIDKOnXboxEnabled'::`2'::result;
  if ( v11 == 16 )
  {
    pvData = 0;
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\MinShell",
           L"IsPresent",
           0xFFFFu,
           0,
           &pvData,
           &pcbData)
      || pvData != 1 )
    {
      goto LABEL_8;
    }
    v6 = v11;
  }
  if ( v6 != 5 && v6 != 11 && v6 != 12 )
  {
    if ( v6 == 10 )
    {
      if ( Windows::Internal::ApplicationModel::WindowManagement::IsIDKOnHoloEnabled(v3) )
        goto LABEL_8;
      v6 = v11;
    }
    if ( v6 != 3 && v6 != 9 )
      return 0;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowManagementIDKOnDesktop>::__private_IsEnabledPreCheck(
      (__int64)`wil::Feature<__WilFeatureTraits_Feature_WindowManagementIDKOnDesktop>::GetImpl'::`2'::impl,
      v4,
      v1,
      v2);
LABEL_8:
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ApplicationActivationWatcher>::__private_IsEnabledPreCheck(
      (__int64)`wil::Feature<__WilFeatureTraits_Feature_ApplicationActivationWatcher>::GetImpl'::`2'::impl,
      v4,
      v1,
      v2);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RequestFromAppModelWatcher>::ReportUsage(
      (__int64)`wil::Feature<__WilFeatureTraits_Feature_RequestFromAppModelWatcher>::GetImpl'::`2'::impl,
      1u,
      v8,
      v9);
    return 1;
  }
  if ( v7 )
    goto LABEL_8;
  return 0;
}

```

## disassembly

```asm
0x1800035b0  push    rbx
0x1800035b2  sub     rsp, 40h
0x1800035b6  xor     r8d, r8d
0x1800035b9  mov     [rsp+48h+arg_0], 11h
0x1800035c1  lea     rdx, [rsp+48h+arg_0]
0x1800035c6  xor     ecx, ecx
0x1800035c8  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800035ce  mov     ecx, cs:_tls_index
0x1800035d4  mov     rax, gs:58h
0x1800035dd  mov     edx, 4
0x1800035e2  mov     rax, [rax+rcx*8]
0x1800035e6  mov     eax, [rdx+rax]
0x1800035e9  cmp     cs:?$TSS0@?1??IsIDKOnXboxEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ@4HA, eax
0x1800035ef  jle     short loc_180003670
0x1800035f1  lea     rcx, ?$TSS0@?1??IsIDKOnXboxEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ@4HA
0x1800035f8  call    _Init_thread_header
0x1800035fd  cmp     cs:?$TSS0@?1??IsIDKOnXboxEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ@4HA, 0FFFFFFFFh
0x180003604  jnz     short loc_180003670
0x180003606  lea     rax, [rsp+48h+arg_10]
0x18000360b  mov     [rsp+48h+arg_8], 0
0x180003613  mov     [rsp+48h+pcbData], rax; pcbData
0x180003618  lea     r8, Value; "IDKOnXbox"
0x18000361f  lea     rax, [rsp+48h+arg_8]
0x180003624  mov     [rsp+48h+arg_10], 4
0x18000362c  mov     [rsp+48h+pvData], rax; pvData
0x180003631  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Co"...
0x180003638  mov     r9d, 0FFFFh; dwFlags
0x18000363e  mov     [rsp+48h+pdwType], 0; pdwType
0x180003647  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000364e  call    cs:__imp_RegGetValueW
0x180003654  test    eax, eax
0x180003656  jz      loc_18000371B
0x18000365c  xor     al, al
0x18000365e  lea     rcx, ?$TSS0@?1??IsIDKOnXboxEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ@4HA
0x180003665  mov     cs:?result@?1??IsIDKOnXboxEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ@4_NA, al; bool `Windows::Internal::ApplicationModel::WindowManagement::IsIDKOnXboxEnabled(void)'::`2'::result
0x18000366b  call    _Init_thread_footer
0x180003670  mov     eax, [rsp+48h+arg_0]
0x180003674  movzx   ebx, cs:?result@?1??IsIDKOnXboxEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ@4_NA; bool `Windows::Internal::ApplicationModel::WindowManagement::IsIDKOnXboxEnabled(void)'::`2'::result
0x18000367b  cmp     eax, 10h
0x18000367e  jnz     short loc_1800036F4
0x180003680  lea     rax, [rsp+48h+arg_10]
0x180003685  mov     [rsp+48h+arg_8], 0
0x18000368d  mov     [rsp+48h+pcbData], rax; pcbData
0x180003692  lea     r8, aIspresent; "IsPresent"
0x180003699  lea     rax, [rsp+48h+arg_8]
0x18000369e  mov     [rsp+48h+arg_10], 4
0x1800036a6  mov     [rsp+48h+pvData], rax; pvData
0x1800036ab  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Mi"...
0x1800036b2  mov     r9d, 0FFFFh; dwFlags
0x1800036b8  mov     [rsp+48h+pdwType], 0; pdwType
0x1800036c1  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800036c8  call    cs:__imp_RegGetValueW
0x1800036ce  test    eax, eax
0x1800036d0  jz      short loc_18000372D
0x1800036d2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ApplicationActivationWatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ApplicationActivationWatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ApplicationActivationWatcher> `wil::Feature<__WilFeatureTraits_Feature_ApplicationActivationWatcher>::GetImpl(void)'::`2'::impl
0x1800036d9  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_ApplicationActivationWatcher@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ApplicationActivationWatcher>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x1800036de  mov     dl, 1
0x1800036e0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RequestFromAppModelWatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RequestFromAppModelWatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RequestFromAppModelWatcher> `wil::Feature<__WilFeatureTraits_Feature_RequestFromAppModelWatcher>::GetImpl(void)'::`2'::impl
0x1800036e7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RequestFromAppModelWatcher@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RequestFromAppModelWatcher>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800036ec  mov     al, 1
0x1800036ee  add     rsp, 40h
0x1800036f2  pop     rbx
0x1800036f3  retn
0x1800036f4  cmp     eax, 5
0x1800036f7  jz      short loc_18000373A
0x1800036f9  cmp     eax, 0Bh
0x1800036fc  jz      short loc_18000373A
0x1800036fe  cmp     eax, 0Ch
0x180003701  jz      short loc_18000373A
0x180003703  cmp     eax, 0Ah
0x180003706  jz      short loc_180003740
0x180003708  cmp     eax, 3
0x18000370b  jnz     short loc_18000374F
0x18000370d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowManagementIDKOnDesktop@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowManagementIDKOnDesktop@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowManagementIDKOnDesktop> `wil::Feature<__WilFeatureTraits_Feature_WindowManagementIDKOnDesktop>::GetImpl(void)'::`2'::impl
0x180003714  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowManagementIDKOnDesktop@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowManagementIDKOnDesktop>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180003719  jmp     short loc_1800036D2
0x18000371b  cmp     [rsp+48h+arg_8], 1
0x180003720  jnz     loc_18000365C
0x180003726  mov     al, 1
0x180003728  jmp     loc_18000365E
0x18000372d  cmp     [rsp+48h+arg_8], 1
0x180003732  jnz     short loc_1800036D2
0x180003734  mov     eax, [rsp+48h+arg_0]
0x180003738  jmp     short loc_1800036F4
0x18000373a  test    bl, bl
0x18000373c  jnz     short loc_1800036D2
0x18000373e  jmp     short loc_180003754
0x180003740  call    ?IsIDKOnHoloEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ; Windows::Internal::ApplicationModel::WindowManagement::IsIDKOnHoloEnabled(void)
0x180003745  test    al, al
0x180003747  jnz     short loc_1800036D2
0x180003749  mov     eax, [rsp+48h+arg_0]
0x18000374d  jmp     short loc_180003708
0x18000374f  cmp     eax, 9
0x180003752  jz      short loc_18000370D
0x180003754  xor     al, al
0x180003756  jmp     short loc_1800036EE
```
