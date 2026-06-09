# CiInitializeNightsWatchPolicyStateGlobal

- ea: `0x18007434c`
- end: `0x180074535`
- name: `CiInitializeNightsWatchPolicyStateGlobal`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005e670`

## callees

- `0x18001d348`
- `0x18001d3a0`
- `0x18005ab10`
- `0x18007434c`
- `0x1800e27f8`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x180074472`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180074472`

## string_xrefs

- `0x1800743b1`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180074423`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180074469`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x1800744fe`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

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
0x18007434c  mov     [rsp-8+arg_18], rbx
0x180074351  push    rbp
0x180074352  mov     rbp, rsp
0x180074355  sub     rsp, 40h
0x180074359  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x18007435e  test    eax, eax
0x180074360  jz      loc_180074480
0x180074366  test    cs:g_CiPolicyState, 4000h
0x180074370  mov     ebx, 4
0x180074375  mov     [rbp+arg_8], 0
0x18007437c  mov     [rbp+arg_10], 0
0x180074383  jnz     short loc_1800743D3
0x180074385  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 0
0x18007438f  mov     [rbp+arg_0], 7
0x180074396  lea     rax, [rbp+arg_8]
0x18007439a  xor     r9d, r9d
0x18007439d  mov     [rsp+40h+var_10], rax
0x1800743a2  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x1800743a9  lea     rax, [rbp+arg_0]
0x1800743ad  mov     [rsp+40h+ValueLength], ebx
0x1800743b1  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800743b8  mov     [rsp+40h+ValueData], rax
0x1800743bd  xor     ecx, ecx
0x1800743bf  call    CipGetRegistryValue
0x1800743c4  test    eax, eax
0x1800743c6  js      short loc_180074408
0x1800743c8  mov     eax, [rbp+arg_0]
0x1800743cb  mov     cs:g_SmartAppControlEnforcementReason, eax
0x1800743d1  jmp     short loc_180074408
0x1800743d3  xor     edx, edx
0x1800743d5  lea     rcx, SiPolicyIDNightsWatchDesktop
0x1800743dc  call    SIPolicyIsPolicyActive
0x1800743e1  test    al, al
0x1800743e3  jz      short loc_1800743F4
0x1800743e5  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 1
0x1800743ef  mov     [rbp+arg_0], ebx
0x1800743f2  jmp     short loc_180074396
0x1800743f4  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 2
0x1800743fe  mov     cs:g_SmartAppControlEnforcementReason, 8
0x180074408  lea     rax, [rbp+arg_8]
0x18007440c  xor     r9d, r9d
0x18007440f  mov     [rsp+40h+var_10], rax
0x180074414  lea     r8, aSacPrevioussta; "SAC_PreviousState"
0x18007441b  lea     rax, [rbp+arg_10]
0x18007441f  mov     [rsp+40h+ValueLength], ebx
0x180074423  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18007442a  mov     [rsp+40h+ValueData], rax
0x18007442f  xor     ecx, ecx
0x180074431  call    CipGetRegistryValue
0x180074436  test    eax, eax
0x180074438  js      short loc_180074445
0x18007443a  mov     eax, [rbp+arg_10]
0x18007443d  mov     cs:g_SmartAppControlPreviousState, eax
0x180074443  jmp     short loc_1800744A9
0x180074445  lea     rax, g_SmartAppControlPreviousState
0x18007444c  mov     [rsp+40h+ValueLength], ebx; ValueLength
0x180074450  mov     r9d, ebx; ValueType
0x180074453  mov     [rsp+40h+ValueData], rax; ValueData
0x180074458  lea     r8, aSacPrevioussta; "SAC_PreviousState"
0x18007445f  mov     cs:g_SmartAppControlPreviousState, 0FFFFFFFFh
0x180074469  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180074470  xor     ecx, ecx; RelativeTo
0x180074472  call    cs:__imp_RtlWriteRegistryValue
0x180074479  nop     dword ptr [rax+rax+00h]
0x18007447e  jmp     short loc_1800744A9
0x180074480  test    cs:g_CiPolicyState, 4000h
0x18007448a  jnz     short loc_1800744B5
0x18007448c  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 0
0x180074496  call    Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline
0x18007449b  test    eax, eax
0x18007449d  jz      short loc_1800744A9
0x18007449f  mov     cs:g_SmartAppControlEnforcementReason, 0
0x1800744a9  mov     rbx, [rsp+40h+arg_18]
0x1800744ae  add     rsp, 40h
0x1800744b2  pop     rbp
0x1800744b3  retn
0x1800744b5  xor     edx, edx
0x1800744b7  lea     rcx, SiPolicyIDNightsWatchDesktop
0x1800744be  call    SIPolicyIsPolicyActive
0x1800744c3  test    al, al
0x1800744c5  jz      short loc_180074526
0x1800744c7  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 1
0x1800744d1  call    Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline
0x1800744d6  test    eax, eax
0x1800744d8  jz      short loc_1800744A9
0x1800744da  lea     rax, [rbp+arg_8]
0x1800744de  mov     [rbp+arg_8], 0
0x1800744e5  mov     [rsp+40h+var_10], rax
0x1800744ea  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x1800744f1  mov     ebx, 4
0x1800744f6  lea     rax, [rbp+arg_0]
0x1800744fa  mov     [rsp+40h+ValueLength], ebx
0x1800744fe  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180074505  xor     r9d, r9d
0x180074508  mov     [rsp+40h+ValueData], rax
0x18007450d  xor     ecx, ecx
0x18007450f  mov     [rbp+arg_0], ebx
0x180074512  call    CipGetRegistryValue
0x180074517  test    eax, eax
0x180074519  js      short loc_1800744A9
0x18007451b  mov     eax, [rbp+arg_0]
0x18007451e  mov     cs:g_SmartAppControlEnforcementReason, eax
0x180074524  jmp     short loc_1800744A9
0x180074526  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 2
0x180074530  jmp     loc_180074496
```
