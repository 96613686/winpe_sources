# CiInitializeNightsWatchPolicyStateGlobal

- ea: `0x18007406c`
- end: `0x180074255`
- name: `CiInitializeNightsWatchPolicyStateGlobal`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005e6d0`

## callees

- `0x18001d290`
- `0x18001d2e8`
- `0x18005abe8`
- `0x18007406c`
- `0x1800e28e8`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x180074192`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180074192`

## string_xrefs

- `0x1800740d1`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180074143`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180074189`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x18007421e`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

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
0x18007406c  mov     [rsp-8+arg_18], rbx
0x180074071  push    rbp
0x180074072  mov     rbp, rsp
0x180074075  sub     rsp, 40h
0x180074079  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x18007407e  test    eax, eax
0x180074080  jz      loc_1800741A0
0x180074086  test    cs:g_CiPolicyState, 4000h
0x180074090  mov     ebx, 4
0x180074095  mov     [rbp+arg_8], 0
0x18007409c  mov     [rbp+arg_10], 0
0x1800740a3  jnz     short loc_1800740F3
0x1800740a5  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 0
0x1800740af  mov     [rbp+arg_0], 7
0x1800740b6  lea     rax, [rbp+arg_8]
0x1800740ba  xor     r9d, r9d
0x1800740bd  mov     [rsp+40h+var_10], rax
0x1800740c2  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x1800740c9  lea     rax, [rbp+arg_0]
0x1800740cd  mov     [rsp+40h+ValueLength], ebx
0x1800740d1  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800740d8  mov     [rsp+40h+ValueData], rax
0x1800740dd  xor     ecx, ecx
0x1800740df  call    CipGetRegistryValue
0x1800740e4  test    eax, eax
0x1800740e6  js      short loc_180074128
0x1800740e8  mov     eax, [rbp+arg_0]
0x1800740eb  mov     cs:g_SmartAppControlEnforcementReason, eax
0x1800740f1  jmp     short loc_180074128
0x1800740f3  xor     edx, edx
0x1800740f5  lea     rcx, SiPolicyIDNightsWatchDesktop
0x1800740fc  call    SIPolicyIsPolicyActive
0x180074101  test    al, al
0x180074103  jz      short loc_180074114
0x180074105  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 1
0x18007410f  mov     [rbp+arg_0], ebx
0x180074112  jmp     short loc_1800740B6
0x180074114  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 2
0x18007411e  mov     cs:g_SmartAppControlEnforcementReason, 8
0x180074128  lea     rax, [rbp+arg_8]
0x18007412c  xor     r9d, r9d
0x18007412f  mov     [rsp+40h+var_10], rax
0x180074134  lea     r8, aSacPrevioussta; "SAC_PreviousState"
0x18007413b  lea     rax, [rbp+arg_10]
0x18007413f  mov     [rsp+40h+ValueLength], ebx
0x180074143  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18007414a  mov     [rsp+40h+ValueData], rax
0x18007414f  xor     ecx, ecx
0x180074151  call    CipGetRegistryValue
0x180074156  test    eax, eax
0x180074158  js      short loc_180074165
0x18007415a  mov     eax, [rbp+arg_10]
0x18007415d  mov     cs:g_SmartAppControlPreviousState, eax
0x180074163  jmp     short loc_1800741C9
0x180074165  lea     rax, g_SmartAppControlPreviousState
0x18007416c  mov     [rsp+40h+ValueLength], ebx; ValueLength
0x180074170  mov     r9d, ebx; ValueType
0x180074173  mov     [rsp+40h+ValueData], rax; ValueData
0x180074178  lea     r8, aSacPrevioussta; "SAC_PreviousState"
0x18007417f  mov     cs:g_SmartAppControlPreviousState, 0FFFFFFFFh
0x180074189  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180074190  xor     ecx, ecx; RelativeTo
0x180074192  call    cs:__imp_RtlWriteRegistryValue
0x180074199  nop     dword ptr [rax+rax+00h]
0x18007419e  jmp     short loc_1800741C9
0x1800741a0  test    cs:g_CiPolicyState, 4000h
0x1800741aa  jnz     short loc_1800741D5
0x1800741ac  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 0
0x1800741b6  call    Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline
0x1800741bb  test    eax, eax
0x1800741bd  jz      short loc_1800741C9
0x1800741bf  mov     cs:g_SmartAppControlEnforcementReason, 0
0x1800741c9  mov     rbx, [rsp+40h+arg_18]
0x1800741ce  add     rsp, 40h
0x1800741d2  pop     rbp
0x1800741d3  retn
0x1800741d5  xor     edx, edx
0x1800741d7  lea     rcx, SiPolicyIDNightsWatchDesktop
0x1800741de  call    SIPolicyIsPolicyActive
0x1800741e3  test    al, al
0x1800741e5  jz      short loc_180074246
0x1800741e7  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 1
0x1800741f1  call    Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline
0x1800741f6  test    eax, eax
0x1800741f8  jz      short loc_1800741C9
0x1800741fa  lea     rax, [rbp+arg_8]
0x1800741fe  mov     [rbp+arg_8], 0
0x180074205  mov     [rsp+40h+var_10], rax
0x18007420a  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x180074211  mov     ebx, 4
0x180074216  lea     rax, [rbp+arg_0]
0x18007421a  mov     [rsp+40h+ValueLength], ebx
0x18007421e  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180074225  xor     r9d, r9d
0x180074228  mov     [rsp+40h+ValueData], rax
0x18007422d  xor     ecx, ecx
0x18007422f  mov     [rbp+arg_0], ebx
0x180074232  call    CipGetRegistryValue
0x180074237  test    eax, eax
0x180074239  js      short loc_1800741C9
0x18007423b  mov     eax, [rbp+arg_0]
0x18007423e  mov     cs:g_SmartAppControlEnforcementReason, eax
0x180074244  jmp     short loc_1800741C9
0x180074246  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, 2
0x180074250  jmp     loc_1800741B6
```
