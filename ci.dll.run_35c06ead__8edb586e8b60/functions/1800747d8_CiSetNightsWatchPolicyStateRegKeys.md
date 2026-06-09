# CiSetNightsWatchPolicyStateRegKeys

- ea: `0x1800747d8`
- end: `0x1800749ad`
- name: `CiSetNightsWatchPolicyStateRegKeys`
- size: `469`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180058048`

## callees

- `0x18001d238`
- `0x18001d348`
- `0x18001d3a0`
- `0x18001e1d8`
- `0x18005ab10`
- `0x18006c344`
- `0x18006c3d8`
- `0x1800747d8`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x1800748be`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180074992`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800748be`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180074992`

## string_xrefs

- `0x1800747f7`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

## pseudocode

```c
__int64 CiSetNightsWatchPolicyStateRegKeys()
{
  NTSTATUS RegistryValue; // edi
  unsigned int v2; // ebx
  int v3[4]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int ValueData; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v5; // [rsp+88h] [rbp+38h] BYREF
  int v6; // [rsp+90h] [rbp+40h] BYREF
  int v7; // [rsp+98h] [rbp+48h] BYREF

  v5 = 0;
  ValueData = 0;
  v6 = 0;
  v3[0] = 0;
  v7 = 0;
  RegistryValue = CipGetRegistryValue(
                    0,
                    (unsigned int)L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
                    (unsigned int)L"VerifiedAndReputablePolicyState",
                    0,
                    (__int64)&v5,
                    4,
                    (__int64)&v6);
  if ( RegistryValue < 0 )
    return RegistryValue & (unsigned int)-((g_CiPolicyState & 0x4000) != 0);
  v2 = g_NightsWatchDesktopMinValueSeenDuringThisBootSession;
  if ( !(unsigned int)Feature_SAC_TwoWaySwitch__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( v5 <= v2 )
    {
      if ( v5 >= v2 )
        goto LABEL_18;
      ValueData = v5;
      g_NightsWatchDesktopMinValueSeenDuringThisBootSession = v5;
      if ( v5 == 1 )
      {
        CiInstrumentSwitchNWToEnforcementMode();
        goto LABEL_18;
      }
LABEL_16:
      if ( !v5 )
        CiInstrumentSwitchNWOff();
      goto LABEL_18;
    }
LABEL_12:
    ValueData = v2;
    RegistryValue = RtlWriteRegistryValue(
                      0,
                      L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
                      L"VerifiedAndReputablePolicyState",
                      4u,
                      &ValueData,
                      4u);
    goto LABEL_18;
  }
  if ( v5 > 2 || v2 <= 1 && v5 == 2 )
    goto LABEL_12;
  ValueData = v5;
  if ( v5 < v2 )
    g_NightsWatchDesktopMinValueSeenDuringThisBootSession = v5;
  if ( v5 != 1 )
    goto LABEL_16;
  CiInstrumentSwitchNWToEnforcementMode2(v2);
LABEL_18:
  if ( (unsigned int)Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( (int)CipGetRegistryValue(
                0,
                (unsigned int)L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
                (unsigned int)L"SAC_PreviousState",
                0,
                (__int64)&v7,
                4,
                (__int64)&v6) >= 0 )
      g_SmartAppControlPreviousState = v7;
    if ( (int)CipGetRegistryValue(
                0,
                (unsigned int)L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
                (unsigned int)L"SAC_EnforcementReason",
                0,
                (__int64)v3,
                4,
                (__int64)&v6) >= 0 )
      g_SmartAppControlEnforcementReason = v3[0];
  }
  else if ( (unsigned int)Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline() )
  {
    RtlWriteRegistryValue(
      0,
      L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
      L"SAC_EnforcementReason",
      4u,
      &g_SmartAppControlEnforcementReason,
      4u);
  }
  return (unsigned int)RegistryValue;
}

```

## disassembly

```asm
0x1800747d8  push    rbp
0x1800747da  push    rbx
0x1800747db  push    rdi
0x1800747dc  push    r14
0x1800747de  push    r15
0x1800747e0  mov     rbp, rsp
0x1800747e3  sub     rsp, 50h
0x1800747e7  lea     rax, [rbp+arg_10]
0x1800747eb  mov     [rbp+arg_8], 0
0x1800747f2  mov     [rsp+50h+var_20], rax
0x1800747f7  lea     r15, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800747fe  lea     rax, [rbp+arg_8]
0x180074802  mov     [rbp+arg_0], 0
0x180074809  mov     r14d, 4
0x18007480f  mov     [rbp+arg_10], 0
0x180074816  mov     [rsp+50h+ValueLength], r14d
0x18007481b  lea     r8, aVerifiedandrep_2; "VerifiedAndReputablePolicyState"
0x180074822  xor     r9d, r9d
0x180074825  mov     [rsp+50h+ValueData], rax
0x18007482a  mov     rdx, r15
0x18007482d  mov     [rbp+var_10], 0
0x180074834  xor     ecx, ecx
0x180074836  mov     [rbp+arg_18], 0
0x18007483d  call    CipGetRegistryValue
0x180074842  mov     edi, eax
0x180074844  test    eax, eax
0x180074846  jns     short loc_18007485E
0x180074848  mov     eax, cs:g_CiPolicyState
0x18007484e  and     eax, 4000h
0x180074853  neg     eax
0x180074855  sbb     eax, eax
0x180074857  and     eax, edi
0x180074859  jmp     loc_1800749A0
0x18007485e  mov     ebx, cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession
0x180074864  call    Feature_SAC_TwoWaySwitch__private_IsEnabledDeviceUsageNoInline
0x180074869  test    eax, eax
0x18007486b  mov     eax, [rbp+arg_8]
0x18007486e  jz      short loc_18007489A
0x180074870  cmp     eax, 2
0x180074873  ja      short loc_18007489E
0x180074875  cmp     ebx, 1
0x180074878  ja      short loc_18007487F
0x18007487a  cmp     eax, 2
0x18007487d  jz      short loc_18007489E
0x18007487f  mov     [rbp+arg_0], eax
0x180074882  cmp     eax, ebx
0x180074884  jnb     short loc_18007488C
0x180074886  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, eax
0x18007488c  cmp     eax, 1
0x18007488f  jnz     short loc_1800748E5
0x180074891  mov     ecx, ebx
0x180074893  call    CiInstrumentSwitchNWToEnforcementMode2
0x180074898  jmp     short loc_1800748EE
0x18007489a  cmp     eax, ebx
0x18007489c  jbe     short loc_1800748CE
0x18007489e  lea     rax, [rbp+arg_0]
0x1800748a2  mov     [rsp+50h+ValueLength], r14d; ValueLength
0x1800748a7  mov     r9d, r14d; ValueType
0x1800748aa  mov     [rsp+50h+ValueData], rax; ValueData
0x1800748af  lea     r8, aVerifiedandrep_2; "VerifiedAndReputablePolicyState"
0x1800748b6  mov     [rbp+arg_0], ebx
0x1800748b9  mov     rdx, r15; Path
0x1800748bc  xor     ecx, ecx; RelativeTo
0x1800748be  call    cs:__imp_RtlWriteRegistryValue
0x1800748c5  nop     dword ptr [rax+rax+00h]
0x1800748ca  mov     edi, eax
0x1800748cc  jmp     short loc_1800748EE
0x1800748ce  jnb     short loc_1800748EE
0x1800748d0  mov     [rbp+arg_0], eax
0x1800748d3  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, eax
0x1800748d9  cmp     eax, 1
0x1800748dc  jnz     short loc_1800748E5
0x1800748de  call    CiInstrumentSwitchNWToEnforcementMode
0x1800748e3  jmp     short loc_1800748EE
0x1800748e5  test    eax, eax
0x1800748e7  jnz     short loc_1800748EE
0x1800748e9  call    CiInstrumentSwitchNWOff
0x1800748ee  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x1800748f3  test    eax, eax
0x1800748f5  jz      short loc_180074969
0x1800748f7  lea     rax, [rbp+arg_10]
0x1800748fb  xor     r9d, r9d
0x1800748fe  mov     [rsp+50h+var_20], rax
0x180074903  lea     r8, aSacPrevioussta; "SAC_PreviousState"
0x18007490a  lea     rax, [rbp+arg_18]
0x18007490e  mov     [rsp+50h+ValueLength], r14d
0x180074913  mov     rdx, r15
0x180074916  mov     [rsp+50h+ValueData], rax
0x18007491b  xor     ecx, ecx
0x18007491d  call    CipGetRegistryValue
0x180074922  test    eax, eax
0x180074924  js      short loc_18007492F
0x180074926  mov     eax, [rbp+arg_18]
0x180074929  mov     cs:g_SmartAppControlPreviousState, eax
0x18007492f  lea     rax, [rbp+arg_10]
0x180074933  xor     r9d, r9d
0x180074936  mov     [rsp+50h+var_20], rax
0x18007493b  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x180074942  lea     rax, [rbp+var_10]
0x180074946  mov     [rsp+50h+ValueLength], r14d
0x18007494b  mov     rdx, r15
0x18007494e  mov     [rsp+50h+ValueData], rax
0x180074953  xor     ecx, ecx
0x180074955  call    CipGetRegistryValue
0x18007495a  test    eax, eax
0x18007495c  js      short loc_18007499E
0x18007495e  mov     eax, [rbp+var_10]
0x180074961  mov     cs:g_SmartAppControlEnforcementReason, eax
0x180074967  jmp     short loc_18007499E
0x180074969  call    Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline
0x18007496e  test    eax, eax
0x180074970  jz      short loc_18007499E
0x180074972  lea     rax, g_SmartAppControlEnforcementReason
0x180074979  mov     [rsp+50h+ValueLength], r14d; ValueLength
0x18007497e  mov     r9d, r14d; ValueType
0x180074981  mov     [rsp+50h+ValueData], rax; ValueData
0x180074986  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x18007498d  mov     rdx, r15; Path
0x180074990  xor     ecx, ecx; RelativeTo
0x180074992  call    cs:__imp_RtlWriteRegistryValue
0x180074999  nop     dword ptr [rax+rax+00h]
0x18007499e  mov     eax, edi
0x1800749a0  add     rsp, 50h
0x1800749a4  pop     r15
0x1800749a6  pop     r14
0x1800749a8  pop     rdi
0x1800749a9  pop     rbx
0x1800749aa  pop     rbp
0x1800749ab  retn
```
