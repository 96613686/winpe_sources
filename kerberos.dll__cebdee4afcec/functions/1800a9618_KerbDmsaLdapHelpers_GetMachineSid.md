# KerbDmsaLdapHelpers::GetMachineSid

- ea: `0x1800a9618`
- end: `0x1800a9702`
- name: `KerbDmsaLdapHelpers::GetMachineSid`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a8380`

## callees

- `0x1800093f0`
- `0x180032964`
- `0x18008b70c`
- `0x1800a9618`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a96b6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a96b6`
- `ntdll!RtlValidSid` at `0x1800a967e`
- `ntdll!RtlValidSid` at `0x1800a967e`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x1800a96ef`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x1800a96ef`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x1800a9645`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x1800a9645`

## string_xrefs

- `0x1800a9662`: `KerbDmsaLdapHelpers::GetMachineSid`
- `0x1800a96cd`: `KerbDmsaLdapHelpers::GetMachineSid`
- `0x1800a96c0`: `CopySid failed\n`

## pseudocode

```c
__int64 __fastcall KerbDmsaLdapHelpers::GetMachineSid(_QWORD *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rcx
  void *v5; // rax
  __int64 v7; // [rsp+58h] [rbp+10h] BYREF

  v7 = 0;
  v2 = LsaIQueryInformationPolicyTrusted(15, &v7);
  v3 = v2;
  if ( v2 >= 0 )
  {
    if ( !RtlValidSid(*(PSID *)(v7 + 8)) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v4);
    v5 = MIDL_user_allocate(0x44u);
    *a1 = v5;
    if ( v5 )
    {
      if ( CopySid(0x44u, v5, *(PSID *)(v7 + 8)) )
      {
        v3 = 0;
      }
      else
      {
        KerbTracerT::Log(1, "KerbDmsaLdapHelpers::GetMachineSid", 2296, "CopySid failed\n");
        v3 = -1073741595;
      }
    }
    else
    {
      v3 = -1073741801;
    }
  }
  else
  {
    KerbTracerT::Log(
      1,
      "KerbDmsaLdapHelpers::GetMachineSid",
      2283,
      "LsaIQueryInformationPolicyTrusted failed to get machine account info Status: %#x\n",
      v2);
  }
  LsaIFree_LSAPR_POLICY_INFORMATION(15, v7);
  return v3;
}

```

## disassembly

```asm
0x1800a9618  mov     r11, rsp
0x1800a961b  mov     [r11+8], rbx
0x1800a961f  push    rdi
0x1800a9620  sub     rsp, 40h
0x1800a9624  mov     rdi, rcx
0x1800a9627  mov     qword ptr [r11+10h], 0
0x1800a962f  lea     rax, [r11+10h]
0x1800a9633  mov     [r11-18h], rax
0x1800a9637  mov     [rsp+48h+var_10], 1
0x1800a963c  lea     rdx, [r11+10h]
0x1800a9640  mov     ecx, 0Fh
0x1800a9645  call    cs:__imp_LsaIQueryInformationPolicyTrusted
0x1800a964b  mov     ebx, eax
0x1800a964d  test    eax, eax
0x1800a964f  jns     short loc_1800A9675
0x1800a9651  mov     [rsp+48h+var_28], eax
0x1800a9655  lea     r9, aLsaiqueryinfor_0; "LsaIQueryInformationPolicyTrusted faile"...
0x1800a965c  mov     r8d, 8EBh
0x1800a9662  lea     rdx, aKerbdmsaldaphe; "KerbDmsaLdapHelpers::GetMachineSid"
0x1800a9669  mov     ecx, 1
0x1800a966e  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a9673  jmp     short loc_1800A96E5
0x1800a9675  mov     rcx, [rsp+48h+arg_8]
0x1800a967a  mov     rcx, [rcx+8]; Sid
0x1800a967e  call    cs:__imp_RtlValidSid
0x1800a9684  test    al, al
0x1800a9686  jnz     short loc_1800A968D
0x1800a9688  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a968d  mov     ebx, 44h ; 'D'
0x1800a9692  mov     ecx, ebx; size
0x1800a9694  call    MIDL_user_allocate
0x1800a9699  mov     [rdi], rax
0x1800a969c  test    rax, rax
0x1800a969f  jnz     short loc_1800A96A8
0x1800a96a1  mov     ebx, 0C0000017h
0x1800a96a6  jmp     short loc_1800A96E5
0x1800a96a8  mov     r8, [rsp+48h+arg_8]
0x1800a96ad  mov     r8, [r8+8]; pSourceSid
0x1800a96b1  mov     rdx, rax; pDestinationSid
0x1800a96b4  mov     ecx, ebx; nDestinationSidLength
0x1800a96b6  call    cs:__imp_CopySid
0x1800a96bc  test    eax, eax
0x1800a96be  jnz     short loc_1800A96E3
0x1800a96c0  lea     r9, aCopysidFailed; "CopySid failed\n"
0x1800a96c7  mov     r8d, 8F8h
0x1800a96cd  lea     rdx, aKerbdmsaldaphe; "KerbDmsaLdapHelpers::GetMachineSid"
0x1800a96d4  lea     ecx, [rax+1]
0x1800a96d7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a96dc  mov     ebx, 0C00000E5h
0x1800a96e1  jmp     short loc_1800A96E5
0x1800a96e3  xor     ebx, ebx
0x1800a96e5  mov     rdx, [rsp+48h+arg_8]
0x1800a96ea  mov     ecx, 0Fh
0x1800a96ef  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x1800a96f5  mov     eax, ebx
0x1800a96f7  mov     rbx, [rsp+48h+arg_0]
0x1800a96fc  add     rsp, 40h
0x1800a9700  pop     rdi
0x1800a9701  retn
```
