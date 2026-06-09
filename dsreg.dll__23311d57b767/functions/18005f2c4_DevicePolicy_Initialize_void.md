# DevicePolicy::Initialize(void)

- ea: `0x18005f2c4`
- end: `0x18005f5be`
- name: `?Initialize@DevicePolicy@@IEAAXXZ`
- size: `762`
- prototype: `void __fastcall(DevicePolicy *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005f178`

## callees

- `0x18000468c`
- `0x1800048cc`
- `0x1800059d0`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180012948`
- `0x180031ae0`
- `0x18005f2c4`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x18005f324`
- `ntdll!RtlIsMultiSessionSku` at `0x18005f324`
- `ntdll!ZwQueryLicenseValue` at `0x18005f350`
- `ntdll!ZwQueryLicenseValue` at `0x18005f350`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18005f31e`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18005f31e`

## string_xrefs

- `0x18005f4c1`: `Logger::WriteUnsupportedRegistryHardwarePolicyValueEvent`
- `0x18005f4ba`: `EventWriteUnsupportedRegistryHardwarePolicyValueEvent`
- `0x18005f44e`: `Logger::WriteUnsupportedRegistryKeyPolicyValueEvent`
- `0x18005f447`: `EventWriteUnsupportedRegistryKeyPolicyValueEvent`
- `0x18005f384`: `%s: Reading license value (AAD-AddDeviceJoinUserToAdminGroup-Policy) failed with error 0x%08x. Using default (%lu).`
- `0x18005f415`: `%s: Registry key policy is set to unsupported value %lu.`
- `0x18005f488`: `%s: Registry hardware policy is set to unsupported value %lu.`
- `0x18005f507`: `%s: Registry key policy is not defined. Using default (%lu).`
- `0x18005f4e0`: `%s: Registry key policy is defined (%lu).`
- `0x18005f528`: `%s: Registry hardware policy is not defined. Using default (%lu).`
- `0x18005f53f`: `%s: Registry hardware policy is defined (%lu).`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DevicePolicy::Initialize(DevicePolicy *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  unsigned int v3; // edi
  unsigned int v4; // eax
  unsigned int v5; // eax
  const wchar_t *v6; // r9
  __int64 v7; // [rsp+20h] [rbp-39h]
  _QWORD v8[2]; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v9[4]; // [rsp+50h] [rbp-9h] BYREF
  __int128 v10; // [rsp+70h] [rbp+17h]
  __int64 v11; // [rsp+80h] [rbp+27h]
  __int64 v12; // [rsp+88h] [rbp+2Fh]
  unsigned int v13; // [rsp+C0h] [rbp+67h] BYREF
  int v14; // [rsp+C4h] [rbp+6Bh]
  unsigned int v15; // [rsp+C8h] [rbp+6Fh] BYREF
  unsigned int v16; // [rsp+D0h] [rbp+77h] BYREF
  int v17; // [rsp+D8h] [rbp+7Fh] BYREF

  v14 = HIDWORD(this);
  v13 = 0;
  v17 = 0;
  v8[0] = 5374032;
  v8[1] = L"AAD-AddDeviceJoinUserToAdminGroup-Policy";
  Logger::TraceVerbose((wchar_t *)L"%s started", L"DevicePolicy::Initialize");
  dword_180142590 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &dword_180142590, 0);
  dword_180142594 = (unsigned __int8)RtlIsMultiSessionSku();
  dword_18014259C = 0;
  v1 = ZwQueryLicenseValue(v8, 0, &v13, 4, &v17);
  if ( v1 < 0 )
  {
    Logger::TraceWarning(
      (wchar_t *)L"%s: Reading license value (AAD-AddDeviceJoinUserToAdminGroup-Policy) failed with error 0x%08x. Using default (%lu).",
      L"DevicePolicy::Initialize",
      (unsigned int)v1,
      (unsigned int)dword_18014259C);
  }
  else if ( v13 && v13 - 1 >= 2 )
  {
    Logger::TraceWarning(
      L"%s: Invalid license value (AAD-AddDeviceJoinUserToAdminGroup-Policy) %lu. Using default (%lu).",
      L"DevicePolicy::Initialize",
      v13,
      (unsigned int)dword_18014259C);
  }
  else
  {
    dword_18014259C = v13;
  }
  memset(v9, 0, sizeof(v9));
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v15 = 0;
  v2 = 0;
  v16 = 0;
  if ( (int)RegistryPath::InitializePersistedStatePath(
              (RegistryPath *)v9,
              L"PoliciesWindows",
              L"Software\\Policies\\Microsoft\\Windows",
              L"WorkplaceJoin") < 0 )
    goto LABEL_21;
  RegistryPath::ReadDwordValue((RegistryPath *)v9, L"KeyPolicy", &v15, 0);
  v3 = v15;
  if ( (v15 & 0xFFFFFFFC) != 0 || v15 == 2 )
  {
    Logger::TraceError(L"%s: Registry key policy is set to unsupported value %lu.", L"DevicePolicy::Initialize", v15);
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 4) != 0 )
    {
      v4 = McTemplateU0q_EventWriteTransfer(
             &UserDeviceRegistrationEventProvider_Context,
             UnsupportedRegistryKeyPolicyValueEvent,
             v3);
      if ( v4 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteUnsupportedRegistryKeyPolicyValueEvent",
          L"EventWriteUnsupportedRegistryKeyPolicyValueEvent",
          v4);
    }
    v3 = 0;
  }
  RegistryPath::ReadDwordValue((RegistryPath *)v9, L"HwPolicy", &v16, 0);
  v2 = v16;
  if ( v16 >= 4 )
  {
    Logger::TraceError(
      L"%s: Registry hardware policy is set to unsupported value %lu.",
      L"DevicePolicy::Initialize",
      v16);
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 4) != 0 )
    {
      v5 = McTemplateU0q_EventWriteTransfer(
             &UserDeviceRegistrationEventProvider_Context,
             UnsupportedRegistryHardwarePolicyValueEvent,
             v2);
      if ( v5 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteUnsupportedRegistryHardwarePolicyValueEvent",
          L"EventWriteUnsupportedRegistryHardwarePolicyValueEvent",
          v5);
    }
    v2 = 0;
  }
  if ( v3 )
  {
    Logger::TraceInformation(L"%s: Registry key policy is defined (%lu).", L"DevicePolicy::Initialize", v3);
    dword_180142598 = v3;
  }
  else
  {
LABEL_21:
    dword_180142598 = 1;
    Logger::TraceInformation(
      L"%s: Registry key policy is not defined. Using default (%lu).",
      L"DevicePolicy::Initialize",
      1);
  }
  if ( v2 )
  {
    Logger::TraceInformation(L"%s: Registry hardware policy is defined (%lu).", L"DevicePolicy::Initialize", v2);
    dword_1801425A0 = v2;
  }
  else
  {
    dword_1801425A0 = 1;
    Logger::TraceInformation(
      L"%s: Registry hardware policy is not defined. Using default (%lu).",
      L"DevicePolicy::Initialize",
      1);
    v2 = dword_1801425A0;
  }
  v6 = L"TRUE";
  if ( !dword_180142594 )
    v6 = L"FALSE";
  LODWORD(v7) = dword_180142598;
  Logger::TraceInformation(
    L"%s: Platform ID = %lu. Is multisession SKU: %s. KeyPolicy = %lu. HardwarePolicy = %lu. AddDeviceJoinUserToAdminGroup = %lu",
    L"DevicePolicy::Initialize",
    (unsigned int)dword_180142590,
    v6,
    v7,
    v2,
    dword_18014259C);
  Logger::TraceVerbose((wchar_t *)L"%s finished", L"DevicePolicy::Initialize");
  RegistryPath::Reset((RegistryPath *)v9);
}

```

## disassembly

```asm
0x18005f2c4  mov     [rsp-8+arg_0], rcx
0x18005f2c9  push    rbp
0x18005f2ca  push    rbx
0x18005f2cb  push    rsi
0x18005f2cc  push    rdi
0x18005f2cd  push    r14
0x18005f2cf  lea     rbp, [rsp-37h]
0x18005f2d4  sub     rsp, 90h
0x18005f2db  xor     esi, esi
0x18005f2dd  mov     dword ptr [rbp+57h+arg_0], esi
0x18005f2e0  mov     [rbp+57h+arg_18], esi
0x18005f2e3  mov     [rbp+57h+var_70], 520050h
0x18005f2eb  lea     rax, aAadAdddevicejo; "AAD-AddDeviceJoinUserToAdminGroup-Polic"...
0x18005f2f2  mov     [rbp+57h+var_68], rax
0x18005f2f6  lea     r14, aDevicepolicyIn; "DevicePolicy::Initialize"
0x18005f2fd  mov     rdx, r14
0x18005f300  lea     rcx, aSStarted; "%s started"
0x18005f307  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005f30c  mov     cs:dword_180142590, esi
0x18005f312  xor     r8d, r8d
0x18005f315  lea     rdx, dword_180142590
0x18005f31c  xor     ecx, ecx
0x18005f31e  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18005f324  call    cs:__imp_RtlIsMultiSessionSku
0x18005f32a  movzx   eax, al
0x18005f32d  mov     cs:dword_180142594, eax
0x18005f333  mov     cs:dword_18014259C, esi
0x18005f339  lea     rax, [rbp+57h+arg_18]
0x18005f33d  mov     [rsp+0B0h+var_90], rax
0x18005f342  lea     r9d, [rsi+4]
0x18005f346  lea     r8, [rbp+57h+arg_0]
0x18005f34a  xor     edx, edx
0x18005f34c  lea     rcx, [rbp+57h+var_70]
0x18005f350  call    cs:__imp_ZwQueryLicenseValue
0x18005f356  test    eax, eax
0x18005f358  js      short loc_18005F381
0x18005f35a  mov     edx, dword ptr [rbp+57h+arg_0]
0x18005f35d  mov     ecx, edx
0x18005f35f  test    edx, edx
0x18005f361  jz      short loc_18005F379
0x18005f363  sub     ecx, 1
0x18005f366  jz      short loc_18005F379
0x18005f368  cmp     ecx, 1
0x18005f36b  jz      short loc_18005F379
0x18005f36d  mov     r8d, edx
0x18005f370  lea     rcx, aSInvalidLicens; "%s: Invalid license value (AAD-AddDevic"...
0x18005f377  jmp     short loc_18005F38B
0x18005f379  mov     cs:dword_18014259C, edx
0x18005f37f  jmp     short loc_18005F39A
0x18005f381  mov     r8d, eax
0x18005f384  lea     rcx, aSReadingLicens; "%s: Reading license value (AAD-AddDevic"...
0x18005f38b  mov     r9d, cs:dword_18014259C
0x18005f392  mov     rdx, r14
0x18005f395  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18005f39a  mov     [rbp+57h+var_60], rsi
0x18005f39e  mov     [rbp+57h+var_58], rsi
0x18005f3a2  mov     [rbp+57h+var_50], rsi
0x18005f3a6  mov     [rbp+57h+var_48], rsi
0x18005f3aa  xorps   xmm0, xmm0
0x18005f3ad  movdqa  [rbp+57h+var_40], xmm0
0x18005f3b2  mov     [rbp+57h+var_30], rsi
0x18005f3b6  mov     [rbp+57h+var_28], rsi
0x18005f3ba  mov     [rbp+57h+arg_8], esi
0x18005f3bd  mov     ebx, esi
0x18005f3bf  mov     [rbp+57h+arg_10], ebx
0x18005f3c2  lea     r9, aWorkplacejoin; "WorkplaceJoin"
0x18005f3c9  lea     r8, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows"
0x18005f3d0  lea     rdx, aPolicieswindow; "PoliciesWindows"
0x18005f3d7  lea     rcx, [rbp+57h+var_60]; this
0x18005f3db  call    ?InitializePersistedStatePath@RegistryPath@@QEAAJPEBG00@Z; RegistryPath::InitializePersistedStatePath(ushort const *,ushort const *,ushort const *)
0x18005f3e0  test    eax, eax
0x18005f3e2  js      loc_18005F4F4
0x18005f3e8  xor     r9d, r9d; unsigned int
0x18005f3eb  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x18005f3ef  lea     rdx, aKeypolicy; "KeyPolicy"
0x18005f3f6  lea     rcx, [rbp+57h+var_60]; this
0x18005f3fa  call    ?ReadDwordValue@RegistryPath@@QEBAKPEBGPEAKK@Z; RegistryPath::ReadDwordValue(ushort const *,ulong *,ulong)
0x18005f3ff  mov     edi, [rbp+57h+arg_8]
0x18005f402  test    edi, 0FFFFFFFCh
0x18005f408  jnz     short loc_18005F40F
0x18005f40a  cmp     edi, 2
0x18005f40d  jnz     short loc_18005F463
0x18005f40f  mov     r8d, edi
0x18005f412  mov     rdx, r14
0x18005f415  lea     rcx, aSRegistryKeyPo; "%s: Registry key policy is set to unsup"...
0x18005f41c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005f421  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 4
0x18005f428  jz      short loc_18005F461
0x18005f42a  mov     r8d, edi
0x18005f42d  lea     rdx, UnsupportedRegistryKeyPolicyValueEvent
0x18005f434  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18005f43b  call    McTemplateU0q_EventWriteTransfer
0x18005f440  test    eax, eax
0x18005f442  jz      short loc_18005F461
0x18005f444  mov     r9d, eax
0x18005f447  lea     r8, aEventwriteunsu_0; "EventWriteUnsupportedRegistryKeyPolicyV"...
0x18005f44e  lea     rdx, aLoggerWriteuns; "Logger::WriteUnsupportedRegistryKeyPoli"...
0x18005f455  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18005f45c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005f461  mov     edi, esi
0x18005f463  xor     r9d, r9d; unsigned int
0x18005f466  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x18005f46a  lea     rdx, aHwpolicy; "HwPolicy"
0x18005f471  lea     rcx, [rbp+57h+var_60]; this
0x18005f475  call    ?ReadDwordValue@RegistryPath@@QEBAKPEBGPEAKK@Z; RegistryPath::ReadDwordValue(ushort const *,ulong *,ulong)
0x18005f47a  mov     ebx, [rbp+57h+arg_10]
0x18005f47d  cmp     ebx, 4
0x18005f480  jb      short loc_18005F4D6
0x18005f482  mov     r8d, ebx
0x18005f485  mov     rdx, r14
0x18005f488  lea     rcx, aSRegistryHardw; "%s: Registry hardware policy is set to "...
0x18005f48f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005f494  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 4
0x18005f49b  jz      short loc_18005F4D4
0x18005f49d  mov     r8d, ebx
0x18005f4a0  lea     rdx, UnsupportedRegistryHardwarePolicyValueEvent
0x18005f4a7  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18005f4ae  call    McTemplateU0q_EventWriteTransfer
0x18005f4b3  test    eax, eax
0x18005f4b5  jz      short loc_18005F4D4
0x18005f4b7  mov     r9d, eax
0x18005f4ba  lea     r8, aEventwriteunsu; "EventWriteUnsupportedRegistryHardwarePo"...
0x18005f4c1  lea     rdx, aLoggerWriteuns_0; "Logger::WriteUnsupportedRegistryHardwar"...
0x18005f4c8  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18005f4cf  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005f4d4  mov     ebx, esi
0x18005f4d6  test    edi, edi
0x18005f4d8  jz      short loc_18005F4F4
0x18005f4da  mov     r8d, edi
0x18005f4dd  mov     rdx, r14
0x18005f4e0  lea     rcx, aSRegistryKeyPo_1; "%s: Registry key policy is defined (%lu"...
0x18005f4e7  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18005f4ec  mov     cs:dword_180142598, edi
0x18005f4f2  jmp     short loc_18005F513
0x18005f4f4  mov     cs:dword_180142598, 1
0x18005f4fe  mov     r8d, 1
0x18005f504  mov     rdx, r14
0x18005f507  lea     rcx, aSRegistryKeyPo_0; "%s: Registry key policy is not defined."...
0x18005f50e  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18005f513  mov     rdx, r14
0x18005f516  test    ebx, ebx
0x18005f518  jnz     short loc_18005F53C
0x18005f51a  mov     cs:dword_1801425A0, 1
0x18005f524  lea     r8d, [rbx+1]
0x18005f528  lea     rcx, aSRegistryHardw_1; "%s: Registry hardware policy is not def"...
0x18005f52f  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18005f534  mov     ebx, cs:dword_1801425A0
0x18005f53a  jmp     short loc_18005F551
0x18005f53c  mov     r8d, ebx
0x18005f53f  lea     rcx, aSRegistryHardw_0; "%s: Registry hardware policy is defined"...
0x18005f546  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18005f54b  mov     cs:dword_1801425A0, ebx
0x18005f551  mov     eax, cs:dword_18014259C
0x18005f557  mov     ecx, cs:dword_180142598
0x18005f55d  lea     r9, aTrue_0; "TRUE"
0x18005f564  lea     r8, aFalse_0; "FALSE"
0x18005f56b  cmp     cs:dword_180142594, esi
0x18005f571  cmovz   r9, r8
0x18005f575  mov     [rsp+0B0h+var_80], eax
0x18005f579  mov     [rsp+0B0h+var_88], ebx
0x18005f57d  mov     dword ptr [rsp+0B0h+var_90], ecx
0x18005f581  mov     r8d, cs:dword_180142590
0x18005f588  mov     rdx, r14
0x18005f58b  lea     rcx, aSPlatformIdLuI; "%s: Platform ID = %lu. Is multisession "...
0x18005f592  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18005f597  mov     rdx, r14
0x18005f59a  lea     rcx, aSFinished; "%s finished"
0x18005f5a1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005f5a6  nop
0x18005f5a7  lea     rcx, [rbp+57h+var_60]; this
0x18005f5ab  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x18005f5b0  add     rsp, 90h
0x18005f5b7  pop     r14
0x18005f5b9  pop     rdi
0x18005f5ba  pop     rsi
0x18005f5bb  pop     rbx
0x18005f5bc  pop     rbp
0x18005f5bd  retn
```
