# CiSetNightsWatchPolicyStateRegKeys

- ea: `0x180073248`
- end: `0x18007341d`
- name: `CiSetNightsWatchPolicyStateRegKeys`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180057408`

## callees

- `0x18001d240`
- `0x18001d2f8`
- `0x18001d350`
- `0x18001e1c0`
- `0x180059ed0`
- `0x18006af54`
- `0x18006afe8`
- `0x180073248`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x18007332e`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180073402`
- `ntoskrnl!RtlWriteRegistryValue` at `0x18007332e`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180073402`

## string_xrefs

- `0x180073267`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

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
0x180073248  push    rbp
0x18007324a  push    rbx
0x18007324b  push    rdi
0x18007324c  push    r14
0x18007324e  push    r15
0x180073250  mov     rbp, rsp
0x180073253  sub     rsp, 50h
0x180073257  lea     rax, [rbp+arg_10]
0x18007325b  mov     [rbp+arg_8], 0
0x180073262  mov     [rsp+50h+var_20], rax
0x180073267  lea     r15, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18007326e  lea     rax, [rbp+arg_8]
0x180073272  mov     [rbp+arg_0], 0
0x180073279  mov     r14d, 4
0x18007327f  mov     [rbp+arg_10], 0
0x180073286  mov     [rsp+50h+ValueLength], r14d
0x18007328b  lea     r8, aVerifiedandrep_2; "VerifiedAndReputablePolicyState"
0x180073292  xor     r9d, r9d
0x180073295  mov     [rsp+50h+ValueData], rax
0x18007329a  mov     rdx, r15
0x18007329d  mov     [rbp+var_10], 0
0x1800732a4  xor     ecx, ecx
0x1800732a6  mov     [rbp+arg_18], 0
0x1800732ad  call    CipGetRegistryValue
0x1800732b2  mov     edi, eax
0x1800732b4  test    eax, eax
0x1800732b6  jns     short loc_1800732CE
0x1800732b8  mov     eax, cs:g_CiPolicyState
0x1800732be  and     eax, 4000h
0x1800732c3  neg     eax
0x1800732c5  sbb     eax, eax
0x1800732c7  and     eax, edi
0x1800732c9  jmp     loc_180073410
0x1800732ce  mov     ebx, cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession
0x1800732d4  call    Feature_SAC_TwoWaySwitch__private_IsEnabledDeviceUsageNoInline
0x1800732d9  test    eax, eax
0x1800732db  mov     eax, [rbp+arg_8]
0x1800732de  jz      short loc_18007330A
0x1800732e0  cmp     eax, 2
0x1800732e3  ja      short loc_18007330E
0x1800732e5  cmp     ebx, 1
0x1800732e8  ja      short loc_1800732EF
0x1800732ea  cmp     eax, 2
0x1800732ed  jz      short loc_18007330E
0x1800732ef  mov     [rbp+arg_0], eax
0x1800732f2  cmp     eax, ebx
0x1800732f4  jnb     short loc_1800732FC
0x1800732f6  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, eax
0x1800732fc  cmp     eax, 1
0x1800732ff  jnz     short loc_180073355
0x180073301  mov     ecx, ebx
0x180073303  call    CiInstrumentSwitchNWToEnforcementMode2
0x180073308  jmp     short loc_18007335E
0x18007330a  cmp     eax, ebx
0x18007330c  jbe     short loc_18007333E
0x18007330e  lea     rax, [rbp+arg_0]
0x180073312  mov     [rsp+50h+ValueLength], r14d; ValueLength
0x180073317  mov     r9d, r14d; ValueType
0x18007331a  mov     [rsp+50h+ValueData], rax; ValueData
0x18007331f  lea     r8, aVerifiedandrep_2; "VerifiedAndReputablePolicyState"
0x180073326  mov     [rbp+arg_0], ebx
0x180073329  mov     rdx, r15; Path
0x18007332c  xor     ecx, ecx; RelativeTo
0x18007332e  call    cs:__imp_RtlWriteRegistryValue
0x180073335  nop     dword ptr [rax+rax+00h]
0x18007333a  mov     edi, eax
0x18007333c  jmp     short loc_18007335E
0x18007333e  jnb     short loc_18007335E
0x180073340  mov     [rbp+arg_0], eax
0x180073343  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, eax
0x180073349  cmp     eax, 1
0x18007334c  jnz     short loc_180073355
0x18007334e  call    CiInstrumentSwitchNWToEnforcementMode
0x180073353  jmp     short loc_18007335E
0x180073355  test    eax, eax
0x180073357  jnz     short loc_18007335E
0x180073359  call    CiInstrumentSwitchNWOff
0x18007335e  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180073363  test    eax, eax
0x180073365  jz      short loc_1800733D9
0x180073367  lea     rax, [rbp+arg_10]
0x18007336b  xor     r9d, r9d
0x18007336e  mov     [rsp+50h+var_20], rax
0x180073373  lea     r8, aSacPrevioussta; "SAC_PreviousState"
0x18007337a  lea     rax, [rbp+arg_18]
0x18007337e  mov     [rsp+50h+ValueLength], r14d
0x180073383  mov     rdx, r15
0x180073386  mov     [rsp+50h+ValueData], rax
0x18007338b  xor     ecx, ecx
0x18007338d  call    CipGetRegistryValue
0x180073392  test    eax, eax
0x180073394  js      short loc_18007339F
0x180073396  mov     eax, [rbp+arg_18]
0x180073399  mov     cs:g_SmartAppControlPreviousState, eax
0x18007339f  lea     rax, [rbp+arg_10]
0x1800733a3  xor     r9d, r9d
0x1800733a6  mov     [rsp+50h+var_20], rax
0x1800733ab  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x1800733b2  lea     rax, [rbp+var_10]
0x1800733b6  mov     [rsp+50h+ValueLength], r14d
0x1800733bb  mov     rdx, r15
0x1800733be  mov     [rsp+50h+ValueData], rax
0x1800733c3  xor     ecx, ecx
0x1800733c5  call    CipGetRegistryValue
0x1800733ca  test    eax, eax
0x1800733cc  js      short loc_18007340E
0x1800733ce  mov     eax, [rbp+var_10]
0x1800733d1  mov     cs:g_SmartAppControlEnforcementReason, eax
0x1800733d7  jmp     short loc_18007340E
0x1800733d9  call    Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline
0x1800733de  test    eax, eax
0x1800733e0  jz      short loc_18007340E
0x1800733e2  lea     rax, g_SmartAppControlEnforcementReason
0x1800733e9  mov     [rsp+50h+ValueLength], r14d; ValueLength
0x1800733ee  mov     r9d, r14d; ValueType
0x1800733f1  mov     [rsp+50h+ValueData], rax; ValueData
0x1800733f6  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x1800733fd  mov     rdx, r15; Path
0x180073400  xor     ecx, ecx; RelativeTo
0x180073402  call    cs:__imp_RtlWriteRegistryValue
0x180073409  nop     dword ptr [rax+rax+00h]
0x18007340e  mov     eax, edi
0x180073410  add     rsp, 50h
0x180073414  pop     r15
0x180073416  pop     r14
0x180073418  pop     rdi
0x180073419  pop     rbx
0x18007341a  pop     rbp
0x18007341b  retn
```
