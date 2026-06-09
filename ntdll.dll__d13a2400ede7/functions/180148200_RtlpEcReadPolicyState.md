# RtlpEcReadPolicyState

- ea: `0x180148200`
- end: `0x1801482a0`
- name: `RtlpEcReadPolicyState`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180148180`

## callees

- `0x180148200`
- `0x180148334`

## string_xrefs

- `0x18014821f`: `TemporaryEnterpriseFeatureControlState`
- `0x180148218`: `\UpdatePolicy\PolicyState`
- `0x180148264`: `TemporaryEnterpriseFeatureControlState_Mirrored`
- `0x180148234`: `\Registry\Machine\SOFTWARE\Microsoft\WindowsUpdate`
- `0x18014823b`: `WindowsUpdate`
- `0x18014826b`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\FeatureManagement`

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
0x180148200  push    rbx
0x180148202  sub     rsp, 30h
0x180148206  lea     rax, [rsp+38h+arg_8]
0x18014820b  mov     [rsp+38h+arg_8], 0
0x180148213  mov     [rsp+38h+var_10], rax
0x180148218  lea     r9, aUpdatepolicyPo; "\\UpdatePolicy\\PolicyState"
0x18014821f  lea     rax, aTemporaryenter_0; "TemporaryEnterpriseFeatureControlState"
0x180148226  mov     rbx, rcx
0x180148229  mov     r8d, 1Ah
0x18014822f  mov     [rsp+38h+var_18], rax
0x180148234  lea     rdx, aRegistryMachin_31; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18014823b  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x180148242  call    RtlpEtcGetDwordFromPersistedState
0x180148247  mov     edx, eax
0x180148249  test    eax, eax
0x18014824b  jns     short loc_180148289
0x18014824d  lea     rax, [rsp+38h+arg_8]
0x180148252  mov     r8d, 0Ah
0x180148258  mov     [rsp+38h+var_10], rax
0x18014825d  lea     r9, aPolicies; "\\Policies"
0x180148264  lea     rax, aTemporaryenter; "TemporaryEnterpriseFeatureControlState_"...
0x18014826b  lea     rdx, aRegistryMachin_30; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x180148272  mov     [rsp+38h+var_18], rax
0x180148277  lea     rcx, aFeaturemanagem; "FeatureManagement"
0x18014827e  call    RtlpEtcGetDwordFromPersistedState
0x180148283  mov     edx, eax
0x180148285  test    eax, eax
0x180148287  js      short loc_180148297
0x180148289  mov     eax, [rsp+38h+arg_8]
0x18014828d  dec     eax
0x18014828f  cmp     eax, 1
0x180148292  setbe   al
0x180148295  mov     [rbx], al
0x180148297  mov     eax, edx
0x180148299  add     rsp, 30h
0x18014829d  pop     rbx
0x18014829e  retn
```
