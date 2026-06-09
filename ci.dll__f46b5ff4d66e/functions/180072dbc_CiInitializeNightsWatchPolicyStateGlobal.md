# CiInitializeNightsWatchPolicyStateGlobal

- ea: `0x180072dbc`
- end: `0x180072fa5`
- name: `CiInitializeNightsWatchPolicyStateGlobal`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005dfd0`

## callees

- `0x18001d2f8`
- `0x18001d350`
- `0x180059ed0`
- `0x180072dbc`
- `0x1800e18f8`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x180072ee2`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180072ee2`

## string_xrefs

- `0x180072e21`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180072e93`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180072ed9`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180072f6e`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

## pseudocode

```c
NTSTATUS CiInitializeNightsWatchPolicyStateGlobal()
{
  NTSTATUS result; // eax
  int v1; // [rsp+50h] [rbp+10h] BYREF
  int v2; // [rsp+58h] [rbp+18h] BYREF
  int v3; // [rsp+60h] [rbp+20h] BYREF

  if ( (unsigned int)Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline() )
  {
    v2 = 0;
    v3 = 0;
    if ( (g_CiPolicyState & 0x4000) != 0 )
    {
      if ( !(unsigned __int8)SIPolicyIsPolicyActive(&SiPolicyIDNightsWatchDesktop, 0) )
      {
        g_NightsWatchDesktopMinValueSeenDuringThisBootSession = 2;
        g_SmartAppControlEnforcementReason = 8;
LABEL_9:
        if ( (int)CipGetRegistryValue(
                    0,
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
                    (__int64)L"SAC_PreviousState",
                    0,
                    (__int64)&v3,
                    4,
                    (__int64)&v2) < 0 )
        {
          g_SmartAppControlPreviousState = -1;
          return RtlWriteRegistryValue(
                   0,
                   L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
                   L"SAC_PreviousState",
                   4u,
                   &g_SmartAppControlPreviousState,
                   4u);
        }
        else
        {
          result = v3;
          g_SmartAppControlPreviousState = v3;
        }
        return result;
      }
      g_NightsWatchDesktopMinValueSeenDuringThisBootSession = 1;
      v1 = 4;
    }
    else
    {
      g_NightsWatchDesktopMinValueSeenDuringThisBootSession = 0;
      v1 = 7;
    }
    if ( (int)CipGetRegistryValue(
                0,
                L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
                (__int64)L"SAC_EnforcementReason",
                0,
                (__int64)&v1,
                4,
                (__int64)&v2) >= 0 )
      g_SmartAppControlEnforcementReason = v1;
    goto LABEL_9;
  }
  if ( (g_CiPolicyState & 0x4000) == 0 )
  {
    g_NightsWatchDesktopMinValueSeenDuringThisBootSession = 0;
    goto LABEL_14;
  }
  if ( !(unsigned __int8)SIPolicyIsPolicyActive(&SiPolicyIDNightsWatchDesktop, 0) )
  {
    g_NightsWatchDesktopMinValueSeenDuringThisBootSession = 2;
LABEL_14:
    result = Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline();
    if ( result )
      g_SmartAppControlEnforcementReason = 0;
    return result;
  }
  g_NightsWatchDesktopMinValueSeenDuringThisBootSession = 1;
  result = Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline();
  if ( result )
  {
    v2 = 0;
    v1 = 4;
    result = CipGetRegistryValue(
               0,
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
               (__int64)L"SAC_EnforcementReason",
               0,
               (__int64)&v1,
               4,
               (__int64)&v2);
    if ( result >= 0 )
    {
      result = v1;
      g_SmartAppControlEnforcementReason = v1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180072dbc  mov     [rsp-8+arg_18], rbx
0x180072dc1  push    rbp
0x180072dc2  mov     rbp, rsp
0x180072dc5  sub     rsp, 40h
0x180072dc9  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180072dce  test    eax, eax
0x180072dd0  jz      loc_180072EF0
0x180072dd6  test    cs:g_CiPolicyState, 4000h
0x180072de0  mov     ebx, 4
0x180072de5  mov     [rbp+arg_8], 0
0x180072dec  mov     [rbp+arg_10], 0
0x180072df3  jnz     short loc_180072E43
0x180072df5  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 0
0x180072dff  mov     [rbp+arg_0], 7
0x180072e06  lea     rax, [rbp+arg_8]
0x180072e0a  xor     r9d, r9d
0x180072e0d  mov     [rsp+40h+var_10], rax
0x180072e12  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x180072e19  lea     rax, [rbp+arg_0]
0x180072e1d  mov     [rsp+40h+ValueLength], ebx
0x180072e21  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180072e28  mov     [rsp+40h+ValueData], rax
0x180072e2d  xor     ecx, ecx
0x180072e2f  call    CipGetRegistryValue
0x180072e34  test    eax, eax
0x180072e36  js      short loc_180072E78
0x180072e38  mov     eax, [rbp+arg_0]
0x180072e3b  mov     cs:g_SmartAppControlEnforcementReason, eax
0x180072e41  jmp     short loc_180072E78
0x180072e43  xor     edx, edx
0x180072e45  lea     rcx, SiPolicyIDNightsWatchDesktop
0x180072e4c  call    SIPolicyIsPolicyActive
0x180072e51  test    al, al
0x180072e53  jz      short loc_180072E64
0x180072e55  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 1
0x180072e5f  mov     [rbp+arg_0], ebx
0x180072e62  jmp     short loc_180072E06
0x180072e64  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 2
0x180072e6e  mov     cs:g_SmartAppControlEnforcementReason, 8
0x180072e78  lea     rax, [rbp+arg_8]
0x180072e7c  xor     r9d, r9d
0x180072e7f  mov     [rsp+40h+var_10], rax
0x180072e84  lea     r8, aSacPrevioussta; "SAC_PreviousState"
0x180072e8b  lea     rax, [rbp+arg_10]
0x180072e8f  mov     [rsp+40h+ValueLength], ebx
0x180072e93  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180072e9a  mov     [rsp+40h+ValueData], rax
0x180072e9f  xor     ecx, ecx
0x180072ea1  call    CipGetRegistryValue
0x180072ea6  test    eax, eax
0x180072ea8  js      short loc_180072EB5
0x180072eaa  mov     eax, [rbp+arg_10]
0x180072ead  mov     cs:g_SmartAppControlPreviousState, eax
0x180072eb3  jmp     short loc_180072F19
0x180072eb5  lea     rax, g_SmartAppControlPreviousState
0x180072ebc  mov     [rsp+40h+ValueLength], ebx; ValueLength
0x180072ec0  mov     r9d, ebx; ValueType
0x180072ec3  mov     [rsp+40h+ValueData], rax; ValueData
0x180072ec8  lea     r8, aSacPrevioussta; "SAC_PreviousState"
0x180072ecf  mov     cs:g_SmartAppControlPreviousState, 0FFFFFFFFh
0x180072ed9  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180072ee0  xor     ecx, ecx; RelativeTo
0x180072ee2  call    cs:__imp_RtlWriteRegistryValue
0x180072ee9  nop     dword ptr [rax+rax+00h]
0x180072eee  jmp     short loc_180072F19
0x180072ef0  test    cs:g_CiPolicyState, 4000h
0x180072efa  jnz     short loc_180072F25
0x180072efc  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 0
0x180072f06  call    Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline
0x180072f0b  test    eax, eax
0x180072f0d  jz      short loc_180072F19
0x180072f0f  mov     cs:g_SmartAppControlEnforcementReason, 0
0x180072f19  mov     rbx, [rsp+40h+arg_18]
0x180072f1e  add     rsp, 40h
0x180072f22  pop     rbp
0x180072f23  retn
0x180072f25  xor     edx, edx
0x180072f27  lea     rcx, SiPolicyIDNightsWatchDesktop
0x180072f2e  call    SIPolicyIsPolicyActive
0x180072f33  test    al, al
0x180072f35  jz      short loc_180072F96
0x180072f37  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 1
0x180072f41  call    Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline
0x180072f46  test    eax, eax
0x180072f48  jz      short loc_180072F19
0x180072f4a  lea     rax, [rbp+arg_8]
0x180072f4e  mov     [rbp+arg_8], 0
0x180072f55  mov     [rsp+40h+var_10], rax
0x180072f5a  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x180072f61  mov     ebx, 4
0x180072f66  lea     rax, [rbp+arg_0]
0x180072f6a  mov     [rsp+40h+ValueLength], ebx
0x180072f6e  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180072f75  xor     r9d, r9d
0x180072f78  mov     [rsp+40h+ValueData], rax
0x180072f7d  xor     ecx, ecx
0x180072f7f  mov     [rbp+arg_0], ebx
0x180072f82  call    CipGetRegistryValue
0x180072f87  test    eax, eax
0x180072f89  js      short loc_180072F19
0x180072f8b  mov     eax, [rbp+arg_0]
0x180072f8e  mov     cs:g_SmartAppControlEnforcementReason, eax
0x180072f94  jmp     short loc_180072F19
0x180072f96  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 2
0x180072fa0  jmp     loc_180072F06
```
