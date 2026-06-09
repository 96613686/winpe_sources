# CiSetNightsWatchPolicyStateRegKeys

- ea: `0x1800744f8`
- end: `0x1800746cd`
- name: `CiSetNightsWatchPolicyStateRegKeys`
- size: `469`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180058120`

## callees

- `0x18001d180`
- `0x18001d290`
- `0x18001d2e8`
- `0x18001e104`
- `0x18005abe8`
- `0x18006c1d4`
- `0x18006c268`
- `0x1800744f8`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x1800745de`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800746b2`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800745de`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800746b2`

## string_xrefs

- `0x180074517`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

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
0x1800744f8  push    rbp
0x1800744fa  push    rbx
0x1800744fb  push    rdi
0x1800744fc  push    r14
0x1800744fe  push    r15
0x180074500  mov     rbp, rsp
0x180074503  sub     rsp, 50h
0x180074507  lea     rax, [rbp+arg_10]
0x18007450b  mov     [rbp+arg_8], 0
0x180074512  mov     [rsp+50h+var_20], rax
0x180074517  lea     r15, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18007451e  lea     rax, [rbp+arg_8]
0x180074522  mov     [rbp+arg_0], 0
0x180074529  mov     r14d, 4
0x18007452f  mov     [rbp+arg_10], 0
0x180074536  mov     [rsp+50h+ValueLength], r14d
0x18007453b  lea     r8, aVerifiedandrep_2; "VerifiedAndReputablePolicyState"
0x180074542  xor     r9d, r9d
0x180074545  mov     [rsp+50h+ValueData], rax
0x18007454a  mov     rdx, r15
0x18007454d  mov     [rbp+var_10], 0
0x180074554  xor     ecx, ecx
0x180074556  mov     [rbp+arg_18], 0
0x18007455d  call    CipGetRegistryValue
0x180074562  mov     edi, eax
0x180074564  test    eax, eax
0x180074566  jns     short loc_18007457E
0x180074568  mov     eax, cs:g_CiPolicyState
0x18007456e  and     eax, 4000h
0x180074573  neg     eax
0x180074575  sbb     eax, eax
0x180074577  and     eax, edi
0x180074579  jmp     loc_1800746C0
0x18007457e  mov     ebx, cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession
0x180074584  call    Feature_SAC_TwoWaySwitch__private_IsEnabledDeviceUsageNoInline
0x180074589  test    eax, eax
0x18007458b  mov     eax, [rbp+arg_8]
0x18007458e  jz      short loc_1800745BA
0x180074590  cmp     eax, 2
0x180074593  ja      short loc_1800745BE
0x180074595  cmp     ebx, 1
0x180074598  ja      short loc_18007459F
0x18007459a  cmp     eax, 2
0x18007459d  jz      short loc_1800745BE
0x18007459f  mov     [rbp+arg_0], eax
0x1800745a2  cmp     eax, ebx
0x1800745a4  jnb     short loc_1800745AC
0x1800745a6  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, eax
0x1800745ac  cmp     eax, 1
0x1800745af  jnz     short loc_180074605
0x1800745b1  mov     ecx, ebx
0x1800745b3  call    CiInstrumentSwitchNWToEnforcementMode2
0x1800745b8  jmp     short loc_18007460E
0x1800745ba  cmp     eax, ebx
0x1800745bc  jbe     short loc_1800745EE
0x1800745be  lea     rax, [rbp+arg_0]
0x1800745c2  mov     [rsp+50h+ValueLength], r14d; ValueLength
0x1800745c7  mov     r9d, r14d; ValueType
0x1800745ca  mov     [rsp+50h+ValueData], rax; ValueData
0x1800745cf  lea     r8, aVerifiedandrep_2; "VerifiedAndReputablePolicyState"
0x1800745d6  mov     [rbp+arg_0], ebx
0x1800745d9  mov     rdx, r15; Path
0x1800745dc  xor     ecx, ecx; RelativeTo
0x1800745de  call    cs:__imp_RtlWriteRegistryValue
0x1800745e5  nop     dword ptr [rax+rax+00h]
0x1800745ea  mov     edi, eax
0x1800745ec  jmp     short loc_18007460E
0x1800745ee  jnb     short loc_18007460E
0x1800745f0  mov     [rbp+arg_0], eax
0x1800745f3  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, eax
0x1800745f9  cmp     eax, 1
0x1800745fc  jnz     short loc_180074605
0x1800745fe  call    CiInstrumentSwitchNWToEnforcementMode
0x180074603  jmp     short loc_18007460E
0x180074605  test    eax, eax
0x180074607  jnz     short loc_18007460E
0x180074609  call    CiInstrumentSwitchNWOff
0x18007460e  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180074613  test    eax, eax
0x180074615  jz      short loc_180074689
0x180074617  lea     rax, [rbp+arg_10]
0x18007461b  xor     r9d, r9d
0x18007461e  mov     [rsp+50h+var_20], rax
0x180074623  lea     r8, aSacPrevioussta; "SAC_PreviousState"
0x18007462a  lea     rax, [rbp+arg_18]
0x18007462e  mov     [rsp+50h+ValueLength], r14d
0x180074633  mov     rdx, r15
0x180074636  mov     [rsp+50h+ValueData], rax
0x18007463b  xor     ecx, ecx
0x18007463d  call    CipGetRegistryValue
0x180074642  test    eax, eax
0x180074644  js      short loc_18007464F
0x180074646  mov     eax, [rbp+arg_18]
0x180074649  mov     cs:g_SmartAppControlPreviousState, eax
0x18007464f  lea     rax, [rbp+arg_10]
0x180074653  xor     r9d, r9d
0x180074656  mov     [rsp+50h+var_20], rax
0x18007465b  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x180074662  lea     rax, [rbp+var_10]
0x180074666  mov     [rsp+50h+ValueLength], r14d
0x18007466b  mov     rdx, r15
0x18007466e  mov     [rsp+50h+ValueData], rax
0x180074673  xor     ecx, ecx
0x180074675  call    CipGetRegistryValue
0x18007467a  test    eax, eax
0x18007467c  js      short loc_1800746BE
0x18007467e  mov     eax, [rbp+var_10]
0x180074681  mov     cs:g_SmartAppControlEnforcementReason, eax
0x180074687  jmp     short loc_1800746BE
0x180074689  call    Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline
0x18007468e  test    eax, eax
0x180074690  jz      short loc_1800746BE
0x180074692  lea     rax, g_SmartAppControlEnforcementReason
0x180074699  mov     [rsp+50h+ValueLength], r14d; ValueLength
0x18007469e  mov     r9d, r14d; ValueType
0x1800746a1  mov     [rsp+50h+ValueData], rax; ValueData
0x1800746a6  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x1800746ad  mov     rdx, r15; Path
0x1800746b0  xor     ecx, ecx; RelativeTo
0x1800746b2  call    cs:__imp_RtlWriteRegistryValue
0x1800746b9  nop     dword ptr [rax+rax+00h]
0x1800746be  mov     eax, edi
0x1800746c0  add     rsp, 50h
0x1800746c4  pop     r15
0x1800746c6  pop     r14
0x1800746c8  pop     rdi
0x1800746c9  pop     rbx
0x1800746ca  pop     rbp
0x1800746cb  retn
```
