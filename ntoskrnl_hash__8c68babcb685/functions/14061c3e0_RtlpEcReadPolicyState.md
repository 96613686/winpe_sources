# RtlpEcReadPolicyState

- ea: `0x14061c3e0`
- end: `0x14061c480`
- name: `RtlpEcReadPolicyState`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14061c360`

## callees

- `0x14061c3e0`
- `0x14061c514`

## string_xrefs

- `0x14061c41b`: `WindowsUpdate`
- `0x14061c414`: `\Registry\Machine\SOFTWARE\Microsoft\WindowsUpdate`
- `0x14061c3f8`: `\UpdatePolicy\PolicyState`
- `0x14061c3ff`: `TemporaryEnterpriseFeatureControlState`
- `0x14061c44b`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\FeatureManagement`
- `0x14061c444`: `TemporaryEnterpriseFeatureControlState_Mirrored`

## pseudocode

```c
__int64 __fastcall RtlpEcReadPolicyState(bool *a1)
{
  int DwordFromPersistedState; // edx
  int v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  DwordFromPersistedState = RtlpEtcGetDwordFromPersistedState(
                              (unsigned int)L"WindowsUpdate",
                              (unsigned int)L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\WindowsUpdate",
                              26,
                              (unsigned int)L"\\UpdatePolicy\\PolicyState",
                              (__int64)L"TemporaryEnterpriseFeatureControlState",
                              (__int64)&v4);
  if ( DwordFromPersistedState >= 0
    || (DwordFromPersistedState = RtlpEtcGetDwordFromPersistedState(
                                    (unsigned int)L"FeatureManagement",
                                    (unsigned int)L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\FeatureManagement",
                                    10,
                                    (unsigned int)L"\\Policies",
                                    (__int64)L"TemporaryEnterpriseFeatureControlState_Mirrored",
                                    (__int64)&v4),
        DwordFromPersistedState >= 0) )
  {
    *a1 = (unsigned int)(v4 - 1) <= 1;
  }
  return (unsigned int)DwordFromPersistedState;
}

```

## disassembly

```asm
0x14061c3e0  push    rbx
0x14061c3e2  sub     rsp, 30h
0x14061c3e6  lea     rax, [rsp+38h+arg_8]
0x14061c3eb  mov     [rsp+38h+arg_8], 0
0x14061c3f3  mov     [rsp+38h+var_10], rax
0x14061c3f8  lea     r9, aUpdatepolicyPo; "\\UpdatePolicy\\PolicyState"
0x14061c3ff  lea     rax, aTemporaryenter_0; "TemporaryEnterpriseFeatureControlState"
0x14061c406  mov     rbx, rcx
0x14061c409  mov     r8d, 1Ah
0x14061c40f  mov     [rsp+38h+var_18], rax
0x14061c414  lea     rdx, aRegistryMachin_176; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x14061c41b  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x14061c422  call    RtlpEtcGetDwordFromPersistedState
0x14061c427  mov     edx, eax
0x14061c429  test    eax, eax
0x14061c42b  jns     short loc_14061C469
0x14061c42d  lea     rax, [rsp+38h+arg_8]
0x14061c432  mov     r8d, 0Ah
0x14061c438  mov     [rsp+38h+var_10], rax
0x14061c43d  lea     r9, aPolicies_0; "\\Policies"
0x14061c444  lea     rax, aTemporaryenter; "TemporaryEnterpriseFeatureControlState_"...
0x14061c44b  lea     rdx, aRegistryMachin_172; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14061c452  mov     [rsp+38h+var_18], rax
0x14061c457  lea     rcx, aFeaturemanagem; "FeatureManagement"
0x14061c45e  call    RtlpEtcGetDwordFromPersistedState
0x14061c463  mov     edx, eax
0x14061c465  test    eax, eax
0x14061c467  js      short loc_14061C477
0x14061c469  mov     eax, [rsp+38h+arg_8]
0x14061c46d  dec     eax
0x14061c46f  cmp     eax, 1
0x14061c472  setbe   al
0x14061c475  mov     [rbx], al
0x14061c477  mov     eax, edx
0x14061c479  add     rsp, 30h
0x14061c47d  pop     rbx
0x14061c47e  retn
```
