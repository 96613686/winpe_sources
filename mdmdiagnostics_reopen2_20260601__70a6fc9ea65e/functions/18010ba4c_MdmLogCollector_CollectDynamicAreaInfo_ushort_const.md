# MdmLogCollector::CollectDynamicAreaInfo(ushort const *)

- ea: `0x18010ba4c`
- end: `0x18010bcf9`
- name: `?CollectDynamicAreaInfo@MdmLogCollector@@AEAAJPEBG@Z`
- size: `685`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180109f74`

## callees

- `0x1800ed46c`
- `0x1800ef868`
- `0x180109f50`
- `0x18010a79c`
- `0x18010a94c`
- `0x18010aafc`
- `0x18010afa8`
- `0x18010b87c`
- `0x18010ba4c`
- `0x18010c924`
- `0x18010d490`
- `0x18010e480`
- `0x18010e984`
- `0x18010efa0`
- `0x18010f3c4`
- `0x180110578`
- `0x18011268c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010ba66`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bb70`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bbce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bc07`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bcb0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010ba66`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bb70`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bbce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bc07`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bcb0`

## string_xrefs

- `0x18010ba8e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010bab3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010bad8`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010bafd`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010bb22`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010bb94`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010bc2f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010bc54`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010bc82`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010bcd9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010bc65`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`

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
                (void *)0x8A1,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                (const char *)(unsigned int)v15,
                v21);
            v16 = MdmLogCollector::CollectDsregLog(this);
            if ( v16 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x8A2,
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
                (void *)0x972,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                (const char *)(unsigned int)v17,
                v21);
            v12 = retaddr;
            if ( v18 >= 0 )
              return 0;
            v19 = (unsigned int)v18;
            v13 = 2211;
            goto LABEL_37;
          }
          if ( (unsigned int)_o__wcsicmp(a2, L"Storage") )
            return 0;
          v11 = MdmLogCollector::CollectStorageSnapshot(this);
          v12 = retaddr;
          if ( v11 >= 0 )
            return 0;
          v13 = 2215;
        }
        else
        {
          v11 = MdmLogCollector::CollectOneTraceInternal(this);
          v12 = retaddr;
          if ( v11 >= 0 )
            return 0;
          v13 = 2205;
        }
      }
      else
      {
        v14 = MdmLogCollector::CollectCertReqAikLogs(this);
        if ( v14 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x898,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
            (const char *)(unsigned int)v14,
            v21);
        v11 = MdmLogCollector::CollectCertUtilTpmLogs(this);
        v12 = retaddr;
        if ( v11 >= 0 )
          return 0;
        v13 = 2201;
      }
    }
    else
    {
      v5 = MdmLogCollector::CollectLicenseDiagLogs(this);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x88C,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)v5,
          v21);
      DeviceHardwareData = MdmLogCollector::GetDeviceHardwareData(this);
      if ( DeviceHardwareData < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x88D,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)DeviceHardwareData,
          v21);
      v7 = MdmLogCollector::CollectTpmHighLevelInfo(this);
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x88E,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)v7,
          v21);
      v8 = MdmLogCollector::CollectDiagnosticsFrameworkInfo(this);
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x88F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)v8,
          v21);
      v9 = MdmLogCollector::CollectUefiEntries(this);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x890,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)v9,
          v21);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
        return 0;
      v11 = MdmLogCollector::CollectDeviceLinkInfo(this);
      v12 = retaddr;
      if ( v11 >= 0 )
        return 0;
      v13 = 2195;
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
                           (void *)0x8AC,
                           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x18010ba4c  mov     [rsp+arg_0], rbx
0x18010ba51  push    rdi; int
0x18010ba52  sub     rsp, 20h
0x18010ba56  mov     rdi, rdx
0x18010ba59  mov     rbx, rcx
0x18010ba5c  lea     rdx, aAutopilot; "Autopilot"
0x18010ba63  mov     rcx, rdi
0x18010ba66  call    cs:__imp__o__wcsicmp
0x18010ba6d  nop     dword ptr [rax+rax+00h]
0x18010ba72  test    eax, eax
0x18010ba74  jnz     loc_18010BB66
0x18010ba7a  mov     rcx, rbx; this
0x18010ba7d  call    ?CollectLicenseDiagLogs@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectLicenseDiagLogs(void)
0x18010ba82  mov     rcx, [rsp+28h]; this
0x18010ba87  test    eax, eax
0x18010ba89  jns     short loc_18010BA9F
0x18010ba8b  mov     r9d, eax; char *
0x18010ba8e  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010ba95  mov     edx, 88Ch; void *
0x18010ba9a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010ba9f  mov     rcx, rbx; this
0x18010baa2  call    ?GetDeviceHardwareData@MdmLogCollector@@AEAAJXZ; MdmLogCollector::GetDeviceHardwareData(void)
0x18010baa7  mov     rcx, [rsp+28h]; this
0x18010baac  test    eax, eax
0x18010baae  jns     short loc_18010BAC4
0x18010bab0  mov     r9d, eax; char *
0x18010bab3  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010baba  mov     edx, 88Dh; void *
0x18010babf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010bac4  mov     rcx, rbx; this
0x18010bac7  call    ?CollectTpmHighLevelInfo@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectTpmHighLevelInfo(void)
0x18010bacc  mov     rcx, [rsp+28h]; this
0x18010bad1  test    eax, eax
0x18010bad3  jns     short loc_18010BAE9
0x18010bad5  mov     r9d, eax; char *
0x18010bad8  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010badf  mov     edx, 88Eh; void *
0x18010bae4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010bae9  mov     rcx, rbx; this
0x18010baec  call    ?CollectDiagnosticsFrameworkInfo@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectDiagnosticsFrameworkInfo(void)
0x18010baf1  mov     rcx, [rsp+28h]; this
0x18010baf6  test    eax, eax
0x18010baf8  jns     short loc_18010BB0E
0x18010bafa  mov     r9d, eax; char *
0x18010bafd  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010bb04  mov     edx, 88Fh; void *
0x18010bb09  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010bb0e  mov     rcx, rbx; this
0x18010bb11  call    ?CollectUefiEntries@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectUefiEntries(void)
0x18010bb16  mov     rcx, [rsp+28h]; this
0x18010bb1b  test    eax, eax
0x18010bb1d  jns     short loc_18010BB33
0x18010bb1f  mov     r9d, eax; char *
0x18010bb22  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010bb29  mov     edx, 890h; void *
0x18010bb2e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010bb33  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18010bb3a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18010bb3f  test    al, al
0x18010bb41  jz      loc_18010BCE5
0x18010bb47  mov     rcx, rbx; this
0x18010bb4a  call    ?CollectDeviceLinkInfo@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectDeviceLinkInfo(void)
0x18010bb4f  mov     rcx, [rsp+28h]
0x18010bb54  test    eax, eax
0x18010bb56  jns     loc_18010BCE5
0x18010bb5c  mov     edx, 893h
0x18010bb61  jmp     loc_18010BCD6
0x18010bb66  lea     rdx, aTpm_0; "Tpm"
0x18010bb6d  mov     rcx, rdi
0x18010bb70  call    cs:__imp__o__wcsicmp
0x18010bb77  nop     dword ptr [rax+rax+00h]
0x18010bb7c  test    eax, eax
0x18010bb7e  jnz     short loc_18010BBC4
0x18010bb80  mov     rcx, rbx; this
0x18010bb83  call    ?CollectCertReqAikLogs@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectCertReqAikLogs(void)
0x18010bb88  mov     rcx, [rsp+28h]; this
0x18010bb8d  test    eax, eax
0x18010bb8f  jns     short loc_18010BBA5
0x18010bb91  mov     r9d, eax; char *
0x18010bb94  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010bb9b  mov     edx, 898h; void *
0x18010bba0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010bba5  mov     rcx, rbx; this
0x18010bba8  call    ?CollectCertUtilTpmLogs@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectCertUtilTpmLogs(void)
0x18010bbad  mov     rcx, [rsp+28h]
0x18010bbb2  test    eax, eax
0x18010bbb4  jns     loc_18010BCE5
0x18010bbba  mov     edx, 899h
0x18010bbbf  jmp     loc_18010BCD6
0x18010bbc4  lea     rdx, aOnetrace; "OneTrace"
0x18010bbcb  mov     rcx, rdi
0x18010bbce  call    cs:__imp__o__wcsicmp
0x18010bbd5  nop     dword ptr [rax+rax+00h]
0x18010bbda  test    eax, eax
0x18010bbdc  jnz     short loc_18010BBFD
0x18010bbde  mov     rcx, rbx; this
0x18010bbe1  call    ?CollectOneTraceInternal@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectOneTraceInternal(void)
0x18010bbe6  mov     rcx, [rsp+28h]
0x18010bbeb  test    eax, eax
0x18010bbed  jns     loc_18010BCE5
0x18010bbf3  mov     edx, 89Dh
0x18010bbf8  jmp     loc_18010BCD6
0x18010bbfd  lea     rdx, aDeviceenrollme; "DeviceEnrollment"
0x18010bc04  mov     rcx, rdi
0x18010bc07  call    cs:__imp__o__wcsicmp
0x18010bc0e  nop     dword ptr [rax+rax+00h]
0x18010bc13  test    eax, eax
0x18010bc15  jnz     loc_18010BCA6
0x18010bc1b  mov     rcx, rbx; this
0x18010bc1e  call    ?CollectWifiLogs@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectWifiLogs(void)
0x18010bc23  mov     rcx, [rsp+28h]; this
0x18010bc28  test    eax, eax
0x18010bc2a  jns     short loc_18010BC40
0x18010bc2c  mov     r9d, eax; char *
0x18010bc2f  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010bc36  mov     edx, 8A1h; void *
0x18010bc3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010bc40  mov     rcx, rbx; this
0x18010bc43  call    ?CollectDsregLog@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectDsregLog(void)
0x18010bc48  mov     rcx, [rsp+28h]; this
0x18010bc4d  test    eax, eax
0x18010bc4f  jns     short loc_18010BC65
0x18010bc51  mov     r9d, eax; char *
0x18010bc54  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010bc5b  mov     edx, 8A2h; void *
0x18010bc60  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010bc65  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18010bc6c  mov     rcx, rbx; this
0x18010bc6f  call    ?AddHklmRegEntry@MdmLogCollector@@QEAAJPEBG@Z; MdmLogCollector::AddHklmRegEntry(ushort const *)
0x18010bc74  mov     ebx, eax
0x18010bc76  test    eax, eax
0x18010bc78  jns     short loc_18010BC93
0x18010bc7a  mov     rcx, [rsp+28h]; this
0x18010bc7f  mov     r9d, eax; char *
0x18010bc82  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010bc89  mov     edx, 972h; void *
0x18010bc8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010bc93  mov     rcx, [rsp+28h]
0x18010bc98  test    ebx, ebx
0x18010bc9a  jns     short loc_18010BCE5
0x18010bc9c  mov     r9d, ebx
0x18010bc9f  mov     edx, 8A3h
0x18010bca4  jmp     short loc_18010BCD9
0x18010bca6  lea     rdx, aStorage; "Storage"
0x18010bcad  mov     rcx, rdi
0x18010bcb0  call    cs:__imp__o__wcsicmp
0x18010bcb7  nop     dword ptr [rax+rax+00h]
0x18010bcbc  test    eax, eax
0x18010bcbe  jnz     short loc_18010BCE5
0x18010bcc0  mov     rcx, rbx; this
0x18010bcc3  call    ?CollectStorageSnapshot@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectStorageSnapshot(void)
0x18010bcc8  mov     rcx, [rsp+28h]; this
0x18010bccd  test    eax, eax
0x18010bccf  jns     short loc_18010BCE5
0x18010bcd1  mov     edx, 8A7h; void *
0x18010bcd6  mov     r9d, eax; char *
0x18010bcd9  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010bce0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010bce5  xor     eax, eax
0x18010bce7  jmp     short loc_18010BCED
0x18010bce9  mov     eax, [rsp+28h+arg_10]
0x18010bced  mov     rbx, [rsp+28h+arg_0]
0x18010bcf2  add     rsp, 20h
0x18010bcf6  pop     rdi
0x18010bcf7  retn
```
