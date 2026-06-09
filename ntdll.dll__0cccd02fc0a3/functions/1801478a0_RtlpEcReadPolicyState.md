# RtlpEcReadPolicyState

- ea: `0x1801478a0`
- end: `0x180147940`
- name: `RtlpEcReadPolicyState`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180147820`

## callees

- `0x1801478a0`
- `0x1801479d4`

## string_xrefs

- `0x1801478bf`: `TemporaryEnterpriseFeatureControlState`
- `0x1801478b8`: `\UpdatePolicy\PolicyState`
- `0x180147904`: `TemporaryEnterpriseFeatureControlState_Mirrored`
- `0x1801478d4`: `\Registry\Machine\SOFTWARE\Microsoft\WindowsUpdate`
- `0x1801478db`: `WindowsUpdate`
- `0x18014790b`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\FeatureManagement`

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
0x1801478a0  push    rbx
0x1801478a2  sub     rsp, 30h
0x1801478a6  lea     rax, [rsp+38h+arg_8]
0x1801478ab  mov     [rsp+38h+arg_8], 0
0x1801478b3  mov     [rsp+38h+var_10], rax
0x1801478b8  lea     r9, aUpdatepolicyPo; "\\UpdatePolicy\\PolicyState"
0x1801478bf  lea     rax, aTemporaryenter_0; "TemporaryEnterpriseFeatureControlState"
0x1801478c6  mov     rbx, rcx
0x1801478c9  mov     r8d, 1Ah
0x1801478cf  mov     [rsp+38h+var_18], rax
0x1801478d4  lea     rdx, aRegistryMachin_31; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1801478db  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x1801478e2  call    RtlpEtcGetDwordFromPersistedState
0x1801478e7  mov     edx, eax
0x1801478e9  test    eax, eax
0x1801478eb  jns     short loc_180147929
0x1801478ed  lea     rax, [rsp+38h+arg_8]
0x1801478f2  mov     r8d, 0Ah
0x1801478f8  mov     [rsp+38h+var_10], rax
0x1801478fd  lea     r9, aPolicies; "\\Policies"
0x180147904  lea     rax, aTemporaryenter; "TemporaryEnterpriseFeatureControlState_"...
0x18014790b  lea     rdx, aRegistryMachin_30; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x180147912  mov     [rsp+38h+var_18], rax
0x180147917  lea     rcx, aFeaturemanagem; "FeatureManagement"
0x18014791e  call    RtlpEtcGetDwordFromPersistedState
0x180147923  mov     edx, eax
0x180147925  test    eax, eax
0x180147927  js      short loc_180147937
0x180147929  mov     eax, [rsp+38h+arg_8]
0x18014792d  dec     eax
0x18014792f  cmp     eax, 1
0x180147932  setbe   al
0x180147935  mov     [rbx], al
0x180147937  mov     eax, edx
0x180147939  add     rsp, 30h
0x18014793d  pop     rbx
0x18014793e  retn
```
