# MdmLogCollector::CollectDynamicAreaInfo(ushort const *)

- ea: `0x18010a670`
- end: `0x18010a8ff`
- name: `?CollectDynamicAreaInfo@MdmLogCollector@@AEAAJPEBG@Z`
- size: `655`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180108be4`

## callees

- `0x1800ece5c`
- `0x1800ef134`
- `0x180108bc0`
- `0x180109400`
- `0x1801095b0`
- `0x180109760`
- `0x180109bfc`
- `0x18010a4a0`
- `0x18010a670`
- `0x18010b4d8`
- `0x18010c014`
- `0x18010cf98`
- `0x18010d45c`
- `0x18010da60`
- `0x18010de78`
- `0x18010efa4`
- `0x1801111ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010a68a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010a78e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010a7e6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010a819`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010a8bc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010a68a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010a78e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010a7e6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010a819`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010a8bc`

## string_xrefs

- `0x18010a6ac`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a6d1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a6f6`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a71b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a740`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a7ac`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a83b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a860`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a88e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a8df`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a871`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`

## pseudocode

```c
__int64 __fastcall MdmLogCollector::CollectDynamicAreaInfo(MdmLogCollector *this, const unsigned __int16 *a2)
{
  int v4; // eax
  int v5; // eax
  int DeviceHardwareData; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  const char *v10; // r9
  int v11; // eax
  wil::details::in1diag3 *v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // ebx
  unsigned __int64 v19; // r9
  __int64 result; // rax
  int v21; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = _o__wcsicmp(a2, L"Autopilot");
  try
  {
    if ( v4 )
    {
      if ( (unsigned int)_o__wcsicmp(a2, L"Tpm") )
      {
        if ( (unsigned int)_o__wcsicmp(a2, L"OneTrace") )
        {
          if ( !(unsigned int)_o__wcsicmp(a2, L"DeviceEnrollment") )
          {
            v15 = MdmLogCollector::CollectWifiLogs(this);
            if ( v15 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x8CA,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                (const char *)(unsigned int)v15,
                v21);
            v16 = MdmLogCollector::CollectDsregLog(this);
            if ( v16 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x8CB,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                (const char *)(unsigned int)v16,
                v21);
            v17 = MdmLogCollector::AddHklmRegEntry(
                    this,
                    L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy");
            v18 = v17;
            if ( v17 < 0 )
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x99B,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                (const char *)(unsigned int)v17,
                v21);
            v12 = retaddr;
            if ( v18 >= 0 )
              return 0;
            v19 = (unsigned int)v18;
            v13 = 2252;
            goto LABEL_37;
          }
          if ( (unsigned int)_o__wcsicmp(a2, L"Storage") )
            return 0;
          v11 = MdmLogCollector::CollectStorageSnapshot(this);
          v12 = retaddr;
          if ( v11 >= 0 )
            return 0;
          v13 = 2256;
        }
        else
        {
          v11 = MdmLogCollector::CollectOneTraceInternal(this);
          v12 = retaddr;
          if ( v11 >= 0 )
            return 0;
          v13 = 2246;
        }
      }
      else
      {
        v14 = MdmLogCollector::CollectCertReqAikLogs(this);
        if ( v14 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x8C1,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
            (const char *)(unsigned int)v14,
            v21);
        v11 = MdmLogCollector::CollectCertUtilTpmLogs(this);
        v12 = retaddr;
        if ( v11 >= 0 )
          return 0;
        v13 = 2242;
      }
    }
    else
    {
      v5 = MdmLogCollector::CollectLicenseDiagLogs(this);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8B5,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)v5,
          v21);
      DeviceHardwareData = MdmLogCollector::GetDeviceHardwareData(this);
      if ( DeviceHardwareData < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8B6,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)DeviceHardwareData,
          v21);
      v7 = MdmLogCollector::CollectTpmHighLevelInfo(this);
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8B7,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)v7,
          v21);
      v8 = MdmLogCollector::CollectDiagnosticsFrameworkInfo(this);
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8B8,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)v8,
          v21);
      v9 = MdmLogCollector::CollectUefiEntries(this);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8B9,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)v9,
          v21);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
        return 0;
      v11 = MdmLogCollector::CollectDeviceLinkInfo(this);
      v12 = retaddr;
      if ( v11 >= 0 )
        return 0;
      v13 = 2236;
    }
    v19 = (unsigned int)v11;
LABEL_37:
    wil::details::in1diag3::_Log_Hr(
      v12,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)v19,
      v21);
    return 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x8D5,
                           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x18010a670  mov     [rsp+arg_0], rbx
0x18010a675  push    rdi; int
0x18010a676  sub     rsp, 20h
0x18010a67a  mov     rdi, rdx
0x18010a67d  mov     rbx, rcx
0x18010a680  lea     rdx, aAutopilot; "Autopilot"
0x18010a687  mov     rcx, rdi
0x18010a68a  call    cs:__imp__o__wcsicmp
0x18010a690  test    eax, eax
0x18010a692  jnz     loc_18010A784
0x18010a698  mov     rcx, rbx; this
0x18010a69b  call    ?CollectLicenseDiagLogs@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectLicenseDiagLogs(void)
0x18010a6a0  mov     rcx, [rsp+28h]; this
0x18010a6a5  test    eax, eax
0x18010a6a7  jns     short loc_18010A6BD
0x18010a6a9  mov     r9d, eax; char *
0x18010a6ac  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010a6b3  mov     edx, 8B5h; void *
0x18010a6b8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010a6bd  mov     rcx, rbx; this
0x18010a6c0  call    ?GetDeviceHardwareData@MdmLogCollector@@AEAAJXZ; MdmLogCollector::GetDeviceHardwareData(void)
0x18010a6c5  mov     rcx, [rsp+28h]; this
0x18010a6ca  test    eax, eax
0x18010a6cc  jns     short loc_18010A6E2
0x18010a6ce  mov     r9d, eax; char *
0x18010a6d1  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010a6d8  mov     edx, 8B6h; void *
0x18010a6dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010a6e2  mov     rcx, rbx; this
0x18010a6e5  call    ?CollectTpmHighLevelInfo@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectTpmHighLevelInfo(void)
0x18010a6ea  mov     rcx, [rsp+28h]; this
0x18010a6ef  test    eax, eax
0x18010a6f1  jns     short loc_18010A707
0x18010a6f3  mov     r9d, eax; char *
0x18010a6f6  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010a6fd  mov     edx, 8B7h; void *
0x18010a702  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010a707  mov     rcx, rbx; this
0x18010a70a  call    ?CollectDiagnosticsFrameworkInfo@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectDiagnosticsFrameworkInfo(void)
0x18010a70f  mov     rcx, [rsp+28h]; this
0x18010a714  test    eax, eax
0x18010a716  jns     short loc_18010A72C
0x18010a718  mov     r9d, eax; char *
0x18010a71b  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010a722  mov     edx, 8B8h; void *
0x18010a727  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010a72c  mov     rcx, rbx; this
0x18010a72f  call    ?CollectUefiEntries@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectUefiEntries(void)
0x18010a734  mov     rcx, [rsp+28h]; this
0x18010a739  test    eax, eax
0x18010a73b  jns     short loc_18010A751
0x18010a73d  mov     r9d, eax; char *
0x18010a740  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010a747  mov     edx, 8B9h; void *
0x18010a74c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010a751  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18010a758  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18010a75d  test    al, al
0x18010a75f  jz      loc_18010A8EB
0x18010a765  mov     rcx, rbx; this
0x18010a768  call    ?CollectDeviceLinkInfo@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectDeviceLinkInfo(void)
0x18010a76d  mov     rcx, [rsp+28h]
0x18010a772  test    eax, eax
0x18010a774  jns     loc_18010A8EB
0x18010a77a  mov     edx, 8BCh
0x18010a77f  jmp     loc_18010A8DC
0x18010a784  lea     rdx, aTpm_0; "Tpm"
0x18010a78b  mov     rcx, rdi
0x18010a78e  call    cs:__imp__o__wcsicmp
0x18010a794  test    eax, eax
0x18010a796  jnz     short loc_18010A7DC
0x18010a798  mov     rcx, rbx; this
0x18010a79b  call    ?CollectCertReqAikLogs@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectCertReqAikLogs(void)
0x18010a7a0  mov     rcx, [rsp+28h]; this
0x18010a7a5  test    eax, eax
0x18010a7a7  jns     short loc_18010A7BD
0x18010a7a9  mov     r9d, eax; char *
0x18010a7ac  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010a7b3  mov     edx, 8C1h; void *
0x18010a7b8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010a7bd  mov     rcx, rbx; this
0x18010a7c0  call    ?CollectCertUtilTpmLogs@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectCertUtilTpmLogs(void)
0x18010a7c5  mov     rcx, [rsp+28h]
0x18010a7ca  test    eax, eax
0x18010a7cc  jns     loc_18010A8EB
0x18010a7d2  mov     edx, 8C2h
0x18010a7d7  jmp     loc_18010A8DC
0x18010a7dc  lea     rdx, aOnetrace; "OneTrace"
0x18010a7e3  mov     rcx, rdi
0x18010a7e6  call    cs:__imp__o__wcsicmp
0x18010a7ec  test    eax, eax
0x18010a7ee  jnz     short loc_18010A80F
0x18010a7f0  mov     rcx, rbx; this
0x18010a7f3  call    ?CollectOneTraceInternal@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectOneTraceInternal(void)
0x18010a7f8  mov     rcx, [rsp+28h]
0x18010a7fd  test    eax, eax
0x18010a7ff  jns     loc_18010A8EB
0x18010a805  mov     edx, 8C6h
0x18010a80a  jmp     loc_18010A8DC
0x18010a80f  lea     rdx, aDeviceenrollme; "DeviceEnrollment"
0x18010a816  mov     rcx, rdi
0x18010a819  call    cs:__imp__o__wcsicmp
0x18010a81f  test    eax, eax
0x18010a821  jnz     loc_18010A8B2
0x18010a827  mov     rcx, rbx; this
0x18010a82a  call    ?CollectWifiLogs@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectWifiLogs(void)
0x18010a82f  mov     rcx, [rsp+28h]; this
0x18010a834  test    eax, eax
0x18010a836  jns     short loc_18010A84C
0x18010a838  mov     r9d, eax; char *
0x18010a83b  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010a842  mov     edx, 8CAh; void *
0x18010a847  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010a84c  mov     rcx, rbx; this
0x18010a84f  call    ?CollectDsregLog@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectDsregLog(void)
0x18010a854  mov     rcx, [rsp+28h]; this
0x18010a859  test    eax, eax
0x18010a85b  jns     short loc_18010A871
0x18010a85d  mov     r9d, eax; char *
0x18010a860  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010a867  mov     edx, 8CBh; void *
0x18010a86c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010a871  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18010a878  mov     rcx, rbx; this
0x18010a87b  call    ?AddHklmRegEntry@MdmLogCollector@@QEAAJPEBG@Z; MdmLogCollector::AddHklmRegEntry(ushort const *)
0x18010a880  mov     ebx, eax
0x18010a882  test    eax, eax
0x18010a884  jns     short loc_18010A89F
0x18010a886  mov     rcx, [rsp+28h]; this
0x18010a88b  mov     r9d, eax; char *
0x18010a88e  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010a895  mov     edx, 99Bh; void *
0x18010a89a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a89f  mov     rcx, [rsp+28h]
0x18010a8a4  test    ebx, ebx
0x18010a8a6  jns     short loc_18010A8EB
0x18010a8a8  mov     r9d, ebx
0x18010a8ab  mov     edx, 8CCh
0x18010a8b0  jmp     short loc_18010A8DF
0x18010a8b2  lea     rdx, aStorage; "Storage"
0x18010a8b9  mov     rcx, rdi
0x18010a8bc  call    cs:__imp__o__wcsicmp
0x18010a8c2  test    eax, eax
0x18010a8c4  jnz     short loc_18010A8EB
0x18010a8c6  mov     rcx, rbx; this
0x18010a8c9  call    ?CollectStorageSnapshot@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectStorageSnapshot(void)
0x18010a8ce  mov     rcx, [rsp+28h]; this
0x18010a8d3  test    eax, eax
0x18010a8d5  jns     short loc_18010A8EB
0x18010a8d7  mov     edx, 8D0h; void *
0x18010a8dc  mov     r9d, eax; char *
0x18010a8df  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010a8e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010a8eb  xor     eax, eax
0x18010a8ed  jmp     short loc_18010A8F3
0x18010a8ef  mov     eax, [rsp+28h+arg_10]
0x18010a8f3  mov     rbx, [rsp+28h+arg_0]
0x18010a8f8  add     rsp, 20h
0x18010a8fc  pop     rdi
0x18010a8fd  retn
```
