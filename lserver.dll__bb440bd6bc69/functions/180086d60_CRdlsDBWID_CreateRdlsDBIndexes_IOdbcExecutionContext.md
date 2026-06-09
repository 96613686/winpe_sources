# CRdlsDBWID::CreateRdlsDBIndexes(IOdbcExecutionContext *)

- ea: `0x180086d60`
- end: `0x180086f7c`
- name: `?CreateRdlsDBIndexes@CRdlsDBWID@@IEAAJPEAVIOdbcExecutionContext@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(CRdlsDBWID *__hidden this, struct IOdbcExecutionContext *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18008757c`

## callees

- `0x180077e9c`
- `0x180086d60`
- `0x180088e68`
- `0x1800a0fb0`
- `0x1800a5010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180086dfa`
- `ADVAPI32!RegQueryValueExW` at `0x180086dfa`
- `ADVAPI32!RegOpenKeyExW` at `0x180086dbd`
- `ADVAPI32!RegOpenKeyExW` at `0x180086dbd`

## string_xrefs

- `0x180086d92`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Parameters`
- `0x180086e21`: `CREATE NONCLUSTERED INDEX[IssuedLicense_ClientHwid_idx] ON[Rdls].[IssuedLicense]                                        ([SystemBIOS] ASC, [VideoBIOS] ASC, [FloppyBIOS] ASC, [HarddiskSize] ASC, [RAMSize] ASC)`
- `0x180086e4f`: `CREATE NONCLUSTERED INDEX[IssuedLicense_LastModifyTime_idx] ON[Rdls].[IssuedLicense]([LastModifyTime] ASC)`
- `0x180086e44`: `CREATE UNIQUE NONCLUSTERED INDEX[IssuedLicense_KpkID_LicID_idx] ON[Rdls].[IssuedLicense]([InternalKeyPackId] ASC, [InternalLicenseID] ASC)`
- `0x180086e39`: `CREATE NONCLUSTERED INDEX[IssuedLicense_InternalKeyPackId_idx] ON[Rdls].[IssuedLicense]([InternalKeyPackId] ASC)`
- `0x180086e2e`: `CREATE NONCLUSTERED INDEX[IssuedLicense_ExpireDate_idx] ON[Rdls].[IssuedLicense]([ExpireDate] ASC)`
- `0x180086e7b`: `CREATE NONCLUSTERED INDEX[LicensedPack_AllocateLicense_idx] ON[Rdls].[LicensedPack]                                        ([AgreementType] ASC, [ProductMajorVersion] ASC, [ProductMinorVersion] ASC, [PlatformType] ASC, [CompanyName] ASC, [ProductID] ASC)`
- `0x180086e70`: `CREATE NONCLUSTERED INDEX[IssuedLicense_UserName_idx] ON[Rdls].[IssuedLicense]([UserName] ASC)`
- `0x180086e65`: `CREATE NONCLUSTERED INDEX[IssuedLicense_MachineName_idx] ON[Rdls].[IssuedLicense]([MachineName] ASC)`
- `0x180086e5a`: `CREATE NONCLUSTERED INDEX[IssuedLicense_MatchHwid_idx] ON[Rdls].[IssuedLicense]([MatchHint1] ASC)`
- `0x180086ea7`: `CREATE NONCLUSTERED INDEX[LicensedPack_LPID_idx] ON[Rdls].[LicensedPack]([LPID] ASC)`
- `0x180086e9c`: `CREATE NONCLUSTERED INDEX[LicensedPack_LastModifyTime_idx] ON[Rdls].[LicensedPack]([LastModifyTime] ASC)`
- `0x180086e91`: `CREATE NONCLUSTERED INDEX[LicensedPack_InstalledProduct_idx] ON[Rdls].[LicensedPack]                                        ([LPID] ASC, [ProductMajorVersion] ASC, [ProductMinorVersion] ASC, [PlatformType] ASC, [CompanyName] ASC, [ProductID] ASC)`
- `0x180086e86`: `CREATE NONCLUSTERED INDEX[LicensedPack_CompanyName_idx] ON[Rdls].[LicensedPack]([CompanyName] ASC)`
- `0x180086ed3`: `CREATE UNIQUE NONCLUSTERED INDEX[WorkStorage_ScheduledTime_idx] ON[Rdls].[WorkStorage]([ScheduledTime] ASC)`
- `0x180086ec8`: `CREATE UNIQUE NONCLUSTERED INDEX[RdlsSecrets_RdlsUUID_RdlsName_idx] ON[Rdls].[RdlsSecrets]([RdlsUUID] ASC, [RdlsName] ASC)`
- `0x180086ebd`: `CREATE NONCLUSTERED INDEX[LicensedPackDesc_KpkID_LangId_idx] ON[Rdls].[LICPACKDESCRECORD]([InternalKeyPackId] ASC, [LangId] ASC)`
- `0x180086eb2`: `CREATE NONCLUSTERED INDEX[LicensedPack_ProductID_idx] ON[Rdls].[LicensedPack]([ProductID] ASC)`
- `0x180086f25`: `pOdbcExecContext->ExecuteSql, CreateRdlsDBIndexes`

## pseudocode

```c
__int64 __fastcall CRdlsDBWID::CreateRdlsDBIndexes(CRdlsDBWID *this, struct IOdbcExecutionContext *a2)
{
  int v3; // edi
  __int64 v5; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  BYTE Data[4]; // [rsp+38h] [rbp-69h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-65h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-61h] BYREF
  _QWORD v10[17]; // [rsp+48h] [rbp-59h]
  __int128 v11; // [rsp+D0h] [rbp+2Fh]
  __int64 v12; // [rsp+E0h] [rbp+3Fh]

  hKey = 0;
  v12 = 0;
  v3 = 0;
  v11 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Parameters",
          0,
          1u,
          &hKey) )
  {
    *(_DWORD *)Data = 0;
    cbData = 4;
    RegQueryValueExW(hKey, L"SkipDBIndexCreation", 0, 0, Data, &cbData);
    if ( *(_DWORD *)Data )
      return 0;
  }
  if ( !a2 )
    return 2147942487LL;
  v5 = 0;
  v10[0] = L"CREATE NONCLUSTERED INDEX[IssuedLicense_ClientHwid_idx] ON[Rdls].[IssuedLicense]                             "
            "           ([SystemBIOS] ASC, [VideoBIOS] ASC, [FloppyBIOS] ASC, [HarddiskSize] ASC, [RAMSize] ASC)";
  v10[1] = L"CREATE NONCLUSTERED INDEX[IssuedLicense_ExpireDate_idx] ON[Rdls].[IssuedLicense]([ExpireDate] ASC)";
  v10[2] = L"CREATE NONCLUSTERED INDEX[IssuedLicense_InternalKeyPackId_idx] ON[Rdls].[IssuedLicense]([InternalKeyPackId] ASC)";
  v10[3] = L"CREATE UNIQUE NONCLUSTERED INDEX[IssuedLicense_KpkID_LicID_idx] ON[Rdls].[IssuedLicense]([InternalKeyPackId] "
            "ASC, [InternalLicenseID] ASC)";
  v10[4] = L"CREATE NONCLUSTERED INDEX[IssuedLicense_LastModifyTime_idx] ON[Rdls].[IssuedLicense]([LastModifyTime] ASC)";
  v10[5] = L"CREATE NONCLUSTERED INDEX[IssuedLicense_MatchHwid_idx] ON[Rdls].[IssuedLicense]([MatchHint1] ASC)";
  v10[6] = L"CREATE NONCLUSTERED INDEX[IssuedLicense_MachineName_idx] ON[Rdls].[IssuedLicense]([MachineName] ASC)";
  v10[7] = L"CREATE NONCLUSTERED INDEX[IssuedLicense_UserName_idx] ON[Rdls].[IssuedLicense]([UserName] ASC)";
  v10[8] = L"CREATE NONCLUSTERED INDEX[LicensedPack_AllocateLicense_idx] ON[Rdls].[LicensedPack]                          "
            "              ([AgreementType] ASC, [ProductMajorVersion] ASC, [ProductMinorVersion] ASC, [PlatformType] ASC"
            ", [CompanyName] ASC, [ProductID] ASC)";
  v10[9] = L"CREATE NONCLUSTERED INDEX[LicensedPack_CompanyName_idx] ON[Rdls].[LicensedPack]([CompanyName] ASC)";
  v10[10] = L"CREATE NONCLUSTERED INDEX[LicensedPack_InstalledProduct_idx] ON[Rdls].[LicensedPack]                        "
             "                ([LPID] ASC, [ProductMajorVersion] ASC, [ProductMinorVersion] ASC, [PlatformType] ASC, [Com"
             "panyName] ASC, [ProductID] ASC)";
  v10[11] = L"CREATE NONCLUSTERED INDEX[LicensedPack_LastModifyTime_idx] ON[Rdls].[LicensedPack]([LastModifyTime] ASC)";
  v10[12] = L"CREATE NONCLUSTERED INDEX[LicensedPack_LPID_idx] ON[Rdls].[LicensedPack]([LPID] ASC)";
  v10[13] = L"CREATE NONCLUSTERED INDEX[LicensedPack_ProductID_idx] ON[Rdls].[LicensedPack]([ProductID] ASC)";
  v10[14] = L"CREATE NONCLUSTERED INDEX[LicensedPackDesc_KpkID_LangId_idx] ON[Rdls].[LICPACKDESCRECORD]([InternalKeyPackId"
             "] ASC, [LangId] ASC)";
  v10[15] = L"CREATE UNIQUE NONCLUSTERED INDEX[RdlsSecrets_RdlsUUID_RdlsName_idx] ON[Rdls].[RdlsSecrets]([RdlsUUID] ASC, [RdlsName] ASC)";
  v10[16] = L"CREATE UNIQUE NONCLUSTERED INDEX[WorkStorage_ScheduledTime_idx] ON[Rdls].[WorkStorage]([ScheduledTime] ASC)";
  while ( (unsigned int)v5 < 0x11 )
  {
    v3 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD))(*(_QWORD *)a2 + 112LL))(a2, v10[v5]);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_c9aedbd3feee3e98c50752067cbb8264_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"pOdbcExecContext->ExecuteSql, CreateRdlsDBIndexes",
          v3);
      }
      return (unsigned int)v3;
    }
    v5 = (unsigned int)(v5 + 1);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180086d60  mov     rax, rsp
0x180086d63  mov     [rax+8], rbx
0x180086d67  mov     [rax+18h], rsi
0x180086d6b  mov     [rax+20h], rdi
0x180086d6f  push    rbp
0x180086d70  lea     rbp, [rax-5Fh]
0x180086d74  sub     rsp, 0F0h
0x180086d7b  mov     rax, cs:__security_cookie
0x180086d82  xor     rax, rsp
0x180086d85  mov     [rbp+57h+var_10], rax
0x180086d89  xor     eax, eax
0x180086d8b  mov     rsi, rdx
0x180086d8e  and     [rbp+57h+hKey], rax
0x180086d92  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x180086d99  mov     [rbp+57h+var_18], rax
0x180086d9d  xorps   xmm0, xmm0
0x180086da0  lea     rax, [rbp+57h+hKey]
0x180086da4  xor     edi, edi
0x180086da6  xor     r8d, r8d; ulOptions
0x180086da9  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180086dae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180086db5  movups  [rbp+57h+var_28], xmm0
0x180086db9  lea     r9d, [rdi+1]; samDesired
0x180086dbd  call    cs:__imp_RegOpenKeyExW
0x180086dc4  nop     dword ptr [rax+rax+00h]
0x180086dc9  test    eax, eax
0x180086dcb  jnz     short loc_180086E12
0x180086dcd  mov     rcx, [rbp+57h+hKey]; hKey
0x180086dd1  lea     rax, [rbp+57h+cbData]
0x180086dd5  and     dword ptr [rbp+57h+Data], edi
0x180086dd8  lea     rdx, aSkipdbindexcre; "SkipDBIndexCreation"
0x180086ddf  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x180086de4  xor     r9d, r9d; lpType
0x180086de7  lea     rax, [rbp+57h+Data]
0x180086deb  mov     [rbp+57h+cbData], 4
0x180086df2  xor     r8d, r8d; lpReserved
0x180086df5  mov     [rsp+0F0h+phkResult], rax; lpData
0x180086dfa  call    cs:__imp_RegQueryValueExW
0x180086e01  nop     dword ptr [rax+rax+00h]
0x180086e06  cmp     dword ptr [rbp+57h+Data], edi
0x180086e09  jz      short loc_180086E12
0x180086e0b  xor     eax, eax
0x180086e0d  jmp     loc_180086F56
0x180086e12  test    rsi, rsi
0x180086e15  jnz     short loc_180086E21
0x180086e17  mov     eax, 80070057h
0x180086e1c  jmp     loc_180086F56
0x180086e21  lea     rax, aCreateNonclust_5; "CREATE NONCLUSTERED INDEX[IssuedLicense"...
0x180086e28  xor     ebx, ebx
0x180086e2a  mov     [rbp+57h+var_B0], rax
0x180086e2e  lea     rax, aCreateNonclust_6; "CREATE NONCLUSTERED INDEX[IssuedLicense"...
0x180086e35  mov     [rbp+57h+var_A8], rax
0x180086e39  lea     rax, aCreateNonclust_12; "CREATE NONCLUSTERED INDEX[IssuedLicense"...
0x180086e40  mov     [rbp+57h+var_A0], rax
0x180086e44  lea     rax, aCreateUniqueNo_0; "CREATE UNIQUE NONCLUSTERED INDEX[Issued"...
0x180086e4b  mov     [rbp+57h+var_98], rax
0x180086e4f  lea     rax, aCreateNonclust_2; "CREATE NONCLUSTERED INDEX[IssuedLicense"...
0x180086e56  mov     [rbp+57h+var_90], rax
0x180086e5a  lea     rax, aCreateNonclust_11; "CREATE NONCLUSTERED INDEX[IssuedLicense"...
0x180086e61  mov     [rbp+57h+var_88], rax
0x180086e65  lea     rax, aCreateNonclust_1; "CREATE NONCLUSTERED INDEX[IssuedLicense"...
0x180086e6c  mov     [rbp+57h+var_80], rax
0x180086e70  lea     rax, aCreateNonclust; "CREATE NONCLUSTERED INDEX[IssuedLicense"...
0x180086e77  mov     [rbp+57h+var_78], rax
0x180086e7b  lea     rax, aCreateNonclust_8; "CREATE NONCLUSTERED INDEX[LicensedPack_"...
0x180086e82  mov     [rbp+57h+var_70], rax
0x180086e86  lea     rax, aCreateNonclust_10; "CREATE NONCLUSTERED INDEX[LicensedPack_"...
0x180086e8d  mov     [rbp+57h+var_68], rax
0x180086e91  lea     rax, aCreateNonclust_0; "CREATE NONCLUSTERED INDEX[LicensedPack_"...
0x180086e98  mov     [rbp+57h+var_60], rax
0x180086e9c  lea     rax, aCreateNonclust_7; "CREATE NONCLUSTERED INDEX[LicensedPack_"...
0x180086ea3  mov     [rbp+57h+var_58], rax
0x180086ea7  lea     rax, aCreateNonclust_4; "CREATE NONCLUSTERED INDEX[LicensedPack_"...
0x180086eae  mov     [rbp+57h+var_50], rax
0x180086eb2  lea     rax, aCreateNonclust_3; "CREATE NONCLUSTERED INDEX[LicensedPack_"...
0x180086eb9  mov     [rbp+57h+var_48], rax
0x180086ebd  lea     rax, aCreateNonclust_9; "CREATE NONCLUSTERED INDEX[LicensedPackD"...
0x180086ec4  mov     [rbp+57h+var_40], rax
0x180086ec8  lea     rax, aCreateUniqueNo_1; "CREATE UNIQUE NONCLUSTERED INDEX[RdlsSe"...
0x180086ecf  mov     [rbp+57h+var_38], rax
0x180086ed3  lea     rax, aCreateUniqueNo; "CREATE UNIQUE NONCLUSTERED INDEX[WorkSt"...
0x180086eda  mov     [rbp+57h+var_30], rax
0x180086ede  cmp     ebx, 11h
0x180086ee1  jnb     short loc_180086F54
0x180086ee3  mov     rax, [rsi]
0x180086ee6  mov     rcx, rsi
0x180086ee9  mov     rdx, [rbp+rbx*8+57h+var_B0]
0x180086eee  mov     rax, [rax+70h]
0x180086ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086ef7  mov     edi, eax
0x180086ef9  test    eax, eax
0x180086efb  js      short loc_180086F01
0x180086efd  inc     ebx
0x180086eff  jmp     short loc_180086EDE
0x180086f01  mov     rax, cs:WPP_GLOBAL_Control
0x180086f08  lea     rcx, WPP_GLOBAL_Control
0x180086f0f  cmp     rax, rcx
0x180086f12  jz      short loc_180086F54
0x180086f14  test    byte ptr [rax+1Ch], 8
0x180086f18  jz      short loc_180086F54
0x180086f1a  cmp     byte ptr [rax+19h], 2
0x180086f1e  jb      short loc_180086F54
0x180086f20  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180086f25  lea     rcx, aPodbcexecconte_3; "pOdbcExecContext->ExecuteSql, CreateRdl"...
0x180086f2c  mov     dword ptr [rsp+0F0h+lpcbData], edi
0x180086f30  mov     [rsp+0F0h+phkResult], rcx
0x180086f35  lea     r8, WPP_c9aedbd3feee3e98c50752067cbb8264_Traceguids
0x180086f3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180086f43  mov     edx, 11h
0x180086f48  mov     r9d, eax
0x180086f4b  mov     rcx, [rcx+10h]
0x180086f4f  call    WPP_SF_DsD
0x180086f54  mov     eax, edi
0x180086f56  mov     rcx, [rbp+57h+var_10]
0x180086f5a  xor     rcx, rsp; StackCookie
0x180086f5d  call    __security_check_cookie
0x180086f62  lea     r11, [rsp+0F0h+var_s0]
0x180086f6a  mov     rbx, [r11+10h]
0x180086f6e  mov     rsi, [r11+20h]
0x180086f72  mov     rdi, [r11+28h]
0x180086f76  mov     rsp, r11
0x180086f79  pop     rbp
0x180086f7a  retn
```
